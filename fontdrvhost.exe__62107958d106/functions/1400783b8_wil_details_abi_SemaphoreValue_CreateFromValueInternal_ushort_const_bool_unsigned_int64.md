# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400783b8`
- end: `0x1400784c8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140074f78`
- `0x1400750cc`

## callees

- `0x1400538bc`
- `0x140075228`
- `0x140075de0`
- `0x1400783b8`
- `0x14007accc`
- `0x14007b754`
- `0x14007b86c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x1400783b8  mov     [rsp+arg_10], rbx
0x1400783bd  push    rbp
0x1400783be  push    rsi
0x1400783bf  push    rdi
0x1400783c0  sub     rsp, 260h
0x1400783c7  mov     rax, cs:__security_cookie
0x1400783ce  xor     rax, rsp
0x1400783d1  mov     [rsp+278h+var_28], rax
0x1400783d9  mov     rax, 0C000000000000000h
0x1400783e3  mov     rbx, r9
0x1400783e6  mov     rbp, rcx
0x1400783e9  test    rax, r9
0x1400783ec  jz      short loc_1400783F4
0x1400783ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400783f4  mov     r9, rdx; pszSrc
0x1400783f7  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1400783fc  mov     edx, 104h; cchDest
0x140078401  call    StringCopyWorkerW
0x140078406  lea     r8, aP0; "_p0"
0x14007840d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140078412  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140078417  mov     edx, ebx
0x140078419  lea     r9, [rsp+278h+pszDest]
0x14007841e  and     edx, 7FFFFFFFh
0x140078424  mov     esi, 1
0x140078429  mov     r8d, esi
0x14007842c  mov     rcx, rbp
0x14007842f  cmova   r8d, edx
0x140078433  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140078438  mov     edi, eax
0x14007843a  test    eax, eax
0x14007843c  jns     short loc_140078457
0x14007843e  mov     rcx, [rsp+278h]; this
0x140078446  mov     r9d, eax; char *
0x140078449  mov     edx, 8Bh; void *
0x14007844e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140078453  mov     eax, edi
0x140078455  jmp     short loc_1400784A5
0x140078457  lea     r8, asc_14009D090; "h"
0x14007845e  shr     rbx, 1Fh
0x140078462  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140078467  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007846c  test    ebx, ebx
0x14007846e  lea     rcx, [rbp+8]
0x140078472  lea     r9, [rsp+278h+pszDest]
0x140078477  mov     edx, ebx
0x140078479  cmovnz  esi, ebx
0x14007847c  mov     r8d, esi
0x14007847f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140078484  mov     ebx, eax
0x140078486  test    eax, eax
0x140078488  jns     short loc_1400784A3
0x14007848a  mov     rcx, [rsp+278h]; this
0x140078492  mov     r9d, eax; char *
0x140078495  mov     edx, 90h; void *
0x14007849a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007849f  mov     eax, ebx
0x1400784a1  jmp     short loc_1400784A5
0x1400784a3  xor     eax, eax
0x1400784a5  mov     rcx, [rsp+278h+var_28]
0x1400784ad  xor     rcx, rsp; StackCookie
0x1400784b0  call    __security_check_cookie
0x1400784b5  mov     rbx, [rsp+278h+arg_10]
0x1400784bd  add     rsp, 260h
0x1400784c4  pop     rdi
0x1400784c5  pop     rsi
0x1400784c6  pop     rbp
0x1400784c7  retn
```
