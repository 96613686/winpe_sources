# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x1800065d8`
- end: `0x180006716`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005c6c`
- `0x180006018`

## callees

- `0x180002ad0`
- `0x1800065d8`
- `0x18000a314`
- `0x18000af80`
- `0x18000bd9c`
- `0x18000be74`

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
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  __int64 v17; // rdx
  unsigned __int64 v18; // rdi
  int v20; // [rsp+20h] [rbp-258h]
  unsigned __int16 v21[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  v6 = a3 >> 2;
  v7 = v21;
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
  StringCchCatW(v21, v9, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6 & 0x7FFFFFFF, v12, v21);
  v16 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    StringCchCatW(v21, v14, L"h");
    v18 = v6 >> 31;
    if ( (_DWORD)v18 )
      v10 = v18;
    semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 1, v18, v10, v21);
    v16 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      return 0;
    v17 = 144;
  }
  else
  {
    v17 = 139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    v15,
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    v20);
  return v16;
}

```

## disassembly

```asm
0x1800065d8  mov     [rsp+arg_8], rbx
0x1800065dd  mov     [rsp+arg_18], rbp
0x1800065e2  push    rsi
0x1800065e3  push    rdi
0x1800065e4  push    r14
0x1800065e6  sub     rsp, 260h
0x1800065ed  mov     rax, cs:__security_cookie
0x1800065f4  xor     rax, rsp
0x1800065f7  mov     [rsp+278h+var_28], rax
0x1800065ff  mov     rdi, r8
0x180006602  mov     rbp, rcx
0x180006605  mov     r8, rdx
0x180006608  test    dil, 3
0x18000660c  jnz     loc_180006710
0x180006612  shr     rdi, 2
0x180006616  lea     rax, [rsp+278h+var_238]
0x18000661b  xor     r14d, r14d
0x18000661e  mov     ecx, 7FFFFFFEh
0x180006623  mov     edx, 104h
0x180006628  lea     esi, [r14+1]
0x18000662c  test    rcx, rcx
0x18000662f  jz      short loc_18000664F
0x180006631  movzx   r9d, word ptr [r8]
0x180006635  test    r9w, r9w
0x180006639  jz      short loc_18000664F
0x18000663b  mov     [rax], r9w
0x18000663f  add     r8, 2
0x180006643  add     rax, 2
0x180006647  sub     rcx, rsi
0x18000664a  sub     rdx, rsi; unsigned __int64
0x18000664d  jnz     short loc_18000662C
0x18000664f  test    rdx, rdx
0x180006652  lea     rcx, [rax-2]
0x180006656  lea     r8, aP0; "_p0"
0x18000665d  cmovnz  rcx, rax
0x180006661  mov     [rcx], r14w
0x180006665  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000666a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000666f  mov     edx, edi
0x180006671  lea     r9, [rsp+278h+var_238]
0x180006676  and     edx, 7FFFFFFFh
0x18000667c  mov     r8d, esi
0x18000667f  mov     rcx, rbp
0x180006682  cmova   r8d, edx
0x180006686  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000668b  mov     ebx, eax
0x18000668d  test    eax, eax
0x18000668f  jns     short loc_1800066A8
0x180006691  mov     edx, 8Bh; void *
0x180006696  mov     rcx, [rsp+278h]; this
0x18000669e  mov     r9d, eax; char *
0x1800066a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066a6  jmp     short loc_1800066E5
0x1800066a8  lea     r8, asc_180038100; "h"
0x1800066af  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800066b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800066b9  shr     rdi, 1Fh
0x1800066bd  lea     rcx, [rbp+8]
0x1800066c1  test    edi, edi
0x1800066c3  lea     r9, [rsp+278h+var_238]
0x1800066c8  mov     edx, edi
0x1800066ca  cmovnz  esi, edi
0x1800066cd  mov     r8d, esi
0x1800066d0  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800066d5  mov     ebx, eax
0x1800066d7  test    eax, eax
0x1800066d9  jns     short loc_1800066E2
0x1800066db  mov     edx, 90h
0x1800066e0  jmp     short loc_180006696
0x1800066e2  mov     ebx, r14d
0x1800066e5  mov     eax, ebx
0x1800066e7  mov     rcx, [rsp+278h+var_28]
0x1800066ef  xor     rcx, rsp; StackCookie
0x1800066f2  call    __security_check_cookie
0x1800066f7  lea     r11, [rsp+278h+var_18]
0x1800066ff  mov     rbx, [r11+28h]
0x180006703  mov     rbp, [r11+38h]
0x180006707  mov     rsp, r11
0x18000670a  pop     r14
0x18000670c  pop     rdi
0x18000670d  pop     rsi
0x18000670e  retn
0x180006710  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
