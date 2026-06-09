# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000b1fc`
- end: `0x14000b310`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bee0`

## callees

- `0x14000b1fc`
- `0x14000c208`
- `0x14000c22c`
- `0x14000c2a8`
- `0x14000c9c4`
- `0x14000c9f0`
- `0x1400161d0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
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
0x14000b1fc  mov     [rsp+arg_10], rbx
0x14000b201  push    rbp
0x14000b202  push    rsi
0x14000b203  push    rdi
0x14000b204  sub     rsp, 260h
0x14000b20b  mov     rax, cs:__security_cookie
0x14000b212  xor     rax, rsp
0x14000b215  mov     [rsp+278h+var_28], rax
0x14000b21d  mov     rax, 0C000000000000000h
0x14000b227  mov     rbx, r9
0x14000b22a  mov     rbp, rcx
0x14000b22d  test    rax, r9
0x14000b230  jnz     loc_14000B30A
0x14000b236  mov     r8, rdx; unsigned __int16 *
0x14000b239  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b23e  mov     edx, 104h; unsigned __int64
0x14000b243  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b248  lea     r8, aP0; "_p0"
0x14000b24f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b254  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b259  mov     edx, ebx
0x14000b25b  lea     r9, [rsp+278h+var_238]
0x14000b260  and     edx, 7FFFFFFFh
0x14000b266  mov     esi, 1
0x14000b26b  mov     r8d, esi
0x14000b26e  mov     rcx, rbp
0x14000b271  cmova   r8d, edx
0x14000b275  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000b27a  mov     edi, eax
0x14000b27c  test    eax, eax
0x14000b27e  jns     short loc_14000B299
0x14000b280  mov     rcx, [rsp+278h]; this
0x14000b288  mov     r9d, eax; char *
0x14000b28b  mov     edx, 8Bh; void *
0x14000b290  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b295  mov     eax, edi
0x14000b297  jmp     short loc_14000B2E7
0x14000b299  lea     r8, asc_14001A098; "h"
0x14000b2a0  shr     rbx, 1Fh
0x14000b2a4  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b2a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b2ae  test    ebx, ebx
0x14000b2b0  lea     rcx, [rbp+8]
0x14000b2b4  lea     r9, [rsp+278h+var_238]
0x14000b2b9  mov     edx, ebx
0x14000b2bb  cmovnz  esi, ebx
0x14000b2be  mov     r8d, esi
0x14000b2c1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000b2c6  mov     ebx, eax
0x14000b2c8  test    eax, eax
0x14000b2ca  jns     short loc_14000B2E5
0x14000b2cc  mov     rcx, [rsp+278h]; this
0x14000b2d4  mov     r9d, eax; char *
0x14000b2d7  mov     edx, 90h; void *
0x14000b2dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b2e1  mov     eax, ebx
0x14000b2e3  jmp     short loc_14000B2E7
0x14000b2e5  xor     eax, eax
0x14000b2e7  mov     rcx, [rsp+278h+var_28]
0x14000b2ef  xor     rcx, rsp; StackCookie
0x14000b2f2  call    __security_check_cookie
0x14000b2f7  mov     rbx, [rsp+278h+arg_10]
0x14000b2ff  add     rsp, 260h
0x14000b306  pop     rdi
0x14000b307  pop     rsi
0x14000b308  pop     rbp
0x14000b309  retn
0x14000b30a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
