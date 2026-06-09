# BitLockerToast::IsAdminUserToken(bool *)

- ea: `0x18000aa00`
- end: `0x18000ab0f`
- name: `?IsAdminUserToken@BitLockerToast@@QEAAJPEA_N@Z`
- size: `271`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010cb0`

## callees

- `0x18000aa00`
- `0x180012090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000aa42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000aa42`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000aa54`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000aa54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aaff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aaff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aaa3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aac6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aaa3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aac6`

## pseudocode

```c
__int64 __fastcall BitLockerToast::IsAdminUserToken(BitLockerToast *this, bool *a2)
{
  HANDLE CurrentProcess; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation_4; // [rsp+54h] [rbp+24h]
  DWORD ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation_4 = HIDWORD(this);
  TokenHandle = 0;
  v12 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    goto LABEL_4;
  v6 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &v12, 8u, &ReturnLength) )
    {
      *a2 = 1;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 == -2147023584 )
      {
        v6 = 0;
        *a2 = 0;
      }
    }
    goto LABEL_15;
  }
  if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    *a2 = TokenInformation == 3;
  }
  else
  {
LABEL_4:
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18000aa00  mov     [rsp-18h+TokenInformation], rcx
0x18000aa05  push    rbp
0x18000aa06  push    rbx
0x18000aa07  push    rdi
0x18000aa08  mov     rbp, rsp
0x18000aa0b  sub     rsp, 30h
0x18000aa0f  mov     [rbp+TokenHandle], 0
0x18000aa17  mov     rdi, rdx
0x18000aa1a  mov     [rbp+arg_18], 0
0x18000aa22  mov     dword ptr [rbp+TokenInformation], 0
0x18000aa29  mov     [rbp+arg_8], 0
0x18000aa30  test    rdx, rdx
0x18000aa33  jnz     short loc_18000AA3F
0x18000aa35  mov     eax, 80004003h
0x18000aa3a  jmp     loc_18000AB07
0x18000aa3f  mov     byte ptr [rdx], 0
0x18000aa42  call    cs:__imp_GetCurrentProcess
0x18000aa48  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000aa4c  mov     edx, 20008h; DesiredAccess
0x18000aa51  mov     rcx, rax; ProcessHandle
0x18000aa54  call    cs:__imp_OpenProcessToken
0x18000aa5a  test    eax, eax
0x18000aa5c  jnz     short loc_18000AA79
0x18000aa5e  call    cs:__imp_GetLastError
0x18000aa64  mov     ebx, eax
0x18000aa66  test    eax, eax
0x18000aa68  jle     loc_18000AAF6
0x18000aa6e  movzx   ebx, ax
0x18000aa71  or      ebx, 80070000h
0x18000aa77  jmp     short loc_18000AAF6
0x18000aa79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18000aa80  xor     ebx, ebx
0x18000aa82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18000aa87  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000aa8b  test    al, al
0x18000aa8d  lea     rax, [rbp+arg_8]
0x18000aa91  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000aa96  jz      short loc_18000AAB8
0x18000aa98  lea     r9d, [rbx+4]; TokenInformationLength
0x18000aa9c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000aaa0  lea     edx, [rbx+12h]; TokenInformationClass
0x18000aaa3  call    cs:__imp_GetTokenInformation
0x18000aaa9  test    eax, eax
0x18000aaab  jz      short loc_18000AA5E
0x18000aaad  cmp     dword ptr [rbp+TokenInformation], 3
0x18000aab1  setz    al
0x18000aab4  mov     [rdi], al
0x18000aab6  jmp     short loc_18000AAF6
0x18000aab8  mov     r9d, 8; TokenInformationLength
0x18000aabe  lea     r8, [rbp+arg_18]; TokenInformation
0x18000aac2  lea     edx, [r9+0Bh]; TokenInformationClass
0x18000aac6  call    cs:__imp_GetTokenInformation
0x18000aacc  test    eax, eax
0x18000aace  jz      short loc_18000AAD5
0x18000aad0  mov     byte ptr [rdi], 1
0x18000aad3  jmp     short loc_18000AAF6
0x18000aad5  call    cs:__imp_GetLastError
0x18000aadb  mov     ebx, eax
0x18000aadd  test    eax, eax
0x18000aadf  jle     short loc_18000AAEA
0x18000aae1  movzx   ebx, ax
0x18000aae4  or      ebx, 80070000h
0x18000aaea  cmp     ebx, 80070520h
0x18000aaf0  jnz     short loc_18000AAF6
0x18000aaf2  xor     ebx, ebx
0x18000aaf4  mov     [rdi], bl
0x18000aaf6  mov     rcx, [rbp+TokenHandle]; hObject
0x18000aafa  test    rcx, rcx
0x18000aafd  jz      short loc_18000AB05
0x18000aaff  call    cs:__imp_CloseHandle
0x18000ab05  mov     eax, ebx
0x18000ab07  add     rsp, 30h
0x18000ab0b  pop     rdi
0x18000ab0c  pop     rbx
0x18000ab0d  pop     rbp
0x18000ab0e  retn
```
