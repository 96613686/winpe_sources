# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000692c`
- end: `0x180006a3d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `273`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800077f0`

## callees

- `0x18000692c`
- `0x180007c44`
- `0x180007fc0`
- `0x180008040`
- `0x1800083d8`
- `0x180008698`
- `0x180009e40`

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
0x18000692c  mov     [rsp+arg_10], rbx
0x180006931  push    rbp
0x180006932  push    rsi
0x180006933  push    rdi
0x180006934  sub     rsp, 260h
0x18000693b  mov     rax, cs:__security_cookie
0x180006942  xor     rax, rsp
0x180006945  mov     [rsp+278h+var_28], rax
0x18000694d  mov     rax, 0C000000000000000h
0x180006957  mov     rbx, r9
0x18000695a  mov     rbp, rcx
0x18000695d  test    rax, r9
0x180006960  jz      short loc_180006968
0x180006962  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006968  mov     r9, rdx; pszSrc
0x18000696b  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180006970  mov     edx, 104h; cchDest
0x180006975  call    StringCopyWorkerW
0x18000697a  lea     r8, aP0; "_p0"
0x180006981  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180006986  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000698b  mov     edx, ebx
0x18000698d  lea     r9, [rsp+278h+pszDest]
0x180006992  and     edx, 7FFFFFFFh
0x180006998  mov     esi, 1
0x18000699d  mov     r8d, esi
0x1800069a0  mov     rcx, rbp
0x1800069a3  cmova   r8d, edx
0x1800069a7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800069ac  mov     edi, eax
0x1800069ae  test    eax, eax
0x1800069b0  jns     short loc_1800069CB
0x1800069b2  mov     rcx, [rsp+278h]; this
0x1800069ba  mov     r9d, eax; char *
0x1800069bd  mov     edx, 8Bh; void *
0x1800069c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069c7  mov     eax, edi
0x1800069c9  jmp     short loc_180006A19
0x1800069cb  lea     r8, asc_18000DA00; "h"
0x1800069d2  shr     rbx, 1Fh
0x1800069d6  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800069db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800069e0  test    ebx, ebx
0x1800069e2  lea     rcx, [rbp+8]
0x1800069e6  lea     r9, [rsp+278h+pszDest]
0x1800069eb  mov     edx, ebx
0x1800069ed  cmovnz  esi, ebx
0x1800069f0  mov     r8d, esi
0x1800069f3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800069f8  mov     ebx, eax
0x1800069fa  test    eax, eax
0x1800069fc  jns     short loc_180006A17
0x1800069fe  mov     rcx, [rsp+278h]; this
0x180006a06  mov     r9d, eax; char *
0x180006a09  mov     edx, 90h; void *
0x180006a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a13  mov     eax, ebx
0x180006a15  jmp     short loc_180006A19
0x180006a17  xor     eax, eax
0x180006a19  mov     rcx, [rsp+278h+var_28]
0x180006a21  xor     rcx, rsp; StackCookie
0x180006a24  call    __security_check_cookie
0x180006a29  mov     rbx, [rsp+278h+arg_10]
0x180006a31  add     rsp, 260h
0x180006a38  pop     rdi
0x180006a39  pop     rsi
0x180006a3a  pop     rbp
0x180006a3b  retn
```
