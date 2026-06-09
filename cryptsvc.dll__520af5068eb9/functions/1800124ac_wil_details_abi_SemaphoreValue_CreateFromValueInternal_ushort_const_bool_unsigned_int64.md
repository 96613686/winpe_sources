# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800124ac`
- end: `0x1800125bc`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d7a4`
- `0x18000d8f8`

## callees

- `0x18000b760`
- `0x18000b9f4`
- `0x18000da54`
- `0x18000e2f0`
- `0x1800124ac`
- `0x180015754`
- `0x180015810`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
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
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x1800124ac  mov     [rsp+arg_10], rbx
0x1800124b1  push    rbp
0x1800124b2  push    rsi
0x1800124b3  push    rdi
0x1800124b4  sub     rsp, 260h
0x1800124bb  mov     rax, cs:__security_cookie
0x1800124c2  xor     rax, rsp
0x1800124c5  mov     [rsp+278h+var_28], rax
0x1800124cd  mov     rax, 0C000000000000000h
0x1800124d7  mov     rbx, r9
0x1800124da  mov     rbp, rcx
0x1800124dd  test    rax, r9
0x1800124e0  jz      short loc_1800124E8
0x1800124e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800124e8  mov     r8, rdx; unsigned __int16 *
0x1800124eb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800124f0  mov     edx, 104h; unsigned __int64
0x1800124f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800124fa  lea     r8, aP0; "_p0"
0x180012501  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180012506  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001250b  mov     edx, ebx
0x18001250d  lea     r9, [rsp+278h+var_238]
0x180012512  and     edx, 7FFFFFFFh
0x180012518  mov     esi, 1
0x18001251d  mov     r8d, esi
0x180012520  mov     rcx, rbp
0x180012523  cmova   r8d, edx
0x180012527  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001252c  mov     edi, eax
0x18001252e  test    eax, eax
0x180012530  jns     short loc_18001254B
0x180012532  mov     rcx, [rsp+278h]; this
0x18001253a  mov     r9d, eax; char *
0x18001253d  mov     edx, 8Bh; void *
0x180012542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012547  mov     eax, edi
0x180012549  jmp     short loc_180012599
0x18001254b  lea     r8, asc_18001B330; "h"
0x180012552  shr     rbx, 1Fh
0x180012556  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18001255b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012560  test    ebx, ebx
0x180012562  lea     rcx, [rbp+8]
0x180012566  lea     r9, [rsp+278h+var_238]
0x18001256b  mov     edx, ebx
0x18001256d  cmovnz  esi, ebx
0x180012570  mov     r8d, esi
0x180012573  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180012578  mov     ebx, eax
0x18001257a  test    eax, eax
0x18001257c  jns     short loc_180012597
0x18001257e  mov     rcx, [rsp+278h]; this
0x180012586  mov     r9d, eax; char *
0x180012589  mov     edx, 90h; void *
0x18001258e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012593  mov     eax, ebx
0x180012595  jmp     short loc_180012599
0x180012597  xor     eax, eax
0x180012599  mov     rcx, [rsp+278h+var_28]
0x1800125a1  xor     rcx, rsp; StackCookie
0x1800125a4  call    __security_check_cookie
0x1800125a9  mov     rbx, [rsp+278h+arg_10]
0x1800125b1  add     rsp, 260h
0x1800125b8  pop     rdi
0x1800125b9  pop     rsi
0x1800125ba  pop     rbp
0x1800125bb  retn
```
