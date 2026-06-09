# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180025660`
- end: `0x18002577e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026068`
- `0x1800283dc`

## callees

- `0x1800210f0`
- `0x180025660`
- `0x1800264a4`
- `0x1800269c0`
- `0x180026aa0`
- `0x180026e40`
- `0x180026f04`

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
0x180025660  mov     [rsp+arg_10], rbx
0x180025665  push    rbp
0x180025666  push    rsi
0x180025667  push    rdi
0x180025668  sub     rsp, 260h
0x18002566f  mov     rax, cs:__security_cookie
0x180025676  xor     rax, rsp
0x180025679  mov     [rsp+278h+var_28], rax
0x180025681  mov     rax, 0C000000000000000h
0x18002568b  mov     rbx, r9
0x18002568e  mov     rbp, rcx
0x180025691  test    rax, r9
0x180025694  jz      short loc_18002569C
0x180025696  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002569c  mov     r9, rdx; pszSrc
0x18002569f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800256a4  mov     edx, 104h; cchDest
0x1800256a9  call    StringCopyWorkerW
0x1800256ae  lea     r8, aP0; "_p0"
0x1800256b5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800256ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800256bf  mov     edx, ebx
0x1800256c1  lea     r9, [rsp+278h+pszDest]
0x1800256c6  and     edx, 7FFFFFFFh
0x1800256cc  mov     esi, 1
0x1800256d1  mov     r8d, esi
0x1800256d4  mov     rcx, rbp
0x1800256d7  cmova   r8d, edx
0x1800256db  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800256e0  mov     edi, eax
0x1800256e2  test    eax, eax
0x1800256e4  jns     short loc_180025706
0x1800256e6  mov     rcx, [rsp+278h]; this
0x1800256ee  lea     r8, aWil; "wil"
0x1800256f5  mov     r9d, eax; char *
0x1800256f8  mov     edx, 8Bh; void *
0x1800256fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025702  mov     eax, edi
0x180025704  jmp     short loc_18002575B
0x180025706  lea     r8, asc_18004AB08; "h"
0x18002570d  shr     rbx, 1Fh
0x180025711  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180025716  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002571b  test    ebx, ebx
0x18002571d  lea     rcx, [rbp+8]
0x180025721  lea     r9, [rsp+278h+pszDest]
0x180025726  mov     edx, ebx
0x180025728  cmovnz  esi, ebx
0x18002572b  mov     r8d, esi
0x18002572e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180025733  mov     ebx, eax
0x180025735  test    eax, eax
0x180025737  jns     short loc_180025759
0x180025739  mov     rcx, [rsp+278h]; this
0x180025741  lea     r8, aWil; "wil"
0x180025748  mov     r9d, eax; char *
0x18002574b  mov     edx, 90h; void *
0x180025750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025755  mov     eax, ebx
0x180025757  jmp     short loc_18002575B
0x180025759  xor     eax, eax
0x18002575b  mov     rcx, [rsp+278h+var_28]
0x180025763  xor     rcx, rsp; StackCookie
0x180025766  call    __security_check_cookie
0x18002576b  mov     rbx, [rsp+278h+arg_10]
0x180025773  add     rsp, 260h
0x18002577a  pop     rdi
0x18002577b  pop     rsi
0x18002577c  pop     rbp
0x18002577d  retn
```
