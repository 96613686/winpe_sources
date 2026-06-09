# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18003292c`
- end: `0x180032a3f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033f2c`
- `0x180034080`

## callees

- `0x180006364`
- `0x18002e61c`
- `0x18003292c`
- `0x180034ff4`
- `0x1800361f8`
- `0x180036364`
- `0x180037620`

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
0x18003292c  push    rbx
0x18003292e  push    rbp
0x18003292f  push    rsi
0x180032930  push    rdi
0x180032931  push    r14
0x180032933  sub     rsp, 260h
0x18003293a  mov     rax, cs:__security_cookie
0x180032941  xor     rax, rsp
0x180032944  mov     [rsp+288h+var_38], rax
0x18003294c  mov     rax, 0C000000000000000h
0x180032956  mov     rbx, r9
0x180032959  mov     rbp, rcx
0x18003295c  test    rax, r9
0x18003295f  jz      short loc_180032967
0x180032961  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180032967  mov     r8, rdx; unsigned __int16 *
0x18003296a  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18003296f  mov     r14d, 104h
0x180032975  mov     edx, r14d; unsigned __int64
0x180032978  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003297d  lea     r8, aP0; "_p0"
0x180032984  mov     edx, r14d; unsigned __int64
0x180032987  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18003298c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032991  mov     edx, ebx
0x180032993  lea     r9, [rsp+288h+var_248]
0x180032998  and     edx, 7FFFFFFFh
0x18003299e  mov     esi, 1
0x1800329a3  mov     r8d, esi
0x1800329a6  mov     rcx, rbp
0x1800329a9  cmova   r8d, edx
0x1800329ad  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800329b2  mov     edi, eax
0x1800329b4  test    eax, eax
0x1800329b6  jns     short loc_1800329D0
0x1800329b8  mov     rcx, [rsp+288h]; this
0x1800329c0  lea     edx, [r14-79h]; void *
0x1800329c4  mov     r9d, eax; char *
0x1800329c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800329cc  mov     eax, edi
0x1800329ce  jmp     short loc_180032A21
0x1800329d0  lea     r8, asc_18003F648; "h"
0x1800329d7  shr     rbx, 1Fh
0x1800329db  mov     rdx, r14; unsigned __int64
0x1800329de  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800329e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800329e8  test    ebx, ebx
0x1800329ea  lea     rcx, [rbp+8]
0x1800329ee  lea     r9, [rsp+288h+var_248]
0x1800329f3  mov     edx, ebx
0x1800329f5  cmovnz  esi, ebx
0x1800329f8  mov     r8d, esi
0x1800329fb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180032a00  mov     ebx, eax
0x180032a02  test    eax, eax
0x180032a04  jns     short loc_180032A1F
0x180032a06  mov     rcx, [rsp+288h]; this
0x180032a0e  mov     r9d, eax; char *
0x180032a11  mov     edx, 90h; void *
0x180032a16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a1b  mov     eax, ebx
0x180032a1d  jmp     short loc_180032A21
0x180032a1f  xor     eax, eax
0x180032a21  mov     rcx, [rsp+288h+var_38]
0x180032a29  xor     rcx, rsp; StackCookie
0x180032a2c  call    __security_check_cookie
0x180032a31  add     rsp, 260h
0x180032a38  pop     r14
0x180032a3a  pop     rdi
0x180032a3b  pop     rsi
0x180032a3c  pop     rbp
0x180032a3d  pop     rbx
0x180032a3e  retn
```
