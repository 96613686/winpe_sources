# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140011a6c`
- end: `0x140011b8f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `291`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012700`
- `0x140016968`

## callees

- `0x140009010`
- `0x14000eaa0`
- `0x14000fb48`
- `0x140011a6c`
- `0x140013674`
- `0x1400136e4`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v6; // rdx
  unsigned int v7; // esi
  __int64 v8; // r8
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-258h]
  unsigned __int16 v16[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v16, (unsigned __int64)a2, a2);
  StringCchCatW(v16, 0x104u, L"_p0");
  v6 = a4 & 0x7FFFFFFF;
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = (unsigned int)v6;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6, v8, v16);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v16, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v7 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (char *)this + 8,
            (unsigned int)v12,
            v7,
            v16);
    v14 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v15);
    return v10;
  }
}

```

## disassembly

```asm
0x140011a6c  mov     [rsp+arg_10], rbx
0x140011a71  push    rbp
0x140011a72  push    rsi
0x140011a73  push    rdi
0x140011a74  sub     rsp, 260h
0x140011a7b  mov     rax, cs:__security_cookie
0x140011a82  xor     rax, rsp
0x140011a85  mov     [rsp+278h+var_28], rax
0x140011a8d  mov     rax, 0C000000000000000h
0x140011a97  mov     rbx, r9
0x140011a9a  mov     rbp, rcx
0x140011a9d  test    rax, r9
0x140011aa0  jz      short loc_140011AA8
0x140011aa2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140011aa8  mov     r8, rdx; unsigned __int16 *
0x140011aab  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140011ab0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140011ab5  lea     r8, aP0; "_p0"
0x140011abc  mov     edx, 104h; unsigned __int64
0x140011ac1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140011ac6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140011acb  mov     edx, ebx
0x140011acd  lea     r9, [rsp+278h+var_238]
0x140011ad2  and     edx, 7FFFFFFFh
0x140011ad8  mov     esi, 1
0x140011add  mov     r8d, esi
0x140011ae0  mov     rcx, rbp
0x140011ae3  cmova   r8d, edx
0x140011ae7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140011aec  mov     edi, eax
0x140011aee  test    eax, eax
0x140011af0  jns     short loc_140011B12
0x140011af2  mov     rcx, [rsp+278h]; this
0x140011afa  lea     r8, aWil; "wil"
0x140011b01  mov     r9d, eax; char *
0x140011b04  mov     edx, 8Bh; void *
0x140011b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011b0e  mov     eax, edi
0x140011b10  jmp     short loc_140011B6C
0x140011b12  lea     r8, asc_140021060; "h"
0x140011b19  shr     rbx, 1Fh
0x140011b1d  mov     edx, 104h; unsigned __int64
0x140011b22  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140011b27  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140011b2c  test    ebx, ebx
0x140011b2e  lea     rcx, [rbp+8]
0x140011b32  lea     r9, [rsp+278h+var_238]
0x140011b37  mov     edx, ebx
0x140011b39  cmovnz  esi, ebx
0x140011b3c  mov     r8d, esi
0x140011b3f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140011b44  mov     ebx, eax
0x140011b46  test    eax, eax
0x140011b48  jns     short loc_140011B6A
0x140011b4a  mov     rcx, [rsp+278h]; this
0x140011b52  lea     r8, aWil; "wil"
0x140011b59  mov     r9d, eax; char *
0x140011b5c  mov     edx, 90h; void *
0x140011b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011b66  mov     eax, ebx
0x140011b68  jmp     short loc_140011B6C
0x140011b6a  xor     eax, eax
0x140011b6c  mov     rcx, [rsp+278h+var_28]
0x140011b74  xor     rcx, rsp; StackCookie
0x140011b77  call    __security_check_cookie
0x140011b7c  mov     rbx, [rsp+278h+arg_10]
0x140011b84  add     rsp, 260h
0x140011b8b  pop     rdi
0x140011b8c  pop     rsi
0x140011b8d  pop     rbp
0x140011b8e  retn
```
