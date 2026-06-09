# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180004fbc`
- end: `0x180005101`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004bb0`
- `0x180014454`

## callees

- `0x180004fbc`
- `0x180006974`
- `0x180007144`
- `0x180007824`
- `0x180007850`
- `0x1800358a0`

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
0x180004fbc  mov     [rsp+arg_8], rbx
0x180004fc1  mov     [rsp+arg_18], rbp
0x180004fc6  push    rsi
0x180004fc7  push    rdi
0x180004fc8  push    r14
0x180004fca  sub     rsp, 260h
0x180004fd1  mov     rax, cs:__security_cookie
0x180004fd8  xor     rax, rsp
0x180004fdb  mov     [rsp+278h+var_28], rax
0x180004fe3  mov     rdi, r8
0x180004fe6  mov     rbp, rcx
0x180004fe9  mov     r8, rdx
0x180004fec  test    dil, 3
0x180004ff0  jnz     loc_1800050FB
0x180004ff6  shr     rdi, 2
0x180004ffa  lea     rax, [rsp+278h+var_238]
0x180004fff  xor     r14d, r14d
0x180005002  mov     ecx, 7FFFFFFEh
0x180005007  mov     edx, 104h
0x18000500c  lea     esi, [r14+1]
0x180005010  test    rcx, rcx
0x180005013  jz      short loc_180005033
0x180005015  movzx   r9d, word ptr [r8]
0x180005019  test    r9w, r9w
0x18000501d  jz      short loc_180005033
0x18000501f  mov     [rax], r9w
0x180005023  add     r8, 2
0x180005027  add     rax, 2
0x18000502b  sub     rcx, rsi
0x18000502e  sub     rdx, rsi; unsigned __int64
0x180005031  jnz     short loc_180005010
0x180005033  test    rdx, rdx
0x180005036  lea     rcx, [rax-2]
0x18000503a  lea     r8, aP0; "_p0"
0x180005041  cmovnz  rcx, rax
0x180005045  mov     [rcx], r14w
0x180005049  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000504e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005053  mov     edx, edi
0x180005055  lea     r9, [rsp+278h+var_238]
0x18000505a  and     edx, 7FFFFFFFh
0x180005060  mov     r8d, esi
0x180005063  mov     rcx, rbp
0x180005066  cmova   r8d, edx
0x18000506a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000506f  mov     ebx, eax
0x180005071  test    eax, eax
0x180005073  jns     short loc_180005093
0x180005075  mov     edx, 8Bh; void *
0x18000507a  mov     rcx, [rsp+278h]; this
0x180005082  lea     r8, aWil; "wil"
0x180005089  mov     r9d, eax; char *
0x18000508c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005091  jmp     short loc_1800050D0
0x180005093  lea     r8, asc_18003C0A8; "h"
0x18000509a  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000509f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800050a4  shr     rdi, 1Fh
0x1800050a8  lea     rcx, [rbp+8]
0x1800050ac  test    edi, edi
0x1800050ae  lea     r9, [rsp+278h+var_238]
0x1800050b3  mov     edx, edi
0x1800050b5  cmovnz  esi, edi
0x1800050b8  mov     r8d, esi
0x1800050bb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800050c0  mov     ebx, eax
0x1800050c2  test    eax, eax
0x1800050c4  jns     short loc_1800050CD
0x1800050c6  mov     edx, 90h
0x1800050cb  jmp     short loc_18000507A
0x1800050cd  mov     ebx, r14d
0x1800050d0  mov     eax, ebx
0x1800050d2  mov     rcx, [rsp+278h+var_28]
0x1800050da  xor     rcx, rsp; StackCookie
0x1800050dd  call    __security_check_cookie
0x1800050e2  lea     r11, [rsp+278h+var_18]
0x1800050ea  mov     rbx, [r11+28h]
0x1800050ee  mov     rbp, [r11+38h]
0x1800050f2  mov     rsp, r11
0x1800050f5  pop     r14
0x1800050f7  pop     rdi
0x1800050f8  pop     rsi
0x1800050f9  retn
0x1800050fb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
