# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000cac0`
- end: `0x18000cbe1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d960`
- `0x180013ecc`

## callees

- `0x180003b80`
- `0x180006a9c`
- `0x180008e5c`
- `0x18000a520`
- `0x18000cac0`
- `0x18000ec08`
- `0x18000eccc`

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
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x18000cac0  push    rbx
0x18000cac2  push    rbp
0x18000cac3  push    rsi
0x18000cac4  push    rdi
0x18000cac5  push    r14
0x18000cac7  sub     rsp, 260h
0x18000cace  mov     rax, cs:__security_cookie
0x18000cad5  xor     rax, rsp
0x18000cad8  mov     [rsp+288h+var_38], rax
0x18000cae0  mov     rax, 0C000000000000000h
0x18000caea  mov     rbx, r9
0x18000caed  mov     rbp, rcx
0x18000caf0  test    rax, r9
0x18000caf3  jz      short loc_18000CAFB
0x18000caf5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cafb  mov     r8, rdx; unsigned __int16 *
0x18000cafe  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000cb03  mov     r14d, 104h
0x18000cb09  mov     edx, r14d; unsigned __int64
0x18000cb0c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cb11  lea     r8, aP0; "_p0"
0x18000cb18  mov     edx, r14d; unsigned __int64
0x18000cb1b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000cb20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cb25  mov     edx, ebx
0x18000cb27  lea     r9, [rsp+288h+var_248]
0x18000cb2c  and     edx, 7FFFFFFFh
0x18000cb32  mov     esi, 1
0x18000cb37  mov     r8d, esi
0x18000cb3a  mov     rcx, rbp
0x18000cb3d  cmova   r8d, edx
0x18000cb41  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cb46  mov     edi, eax
0x18000cb48  test    eax, eax
0x18000cb4a  jns     short loc_18000CB6B
0x18000cb4c  mov     rcx, [rsp+288h]; this
0x18000cb54  lea     r8, aWil; "wil"
0x18000cb5b  mov     r9d, eax; char *
0x18000cb5e  lea     edx, [r14-79h]; void *
0x18000cb62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb67  mov     eax, edi
0x18000cb69  jmp     short loc_18000CBC3
0x18000cb6b  lea     r8, asc_1800227C0; "h"
0x18000cb72  shr     rbx, 1Fh
0x18000cb76  mov     rdx, r14; unsigned __int64
0x18000cb79  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000cb7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cb83  test    ebx, ebx
0x18000cb85  lea     rcx, [rbp+8]
0x18000cb89  lea     r9, [rsp+288h+var_248]
0x18000cb8e  mov     edx, ebx
0x18000cb90  cmovnz  esi, ebx
0x18000cb93  mov     r8d, esi
0x18000cb96  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cb9b  mov     ebx, eax
0x18000cb9d  test    eax, eax
0x18000cb9f  jns     short loc_18000CBC1
0x18000cba1  mov     rcx, [rsp+288h]; this
0x18000cba9  lea     r8, aWil; "wil"
0x18000cbb0  mov     r9d, eax; char *
0x18000cbb3  mov     edx, 90h; void *
0x18000cbb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbbd  mov     eax, ebx
0x18000cbbf  jmp     short loc_18000CBC3
0x18000cbc1  xor     eax, eax
0x18000cbc3  mov     rcx, [rsp+288h+var_38]
0x18000cbcb  xor     rcx, rsp; StackCookie
0x18000cbce  call    __security_check_cookie
0x18000cbd3  add     rsp, 260h
0x18000cbda  pop     r14
0x18000cbdc  pop     rdi
0x18000cbdd  pop     rsi
0x18000cbde  pop     rbp
0x18000cbdf  pop     rbx
0x18000cbe0  retn
```
