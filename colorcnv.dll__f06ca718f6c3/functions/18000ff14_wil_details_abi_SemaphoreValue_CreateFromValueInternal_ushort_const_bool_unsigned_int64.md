# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000ff14`
- end: `0x180010024`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a3f8`

## callees

- `0x18000a590`
- `0x18000ab30`
- `0x18000e440`
- `0x18000ff14`
- `0x180013ab8`
- `0x1800146b8`
- `0x180014738`

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
  StringCchCopyW(v19, 0x104u, a2);
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
0x18000ff14  mov     [rsp+arg_10], rbx
0x18000ff19  push    rbp
0x18000ff1a  push    rsi
0x18000ff1b  push    rdi
0x18000ff1c  sub     rsp, 260h
0x18000ff23  mov     rax, cs:__security_cookie
0x18000ff2a  xor     rax, rsp
0x18000ff2d  mov     [rsp+278h+var_28], rax
0x18000ff35  mov     rax, 0C000000000000000h
0x18000ff3f  mov     rbx, r9
0x18000ff42  mov     rbp, rcx
0x18000ff45  test    rax, r9
0x18000ff48  jz      short loc_18000FF50
0x18000ff4a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ff50  mov     r8, rdx; unsigned __int16 *
0x18000ff53  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ff58  mov     edx, 104h; unsigned __int64
0x18000ff5d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ff62  lea     r8, aP0; "_p0"
0x18000ff69  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ff6e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ff73  mov     edx, ebx
0x18000ff75  lea     r9, [rsp+278h+var_238]
0x18000ff7a  and     edx, 7FFFFFFFh
0x18000ff80  mov     esi, 1
0x18000ff85  mov     r8d, esi
0x18000ff88  mov     rcx, rbp
0x18000ff8b  cmova   r8d, edx
0x18000ff8f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ff94  mov     edi, eax
0x18000ff96  test    eax, eax
0x18000ff98  jns     short loc_18000FFB3
0x18000ff9a  mov     rcx, [rsp+278h]; this
0x18000ffa2  mov     r9d, eax; char *
0x18000ffa5  mov     edx, 8Bh; void *
0x18000ffaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffaf  mov     eax, edi
0x18000ffb1  jmp     short loc_180010001
0x18000ffb3  lea     r8, asc_18002FF90; "h"
0x18000ffba  shr     rbx, 1Fh
0x18000ffbe  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ffc3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ffc8  test    ebx, ebx
0x18000ffca  lea     rcx, [rbp+8]
0x18000ffce  lea     r9, [rsp+278h+var_238]
0x18000ffd3  mov     edx, ebx
0x18000ffd5  cmovnz  esi, ebx
0x18000ffd8  mov     r8d, esi
0x18000ffdb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ffe0  mov     ebx, eax
0x18000ffe2  test    eax, eax
0x18000ffe4  jns     short loc_18000FFFF
0x18000ffe6  mov     rcx, [rsp+278h]; this
0x18000ffee  mov     r9d, eax; char *
0x18000fff1  mov     edx, 90h; void *
0x18000fff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fffb  mov     eax, ebx
0x18000fffd  jmp     short loc_180010001
0x18000ffff  xor     eax, eax
0x180010001  mov     rcx, [rsp+278h+var_28]
0x180010009  xor     rcx, rsp; StackCookie
0x18001000c  call    __security_check_cookie
0x180010011  mov     rbx, [rsp+278h+arg_10]
0x180010019  add     rsp, 260h
0x180010020  pop     rdi
0x180010021  pop     rsi
0x180010022  pop     rbp
0x180010023  retn
```
