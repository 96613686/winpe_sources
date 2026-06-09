# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800767cc`
- end: `0x1800768e0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800783a8`
- `0x1800784d0`

## callees

- `0x1800767cc`
- `0x180079cec`
- `0x18007a224`
- `0x18007a36c`
- `0x18007ae8c`
- `0x18007b030`
- `0x180091140`

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
0x1800767cc  mov     [rsp+arg_10], rbx
0x1800767d1  push    rbp
0x1800767d2  push    rsi
0x1800767d3  push    rdi
0x1800767d4  sub     rsp, 260h
0x1800767db  mov     rax, cs:__security_cookie
0x1800767e2  xor     rax, rsp
0x1800767e5  mov     [rsp+278h+var_28], rax
0x1800767ed  mov     rax, 0C000000000000000h
0x1800767f7  mov     rbx, r9
0x1800767fa  mov     rbp, rcx
0x1800767fd  test    rax, r9
0x180076800  jnz     loc_1800768DA
0x180076806  mov     r9, rdx; pszSrc
0x180076809  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18007680e  mov     edx, 104h; cchDest
0x180076813  call    StringCopyWorkerW
0x180076818  lea     r8, aP0; "_p0"
0x18007681f  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180076824  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180076829  mov     edx, ebx
0x18007682b  lea     r9, [rsp+278h+pszDest]
0x180076830  and     edx, 7FFFFFFFh
0x180076836  mov     esi, 1
0x18007683b  mov     r8d, esi
0x18007683e  mov     rcx, rbp
0x180076841  cmova   r8d, edx
0x180076845  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007684a  mov     edi, eax
0x18007684c  test    eax, eax
0x18007684e  jns     short loc_180076869
0x180076850  mov     rcx, [rsp+278h]; this
0x180076858  mov     r9d, eax; char *
0x18007685b  mov     edx, 8Bh; void *
0x180076860  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076865  mov     eax, edi
0x180076867  jmp     short loc_1800768B7
0x180076869  lea     r8, asc_180099BA0; "h"
0x180076870  shr     rbx, 1Fh
0x180076874  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180076879  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007687e  test    ebx, ebx
0x180076880  lea     rcx, [rbp+8]
0x180076884  lea     r9, [rsp+278h+pszDest]
0x180076889  mov     edx, ebx
0x18007688b  cmovnz  esi, ebx
0x18007688e  mov     r8d, esi
0x180076891  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180076896  mov     ebx, eax
0x180076898  test    eax, eax
0x18007689a  jns     short loc_1800768B5
0x18007689c  mov     rcx, [rsp+278h]; this
0x1800768a4  mov     r9d, eax; char *
0x1800768a7  mov     edx, 90h; void *
0x1800768ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800768b1  mov     eax, ebx
0x1800768b3  jmp     short loc_1800768B7
0x1800768b5  xor     eax, eax
0x1800768b7  mov     rcx, [rsp+278h+var_28]
0x1800768bf  xor     rcx, rsp; StackCookie
0x1800768c2  call    __security_check_cookie
0x1800768c7  mov     rbx, [rsp+278h+arg_10]
0x1800768cf  add     rsp, 260h
0x1800768d6  pop     rdi
0x1800768d7  pop     rsi
0x1800768d8  pop     rbp
0x1800768d9  retn
0x1800768da  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
