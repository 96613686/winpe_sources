# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180003f78`
- end: `0x1800040b6`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800037f4`
- `0x180003ba0`

## callees

- `0x180003f78`
- `0x180006ca8`
- `0x18000710c`
- `0x180007e00`
- `0x180007e84`
- `0x180014e00`

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
0x180003f78  mov     [rsp+arg_8], rbx
0x180003f7d  mov     [rsp+arg_18], rbp
0x180003f82  push    rsi
0x180003f83  push    rdi
0x180003f84  push    r14
0x180003f86  sub     rsp, 260h
0x180003f8d  mov     rax, cs:__security_cookie
0x180003f94  xor     rax, rsp
0x180003f97  mov     [rsp+278h+var_28], rax
0x180003f9f  mov     rdi, r8
0x180003fa2  mov     rbp, rcx
0x180003fa5  mov     r8, rdx
0x180003fa8  test    dil, 3
0x180003fac  jnz     loc_1800040B0
0x180003fb2  shr     rdi, 2
0x180003fb6  lea     rax, [rsp+278h+var_238]
0x180003fbb  xor     r14d, r14d
0x180003fbe  mov     ecx, 7FFFFFFEh
0x180003fc3  mov     edx, 104h
0x180003fc8  lea     esi, [r14+1]
0x180003fcc  test    rcx, rcx
0x180003fcf  jz      short loc_180003FEF
0x180003fd1  movzx   r9d, word ptr [r8]
0x180003fd5  test    r9w, r9w
0x180003fd9  jz      short loc_180003FEF
0x180003fdb  mov     [rax], r9w
0x180003fdf  add     r8, 2
0x180003fe3  add     rax, 2
0x180003fe7  sub     rcx, rsi
0x180003fea  sub     rdx, rsi; unsigned __int64
0x180003fed  jnz     short loc_180003FCC
0x180003fef  test    rdx, rdx
0x180003ff2  lea     rcx, [rax-2]
0x180003ff6  lea     r8, aP0; "_p0"
0x180003ffd  cmovnz  rcx, rax
0x180004001  mov     [rcx], r14w
0x180004005  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000400a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000400f  mov     edx, edi
0x180004011  lea     r9, [rsp+278h+var_238]
0x180004016  and     edx, 7FFFFFFFh
0x18000401c  mov     r8d, esi
0x18000401f  mov     rcx, rbp
0x180004022  cmova   r8d, edx
0x180004026  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000402b  mov     ebx, eax
0x18000402d  test    eax, eax
0x18000402f  jns     short loc_180004048
0x180004031  mov     edx, 8Bh; void *
0x180004036  mov     rcx, [rsp+278h]; this
0x18000403e  mov     r9d, eax; char *
0x180004041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004046  jmp     short loc_180004085
0x180004048  lea     r8, asc_1800191F0; "h"
0x18000404f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180004054  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004059  shr     rdi, 1Fh
0x18000405d  lea     rcx, [rbp+8]
0x180004061  test    edi, edi
0x180004063  lea     r9, [rsp+278h+var_238]
0x180004068  mov     edx, edi
0x18000406a  cmovnz  esi, edi
0x18000406d  mov     r8d, esi
0x180004070  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004075  mov     ebx, eax
0x180004077  test    eax, eax
0x180004079  jns     short loc_180004082
0x18000407b  mov     edx, 90h
0x180004080  jmp     short loc_180004036
0x180004082  mov     ebx, r14d
0x180004085  mov     eax, ebx
0x180004087  mov     rcx, [rsp+278h+var_28]
0x18000408f  xor     rcx, rsp; StackCookie
0x180004092  call    __security_check_cookie
0x180004097  lea     r11, [rsp+278h+var_18]
0x18000409f  mov     rbx, [r11+28h]
0x1800040a3  mov     rbp, [r11+38h]
0x1800040a7  mov     rsp, r11
0x1800040aa  pop     r14
0x1800040ac  pop     rdi
0x1800040ad  pop     rsi
0x1800040ae  retn
0x1800040b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
