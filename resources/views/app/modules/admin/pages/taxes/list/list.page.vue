<template>
   <div class="main-content-inner">
      <div class="row">
         <!-- data table start -->
         <div class="col-12 mt-5">
            <div class="card">
               <div class="card-body">
                  <h4 class="header-title relative">Data Table Default</h4>
                  <router-link :to="{ path: '/admin/taxes/create' }" class="relative">
                     <button type="button" class="btn btn-flat btn-outline-secondary px-3 py-2 absolute" style="left: 234px;">add taxe</button>
                  </router-link>
                  <div class="data-tables mt-4 pt-2">
                     <table id="dataTable" class="text-center">
                        <thead class="bg-light text-capitalize">
                           <tr>
                              <th>Name</th>
                              <th>Value</th>
                              <th>Action</th>
                           </tr>
                        </thead>
                        <tbody>
                           <tr v-for="taxe in taxes" :key="taxe.id">
                              <td> {{ taxe.name }} </td>
                              <td> {{ taxe.value }} </td>
                              <td>
                                 <router-link :to="{ path: `/admin/taxes/${taxe.id}/edit` }">
                                    <button type="button" class="btn btn-outline-secondary btn-xs mb-3">
                                    <i class="ti-pencil-alt"></i>
                                    Edit
                                    </button>
                                 </router-link>
                                 <button type="button" v-on:click="taxeDelete($event,taxe.id)" class="btn btn-outline-danger btn-xs mb-3">
                                 <i class="ti-trash"></i>
                                 Delete
                                 </button>
                              </td>
                           </tr>
                        </tbody>
                     </table>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </div>
</template>
<script lang="ts" src="./list.page.ts"></script>