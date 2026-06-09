# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008a5c`
- end: `0x180008b6c`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a7c8`

## callees

- `0x18000601c`
- `0x180008a5c`
- `0x18000bd5c`
- `0x18000c4ec`
- `0x18000c85c`
- `0x18000c8dc`
- `0x18002b960`

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
0x180008a5c  mov     [rsp+arg_10], rbx
0x180008a61  push    rbp
0x180008a62  push    rsi
0x180008a63  push    rdi
0x180008a64  sub     rsp, 260h
0x180008a6b  mov     rax, cs:__security_cookie
0x180008a72  xor     rax, rsp
0x180008a75  mov     [rsp+278h+var_28], rax
0x180008a7d  mov     rax, 0C000000000000000h
0x180008a87  mov     rbx, r9
0x180008a8a  mov     rbp, rcx
0x180008a8d  test    rax, r9
0x180008a90  jz      short loc_180008A98
0x180008a92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008a98  mov     r8, rdx; unsigned __int16 *
0x180008a9b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180008aa0  mov     edx, 104h; unsigned __int64
0x180008aa5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008aaa  lea     r8, aP0; "_p0"
0x180008ab1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180008ab6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008abb  mov     edx, ebx
0x180008abd  lea     r9, [rsp+278h+var_238]
0x180008ac2  and     edx, 7FFFFFFFh
0x180008ac8  mov     esi, 1
0x180008acd  mov     r8d, esi
0x180008ad0  mov     rcx, rbp
0x180008ad3  cmova   r8d, edx
0x180008ad7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180008adc  mov     edi, eax
0x180008ade  test    eax, eax
0x180008ae0  jns     short loc_180008AFB
0x180008ae2  mov     rcx, [rsp+278h]; this
0x180008aea  mov     r9d, eax; char *
0x180008aed  mov     edx, 8Bh; void *
0x180008af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008af7  mov     eax, edi
0x180008af9  jmp     short loc_180008B49
0x180008afb  lea     r8, asc_18002F988; "h"
0x180008b02  shr     rbx, 1Fh
0x180008b06  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180008b0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b10  test    ebx, ebx
0x180008b12  lea     rcx, [rbp+8]
0x180008b16  lea     r9, [rsp+278h+var_238]
0x180008b1b  mov     edx, ebx
0x180008b1d  cmovnz  esi, ebx
0x180008b20  mov     r8d, esi
0x180008b23  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180008b28  mov     ebx, eax
0x180008b2a  test    eax, eax
0x180008b2c  jns     short loc_180008B47
0x180008b2e  mov     rcx, [rsp+278h]; this
0x180008b36  mov     r9d, eax; char *
0x180008b39  mov     edx, 90h; void *
0x180008b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b43  mov     eax, ebx
0x180008b45  jmp     short loc_180008B49
0x180008b47  xor     eax, eax
0x180008b49  mov     rcx, [rsp+278h+var_28]
0x180008b51  xor     rcx, rsp; StackCookie
0x180008b54  call    __security_check_cookie
0x180008b59  mov     rbx, [rsp+278h+arg_10]
0x180008b61  add     rsp, 260h
0x180008b68  pop     rdi
0x180008b69  pop     rsi
0x180008b6a  pop     rbp
0x180008b6b  retn
```
