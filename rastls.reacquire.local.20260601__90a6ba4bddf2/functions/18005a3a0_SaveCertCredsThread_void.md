# SaveCertCredsThread(void *)

- ea: `0x18005a3a0`
- end: `0x18005a5e3`
- name: `?SaveCertCredsThread@@YAKPEAX@Z`
- size: `579`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025ff0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180038e64`
- `0x180055208`
- `0x18005a3a0`
- `0x18005b328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a51a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a5a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a5b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a5a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a5b5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005a431`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005a431`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18005a50a`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18005a50a`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005a4dd`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005a4f7`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005a4dd`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005a4f7`

## pseudocode

```c
__int64 __fastcall SaveCertCredsThread(char *Parameter)
{
  unsigned __int16 *v2; // rsi
  DWORD LastError; // eax
  DWORD v4; // ebx
  unsigned int EapTLSSSOCertCredentials; // eax
  DWORD v6; // eax
  unsigned int v7; // ecx
  __int64 CredentialBlobSize; // rax
  LPBYTE CredentialBlob; // rdx
  unsigned __int16 *v11; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v12; // [rsp+40h] [rbp-C0h] BYREF
  _CREDENTIALW Credential; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v14[256]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(&Credential, 0, sizeof(Credential));
  memset_0(v14, 0, sizeof(v14));
  v2 = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  if ( hObject && *(_QWORD *)Parameter != -1 && !ImpersonateLoggedOnUser(*(HANDLE *)Parameter) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
    goto LABEL_21;
  }
  EapTLSSSOCertCredentials = GetEapTLSSSOCertCredentials(
                               *((struct _EAPTLS_USER_PROPERTIES **)Parameter + 1),
                               *((struct _EAPTLS_CONN_PROPERTIES_V1 **)Parameter + 2),
                               *(void **)Parameter,
                               &Credential,
                               v14,
                               &v11);
  v4 = EapTLSSSOCertCredentials;
  if ( EapTLSSSOCertCredentials )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        227,
        &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
        EapTLSSSOCertCredentials);
  }
  else
  {
    CredDeleteW(L"*Session", 3u, 0);
    CredDeleteW(L"*Session", 2u, 0);
    if ( CredWriteW(&Credential, 0) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      v7 = 0;
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v6);
      v7 = v4;
    }
    v12 = *(struct _GUID *)(Parameter + 24);
    WriteCredentialPlumbingEvent(v7, &v12);
  }
  if ( Parameter )
  {
    v2 = v11;
LABEL_21:
    CredentialBlobSize = Credential.CredentialBlobSize;
    CredentialBlob = Credential.CredentialBlob;
    if ( Credential.CredentialBlobSize )
    {
      do
      {
        *CredentialBlob++ = 0;
        --CredentialBlobSize;
      }
      while ( CredentialBlobSize );
    }
    LocalFree(v2);
    LocalFree(Parameter);
  }
  return v4;
}

```

## disassembly

```asm
0x18005a3a0  push    rbp
0x18005a3a2  push    rbx
0x18005a3a3  push    rsi
0x18005a3a4  push    rdi
0x18005a3a5  push    r14
0x18005a3a7  push    r15
0x18005a3a9  lea     rbp, [rsp-1B8h]
0x18005a3b1  sub     rsp, 2B8h
0x18005a3b8  mov     rax, cs:__security_cookie
0x18005a3bf  xor     rax, rsp
0x18005a3c2  mov     [rbp+1E0h+var_40], rax
0x18005a3c9  xor     edx, edx; Val
0x18005a3cb  mov     rdi, rcx
0x18005a3ce  lea     rcx, [rsp+2E0h+Credential]; void *
0x18005a3d3  lea     r8d, [rdx+50h]; Size
0x18005a3d7  call    memset_0
0x18005a3dc  xor     edx, edx; Val
0x18005a3de  lea     rcx, [rbp+1E0h+var_240]; void *
0x18005a3e2  mov     r8d, 200h; Size
0x18005a3e8  call    memset_0
0x18005a3ed  xor     esi, esi
0x18005a3ef  mov     [rsp+2E0h+var_2B0], rsi
0x18005a3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a3fb  lea     r14, WPP_GLOBAL_Control
0x18005a402  lea     r15, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005a409  cmp     rcx, r14
0x18005a40c  jz      short loc_18005A41F
0x18005a40e  mov     rcx, [rcx+10h]
0x18005a412  mov     edx, 0E1h
0x18005a417  mov     r8, r15
0x18005a41a  call    WPP_SF_
0x18005a41f  cmp     cs:hObject, rsi
0x18005a426  jz      short loc_18005A478
0x18005a428  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18005a42c  jz      short loc_18005A478
0x18005a42e  mov     rcx, [rdi]; hToken
0x18005a431  call    cs:__imp_ImpersonateLoggedOnUser
0x18005a438  nop     dword ptr [rax+rax+00h]
0x18005a43d  test    eax, eax
0x18005a43f  jnz     short loc_18005A478
0x18005a441  call    cs:__imp_GetLastError
0x18005a448  nop     dword ptr [rax+rax+00h]
0x18005a44d  mov     ebx, eax
0x18005a44f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a456  cmp     rcx, r14
0x18005a459  jz      loc_18005A589
0x18005a45f  mov     rcx, [rcx+10h]
0x18005a463  mov     edx, 0E2h
0x18005a468  mov     r9d, eax
0x18005a46b  mov     r8, r15
0x18005a46e  call    WPP_SF_d
0x18005a473  jmp     loc_18005A589
0x18005a478  mov     r8, [rdi]; void *
0x18005a47b  lea     rax, [rsp+2E0h+var_2B0]
0x18005a480  mov     rdx, [rdi+10h]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18005a484  lea     r9, [rsp+2E0h+Credential]; struct _CREDENTIALW *
0x18005a489  mov     rcx, [rdi+8]; struct _EAPTLS_USER_PROPERTIES *
0x18005a48d  mov     [rsp+2E0h+var_2B8], rax; unsigned __int16 **
0x18005a492  lea     rax, [rbp+1E0h+var_240]
0x18005a496  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 *
0x18005a49b  call    ?GetEapTLSSSOCertCredentials@@YAKPEAU_EAPTLS_USER_PROPERTIES@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAXPEAU_CREDENTIALW@@PEAGPEAPEAG@Z; GetEapTLSSSOCertCredentials(_EAPTLS_USER_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 *,void *,_CREDENTIALW *,ushort *,ushort * *)
0x18005a4a0  mov     ebx, eax
0x18005a4a2  test    eax, eax
0x18005a4a4  jz      short loc_18005A4CF
0x18005a4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a4ad  cmp     rcx, r14
0x18005a4b0  jz      loc_18005A57F
0x18005a4b6  mov     rcx, [rcx+10h]
0x18005a4ba  mov     edx, 0E3h
0x18005a4bf  mov     r9d, eax
0x18005a4c2  mov     r8, r15
0x18005a4c5  call    WPP_SF_d
0x18005a4ca  jmp     loc_18005A57F
0x18005a4cf  xor     r8d, r8d; Flags
0x18005a4d2  lea     rcx, TargetName; "*Session"
0x18005a4d9  lea     edx, [r8+3]; Type
0x18005a4dd  call    cs:__imp_CredDeleteW
0x18005a4e4  nop     dword ptr [rax+rax+00h]
0x18005a4e9  xor     r8d, r8d; Flags
0x18005a4ec  lea     rcx, TargetName; "*Session"
0x18005a4f3  lea     edx, [r8+2]; Type
0x18005a4f7  call    cs:__imp_CredDeleteW
0x18005a4fe  nop     dword ptr [rax+rax+00h]
0x18005a503  xor     edx, edx; Flags
0x18005a505  lea     rcx, [rsp+2E0h+Credential]; Credential
0x18005a50a  call    cs:__imp_CredWriteW
0x18005a511  nop     dword ptr [rax+rax+00h]
0x18005a516  test    eax, eax
0x18005a518  jnz     short loc_18005A54C
0x18005a51a  call    cs:__imp_GetLastError
0x18005a521  nop     dword ptr [rax+rax+00h]
0x18005a526  mov     ebx, eax
0x18005a528  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a52f  cmp     rcx, r14
0x18005a532  jz      short loc_18005A548
0x18005a534  mov     rcx, [rcx+10h]
0x18005a538  mov     edx, 0E4h
0x18005a53d  mov     r9d, eax
0x18005a540  mov     r8, r15
0x18005a543  call    WPP_SF_d
0x18005a548  mov     ecx, ebx
0x18005a54a  jmp     short loc_18005A56B
0x18005a54c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a553  cmp     rcx, r14
0x18005a556  jz      short loc_18005A569
0x18005a558  mov     rcx, [rcx+10h]
0x18005a55c  mov     edx, 0E5h
0x18005a561  mov     r8, r15
0x18005a564  call    WPP_SF_
0x18005a569  xor     ecx, ecx; unsigned int
0x18005a56b  movups  xmm0, xmmword ptr [rdi+18h]
0x18005a56f  lea     rdx, [rsp+2E0h+var_2A0]; struct _GUID
0x18005a574  movdqu  xmmword ptr [rsp+2E0h+var_2A0.Data1], xmm0
0x18005a57a  call    ?WriteCredentialPlumbingEvent@@YAXKU_GUID@@@Z; WriteCredentialPlumbingEvent(ulong,_GUID)
0x18005a57f  test    rdi, rdi
0x18005a582  jz      short loc_18005A5C1
0x18005a584  mov     rsi, [rsp+2E0h+var_2B0]
0x18005a589  mov     eax, [rsp+2E0h+Credential.CredentialBlobSize]
0x18005a58d  mov     rdx, [rsp+2E0h+Credential.CredentialBlob]
0x18005a592  test    rax, rax
0x18005a595  jz      short loc_18005A5A3
0x18005a597  mov     byte ptr [rdx], 0
0x18005a59a  inc     rdx
0x18005a59d  sub     rax, 1
0x18005a5a1  jnz     short loc_18005A597
0x18005a5a3  mov     rcx, rsi; hMem
0x18005a5a6  call    cs:__imp_LocalFree
0x18005a5ad  nop     dword ptr [rax+rax+00h]
0x18005a5b2  mov     rcx, rdi; hMem
0x18005a5b5  call    cs:__imp_LocalFree
0x18005a5bc  nop     dword ptr [rax+rax+00h]
0x18005a5c1  mov     eax, ebx
0x18005a5c3  mov     rcx, [rbp+1E0h+var_40]
0x18005a5ca  xor     rcx, rsp; StackCookie
0x18005a5cd  call    __security_check_cookie
0x18005a5d2  add     rsp, 2B8h
0x18005a5d9  pop     r15
0x18005a5db  pop     r14
0x18005a5dd  pop     rdi
0x18005a5de  pop     rsi
0x18005a5df  pop     rbx
0x18005a5e0  pop     rbp
0x18005a5e1  retn
```
