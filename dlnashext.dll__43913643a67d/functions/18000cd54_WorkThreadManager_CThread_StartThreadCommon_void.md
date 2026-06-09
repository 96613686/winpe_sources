# WorkThreadManager::CThread::StartThreadCommon(void)

- ea: `0x18000cd54`
- end: `0x18000cec6`
- name: `?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ`
- size: `370`
- prototype: `__int64 __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007880`
- `0x18000c3f4`

## callees

- `0x180008f50`
- `0x18000a610`
- `0x18000c548`
- `0x18000cd54`
- `0x18000cecc`
- `0x180011954`
- `0x1800316f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ceb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ceb2`

## string_xrefs

- `0x18000cd73`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000cd91`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CThread::StartThreadCommon(
        WorkThreadManager::CThread *this,
        __int64 a2,
        __int64 a3)
{
  int inited; // eax
  __int64 v5; // r8
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  __int64 v7; // rdx
  __int64 *v9; // rsi
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  inited = wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___((__int64)this, a2, a3);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)inited,
      v14);
    v7 = 654;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  v9 = (__int64 *)((char *)this + 104);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((wil::details **)this + 13, 0, v5);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v7 = 656;
    goto LABEL_3;
  }
  v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
  {
    v11 = *v9;
    v10[1] = (char *)this + 132;
    v10[3] = v11;
    *v10 = &CRefThread::`vftable';
    *((_DWORD *)v10 + 4) = 0;
    *((_DWORD *)this + 33) = 1;
  }
  Microsoft::WRL::ComPtr<CRefThread>::Attach((char *)this + 112, v10);
  if ( !*((_QWORD *)this + 14) )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2147024882;
    v7 = 659;
    goto LABEL_3;
  }
  v12 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
  {
    v13 = *v9;
    v12[1] = (char *)this + 84;
    v12[3] = v13;
    *v12 = &CRefThread::`vftable';
    *((_DWORD *)v12 + 4) = 0;
    *((_DWORD *)this + 21) = 1;
  }
  Microsoft::WRL::ComPtr<CRefThread>::Attach((char *)this + 120, v12);
  if ( !*((_QWORD *)this + 15) )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2147024882;
    v7 = 662;
    goto LABEL_3;
  }
  *((_QWORD *)this + 17) = *((_QWORD *)this + 14);
  *((_DWORD *)this + 32) = (*((_DWORD *)this + 19) | (*((_DWORD *)this + 18) << 24)) + 1;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    0);
  GetModuleHandleExW(4u, (LPCWSTR)SHTaskPoolQueueTask, (HMODULE *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x18000cd54  push    rbx
0x18000cd56  push    rsi
0x18000cd57  push    rdi
0x18000cd58  push    r12
0x18000cd5a  push    r14
0x18000cd5c  sub     rsp, 30h
0x18000cd60  mov     rdi, rcx
0x18000cd63  call    wil__init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___
0x18000cd68  mov     ebx, eax
0x18000cd6a  test    eax, eax
0x18000cd6c  jns     short loc_18000CDA7
0x18000cd6e  mov     rcx, [rsp+58h]; this
0x18000cd73  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000cd7a  mov     r9d, eax; char *
0x18000cd7d  mov     edx, 70h ; 'p'; void *
0x18000cd82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd87  mov     edx, 28Eh; void *
0x18000cd8c  mov     rcx, [rsp+58h]; this
0x18000cd91  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000cd98  mov     r9d, ebx; char *
0x18000cd9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cda0  mov     eax, ebx
0x18000cda2  jmp     loc_18000CEBA
0x18000cda7  lea     rsi, [rdi+68h]
0x18000cdab  xor     edx, edx
0x18000cdad  mov     rcx, rsi
0x18000cdb0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cdb5  mov     ebx, eax
0x18000cdb7  test    eax, eax
0x18000cdb9  jns     short loc_18000CDC2
0x18000cdbb  mov     edx, 290h
0x18000cdc0  jmp     short loc_18000CD8C
0x18000cdc2  mov     ebx, 20h ; ' '
0x18000cdc7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cdce  mov     ecx, ebx; unsigned __int64
0x18000cdd0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cdd5  lea     r12, ??_7CRefThread@@6B@; const CRefThread::`vftable'
0x18000cddc  test    rax, rax
0x18000cddf  jz      short loc_18000CE03
0x18000cde1  mov     rdx, [rsi]
0x18000cde4  lea     rcx, [rdi+84h]
0x18000cdeb  mov     [rax+8], rcx
0x18000cdef  mov     [rax+18h], rdx
0x18000cdf3  mov     [rax], r12
0x18000cdf6  mov     dword ptr [rax+10h], 0
0x18000cdfd  mov     dword ptr [rcx], 1
0x18000ce03  lea     r14, [rdi+70h]
0x18000ce07  mov     rdx, rax
0x18000ce0a  mov     rcx, r14
0x18000ce0d  call    ?Attach@?$ComPtr@VCRefThread@@@WRL@Microsoft@@QEAAXPEAVCRefThread@@@Z; Microsoft::WRL::ComPtr<CRefThread>::Attach(CRefThread *)
0x18000ce12  cmp     qword ptr [r14], 0
0x18000ce16  jnz     short loc_18000CE27
0x18000ce18  mov     ebx, 8007000Eh
0x18000ce1d  mov     edx, 293h
0x18000ce22  jmp     loc_18000CD8C
0x18000ce27  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ce2e  mov     rcx, rbx; unsigned __int64
0x18000ce31  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ce36  test    rax, rax
0x18000ce39  jz      short loc_18000CE5A
0x18000ce3b  mov     rdx, [rsi]
0x18000ce3e  lea     rcx, [rdi+54h]
0x18000ce42  mov     [rax+8], rcx
0x18000ce46  mov     [rax+18h], rdx
0x18000ce4a  mov     [rax], r12
0x18000ce4d  mov     dword ptr [rax+10h], 0
0x18000ce54  mov     dword ptr [rcx], 1
0x18000ce5a  mov     rdx, rax
0x18000ce5d  lea     rcx, [rdi+78h]
0x18000ce61  call    ?Attach@?$ComPtr@VCRefThread@@@WRL@Microsoft@@QEAAXPEAVCRefThread@@@Z; Microsoft::WRL::ComPtr<CRefThread>::Attach(CRefThread *)
0x18000ce66  cmp     qword ptr [rdi+78h], 0
0x18000ce6b  jnz     short loc_18000CE7C
0x18000ce6d  mov     ebx, 8007000Eh
0x18000ce72  mov     edx, 296h
0x18000ce77  jmp     loc_18000CD8C
0x18000ce7c  mov     rax, [r14]
0x18000ce7f  lea     rcx, [rdi+40h]
0x18000ce83  mov     [rdi+88h], rax
0x18000ce8a  xor     edx, edx
0x18000ce8c  mov     eax, [rdi+48h]
0x18000ce8f  shl     eax, 18h
0x18000ce92  or      eax, [rdi+4Ch]
0x18000ce95  inc     eax
0x18000ce97  mov     [rdi+80h], eax
0x18000ce9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000cea2  lea     r8, [rdi+40h]; phModule
0x18000cea6  mov     ecx, 4; dwFlags
0x18000ceab  lea     rdx, SHTaskPoolQueueTask; lpModuleName
0x18000ceb2  call    cs:__imp_GetModuleHandleExW
0x18000ceb8  xor     eax, eax
0x18000ceba  add     rsp, 30h
0x18000cebe  pop     r14
0x18000cec0  pop     r12
0x18000cec2  pop     rdi
0x18000cec3  pop     rsi
0x18000cec4  pop     rbx
0x18000cec5  retn
```
