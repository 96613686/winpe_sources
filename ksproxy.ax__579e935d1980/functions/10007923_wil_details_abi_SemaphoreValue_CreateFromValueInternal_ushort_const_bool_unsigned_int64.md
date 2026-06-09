# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x10007923`
- end: `0x100079c4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AAEJPBG_N_K@Z`
- size: `161`
- prototype: `int __thiscall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1000fcc8`

## callees

- `0x100068a9`
- `0x1000697b`
- `0x100075ad`
- `0x10007624`
- `0x10007923`
- `0x1000f649`
- `0x1003aba0`

## pseudocode

```c
void *__thiscall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        wchar_t *pszDest,
        bool a3,
        unsigned __int64 a4)
{
  LONG v5; // eax
  void *semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z; // eax
  void *v7; // esi
  int v9; // [esp-Ch] [ebp-224h]
  int v10; // [esp-8h] [ebp-220h]
  int v11; // [esp-4h] [ebp-21Ch]
  wil::details::in1diag3 *v12; // [esp+0h] [ebp-218h]
  unsigned int v13; // [esp+0h] [ebp-218h]
  unsigned int v14; // [esp+0h] [ebp-218h]
  size_t v15; // [esp+4h] [ebp-214h]
  const unsigned __int16 *v16; // [esp+4h] [ebp-214h]
  const char *v17; // [esp+4h] [ebp-214h]
  int v18[131]; // [esp+8h] [ebp-210h] BYREF

  if ( HIDWORD(a4) | a4 & 0x80000000 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
  StringCopyWorkerW(pszDest, (size_t)pszDest, (size_t *)pszDest, (STRSAFE_PCNZWCH)v12, v15);
  StringCchCatW(L"_p0", v13, v16);
  v5 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v5 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z = (void *)_create___semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z(this, a4 & 0x7FFFFFFF, v5, (const WCHAR *)v18, v9, v10, v11);
  v7 = semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z;
  if ( (int)semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    (wil::details::in1diag3 *)"wil",
    semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z,
    v14,
    v17,
    v18[0]);
  return v7;
}

```

## disassembly

```asm
0x10007923  mov     edi, edi
0x10007925  push    ebp
0x10007926  mov     ebp, esp
0x10007928  sub     esp, 210h
0x1000792e  mov     eax, ___security_cookie
0x10007933  xor     eax, ebp
0x10007935  mov     [ebp+var_4], eax
0x10007938  push    esi; char *
0x10007939  mov     esi, dword ptr [ebp+arg_8]
0x1000793c  mov     eax, esi
0x1000793e  and     eax, 80000000h
0x10007943  or      eax, dword ptr [ebp+arg_8+4]
0x10007946  push    edi; this
0x10007947  mov     edi, ecx
0x10007949  mov     ecx, [ebp+pszDest]
0x1000794c  jnz     short loc_100079BF
0x1000794e  push    ecx; pcchNewDestLength
0x1000794f  push    ecx; cchDest
0x10007950  push    ecx; pszDest
0x10007951  mov     edx, 104h
0x10007956  lea     ecx, [ebp+var_210]
0x1000795c  call    StringCopyWorkerW
0x10007961  push    offset aP0; "_p0"
0x10007966  lea     ecx, [ebp+var_210]
0x1000796c  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x10007971  sub     esp, 0Ch
0x10007974  lea     eax, [ebp+var_210]
0x1000797a  mov     ecx, edi
0x1000797c  push    eax
0x1000797d  xor     eax, eax
0x1000797f  inc     eax
0x10007980  and     esi, 7FFFFFFFh
0x10007986  cmovnz  eax, esi
0x10007989  push    eax
0x1000798a  push    esi
0x1000798b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z
0x10007990  mov     esi, eax
0x10007992  test    esi, esi
0x10007994  jns     short loc_100079AD
0x10007996  mov     ecx, [ebp+4]
0x10007999  mov     edx, 8Bh
0x1000799e  push    esi; void *
0x1000799f  push    offset aWil; "wil"
0x100079a4  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100079a9  mov     eax, esi
0x100079ab  jmp     short loc_100079AF
0x100079ad  xor     eax, eax
0x100079af  mov     ecx, [ebp+var_4]
0x100079b2  pop     edi
0x100079b3  xor     ecx, ebp; StackCookie
0x100079b5  pop     esi
0x100079b6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100079bb  leave
0x100079bc  retn    10h
0x100079bf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
