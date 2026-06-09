# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004808`
- end: `0x180004926`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005924`

## callees

- `0x180002b10`
- `0x180004808`
- `0x180005fc4`
- `0x1800064e0`
- `0x1800065c0`
- `0x180006ae4`
- `0x180006ba8`

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
0x180004808  mov     [rsp+arg_10], rbx
0x18000480d  push    rbp
0x18000480e  push    rsi
0x18000480f  push    rdi
0x180004810  sub     rsp, 260h
0x180004817  mov     rax, cs:__security_cookie
0x18000481e  xor     rax, rsp
0x180004821  mov     [rsp+278h+var_28], rax
0x180004829  mov     rax, 0C000000000000000h
0x180004833  mov     rbx, r9
0x180004836  mov     rbp, rcx
0x180004839  test    rax, r9
0x18000483c  jz      short loc_180004844
0x18000483e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004844  mov     r9, rdx; pszSrc
0x180004847  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000484c  mov     edx, 104h; cchDest
0x180004851  call    StringCopyWorkerW
0x180004856  lea     r8, aP0; "_p0"
0x18000485d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180004862  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004867  mov     edx, ebx
0x180004869  lea     r9, [rsp+278h+pszDest]
0x18000486e  and     edx, 7FFFFFFFh
0x180004874  mov     esi, 1
0x180004879  mov     r8d, esi
0x18000487c  mov     rcx, rbp
0x18000487f  cmova   r8d, edx
0x180004883  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004888  mov     edi, eax
0x18000488a  test    eax, eax
0x18000488c  jns     short loc_1800048AE
0x18000488e  mov     rcx, [rsp+278h]; this
0x180004896  lea     r8, aWil; "wil"
0x18000489d  mov     r9d, eax; char *
0x1800048a0  mov     edx, 8Bh; void *
0x1800048a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048aa  mov     eax, edi
0x1800048ac  jmp     short loc_180004903
0x1800048ae  lea     r8, asc_18001DE68; "h"
0x1800048b5  shr     rbx, 1Fh
0x1800048b9  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800048be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800048c3  test    ebx, ebx
0x1800048c5  lea     rcx, [rbp+8]
0x1800048c9  lea     r9, [rsp+278h+pszDest]
0x1800048ce  mov     edx, ebx
0x1800048d0  cmovnz  esi, ebx
0x1800048d3  mov     r8d, esi
0x1800048d6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800048db  mov     ebx, eax
0x1800048dd  test    eax, eax
0x1800048df  jns     short loc_180004901
0x1800048e1  mov     rcx, [rsp+278h]; this
0x1800048e9  lea     r8, aWil; "wil"
0x1800048f0  mov     r9d, eax; char *
0x1800048f3  mov     edx, 90h; void *
0x1800048f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048fd  mov     eax, ebx
0x1800048ff  jmp     short loc_180004903
0x180004901  xor     eax, eax
0x180004903  mov     rcx, [rsp+278h+var_28]
0x18000490b  xor     rcx, rsp; StackCookie
0x18000490e  call    __security_check_cookie
0x180004913  mov     rbx, [rsp+278h+arg_10]
0x18000491b  add     rsp, 260h
0x180004922  pop     rdi
0x180004923  pop     rsi
0x180004924  pop     rbp
0x180004925  retn
```
