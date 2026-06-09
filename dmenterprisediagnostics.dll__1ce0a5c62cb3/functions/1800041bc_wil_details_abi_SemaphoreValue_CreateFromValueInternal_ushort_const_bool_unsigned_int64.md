# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800041bc`
- end: `0x1800042dd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052ec`

## callees

- `0x1800017e0`
- `0x1800041bc`
- `0x180005a14`
- `0x180006960`
- `0x1800069ec`
- `0x1800071e0`
- `0x1800072f8`

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
0x1800041bc  push    rbx
0x1800041be  push    rbp
0x1800041bf  push    rsi
0x1800041c0  push    rdi
0x1800041c1  push    r14
0x1800041c3  sub     rsp, 260h
0x1800041ca  mov     rax, cs:__security_cookie
0x1800041d1  xor     rax, rsp
0x1800041d4  mov     [rsp+288h+var_38], rax
0x1800041dc  mov     rax, 0C000000000000000h
0x1800041e6  mov     rbx, r9
0x1800041e9  mov     rbp, rcx
0x1800041ec  test    rax, r9
0x1800041ef  jz      short loc_1800041F7
0x1800041f1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800041f7  mov     r8, rdx; unsigned __int16 *
0x1800041fa  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800041ff  mov     r14d, 104h
0x180004205  mov     edx, r14d; unsigned __int64
0x180004208  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000420d  lea     r8, aP0; "_p0"
0x180004214  mov     edx, r14d; unsigned __int64
0x180004217  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000421c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004221  mov     edx, ebx
0x180004223  lea     r9, [rsp+288h+var_248]
0x180004228  and     edx, 7FFFFFFFh
0x18000422e  mov     esi, 1
0x180004233  mov     r8d, esi
0x180004236  mov     rcx, rbp
0x180004239  cmova   r8d, edx
0x18000423d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004242  mov     edi, eax
0x180004244  test    eax, eax
0x180004246  jns     short loc_180004267
0x180004248  mov     rcx, [rsp+288h]; this
0x180004250  lea     r8, aWil; "wil"
0x180004257  mov     r9d, eax; char *
0x18000425a  lea     edx, [r14-79h]; void *
0x18000425e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004263  mov     eax, edi
0x180004265  jmp     short loc_1800042BF
0x180004267  lea     r8, asc_1800296A0; "h"
0x18000426e  shr     rbx, 1Fh
0x180004272  mov     rdx, r14; unsigned __int64
0x180004275  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000427a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000427f  test    ebx, ebx
0x180004281  lea     rcx, [rbp+8]
0x180004285  lea     r9, [rsp+288h+var_248]
0x18000428a  mov     edx, ebx
0x18000428c  cmovnz  esi, ebx
0x18000428f  mov     r8d, esi
0x180004292  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004297  mov     ebx, eax
0x180004299  test    eax, eax
0x18000429b  jns     short loc_1800042BD
0x18000429d  mov     rcx, [rsp+288h]; this
0x1800042a5  lea     r8, aWil; "wil"
0x1800042ac  mov     r9d, eax; char *
0x1800042af  mov     edx, 90h; void *
0x1800042b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042b9  mov     eax, ebx
0x1800042bb  jmp     short loc_1800042BF
0x1800042bd  xor     eax, eax
0x1800042bf  mov     rcx, [rsp+288h+var_38]
0x1800042c7  xor     rcx, rsp; StackCookie
0x1800042ca  call    __security_check_cookie
0x1800042cf  add     rsp, 260h
0x1800042d6  pop     r14
0x1800042d8  pop     rdi
0x1800042d9  pop     rsi
0x1800042da  pop     rbp
0x1800042db  pop     rbx
0x1800042dc  retn
```
