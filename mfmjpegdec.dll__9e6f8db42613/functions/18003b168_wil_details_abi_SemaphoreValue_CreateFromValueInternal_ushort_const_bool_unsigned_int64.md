# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18003b168`
- end: `0x18003b278`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c944`

## callees

- `0x180024220`
- `0x18003b168`
- `0x18003d29c`
- `0x18003d510`
- `0x18003d5f0`
- `0x18003dafc`
- `0x18003dbf8`

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
0x18003b168  mov     [rsp+arg_10], rbx
0x18003b16d  push    rbp
0x18003b16e  push    rsi
0x18003b16f  push    rdi
0x18003b170  sub     rsp, 260h
0x18003b177  mov     rax, cs:__security_cookie
0x18003b17e  xor     rax, rsp
0x18003b181  mov     [rsp+278h+var_28], rax
0x18003b189  mov     rax, 0C000000000000000h
0x18003b193  mov     rbx, r9
0x18003b196  mov     rbp, rcx
0x18003b199  test    rax, r9
0x18003b19c  jz      short loc_18003B1A4
0x18003b19e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003b1a4  mov     r9, rdx; pszSrc
0x18003b1a7  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18003b1ac  mov     edx, 104h; cchDest
0x18003b1b1  call    StringCopyWorkerW
0x18003b1b6  lea     r8, aP0; "_p0"
0x18003b1bd  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18003b1c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b1c7  mov     edx, ebx
0x18003b1c9  lea     r9, [rsp+278h+pszDest]
0x18003b1ce  and     edx, 7FFFFFFFh
0x18003b1d4  mov     esi, 1
0x18003b1d9  mov     r8d, esi
0x18003b1dc  mov     rcx, rbp
0x18003b1df  cmova   r8d, edx
0x18003b1e3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003b1e8  mov     edi, eax
0x18003b1ea  test    eax, eax
0x18003b1ec  jns     short loc_18003B207
0x18003b1ee  mov     rcx, [rsp+278h]; this
0x18003b1f6  mov     r9d, eax; char *
0x18003b1f9  mov     edx, 8Bh; void *
0x18003b1fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b203  mov     eax, edi
0x18003b205  jmp     short loc_18003B255
0x18003b207  lea     r8, asc_1800914F8; "h"
0x18003b20e  shr     rbx, 1Fh
0x18003b212  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18003b217  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b21c  test    ebx, ebx
0x18003b21e  lea     rcx, [rbp+8]
0x18003b222  lea     r9, [rsp+278h+pszDest]
0x18003b227  mov     edx, ebx
0x18003b229  cmovnz  esi, ebx
0x18003b22c  mov     r8d, esi
0x18003b22f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003b234  mov     ebx, eax
0x18003b236  test    eax, eax
0x18003b238  jns     short loc_18003B253
0x18003b23a  mov     rcx, [rsp+278h]; this
0x18003b242  mov     r9d, eax; char *
0x18003b245  mov     edx, 90h; void *
0x18003b24a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b24f  mov     eax, ebx
0x18003b251  jmp     short loc_18003B255
0x18003b253  xor     eax, eax
0x18003b255  mov     rcx, [rsp+278h+var_28]
0x18003b25d  xor     rcx, rsp; StackCookie
0x18003b260  call    __security_check_cookie
0x18003b265  mov     rbx, [rsp+278h+arg_10]
0x18003b26d  add     rsp, 260h
0x18003b274  pop     rdi
0x18003b275  pop     rsi
0x18003b276  pop     rbp
0x18003b277  retn
```
