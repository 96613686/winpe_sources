# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007074`
- end: `0x180007187`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008104`

## callees

- `0x180001e70`
- `0x180007074`
- `0x180008794`
- `0x180008c6c`
- `0x180008cf8`
- `0x180009210`
- `0x1800092d8`

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
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x180007074  push    rbx
0x180007076  push    rbp
0x180007077  push    rsi
0x180007078  push    rdi
0x180007079  push    r14
0x18000707b  sub     rsp, 260h
0x180007082  mov     rax, cs:__security_cookie
0x180007089  xor     rax, rsp
0x18000708c  mov     [rsp+288h+var_38], rax
0x180007094  mov     rax, 0C000000000000000h
0x18000709e  mov     rbx, r9
0x1800070a1  mov     rbp, rcx
0x1800070a4  test    rax, r9
0x1800070a7  jz      short loc_1800070AF
0x1800070a9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800070af  mov     r8, rdx; unsigned __int16 *
0x1800070b2  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800070b7  mov     r14d, 104h
0x1800070bd  mov     edx, r14d; unsigned __int64
0x1800070c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800070c5  lea     r8, aP0; "_p0"
0x1800070cc  mov     edx, r14d; unsigned __int64
0x1800070cf  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800070d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070d9  mov     edx, ebx
0x1800070db  lea     r9, [rsp+288h+var_248]
0x1800070e0  and     edx, 7FFFFFFFh
0x1800070e6  mov     esi, 1
0x1800070eb  mov     r8d, esi
0x1800070ee  mov     rcx, rbp
0x1800070f1  cmova   r8d, edx
0x1800070f5  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800070fa  mov     edi, eax
0x1800070fc  test    eax, eax
0x1800070fe  jns     short loc_180007118
0x180007100  mov     rcx, [rsp+288h]; this
0x180007108  lea     edx, [r14-79h]; void *
0x18000710c  mov     r9d, eax; char *
0x18000710f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007114  mov     eax, edi
0x180007116  jmp     short loc_180007169
0x180007118  lea     r8, asc_1800176A0; "h"
0x18000711f  shr     rbx, 1Fh
0x180007123  mov     rdx, r14; unsigned __int64
0x180007126  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000712b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007130  test    ebx, ebx
0x180007132  lea     rcx, [rbp+8]
0x180007136  lea     r9, [rsp+288h+var_248]
0x18000713b  mov     edx, ebx
0x18000713d  cmovnz  esi, ebx
0x180007140  mov     r8d, esi
0x180007143  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180007148  mov     ebx, eax
0x18000714a  test    eax, eax
0x18000714c  jns     short loc_180007167
0x18000714e  mov     rcx, [rsp+288h]; this
0x180007156  mov     r9d, eax; char *
0x180007159  mov     edx, 90h; void *
0x18000715e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007163  mov     eax, ebx
0x180007165  jmp     short loc_180007169
0x180007167  xor     eax, eax
0x180007169  mov     rcx, [rsp+288h+var_38]
0x180007171  xor     rcx, rsp; StackCookie
0x180007174  call    __security_check_cookie
0x180007179  add     rsp, 260h
0x180007180  pop     r14
0x180007182  pop     rdi
0x180007183  pop     rsi
0x180007184  pop     rbp
0x180007185  pop     rbx
0x180007186  retn
```
