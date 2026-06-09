# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006a34`
- end: `0x180006b52`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007534`

## callees

- `0x180003290`
- `0x180005020`
- `0x180006a34`
- `0x180007ebc`
- `0x180007f38`
- `0x18000843c`
- `0x180008500`

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
0x180006a34  mov     [rsp+arg_10], rbx
0x180006a39  push    rbp
0x180006a3a  push    rsi
0x180006a3b  push    rdi
0x180006a3c  sub     rsp, 260h
0x180006a43  mov     rax, cs:__security_cookie
0x180006a4a  xor     rax, rsp
0x180006a4d  mov     [rsp+278h+var_28], rax
0x180006a55  mov     rax, 0C000000000000000h
0x180006a5f  mov     rbx, r9
0x180006a62  mov     rbp, rcx
0x180006a65  test    rax, r9
0x180006a68  jz      short loc_180006A70
0x180006a6a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006a70  mov     r8, rdx; unsigned __int16 *
0x180006a73  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180006a78  mov     edx, 104h; unsigned __int64
0x180006a7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006a82  lea     r8, aP0; "_p0"
0x180006a89  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180006a8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006a93  mov     edx, ebx
0x180006a95  lea     r9, [rsp+278h+var_238]
0x180006a9a  and     edx, 7FFFFFFFh
0x180006aa0  mov     esi, 1
0x180006aa5  mov     r8d, esi
0x180006aa8  mov     rcx, rbp
0x180006aab  cmova   r8d, edx
0x180006aaf  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006ab4  mov     edi, eax
0x180006ab6  test    eax, eax
0x180006ab8  jns     short loc_180006ADA
0x180006aba  mov     rcx, [rsp+278h]; this
0x180006ac2  lea     r8, aWil; "wil"
0x180006ac9  mov     r9d, eax; char *
0x180006acc  mov     edx, 8Bh; void *
0x180006ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ad6  mov     eax, edi
0x180006ad8  jmp     short loc_180006B2F
0x180006ada  lea     r8, asc_18000D3C8; "h"
0x180006ae1  shr     rbx, 1Fh
0x180006ae5  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180006aea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006aef  test    ebx, ebx
0x180006af1  lea     rcx, [rbp+8]
0x180006af5  lea     r9, [rsp+278h+var_238]
0x180006afa  mov     edx, ebx
0x180006afc  cmovnz  esi, ebx
0x180006aff  mov     r8d, esi
0x180006b02  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006b07  mov     ebx, eax
0x180006b09  test    eax, eax
0x180006b0b  jns     short loc_180006B2D
0x180006b0d  mov     rcx, [rsp+278h]; this
0x180006b15  lea     r8, aWil; "wil"
0x180006b1c  mov     r9d, eax; char *
0x180006b1f  mov     edx, 90h; void *
0x180006b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b29  mov     eax, ebx
0x180006b2b  jmp     short loc_180006B2F
0x180006b2d  xor     eax, eax
0x180006b2f  mov     rcx, [rsp+278h+var_28]
0x180006b37  xor     rcx, rsp; StackCookie
0x180006b3a  call    __security_check_cookie
0x180006b3f  mov     rbx, [rsp+278h+arg_10]
0x180006b47  add     rsp, 260h
0x180006b4e  pop     rdi
0x180006b4f  pop     rsi
0x180006b50  pop     rbp
0x180006b51  retn
```
