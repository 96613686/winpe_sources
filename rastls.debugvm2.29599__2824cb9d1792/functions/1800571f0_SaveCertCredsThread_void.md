# SaveCertCredsThread(void *)

- ea: `0x1800571f0`
- end: `0x180057402`
- name: `?SaveCertCredsThread@@YAKPEAX@Z`
- size: `530`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800234e0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x180036254`
- `0x180052430`
- `0x1800571f0`
- `0x1800580f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005728b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005734c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005728b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005734c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800573d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800573db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800573d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800573db`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180057281`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180057281`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180057342`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180057342`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180057321`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180057335`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180057321`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180057335`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  if ( hObject && *(_QWORD *)Parameter != -1 && !ImpersonateLoggedOnUser(*(HANDLE *)Parameter) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
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
        &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
        EapTLSSSOCertCredentials);
  }
  else
  {
    CredDeleteW(L"*Session", 3u, 0);
    CredDeleteW(L"*Session", 2u, 0);
    if ( CredWriteW(&Credential, 0) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      v7 = 0;
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v6);
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
0x1800571f0  push    rbp
0x1800571f2  push    rbx
0x1800571f3  push    rsi
0x1800571f4  push    rdi
0x1800571f5  push    r14
0x1800571f7  push    r15
0x1800571f9  lea     rbp, [rsp-1B8h]
0x180057201  sub     rsp, 2B8h
0x180057208  mov     rax, cs:__security_cookie
0x18005720f  xor     rax, rsp
0x180057212  mov     [rbp+1E0h+var_40], rax
0x180057219  xor     edx, edx; Val
0x18005721b  mov     rdi, rcx
0x18005721e  lea     rcx, [rsp+2E0h+Credential]; void *
0x180057223  lea     r8d, [rdx+50h]; Size
0x180057227  call    memset_0
0x18005722c  xor     edx, edx; Val
0x18005722e  lea     rcx, [rbp+1E0h+var_240]; void *
0x180057232  mov     r8d, 200h; Size
0x180057238  call    memset_0
0x18005723d  xor     esi, esi
0x18005723f  mov     [rsp+2E0h+var_2B0], rsi
0x180057244  mov     rcx, cs:WPP_GLOBAL_Control
0x18005724b  lea     r14, WPP_GLOBAL_Control
0x180057252  lea     r15, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180057259  cmp     rcx, r14
0x18005725c  jz      short loc_18005726F
0x18005725e  mov     rcx, [rcx+10h]
0x180057262  mov     edx, 0E1h
0x180057267  mov     r8, r15
0x18005726a  call    WPP_SF_
0x18005726f  cmp     cs:hObject, rsi
0x180057276  jz      short loc_1800572BC
0x180057278  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18005727c  jz      short loc_1800572BC
0x18005727e  mov     rcx, [rdi]; hToken
0x180057281  call    cs:__imp_ImpersonateLoggedOnUser
0x180057287  test    eax, eax
0x180057289  jnz     short loc_1800572BC
0x18005728b  call    cs:__imp_GetLastError
0x180057291  mov     ebx, eax
0x180057293  mov     rcx, cs:WPP_GLOBAL_Control
0x18005729a  cmp     rcx, r14
0x18005729d  jz      loc_1800573B5
0x1800572a3  mov     rcx, [rcx+10h]
0x1800572a7  mov     edx, 0E2h
0x1800572ac  mov     r9d, eax
0x1800572af  mov     r8, r15
0x1800572b2  call    WPP_SF_d
0x1800572b7  jmp     loc_1800573B5
0x1800572bc  mov     r8, [rdi]; void *
0x1800572bf  lea     rax, [rsp+2E0h+var_2B0]
0x1800572c4  mov     rdx, [rdi+10h]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x1800572c8  lea     r9, [rsp+2E0h+Credential]; struct _CREDENTIALW *
0x1800572cd  mov     rcx, [rdi+8]; struct _EAPTLS_USER_PROPERTIES *
0x1800572d1  mov     [rsp+2E0h+var_2B8], rax; unsigned __int16 **
0x1800572d6  lea     rax, [rbp+1E0h+var_240]
0x1800572da  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 *
0x1800572df  call    ?GetEapTLSSSOCertCredentials@@YAKPEAU_EAPTLS_USER_PROPERTIES@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAXPEAU_CREDENTIALW@@PEAGPEAPEAG@Z; GetEapTLSSSOCertCredentials(_EAPTLS_USER_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 *,void *,_CREDENTIALW *,ushort *,ushort * *)
0x1800572e4  mov     ebx, eax
0x1800572e6  test    eax, eax
0x1800572e8  jz      short loc_180057313
0x1800572ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572f1  cmp     rcx, r14
0x1800572f4  jz      loc_1800573AB
0x1800572fa  mov     rcx, [rcx+10h]
0x1800572fe  mov     edx, 0E3h
0x180057303  mov     r9d, eax
0x180057306  mov     r8, r15
0x180057309  call    WPP_SF_d
0x18005730e  jmp     loc_1800573AB
0x180057313  xor     r8d, r8d; Flags
0x180057316  lea     rcx, TargetName; "*Session"
0x18005731d  lea     edx, [r8+3]; Type
0x180057321  call    cs:__imp_CredDeleteW
0x180057327  xor     r8d, r8d; Flags
0x18005732a  lea     rcx, TargetName; "*Session"
0x180057331  lea     edx, [r8+2]; Type
0x180057335  call    cs:__imp_CredDeleteW
0x18005733b  xor     edx, edx; Flags
0x18005733d  lea     rcx, [rsp+2E0h+Credential]; Credential
0x180057342  call    cs:__imp_CredWriteW
0x180057348  test    eax, eax
0x18005734a  jnz     short loc_180057378
0x18005734c  call    cs:__imp_GetLastError
0x180057352  mov     ebx, eax
0x180057354  mov     rcx, cs:WPP_GLOBAL_Control
0x18005735b  cmp     rcx, r14
0x18005735e  jz      short loc_180057374
0x180057360  mov     rcx, [rcx+10h]
0x180057364  mov     edx, 0E4h
0x180057369  mov     r9d, eax
0x18005736c  mov     r8, r15
0x18005736f  call    WPP_SF_d
0x180057374  mov     ecx, ebx
0x180057376  jmp     short loc_180057397
0x180057378  mov     rcx, cs:WPP_GLOBAL_Control
0x18005737f  cmp     rcx, r14
0x180057382  jz      short loc_180057395
0x180057384  mov     rcx, [rcx+10h]
0x180057388  mov     edx, 0E5h
0x18005738d  mov     r8, r15
0x180057390  call    WPP_SF_
0x180057395  xor     ecx, ecx; unsigned int
0x180057397  movups  xmm0, xmmword ptr [rdi+18h]
0x18005739b  lea     rdx, [rsp+2E0h+var_2A0]; struct _GUID
0x1800573a0  movdqu  xmmword ptr [rsp+2E0h+var_2A0.Data1], xmm0
0x1800573a6  call    ?WriteCredentialPlumbingEvent@@YAXKU_GUID@@@Z; WriteCredentialPlumbingEvent(ulong,_GUID)
0x1800573ab  test    rdi, rdi
0x1800573ae  jz      short loc_1800573E1
0x1800573b0  mov     rsi, [rsp+2E0h+var_2B0]
0x1800573b5  mov     eax, [rsp+2E0h+Credential.CredentialBlobSize]
0x1800573b9  mov     rdx, [rsp+2E0h+Credential.CredentialBlob]
0x1800573be  test    rax, rax
0x1800573c1  jz      short loc_1800573CF
0x1800573c3  mov     byte ptr [rdx], 0
0x1800573c6  inc     rdx
0x1800573c9  sub     rax, 1
0x1800573cd  jnz     short loc_1800573C3
0x1800573cf  mov     rcx, rsi; hMem
0x1800573d2  call    cs:__imp_LocalFree
0x1800573d8  mov     rcx, rdi; hMem
0x1800573db  call    cs:__imp_LocalFree
0x1800573e1  mov     eax, ebx
0x1800573e3  mov     rcx, [rbp+1E0h+var_40]
0x1800573ea  xor     rcx, rsp; StackCookie
0x1800573ed  call    __security_check_cookie
0x1800573f2  add     rsp, 2B8h
0x1800573f9  pop     r15
0x1800573fb  pop     r14
0x1800573fd  pop     rdi
0x1800573fe  pop     rsi
0x1800573ff  pop     rbx
0x180057400  pop     rbp
0x180057401  retn
```
