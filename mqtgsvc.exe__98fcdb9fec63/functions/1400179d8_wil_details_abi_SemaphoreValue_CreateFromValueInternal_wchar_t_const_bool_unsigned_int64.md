# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1400179d8`
- end: `0x140017aeb`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400190b0`
- `0x1400191dc`

## callees

- `0x140004648`
- `0x14000c9b0`
- `0x1400179d8`
- `0x14001a3bc`
- `0x14001b50c`
- `0x14001b7b8`
- `0x14001cf00`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  wchar_t v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x1400179d8  push    rbx
0x1400179da  push    rbp
0x1400179db  push    rsi
0x1400179dc  push    rdi
0x1400179dd  push    r14
0x1400179df  sub     rsp, 260h
0x1400179e6  mov     rax, cs:__security_cookie
0x1400179ed  xor     rax, rsp
0x1400179f0  mov     [rsp+288h+var_38], rax
0x1400179f8  mov     rax, 0C000000000000000h
0x140017a02  mov     rbx, r9
0x140017a05  mov     rbp, rcx
0x140017a08  test    rax, r9
0x140017a0b  jz      short loc_140017A13
0x140017a0d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140017a13  mov     r8, rdx; wchar_t *
0x140017a16  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140017a1b  mov     r14d, 104h
0x140017a21  mov     edx, r14d; unsigned __int64
0x140017a24  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017a29  lea     r8, aP0; "_p0"
0x140017a30  mov     edx, r14d; unsigned __int64
0x140017a33  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140017a38  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017a3d  mov     edx, ebx
0x140017a3f  lea     r9, [rsp+288h+var_248]
0x140017a44  and     edx, 7FFFFFFFh
0x140017a4a  mov     esi, 1
0x140017a4f  mov     r8d, esi
0x140017a52  mov     rcx, rbp
0x140017a55  cmova   r8d, edx
0x140017a59  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140017a5e  mov     edi, eax
0x140017a60  test    eax, eax
0x140017a62  jns     short loc_140017A7C
0x140017a64  mov     rcx, [rsp+288h]; this
0x140017a6c  lea     edx, [r14-79h]; void *
0x140017a70  mov     r9d, eax; char *
0x140017a73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017a78  mov     eax, edi
0x140017a7a  jmp     short loc_140017ACD
0x140017a7c  lea     r8, asc_140023148; "h"
0x140017a83  shr     rbx, 1Fh
0x140017a87  mov     rdx, r14; unsigned __int64
0x140017a8a  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140017a8f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017a94  test    ebx, ebx
0x140017a96  lea     rcx, [rbp+8]
0x140017a9a  lea     r9, [rsp+288h+var_248]
0x140017a9f  mov     edx, ebx
0x140017aa1  cmovnz  esi, ebx
0x140017aa4  mov     r8d, esi
0x140017aa7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140017aac  mov     ebx, eax
0x140017aae  test    eax, eax
0x140017ab0  jns     short loc_140017ACB
0x140017ab2  mov     rcx, [rsp+288h]; this
0x140017aba  mov     r9d, eax; char *
0x140017abd  mov     edx, 90h; void *
0x140017ac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017ac7  mov     eax, ebx
0x140017ac9  jmp     short loc_140017ACD
0x140017acb  xor     eax, eax
0x140017acd  mov     rcx, [rsp+288h+var_38]
0x140017ad5  xor     rcx, rsp; StackCookie
0x140017ad8  call    __security_check_cookie
0x140017add  add     rsp, 260h
0x140017ae4  pop     r14
0x140017ae6  pop     rdi
0x140017ae7  pop     rsi
0x140017ae8  pop     rbp
0x140017ae9  pop     rbx
0x140017aea  retn
```
