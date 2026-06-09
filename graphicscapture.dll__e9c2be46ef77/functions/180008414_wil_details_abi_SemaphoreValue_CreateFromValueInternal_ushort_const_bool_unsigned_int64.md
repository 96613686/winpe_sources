# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008414`
- end: `0x180008532`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009bd0`
- `0x180009d34`

## callees

- `0x180001640`
- `0x180008414`
- `0x18000b18c`
- `0x18000b84c`
- `0x18000b92c`
- `0x18000c544`
- `0x18000c738`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            pszDest);
    v15 = v14;
    if ( v14 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v14,
        v17);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x180008414  mov     [rsp+arg_10], rbx
0x180008419  push    rbp
0x18000841a  push    rsi
0x18000841b  push    rdi
0x18000841c  sub     rsp, 260h
0x180008423  mov     rax, cs:__security_cookie
0x18000842a  xor     rax, rsp
0x18000842d  mov     [rsp+278h+var_28], rax
0x180008435  mov     rax, 0C000000000000000h
0x18000843f  mov     rbx, r9
0x180008442  mov     rbp, rcx
0x180008445  test    rax, r9
0x180008448  jz      short loc_180008450
0x18000844a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008450  mov     r9, rdx; pszSrc
0x180008453  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180008458  mov     edx, 104h; cchDest
0x18000845d  call    StringCopyWorkerW
0x180008462  lea     r8, aP0; "_p0"
0x180008469  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000846e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008473  mov     edx, ebx
0x180008475  lea     r9, [rsp+278h+pszDest]
0x18000847a  and     edx, 7FFFFFFFh
0x180008480  mov     esi, 1
0x180008485  mov     r8d, esi
0x180008488  mov     rcx, rbp
0x18000848b  cmova   r8d, edx
0x18000848f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180008494  mov     edi, eax
0x180008496  test    eax, eax
0x180008498  jns     short loc_1800084BA
0x18000849a  mov     rcx, [rsp+278h]; this
0x1800084a2  lea     r8, aWil; "wil"
0x1800084a9  mov     r9d, eax; char *
0x1800084ac  mov     edx, 8Bh; void *
0x1800084b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084b6  mov     eax, edi
0x1800084b8  jmp     short loc_18000850F
0x1800084ba  lea     r8, asc_18002D068; "h"
0x1800084c1  shr     rbx, 1Fh
0x1800084c5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800084ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800084cf  test    ebx, ebx
0x1800084d1  lea     rcx, [rbp+8]
0x1800084d5  lea     r9, [rsp+278h+pszDest]
0x1800084da  mov     edx, ebx
0x1800084dc  cmovnz  esi, ebx
0x1800084df  mov     r8d, esi
0x1800084e2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800084e7  mov     ebx, eax
0x1800084e9  test    eax, eax
0x1800084eb  jns     short loc_18000850D
0x1800084ed  mov     rcx, [rsp+278h]; this
0x1800084f5  lea     r8, aWil; "wil"
0x1800084fc  mov     r9d, eax; char *
0x1800084ff  mov     edx, 90h; void *
0x180008504  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008509  mov     eax, ebx
0x18000850b  jmp     short loc_18000850F
0x18000850d  xor     eax, eax
0x18000850f  mov     rcx, [rsp+278h+var_28]
0x180008517  xor     rcx, rsp; StackCookie
0x18000851a  call    __security_check_cookie
0x18000851f  mov     rbx, [rsp+278h+arg_10]
0x180008527  add     rsp, 260h
0x18000852e  pop     rdi
0x18000852f  pop     rsi
0x180008530  pop     rbp
0x180008531  retn
```
