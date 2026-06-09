# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400043e4`
- end: `0x1400044f4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400054dc`
- `0x140007dd0`

## callees

- `0x1400029a0`
- `0x1400043e4`
- `0x1400059c4`
- `0x140005f24`
- `0x140005fa0`
- `0x140006564`
- `0x140006628`

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
0x1400043e4  mov     [rsp+arg_10], rbx
0x1400043e9  push    rbp
0x1400043ea  push    rsi
0x1400043eb  push    rdi
0x1400043ec  sub     rsp, 260h
0x1400043f3  mov     rax, cs:__security_cookie
0x1400043fa  xor     rax, rsp
0x1400043fd  mov     [rsp+278h+var_28], rax
0x140004405  mov     rax, 0C000000000000000h
0x14000440f  mov     rbx, r9
0x140004412  mov     rbp, rcx
0x140004415  test    rax, r9
0x140004418  jz      short loc_140004420
0x14000441a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004420  mov     r8, rdx; unsigned __int16 *
0x140004423  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004428  mov     edx, 104h; unsigned __int64
0x14000442d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004432  lea     r8, aP0; "_p0"
0x140004439  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000443e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004443  mov     edx, ebx
0x140004445  lea     r9, [rsp+278h+var_238]
0x14000444a  and     edx, 7FFFFFFFh
0x140004450  mov     esi, 1
0x140004455  mov     r8d, esi
0x140004458  mov     rcx, rbp
0x14000445b  cmova   r8d, edx
0x14000445f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004464  mov     edi, eax
0x140004466  test    eax, eax
0x140004468  jns     short loc_140004483
0x14000446a  mov     rcx, [rsp+278h]; this
0x140004472  mov     r9d, eax; char *
0x140004475  mov     edx, 8Bh; void *
0x14000447a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000447f  mov     eax, edi
0x140004481  jmp     short loc_1400044D1
0x140004483  lea     r8, asc_140019FF0; "h"
0x14000448a  shr     rbx, 1Fh
0x14000448e  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004493  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004498  test    ebx, ebx
0x14000449a  lea     rcx, [rbp+8]
0x14000449e  lea     r9, [rsp+278h+var_238]
0x1400044a3  mov     edx, ebx
0x1400044a5  cmovnz  esi, ebx
0x1400044a8  mov     r8d, esi
0x1400044ab  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400044b0  mov     ebx, eax
0x1400044b2  test    eax, eax
0x1400044b4  jns     short loc_1400044CF
0x1400044b6  mov     rcx, [rsp+278h]; this
0x1400044be  mov     r9d, eax; char *
0x1400044c1  mov     edx, 90h; void *
0x1400044c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400044cb  mov     eax, ebx
0x1400044cd  jmp     short loc_1400044D1
0x1400044cf  xor     eax, eax
0x1400044d1  mov     rcx, [rsp+278h+var_28]
0x1400044d9  xor     rcx, rsp; StackCookie
0x1400044dc  call    __security_check_cookie
0x1400044e1  mov     rbx, [rsp+278h+arg_10]
0x1400044e9  add     rsp, 260h
0x1400044f0  pop     rdi
0x1400044f1  pop     rsi
0x1400044f2  pop     rbp
0x1400044f3  retn
```
