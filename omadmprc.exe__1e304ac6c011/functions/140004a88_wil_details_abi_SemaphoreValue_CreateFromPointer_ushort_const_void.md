# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x140004a88`
- end: `0x140004bcd`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400042a4`
- `0x140004680`

## callees

- `0x140004a88`
- `0x140008504`
- `0x140008df0`
- `0x140009e10`
- `0x14000a120`
- `0x140015690`

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
0x140004a88  mov     [rsp+arg_8], rbx
0x140004a8d  mov     [rsp+arg_18], rbp
0x140004a92  push    rsi
0x140004a93  push    rdi
0x140004a94  push    r14
0x140004a96  sub     rsp, 260h
0x140004a9d  mov     rax, cs:__security_cookie
0x140004aa4  xor     rax, rsp
0x140004aa7  mov     [rsp+278h+var_28], rax
0x140004aaf  mov     rdi, r8
0x140004ab2  mov     rbp, rcx
0x140004ab5  mov     r8, rdx
0x140004ab8  test    dil, 3
0x140004abc  jnz     loc_140004BC7
0x140004ac2  shr     rdi, 2
0x140004ac6  lea     rax, [rsp+278h+var_238]
0x140004acb  xor     r14d, r14d
0x140004ace  mov     ecx, 7FFFFFFEh
0x140004ad3  mov     edx, 104h
0x140004ad8  lea     esi, [r14+1]
0x140004adc  test    rcx, rcx
0x140004adf  jz      short loc_140004AFF
0x140004ae1  movzx   r9d, word ptr [r8]
0x140004ae5  test    r9w, r9w
0x140004ae9  jz      short loc_140004AFF
0x140004aeb  mov     [rax], r9w
0x140004aef  add     r8, 2
0x140004af3  add     rax, 2
0x140004af7  sub     rcx, rsi
0x140004afa  sub     rdx, rsi; unsigned __int64
0x140004afd  jnz     short loc_140004ADC
0x140004aff  test    rdx, rdx
0x140004b02  lea     rcx, [rax-2]
0x140004b06  lea     r8, aP0; "_p0"
0x140004b0d  cmovnz  rcx, rax
0x140004b11  mov     [rcx], r14w
0x140004b15  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004b1a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004b1f  mov     edx, edi
0x140004b21  lea     r9, [rsp+278h+var_238]
0x140004b26  and     edx, 7FFFFFFFh
0x140004b2c  mov     r8d, esi
0x140004b2f  mov     rcx, rbp
0x140004b32  cmova   r8d, edx
0x140004b36  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004b3b  mov     ebx, eax
0x140004b3d  test    eax, eax
0x140004b3f  jns     short loc_140004B5F
0x140004b41  mov     edx, 8Bh; void *
0x140004b46  mov     rcx, [rsp+278h]; this
0x140004b4e  lea     r8, aWil; "wil"
0x140004b55  mov     r9d, eax; char *
0x140004b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004b5d  jmp     short loc_140004B9C
0x140004b5f  lea     r8, asc_14001A420; "h"
0x140004b66  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004b6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004b70  shr     rdi, 1Fh
0x140004b74  lea     rcx, [rbp+8]
0x140004b78  test    edi, edi
0x140004b7a  lea     r9, [rsp+278h+var_238]
0x140004b7f  mov     edx, edi
0x140004b81  cmovnz  esi, edi
0x140004b84  mov     r8d, esi
0x140004b87  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004b8c  mov     ebx, eax
0x140004b8e  test    eax, eax
0x140004b90  jns     short loc_140004B99
0x140004b92  mov     edx, 90h
0x140004b97  jmp     short loc_140004B46
0x140004b99  mov     ebx, r14d
0x140004b9c  mov     eax, ebx
0x140004b9e  mov     rcx, [rsp+278h+var_28]
0x140004ba6  xor     rcx, rsp; StackCookie
0x140004ba9  call    __security_check_cookie
0x140004bae  lea     r11, [rsp+278h+var_18]
0x140004bb6  mov     rbx, [r11+28h]
0x140004bba  mov     rbp, [r11+38h]
0x140004bbe  mov     rsp, r11
0x140004bc1  pop     r14
0x140004bc3  pop     rdi
0x140004bc4  pop     rsi
0x140004bc5  retn
0x140004bc7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
