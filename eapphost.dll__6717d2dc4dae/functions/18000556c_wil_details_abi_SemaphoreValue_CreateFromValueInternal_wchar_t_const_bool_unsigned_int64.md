# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000556c`
- end: `0x180005677`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `267`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008448`
- `0x18000bb04`

## callees

- `0x180002a90`
- `0x18000556c`
- `0x180008aa4`
- `0x180009094`
- `0x1800090e0`
- `0x180009728`
- `0x1800097ec`

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
0x18000556c  mov     [rsp+arg_10], rbx
0x180005571  push    rbp
0x180005572  push    rsi
0x180005573  push    rdi
0x180005574  sub     rsp, 260h
0x18000557b  mov     rax, cs:__security_cookie
0x180005582  xor     rax, rsp
0x180005585  mov     [rsp+278h+var_28], rax
0x18000558d  mov     rax, 0C000000000000000h
0x180005597  mov     rbx, r9
0x18000559a  mov     rbp, rcx
0x18000559d  test    rax, r9
0x1800055a0  jz      short loc_1800055A8
0x1800055a2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800055a8  mov     r8, rdx; wchar_t *
0x1800055ab  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800055b0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800055b5  lea     r8, aP0; "_p0"
0x1800055bc  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800055c1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800055c6  mov     edx, ebx
0x1800055c8  lea     r9, [rsp+278h+var_238]
0x1800055cd  and     edx, 7FFFFFFFh
0x1800055d3  mov     esi, 1
0x1800055d8  mov     r8d, esi
0x1800055db  mov     rcx, rbp
0x1800055de  cmova   r8d, edx
0x1800055e2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800055e7  mov     edi, eax
0x1800055e9  test    eax, eax
0x1800055eb  jns     short loc_180005606
0x1800055ed  mov     rcx, [rsp+278h]; this
0x1800055f5  mov     r9d, eax; char *
0x1800055f8  mov     edx, 8Bh; void *
0x1800055fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005602  mov     eax, edi
0x180005604  jmp     short loc_180005654
0x180005606  lea     r8, asc_18003BDD8; "h"
0x18000560d  shr     rbx, 1Fh
0x180005611  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180005616  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000561b  test    ebx, ebx
0x18000561d  lea     rcx, [rbp+8]
0x180005621  lea     r9, [rsp+278h+var_238]
0x180005626  mov     edx, ebx
0x180005628  cmovnz  esi, ebx
0x18000562b  mov     r8d, esi
0x18000562e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005633  mov     ebx, eax
0x180005635  test    eax, eax
0x180005637  jns     short loc_180005652
0x180005639  mov     rcx, [rsp+278h]; this
0x180005641  mov     r9d, eax; char *
0x180005644  mov     edx, 90h; void *
0x180005649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000564e  mov     eax, ebx
0x180005650  jmp     short loc_180005654
0x180005652  xor     eax, eax
0x180005654  mov     rcx, [rsp+278h+var_28]
0x18000565c  xor     rcx, rsp; StackCookie
0x18000565f  call    __security_check_cookie
0x180005664  mov     rbx, [rsp+278h+arg_10]
0x18000566c  add     rsp, 260h
0x180005673  pop     rdi
0x180005674  pop     rsi
0x180005675  pop     rbp
0x180005676  retn
```
