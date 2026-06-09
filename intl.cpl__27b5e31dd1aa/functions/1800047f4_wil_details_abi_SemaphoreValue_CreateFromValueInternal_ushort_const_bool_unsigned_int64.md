# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800047f4`
- end: `0x180004907`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800058d8`
- `0x180019f54`

## callees

- `0x1800047f4`
- `0x180005cc4`
- `0x1800061e0`
- `0x18000626c`
- `0x180006984`
- `0x180006d20`
- `0x18002a150`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        size_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x1800047f4  push    rbx
0x1800047f6  push    rbp
0x1800047f7  push    rsi
0x1800047f8  push    rdi
0x1800047f9  push    r14
0x1800047fb  sub     rsp, 260h
0x180004802  mov     rax, cs:__security_cookie
0x180004809  xor     rax, rsp
0x18000480c  mov     [rsp+288h+var_38], rax
0x180004814  mov     rax, 0C000000000000000h
0x18000481e  mov     rbx, r9
0x180004821  mov     rbp, rcx
0x180004824  test    rax, r9
0x180004827  jz      short loc_18000482F
0x180004829  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000482f  mov     r8, rdx; unsigned __int16 *
0x180004832  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004837  mov     r14d, 104h
0x18000483d  mov     edx, r14d; unsigned __int64
0x180004840  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004845  lea     r8, aP0; "_p0"
0x18000484c  mov     edx, r14d; unsigned __int64
0x18000484f  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004854  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004859  mov     edx, ebx
0x18000485b  lea     r9, [rsp+288h+var_248]
0x180004860  and     edx, 7FFFFFFFh
0x180004866  mov     esi, 1
0x18000486b  mov     r8d, esi
0x18000486e  mov     rcx, rbp
0x180004871  cmova   r8d, edx
0x180004875  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000487a  mov     edi, eax
0x18000487c  test    eax, eax
0x18000487e  jns     short loc_180004898
0x180004880  mov     rcx, [rsp+288h]; this
0x180004888  lea     edx, [r14-79h]; void *
0x18000488c  mov     r9d, eax; char *
0x18000488f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004894  mov     eax, edi
0x180004896  jmp     short loc_1800048E9
0x180004898  lea     r8, asc_18002F620; "h"
0x18000489f  shr     rbx, 1Fh
0x1800048a3  mov     rdx, r14; unsigned __int64
0x1800048a6  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800048ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800048b0  test    ebx, ebx
0x1800048b2  lea     rcx, [rbp+8]
0x1800048b6  lea     r9, [rsp+288h+var_248]
0x1800048bb  mov     edx, ebx
0x1800048bd  cmovnz  esi, ebx
0x1800048c0  mov     r8d, esi
0x1800048c3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800048c8  mov     ebx, eax
0x1800048ca  test    eax, eax
0x1800048cc  jns     short loc_1800048E7
0x1800048ce  mov     rcx, [rsp+288h]; this
0x1800048d6  mov     r9d, eax; char *
0x1800048d9  mov     edx, 90h; void *
0x1800048de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048e3  mov     eax, ebx
0x1800048e5  jmp     short loc_1800048E9
0x1800048e7  xor     eax, eax
0x1800048e9  mov     rcx, [rsp+288h+var_38]
0x1800048f1  xor     rcx, rsp; StackCookie
0x1800048f4  call    __security_check_cookie
0x1800048f9  add     rsp, 260h
0x180004900  pop     r14
0x180004902  pop     rdi
0x180004903  pop     rsi
0x180004904  pop     rbp
0x180004905  pop     rbx
0x180004906  retn
```
