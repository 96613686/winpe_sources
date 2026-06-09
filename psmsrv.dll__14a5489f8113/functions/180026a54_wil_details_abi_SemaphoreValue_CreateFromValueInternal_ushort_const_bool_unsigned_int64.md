# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180026a54`
- end: `0x180026b67`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a554`
- `0x18001a6a8`

## callees

- `0x180004730`
- `0x18001a804`
- `0x18001b7e0`
- `0x180026a54`
- `0x180029200`
- `0x180029c84`
- `0x180029d58`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
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
  StringCopyWorkerW(pszDest, 0x104u, 0, a2, v18);
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
0x180026a54  mov     [rsp+arg_10], rbx
0x180026a59  push    rbp
0x180026a5a  push    rsi
0x180026a5b  push    rdi
0x180026a5c  sub     rsp, 260h
0x180026a63  mov     rax, cs:__security_cookie
0x180026a6a  xor     rax, rsp
0x180026a6d  mov     [rsp+278h+var_28], rax
0x180026a75  mov     rax, 0C000000000000000h
0x180026a7f  mov     rbx, r9
0x180026a82  mov     rbp, rcx
0x180026a85  test    rax, r9
0x180026a88  jz      short loc_180026A90
0x180026a8a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180026a90  mov     r9, rdx; pszSrc
0x180026a93  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180026a98  mov     edx, 104h; cchDest
0x180026a9d  xor     r8d, r8d; pcchNewDestLength
0x180026aa0  call    StringCopyWorkerW
0x180026aa5  lea     r8, aP0; "_p0"
0x180026aac  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180026ab1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026ab6  mov     edx, ebx
0x180026ab8  lea     r9, [rsp+278h+pszDest]
0x180026abd  and     edx, 7FFFFFFFh
0x180026ac3  mov     esi, 1
0x180026ac8  mov     r8d, esi
0x180026acb  mov     rcx, rbp
0x180026ace  cmova   r8d, edx
0x180026ad2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180026ad7  mov     edi, eax
0x180026ad9  test    eax, eax
0x180026adb  jns     short loc_180026AF6
0x180026add  mov     rcx, [rsp+278h]; this
0x180026ae5  mov     r9d, eax; char *
0x180026ae8  mov     edx, 8Bh; void *
0x180026aed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026af2  mov     eax, edi
0x180026af4  jmp     short loc_180026B44
0x180026af6  lea     r8, asc_180036118; "h"
0x180026afd  shr     rbx, 1Fh
0x180026b01  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180026b06  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026b0b  test    ebx, ebx
0x180026b0d  lea     rcx, [rbp+8]
0x180026b11  lea     r9, [rsp+278h+pszDest]
0x180026b16  mov     edx, ebx
0x180026b18  cmovnz  esi, ebx
0x180026b1b  mov     r8d, esi
0x180026b1e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180026b23  mov     ebx, eax
0x180026b25  test    eax, eax
0x180026b27  jns     short loc_180026B42
0x180026b29  mov     rcx, [rsp+278h]; this
0x180026b31  mov     r9d, eax; char *
0x180026b34  mov     edx, 90h; void *
0x180026b39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026b3e  mov     eax, ebx
0x180026b40  jmp     short loc_180026B44
0x180026b42  xor     eax, eax
0x180026b44  mov     rcx, [rsp+278h+var_28]
0x180026b4c  xor     rcx, rsp; StackCookie
0x180026b4f  call    __security_check_cookie
0x180026b54  mov     rbx, [rsp+278h+arg_10]
0x180026b5c  add     rsp, 260h
0x180026b63  pop     rdi
0x180026b64  pop     rsi
0x180026b65  pop     rbp
0x180026b66  retn
```
