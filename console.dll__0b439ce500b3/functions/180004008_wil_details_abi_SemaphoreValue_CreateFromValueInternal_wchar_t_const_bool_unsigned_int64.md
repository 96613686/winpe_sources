# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180004008`
- end: `0x180004127`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `287`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005178`

## callees

- `0x1800015b0`
- `0x180004008`
- `0x1800058a4`
- `0x180005de0`
- `0x180005e60`
- `0x18000633c`
- `0x180006404`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  wchar_t v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x180004008  mov     [rsp+arg_10], rbx
0x18000400d  push    rbp
0x18000400e  push    rsi
0x18000400f  push    rdi
0x180004010  sub     rsp, 260h
0x180004017  mov     rax, cs:__security_cookie
0x18000401e  xor     rax, rsp
0x180004021  mov     [rsp+278h+var_28], rax
0x180004029  mov     rax, 0C000000000000000h
0x180004033  mov     rbx, r9
0x180004036  mov     rbp, rcx
0x180004039  test    rax, r9
0x18000403c  jz      short loc_180004044
0x18000403e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004044  mov     r8, rdx; wchar_t *
0x180004047  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x18000404c  mov     edx, 104h; unsigned __int64
0x180004051  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004056  lea     r8, aP0; "_p0"
0x18000405d  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180004062  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004067  mov     edx, ebx
0x180004069  lea     r9, [rsp+278h+var_238]
0x18000406e  and     edx, 7FFFFFFFh
0x180004074  mov     esi, 1
0x180004079  mov     r8d, esi
0x18000407c  mov     rcx, rbp
0x18000407f  cmova   r8d, edx
0x180004083  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004088  mov     edi, eax
0x18000408a  test    eax, eax
0x18000408c  jns     short loc_1800040AE
0x18000408e  mov     rcx, [rsp+278h]; this
0x180004096  lea     r8, aWil; "wil"
0x18000409d  mov     r9d, eax; char *
0x1800040a0  mov     edx, 8Bh; void *
0x1800040a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040aa  mov     eax, edi
0x1800040ac  jmp     short loc_180004103
0x1800040ae  lea     r8, asc_18001C720; "h"
0x1800040b5  shr     rbx, 1Fh
0x1800040b9  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x1800040be  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800040c3  test    ebx, ebx
0x1800040c5  lea     rcx, [rbp+8]
0x1800040c9  lea     r9, [rsp+278h+var_238]
0x1800040ce  mov     edx, ebx
0x1800040d0  cmovnz  esi, ebx
0x1800040d3  mov     r8d, esi
0x1800040d6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800040db  mov     ebx, eax
0x1800040dd  test    eax, eax
0x1800040df  jns     short loc_180004101
0x1800040e1  mov     rcx, [rsp+278h]; this
0x1800040e9  lea     r8, aWil; "wil"
0x1800040f0  mov     r9d, eax; char *
0x1800040f3  mov     edx, 90h; void *
0x1800040f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040fd  mov     eax, ebx
0x1800040ff  jmp     short loc_180004103
0x180004101  xor     eax, eax
0x180004103  mov     rcx, [rsp+278h+var_28]
0x18000410b  xor     rcx, rsp; StackCookie
0x18000410e  call    __security_check_cookie
0x180004113  mov     rbx, [rsp+278h+arg_10]
0x18000411b  add     rsp, 260h
0x180004122  pop     rdi
0x180004123  pop     rsi
0x180004124  pop     rbp
0x180004125  retn
```
