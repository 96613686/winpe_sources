# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x140004190`
- end: `0x1400042b1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005280`
- `0x14000f180`

## callees

- `0x140002360`
- `0x140004190`
- `0x1400056ac`
- `0x140005bf0`
- `0x140005c44`
- `0x1400062a4`
- `0x140006370`

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
0x140004190  push    rbx
0x140004192  push    rbp
0x140004193  push    rsi
0x140004194  push    rdi
0x140004195  push    r14
0x140004197  sub     rsp, 260h
0x14000419e  mov     rax, cs:__security_cookie
0x1400041a5  xor     rax, rsp
0x1400041a8  mov     [rsp+288h+var_38], rax
0x1400041b0  mov     rax, 0C000000000000000h
0x1400041ba  mov     rbx, r9
0x1400041bd  mov     rbp, rcx
0x1400041c0  test    rax, r9
0x1400041c3  jz      short loc_1400041CB
0x1400041c5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400041cb  mov     r8, rdx; wchar_t *
0x1400041ce  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x1400041d3  mov     r14d, 104h
0x1400041d9  mov     edx, r14d; unsigned __int64
0x1400041dc  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400041e1  lea     r8, aP0; "_p0"
0x1400041e8  mov     edx, r14d; unsigned __int64
0x1400041eb  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x1400041f0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400041f5  mov     edx, ebx
0x1400041f7  lea     r9, [rsp+288h+var_248]
0x1400041fc  and     edx, 7FFFFFFFh
0x140004202  mov     esi, 1
0x140004207  mov     r8d, esi
0x14000420a  mov     rcx, rbp
0x14000420d  cmova   r8d, edx
0x140004211  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004216  mov     edi, eax
0x140004218  test    eax, eax
0x14000421a  jns     short loc_14000423B
0x14000421c  mov     rcx, [rsp+288h]; this
0x140004224  lea     r8, aWil; "wil"
0x14000422b  mov     r9d, eax; char *
0x14000422e  lea     edx, [r14-79h]; void *
0x140004232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004237  mov     eax, edi
0x140004239  jmp     short loc_140004293
0x14000423b  lea     r8, asc_14002D478; "h"
0x140004242  shr     rbx, 1Fh
0x140004246  mov     rdx, r14; unsigned __int64
0x140004249  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x14000424e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140004253  test    ebx, ebx
0x140004255  lea     rcx, [rbp+8]
0x140004259  lea     r9, [rsp+288h+var_248]
0x14000425e  mov     edx, ebx
0x140004260  cmovnz  esi, ebx
0x140004263  mov     r8d, esi
0x140004266  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000426b  mov     ebx, eax
0x14000426d  test    eax, eax
0x14000426f  jns     short loc_140004291
0x140004271  mov     rcx, [rsp+288h]; this
0x140004279  lea     r8, aWil; "wil"
0x140004280  mov     r9d, eax; char *
0x140004283  mov     edx, 90h; void *
0x140004288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000428d  mov     eax, ebx
0x14000428f  jmp     short loc_140004293
0x140004291  xor     eax, eax
0x140004293  mov     rcx, [rsp+288h+var_38]
0x14000429b  xor     rcx, rsp; StackCookie
0x14000429e  call    __security_check_cookie
0x1400042a3  add     rsp, 260h
0x1400042aa  pop     r14
0x1400042ac  pop     rdi
0x1400042ad  pop     rsi
0x1400042ae  pop     rbp
0x1400042af  pop     rbx
0x1400042b0  retn
```
