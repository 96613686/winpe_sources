# SpUpdateCredentials(unsigned __int64,_GUID *,ulong,uchar *)

- ea: `0x18002a320`
- end: `0x18002a61b`
- name: `?SpUpdateCredentials@@YAJ_KPEAU_GUID@@KPEAE@Z`
- size: `763`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, DWORD, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000d160`
- `0x180014fe0`
- `0x180017820`
- `0x1800178d0`
- `0x180023ce0`
- `0x180023e30`
- `0x18002a320`
- `0x18002b158`
- `0x18002b604`
- `0x18003b1f8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a576`
- `ntdll!RtlFreeUnicodeString` at `0x18002a5a2`
- `ntdll!RtlFreeUnicodeString` at `0x18002a5a2`
- `CRYPT32!CertFreeCertificateContext` at `0x18002a5cb`
- `CRYPT32!CertFreeCertificateContext` at `0x18002a5cb`
- `ext-ms-win-security-certpoleng-l1-1-0!PstGetUserNameForCertificate` at `0x18002a4e7`
- `ext-ms-win-security-certpoleng-l1-1-0!PstGetUserNameForCertificate` at `0x18002a4e7`
- `ext-ms-win-security-certpoleng-l1-1-0!PstAcquirePrivateKey` at `0x18002a499`
- `ext-ms-win-security-certpoleng-l1-1-0!PstAcquirePrivateKey` at `0x18002a499`

## pseudocode

```c
__int64 __fastcall SpUpdateCredentials(__int64 a1, struct _GUID *a2, DWORD a3, unsigned __int8 *a4)
{
  const CERT_CONTEXT *v4; // rsi
  struct _PKU2U_LOGON_SESSION *LogonSession; // r15
  PVOID *v10; // rcx
  unsigned __int64 v11; // rdx
  signed int v12; // ebx
  struct _PKU2U_ASSOCIATED_CREDENTIAL *v13; // rcx
  int v14; // eax
  NTSTATUS UserNameForCertificate; // eax
  __int64 v16; // rdx
  HANDLE v17; // rdi
  PCCERT_CONTEXT pCert; // [rsp+30h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING UserName; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+A0h] [rbp+30h] BYREF

  v4 = 0;
  pCert = 0;
  LogonSession = 0;
  hObject = 0;
  UserName = 0;
  v23 = 0;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a1);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
    {
      v22[1] = 16;
      v22[0] = a2;
      WPP_SF_q_HEX_((unsigned int)v10[2], 175, a3, a1, (__int64)v22);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v11 = *(_QWORD *)&a2->Data1 - SEC_WINNT_AUTH_DATA_TYPE_CERT;
  if ( *(_QWORD *)&a2->Data1 == (_QWORD)SEC_WINNT_AUTH_DATA_TYPE_CERT )
    v11 = *(_QWORD *)a2->Data4 - _mm_srli_si128((__m128i)SEC_WINNT_AUTH_DATA_TYPE_CERT, 8).m128i_u64[0];
  if ( v11 || !*(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) )
  {
    v12 = -2146893042;
    goto LABEL_37;
  }
  v13 = *(struct _PKU2U_ASSOCIATED_CREDENTIAL **)(a1 + 32);
  if ( v13 )
  {
    Pku2uDereferenceAssociatedCredential(v13);
    *(_QWORD *)(a1 + 32) = 0;
  }
  LogonSession = Pku2uLocateLogonSession((struct _LUID *)(*(_QWORD *)(a1 + 16) + 40LL));
  if ( !LogonSession )
  {
    v12 = -1073741729;
LABEL_36:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  v12 = ScHelperBuildCertContext(a4, a3, &pCert);
  if ( v12 < 0 )
  {
    v4 = pCert;
    goto LABEL_36;
  }
  v14 = Pku2uImpersonateToken(*(HANDLE *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 32LL), &hObject, &v23);
  v4 = pCert;
  v12 = v14;
  if ( v14 >= 0 )
  {
    UserNameForCertificate = PstAcquirePrivateKey(pCert);
    v12 = UserNameForCertificate;
    if ( UserNameForCertificate >= 0 )
    {
      UserNameForCertificate = PstGetUserNameForCertificate(v4, &UserName);
      v12 = UserNameForCertificate;
      if ( UserNameForCertificate >= 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_31;
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
        goto LABEL_30;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v16 = 178;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v16 = 177;
    }
    WPP_SF_d(v10[2], v16, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, (unsigned int)UserNameForCertificate);
  }
LABEL_30:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_31:
  v17 = hObject;
  if ( v23 )
  {
    Pku2uRevertImpersonation(hObject);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 )
  {
    CloseHandle(v17);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( UserName.Buffer )
  {
    RtlFreeUnicodeString(&UserName);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( LogonSession )
  {
    Pku2uDereferenceLogonSession(LogonSession);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    CertFreeCertificateContext(v4);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_q(v10[2], 180, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002a320  mov     [rsp-28h+arg_8], rbx
0x18002a325  mov     [rsp-28h+arg_10], rsi
0x18002a32a  push    rbp
0x18002a32b  push    rdi
0x18002a32c  push    r12
0x18002a32e  push    r14
0x18002a330  push    r15
0x18002a332  mov     rbp, rsp
0x18002a335  sub     rsp, 70h
0x18002a339  xor     esi, esi
0x18002a33b  movaps  [rsp+70h+var_10], xmm6
0x18002a340  movups  xmm6, cs:SEC_WINNT_AUTH_DATA_TYPE_CERT
0x18002a347  mov     [rbp+pCert], rsi
0x18002a34b  xor     r15d, r15d
0x18002a34e  xorps   xmm0, xmm0
0x18002a351  mov     [rbp+hObject], rsi
0x18002a355  movups  xmmword ptr [rbp+UserName.Length], xmm0
0x18002a359  mov     [rbp+arg_0], esi
0x18002a35c  mov     rdi, r9
0x18002a35f  mov     r12d, r8d
0x18002a362  mov     rbx, rdx
0x18002a365  mov     r14, rcx
0x18002a368  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a36f  lea     rax, WPP_GLOBAL_Control
0x18002a376  cmp     rcx, rax
0x18002a379  jz      short loc_18002A3EF
0x18002a37b  test    byte ptr [rcx+1Ch], 8
0x18002a37f  jz      short loc_18002A3A7
0x18002a381  mov     rcx, [rcx+10h]
0x18002a385  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18002a38c  mov     edx, 0AEh
0x18002a391  mov     r9, r14
0x18002a394  call    WPP_SF_q
0x18002a399  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3a0  lea     rax, WPP_GLOBAL_Control
0x18002a3a7  cmp     rcx, rax
0x18002a3aa  jz      short loc_18002A3EF
0x18002a3ac  mov     eax, 10h
0x18002a3b1  test    [rcx+1Ch], al
0x18002a3b4  jz      short loc_18002A3EF
0x18002a3b6  xorps   xmm0, xmm0
0x18002a3b9  mov     edx, 0AFh
0x18002a3be  movups  [rbp+var_20], xmm0
0x18002a3c2  mov     word ptr [rbp+var_20+8], ax
0x18002a3c6  mov     r9, r14
0x18002a3c9  mov     qword ptr [rbp+var_20], rbx
0x18002a3cd  lea     rax, [rbp+var_20]
0x18002a3d1  movaps  xmm0, [rbp+var_20]
0x18002a3d5  movdqa  [rbp+var_20], xmm0
0x18002a3da  mov     rcx, [rcx+10h]
0x18002a3de  mov     [rsp+70h+var_50], rax
0x18002a3e3  call    WPP_SF_q_HEX_
0x18002a3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3ef  mov     rdx, [rbx]
0x18002a3f2  movq    rax, xmm6
0x18002a3f7  sub     rdx, rax
0x18002a3fa  jnz     short loc_18002A40D
0x18002a3fc  mov     rdx, [rbx+8]
0x18002a400  psrldq  xmm6, 8
0x18002a405  movq    rax, xmm6
0x18002a40a  sub     rdx, rax
0x18002a40d  test    rdx, rdx
0x18002a410  jz      short loc_18002A41C
0x18002a412  mov     ebx, 8009030Eh
0x18002a417  jmp     loc_18002A590
0x18002a41c  mov     rax, [r14+10h]
0x18002a420  cmp     [rax+20h], esi
0x18002a423  jz      short loc_18002A412
0x18002a425  mov     rcx, [r14+20h]; struct _PKU2U_ASSOCIATED_CREDENTIAL *
0x18002a429  test    rcx, rcx
0x18002a42c  jz      short loc_18002A437
0x18002a42e  call    ?Pku2uDereferenceAssociatedCredential@@YAXPEAU_PKU2U_ASSOCIATED_CREDENTIAL@@@Z; Pku2uDereferenceAssociatedCredential(_PKU2U_ASSOCIATED_CREDENTIAL *)
0x18002a433  mov     [r14+20h], rsi
0x18002a437  mov     rcx, [r14+10h]
0x18002a43b  add     rcx, 28h ; '('; struct _LUID *
0x18002a43f  call    ?Pku2uLocateLogonSession@@YAPEAU_PKU2U_LOGON_SESSION@@PEAU_LUID@@@Z; Pku2uLocateLogonSession(_LUID *)
0x18002a444  mov     r15, rax
0x18002a447  test    rax, rax
0x18002a44a  jnz     short loc_18002A456
0x18002a44c  mov     ebx, 0C000005Fh
0x18002a451  jmp     loc_18002A589
0x18002a456  lea     r8, [rbp+pCert]; struct _CERT_CONTEXT **
0x18002a45a  mov     edx, r12d; cbCertEncoded
0x18002a45d  mov     rcx, rdi; pbCertEncoded
0x18002a460  call    ?ScHelperBuildCertContext@@YAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z; ScHelperBuildCertContext(uchar *,ulong,_CERT_CONTEXT const * *)
0x18002a465  mov     ebx, eax
0x18002a467  test    eax, eax
0x18002a469  js      loc_18002A585
0x18002a46f  mov     rax, [r14+10h]
0x18002a473  lea     r8, [rbp+arg_0]; int *
0x18002a477  lea     rdx, [rbp+hObject]; void **
0x18002a47b  mov     rcx, [rax+18h]
0x18002a47f  mov     rcx, [rcx+20h]; TokenHandle
0x18002a483  call    ?Pku2uImpersonateToken@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken(void *,void * *,int *)
0x18002a488  mov     rsi, [rbp+pCert]
0x18002a48c  mov     ebx, eax
0x18002a48e  test    eax, eax
0x18002a490  js      loc_18002A547
0x18002a496  mov     rcx, rsi; pCert
0x18002a499  call    cs:__imp_PstAcquirePrivateKey
0x18002a49f  mov     ebx, eax
0x18002a4a1  test    eax, eax
0x18002a4a3  jns     short loc_18002A4E0
0x18002a4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4ac  lea     r12, WPP_GLOBAL_Control
0x18002a4b3  cmp     rcx, r12
0x18002a4b6  jz      loc_18002A555
0x18002a4bc  test    byte ptr [rcx+1Ch], 1
0x18002a4c0  jz      loc_18002A555
0x18002a4c6  mov     edx, 0B1h
0x18002a4cb  mov     rcx, [rcx+10h]
0x18002a4cf  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18002a4d6  mov     r9d, eax
0x18002a4d9  call    WPP_SF_d
0x18002a4de  jmp     short loc_18002A54E
0x18002a4e0  lea     rdx, [rbp+UserName]; UserName
0x18002a4e4  mov     rcx, rsi; pCertContext
0x18002a4e7  call    cs:__imp_PstGetUserNameForCertificate
0x18002a4ed  mov     ebx, eax
0x18002a4ef  test    eax, eax
0x18002a4f1  jns     short loc_18002A513
0x18002a4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4fa  lea     r12, WPP_GLOBAL_Control
0x18002a501  cmp     rcx, r12
0x18002a504  jz      short loc_18002A555
0x18002a506  test    byte ptr [rcx+1Ch], 1
0x18002a50a  jz      short loc_18002A555
0x18002a50c  mov     edx, 0B2h
0x18002a511  jmp     short loc_18002A4CB
0x18002a513  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a51a  lea     r12, WPP_GLOBAL_Control
0x18002a521  cmp     rcx, r12
0x18002a524  jz      short loc_18002A555
0x18002a526  test    byte ptr [rcx+1Ch], 2
0x18002a52a  jz      short loc_18002A555
0x18002a52c  mov     rcx, [rcx+10h]; LoggerHandle
0x18002a530  lea     r9, [rbp+UserName]
0x18002a534  mov     edx, 0B3h
0x18002a539  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18002a540  call    WPP_SF_Z
0x18002a545  jmp     short loc_18002A54E
0x18002a547  lea     r12, WPP_GLOBAL_Control
0x18002a54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a555  cmp     [rbp+arg_0], 0
0x18002a559  mov     rdi, [rbp+hObject]
0x18002a55d  jz      short loc_18002A56E
0x18002a55f  mov     rcx, rdi; Token
0x18002a562  call    ?Pku2uRevertImpersonation@@YAXPEAX@Z; Pku2uRevertImpersonation(void *)
0x18002a567  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a56e  test    rdi, rdi
0x18002a571  jz      short loc_18002A597
0x18002a573  mov     rcx, rdi; hObject
0x18002a576  call    cs:__imp_CloseHandle
0x18002a57c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a583  jmp     short loc_18002A597
0x18002a585  mov     rsi, [rbp+pCert]
0x18002a589  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a590  lea     r12, WPP_GLOBAL_Control
0x18002a597  cmp     [rbp+UserName.Buffer], 0
0x18002a59c  jz      short loc_18002A5AF
0x18002a59e  lea     rcx, [rbp+UserName]; UnicodeString
0x18002a5a2  call    cs:__imp_RtlFreeUnicodeString
0x18002a5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5af  test    r15, r15
0x18002a5b2  jz      short loc_18002A5C3
0x18002a5b4  mov     rcx, r15; struct _PKU2U_LOGON_SESSION *
0x18002a5b7  call    ?Pku2uDereferenceLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uDereferenceLogonSession(_PKU2U_LOGON_SESSION *)
0x18002a5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5c3  test    rsi, rsi
0x18002a5c6  jz      short loc_18002A5D8
0x18002a5c8  mov     rcx, rsi; pCertContext
0x18002a5cb  call    cs:__imp_CertFreeCertificateContext
0x18002a5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5d8  cmp     rcx, r12
0x18002a5db  jz      short loc_18002A5FB
0x18002a5dd  test    byte ptr [rcx+1Ch], 8
0x18002a5e1  jz      short loc_18002A5FB
0x18002a5e3  mov     rcx, [rcx+10h]
0x18002a5e7  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18002a5ee  mov     edx, 0B4h
0x18002a5f3  mov     r9, r14
0x18002a5f6  call    WPP_SF_q
0x18002a5fb  movaps  xmm6, [rsp+70h+var_10]
0x18002a600  lea     r11, [rsp+70h+var_s0]
0x18002a605  mov     rsi, [r11+40h]
0x18002a609  mov     eax, ebx
0x18002a60b  mov     rbx, [r11+38h]
0x18002a60f  mov     rsp, r11
0x18002a612  pop     r15
0x18002a614  pop     r14
0x18002a616  pop     r12
0x18002a618  pop     rdi
0x18002a619  pop     rbp
0x18002a61a  retn
```
