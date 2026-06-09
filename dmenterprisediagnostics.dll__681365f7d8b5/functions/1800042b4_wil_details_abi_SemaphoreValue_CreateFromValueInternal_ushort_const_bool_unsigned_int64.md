# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800042b4`
- end: `0x1800043d6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000548c`

## callees

- `0x180001800`
- `0x1800042b4`
- `0x180005c14`
- `0x180006be0`
- `0x180006c6c`
- `0x18000748c`
- `0x1800075b0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        size_t *a2,
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
0x1800042b4  push    rbx
0x1800042b6  push    rbp
0x1800042b7  push    rsi
0x1800042b8  push    rdi
0x1800042b9  push    r14
0x1800042bb  sub     rsp, 260h
0x1800042c2  mov     rax, cs:__security_cookie
0x1800042c9  xor     rax, rsp
0x1800042cc  mov     [rsp+288h+var_38], rax
0x1800042d4  mov     rax, 0C000000000000000h
0x1800042de  mov     rbx, r9
0x1800042e1  mov     rbp, rcx
0x1800042e4  test    rax, r9
0x1800042e7  jz      short loc_1800042EF
0x1800042e9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800042ef  mov     r8, rdx; unsigned __int16 *
0x1800042f2  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800042f7  mov     r14d, 104h
0x1800042fd  mov     edx, r14d; unsigned __int64
0x180004300  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004305  lea     r8, aP0; "_p0"
0x18000430c  mov     edx, r14d; unsigned __int64
0x18000430f  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004314  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004319  mov     edx, ebx
0x18000431b  lea     r9, [rsp+288h+var_248]
0x180004320  and     edx, 7FFFFFFFh
0x180004326  mov     esi, 1
0x18000432b  mov     r8d, esi
0x18000432e  mov     rcx, rbp
0x180004331  cmova   r8d, edx
0x180004335  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000433a  mov     edi, eax
0x18000433c  test    eax, eax
0x18000433e  jns     short loc_18000435F
0x180004340  mov     rcx, [rsp+288h]; this
0x180004348  lea     r8, aWil; "wil"
0x18000434f  mov     r9d, eax; char *
0x180004352  lea     edx, [r14-79h]; void *
0x180004356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000435b  mov     eax, edi
0x18000435d  jmp     short loc_1800043B7
0x18000435f  lea     r8, asc_18002A6A0; "h"
0x180004366  shr     rbx, 1Fh
0x18000436a  mov     rdx, r14; unsigned __int64
0x18000436d  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004372  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004377  test    ebx, ebx
0x180004379  lea     rcx, [rbp+8]
0x18000437d  lea     r9, [rsp+288h+var_248]
0x180004382  mov     edx, ebx
0x180004384  cmovnz  esi, ebx
0x180004387  mov     r8d, esi
0x18000438a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000438f  mov     ebx, eax
0x180004391  test    eax, eax
0x180004393  jns     short loc_1800043B5
0x180004395  mov     rcx, [rsp+288h]; this
0x18000439d  lea     r8, aWil; "wil"
0x1800043a4  mov     r9d, eax; char *
0x1800043a7  mov     edx, 90h; void *
0x1800043ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043b1  mov     eax, ebx
0x1800043b3  jmp     short loc_1800043B7
0x1800043b5  xor     eax, eax
0x1800043b7  mov     rcx, [rsp+288h+var_38]
0x1800043bf  xor     rcx, rsp; StackCookie
0x1800043c2  call    __security_check_cookie
0x1800043c7  add     rsp, 260h
0x1800043ce  pop     r14
0x1800043d0  pop     rdi
0x1800043d1  pop     rsi
0x1800043d2  pop     rbp
0x1800043d3  pop     rbx
0x1800043d4  retn
```
