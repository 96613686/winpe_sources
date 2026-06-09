# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000527c`
- end: `0x18000539d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e60`
- `0x180006fd0`

## callees

- `0x180002620`
- `0x18000527c`
- `0x180008498`
- `0x180008af8`
- `0x180008c48`
- `0x180009c4c`
- `0x180009df4`

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
0x18000527c  push    rbx
0x18000527e  push    rbp
0x18000527f  push    rsi
0x180005280  push    rdi
0x180005281  push    r14
0x180005283  sub     rsp, 260h
0x18000528a  mov     rax, cs:__security_cookie
0x180005291  xor     rax, rsp
0x180005294  mov     [rsp+288h+var_38], rax
0x18000529c  mov     rax, 0C000000000000000h
0x1800052a6  mov     rbx, r9
0x1800052a9  mov     rbp, rcx
0x1800052ac  test    rax, r9
0x1800052af  jz      short loc_1800052B7
0x1800052b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800052b7  mov     r8, rdx; unsigned __int16 *
0x1800052ba  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800052bf  mov     r14d, 104h
0x1800052c5  mov     edx, r14d; unsigned __int64
0x1800052c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800052cd  lea     r8, aP0; "_p0"
0x1800052d4  mov     edx, r14d; unsigned __int64
0x1800052d7  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800052dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800052e1  mov     edx, ebx
0x1800052e3  lea     r9, [rsp+288h+var_248]
0x1800052e8  and     edx, 7FFFFFFFh
0x1800052ee  mov     esi, 1
0x1800052f3  mov     r8d, esi
0x1800052f6  mov     rcx, rbp
0x1800052f9  cmova   r8d, edx
0x1800052fd  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005302  mov     edi, eax
0x180005304  test    eax, eax
0x180005306  jns     short loc_180005327
0x180005308  mov     rcx, [rsp+288h]; this
0x180005310  lea     r8, aWil; "wil"
0x180005317  mov     r9d, eax; char *
0x18000531a  lea     edx, [r14-79h]; void *
0x18000531e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005323  mov     eax, edi
0x180005325  jmp     short loc_18000537F
0x180005327  lea     r8, asc_180015560; "h"
0x18000532e  shr     rbx, 1Fh
0x180005332  mov     rdx, r14; unsigned __int64
0x180005335  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000533a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000533f  test    ebx, ebx
0x180005341  lea     rcx, [rbp+8]
0x180005345  lea     r9, [rsp+288h+var_248]
0x18000534a  mov     edx, ebx
0x18000534c  cmovnz  esi, ebx
0x18000534f  mov     r8d, esi
0x180005352  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005357  mov     ebx, eax
0x180005359  test    eax, eax
0x18000535b  jns     short loc_18000537D
0x18000535d  mov     rcx, [rsp+288h]; this
0x180005365  lea     r8, aWil; "wil"
0x18000536c  mov     r9d, eax; char *
0x18000536f  mov     edx, 90h; void *
0x180005374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005379  mov     eax, ebx
0x18000537b  jmp     short loc_18000537F
0x18000537d  xor     eax, eax
0x18000537f  mov     rcx, [rsp+288h+var_38]
0x180005387  xor     rcx, rsp; StackCookie
0x18000538a  call    __security_check_cookie
0x18000538f  add     rsp, 260h
0x180005396  pop     r14
0x180005398  pop     rdi
0x180005399  pop     rsi
0x18000539a  pop     rbp
0x18000539b  pop     rbx
0x18000539c  retn
```
