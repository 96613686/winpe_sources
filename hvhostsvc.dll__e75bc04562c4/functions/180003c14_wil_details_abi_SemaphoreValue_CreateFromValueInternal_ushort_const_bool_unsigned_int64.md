# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003c14`
- end: `0x180003d2d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `281`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004e4c`

## callees

- `0x180002100`
- `0x180003c14`
- `0x180005524`
- `0x1800059fc`
- `0x180005a48`
- `0x180005fc4`
- `0x180006088`

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
0x180003c14  mov     [rsp+arg_10], rbx
0x180003c19  push    rbp
0x180003c1a  push    rsi
0x180003c1b  push    rdi
0x180003c1c  sub     rsp, 260h
0x180003c23  mov     rax, cs:__security_cookie
0x180003c2a  xor     rax, rsp
0x180003c2d  mov     [rsp+278h+var_28], rax
0x180003c35  mov     rax, 0C000000000000000h
0x180003c3f  mov     rbx, r9
0x180003c42  mov     rbp, rcx
0x180003c45  test    rax, r9
0x180003c48  jz      short loc_180003C50
0x180003c4a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c50  mov     r8, rdx; unsigned __int16 *
0x180003c53  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003c58  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003c5d  lea     r8, aP0; "_p0"
0x180003c64  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003c69  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c6e  mov     edx, ebx
0x180003c70  lea     r9, [rsp+278h+var_238]
0x180003c75  and     edx, 7FFFFFFFh
0x180003c7b  mov     esi, 1
0x180003c80  mov     r8d, esi
0x180003c83  mov     rcx, rbp
0x180003c86  cmova   r8d, edx
0x180003c8a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003c8f  mov     edi, eax
0x180003c91  test    eax, eax
0x180003c93  jns     short loc_180003CB5
0x180003c95  mov     rcx, [rsp+278h]; this
0x180003c9d  lea     r8, aWil; "wil"
0x180003ca4  mov     r9d, eax; char *
0x180003ca7  mov     edx, 8Bh; void *
0x180003cac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cb1  mov     eax, edi
0x180003cb3  jmp     short loc_180003D0A
0x180003cb5  lea     r8, asc_18000BD90; "h"
0x180003cbc  shr     rbx, 1Fh
0x180003cc0  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003cc5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003cca  test    ebx, ebx
0x180003ccc  lea     rcx, [rbp+8]
0x180003cd0  lea     r9, [rsp+278h+var_238]
0x180003cd5  mov     edx, ebx
0x180003cd7  cmovnz  esi, ebx
0x180003cda  mov     r8d, esi
0x180003cdd  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003ce2  mov     ebx, eax
0x180003ce4  test    eax, eax
0x180003ce6  jns     short loc_180003D08
0x180003ce8  mov     rcx, [rsp+278h]; this
0x180003cf0  lea     r8, aWil; "wil"
0x180003cf7  mov     r9d, eax; char *
0x180003cfa  mov     edx, 90h; void *
0x180003cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d04  mov     eax, ebx
0x180003d06  jmp     short loc_180003D0A
0x180003d08  xor     eax, eax
0x180003d0a  mov     rcx, [rsp+278h+var_28]
0x180003d12  xor     rcx, rsp; StackCookie
0x180003d15  call    __security_check_cookie
0x180003d1a  mov     rbx, [rsp+278h+arg_10]
0x180003d22  add     rsp, 260h
0x180003d29  pop     rdi
0x180003d2a  pop     rsi
0x180003d2b  pop     rbp
0x180003d2c  retn
```
