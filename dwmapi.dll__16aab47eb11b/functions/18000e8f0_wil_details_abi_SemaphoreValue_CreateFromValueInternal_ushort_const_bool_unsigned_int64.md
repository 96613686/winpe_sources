# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000e8f0`
- end: `0x18000ea0e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c35c`
- `0x18000c48c`

## callees

- `0x180004d20`
- `0x180009dd8`
- `0x180009e54`
- `0x18000d0a0`
- `0x18000e8f0`
- `0x180010968`
- `0x1800109d4`

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
0x18000e8f0  mov     [rsp+arg_10], rbx
0x18000e8f5  push    rbp
0x18000e8f6  push    rsi
0x18000e8f7  push    rdi
0x18000e8f8  sub     rsp, 260h
0x18000e8ff  mov     rax, cs:__security_cookie
0x18000e906  xor     rax, rsp
0x18000e909  mov     [rsp+278h+var_28], rax
0x18000e911  mov     rax, 0C000000000000000h
0x18000e91b  mov     rbx, r9
0x18000e91e  mov     rbp, rcx
0x18000e921  test    rax, r9
0x18000e924  jz      short loc_18000E92C
0x18000e926  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000e92c  mov     r8, rdx; unsigned __int16 *
0x18000e92f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000e934  mov     edx, 104h; unsigned __int64
0x18000e939  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e93e  lea     r8, aP0; "_p0"
0x18000e945  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000e94a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e94f  mov     edx, ebx
0x18000e951  lea     r9, [rsp+278h+var_238]
0x18000e956  and     edx, 7FFFFFFFh
0x18000e95c  mov     esi, 1
0x18000e961  mov     r8d, esi
0x18000e964  mov     rcx, rbp
0x18000e967  cmova   r8d, edx
0x18000e96b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e970  mov     edi, eax
0x18000e972  test    eax, eax
0x18000e974  jns     short loc_18000E996
0x18000e976  mov     rcx, [rsp+278h]; this
0x18000e97e  lea     r8, aWil; "wil"
0x18000e985  mov     r9d, eax; char *
0x18000e988  mov     edx, 8Bh; void *
0x18000e98d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e992  mov     eax, edi
0x18000e994  jmp     short loc_18000E9EB
0x18000e996  lea     r8, asc_180019390; "h"
0x18000e99d  shr     rbx, 1Fh
0x18000e9a1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000e9a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e9ab  test    ebx, ebx
0x18000e9ad  lea     rcx, [rbp+8]
0x18000e9b1  lea     r9, [rsp+278h+var_238]
0x18000e9b6  mov     edx, ebx
0x18000e9b8  cmovnz  esi, ebx
0x18000e9bb  mov     r8d, esi
0x18000e9be  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e9c3  mov     ebx, eax
0x18000e9c5  test    eax, eax
0x18000e9c7  jns     short loc_18000E9E9
0x18000e9c9  mov     rcx, [rsp+278h]; this
0x18000e9d1  lea     r8, aWil; "wil"
0x18000e9d8  mov     r9d, eax; char *
0x18000e9db  mov     edx, 90h; void *
0x18000e9e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9e5  mov     eax, ebx
0x18000e9e7  jmp     short loc_18000E9EB
0x18000e9e9  xor     eax, eax
0x18000e9eb  mov     rcx, [rsp+278h+var_28]
0x18000e9f3  xor     rcx, rsp; StackCookie
0x18000e9f6  call    __security_check_cookie
0x18000e9fb  mov     rbx, [rsp+278h+arg_10]
0x18000ea03  add     rsp, 260h
0x18000ea0a  pop     rdi
0x18000ea0b  pop     rsi
0x18000ea0c  pop     rbp
0x18000ea0d  retn
```
