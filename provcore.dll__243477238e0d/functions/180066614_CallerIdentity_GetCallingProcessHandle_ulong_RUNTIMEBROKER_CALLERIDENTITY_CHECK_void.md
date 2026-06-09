# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180066614`
- end: `0x180066700`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `236`
- prototype: `HRESULT __fastcall(unsigned int runtimeBrokerCheck, RUNTIMEBROKER_CALLERIDENTITY_CHECK phProcess, void **dwProcessAccessFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180066524`
- `0x1800665f0`

## callees

- `0x1800071f4`
- `0x180066614`
- `0x1800668d8`
- `0x180066cd4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066682`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066682`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180066698`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180066698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800666a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800666a9`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18006664d`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18006664d`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(
        unsigned int runtimeBrokerCheck,
        RUNTIMEBROKER_CALLERIDENTITY_CHECK phProcess,
        void **dwProcessAccessFlags)
{
  int v5; // eax
  int v6; // edi
  CallerIdentity *v7; // rcx
  void *retaddr; // [rsp+28h] [rbp+0h]
  Microsoft::WRL::ComPtr<ICallingProcessInfo> spCallingProcessInfo; // [rsp+40h] [rbp+18h] BYREF

  *dwProcessAccessFlags = 0;
  spCallingProcessInfo.ptr_ = 0;
  Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease((Microsoft::WRL::ComPtr<IApplicationResolver> *)&spCallingProcessInfo);
  v5 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, (void **)&spCallingProcessInfo.ptr_);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147417833 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x58u, "onecore\\shell\\lib\\calleridentity\\calleridentity.cpp", v5);
      goto LABEL_11;
    }
    *dwProcessAccessFlags = GetCurrentProcess();
  }
  else
  {
    v6 = spCallingProcessInfo.ptr_->OpenCallerProcessHandle(spCallingProcessInfo.ptr_, 4096u, dwProcessAccessFlags);
    if ( v6 < 0 )
      goto LABEL_11;
  }
  if ( phProcess != RCC_FAIL_IF_RUNTIMEBROKER
    || (CallerIdentity::_EnsureRuntimeBrokerPID(v7),
        GetProcessId(*dwProcessAccessFlags) != CallerIdentity::g_dwRuntimeBrokerProcessId) )
  {
    Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease((Microsoft::WRL::ComPtr<IApplicationResolver> *)&spCallingProcessInfo);
    return 0;
  }
  CloseHandle(*dwProcessAccessFlags);
  *dwProcessAccessFlags = 0;
  v6 = -2147467259;
LABEL_11:
  Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease((Microsoft::WRL::ComPtr<IApplicationResolver> *)&spCallingProcessInfo);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180066614  mov     rax, rsp
0x180066617  mov     [rax+8], rbx
0x18006661b  mov     [rax+10h], rsi
0x18006661f  push    rdi
0x180066620  sub     rsp, 20h
0x180066624  lea     rcx, [rax+18h]; this
0x180066628  mov     qword ptr [phProcess], 0
0x18006662f  mov     rbx, phProcess
0x180066632  mov     qword ptr [rax+18h], 0
0x18006663a  mov     esi, runtimeBrokerCheck
0x18006663c  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x180066641  lea     rdx, [rsp+28h+spCallingProcessInfo]; ppInterface
0x180066646  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18006664d  call    cs:__imp_CoGetCallContext
0x180066653  mov     edi, eax
0x180066655  test    eax, eax
0x180066657  js      short loc_18006667A
0x180066659  mov     rcx, [rsp+28h+spCallingProcessInfo.ptr_]
0x18006665e  mov     phProcess, rbx
0x180066661  mov     runtimeBrokerCheck, 1000h
0x180066666  mov     rax, [rcx]
0x180066669  mov     rax, [rax+18h]
0x18006666d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066672  mov     edi, eax
0x180066674  test    eax, eax
0x180066676  jns     short loc_18006668B
0x180066678  jmp     short loc_1800666E4
0x18006667a  cmp     edi, 80010117h
0x180066680  jnz     short loc_1800666CB
0x180066682  call    cs:__imp_GetCurrentProcess
0x180066688  mov     [rbx], rax
0x18006668b  cmp     esi, 1
0x18006668e  jnz     short loc_1800666BD
0x180066690  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x180066695  mov     rcx, [rbx]; Process
0x180066698  call    cs:__imp_GetProcessId
0x18006669e  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800666a4  jnz     short loc_1800666BD
0x1800666a6  mov     rcx, [rbx]; hObject
0x1800666a9  call    cs:__imp_CloseHandle
0x1800666af  mov     qword ptr [rbx], 0
0x1800666b6  mov     edi, 80004005h
0x1800666bb  jmp     short loc_1800666E4
0x1800666bd  lea     rcx, [rsp+28h+spCallingProcessInfo]; this
0x1800666c2  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x1800666c7  xor     eax, eax
0x1800666c9  jmp     short loc_1800666F0
0x1800666cb  mov     rcx, [rsp+28h]; callerReturnAddress
0x1800666d0  lea     phProcess, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800666d7  mov     r9d, edi; hr
0x1800666da  mov     runtimeBrokerCheck, 58h ; 'X'; lineNumber
0x1800666df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800666e4  lea     rcx, [rsp+28h+spCallingProcessInfo]; this
0x1800666e9  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x1800666ee  mov     eax, edi
0x1800666f0  mov     rbx, [rsp+28h+arg_0]
0x1800666f5  mov     rsi, [rsp+28h+arg_8]
0x1800666fa  add     rsp, 20h
0x1800666fe  pop     rdi
0x1800666ff  retn
```
