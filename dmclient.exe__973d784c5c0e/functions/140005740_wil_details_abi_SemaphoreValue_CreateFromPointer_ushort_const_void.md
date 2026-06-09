# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x140005740`
- end: `0x140005885`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004ce4`
- `0x140015fb4`

## callees

- `0x140005740`
- `0x14000b084`
- `0x14000b854`
- `0x14000bfc4`
- `0x14000c340`
- `0x140019610`

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
0x140005740  mov     [rsp+arg_8], rbx
0x140005745  mov     [rsp+arg_18], rbp
0x14000574a  push    rsi
0x14000574b  push    rdi
0x14000574c  push    r14
0x14000574e  sub     rsp, 260h
0x140005755  mov     rax, cs:__security_cookie
0x14000575c  xor     rax, rsp
0x14000575f  mov     [rsp+278h+var_28], rax
0x140005767  mov     rdi, r8
0x14000576a  mov     rbp, rcx
0x14000576d  mov     r8, rdx
0x140005770  test    dil, 3
0x140005774  jnz     loc_14000587F
0x14000577a  shr     rdi, 2
0x14000577e  lea     rax, [rsp+278h+var_238]
0x140005783  xor     r14d, r14d
0x140005786  mov     ecx, 7FFFFFFEh
0x14000578b  mov     edx, 104h
0x140005790  lea     esi, [r14+1]
0x140005794  test    rcx, rcx
0x140005797  jz      short loc_1400057B7
0x140005799  movzx   r9d, word ptr [r8]
0x14000579d  test    r9w, r9w
0x1400057a1  jz      short loc_1400057B7
0x1400057a3  mov     [rax], r9w
0x1400057a7  add     r8, 2
0x1400057ab  add     rax, 2
0x1400057af  sub     rcx, rsi
0x1400057b2  sub     rdx, rsi; unsigned __int64
0x1400057b5  jnz     short loc_140005794
0x1400057b7  test    rdx, rdx
0x1400057ba  lea     rcx, [rax-2]
0x1400057be  lea     r8, aP0; "_p0"
0x1400057c5  cmovnz  rcx, rax
0x1400057c9  mov     [rcx], r14w
0x1400057cd  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1400057d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400057d7  mov     edx, edi
0x1400057d9  lea     r9, [rsp+278h+var_238]
0x1400057de  and     edx, 7FFFFFFFh
0x1400057e4  mov     r8d, esi
0x1400057e7  mov     rcx, rbp
0x1400057ea  cmova   r8d, edx
0x1400057ee  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400057f3  mov     ebx, eax
0x1400057f5  test    eax, eax
0x1400057f7  jns     short loc_140005817
0x1400057f9  mov     edx, 8Bh; void *
0x1400057fe  mov     rcx, [rsp+278h]; this
0x140005806  lea     r8, aWil; "wil"
0x14000580d  mov     r9d, eax; char *
0x140005810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005815  jmp     short loc_140005854
0x140005817  lea     r8, asc_14001D850; "h"
0x14000581e  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140005823  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005828  shr     rdi, 1Fh
0x14000582c  lea     rcx, [rbp+8]
0x140005830  test    edi, edi
0x140005832  lea     r9, [rsp+278h+var_238]
0x140005837  mov     edx, edi
0x140005839  cmovnz  esi, edi
0x14000583c  mov     r8d, esi
0x14000583f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005844  mov     ebx, eax
0x140005846  test    eax, eax
0x140005848  jns     short loc_140005851
0x14000584a  mov     edx, 90h
0x14000584f  jmp     short loc_1400057FE
0x140005851  mov     ebx, r14d
0x140005854  mov     eax, ebx
0x140005856  mov     rcx, [rsp+278h+var_28]
0x14000585e  xor     rcx, rsp; StackCookie
0x140005861  call    __security_check_cookie
0x140005866  lea     r11, [rsp+278h+var_18]
0x14000586e  mov     rbx, [r11+28h]
0x140005872  mov     rbp, [r11+38h]
0x140005876  mov     rsp, r11
0x140005879  pop     r14
0x14000587b  pop     rdi
0x14000587c  pop     rsi
0x14000587d  retn
0x14000587f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
