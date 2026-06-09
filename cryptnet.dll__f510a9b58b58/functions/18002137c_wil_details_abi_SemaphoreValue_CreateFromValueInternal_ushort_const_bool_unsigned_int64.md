# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18002137c`
- end: `0x18002148f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001acf4`
- `0x18001ae48`

## callees

- `0x180003640`
- `0x180011e40`
- `0x18001afa4`
- `0x18002137c`
- `0x1800242a8`
- `0x180024378`
- `0x1800265b0`

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
0x18002137c  push    rbx
0x18002137e  push    rbp
0x18002137f  push    rsi
0x180021380  push    rdi
0x180021381  push    r14
0x180021383  sub     rsp, 260h
0x18002138a  mov     rax, cs:__security_cookie
0x180021391  xor     rax, rsp
0x180021394  mov     [rsp+288h+var_38], rax
0x18002139c  mov     rax, 0C000000000000000h
0x1800213a6  mov     rbx, r9
0x1800213a9  mov     rbp, rcx
0x1800213ac  test    rax, r9
0x1800213af  jz      short loc_1800213B7
0x1800213b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800213b7  mov     r8, rdx; unsigned __int16 *
0x1800213ba  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800213bf  mov     r14d, 104h
0x1800213c5  mov     edx, r14d; unsigned __int64
0x1800213c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800213cd  lea     r8, aP0; "_p0"
0x1800213d4  mov     edx, r14d; unsigned __int64
0x1800213d7  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800213dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800213e1  mov     edx, ebx
0x1800213e3  lea     r9, [rsp+288h+var_248]
0x1800213e8  and     edx, 7FFFFFFFh
0x1800213ee  mov     esi, 1
0x1800213f3  mov     r8d, esi
0x1800213f6  mov     rcx, rbp
0x1800213f9  cmova   r8d, edx
0x1800213fd  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180021402  mov     edi, eax
0x180021404  test    eax, eax
0x180021406  jns     short loc_180021420
0x180021408  mov     rcx, [rsp+288h]; this
0x180021410  lea     edx, [r14-79h]; void *
0x180021414  mov     r9d, eax; char *
0x180021417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002141c  mov     eax, edi
0x18002141e  jmp     short loc_180021471
0x180021420  lea     r8, asc_18002AC78; "h"
0x180021427  shr     rbx, 1Fh
0x18002142b  mov     rdx, r14; unsigned __int64
0x18002142e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180021433  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021438  test    ebx, ebx
0x18002143a  lea     rcx, [rbp+8]
0x18002143e  lea     r9, [rsp+288h+var_248]
0x180021443  mov     edx, ebx
0x180021445  cmovnz  esi, ebx
0x180021448  mov     r8d, esi
0x18002144b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180021450  mov     ebx, eax
0x180021452  test    eax, eax
0x180021454  jns     short loc_18002146F
0x180021456  mov     rcx, [rsp+288h]; this
0x18002145e  mov     r9d, eax; char *
0x180021461  mov     edx, 90h; void *
0x180021466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002146b  mov     eax, ebx
0x18002146d  jmp     short loc_180021471
0x18002146f  xor     eax, eax
0x180021471  mov     rcx, [rsp+288h+var_38]
0x180021479  xor     rcx, rsp; StackCookie
0x18002147c  call    __security_check_cookie
0x180021481  add     rsp, 260h
0x180021488  pop     r14
0x18002148a  pop     rdi
0x18002148b  pop     rsi
0x18002148c  pop     rbp
0x18002148d  pop     rbx
0x18002148e  retn
```
