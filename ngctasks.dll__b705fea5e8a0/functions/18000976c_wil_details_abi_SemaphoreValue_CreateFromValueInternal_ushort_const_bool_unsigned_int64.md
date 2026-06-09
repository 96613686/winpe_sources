# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000976c`
- end: `0x18000988d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b7d4`
- `0x180018e10`

## callees

- `0x180006330`
- `0x18000976c`
- `0x18000cc34`
- `0x18000de7c`
- `0x18000df08`
- `0x18000eb94`
- `0x18000ecf8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x18000976c  push    rbx
0x18000976e  push    rbp
0x18000976f  push    rsi
0x180009770  push    rdi
0x180009771  push    r14
0x180009773  sub     rsp, 260h
0x18000977a  mov     rax, cs:__security_cookie
0x180009781  xor     rax, rsp
0x180009784  mov     [rsp+288h+var_38], rax
0x18000978c  mov     rax, 0C000000000000000h
0x180009796  mov     rbx, r9
0x180009799  mov     rbp, rcx
0x18000979c  test    rax, r9
0x18000979f  jz      short loc_1800097A7
0x1800097a1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800097a7  mov     r8, rdx; unsigned __int16 *
0x1800097aa  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800097af  mov     r14d, 104h
0x1800097b5  mov     edx, r14d; unsigned __int64
0x1800097b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800097bd  lea     r8, aP0; "_p0"
0x1800097c4  mov     edx, r14d; unsigned __int64
0x1800097c7  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800097cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097d1  mov     edx, ebx
0x1800097d3  lea     r9, [rsp+288h+var_248]
0x1800097d8  and     edx, 7FFFFFFFh
0x1800097de  mov     esi, 1
0x1800097e3  mov     r8d, esi
0x1800097e6  mov     rcx, rbp
0x1800097e9  cmova   r8d, edx
0x1800097ed  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800097f2  mov     edi, eax
0x1800097f4  test    eax, eax
0x1800097f6  jns     short loc_180009817
0x1800097f8  mov     rcx, [rsp+288h]; this
0x180009800  lea     r8, aWil; "wil"
0x180009807  mov     r9d, eax; char *
0x18000980a  lea     edx, [r14-79h]; void *
0x18000980e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009813  mov     eax, edi
0x180009815  jmp     short loc_18000986F
0x180009817  lea     r8, asc_180024AC0; "h"
0x18000981e  shr     rbx, 1Fh
0x180009822  mov     rdx, r14; unsigned __int64
0x180009825  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000982a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000982f  test    ebx, ebx
0x180009831  lea     rcx, [rbp+8]
0x180009835  lea     r9, [rsp+288h+var_248]
0x18000983a  mov     edx, ebx
0x18000983c  cmovnz  esi, ebx
0x18000983f  mov     r8d, esi
0x180009842  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180009847  mov     ebx, eax
0x180009849  test    eax, eax
0x18000984b  jns     short loc_18000986D
0x18000984d  mov     rcx, [rsp+288h]; this
0x180009855  lea     r8, aWil; "wil"
0x18000985c  mov     r9d, eax; char *
0x18000985f  mov     edx, 90h; void *
0x180009864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009869  mov     eax, ebx
0x18000986b  jmp     short loc_18000986F
0x18000986d  xor     eax, eax
0x18000986f  mov     rcx, [rsp+288h+var_38]
0x180009877  xor     rcx, rsp; StackCookie
0x18000987a  call    __security_check_cookie
0x18000987f  add     rsp, 260h
0x180009886  pop     r14
0x180009888  pop     rdi
0x180009889  pop     rsi
0x18000988a  pop     rbp
0x18000988b  pop     rbx
0x18000988c  retn
```
