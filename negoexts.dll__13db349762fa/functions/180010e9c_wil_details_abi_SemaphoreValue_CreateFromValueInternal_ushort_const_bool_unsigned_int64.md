# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180010e9c`
- end: `0x180010fa7`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `267`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800129bc`
- `0x180012ae0`

## callees

- `0x180010e9c`
- `0x180013ca4`
- `0x1800143d8`
- `0x180014424`
- `0x18001509c`
- `0x1800151e0`
- `0x18001ed20`

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
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, (unsigned __int64)a2, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            v19);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v18);
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
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x180010e9c  mov     [rsp+arg_10], rbx
0x180010ea1  push    rbp
0x180010ea2  push    rsi
0x180010ea3  push    rdi
0x180010ea4  sub     rsp, 260h
0x180010eab  mov     rax, cs:__security_cookie
0x180010eb2  xor     rax, rsp
0x180010eb5  mov     [rsp+278h+var_28], rax
0x180010ebd  mov     rax, 0C000000000000000h
0x180010ec7  mov     rbx, r9
0x180010eca  mov     rbp, rcx
0x180010ecd  test    rax, r9
0x180010ed0  jz      short loc_180010ED8
0x180010ed2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010ed8  mov     r8, rdx; unsigned __int16 *
0x180010edb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180010ee0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010ee5  lea     r8, aP0; "_p0"
0x180010eec  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180010ef1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010ef6  mov     edx, ebx
0x180010ef8  lea     r9, [rsp+278h+var_238]
0x180010efd  and     edx, 7FFFFFFFh
0x180010f03  mov     esi, 1
0x180010f08  mov     r8d, esi
0x180010f0b  mov     rcx, rbp
0x180010f0e  cmova   r8d, edx
0x180010f12  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180010f17  mov     edi, eax
0x180010f19  test    eax, eax
0x180010f1b  jns     short loc_180010F36
0x180010f1d  mov     rcx, [rsp+278h]; this
0x180010f25  mov     r9d, eax; char *
0x180010f28  mov     edx, 8Bh; void *
0x180010f2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f32  mov     eax, edi
0x180010f34  jmp     short loc_180010F84
0x180010f36  lea     r8, asc_1800221B8; "h"
0x180010f3d  shr     rbx, 1Fh
0x180010f41  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180010f46  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010f4b  test    ebx, ebx
0x180010f4d  lea     rcx, [rbp+8]
0x180010f51  lea     r9, [rsp+278h+var_238]
0x180010f56  mov     edx, ebx
0x180010f58  cmovnz  esi, ebx
0x180010f5b  mov     r8d, esi
0x180010f5e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180010f63  mov     ebx, eax
0x180010f65  test    eax, eax
0x180010f67  jns     short loc_180010F82
0x180010f69  mov     rcx, [rsp+278h]; this
0x180010f71  mov     r9d, eax; char *
0x180010f74  mov     edx, 90h; void *
0x180010f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f7e  mov     eax, ebx
0x180010f80  jmp     short loc_180010F84
0x180010f82  xor     eax, eax
0x180010f84  mov     rcx, [rsp+278h+var_28]
0x180010f8c  xor     rcx, rsp; StackCookie
0x180010f8f  call    __security_check_cookie
0x180010f94  mov     rbx, [rsp+278h+arg_10]
0x180010f9c  add     rsp, 260h
0x180010fa3  pop     rdi
0x180010fa4  pop     rsi
0x180010fa5  pop     rbp
0x180010fa6  retn
```
