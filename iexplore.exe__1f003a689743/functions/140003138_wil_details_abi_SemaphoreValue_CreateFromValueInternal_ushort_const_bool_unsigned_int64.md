# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003138`
- end: `0x140003248`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004594`

## callees

- `0x140003138`
- `0x1400049d4`
- `0x140004cec`
- `0x140004d68`
- `0x1400052fc`
- `0x140005388`
- `0x1400059b0`

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
0x140003138  mov     [rsp+arg_10], rbx
0x14000313d  push    rbp
0x14000313e  push    rsi
0x14000313f  push    rdi
0x140003140  sub     rsp, 260h
0x140003147  mov     rax, cs:__security_cookie
0x14000314e  xor     rax, rsp
0x140003151  mov     [rsp+278h+var_28], rax
0x140003159  mov     rax, 0C000000000000000h
0x140003163  mov     rbx, r9
0x140003166  mov     rbp, rcx
0x140003169  test    rax, r9
0x14000316c  jz      short loc_140003174
0x14000316e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003174  mov     r8, rdx; unsigned __int16 *
0x140003177  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000317c  mov     edx, 104h; unsigned __int64
0x140003181  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140003186  lea     r8, aP0; "_p0"
0x14000318d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140003192  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003197  mov     edx, ebx
0x140003199  lea     r9, [rsp+278h+var_238]
0x14000319e  and     edx, 7FFFFFFFh
0x1400031a4  mov     esi, 1
0x1400031a9  mov     r8d, esi
0x1400031ac  mov     rcx, rbp
0x1400031af  cmova   r8d, edx
0x1400031b3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400031b8  mov     edi, eax
0x1400031ba  test    eax, eax
0x1400031bc  jns     short loc_1400031D7
0x1400031be  mov     rcx, [rsp+278h]; this
0x1400031c6  mov     r9d, eax; char *
0x1400031c9  mov     edx, 8Bh; void *
0x1400031ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031d3  mov     eax, edi
0x1400031d5  jmp     short loc_140003225
0x1400031d7  lea     r8, asc_1400078E8; "h"
0x1400031de  shr     rbx, 1Fh
0x1400031e2  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1400031e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400031ec  test    ebx, ebx
0x1400031ee  lea     rcx, [rbp+8]
0x1400031f2  lea     r9, [rsp+278h+var_238]
0x1400031f7  mov     edx, ebx
0x1400031f9  cmovnz  esi, ebx
0x1400031fc  mov     r8d, esi
0x1400031ff  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003204  mov     ebx, eax
0x140003206  test    eax, eax
0x140003208  jns     short loc_140003223
0x14000320a  mov     rcx, [rsp+278h]; this
0x140003212  mov     r9d, eax; char *
0x140003215  mov     edx, 90h; void *
0x14000321a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000321f  mov     eax, ebx
0x140003221  jmp     short loc_140003225
0x140003223  xor     eax, eax
0x140003225  mov     rcx, [rsp+278h+var_28]
0x14000322d  xor     rcx, rsp; StackCookie
0x140003230  call    __security_check_cookie
0x140003235  mov     rbx, [rsp+278h+arg_10]
0x14000323d  add     rsp, 260h
0x140003244  pop     rdi
0x140003245  pop     rsi
0x140003246  pop     rbp
0x140003247  retn
```
