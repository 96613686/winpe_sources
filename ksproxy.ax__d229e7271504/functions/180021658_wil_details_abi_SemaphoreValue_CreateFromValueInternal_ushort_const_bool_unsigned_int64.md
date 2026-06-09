# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180021658`
- end: `0x180021777`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `287`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eed8`

## callees

- `0x1800081e4`
- `0x1800109d4`
- `0x18001ba6c`
- `0x18001f620`
- `0x180021658`
- `0x180025714`
- `0x180025740`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned int v8; // esi
  __int64 v9; // r8
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v11; // rdx
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = a4 & 0x7FFFFFFF;
  v8 = 1;
  v9 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v9 = (unsigned int)v7;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v7, v9, v17);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v17, v11, L"h");
    if ( (_DWORD)v14 )
      v8 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &this->m_semaphoreHigh,
            (unsigned int)v14,
            v8,
            v17);
    v16 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, (int)"wil", (const char *)(unsigned int)v15);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    return v12;
  }
}

```

## disassembly

```asm
0x180021658  mov     [rsp+arg_10], rbx
0x18002165d  push    rbp
0x18002165e  push    rsi
0x18002165f  push    rdi
0x180021660  sub     rsp, 260h
0x180021667  mov     rax, cs:__security_cookie
0x18002166e  xor     rax, rsp
0x180021671  mov     [rsp+278h+var_28], rax
0x180021679  mov     rax, 0C000000000000000h
0x180021683  mov     rbx, r9
0x180021686  mov     rbp, rcx
0x180021689  test    rax, r9
0x18002168c  jz      short loc_180021694
0x18002168e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180021694  mov     r8, rdx; unsigned __int16 *
0x180021697  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002169c  mov     edx, 104h; unsigned __int64
0x1800216a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800216a6  lea     r8, aP0; "_p0"
0x1800216ad  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800216b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800216b7  mov     edx, ebx
0x1800216b9  lea     r9, [rsp+278h+var_238]
0x1800216be  and     edx, 7FFFFFFFh
0x1800216c4  mov     esi, 1
0x1800216c9  mov     r8d, esi
0x1800216cc  mov     rcx, rbp
0x1800216cf  cmova   r8d, edx
0x1800216d3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800216d8  mov     edi, eax
0x1800216da  test    eax, eax
0x1800216dc  jns     short loc_1800216FE
0x1800216de  mov     rcx, [rsp+278h]; this
0x1800216e6  lea     r8, aWil; "wil"
0x1800216ed  mov     r9d, eax; char *
0x1800216f0  mov     edx, 8Bh; void *
0x1800216f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800216fa  mov     eax, edi
0x1800216fc  jmp     short loc_180021753
0x1800216fe  lea     r8, asc_180049BC0; "h"
0x180021705  shr     rbx, 1Fh
0x180021709  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002170e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021713  test    ebx, ebx
0x180021715  lea     rcx, [rbp+8]
0x180021719  lea     r9, [rsp+278h+var_238]
0x18002171e  mov     edx, ebx
0x180021720  cmovnz  esi, ebx
0x180021723  mov     r8d, esi
0x180021726  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002172b  mov     ebx, eax
0x18002172d  test    eax, eax
0x18002172f  jns     short loc_180021751
0x180021731  mov     rcx, [rsp+278h]; this
0x180021739  lea     r8, aWil; "wil"
0x180021740  mov     r9d, eax; char *
0x180021743  mov     edx, 90h; void *
0x180021748  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002174d  mov     eax, ebx
0x18002174f  jmp     short loc_180021753
0x180021751  xor     eax, eax
0x180021753  mov     rcx, [rsp+278h+var_28]
0x18002175b  xor     rcx, rsp; StackCookie
0x18002175e  call    __security_check_cookie
0x180021763  mov     rbx, [rsp+278h+arg_10]
0x18002176b  add     rsp, 260h
0x180021772  pop     rdi
0x180021773  pop     rsi
0x180021774  pop     rbp
0x180021775  retn
```
