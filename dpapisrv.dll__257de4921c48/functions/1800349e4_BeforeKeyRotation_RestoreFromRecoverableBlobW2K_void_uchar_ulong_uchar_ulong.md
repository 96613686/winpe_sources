# BeforeKeyRotation::RestoreFromRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800349e4`
- end: `0x180034ff0`
- name: `?RestoreFromRecoverableBlobW2K@BeforeKeyRotation@@YAHPEAXPEAEKPEAPEAEPEAK@Z`
- size: `1548`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, unsigned int *, unsigned __int8 *, HLOCAL *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035dd4`

## callees

- `0x180002310`
- `0x1800029d0`
- `0x180007f10`
- `0x18001d810`
- `0x180032218`
- `0x1800349e4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180034d20`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180034d20`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180034cd4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180034cd4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180034dd8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180034dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034f89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034f89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034fac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034fac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034aab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034e80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034aab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034e80`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180034c12`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180034c12`
- `bcrypt!BCryptDecrypt` at `0x180034c5c`
- `bcrypt!BCryptDecrypt` at `0x180034c5c`
- `bcrypt!BCryptDestroyKey` at `0x180034c74`
- `bcrypt!BCryptDestroyKey` at `0x180034eda`
- `bcrypt!BCryptDestroyKey` at `0x180034c74`
- `bcrypt!BCryptDestroyKey` at `0x180034eda`

## string_xrefs

- `0x180034b52`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180034d8f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180034e4a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::RestoreFromRecoverableBlobW2K(
        BeforeKeyRotation *this,
        unsigned int *a2,
        unsigned __int8 *a3,
        HLOCAL *a4,
        unsigned __int8 **a5)
{
  size_t v6; // r15
  UCHAR *v7; // r14
  unsigned int v8; // esi
  HLOCAL *v9; // r13
  void *BCryptProviderHandle; // rax
  unsigned int v11; // r8d
  int v12; // edx
  DWORD v13; // ebx
  UCHAR *v14; // r12
  __int64 v15; // rcx
  UCHAR *v16; // rax
  DWORD v17; // ecx
  __int64 v18; // rcx
  UCHAR *v19; // r13
  unsigned int v20; // eax
  unsigned int *v21; // r13
  __int64 v22; // r9
  const char *v23; // rdx
  __int64 v24; // rcx
  char *v25; // r13
  DWORD LastError; // eax
  SIZE_T v27; // rdx
  __int64 v28; // r9
  unsigned __int8 **v29; // r15
  HLOCAL v30; // rax
  UCHAR *v31; // rax
  size_t v32; // rax
  UCHAR *v33; // rax
  __int64 v34; // rdx
  unsigned int v35; // edi
  UCHAR *v36; // rcx
  unsigned int v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+64h] [rbp-9Ch]
  unsigned int v40; // [rsp+68h] [rbp-98h]
  unsigned __int8 *v42; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v43; // [rsp+80h] [rbp-80h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp-70h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp-68h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+A0h] [rbp-60h]
  PSID SidToCheck; // [rsp+A8h] [rbp-58h]
  HANDLE TokenHandle; // [rsp+B0h] [rbp-50h]
  unsigned __int8 **v49; // [rsp+B8h] [rbp-48h]
  UCHAR v50[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+D0h] [rbp-30h]
  UCHAR pbOutput[24]; // [rsp+D8h] [rbp-28h] BYREF
  UCHAR v54[24]; // [rsp+F0h] [rbp-10h] BYREF

  v6 = (unsigned int)a3;
  v7 = 0;
  TokenHandle = this;
  v8 = 0;
  v40 = (unsigned int)a3;
  v49 = a5;
  *(_QWORD *)&v43.Data1 = 0;
  LODWORD(v42) = 0;
  v9 = a4;
  *(_DWORD *)v43.Data4 = 0;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6801u);
  hAlgorithm = BCryptProviderHandle;
  phKey = 0;
  pcbResult = 0;
  if ( !a2 || !(_DWORD)v6 || !v9 || !a5 )
    goto LABEL_80;
  v11 = 0;
  v12 = 1;
  v13 = 0;
  v38 = 0;
  v14 = 0;
  *(_DWORD *)&v43.Data4[4] = 0;
  v15 = 20;
  if ( !BCryptProviderHandle )
    goto LABEL_58;
  *v9 = 0;
  v16 = (UCHAR *)LocalAlloc(0, (unsigned int)v6);
  v14 = v16;
  if ( !v16 )
  {
    v17 = 1130;
LABEL_81:
    SetLastError(v17);
    return 0;
  }
  memcpy_0(v16, a2, v6);
  if ( (unsigned int)v6 < 0x94 || *a2 != 1 || (v18 = a2[2], v18 != v6 - 96) || a2[1] > (unsigned int)v18 )
  {
LABEL_80:
    v17 = 87;
    goto LABEL_81;
  }
  if ( *(_QWORD *)&BeforeKeyRotation::g_guidW2KPreferredKey.Data1 == *(_QWORD *)(a2 + 3)
    && *(_QWORD *)BeforeKeyRotation::g_guidW2KPreferredKey.Data4 == *(_QWORD *)(a2 + 5) )
  {
    v7 = *(UCHAR **)&BeforeKeyRotation::g_pbW2KPreferredKey.Data1;
    v12 = 1;
    v8 = (unsigned int)BeforeKeyRotation::g_cbW2KPreferredKey;
  }
  else
  {
    if ( !(unsigned int)BeforeKeyRotation::GetBackupKey((BeforeKeyRotation *)(a2 + 3), &v43, &v42, 0) )
    {
      DebugTraceError(2147500037LL, "E_FAIL", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 5535);
      v12 = 1;
      v7 = *(UCHAR **)&v43.Data1;
      v8 = (unsigned int)v42;
      goto LABEL_55;
    }
    v7 = *(UCHAR **)&v43.Data1;
    v12 = 0;
    v8 = (unsigned int)v42;
  }
  v19 = (UCHAR *)a2;
  v39 = v12;
  if ( *(_DWORD *)v7 != 1 )
  {
    v9 = a4;
LABEL_55:
    v11 = 0;
LABEL_56:
    v6 = (unsigned int)v6;
    goto LABEL_57;
  }
  v20 = 0;
  while ( 1 )
  {
    if ( v20 )
      v19 = v14;
    *(_QWORD *)&v43.Data1 = v19;
    if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v7 + 4, v8 - 4, v19 + 28, 0x44u, 0, 0, pbOutput, 0x14u) )
    {
      v22 = 5572;
LABEL_33:
      v23 = "E_FAIL";
      v24 = 2147500037LL;
LABEL_34:
      DebugTraceError(v24, v23, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v22);
      goto LABEL_30;
    }
    if ( BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbOutput, 0x14u, 0) < 0 )
      goto LABEL_30;
    v21 = (unsigned int *)(v19 + 96);
    if ( BCryptDecrypt(
           phKey,
           (PUCHAR)v21,
           *(_DWORD *)(*(_QWORD *)&v43.Data1 + 8LL),
           0,
           0,
           0,
           (PUCHAR)v21,
           *(_DWORD *)(*(_QWORD *)&v43.Data1 + 8LL),
           &pcbResult,
           0) < 0 )
    {
      BCryptDestroyKey(phKey);
      goto LABEL_30;
    }
    BCryptDestroyKey(phKey);
    if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v7 + 4, v8 - 4, (PUCHAR)v21, 0x20u, 0, 0, v54, 0x14u) )
    {
      v22 = 5633;
      goto LABEL_33;
    }
    SidToCheck = v21 + 13;
    if ( IsValidSid(v21 + 13) )
      break;
    if ( (unsigned __int64)v8 - 4 <= 0x40 )
    {
      v13 = 1337;
LABEL_30:
      v9 = a4;
      v12 = v39;
      v11 = v38;
      goto LABEL_56;
    }
    v19 = *(UCHAR **)&v43.Data1;
    v20 = v8;
    v38 = v8;
    v8 = 68;
  }
  LODWORD(v42) = GetLengthSid(v21 + 13);
  if ( !(unsigned int)ReusableHMAC(
                        0,
                        0,
                        0x8009u,
                        v54,
                        0x14u,
                        (PUCHAR)v21 + 52,
                        *(_DWORD *)(*(_QWORD *)&v43.Data1 + 8LL) - 52,
                        0,
                        0,
                        v50,
                        0x14u) )
  {
    v22 = 5683;
    goto LABEL_33;
  }
  if ( *((_QWORD *)v21 + 4) != *(_QWORD *)v50 || *((_QWORD *)v21 + 5) != v51 || v21[12] != v52 )
  {
    v22 = 5694;
LABEL_42:
    v24 = 12;
    v23 = "dwLastError";
    v13 = 12;
    goto LABEL_34;
  }
  v25 = (char *)SidToCheck;
  if ( !CheckTokenMembership(TokenHandle, SidToCheck, (PBOOL)v43.Data4) )
  {
    LastError = GetLastError();
    v22 = 5706;
    v23 = "dwLastError";
    v13 = LastError;
    v24 = LastError;
    goto LABEL_34;
  }
  if ( !*(_DWORD *)v43.Data4 )
  {
    v22 = 5713;
    goto LABEL_42;
  }
  v27 = *(unsigned int *)(*(_QWORD *)&v43.Data1 + 4LL);
  if ( v27 != v6 - (unsigned int)v42 - 148 )
  {
    v13 = 87;
    v28 = 5728;
    goto LABEL_45;
  }
  v29 = v49;
  *(_DWORD *)v49 = v27;
  v30 = LocalAlloc(0, v27);
  *a4 = v30;
  if ( v30 )
  {
    memcpy_0(v30, &v25[(unsigned int)v42], *(unsigned int *)v29);
    *(_DWORD *)&v43.Data4[4] = 1;
  }
  else
  {
    *(_DWORD *)v29 = 0;
    v28 = 5743;
    v13 = 1130;
LABEL_45:
    DebugTraceError(v13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v28);
  }
  v9 = a4;
  v6 = v40;
  v12 = v39;
  v11 = v38;
LABEL_57:
  v15 = 20;
LABEL_58:
  v31 = pbOutput;
  do
  {
    *v31++ = 0;
    --v15;
  }
  while ( v15 );
  v32 = v6;
  do
  {
    *(_BYTE *)a2 = 0;
    a2 = (unsigned int *)((char *)a2 + 1);
    --v32;
  }
  while ( v32 );
  if ( !v12 && v7 )
  {
    v33 = v7;
    if ( v11 )
      v8 = v11;
    v34 = v8;
    if ( v8 )
    {
      do
      {
        *v33++ = 0;
        --v34;
      }
      while ( v34 );
    }
    LocalFree(v7);
  }
  v35 = *(_DWORD *)&v43.Data4[4];
  if ( !*(_DWORD *)&v43.Data4[4] )
  {
    if ( *v9 )
    {
      LocalFree(*v9);
      *v9 = 0;
    }
    if ( !v13 )
      v13 = 13;
    SetLastError(v13);
  }
  if ( v14 )
  {
    v36 = v14;
    do
    {
      *v36++ = 0;
      --v6;
    }
    while ( v6 );
    LocalFree(v14);
  }
  return v35;
}

```

## disassembly

```asm
0x1800349e4  push    rbp
0x1800349e6  push    rbx
0x1800349e7  push    rsi
0x1800349e8  push    rdi
0x1800349e9  push    r12
0x1800349eb  push    r13
0x1800349ed  push    r14
0x1800349ef  push    r15
0x1800349f1  lea     rbp, [rsp-18h]
0x1800349f6  sub     rsp, 118h
0x1800349fd  mov     rax, cs:__security_cookie
0x180034a04  xor     rax, rsp
0x180034a07  mov     [rbp+50h+var_48], rax
0x180034a0b  mov     rbx, [rbp+50h+arg_20]
0x180034a12  mov     rdi, rdx
0x180034a15  mov     r15d, r8d
0x180034a18  xor     r14d, r14d
0x180034a1b  mov     [rbp+50h+TokenHandle], rcx
0x180034a1f  xor     esi, esi
0x180034a21  xor     r8d, r8d
0x180034a24  mov     [rsp+150h+var_E8], r15d
0x180034a29  xor     edx, edx
0x180034a2b  mov     [rbp+50h+var_98], rbx
0x180034a2f  mov     ecx, 6801h; unsigned int
0x180034a34  mov     qword ptr [rbp+50h+var_D0.Data1], r14
0x180034a38  mov     dword ptr [rsp+150h+var_D8], esi
0x180034a3c  mov     r13, r9
0x180034a3f  mov     [rsp+150h+var_E0], r9
0x180034a44  mov     dword ptr [rbp+50h+var_D0.Data4], 0
0x180034a4b  call    GetBCryptProviderHandle
0x180034a50  mov     [rbp+50h+hAlgorithm], rax
0x180034a54  mov     [rbp+50h+phKey], rsi
0x180034a58  mov     [rbp+50h+var_B8], esi
0x180034a5b  test    rdi, rdi
0x180034a5e  jz      loc_180034FBC
0x180034a64  test    r15d, r15d
0x180034a67  jz      loc_180034FBC
0x180034a6d  test    r13, r13
0x180034a70  jz      loc_180034FBC
0x180034a76  test    rbx, rbx
0x180034a79  jz      loc_180034FBC
0x180034a7f  xor     r8d, r8d
0x180034a82  lea     edx, [rsi+1]
0x180034a85  xor     ebx, ebx
0x180034a87  mov     [rsp+150h+var_F0], r8d
0x180034a8c  xor     r12d, r12d
0x180034a8f  mov     [rsp+150h+var_EC], edx
0x180034a93  mov     dword ptr [rbp+50h+var_D0.Data4+4], ebx
0x180034a96  lea     ecx, [rsi+14h]
0x180034a99  test    rax, rax
0x180034a9c  jz      loc_180034F06
0x180034aa2  mov     edx, r15d; uBytes
0x180034aa5  mov     [r13+0], rbx
0x180034aa9  xor     ecx, ecx; uFlags
0x180034aab  call    cs:__imp_LocalAlloc
0x180034ab2  nop     dword ptr [rax+rax+00h]
0x180034ab7  mov     r12, rax
0x180034aba  test    rax, rax
0x180034abd  jnz     short loc_180034AC9
0x180034abf  mov     ecx, 46Ah
0x180034ac4  jmp     loc_180034FC1
0x180034ac9  mov     r8, r15; Size
0x180034acc  mov     rdx, rdi; Src
0x180034acf  mov     rcx, r12; void *
0x180034ad2  call    memcpy_0
0x180034ad7  cmp     r15d, 94h
0x180034ade  jb      loc_180034FBC
0x180034ae4  cmp     dword ptr [rdi], 1
0x180034ae7  jnz     loc_180034FBC
0x180034aed  mov     ecx, [rdi+8]
0x180034af0  lea     rax, [r15-60h]
0x180034af4  cmp     rcx, rax
0x180034af7  jnz     loc_180034FBC
0x180034afd  cmp     [rdi+4], ecx
0x180034b00  ja      loc_180034FBC
0x180034b06  mov     rax, qword ptr cs:?g_guidW2KPreferredKey@BeforeKeyRotation@@3U_GUID@@A.Data1; _GUID BeforeKeyRotation::g_guidW2KPreferredKey ...
0x180034b0d  lea     rcx, [rdi+0Ch]; this
0x180034b11  cmp     rax, [rcx]
0x180034b14  jnz     short loc_180034B37
0x180034b16  mov     rax, qword ptr cs:?g_guidW2KPreferredKey@BeforeKeyRotation@@3U_GUID@@A.Data4; _GUID BeforeKeyRotation::g_guidW2KPreferredKey ...
0x180034b1d  cmp     rax, [rcx+8]
0x180034b21  jnz     short loc_180034B37
0x180034b23  mov     r14, qword ptr cs:?g_pbW2KPreferredKey@BeforeKeyRotation@@3PEAEEA.Data1; uchar * BeforeKeyRotation::g_pbW2KPreferredKey ...
0x180034b2a  mov     edx, 1
0x180034b2f  mov     esi, cs:?g_cbW2KPreferredKey@BeforeKeyRotation@@3KA; ulong BeforeKeyRotation::g_cbW2KPreferredKey
0x180034b35  jmp     short loc_180034B85
0x180034b37  xor     r9d, r9d; unsigned int *
0x180034b3a  lea     r8, [rsp+150h+var_D8]; unsigned __int8 **
0x180034b3f  lea     rdx, [rbp+50h+var_D0]; struct _GUID *
0x180034b43  call    ?GetBackupKey@BeforeKeyRotation@@YAHPEAU_GUID@@PEAPEAEPEAKPEAPEAX@Z; BeforeKeyRotation::GetBackupKey(_GUID *,uchar * *,ulong *,void * *)
0x180034b48  test    eax, eax
0x180034b4a  jnz     short loc_180034B7B
0x180034b4c  mov     r9d, 159Fh
0x180034b52  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180034b59  lea     rdx, aEFail; "E_FAIL"
0x180034b60  mov     ecx, 80004005h
0x180034b65  call    DebugTraceError
0x180034b6a  mov     edx, [rsp+150h+var_EC]
0x180034b6e  mov     r14, qword ptr [rbp+50h+var_D0.Data1]
0x180034b72  mov     esi, dword ptr [rsp+150h+var_D8]
0x180034b76  jmp     loc_180034EFB
0x180034b7b  mov     r14, qword ptr [rbp+50h+var_D0.Data1]
0x180034b7f  xor     edx, edx
0x180034b81  mov     esi, dword ptr [rsp+150h+var_D8]
0x180034b85  cmp     dword ptr [r14], 1
0x180034b89  mov     r13, rdi
0x180034b8c  mov     [rsp+150h+var_EC], edx
0x180034b90  jnz     loc_180034EF6
0x180034b96  mov     eax, ebx
0x180034b98  mov     [rsp+150h+var_100], 14h; unsigned int
0x180034ba0  lea     r8, [rbp+50h+pbOutput]
0x180034ba4  mov     qword ptr [rsp+150h+var_108], r8; pbOutput
0x180034ba9  lea     ecx, [rsi-4]
0x180034bac  mov     dword ptr [rsp+150h+pcbResult], ebx; cbHashObject
0x180034bb0  lea     r9, [r14+4]; pbSecret
0x180034bb4  test    eax, eax
0x180034bb6  mov     qword ptr [rsp+150h+cbOutput], rbx; pbHashObject
0x180034bbb  mov     [rsp+150h+dwFlags], 44h ; 'D'; cbInput
0x180034bc3  mov     r8d, 8009h; unsigned int
0x180034bc9  cmovnz  r13, r12
0x180034bcd  xor     edx, edx; hHash
0x180034bcf  mov     qword ptr [rbp+50h+var_D0.Data1], r13
0x180034bd3  lea     rax, [r13+1Ch]
0x180034bd7  mov     qword ptr [rsp+150h+cbSecret], rax; pbInput
0x180034bdc  mov     dword ptr [rsp+150h+pbSecret], ecx; ULONG
0x180034be0  xor     ecx, ecx; hAlgorithm
0x180034be2  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180034be7  test    eax, eax
0x180034be9  jz      loc_180034EEB
0x180034bef  mov     rcx, [rbp+50h+hAlgorithm]; hAlgorithm
0x180034bf3  lea     rax, [rbp+50h+pbOutput]
0x180034bf7  mov     [rsp+150h+dwFlags], ebx; dwFlags
0x180034bfb  lea     rdx, [rbp+50h+phKey]; phKey
0x180034bff  mov     [rsp+150h+cbSecret], 14h; cbSecret
0x180034c07  xor     r9d, r9d; cbKeyObject
0x180034c0a  xor     r8d, r8d; pbKeyObject
0x180034c0d  mov     [rsp+150h+pbSecret], rax; pbSecret
0x180034c12  call    cs:__imp_BCryptGenerateSymmetricKey
0x180034c19  nop     dword ptr [rax+rax+00h]
0x180034c1e  test    eax, eax
0x180034c20  js      loc_180034D09
0x180034c26  mov     rcx, qword ptr [rbp+50h+var_D0.Data1]
0x180034c2a  lea     rax, [rbp+50h+var_B8]
0x180034c2e  mov     [rsp+150h+var_108], ebx; dwFlags
0x180034c32  add     r13, 60h ; '`'
0x180034c36  mov     [rsp+150h+pcbResult], rax; pcbResult
0x180034c3b  xor     r9d, r9d; pPaddingInfo
0x180034c3e  mov     rdx, r13; pbInput
0x180034c41  mov     r8d, [rcx+8]; cbInput
0x180034c45  mov     rcx, [rbp+50h+phKey]; hKey
0x180034c49  mov     [rsp+150h+cbOutput], r8d; cbOutput
0x180034c4e  mov     qword ptr [rsp+150h+dwFlags], r13; pbOutput
0x180034c53  mov     [rsp+150h+cbSecret], ebx; cbIV
0x180034c57  mov     [rsp+150h+pbSecret], rbx; pbIV
0x180034c5c  call    cs:__imp_BCryptDecrypt
0x180034c63  nop     dword ptr [rax+rax+00h]
0x180034c68  mov     rcx, [rbp+50h+phKey]; hKey
0x180034c6c  test    eax, eax
0x180034c6e  js      loc_180034EDA
0x180034c74  call    cs:__imp_BCryptDestroyKey
0x180034c7b  nop     dword ptr [rax+rax+00h]
0x180034c80  mov     [rsp+150h+var_100], 14h; unsigned int
0x180034c88  lea     rax, [rbp+50h+var_60]
0x180034c8c  mov     qword ptr [rsp+150h+var_108], rax; pbOutput
0x180034c91  lea     r9, [r14+4]; pbSecret
0x180034c95  mov     dword ptr [rsp+150h+pcbResult], ebx; cbHashObject
0x180034c99  lea     eax, [rsi-4]
0x180034c9c  mov     qword ptr [rsp+150h+cbOutput], rbx; pbHashObject
0x180034ca1  xor     edx, edx; hHash
0x180034ca3  mov     [rsp+150h+dwFlags], 20h ; ' '; cbInput
0x180034cab  xor     ecx, ecx; hAlgorithm
0x180034cad  mov     qword ptr [rsp+150h+cbSecret], r13; pbInput
0x180034cb2  mov     r8d, 8009h; unsigned int
0x180034cb8  mov     dword ptr [rsp+150h+pbSecret], eax; ULONG
0x180034cbc  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180034cc1  test    eax, eax
0x180034cc3  jz      loc_180034ECF
0x180034cc9  lea     rax, [r13+34h]
0x180034ccd  mov     rcx, rax; pSid
0x180034cd0  mov     [rbp+50h+SidToCheck], rax
0x180034cd4  call    cs:__imp_IsValidSid
0x180034cdb  nop     dword ptr [rax+rax+00h]
0x180034ce0  test    eax, eax
0x180034ce2  jnz     short loc_180034D1C
0x180034ce4  mov     eax, esi
0x180034ce6  sub     rax, 4
0x180034cea  cmp     rax, 40h ; '@'
0x180034cee  jbe     short loc_180034D04
0x180034cf0  mov     r13, qword ptr [rbp+50h+var_D0.Data1]
0x180034cf4  mov     eax, esi
0x180034cf6  mov     [rsp+150h+var_F0], eax
0x180034cfa  mov     esi, 44h ; 'D'
0x180034cff  jmp     loc_180034B98
0x180034d04  mov     ebx, 539h
0x180034d09  mov     r13, [rsp+150h+var_E0]
0x180034d0e  mov     edx, [rsp+150h+var_EC]
0x180034d12  mov     r8d, [rsp+150h+var_F0]
0x180034d17  jmp     loc_180034EFE
0x180034d1c  lea     rcx, [r13+34h]; pSid
0x180034d20  call    cs:__imp_GetLengthSid
0x180034d27  nop     dword ptr [rax+rax+00h]
0x180034d2c  mov     dword ptr [rsp+150h+var_D8], eax
0x180034d30  mov     edx, 14h
0x180034d35  mov     rax, qword ptr [rbp+50h+var_D0.Data1]
0x180034d39  lea     r9, [rbp+50h+var_60]; pbSecret
0x180034d3d  mov     [rsp+150h+var_100], edx; unsigned int
0x180034d41  mov     r8d, 8009h; unsigned int
0x180034d47  mov     ecx, [rax+8]
0x180034d4a  lea     rax, [rbp+50h+var_90]
0x180034d4e  mov     qword ptr [rsp+150h+var_108], rax; pbOutput
0x180034d53  sub     ecx, 34h ; '4'
0x180034d56  mov     dword ptr [rsp+150h+pcbResult], ebx; cbHashObject
0x180034d5a  lea     rax, [r13+34h]
0x180034d5e  mov     qword ptr [rsp+150h+cbOutput], rbx; pbHashObject
0x180034d63  mov     [rsp+150h+dwFlags], ecx; cbInput
0x180034d67  xor     ecx, ecx; hAlgorithm
0x180034d69  mov     qword ptr [rsp+150h+cbSecret], rax; pbInput
0x180034d6e  mov     dword ptr [rsp+150h+pbSecret], edx; ULONG
0x180034d72  xor     edx, edx; hHash
0x180034d74  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180034d79  test    eax, eax
0x180034d7b  jnz     short loc_180034DA0
0x180034d7d  mov     r9d, 1633h
0x180034d83  lea     rdx, aEFail; "E_FAIL"
0x180034d8a  mov     ecx, 80004005h
0x180034d8f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180034d96  call    DebugTraceError
0x180034d9b  jmp     loc_180034D09
0x180034da0  mov     rax, [r13+20h]
0x180034da4  cmp     rax, qword ptr [rbp+50h+var_90]
0x180034da8  jnz     loc_180034EC4
0x180034dae  mov     rax, [r13+28h]
0x180034db2  cmp     rax, [rbp+50h+var_88]
0x180034db6  jnz     loc_180034EC4
0x180034dbc  mov     eax, [r13+30h]
0x180034dc0  cmp     eax, [rbp+50h+var_80]
0x180034dc3  jnz     loc_180034EC4
0x180034dc9  mov     r13, [rbp+50h+SidToCheck]
0x180034dcd  lea     r8, [rbp+50h+var_D0.Data4]; IsMember
0x180034dd1  mov     rcx, [rbp+50h+TokenHandle]; TokenHandle
0x180034dd5  mov     rdx, r13; SidToCheck
0x180034dd8  call    cs:__imp_CheckTokenMembership
0x180034ddf  nop     dword ptr [rax+rax+00h]
0x180034de4  test    eax, eax
0x180034de6  jnz     short loc_180034E07
0x180034de8  call    cs:__imp_GetLastError
0x180034def  nop     dword ptr [rax+rax+00h]
0x180034df4  mov     r9d, 164Ah
0x180034dfa  lea     rdx, aDwlasterror; "dwLastError"
0x180034e01  mov     ebx, eax
0x180034e03  mov     ecx, eax
0x180034e05  jmp     short loc_180034D8F
0x180034e07  cmp     dword ptr [rbp+50h+var_D0.Data4], ebx
0x180034e0a  jnz     short loc_180034E25
0x180034e0c  mov     r9d, 1651h
0x180034e12  mov     ecx, 0Ch
0x180034e17  lea     rdx, aDwlasterror; "dwLastError"
0x180034e1e  mov     ebx, ecx
0x180034e20  jmp     loc_180034D8F
0x180034e25  mov     rcx, qword ptr [rbp+50h+var_D0.Data1]
0x180034e29  mov     eax, dword ptr [rsp+150h+var_D8]
0x180034e2d  sub     r15, rax
0x180034e30  sub     r15, 94h
0x180034e37  mov     edx, [rcx+4]; uBytes
0x180034e3a  cmp     rdx, r15
0x180034e3d  jz      short loc_180034E77
0x180034e3f  mov     ebx, 57h ; 'W'
0x180034e44  mov     r9d, 1660h
0x180034e4a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180034e51  mov     ecx, ebx
0x180034e53  lea     rdx, aDwlasterror; "dwLastError"
0x180034e5a  call    DebugTraceError
0x180034e5f  mov     r13, [rsp+150h+var_E0]
0x180034e64  mov     r15d, [rsp+150h+var_E8]
0x180034e69  mov     edx, [rsp+150h+var_EC]
0x180034e6d  mov     r8d, [rsp+150h+var_F0]
0x180034e72  jmp     loc_180034F01
0x180034e77  mov     r15, [rbp+50h+var_98]
0x180034e7b  xor     ecx, ecx; uFlags
0x180034e7d  mov     [r15], edx
0x180034e80  call    cs:__imp_LocalAlloc
0x180034e87  nop     dword ptr [rax+rax+00h]
0x180034e8c  mov     rcx, [rsp+150h+var_E0]
0x180034e91  mov     [rcx], rax
0x180034e94  test    rax, rax
0x180034e97  jnz     short loc_180034EA9
0x180034e99  mov     [r15], ebx
0x180034e9c  mov     r9d, 166Fh
0x180034ea2  mov     ebx, 46Ah
0x180034ea7  jmp     short loc_180034E4A
0x180034ea9  mov     edx, dword ptr [rsp+150h+var_D8]
0x180034ead  mov     rcx, rax; void *
0x180034eb0  mov     r8d, [r15]; Size
0x180034eb3  add     rdx, r13; Src
0x180034eb6  call    memcpy_0
0x180034ebb  mov     dword ptr [rbp+50h+var_D0.Data4+4], 1
0x180034ec2  jmp     short loc_180034E5F
0x180034ec4  mov     r9d, 163Eh
0x180034eca  jmp     loc_180034E12
0x180034ecf  mov     r9d, 1601h
  ... truncated ...
```
