# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006698`
- end: `0x1800067d0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `312`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c9c`
- `0x180007df0`

## callees

- `0x180004310`
- `0x180006698`
- `0x180008b68`
- `0x1800092e0`
- `0x18000941c`
- `0x180009e10`
- `0x180009f9c`

## string_xrefs

- `0x180006736`: `m_semaphore.create(static_cast<LONG>(lowPart), static_cast<LONG>((lowPart > 0) ? lowPart : 1), localName)`
- `0x180006726`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`
- `0x180006786`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`
- `0x180006796`: `m_semaphoreHigh.create(static_cast<LONG>(highPart), static_cast<LONG>((highPart > 0) ? highPart : 1), localName)`

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
  char *v18; // [rsp+20h] [rbp-258h]
  wil::details *v19; // [rsp+28h] [rbp-250h]
  int v20; // [rsp+30h] [rbp-248h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag5::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, (size_t)v18);
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
      LODWORD(v19) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x90,
        v16,
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        "m_semaphoreHigh.create(static_cast<LONG>(highPart), static_cast<LONG>((highPart > 0) ? highPart : 1), localName)",
        v19,
        v20);
      return v17;
    }
  }
  else
  {
    LODWORD(v19) = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
      "m_semaphore.create(static_cast<LONG>(lowPart), static_cast<LONG>((lowPart > 0) ? lowPart : 1), localName)",
      v19,
      v20);
    return v12;
  }
}

```

## disassembly

```asm
0x180006698  mov     [rsp+arg_10], rbx
0x18000669d  push    rbp
0x18000669e  push    rsi
0x18000669f  push    rdi
0x1800066a0  sub     rsp, 260h
0x1800066a7  mov     rax, cs:__security_cookie
0x1800066ae  xor     rax, rsp
0x1800066b1  mov     [rsp+278h+var_28], rax
0x1800066b9  mov     rax, 0C000000000000000h
0x1800066c3  mov     rbx, r9
0x1800066c6  mov     rbp, rcx
0x1800066c9  test    rax, r9
0x1800066cc  jz      short loc_1800066D4
0x1800066ce  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
0x1800066d4  mov     r9, rdx; pszSrc
0x1800066d7  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800066dc  mov     edx, 104h; cchDest
0x1800066e1  call    StringCopyWorkerW
0x1800066e6  lea     r8, aP0; "_p0"
0x1800066ed  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800066f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800066f7  mov     edx, ebx
0x1800066f9  lea     r9, [rsp+278h+pszDest]
0x1800066fe  and     edx, 7FFFFFFFh
0x180006704  mov     esi, 1
0x180006709  mov     r8d, esi
0x18000670c  mov     rcx, rbp
0x18000670f  cmova   r8d, edx
0x180006713  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006718  mov     edi, eax
0x18000671a  test    eax, eax
0x18000671c  jns     short loc_18000674B
0x18000671e  mov     rcx, [rsp+278h]; this
0x180006726  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x18000672d  mov     dword ptr [rsp+278h+var_250], eax; wil::details *
0x180006731  mov     edx, 8Bh; void *
0x180006736  lea     rax, aMSemaphoreCrea; "m_semaphore.create(static_cast<LONG>(lo"...
0x18000673d  mov     [rsp+278h+var_258], rax; char *
0x180006742  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180006747  mov     eax, edi
0x180006749  jmp     short loc_1800067AD
0x18000674b  lea     r8, asc_18000DDAC; "h"
0x180006752  shr     rbx, 1Fh
0x180006756  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000675b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006760  test    ebx, ebx
0x180006762  lea     rcx, [rbp+8]
0x180006766  lea     r9, [rsp+278h+pszDest]
0x18000676b  mov     edx, ebx
0x18000676d  cmovnz  esi, ebx
0x180006770  mov     r8d, esi
0x180006773  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006778  mov     ebx, eax
0x18000677a  test    eax, eax
0x18000677c  jns     short loc_1800067AB
0x18000677e  mov     rcx, [rsp+278h]; this
0x180006786  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x18000678d  mov     dword ptr [rsp+278h+var_250], eax; wil::details *
0x180006791  mov     edx, 90h; void *
0x180006796  lea     rax, aMSemaphorehigh; "m_semaphoreHigh.create(static_cast<LONG"...
0x18000679d  mov     [rsp+278h+var_258], rax; char *
0x1800067a2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800067a7  mov     eax, ebx
0x1800067a9  jmp     short loc_1800067AD
0x1800067ab  xor     eax, eax
0x1800067ad  mov     rcx, [rsp+278h+var_28]
0x1800067b5  xor     rcx, rsp; StackCookie
0x1800067b8  call    __security_check_cookie
0x1800067bd  mov     rbx, [rsp+278h+arg_10]
0x1800067c5  add     rsp, 260h
0x1800067cc  pop     rdi
0x1800067cd  pop     rsi
0x1800067ce  pop     rbp
0x1800067cf  retn
```
