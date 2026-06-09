# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000e440`
- end: `0x18000e553`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000af70`
- `0x18000b0d0`

## callees

- `0x180004170`
- `0x1800041ec`
- `0x18000b238`
- `0x18000be40`
- `0x18000e440`
- `0x180011e40`
- `0x180011f80`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
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
0x18000e440  push    rbx
0x18000e442  push    rbp
0x18000e443  push    rsi
0x18000e444  push    rdi
0x18000e445  push    r14
0x18000e447  sub     rsp, 260h
0x18000e44e  mov     rax, cs:__security_cookie
0x18000e455  xor     rax, rsp
0x18000e458  mov     [rsp+288h+var_38], rax
0x18000e460  mov     rax, 0C000000000000000h
0x18000e46a  mov     rbx, r9
0x18000e46d  mov     rbp, rcx
0x18000e470  test    rax, r9
0x18000e473  jz      short loc_18000E47B
0x18000e475  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000e47b  mov     r8, rdx; unsigned __int16 *
0x18000e47e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000e483  mov     r14d, 104h
0x18000e489  mov     edx, r14d; unsigned __int64
0x18000e48c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e491  lea     r8, aP0; "_p0"
0x18000e498  mov     edx, r14d; unsigned __int64
0x18000e49b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000e4a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e4a5  mov     edx, ebx
0x18000e4a7  lea     r9, [rsp+288h+var_248]
0x18000e4ac  and     edx, 7FFFFFFFh
0x18000e4b2  mov     esi, 1
0x18000e4b7  mov     r8d, esi
0x18000e4ba  mov     rcx, rbp
0x18000e4bd  cmova   r8d, edx
0x18000e4c1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e4c6  mov     edi, eax
0x18000e4c8  test    eax, eax
0x18000e4ca  jns     short loc_18000E4E4
0x18000e4cc  mov     rcx, [rsp+288h]; this
0x18000e4d4  lea     edx, [r14-79h]; void *
0x18000e4d8  mov     r9d, eax; char *
0x18000e4db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4e0  mov     eax, edi
0x18000e4e2  jmp     short loc_18000E535
0x18000e4e4  lea     r8, asc_180025A10; "h"
0x18000e4eb  shr     rbx, 1Fh
0x18000e4ef  mov     rdx, r14; unsigned __int64
0x18000e4f2  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000e4f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e4fc  test    ebx, ebx
0x18000e4fe  lea     rcx, [rbp+8]
0x18000e502  lea     r9, [rsp+288h+var_248]
0x18000e507  mov     edx, ebx
0x18000e509  cmovnz  esi, ebx
0x18000e50c  mov     r8d, esi
0x18000e50f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e514  mov     ebx, eax
0x18000e516  test    eax, eax
0x18000e518  jns     short loc_18000E533
0x18000e51a  mov     rcx, [rsp+288h]; this
0x18000e522  mov     r9d, eax; char *
0x18000e525  mov     edx, 90h; void *
0x18000e52a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e52f  mov     eax, ebx
0x18000e531  jmp     short loc_18000E535
0x18000e533  xor     eax, eax
0x18000e535  mov     rcx, [rsp+288h+var_38]
0x18000e53d  xor     rcx, rsp; StackCookie
0x18000e540  call    __security_check_cookie
0x18000e545  add     rsp, 260h
0x18000e54c  pop     r14
0x18000e54e  pop     rdi
0x18000e54f  pop     rsi
0x18000e550  pop     rbp
0x18000e551  pop     rbx
0x18000e552  retn
```
