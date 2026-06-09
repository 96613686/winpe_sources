# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18000b528`
- end: `0x18000b674`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `332`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a8a4`
- `0x18000ac80`

## callees

- `0x1800031b0`
- `0x18000b528`
- `0x180011b98`
- `0x180012ef0`
- `0x180013ce8`
- `0x180013e74`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        void **this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // esi
  unsigned __int16 *v11; // rcx
  LONG v12; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  int v18; // [rsp+20h] [rbp-268h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  v6 = a3 >> 2;
  v7 = v19;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(v19, 0x104u, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6 & 0x7FFFFFFF, v12, v19);
  v14 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    StringCchCatW(v19, 0x104u, L"h");
    v16 = v6 >> 31;
    if ( (_DWORD)v16 )
      v10 = v16;
    semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 1, v16, v10, v19);
    v14 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      return 0;
    v15 = 144;
  }
  else
  {
    v15 = 139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"wil",
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    v18);
  return v14;
}

```

## disassembly

```asm
0x18000b528  mov     [rsp+arg_8], rbx
0x18000b52d  push    rbp
0x18000b52e  push    rsi
0x18000b52f  push    rdi
0x18000b530  push    r14
0x18000b532  push    r15
0x18000b534  sub     rsp, 260h
0x18000b53b  mov     rax, cs:__security_cookie
0x18000b542  xor     rax, rsp
0x18000b545  mov     [rsp+288h+var_38], rax
0x18000b54d  mov     rdi, r8
0x18000b550  mov     rbp, rcx
0x18000b553  mov     r8, rdx
0x18000b556  test    dil, 3
0x18000b55a  jnz     loc_18000B66E
0x18000b560  shr     rdi, 2
0x18000b564  lea     rax, [rsp+288h+var_248]
0x18000b569  xor     r14d, r14d
0x18000b56c  mov     r15d, 104h
0x18000b572  mov     ecx, 7FFFFFFEh
0x18000b577  mov     edx, r15d
0x18000b57a  lea     esi, [r14+1]
0x18000b57e  test    rcx, rcx
0x18000b581  jz      short loc_18000B5A1
0x18000b583  movzx   r9d, word ptr [r8]
0x18000b587  test    r9w, r9w
0x18000b58b  jz      short loc_18000B5A1
0x18000b58d  mov     [rax], r9w
0x18000b591  add     r8, 2
0x18000b595  add     rax, 2
0x18000b599  sub     rcx, rsi
0x18000b59c  sub     rdx, rsi
0x18000b59f  jnz     short loc_18000B57E
0x18000b5a1  test    rdx, rdx
0x18000b5a4  lea     rcx, [rax-2]
0x18000b5a8  lea     r8, aP0; "_p0"
0x18000b5af  mov     rdx, r15; unsigned __int64
0x18000b5b2  cmovnz  rcx, rax
0x18000b5b6  mov     [rcx], r14w
0x18000b5ba  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000b5bf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b5c4  mov     edx, edi
0x18000b5c6  lea     r9, [rsp+288h+var_248]
0x18000b5cb  and     edx, 7FFFFFFFh
0x18000b5d1  mov     r8d, esi
0x18000b5d4  mov     rcx, rbp
0x18000b5d7  cmova   r8d, edx
0x18000b5db  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000b5e0  mov     ebx, eax
0x18000b5e2  test    eax, eax
0x18000b5e4  jns     short loc_18000B604
0x18000b5e6  mov     edx, 8Bh; void *
0x18000b5eb  mov     rcx, [rsp+288h]; this
0x18000b5f3  lea     r8, aWil; "wil"
0x18000b5fa  mov     r9d, eax; char *
0x18000b5fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b602  jmp     short loc_18000B644
0x18000b604  lea     r8, asc_180028B30; "h"
0x18000b60b  mov     rdx, r15; unsigned __int64
0x18000b60e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000b613  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b618  shr     rdi, 1Fh
0x18000b61c  lea     rcx, [rbp+8]
0x18000b620  test    edi, edi
0x18000b622  lea     r9, [rsp+288h+var_248]
0x18000b627  mov     edx, edi
0x18000b629  cmovnz  esi, edi
0x18000b62c  mov     r8d, esi
0x18000b62f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000b634  mov     ebx, eax
0x18000b636  test    eax, eax
0x18000b638  jns     short loc_18000B641
0x18000b63a  mov     edx, 90h
0x18000b63f  jmp     short loc_18000B5EB
0x18000b641  mov     ebx, r14d
0x18000b644  mov     eax, ebx
0x18000b646  mov     rcx, [rsp+288h+var_38]
0x18000b64e  xor     rcx, rsp; StackCookie
0x18000b651  call    __security_check_cookie
0x18000b656  mov     rbx, [rsp+288h+arg_8]
0x18000b65e  add     rsp, 260h
0x18000b665  pop     r15
0x18000b667  pop     r14
0x18000b669  pop     rdi
0x18000b66a  pop     rsi
0x18000b66b  pop     rbp
0x18000b66c  retn
0x18000b66e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
