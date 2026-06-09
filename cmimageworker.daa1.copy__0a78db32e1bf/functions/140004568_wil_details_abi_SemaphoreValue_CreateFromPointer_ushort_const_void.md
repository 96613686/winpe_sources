# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x140004568`
- end: `0x1400046ad`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000418c`
- `0x140016494`

## callees

- `0x1400020b0`
- `0x140004568`
- `0x140006fe4`
- `0x1400088dc`
- `0x140008f64`
- `0x1400090c8`

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
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  unsigned __int16 *v11; // rcx
  LONG v12; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v14; // rdx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  int v19; // [rsp+20h] [rbp-258h]
  unsigned __int16 v20[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  v6 = a3 >> 2;
  v7 = v20;
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
  StringCchCatW(v20, v9, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6 & 0x7FFFFFFF, v12, v20);
  v15 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    StringCchCatW(v20, v14, L"h");
    v17 = v6 >> 31;
    if ( (_DWORD)v17 )
      v10 = v17;
    semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 1, v17, v10, v20);
    v15 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      return 0;
    v16 = 144;
  }
  else
  {
    v16 = 139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"wil",
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    v19);
  return v15;
}

```

## disassembly

```asm
0x140004568  mov     [rsp+arg_8], rbx
0x14000456d  mov     [rsp+arg_18], rbp
0x140004572  push    rsi
0x140004573  push    rdi
0x140004574  push    r14
0x140004576  sub     rsp, 260h
0x14000457d  mov     rax, cs:__security_cookie
0x140004584  xor     rax, rsp
0x140004587  mov     [rsp+278h+var_28], rax
0x14000458f  mov     rdi, r8
0x140004592  mov     rbp, rcx
0x140004595  mov     r8, rdx
0x140004598  test    dil, 3
0x14000459c  jnz     loc_1400046A7
0x1400045a2  shr     rdi, 2
0x1400045a6  lea     rax, [rsp+278h+var_238]
0x1400045ab  xor     r14d, r14d
0x1400045ae  mov     ecx, 7FFFFFFEh
0x1400045b3  mov     edx, 104h
0x1400045b8  lea     esi, [r14+1]
0x1400045bc  test    rcx, rcx
0x1400045bf  jz      short loc_1400045DF
0x1400045c1  movzx   r9d, word ptr [r8]
0x1400045c5  test    r9w, r9w
0x1400045c9  jz      short loc_1400045DF
0x1400045cb  mov     [rax], r9w
0x1400045cf  add     r8, 2
0x1400045d3  add     rax, 2
0x1400045d7  sub     rcx, rsi
0x1400045da  sub     rdx, rsi; unsigned __int64
0x1400045dd  jnz     short loc_1400045BC
0x1400045df  test    rdx, rdx
0x1400045e2  lea     rcx, [rax-2]
0x1400045e6  lea     r8, aP0; "_p0"
0x1400045ed  cmovnz  rcx, rax
0x1400045f1  mov     [rcx], r14w
0x1400045f5  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1400045fa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400045ff  mov     edx, edi
0x140004601  lea     r9, [rsp+278h+var_238]
0x140004606  and     edx, 7FFFFFFFh
0x14000460c  mov     r8d, esi
0x14000460f  mov     rcx, rbp
0x140004612  cmova   r8d, edx
0x140004616  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000461b  mov     ebx, eax
0x14000461d  test    eax, eax
0x14000461f  jns     short loc_14000463F
0x140004621  mov     edx, 8Bh; void *
0x140004626  mov     rcx, [rsp+278h]; this
0x14000462e  lea     r8, aWil; "wil"
0x140004635  mov     r9d, eax; char *
0x140004638  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000463d  jmp     short loc_14000467C
0x14000463f  lea     r8, asc_1400368A0; "h"
0x140004646  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000464b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004650  shr     rdi, 1Fh
0x140004654  lea     rcx, [rbp+8]
0x140004658  test    edi, edi
0x14000465a  lea     r9, [rsp+278h+var_238]
0x14000465f  mov     edx, edi
0x140004661  cmovnz  esi, edi
0x140004664  mov     r8d, esi
0x140004667  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000466c  mov     ebx, eax
0x14000466e  test    eax, eax
0x140004670  jns     short loc_140004679
0x140004672  mov     edx, 90h
0x140004677  jmp     short loc_140004626
0x140004679  mov     ebx, r14d
0x14000467c  mov     eax, ebx
0x14000467e  mov     rcx, [rsp+278h+var_28]
0x140004686  xor     rcx, rsp; StackCookie
0x140004689  call    __security_check_cookie
0x14000468e  lea     r11, [rsp+278h+var_18]
0x140004696  mov     rbx, [r11+28h]
0x14000469a  mov     rbp, [r11+38h]
0x14000469e  mov     rsp, r11
0x1400046a1  pop     r14
0x1400046a3  pop     rdi
0x1400046a4  pop     rsi
0x1400046a5  retn
0x1400046a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
