# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005514`
- end: `0x180005632`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800064b4`

## callees

- `0x1800036f0`
- `0x180005514`
- `0x180006a74`
- `0x180006f90`
- `0x180007120`
- `0x180007558`
- `0x180007664`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            pszDest);
    v15 = v14;
    if ( v14 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v14,
        v17);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x180005514  mov     [rsp+arg_10], rbx
0x180005519  push    rbp
0x18000551a  push    rsi
0x18000551b  push    rdi
0x18000551c  sub     rsp, 260h
0x180005523  mov     rax, cs:__security_cookie
0x18000552a  xor     rax, rsp
0x18000552d  mov     [rsp+278h+var_28], rax
0x180005535  mov     rax, 0C000000000000000h
0x18000553f  mov     rbx, r9
0x180005542  mov     rbp, rcx
0x180005545  test    rax, r9
0x180005548  jz      short loc_180005550
0x18000554a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005550  mov     r9, rdx; pszSrc
0x180005553  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180005558  mov     edx, 104h; cchDest
0x18000555d  call    StringCopyWorkerW
0x180005562  lea     r8, aP0; "_p0"
0x180005569  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000556e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005573  mov     edx, ebx
0x180005575  lea     r9, [rsp+278h+pszDest]
0x18000557a  and     edx, 7FFFFFFFh
0x180005580  mov     esi, 1
0x180005585  mov     r8d, esi
0x180005588  mov     rcx, rbp
0x18000558b  cmova   r8d, edx
0x18000558f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005594  mov     edi, eax
0x180005596  test    eax, eax
0x180005598  jns     short loc_1800055BA
0x18000559a  mov     rcx, [rsp+278h]; this
0x1800055a2  lea     r8, aWil; "wil"
0x1800055a9  mov     r9d, eax; char *
0x1800055ac  mov     edx, 8Bh; void *
0x1800055b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055b6  mov     eax, edi
0x1800055b8  jmp     short loc_18000560F
0x1800055ba  lea     r8, asc_18002D950; "h"
0x1800055c1  shr     rbx, 1Fh
0x1800055c5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800055ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800055cf  test    ebx, ebx
0x1800055d1  lea     rcx, [rbp+8]
0x1800055d5  lea     r9, [rsp+278h+pszDest]
0x1800055da  mov     edx, ebx
0x1800055dc  cmovnz  esi, ebx
0x1800055df  mov     r8d, esi
0x1800055e2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800055e7  mov     ebx, eax
0x1800055e9  test    eax, eax
0x1800055eb  jns     short loc_18000560D
0x1800055ed  mov     rcx, [rsp+278h]; this
0x1800055f5  lea     r8, aWil; "wil"
0x1800055fc  mov     r9d, eax; char *
0x1800055ff  mov     edx, 90h; void *
0x180005604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005609  mov     eax, ebx
0x18000560b  jmp     short loc_18000560F
0x18000560d  xor     eax, eax
0x18000560f  mov     rcx, [rsp+278h+var_28]
0x180005617  xor     rcx, rsp; StackCookie
0x18000561a  call    __security_check_cookie
0x18000561f  mov     rbx, [rsp+278h+arg_10]
0x180005627  add     rsp, 260h
0x18000562e  pop     rdi
0x18000562f  pop     rsi
0x180005630  pop     rbp
0x180005631  retn
```
