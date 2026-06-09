# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180005774`
- end: `0x180005880`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `268`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000878c`
- `0x18000bff4`

## callees

- `0x180002af0`
- `0x180005774`
- `0x180008e34`
- `0x180009448`
- `0x180009498`
- `0x180009b10`
- `0x180009bd8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  wchar_t v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, (unsigned __int64)a2, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x180005774  mov     [rsp+arg_10], rbx
0x180005779  push    rbp
0x18000577a  push    rsi
0x18000577b  push    rdi
0x18000577c  sub     rsp, 260h
0x180005783  mov     rax, cs:__security_cookie
0x18000578a  xor     rax, rsp
0x18000578d  mov     [rsp+278h+var_28], rax
0x180005795  mov     rax, 0C000000000000000h
0x18000579f  mov     rbx, r9
0x1800057a2  mov     rbp, rcx
0x1800057a5  test    rax, r9
0x1800057a8  jz      short loc_1800057B0
0x1800057aa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800057b0  mov     r8, rdx; wchar_t *
0x1800057b3  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800057b8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800057bd  lea     r8, aP0; "_p0"
0x1800057c4  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800057c9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800057ce  mov     edx, ebx
0x1800057d0  lea     r9, [rsp+278h+var_238]
0x1800057d5  and     edx, 7FFFFFFFh
0x1800057db  mov     esi, 1
0x1800057e0  mov     r8d, esi
0x1800057e3  mov     rcx, rbp
0x1800057e6  cmova   r8d, edx
0x1800057ea  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800057ef  mov     edi, eax
0x1800057f1  test    eax, eax
0x1800057f3  jns     short loc_18000580E
0x1800057f5  mov     rcx, [rsp+278h]; this
0x1800057fd  mov     r9d, eax; char *
0x180005800  mov     edx, 8Bh; void *
0x180005805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000580a  mov     eax, edi
0x18000580c  jmp     short loc_18000585C
0x18000580e  lea     r8, asc_18003CDD8; "h"
0x180005815  shr     rbx, 1Fh
0x180005819  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x18000581e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005823  test    ebx, ebx
0x180005825  lea     rcx, [rbp+8]
0x180005829  lea     r9, [rsp+278h+var_238]
0x18000582e  mov     edx, ebx
0x180005830  cmovnz  esi, ebx
0x180005833  mov     r8d, esi
0x180005836  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000583b  mov     ebx, eax
0x18000583d  test    eax, eax
0x18000583f  jns     short loc_18000585A
0x180005841  mov     rcx, [rsp+278h]; this
0x180005849  mov     r9d, eax; char *
0x18000584c  mov     edx, 90h; void *
0x180005851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005856  mov     eax, ebx
0x180005858  jmp     short loc_18000585C
0x18000585a  xor     eax, eax
0x18000585c  mov     rcx, [rsp+278h+var_28]
0x180005864  xor     rcx, rsp; StackCookie
0x180005867  call    __security_check_cookie
0x18000586c  mov     rbx, [rsp+278h+arg_10]
0x180005874  add     rsp, 260h
0x18000587b  pop     rdi
0x18000587c  pop     rsi
0x18000587d  pop     rbp
0x18000587e  retn
```
