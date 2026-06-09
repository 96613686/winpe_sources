# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005fd8`
- end: `0x1800060e8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800075a8`
- `0x1800076cc`

## callees

- `0x180005fd8`
- `0x1800087fc`
- `0x180008ebc`
- `0x180008f9c`
- `0x18000995c`
- `0x180009a6c`
- `0x18000ad30`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
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
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
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
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x180005fd8  mov     [rsp+arg_10], rbx
0x180005fdd  push    rbp
0x180005fde  push    rsi
0x180005fdf  push    rdi
0x180005fe0  sub     rsp, 260h
0x180005fe7  mov     rax, cs:__security_cookie
0x180005fee  xor     rax, rsp
0x180005ff1  mov     [rsp+278h+var_28], rax
0x180005ff9  mov     rax, 0C000000000000000h
0x180006003  mov     rbx, r9
0x180006006  mov     rbp, rcx
0x180006009  test    rax, r9
0x18000600c  jz      short loc_180006014
0x18000600e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006014  mov     r9, rdx; pszSrc
0x180006017  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000601c  mov     edx, 104h; cchDest
0x180006021  call    StringCopyWorkerW
0x180006026  lea     r8, aP0; "_p0"
0x18000602d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180006032  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006037  mov     edx, ebx
0x180006039  lea     r9, [rsp+278h+pszDest]
0x18000603e  and     edx, 7FFFFFFFh
0x180006044  mov     esi, 1
0x180006049  mov     r8d, esi
0x18000604c  mov     rcx, rbp
0x18000604f  cmova   r8d, edx
0x180006053  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006058  mov     edi, eax
0x18000605a  test    eax, eax
0x18000605c  jns     short loc_180006077
0x18000605e  mov     rcx, [rsp+278h]; this
0x180006066  mov     r9d, eax; char *
0x180006069  mov     edx, 8Bh; void *
0x18000606e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006073  mov     eax, edi
0x180006075  jmp     short loc_1800060C5
0x180006077  lea     r8, asc_18000E138; "h"
0x18000607e  shr     rbx, 1Fh
0x180006082  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180006087  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000608c  test    ebx, ebx
0x18000608e  lea     rcx, [rbp+8]
0x180006092  lea     r9, [rsp+278h+pszDest]
0x180006097  mov     edx, ebx
0x180006099  cmovnz  esi, ebx
0x18000609c  mov     r8d, esi
0x18000609f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800060a4  mov     ebx, eax
0x1800060a6  test    eax, eax
0x1800060a8  jns     short loc_1800060C3
0x1800060aa  mov     rcx, [rsp+278h]; this
0x1800060b2  mov     r9d, eax; char *
0x1800060b5  mov     edx, 90h; void *
0x1800060ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060bf  mov     eax, ebx
0x1800060c1  jmp     short loc_1800060C5
0x1800060c3  xor     eax, eax
0x1800060c5  mov     rcx, [rsp+278h+var_28]
0x1800060cd  xor     rcx, rsp; StackCookie
0x1800060d0  call    __security_check_cookie
0x1800060d5  mov     rbx, [rsp+278h+arg_10]
0x1800060dd  add     rsp, 260h
0x1800060e4  pop     rdi
0x1800060e5  pop     rsi
0x1800060e6  pop     rbp
0x1800060e7  retn
```
