# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800050d0`
- end: `0x1800051e0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e0c`
- `0x180009f30`

## callees

- `0x180001bb0`
- `0x1800050d0`
- `0x18000b18c`
- `0x18000b91c`
- `0x18000b978`
- `0x18000cf10`
- `0x18000d898`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            v19);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v18);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x1800050d0  mov     [rsp+arg_10], rbx
0x1800050d5  push    rbp
0x1800050d6  push    rsi
0x1800050d7  push    rdi
0x1800050d8  sub     rsp, 260h
0x1800050df  mov     rax, cs:__security_cookie
0x1800050e6  xor     rax, rsp
0x1800050e9  mov     [rsp+278h+var_28], rax
0x1800050f1  mov     rax, 0C000000000000000h
0x1800050fb  mov     rbx, r9
0x1800050fe  mov     rbp, rcx
0x180005101  test    rax, r9
0x180005104  jz      short loc_18000510C
0x180005106  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000510c  mov     r8, rdx; unsigned __int16 *
0x18000510f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180005114  mov     edx, 104h; unsigned __int64
0x180005119  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000511e  lea     r8, aP0; "_p0"
0x180005125  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000512a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000512f  mov     edx, ebx
0x180005131  lea     r9, [rsp+278h+var_238]
0x180005136  and     edx, 7FFFFFFFh
0x18000513c  mov     esi, 1
0x180005141  mov     r8d, esi
0x180005144  mov     rcx, rbp
0x180005147  cmova   r8d, edx
0x18000514b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005150  mov     edi, eax
0x180005152  test    eax, eax
0x180005154  jns     short loc_18000516F
0x180005156  mov     rcx, [rsp+278h]; this
0x18000515e  mov     r9d, eax; char *
0x180005161  mov     edx, 8Bh; void *
0x180005166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000516b  mov     eax, edi
0x18000516d  jmp     short loc_1800051BD
0x18000516f  lea     r8, asc_1800315B0; "h"
0x180005176  shr     rbx, 1Fh
0x18000517a  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000517f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005184  test    ebx, ebx
0x180005186  lea     rcx, [rbp+8]
0x18000518a  lea     r9, [rsp+278h+var_238]
0x18000518f  mov     edx, ebx
0x180005191  cmovnz  esi, ebx
0x180005194  mov     r8d, esi
0x180005197  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000519c  mov     ebx, eax
0x18000519e  test    eax, eax
0x1800051a0  jns     short loc_1800051BB
0x1800051a2  mov     rcx, [rsp+278h]; this
0x1800051aa  mov     r9d, eax; char *
0x1800051ad  mov     edx, 90h; void *
0x1800051b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051b7  mov     eax, ebx
0x1800051b9  jmp     short loc_1800051BD
0x1800051bb  xor     eax, eax
0x1800051bd  mov     rcx, [rsp+278h+var_28]
0x1800051c5  xor     rcx, rsp; StackCookie
0x1800051c8  call    __security_check_cookie
0x1800051cd  mov     rbx, [rsp+278h+arg_10]
0x1800051d5  add     rsp, 260h
0x1800051dc  pop     rdi
0x1800051dd  pop     rsi
0x1800051de  pop     rbp
0x1800051df  retn
```
