# MergeSdbp_InitWaitEventAndWorker(MergeSdbWaitEventWorkerPair *,ulong (*)(void *),void *)

- ea: `0x18004a824`
- end: `0x18004a9e9`
- name: `?MergeSdbp_InitWaitEventAndWorker@@YAKPEAUMergeSdbWaitEventWorkerPair@@P6AKPEAX@Z1@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct MergeSdbWaitEventWorkerPair *, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004a580`

## callees

- `0x180012920`
- `0x18004a640`
- `0x18004a824`
- `0x18004aa34`
- `0x18004aa5c`
- `0x18004ac18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a848`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a890`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a8d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a848`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a890`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a94a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004a935`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004a935`

## string_xrefs

- `0x18004a863`: `Failed to create wait event [%d]`
- `0x18004a8ab`: `Failed to create wait event [%d]`
- `0x18004a8f3`: `Failed to create wait event [%d]`
- `0x18004a956`: `Failed to create the worker thread [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MergeSdbp_InitWaitEventAndWorker(
        struct MergeSdbWaitEventWorkerPair *a1,
        unsigned int (*a2)(void *),
        void *a3)
{
  DWORD LastError; // ebx
  _QWORD v6[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int (*v7)(void *); // [rsp+58h] [rbp+18h] BYREF
  HANDLE EventW; // [rsp+60h] [rbp+20h] BYREF
  HANDLE v9; // [rsp+68h] [rbp+28h] BYREF

  EventW = a3;
  v7 = a2;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v7 = (unsigned int (*)(void *))CreateEventW(0, 0, 0, 0);
    if ( v7 )
    {
      v9 = CreateEventW(0, 0, 0, 0);
      if ( v9 )
      {
        v6[0] = CreateThread(0, 0, MergeSdb_WorkerScanAndMerge, 0, 4u, 0);
        if ( ((v6[0] + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          _swap___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAXAEAV12__Z(
            a1,
            &EventW);
          _swap___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAXAEAV12__Z(
            (char *)a1 + 8,
            &v7);
          _swap___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAXAEAV12__Z(
            (char *)a1 + 16,
            &v9);
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::swap(
            (char *)a1 + 24,
            v6);
          g_MergeSdbScanRegistryState = 1;
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbp_InitWaitEventAndWorker",
            412,
            (unsigned int)"Failed to create the worker thread [%d]");
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6);
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbp_InitWaitEventAndWorker",
          398,
          (unsigned int)"Failed to create wait event [%d]");
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v9);
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbp_InitWaitEventAndWorker",
        391,
        (unsigned int)"Failed to create wait event [%d]");
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v7);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbp_InitWaitEventAndWorker",
      384,
      (unsigned int)"Failed to create wait event [%d]");
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventW);
  return LastError;
}

```

## disassembly

```asm
0x18004a824  mov     [rsp-8+arg_0], rbx
0x18004a829  mov     [rsp-8+arg_10], r8
0x18004a82e  mov     [rsp-8+arg_8], rdx
0x18004a833  push    rbp
0x18004a834  mov     rbp, rsp
0x18004a837  sub     rsp, 40h
0x18004a83b  mov     rbx, rcx
0x18004a83e  xor     r9d, r9d; lpName
0x18004a841  xor     r8d, r8d; bInitialState
0x18004a844  xor     edx, edx; bManualReset
0x18004a846  xor     ecx, ecx; lpEventAttributes
0x18004a848  call    cs:__imp_CreateEventW
0x18004a84e  mov     [rbp+arg_10], rax
0x18004a852  test    rax, rax
0x18004a855  jnz     short loc_18004A886
0x18004a857  call    cs:__imp_GetLastError
0x18004a85d  mov     ebx, eax
0x18004a85f  mov     [rsp+40h+dwCreationFlags], eax
0x18004a863  lea     r9, aFailedToCreate_43; "Failed to create wait event [%d]"
0x18004a86a  mov     r8d, 180h
0x18004a870  lea     rdx, aMergesdbpInitw; "MergeSdbp_InitWaitEventAndWorker"
0x18004a877  mov     ecx, 1
0x18004a87c  call    AslLogCallPrintf
0x18004a881  jmp     loc_18004A9D3
0x18004a886  xor     r9d, r9d; lpName
0x18004a889  xor     r8d, r8d; bInitialState
0x18004a88c  xor     edx, edx; bManualReset
0x18004a88e  xor     ecx, ecx; lpEventAttributes
0x18004a890  call    cs:__imp_CreateEventW
0x18004a896  mov     [rbp+arg_8], rax
0x18004a89a  test    rax, rax
0x18004a89d  jnz     short loc_18004A8CE
0x18004a89f  call    cs:__imp_GetLastError
0x18004a8a5  mov     ebx, eax
0x18004a8a7  mov     [rsp+40h+dwCreationFlags], eax
0x18004a8ab  lea     r9, aFailedToCreate_43; "Failed to create wait event [%d]"
0x18004a8b2  mov     r8d, 187h
0x18004a8b8  lea     rdx, aMergesdbpInitw; "MergeSdbp_InitWaitEventAndWorker"
0x18004a8bf  mov     ecx, 1
0x18004a8c4  call    AslLogCallPrintf
0x18004a8c9  jmp     loc_18004A9C9
0x18004a8ce  xor     r9d, r9d; lpName
0x18004a8d1  xor     r8d, r8d; bInitialState
0x18004a8d4  xor     edx, edx; bManualReset
0x18004a8d6  xor     ecx, ecx; lpEventAttributes
0x18004a8d8  call    cs:__imp_CreateEventW
0x18004a8de  mov     [rbp+arg_18], rax
0x18004a8e2  test    rax, rax
0x18004a8e5  jnz     short loc_18004A916
0x18004a8e7  call    cs:__imp_GetLastError
0x18004a8ed  mov     ebx, eax
0x18004a8ef  mov     [rsp+40h+dwCreationFlags], eax
0x18004a8f3  lea     r9, aFailedToCreate_43; "Failed to create wait event [%d]"
0x18004a8fa  mov     r8d, 18Eh
0x18004a900  lea     rdx, aMergesdbpInitw; "MergeSdbp_InitWaitEventAndWorker"
0x18004a907  mov     ecx, 1
0x18004a90c  call    AslLogCallPrintf
0x18004a911  jmp     loc_18004A9BF
0x18004a916  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x18004a91f  mov     [rsp+40h+dwCreationFlags], 4; dwCreationFlags
0x18004a927  xor     r9d, r9d; lpParameter
0x18004a92a  lea     r8, ?MergeSdb_WorkerScanAndMerge@@YAKPEAX@Z; lpStartAddress
0x18004a931  xor     edx, edx; dwStackSize
0x18004a933  xor     ecx, ecx; lpThreadAttributes
0x18004a935  call    cs:__imp_CreateThread
0x18004a93b  mov     [rbp+var_10], rax
0x18004a93f  inc     rax
0x18004a942  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004a948  jnz     short loc_18004A976
0x18004a94a  call    cs:__imp_GetLastError
0x18004a950  mov     ebx, eax
0x18004a952  mov     [rsp+40h+dwCreationFlags], eax
0x18004a956  lea     r9, aFailedToCreate_99; "Failed to create the worker thread [%d]"
0x18004a95d  mov     r8d, 19Ch
0x18004a963  lea     rdx, aMergesdbpInitw; "MergeSdbp_InitWaitEventAndWorker"
0x18004a96a  mov     ecx, 1
0x18004a96f  call    AslLogCallPrintf
0x18004a974  jmp     short loc_18004A9B5
0x18004a976  lea     rdx, [rbp+arg_10]
0x18004a97a  mov     rcx, rbx
0x18004a97d  call    ?swap@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAXAEAV12@@Z
0x18004a982  lea     rcx, [rbx+8]
0x18004a986  lea     rdx, [rbp+arg_8]
0x18004a98a  call    ?swap@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAXAEAV12@@Z
0x18004a98f  lea     rcx, [rbx+10h]
0x18004a993  lea     rdx, [rbp+arg_18]
0x18004a997  call    ?swap@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAXAEAV12@@Z
0x18004a99c  lea     rcx, [rbx+18h]
0x18004a9a0  lea     rdx, [rbp+var_10]
0x18004a9a4  call    ?swap@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18004a9a9  mov     cs:?g_MergeSdbScanRegistryState@@3KA, 1; ulong g_MergeSdbScanRegistryState
0x18004a9b3  xor     ebx, ebx
0x18004a9b5  lea     rcx, [rbp+var_10]
0x18004a9b9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004a9be  nop
0x18004a9bf  lea     rcx, [rbp+arg_18]
0x18004a9c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004a9c8  nop
0x18004a9c9  lea     rcx, [rbp+arg_8]
0x18004a9cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004a9d2  nop
0x18004a9d3  lea     rcx, [rbp+arg_10]
0x18004a9d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004a9dc  mov     eax, ebx
0x18004a9de  mov     rbx, [rsp+40h+arg_0]
0x18004a9e3  add     rsp, 40h
0x18004a9e7  pop     rbp
0x18004a9e8  retn
```
