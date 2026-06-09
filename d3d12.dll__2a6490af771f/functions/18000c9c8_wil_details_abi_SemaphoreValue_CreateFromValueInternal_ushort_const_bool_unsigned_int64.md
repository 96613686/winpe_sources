# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000c9c8`
- end: `0x18000cad8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d32c`
- `0x18000d450`

## callees

- `0x180007844`
- `0x180007a28`
- `0x180009d5c`
- `0x18000b410`
- `0x18000c9c8`
- `0x18000dfd0`
- `0x18000e098`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x18000c9c8  mov     [rsp+arg_10], rbx
0x18000c9cd  push    rbp
0x18000c9ce  push    rsi
0x18000c9cf  push    rdi
0x18000c9d0  sub     rsp, 260h
0x18000c9d7  mov     rax, cs:__security_cookie
0x18000c9de  xor     rax, rsp
0x18000c9e1  mov     [rsp+278h+var_28], rax
0x18000c9e9  mov     rax, 0C000000000000000h
0x18000c9f3  mov     rbx, r9
0x18000c9f6  mov     rbp, rcx
0x18000c9f9  test    rax, r9
0x18000c9fc  jz      short loc_18000CA04
0x18000c9fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ca04  mov     r9, rdx; pszSrc
0x18000ca07  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000ca0c  mov     edx, 104h; cchDest
0x18000ca11  call    StringCopyWorkerW
0x18000ca16  lea     r8, aP0; "_p0"
0x18000ca1d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000ca22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ca27  mov     edx, ebx
0x18000ca29  lea     r9, [rsp+278h+pszDest]
0x18000ca2e  and     edx, 7FFFFFFFh
0x18000ca34  mov     esi, 1
0x18000ca39  mov     r8d, esi
0x18000ca3c  mov     rcx, rbp
0x18000ca3f  cmova   r8d, edx
0x18000ca43  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ca48  mov     edi, eax
0x18000ca4a  test    eax, eax
0x18000ca4c  jns     short loc_18000CA67
0x18000ca4e  mov     rcx, [rsp+278h]; this
0x18000ca56  mov     r9d, eax; char *
0x18000ca59  mov     edx, 8Bh; void *
0x18000ca5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca63  mov     eax, edi
0x18000ca65  jmp     short loc_18000CAB5
0x18000ca67  lea     r8, asc_180017098; "h"
0x18000ca6e  shr     rbx, 1Fh
0x18000ca72  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000ca77  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ca7c  test    ebx, ebx
0x18000ca7e  lea     rcx, [rbp+8]
0x18000ca82  lea     r9, [rsp+278h+pszDest]
0x18000ca87  mov     edx, ebx
0x18000ca89  cmovnz  esi, ebx
0x18000ca8c  mov     r8d, esi
0x18000ca8f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ca94  mov     ebx, eax
0x18000ca96  test    eax, eax
0x18000ca98  jns     short loc_18000CAB3
0x18000ca9a  mov     rcx, [rsp+278h]; this
0x18000caa2  mov     r9d, eax; char *
0x18000caa5  mov     edx, 90h; void *
0x18000caaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000caaf  mov     eax, ebx
0x18000cab1  jmp     short loc_18000CAB5
0x18000cab3  xor     eax, eax
0x18000cab5  mov     rcx, [rsp+278h+var_28]
0x18000cabd  xor     rcx, rsp; StackCookie
0x18000cac0  call    __security_check_cookie
0x18000cac5  mov     rbx, [rsp+278h+arg_10]
0x18000cacd  add     rsp, 260h
0x18000cad4  pop     rdi
0x18000cad5  pop     rsi
0x18000cad6  pop     rbp
0x18000cad7  retn
```
