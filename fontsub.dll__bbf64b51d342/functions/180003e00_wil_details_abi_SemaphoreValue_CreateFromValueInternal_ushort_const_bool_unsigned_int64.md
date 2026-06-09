# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003e00`
- end: `0x180003f10`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000509c`

## callees

- `0x180003e00`
- `0x180005a94`
- `0x180006ac4`
- `0x180006ba4`
- `0x180007074`
- `0x1800070f4`
- `0x18001ac90`

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
0x180003e00  mov     [rsp+arg_10], rbx
0x180003e05  push    rbp
0x180003e06  push    rsi
0x180003e07  push    rdi
0x180003e08  sub     rsp, 260h
0x180003e0f  mov     rax, cs:__security_cookie
0x180003e16  xor     rax, rsp
0x180003e19  mov     [rsp+278h+var_28], rax
0x180003e21  mov     rax, 0C000000000000000h
0x180003e2b  mov     rbx, r9
0x180003e2e  mov     rbp, rcx
0x180003e31  test    rax, r9
0x180003e34  jz      short loc_180003E3C
0x180003e36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e3c  mov     r9, rdx; pszSrc
0x180003e3f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180003e44  mov     edx, 104h; cchDest
0x180003e49  call    StringCopyWorkerW
0x180003e4e  lea     r8, aP0; "_p0"
0x180003e55  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180003e5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e5f  mov     edx, ebx
0x180003e61  lea     r9, [rsp+278h+pszDest]
0x180003e66  and     edx, 7FFFFFFFh
0x180003e6c  mov     esi, 1
0x180003e71  mov     r8d, esi
0x180003e74  mov     rcx, rbp
0x180003e77  cmova   r8d, edx
0x180003e7b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003e80  mov     edi, eax
0x180003e82  test    eax, eax
0x180003e84  jns     short loc_180003E9F
0x180003e86  mov     rcx, [rsp+278h]; this
0x180003e8e  mov     r9d, eax; char *
0x180003e91  mov     edx, 8Bh; void *
0x180003e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e9b  mov     eax, edi
0x180003e9d  jmp     short loc_180003EED
0x180003e9f  lea     r8, asc_18001D798; "h"
0x180003ea6  shr     rbx, 1Fh
0x180003eaa  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180003eaf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003eb4  test    ebx, ebx
0x180003eb6  lea     rcx, [rbp+8]
0x180003eba  lea     r9, [rsp+278h+pszDest]
0x180003ebf  mov     edx, ebx
0x180003ec1  cmovnz  esi, ebx
0x180003ec4  mov     r8d, esi
0x180003ec7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003ecc  mov     ebx, eax
0x180003ece  test    eax, eax
0x180003ed0  jns     short loc_180003EEB
0x180003ed2  mov     rcx, [rsp+278h]; this
0x180003eda  mov     r9d, eax; char *
0x180003edd  mov     edx, 90h; void *
0x180003ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ee7  mov     eax, ebx
0x180003ee9  jmp     short loc_180003EED
0x180003eeb  xor     eax, eax
0x180003eed  mov     rcx, [rsp+278h+var_28]
0x180003ef5  xor     rcx, rsp; StackCookie
0x180003ef8  call    __security_check_cookie
0x180003efd  mov     rbx, [rsp+278h+arg_10]
0x180003f05  add     rsp, 260h
0x180003f0c  pop     rdi
0x180003f0d  pop     rsi
0x180003f0e  pop     rbp
0x180003f0f  retn
```
