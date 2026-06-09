# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800169a0`
- end: `0x180016ac1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `289`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017ed0`
- `0x180018030`

## callees

- `0x1800112e0`
- `0x180011324`
- `0x1800138ec`
- `0x180014130`
- `0x1800169a0`
- `0x18001a580`
- `0x18001a7c8`

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
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  wchar_t v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x1800169a0  push    rbx
0x1800169a2  push    rbp
0x1800169a3  push    rsi
0x1800169a4  push    rdi
0x1800169a5  push    r14
0x1800169a7  sub     rsp, 260h
0x1800169ae  mov     rax, cs:__security_cookie
0x1800169b5  xor     rax, rsp
0x1800169b8  mov     [rsp+288h+var_38], rax
0x1800169c0  mov     rax, 0C000000000000000h
0x1800169ca  mov     rbx, r9
0x1800169cd  mov     rbp, rcx
0x1800169d0  test    rax, r9
0x1800169d3  jz      short loc_1800169DB
0x1800169d5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800169db  mov     r8, rdx; wchar_t *
0x1800169de  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x1800169e3  mov     r14d, 104h
0x1800169e9  mov     edx, r14d; unsigned __int64
0x1800169ec  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800169f1  lea     r8, aP0; "_p0"
0x1800169f8  mov     edx, r14d; unsigned __int64
0x1800169fb  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x180016a00  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180016a05  mov     edx, ebx
0x180016a07  lea     r9, [rsp+288h+var_248]
0x180016a0c  and     edx, 7FFFFFFFh
0x180016a12  mov     esi, 1
0x180016a17  mov     r8d, esi
0x180016a1a  mov     rcx, rbp
0x180016a1d  cmova   r8d, edx
0x180016a21  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180016a26  mov     edi, eax
0x180016a28  test    eax, eax
0x180016a2a  jns     short loc_180016A4B
0x180016a2c  mov     rcx, [rsp+288h]; this
0x180016a34  lea     r8, aWil; "wil"
0x180016a3b  mov     r9d, eax; char *
0x180016a3e  lea     edx, [r14-79h]; void *
0x180016a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a47  mov     eax, edi
0x180016a49  jmp     short loc_180016AA3
0x180016a4b  lea     r8, asc_180031750; "h"
0x180016a52  shr     rbx, 1Fh
0x180016a56  mov     rdx, r14; unsigned __int64
0x180016a59  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x180016a5e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180016a63  test    ebx, ebx
0x180016a65  lea     rcx, [rbp+8]
0x180016a69  lea     r9, [rsp+288h+var_248]
0x180016a6e  mov     edx, ebx
0x180016a70  cmovnz  esi, ebx
0x180016a73  mov     r8d, esi
0x180016a76  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180016a7b  mov     ebx, eax
0x180016a7d  test    eax, eax
0x180016a7f  jns     short loc_180016AA1
0x180016a81  mov     rcx, [rsp+288h]; this
0x180016a89  lea     r8, aWil; "wil"
0x180016a90  mov     r9d, eax; char *
0x180016a93  mov     edx, 90h; void *
0x180016a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a9d  mov     eax, ebx
0x180016a9f  jmp     short loc_180016AA3
0x180016aa1  xor     eax, eax
0x180016aa3  mov     rcx, [rsp+288h+var_38]
0x180016aab  xor     rcx, rsp; StackCookie
0x180016aae  call    __security_check_cookie
0x180016ab3  add     rsp, 260h
0x180016aba  pop     r14
0x180016abc  pop     rdi
0x180016abd  pop     rsi
0x180016abe  pop     rbp
0x180016abf  pop     rbx
0x180016ac0  retn
```
