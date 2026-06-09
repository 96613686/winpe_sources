# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180012998`
- end: `0x180012aa8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001420c`
- `0x180014338`

## callees

- `0x180012998`
- `0x18001539c`
- `0x180015a5c`
- `0x180015b3c`
- `0x1800166c8`
- `0x180016818`
- `0x180018950`

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
0x180012998  mov     [rsp+arg_10], rbx
0x18001299d  push    rbp
0x18001299e  push    rsi
0x18001299f  push    rdi
0x1800129a0  sub     rsp, 260h
0x1800129a7  mov     rax, cs:__security_cookie
0x1800129ae  xor     rax, rsp
0x1800129b1  mov     [rsp+278h+var_28], rax
0x1800129b9  mov     rax, 0C000000000000000h
0x1800129c3  mov     rbx, r9
0x1800129c6  mov     rbp, rcx
0x1800129c9  test    rax, r9
0x1800129cc  jz      short loc_1800129D4
0x1800129ce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800129d4  mov     r9, rdx; pszSrc
0x1800129d7  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800129dc  mov     edx, 104h; cchDest
0x1800129e1  call    StringCopyWorkerW
0x1800129e6  lea     r8, aP0; "_p0"
0x1800129ed  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800129f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800129f7  mov     edx, ebx
0x1800129f9  lea     r9, [rsp+278h+pszDest]
0x1800129fe  and     edx, 7FFFFFFFh
0x180012a04  mov     esi, 1
0x180012a09  mov     r8d, esi
0x180012a0c  mov     rcx, rbp
0x180012a0f  cmova   r8d, edx
0x180012a13  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180012a18  mov     edi, eax
0x180012a1a  test    eax, eax
0x180012a1c  jns     short loc_180012A37
0x180012a1e  mov     rcx, [rsp+278h]; this
0x180012a26  mov     r9d, eax; char *
0x180012a29  mov     edx, 8Bh; void *
0x180012a2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a33  mov     eax, edi
0x180012a35  jmp     short loc_180012A85
0x180012a37  lea     r8, asc_180020928; "h"
0x180012a3e  shr     rbx, 1Fh
0x180012a42  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180012a47  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012a4c  test    ebx, ebx
0x180012a4e  lea     rcx, [rbp+8]
0x180012a52  lea     r9, [rsp+278h+pszDest]
0x180012a57  mov     edx, ebx
0x180012a59  cmovnz  esi, ebx
0x180012a5c  mov     r8d, esi
0x180012a5f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180012a64  mov     ebx, eax
0x180012a66  test    eax, eax
0x180012a68  jns     short loc_180012A83
0x180012a6a  mov     rcx, [rsp+278h]; this
0x180012a72  mov     r9d, eax; char *
0x180012a75  mov     edx, 90h; void *
0x180012a7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a7f  mov     eax, ebx
0x180012a81  jmp     short loc_180012A85
0x180012a83  xor     eax, eax
0x180012a85  mov     rcx, [rsp+278h+var_28]
0x180012a8d  xor     rcx, rsp; StackCookie
0x180012a90  call    __security_check_cookie
0x180012a95  mov     rbx, [rsp+278h+arg_10]
0x180012a9d  add     rsp, 260h
0x180012aa4  pop     rdi
0x180012aa5  pop     rsi
0x180012aa6  pop     rbp
0x180012aa7  retn
```
