# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180006438`
- end: `0x18000654f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `279`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000862c`
- `0x18000875c`

## callees

- `0x180003df0`
- `0x180006438`
- `0x18000989c`
- `0x18000a0f4`
- `0x18000abec`
- `0x18000ad98`
- `0x18002f0e0`

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
0x180006438  push    rbx
0x18000643a  push    rbp
0x18000643b  push    rsi
0x18000643c  push    rdi
0x18000643d  push    r14
0x18000643f  sub     rsp, 260h
0x180006446  mov     rax, cs:__security_cookie
0x18000644d  xor     rax, rsp
0x180006450  mov     [rsp+288h+var_38], rax
0x180006458  mov     rax, 0C000000000000000h
0x180006462  mov     rbx, r9
0x180006465  mov     rbp, rcx
0x180006468  test    rax, r9
0x18000646b  jnz     loc_180006549
0x180006471  mov     r8, rdx; wchar_t *
0x180006474  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x180006479  mov     r14d, 104h
0x18000647f  mov     edx, r14d; unsigned __int64
0x180006482  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006487  lea     r8, aP0; "_p0"
0x18000648e  mov     edx, r14d; unsigned __int64
0x180006491  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x180006496  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000649b  mov     edx, ebx
0x18000649d  lea     r9, [rsp+288h+var_248]
0x1800064a2  and     edx, 7FFFFFFFh
0x1800064a8  mov     esi, 1
0x1800064ad  mov     r8d, esi
0x1800064b0  mov     rcx, rbp
0x1800064b3  cmova   r8d, edx
0x1800064b7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800064bc  mov     edi, eax
0x1800064be  test    eax, eax
0x1800064c0  jns     short loc_1800064DA
0x1800064c2  mov     rcx, [rsp+288h]; this
0x1800064ca  lea     edx, [r14-79h]; void *
0x1800064ce  mov     r9d, eax; char *
0x1800064d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064d6  mov     eax, edi
0x1800064d8  jmp     short loc_18000652B
0x1800064da  lea     r8, asc_180034918; "h"
0x1800064e1  shr     rbx, 1Fh
0x1800064e5  mov     rdx, r14; unsigned __int64
0x1800064e8  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x1800064ed  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800064f2  test    ebx, ebx
0x1800064f4  lea     rcx, [rbp+8]
0x1800064f8  lea     r9, [rsp+288h+var_248]
0x1800064fd  mov     edx, ebx
0x1800064ff  cmovnz  esi, ebx
0x180006502  mov     r8d, esi
0x180006505  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000650a  mov     ebx, eax
0x18000650c  test    eax, eax
0x18000650e  jns     short loc_180006529
0x180006510  mov     rcx, [rsp+288h]; this
0x180006518  mov     r9d, eax; char *
0x18000651b  mov     edx, 90h; void *
0x180006520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006525  mov     eax, ebx
0x180006527  jmp     short loc_18000652B
0x180006529  xor     eax, eax
0x18000652b  mov     rcx, [rsp+288h+var_38]
0x180006533  xor     rcx, rsp; StackCookie
0x180006536  call    __security_check_cookie
0x18000653b  add     rsp, 260h
0x180006542  pop     r14
0x180006544  pop     rdi
0x180006545  pop     rsi
0x180006546  pop     rbp
0x180006547  pop     rbx
0x180006548  retn
0x180006549  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
