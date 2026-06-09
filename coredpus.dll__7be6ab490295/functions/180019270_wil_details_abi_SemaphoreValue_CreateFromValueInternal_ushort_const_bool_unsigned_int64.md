# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180019270`
- end: `0x18001938f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `287`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a834`
- `0x18001a968`

## callees

- `0x180011d9c`
- `0x180014330`
- `0x1800163d8`
- `0x180019270`
- `0x18001c698`
- `0x18001d4fc`
- `0x18001da3c`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            v17);
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
        v16);
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
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x180019270  mov     [rsp+arg_10], rbx
0x180019275  push    rbp
0x180019276  push    rsi
0x180019277  push    rdi
0x180019278  sub     rsp, 260h
0x18001927f  mov     rax, cs:__security_cookie
0x180019286  xor     rax, rsp
0x180019289  mov     [rsp+278h+var_28], rax
0x180019291  mov     rax, 0C000000000000000h
0x18001929b  mov     rbx, r9
0x18001929e  mov     rbp, rcx
0x1800192a1  test    rax, r9
0x1800192a4  jz      short loc_1800192AC
0x1800192a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800192ac  mov     r8, rdx; unsigned __int16 *
0x1800192af  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800192b4  mov     edx, 104h; unsigned __int64
0x1800192b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800192be  lea     r8, aP0; "_p0"
0x1800192c5  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800192ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800192cf  mov     edx, ebx
0x1800192d1  lea     r9, [rsp+278h+var_238]
0x1800192d6  and     edx, 7FFFFFFFh
0x1800192dc  mov     esi, 1
0x1800192e1  mov     r8d, esi
0x1800192e4  mov     rcx, rbp
0x1800192e7  cmova   r8d, edx
0x1800192eb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800192f0  mov     edi, eax
0x1800192f2  test    eax, eax
0x1800192f4  jns     short loc_180019316
0x1800192f6  mov     rcx, [rsp+278h]; this
0x1800192fe  lea     r8, aWil; "wil"
0x180019305  mov     r9d, eax; char *
0x180019308  mov     edx, 8Bh; void *
0x18001930d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019312  mov     eax, edi
0x180019314  jmp     short loc_18001936B
0x180019316  lea     r8, asc_180034100; "h"
0x18001931d  shr     rbx, 1Fh
0x180019321  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180019326  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001932b  test    ebx, ebx
0x18001932d  lea     rcx, [rbp+8]
0x180019331  lea     r9, [rsp+278h+var_238]
0x180019336  mov     edx, ebx
0x180019338  cmovnz  esi, ebx
0x18001933b  mov     r8d, esi
0x18001933e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180019343  mov     ebx, eax
0x180019345  test    eax, eax
0x180019347  jns     short loc_180019369
0x180019349  mov     rcx, [rsp+278h]; this
0x180019351  lea     r8, aWil; "wil"
0x180019358  mov     r9d, eax; char *
0x18001935b  mov     edx, 90h; void *
0x180019360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019365  mov     eax, ebx
0x180019367  jmp     short loc_18001936B
0x180019369  xor     eax, eax
0x18001936b  mov     rcx, [rsp+278h+var_28]
0x180019373  xor     rcx, rsp; StackCookie
0x180019376  call    __security_check_cookie
0x18001937b  mov     rbx, [rsp+278h+arg_10]
0x180019383  add     rsp, 260h
0x18001938a  pop     rdi
0x18001938b  pop     rsi
0x18001938c  pop     rbp
0x18001938d  retn
```
