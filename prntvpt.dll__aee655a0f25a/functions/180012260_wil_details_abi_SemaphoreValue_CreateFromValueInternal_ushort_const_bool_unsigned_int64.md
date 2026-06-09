# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180012260`
- end: `0x180012370`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013f58`
- `0x18001407c`

## callees

- `0x18000f970`
- `0x180012260`
- `0x180015fd0`
- `0x1800165a0`
- `0x18001661c`
- `0x180017438`
- `0x180017544`

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
0x180012260  mov     [rsp+arg_10], rbx
0x180012265  push    rbp
0x180012266  push    rsi
0x180012267  push    rdi
0x180012268  sub     rsp, 260h
0x18001226f  mov     rax, cs:__security_cookie
0x180012276  xor     rax, rsp
0x180012279  mov     [rsp+278h+var_28], rax
0x180012281  mov     rax, 0C000000000000000h
0x18001228b  mov     rbx, r9
0x18001228e  mov     rbp, rcx
0x180012291  test    rax, r9
0x180012294  jz      short loc_18001229C
0x180012296  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001229c  mov     r9, rdx; pszSrc
0x18001229f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800122a4  mov     edx, 104h; cchDest
0x1800122a9  call    StringCopyWorkerW
0x1800122ae  lea     r8, aP0; "_p0"
0x1800122b5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800122ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800122bf  mov     edx, ebx
0x1800122c1  lea     r9, [rsp+278h+pszDest]
0x1800122c6  and     edx, 7FFFFFFFh
0x1800122cc  mov     esi, 1
0x1800122d1  mov     r8d, esi
0x1800122d4  mov     rcx, rbp
0x1800122d7  cmova   r8d, edx
0x1800122db  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800122e0  mov     edi, eax
0x1800122e2  test    eax, eax
0x1800122e4  jns     short loc_1800122FF
0x1800122e6  mov     rcx, [rsp+278h]; this
0x1800122ee  mov     r9d, eax; char *
0x1800122f1  mov     edx, 8Bh; void *
0x1800122f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800122fb  mov     eax, edi
0x1800122fd  jmp     short loc_18001234D
0x1800122ff  lea     r8, asc_180027BD8; "h"
0x180012306  shr     rbx, 1Fh
0x18001230a  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18001230f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012314  test    ebx, ebx
0x180012316  lea     rcx, [rbp+8]
0x18001231a  lea     r9, [rsp+278h+pszDest]
0x18001231f  mov     edx, ebx
0x180012321  cmovnz  esi, ebx
0x180012324  mov     r8d, esi
0x180012327  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001232c  mov     ebx, eax
0x18001232e  test    eax, eax
0x180012330  jns     short loc_18001234B
0x180012332  mov     rcx, [rsp+278h]; this
0x18001233a  mov     r9d, eax; char *
0x18001233d  mov     edx, 90h; void *
0x180012342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012347  mov     eax, ebx
0x180012349  jmp     short loc_18001234D
0x18001234b  xor     eax, eax
0x18001234d  mov     rcx, [rsp+278h+var_28]
0x180012355  xor     rcx, rsp; StackCookie
0x180012358  call    __security_check_cookie
0x18001235d  mov     rbx, [rsp+278h+arg_10]
0x180012365  add     rsp, 260h
0x18001236c  pop     rdi
0x18001236d  pop     rsi
0x18001236e  pop     rbp
0x18001236f  retn
```
