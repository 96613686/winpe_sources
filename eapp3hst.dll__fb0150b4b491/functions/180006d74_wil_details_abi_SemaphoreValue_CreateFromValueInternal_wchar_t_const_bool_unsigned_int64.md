# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180006d74`
- end: `0x180006e7f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `267`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ff4`
- `0x180009148`

## callees

- `0x1800017a0`
- `0x1800046b8`
- `0x180006d74`
- `0x18000a76c`
- `0x18000ae6c`
- `0x18000b944`
- `0x18000bb20`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180006d74  mov     [rsp+arg_10], rbx
0x180006d79  push    rbp
0x180006d7a  push    rsi
0x180006d7b  push    rdi
0x180006d7c  sub     rsp, 260h
0x180006d83  mov     rax, cs:__security_cookie
0x180006d8a  xor     rax, rsp
0x180006d8d  mov     [rsp+278h+var_28], rax
0x180006d95  mov     rax, 0C000000000000000h
0x180006d9f  mov     rbx, r9
0x180006da2  mov     rbp, rcx
0x180006da5  test    rax, r9
0x180006da8  jz      short loc_180006DB0
0x180006daa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006db0  mov     r8, rdx; wchar_t *
0x180006db3  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180006db8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006dbd  lea     r8, aP0; "_p0"
0x180006dc4  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180006dc9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006dce  mov     edx, ebx
0x180006dd0  lea     r9, [rsp+278h+var_238]
0x180006dd5  and     edx, 7FFFFFFFh
0x180006ddb  mov     esi, 1
0x180006de0  mov     r8d, esi
0x180006de3  mov     rcx, rbp
0x180006de6  cmova   r8d, edx
0x180006dea  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006def  mov     edi, eax
0x180006df1  test    eax, eax
0x180006df3  jns     short loc_180006E0E
0x180006df5  mov     rcx, [rsp+278h]; this
0x180006dfd  mov     r9d, eax; char *
0x180006e00  mov     edx, 8Bh; void *
0x180006e05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e0a  mov     eax, edi
0x180006e0c  jmp     short loc_180006E5C
0x180006e0e  lea     r8, asc_180039520; "h"
0x180006e15  shr     rbx, 1Fh
0x180006e19  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180006e1e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006e23  test    ebx, ebx
0x180006e25  lea     rcx, [rbp+8]
0x180006e29  lea     r9, [rsp+278h+var_238]
0x180006e2e  mov     edx, ebx
0x180006e30  cmovnz  esi, ebx
0x180006e33  mov     r8d, esi
0x180006e36  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006e3b  mov     ebx, eax
0x180006e3d  test    eax, eax
0x180006e3f  jns     short loc_180006E5A
0x180006e41  mov     rcx, [rsp+278h]; this
0x180006e49  mov     r9d, eax; char *
0x180006e4c  mov     edx, 90h; void *
0x180006e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e56  mov     eax, ebx
0x180006e58  jmp     short loc_180006E5C
0x180006e5a  xor     eax, eax
0x180006e5c  mov     rcx, [rsp+278h+var_28]
0x180006e64  xor     rcx, rsp; StackCookie
0x180006e67  call    __security_check_cookie
0x180006e6c  mov     rbx, [rsp+278h+arg_10]
0x180006e74  add     rsp, 260h
0x180006e7b  pop     rdi
0x180006e7c  pop     rsi
0x180006e7d  pop     rbp
0x180006e7e  retn
```
