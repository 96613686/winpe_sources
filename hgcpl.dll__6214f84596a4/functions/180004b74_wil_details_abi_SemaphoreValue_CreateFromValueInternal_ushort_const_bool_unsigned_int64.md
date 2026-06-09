# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004b74`
- end: `0x180004c87`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005c98`
- `0x180010f04`

## callees

- `0x180004b74`
- `0x180006070`
- `0x180006338`
- `0x1800063c4`
- `0x180006954`
- `0x1800069d4`
- `0x180018a80`

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
0x180004b74  push    rbx
0x180004b76  push    rbp
0x180004b77  push    rsi
0x180004b78  push    rdi
0x180004b79  push    r14
0x180004b7b  sub     rsp, 260h
0x180004b82  mov     rax, cs:__security_cookie
0x180004b89  xor     rax, rsp
0x180004b8c  mov     [rsp+288h+var_38], rax
0x180004b94  mov     rax, 0C000000000000000h
0x180004b9e  mov     rbx, r9
0x180004ba1  mov     rbp, rcx
0x180004ba4  test    rax, r9
0x180004ba7  jz      short loc_180004BAF
0x180004ba9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004baf  mov     r8, rdx; unsigned __int16 *
0x180004bb2  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004bb7  mov     r14d, 104h
0x180004bbd  mov     edx, r14d; unsigned __int64
0x180004bc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004bc5  lea     r8, aP0; "_p0"
0x180004bcc  mov     edx, r14d; unsigned __int64
0x180004bcf  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004bd4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004bd9  mov     edx, ebx
0x180004bdb  lea     r9, [rsp+288h+var_248]
0x180004be0  and     edx, 7FFFFFFFh
0x180004be6  mov     esi, 1
0x180004beb  mov     r8d, esi
0x180004bee  mov     rcx, rbp
0x180004bf1  cmova   r8d, edx
0x180004bf5  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004bfa  mov     edi, eax
0x180004bfc  test    eax, eax
0x180004bfe  jns     short loc_180004C18
0x180004c00  mov     rcx, [rsp+288h]; this
0x180004c08  lea     edx, [r14-79h]; void *
0x180004c0c  mov     r9d, eax; char *
0x180004c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c14  mov     eax, edi
0x180004c16  jmp     short loc_180004C69
0x180004c18  lea     r8, asc_18001D968; "h"
0x180004c1f  shr     rbx, 1Fh
0x180004c23  mov     rdx, r14; unsigned __int64
0x180004c26  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004c2b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004c30  test    ebx, ebx
0x180004c32  lea     rcx, [rbp+8]
0x180004c36  lea     r9, [rsp+288h+var_248]
0x180004c3b  mov     edx, ebx
0x180004c3d  cmovnz  esi, ebx
0x180004c40  mov     r8d, esi
0x180004c43  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004c48  mov     ebx, eax
0x180004c4a  test    eax, eax
0x180004c4c  jns     short loc_180004C67
0x180004c4e  mov     rcx, [rsp+288h]; this
0x180004c56  mov     r9d, eax; char *
0x180004c59  mov     edx, 90h; void *
0x180004c5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c63  mov     eax, ebx
0x180004c65  jmp     short loc_180004C69
0x180004c67  xor     eax, eax
0x180004c69  mov     rcx, [rsp+288h+var_38]
0x180004c71  xor     rcx, rsp; StackCookie
0x180004c74  call    __security_check_cookie
0x180004c79  add     rsp, 260h
0x180004c80  pop     r14
0x180004c82  pop     rdi
0x180004c83  pop     rsi
0x180004c84  pop     rbp
0x180004c85  pop     rbx
0x180004c86  retn
```
