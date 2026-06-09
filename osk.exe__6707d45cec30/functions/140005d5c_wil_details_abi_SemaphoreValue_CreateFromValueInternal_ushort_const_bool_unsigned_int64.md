# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140005d5c`
- end: `0x140005e75`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `281`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400077fc`
- `0x140007960`

## callees

- `0x140005d5c`
- `0x14000966c`
- `0x140009ea4`
- `0x140009ef0`
- `0x14000b134`
- `0x14000b750`
- `0x140025d70`

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
  StringCchCopyW(v17, (unsigned __int64)a2, a2);
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
0x140005d5c  mov     [rsp+arg_10], rbx
0x140005d61  push    rbp
0x140005d62  push    rsi
0x140005d63  push    rdi
0x140005d64  sub     rsp, 260h
0x140005d6b  mov     rax, cs:__security_cookie
0x140005d72  xor     rax, rsp
0x140005d75  mov     [rsp+278h+var_28], rax
0x140005d7d  mov     rax, 0C000000000000000h
0x140005d87  mov     rbx, r9
0x140005d8a  mov     rbp, rcx
0x140005d8d  test    rax, r9
0x140005d90  jz      short loc_140005D98
0x140005d92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005d98  mov     r8, rdx; unsigned __int16 *
0x140005d9b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140005da0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140005da5  lea     r8, aP0; "_p0"
0x140005dac  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140005db1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005db6  mov     edx, ebx
0x140005db8  lea     r9, [rsp+278h+var_238]
0x140005dbd  and     edx, 7FFFFFFFh
0x140005dc3  mov     esi, 1
0x140005dc8  mov     r8d, esi
0x140005dcb  mov     rcx, rbp
0x140005dce  cmova   r8d, edx
0x140005dd2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005dd7  mov     edi, eax
0x140005dd9  test    eax, eax
0x140005ddb  jns     short loc_140005DFD
0x140005ddd  mov     rcx, [rsp+278h]; this
0x140005de5  lea     r8, aWil; "wil"
0x140005dec  mov     r9d, eax; char *
0x140005def  mov     edx, 8Bh; void *
0x140005df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005df9  mov     eax, edi
0x140005dfb  jmp     short loc_140005E52
0x140005dfd  lea     r8, asc_14002ADE8; "h"
0x140005e04  shr     rbx, 1Fh
0x140005e08  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140005e0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005e12  test    ebx, ebx
0x140005e14  lea     rcx, [rbp+8]
0x140005e18  lea     r9, [rsp+278h+var_238]
0x140005e1d  mov     edx, ebx
0x140005e1f  cmovnz  esi, ebx
0x140005e22  mov     r8d, esi
0x140005e25  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005e2a  mov     ebx, eax
0x140005e2c  test    eax, eax
0x140005e2e  jns     short loc_140005E50
0x140005e30  mov     rcx, [rsp+278h]; this
0x140005e38  lea     r8, aWil; "wil"
0x140005e3f  mov     r9d, eax; char *
0x140005e42  mov     edx, 90h; void *
0x140005e47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005e4c  mov     eax, ebx
0x140005e4e  jmp     short loc_140005E52
0x140005e50  xor     eax, eax
0x140005e52  mov     rcx, [rsp+278h+var_28]
0x140005e5a  xor     rcx, rsp; StackCookie
0x140005e5d  call    __security_check_cookie
0x140005e62  mov     rbx, [rsp+278h+arg_10]
0x140005e6a  add     rsp, 260h
0x140005e71  pop     rdi
0x140005e72  pop     rsi
0x140005e73  pop     rbp
0x140005e74  retn
```
