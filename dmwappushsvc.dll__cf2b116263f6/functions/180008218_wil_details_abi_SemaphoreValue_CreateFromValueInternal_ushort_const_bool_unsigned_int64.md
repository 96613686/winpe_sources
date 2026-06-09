# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008218`
- end: `0x180008336`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800097dc`
- `0x18000990c`

## callees

- `0x180001a70`
- `0x1800040a4`
- `0x180008218`
- `0x18000af78`
- `0x18000b4d8`
- `0x18000c314`
- `0x18000c688`

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
0x180008218  mov     [rsp+arg_10], rbx
0x18000821d  push    rbp
0x18000821e  push    rsi
0x18000821f  push    rdi
0x180008220  sub     rsp, 260h
0x180008227  mov     rax, cs:__security_cookie
0x18000822e  xor     rax, rsp
0x180008231  mov     [rsp+278h+var_28], rax
0x180008239  mov     rax, 0C000000000000000h
0x180008243  mov     rbx, r9
0x180008246  mov     rbp, rcx
0x180008249  test    rax, r9
0x18000824c  jz      short loc_180008254
0x18000824e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008254  mov     r8, rdx; unsigned __int16 *
0x180008257  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000825c  mov     edx, 104h; unsigned __int64
0x180008261  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008266  lea     r8, aP0; "_p0"
0x18000826d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180008272  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008277  mov     edx, ebx
0x180008279  lea     r9, [rsp+278h+var_238]
0x18000827e  and     edx, 7FFFFFFFh
0x180008284  mov     esi, 1
0x180008289  mov     r8d, esi
0x18000828c  mov     rcx, rbp
0x18000828f  cmova   r8d, edx
0x180008293  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180008298  mov     edi, eax
0x18000829a  test    eax, eax
0x18000829c  jns     short loc_1800082BE
0x18000829e  mov     rcx, [rsp+278h]; this
0x1800082a6  lea     r8, aWil; "wil"
0x1800082ad  mov     r9d, eax; char *
0x1800082b0  mov     edx, 8Bh; void *
0x1800082b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082ba  mov     eax, edi
0x1800082bc  jmp     short loc_180008313
0x1800082be  lea     r8, asc_1800149C0; "h"
0x1800082c5  shr     rbx, 1Fh
0x1800082c9  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800082ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082d3  test    ebx, ebx
0x1800082d5  lea     rcx, [rbp+8]
0x1800082d9  lea     r9, [rsp+278h+var_238]
0x1800082de  mov     edx, ebx
0x1800082e0  cmovnz  esi, ebx
0x1800082e3  mov     r8d, esi
0x1800082e6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800082eb  mov     ebx, eax
0x1800082ed  test    eax, eax
0x1800082ef  jns     short loc_180008311
0x1800082f1  mov     rcx, [rsp+278h]; this
0x1800082f9  lea     r8, aWil; "wil"
0x180008300  mov     r9d, eax; char *
0x180008303  mov     edx, 90h; void *
0x180008308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000830d  mov     eax, ebx
0x18000830f  jmp     short loc_180008313
0x180008311  xor     eax, eax
0x180008313  mov     rcx, [rsp+278h+var_28]
0x18000831b  xor     rcx, rsp; StackCookie
0x18000831e  call    __security_check_cookie
0x180008323  mov     rbx, [rsp+278h+arg_10]
0x18000832b  add     rsp, 260h
0x180008332  pop     rdi
0x180008333  pop     rsi
0x180008334  pop     rbp
0x180008335  retn
```
