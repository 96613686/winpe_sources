# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003c08`
- end: `0x180003d26`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005240`
- `0x180005370`

## callees

- `0x180003c08`
- `0x18000635c`
- `0x180006a20`
- `0x180006b04`
- `0x1800076d8`
- `0x180007b68`
- `0x18001a5e0`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            v17);
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
        v16);
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
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x180003c08  mov     [rsp+arg_10], rbx
0x180003c0d  push    rbp
0x180003c0e  push    rsi
0x180003c0f  push    rdi
0x180003c10  sub     rsp, 260h
0x180003c17  mov     rax, cs:__security_cookie
0x180003c1e  xor     rax, rsp
0x180003c21  mov     [rsp+278h+var_28], rax
0x180003c29  mov     rax, 0C000000000000000h
0x180003c33  mov     rbx, r9
0x180003c36  mov     rbp, rcx
0x180003c39  test    rax, r9
0x180003c3c  jz      short loc_180003C44
0x180003c3e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c44  mov     r8, rdx; unsigned __int16 *
0x180003c47  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003c4c  mov     edx, 104h; unsigned __int64
0x180003c51  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003c56  lea     r8, aP0; "_p0"
0x180003c5d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003c62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c67  mov     edx, ebx
0x180003c69  lea     r9, [rsp+278h+var_238]
0x180003c6e  and     edx, 7FFFFFFFh
0x180003c74  mov     esi, 1
0x180003c79  mov     r8d, esi
0x180003c7c  mov     rcx, rbp
0x180003c7f  cmova   r8d, edx
0x180003c83  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003c88  mov     edi, eax
0x180003c8a  test    eax, eax
0x180003c8c  jns     short loc_180003CAE
0x180003c8e  mov     rcx, [rsp+278h]; this
0x180003c96  lea     r8, aWil; "wil"
0x180003c9d  mov     r9d, eax; char *
0x180003ca0  mov     edx, 8Bh; void *
0x180003ca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003caa  mov     eax, edi
0x180003cac  jmp     short loc_180003D03
0x180003cae  lea     r8, asc_18001FDA8; "h"
0x180003cb5  shr     rbx, 1Fh
0x180003cb9  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003cbe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003cc3  test    ebx, ebx
0x180003cc5  lea     rcx, [rbp+8]
0x180003cc9  lea     r9, [rsp+278h+var_238]
0x180003cce  mov     edx, ebx
0x180003cd0  cmovnz  esi, ebx
0x180003cd3  mov     r8d, esi
0x180003cd6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003cdb  mov     ebx, eax
0x180003cdd  test    eax, eax
0x180003cdf  jns     short loc_180003D01
0x180003ce1  mov     rcx, [rsp+278h]; this
0x180003ce9  lea     r8, aWil; "wil"
0x180003cf0  mov     r9d, eax; char *
0x180003cf3  mov     edx, 90h; void *
0x180003cf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cfd  mov     eax, ebx
0x180003cff  jmp     short loc_180003D03
0x180003d01  xor     eax, eax
0x180003d03  mov     rcx, [rsp+278h+var_28]
0x180003d0b  xor     rcx, rsp; StackCookie
0x180003d0e  call    __security_check_cookie
0x180003d13  mov     rbx, [rsp+278h+arg_10]
0x180003d1b  add     rsp, 260h
0x180003d22  pop     rdi
0x180003d23  pop     rsi
0x180003d24  pop     rbp
0x180003d25  retn
```
