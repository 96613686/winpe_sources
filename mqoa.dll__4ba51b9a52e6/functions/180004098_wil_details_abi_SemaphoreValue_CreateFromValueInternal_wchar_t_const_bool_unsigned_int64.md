# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180004098`
- end: `0x1800041a8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b08`
- `0x180005c34`

## callees

- `0x180004098`
- `0x180006e6c`
- `0x18000752c`
- `0x1800075a8`
- `0x18000815c`
- `0x180008308`
- `0x1800273b0`

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
  StringCchCopyW(v19, 0x104u, a2);
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
0x180004098  mov     [rsp+arg_10], rbx
0x18000409d  push    rbp
0x18000409e  push    rsi
0x18000409f  push    rdi
0x1800040a0  sub     rsp, 260h
0x1800040a7  mov     rax, cs:__security_cookie
0x1800040ae  xor     rax, rsp
0x1800040b1  mov     [rsp+278h+var_28], rax
0x1800040b9  mov     rax, 0C000000000000000h
0x1800040c3  mov     rbx, r9
0x1800040c6  mov     rbp, rcx
0x1800040c9  test    rax, r9
0x1800040cc  jz      short loc_1800040D4
0x1800040ce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800040d4  mov     r8, rdx; wchar_t *
0x1800040d7  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800040dc  mov     edx, 104h; unsigned __int64
0x1800040e1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800040e6  lea     r8, aP0; "_p0"
0x1800040ed  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800040f2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800040f7  mov     edx, ebx
0x1800040f9  lea     r9, [rsp+278h+var_238]
0x1800040fe  and     edx, 7FFFFFFFh
0x180004104  mov     esi, 1
0x180004109  mov     r8d, esi
0x18000410c  mov     rcx, rbp
0x18000410f  cmova   r8d, edx
0x180004113  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004118  mov     edi, eax
0x18000411a  test    eax, eax
0x18000411c  jns     short loc_180004137
0x18000411e  mov     rcx, [rsp+278h]; this
0x180004126  mov     r9d, eax; char *
0x180004129  mov     edx, 8Bh; void *
0x18000412e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004133  mov     eax, edi
0x180004135  jmp     short loc_180004185
0x180004137  lea     r8, asc_18002F138; "h"
0x18000413e  shr     rbx, 1Fh
0x180004142  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180004147  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000414c  test    ebx, ebx
0x18000414e  lea     rcx, [rbp+8]
0x180004152  lea     r9, [rsp+278h+var_238]
0x180004157  mov     edx, ebx
0x180004159  cmovnz  esi, ebx
0x18000415c  mov     r8d, esi
0x18000415f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004164  mov     ebx, eax
0x180004166  test    eax, eax
0x180004168  jns     short loc_180004183
0x18000416a  mov     rcx, [rsp+278h]; this
0x180004172  mov     r9d, eax; char *
0x180004175  mov     edx, 90h; void *
0x18000417a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000417f  mov     eax, ebx
0x180004181  jmp     short loc_180004185
0x180004183  xor     eax, eax
0x180004185  mov     rcx, [rsp+278h+var_28]
0x18000418d  xor     rcx, rsp; StackCookie
0x180004190  call    __security_check_cookie
0x180004195  mov     rbx, [rsp+278h+arg_10]
0x18000419d  add     rsp, 260h
0x1800041a4  pop     rdi
0x1800041a5  pop     rsi
0x1800041a6  pop     rbp
0x1800041a7  retn
```
