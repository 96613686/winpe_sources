# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180004010`
- end: `0x180004123`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005754`
- `0x1800058b0`

## callees

- `0x180004010`
- `0x18000685c`
- `0x180006f5c`
- `0x180006fdc`
- `0x180007b88`
- `0x180007d38`
- `0x180023ca0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  wchar_t v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x180004010  push    rbx
0x180004012  push    rbp
0x180004013  push    rsi
0x180004014  push    rdi
0x180004015  push    r14
0x180004017  sub     rsp, 260h
0x18000401e  mov     rax, cs:__security_cookie
0x180004025  xor     rax, rsp
0x180004028  mov     [rsp+288h+var_38], rax
0x180004030  mov     rax, 0C000000000000000h
0x18000403a  mov     rbx, r9
0x18000403d  mov     rbp, rcx
0x180004040  test    rax, r9
0x180004043  jz      short loc_18000404B
0x180004045  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000404b  mov     r8, rdx; wchar_t *
0x18000404e  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x180004053  mov     r14d, 104h
0x180004059  mov     edx, r14d; unsigned __int64
0x18000405c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004061  lea     r8, aP0; "_p0"
0x180004068  mov     edx, r14d; unsigned __int64
0x18000406b  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x180004070  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004075  mov     edx, ebx
0x180004077  lea     r9, [rsp+288h+var_248]
0x18000407c  and     edx, 7FFFFFFFh
0x180004082  mov     esi, 1
0x180004087  mov     r8d, esi
0x18000408a  mov     rcx, rbp
0x18000408d  cmova   r8d, edx
0x180004091  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004096  mov     edi, eax
0x180004098  test    eax, eax
0x18000409a  jns     short loc_1800040B4
0x18000409c  mov     rcx, [rsp+288h]; this
0x1800040a4  lea     edx, [r14-79h]; void *
0x1800040a8  mov     r9d, eax; char *
0x1800040ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040b0  mov     eax, edi
0x1800040b2  jmp     short loc_180004105
0x1800040b4  lea     r8, asc_180031690; "h"
0x1800040bb  shr     rbx, 1Fh
0x1800040bf  mov     rdx, r14; unsigned __int64
0x1800040c2  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x1800040c7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800040cc  test    ebx, ebx
0x1800040ce  lea     rcx, [rbp+8]
0x1800040d2  lea     r9, [rsp+288h+var_248]
0x1800040d7  mov     edx, ebx
0x1800040d9  cmovnz  esi, ebx
0x1800040dc  mov     r8d, esi
0x1800040df  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800040e4  mov     ebx, eax
0x1800040e6  test    eax, eax
0x1800040e8  jns     short loc_180004103
0x1800040ea  mov     rcx, [rsp+288h]; this
0x1800040f2  mov     r9d, eax; char *
0x1800040f5  mov     edx, 90h; void *
0x1800040fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ff  mov     eax, ebx
0x180004101  jmp     short loc_180004105
0x180004103  xor     eax, eax
0x180004105  mov     rcx, [rsp+288h+var_38]
0x18000410d  xor     rcx, rsp; StackCookie
0x180004110  call    __security_check_cookie
0x180004115  add     rsp, 260h
0x18000411c  pop     r14
0x18000411e  pop     rdi
0x18000411f  pop     rsi
0x180004120  pop     rbp
0x180004121  pop     rbx
0x180004122  retn
```
