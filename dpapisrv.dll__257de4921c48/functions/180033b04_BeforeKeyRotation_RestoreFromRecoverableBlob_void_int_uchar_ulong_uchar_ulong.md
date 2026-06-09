# BeforeKeyRotation::RestoreFromRecoverableBlob(void *,int,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180033b04`
- end: `0x180034424`
- name: `?RestoreFromRecoverableBlob@BeforeKeyRotation@@YAHPEAXHPEAEKPEAPEAEPEAK@Z`
- size: `2336`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, void *, _BYTE *, unsigned __int8 *, HLOCAL *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035dd4`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x18000c4a0`
- `0x18001d810`
- `0x18003048c`
- `0x180032218`
- `0x180033b04`
- `0x180036a18`
- `0x18003b41c`
- `0x18003c620`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800341d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800341d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800341ac`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800341ac`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180034207`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180034207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034275`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800343b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800343ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800343b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800343ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033bb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003429a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033bb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003429a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180033f4d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003405a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180033f4d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003405a`
- `bcrypt!BCryptDecrypt` at `0x180033d4a`
- `bcrypt!BCryptDecrypt` at `0x180033fc8`
- `bcrypt!BCryptDecrypt` at `0x1800340ba`
- `bcrypt!BCryptDecrypt` at `0x180033d4a`
- `bcrypt!BCryptDecrypt` at `0x180033fc8`
- `bcrypt!BCryptDecrypt` at `0x1800340ba`
- `bcrypt!BCryptDestroyKey` at `0x180033fdb`
- `bcrypt!BCryptDestroyKey` at `0x1800340cd`
- `bcrypt!BCryptDestroyKey` at `0x18003437e`
- `bcrypt!BCryptDestroyKey` at `0x180033fdb`
- `bcrypt!BCryptDestroyKey` at `0x1800340cd`
- `bcrypt!BCryptDestroyKey` at `0x18003437e`
- `ntdll!RtlNtStatusToDosError` at `0x180033d79`
- `ntdll!RtlNtStatusToDosError` at `0x180033d79`

## string_xrefs

- `0x180033c98`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033cd6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033d62`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033e12`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033e89`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033f19`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033f66`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800342fb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::RestoreFromRecoverableBlob(
        BeforeKeyRotation *this,
        void *a2,
        _BYTE *a3,
        unsigned __int8 *a4,
        HLOCAL *a5,
        unsigned __int8 **a6)
{
  HLOCAL *v6; // r14
  unsigned int v7; // r15d
  _BYTE *v8; // r12
  size_t v9; // rbx
  _DWORD *v10; // rdi
  unsigned int v11; // r13d
  unsigned int *v12; // rax
  unsigned int *v13; // rsi
  DWORD v14; // ecx
  DWORD LastError; // ebx
  bool v16; // zf
  __int64 v17; // r14
  unsigned int *v18; // r15
  NTSTATUS v19; // eax
  NTSTATUS v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // r10d
  int v25; // r13d
  int v26; // edx
  __int64 v27; // r9
  unsigned __int64 v28; // rcx
  char *pbOutput; // rdi
  UCHAR *v30; // r14
  ULONG cbOutput; // r12d
  void *BCryptProviderHandle; // rax
  __int64 v33; // r9
  DWORD v34; // eax
  __int64 v35; // rcx
  NTSTATUS v36; // r14d
  __int64 v37; // r9
  ULONG v38; // r12d
  void *v39; // rax
  size_t v40; // r12
  unsigned __int64 v41; // r14
  __int64 v42; // rcx
  char *v43; // r14
  unsigned int *v44; // r12
  unsigned int v45; // eax
  _DWORD *v46; // rax
  void *v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rdx
  _BYTE *v50; // rax
  __int64 v51; // rax
  _BYTE *v52; // rdx
  _BYTE v54[12]; // [rsp+54h] [rbp-ACh] BYREF
  struct _GUID v55; // [rsp+60h] [rbp-A0h] BYREF
  ULONG cbInput; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v57; // [rsp+74h] [rbp-8Ch]
  int v58; // [rsp+78h] [rbp-88h]
  ULONG pcbResult; // [rsp+7Ch] [rbp-84h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp-78h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+90h] [rbp-70h] BYREF
  int v63; // [rsp+98h] [rbp-68h]
  UCHAR *v64; // [rsp+A0h] [rbp-60h]
  size_t v65; // [rsp+A8h] [rbp-58h]
  unsigned int *v66; // [rsp+B0h] [rbp-50h]
  void *Src; // [rsp+B8h] [rbp-48h]
  __int64 v68; // [rsp+C0h] [rbp-40h]
  HANDLE TokenHandle; // [rsp+C8h] [rbp-38h]
  UCHAR pbIV[16]; // [rsp+D0h] [rbp-30h] BYREF
  UCHAR Buf1[64]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = a5;
  v7 = 0;
  v8 = a3;
  v9 = (unsigned int)a4;
  v10 = 0;
  *(_QWORD *)v55.Data4 = a3;
  v11 = 0;
  v63 = (int)a2;
  TokenHandle = this;
  *(_QWORD *)&v54[4] = a5;
  v66 = (unsigned int *)a6;
  IsMember = 0;
  cbInput = 0;
  *(_QWORD *)&v55.Data1 = 0;
  *(_DWORD *)v54 = 0;
  hKey = 0;
  if ( !a3 || !(_DWORD)a4 || !a5 || !a6 || (unsigned int)a4 > 0x7FFFFFFF )
  {
    v14 = 87;
    goto LABEL_116;
  }
  *a5 = 0;
  v68 = (unsigned int)a4;
  v12 = (unsigned int *)LocalAlloc(0, (unsigned int)a4);
  v13 = v12;
  if ( !v12 )
  {
    v14 = 1130;
LABEL_116:
    SetLastError(v14);
    return 0;
  }
  v58 = 1;
  memcpy_0(v12, v8, v9);
  if ( (unsigned int)v9 < 0x1C
    || v13[1] > 0xFFFF
    || v13[2] > 0xFFFF
    || v9 < v13[1] + (unsigned __int64)v13[2] + 28
    || *v13 - 2 > 1 )
  {
    LastError = 87;
    DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 5881);
    v7 = 0;
    goto LABEL_98;
  }
  if ( *(_QWORD *)&BeforeKeyRotation::g_guidPreferredKey.Data1 == *(_QWORD *)(v13 + 3)
    && *(_QWORD *)BeforeKeyRotation::g_guidPreferredKey.Data4 == *(_QWORD *)(v13 + 5) )
  {
    v10 = BeforeKeyRotation::g_pbPreferredKey;
    v11 = (unsigned int)BeforeKeyRotation::g_cbPreferredKey;
    hKey = *(BCRYPT_KEY_HANDLE *)&BeforeKeyRotation::g_hKeyPreferredKey;
    v58 = 1;
  }
  else
  {
    if ( !(unsigned int)BeforeKeyRotation::GetBackupKey(
                          (BeforeKeyRotation *)(v13 + 3),
                          &v55,
                          (unsigned __int8 **)v54,
                          &hKey) )
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 5909);
LABEL_96:
      v10 = *(_DWORD **)&v55.Data1;
      goto LABEL_97;
    }
    v11 = *(_DWORD *)v54;
    v58 = 0;
    v10 = *(_DWORD **)&v55.Data1;
  }
  v16 = *v10 == 2;
  *(_DWORD *)v54 = v11;
  *(_QWORD *)&v55.Data1 = v10;
  if ( !v16 )
  {
    LastError = -2146893821;
    DebugTraceError(
      2148073475LL,
      "dwLastError",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      5925);
    goto LABEL_98;
  }
  v17 = v13[1];
  v18 = v13 + 7;
  cbInput = v13[1];
  FMyReverseBytes((unsigned __int8 *)v13 + 28, cbInput);
  v19 = BCryptDecrypt(hKey, (PUCHAR)v13 + 28, cbInput, 0, 0, 0, (PUCHAR)v13 + 28, cbInput, &cbInput, 2u);
  v20 = v19;
  if ( v19 < 0 )
  {
    DebugTraceError(
      (unsigned int)v19,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      5953);
    LastError = RtlNtStatusToDosError(v20);
LABEL_23:
    v6 = *(HLOCAL **)&v54[4];
    v7 = 0;
    goto LABEL_98;
  }
  if ( *v18 > 0xFFFF || (v21 = v13[8], (unsigned int)v21 > 0xFFFF) )
  {
    LastError = 13;
    goto LABEL_23;
  }
  if ( *v13 == 3 )
  {
    if ( v13[9] != 26128 || v13[10] != 32782 )
    {
      v23 = 5976;
      goto LABEL_35;
    }
    v22 = *v18;
    if ( v22 + v21 + 16 > (unsigned __int64)cbInput )
    {
      v23 = 5985;
LABEL_35:
      LastError = 13;
      DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v23);
      goto LABEL_23;
    }
    if ( (_DWORD)v21 != 48 )
    {
      v23 = 6000;
      goto LABEL_35;
    }
    v24 = 64;
    v25 = 32782;
    v26 = 26128;
    v27 = 4;
  }
  else
  {
    v22 = *v18;
    if ( v22 + v21 + 8 > (unsigned __int64)cbInput )
    {
      v23 = 6013;
      goto LABEL_35;
    }
    if ( (_DWORD)v21 != 32 )
    {
      v23 = 6020;
      goto LABEL_35;
    }
    v24 = 20;
    v26 = 26115;
    v25 = 32777;
    v27 = 2;
  }
  v28 = v13[2];
  v57 = v24;
  v65 = v24;
  if ( v28 >= (unsigned __int64)v24 + 8 )
  {
    LastError = 0;
    Src = &v18[v27];
    pbOutput = (char *)v18 + v17;
    v30 = (UCHAR *)&v18[v27] + v22;
    v64 = v30;
    if ( v26 == 26128 )
    {
      phKey = 0;
      cbOutput = v28 & 0xFFFFFFF0;
      pcbResult = 0;
      if ( (v28 & 0xFFFFFFF0) == (_DWORD)v28 )
      {
        BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6610u);
        if ( !BCryptProviderHandle )
        {
          v33 = 6067;
LABEL_47:
          v34 = 13;
LABEL_48:
          LastError = v34;
          v35 = v34;
LABEL_49:
          DebugTraceError(v35, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v33);
LABEL_50:
          v7 = 0;
LABEL_94:
          v6 = *(HLOCAL **)&v54[4];
          goto LABEL_95;
        }
        v36 = BCryptGenerateSymmetricKey(BCryptProviderHandle, &phKey, 0, 0, v30, 0x20u, 0);
        if ( v36 < 0 )
        {
          v37 = 6081;
LABEL_53:
          DebugTraceError(
            (unsigned int)v36,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            v37);
          LastError = v36 | 0x10000000;
          goto LABEL_50;
        }
        *(_OWORD *)pbIV = *((_OWORD *)v64 + 2);
        v36 = BCryptDecrypt(
                phKey,
                (PUCHAR)pbOutput,
                cbOutput,
                0,
                pbIV,
                0x10u,
                (PUCHAR)pbOutput,
                cbOutput,
                &pcbResult,
                0);
        BCryptDestroyKey(phKey);
        if ( v36 < 0 )
        {
          v37 = 6105;
          goto LABEL_53;
        }
LABEL_63:
        v40 = v65;
        if ( v25 == 32782 )
        {
          if ( !(unsigned int)FMyPrimitiveSHA512((PUCHAR)pbOutput, v13[2] - v57, Buf1) )
          {
            v33 = 6196;
            goto LABEL_47;
          }
        }
        else if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)pbOutput, v13[2] - v57, Buf1) )
        {
          v33 = 6210;
          goto LABEL_47;
        }
        v41 = v13[2];
        if ( memcmp_0(Buf1, &pbOutput[v41 - v40], v40) )
        {
          v33 = 6220;
          goto LABEL_47;
        }
        if ( *(_DWORD *)pbOutput != 1 )
        {
          v33 = 6227;
          goto LABEL_47;
        }
        v42 = *((unsigned int *)pbOutput + 1);
        if ( v40 + v42 + 8 > v41 )
        {
          v33 = 6236;
          goto LABEL_47;
        }
        v43 = &pbOutput[v42 + 8];
        if ( !IsValidSid(v43) )
        {
          LastError = 1337;
          v33 = 6250;
LABEL_76:
          v35 = LastError;
          goto LABEL_49;
        }
        if ( v40 + GetLengthSid(v43) + *((_DWORD *)pbOutput + 1) + 8LL > v13[2] )
        {
          v33 = 6262;
          goto LABEL_47;
        }
        if ( !CheckTokenMembership(TokenHandle, v43, &IsMember) )
        {
          v34 = GetLastError();
          v33 = 6273;
          goto LABEL_48;
        }
        if ( !IsMember )
        {
          LastError = 12;
          v33 = 6279;
          goto LABEL_76;
        }
        v44 = v66;
        if ( v63 )
        {
          if ( !ConvertRecoveredBlobToW2KBlob(
                  (unsigned __int8 *)Src,
                  *v18,
                  (unsigned __int8 *)pbOutput + 8,
                  *((_DWORD *)pbOutput + 1),
                  v43,
                  *(unsigned __int8 ***)&v54[4],
                  v66) )
          {
            v34 = GetLastError();
            v33 = 6296;
            goto LABEL_48;
          }
          v6 = *(HLOCAL **)&v54[4];
        }
        else
        {
          v45 = *v18 + 4;
          *v66 = v45;
          v46 = LocalAlloc(0, v45);
          v6 = *(HLOCAL **)&v54[4];
          **(_QWORD **)&v54[4] = v46;
          if ( !v46 )
          {
            v7 = 0;
            *v44 = 0;
            LastError = 1130;
LABEL_95:
            v8 = *(_BYTE **)v55.Data4;
            goto LABEL_96;
          }
          v47 = Src;
          *v46 = 0;
          memcpy_0((char *)*v6 + 4, v47, *v44 - 4LL);
        }
        v7 = 1;
        goto LABEL_95;
      }
    }
    else
    {
      phKey = 0;
      v38 = v28 & 0xFFFFFFF8;
      pcbResult = 0;
      if ( (v28 & 0xFFFFFFF8) == (_DWORD)v28 )
      {
        v39 = (void *)GetBCryptProviderHandle(0x6603u);
        if ( !v39 )
        {
          v33 = 6137;
          goto LABEL_47;
        }
        v36 = BCryptGenerateSymmetricKey(v39, &phKey, 0, 0, v30, 0x18u, 0);
        if ( v36 < 0 )
        {
          v37 = 6151;
          goto LABEL_53;
        }
        *(_QWORD *)pbIV = *((_QWORD *)v64 + 3);
        v36 = BCryptDecrypt(phKey, (PUCHAR)pbOutput, v38, 0, pbIV, 8u, (PUCHAR)pbOutput, v38, &pcbResult, 0);
        BCryptDestroyKey(phKey);
        if ( v36 < 0 )
        {
          v37 = 6175;
          goto LABEL_53;
        }
        goto LABEL_63;
      }
    }
    v7 = 0;
    goto LABEL_94;
  }
  LastError = 13;
  DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6032);
  v6 = *(HLOCAL **)&v54[4];
  v8 = *(_BYTE **)v55.Data4;
  v7 = 0;
LABEL_97:
  v11 = *(_DWORD *)v54;
LABEL_98:
  v48 = v68;
  do
  {
    *v8++ = 0;
    --v48;
  }
  while ( v48 );
  if ( !v58 && v10 )
  {
    v49 = v11;
    v50 = v10;
    if ( v11 )
    {
      do
      {
        *v50++ = 0;
        --v49;
      }
      while ( v49 );
    }
    LocalFree(v10);
    if ( hKey )
      BCryptDestroyKey(hKey);
  }
  if ( !v7 )
  {
    if ( *v6 )
    {
      LocalFree(*v6);
      *v6 = 0;
    }
    if ( !LastError )
      LastError = 13;
    SetLastError(LastError);
  }
  v51 = v68;
  v52 = v13;
  do
  {
    *v52++ = 0;
    --v51;
  }
  while ( v51 );
  LocalFree(v13);
  return v7;
}

```

## disassembly

```asm
0x180033b04  mov     [rsp-8+arg_8], rbx
0x180033b09  push    rbp
0x180033b0a  push    rsi
0x180033b0b  push    rdi
0x180033b0c  push    r12
0x180033b0e  push    r13
0x180033b10  push    r14
0x180033b12  push    r15
0x180033b14  lea     rbp, [rsp-30h]
0x180033b19  sub     rsp, 130h
0x180033b20  mov     rax, cs:__security_cookie
0x180033b27  xor     rax, rsp
0x180033b2a  mov     [rbp+60h+var_40], rax
0x180033b2e  mov     r14, [rbp+60h+arg_20]
0x180033b35  xor     r15d, r15d
0x180033b38  mov     rax, [rbp+60h+arg_28]
0x180033b3f  mov     r12, r8
0x180033b42  mov     ebx, r9d
0x180033b45  mov     edi, r15d
0x180033b48  mov     qword ptr [rsp+160h+var_100.Data4], r8
0x180033b4d  mov     r13d, r15d
0x180033b50  mov     [rbp+60h+var_C8], edx
0x180033b53  mov     [rbp+60h+TokenHandle], rcx
0x180033b57  mov     qword ptr [rsp+160h+var_10C+4], r14
0x180033b5c  mov     [rbp+60h+var_B0], rax
0x180033b60  mov     [rbp+60h+IsMember], r15d
0x180033b64  mov     [rsp+160h+cbInput], r15d
0x180033b69  mov     qword ptr [rsp+160h+var_100.Data1], r15
0x180033b6e  mov     dword ptr [rsp+160h+var_10C], r15d
0x180033b73  mov     [rbp+60h+hKey], r15
0x180033b77  test    r8, r8
0x180033b7a  jz      loc_1800343E9
0x180033b80  test    r9d, r9d
0x180033b83  jz      loc_1800343E9
0x180033b89  test    r14, r14
0x180033b8c  jz      loc_1800343E9
0x180033b92  test    rax, rax
0x180033b95  jz      loc_1800343E9
0x180033b9b  cmp     ebx, 7FFFFFFFh
0x180033ba1  ja      loc_1800343E9
0x180033ba7  mov     edx, ebx; uBytes
0x180033ba9  mov     [r14], r15
0x180033bac  xor     ecx, ecx; uFlags
0x180033bae  mov     [rbp+60h+var_A0], rbx
0x180033bb2  call    cs:__imp_LocalAlloc
0x180033bb9  nop     dword ptr [rax+rax+00h]
0x180033bbe  mov     rsi, rax
0x180033bc1  test    rax, rax
0x180033bc4  jnz     short loc_180033BD0
0x180033bc6  mov     ecx, 46Ah
0x180033bcb  jmp     loc_1800343EE
0x180033bd0  mov     r8, rbx; Size
0x180033bd3  mov     [rsp+160h+var_E8], 1
0x180033bdb  mov     rdx, r12; Src
0x180033bde  mov     [rsp+160h+var_110], r15d
0x180033be3  mov     rcx, rsi; void *
0x180033be6  call    memcpy_0
0x180033beb  cmp     ebx, 1Ch
0x180033bee  jb      loc_1800342F6
0x180033bf4  mov     eax, 0FFFFh
0x180033bf9  cmp     [rsi+4], eax
0x180033bfc  ja      loc_1800342F6
0x180033c02  cmp     [rsi+8], eax
0x180033c05  ja      loc_1800342F6
0x180033c0b  mov     ecx, [rsi+8]
0x180033c0e  mov     eax, [rsi+4]
0x180033c11  add     rcx, 1Ch
0x180033c15  add     rcx, rax
0x180033c18  cmp     rbx, rcx
0x180033c1b  jb      loc_1800342F6
0x180033c21  mov     eax, [rsi]
0x180033c23  sub     eax, 2
0x180033c26  cmp     eax, 1
0x180033c29  ja      loc_1800342F6
0x180033c2f  mov     rax, qword ptr cs:?g_guidPreferredKey@BeforeKeyRotation@@3U_GUID@@A.Data1; _GUID BeforeKeyRotation::g_guidPreferredKey ...
0x180033c36  lea     rcx, [rsi+0Ch]; this
0x180033c3a  cmp     rax, [rcx]
0x180033c3d  jnz     short loc_180033C6F
0x180033c3f  mov     rax, qword ptr cs:?g_guidPreferredKey@BeforeKeyRotation@@3U_GUID@@A.Data4; _GUID BeforeKeyRotation::g_guidPreferredKey ...
0x180033c46  cmp     rax, [rcx+8]
0x180033c4a  jnz     short loc_180033C6F
0x180033c4c  mov     rax, cs:?g_hKeyPreferredKey@BeforeKeyRotation@@3PEAXEA; void * BeforeKeyRotation::g_hKeyPreferredKey
0x180033c53  mov     rdi, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x180033c5a  mov     r13d, cs:?g_cbPreferredKey@BeforeKeyRotation@@3KA; ulong BeforeKeyRotation::g_cbPreferredKey
0x180033c61  mov     [rbp+60h+hKey], rax
0x180033c65  mov     [rsp+160h+var_E8], 1
0x180033c6d  jmp     short loc_180033CC2
0x180033c6f  lea     r9, [rbp+60h+hKey]; unsigned int *
0x180033c73  lea     r8, [rsp+160h+var_10C]; unsigned __int8 **
0x180033c78  lea     rdx, [rsp+160h+var_100]; struct _GUID *
0x180033c7d  call    ?GetBackupKey@BeforeKeyRotation@@YAHPEAU_GUID@@PEAPEAEPEAKPEAPEAX@Z; BeforeKeyRotation::GetBackupKey(_GUID *,uchar * *,ulong *,void * *)
0x180033c82  test    eax, eax
0x180033c84  jnz     short loc_180033CB4
0x180033c86  call    cs:__imp_GetLastError
0x180033c8d  nop     dword ptr [rax+rax+00h]
0x180033c92  mov     r9d, 1715h
0x180033c98  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033c9f  mov     ecx, eax
0x180033ca1  lea     rdx, aDwlasterror; "dwLastError"
0x180033ca8  mov     ebx, eax
0x180033caa  call    DebugTraceError
0x180033caf  jmp     loc_180034328
0x180033cb4  mov     r13d, dword ptr [rsp+160h+var_10C]
0x180033cb9  mov     [rsp+160h+var_E8], edi
0x180033cbd  mov     rdi, qword ptr [rsp+160h+var_100.Data1]
0x180033cc2  cmp     dword ptr [rdi], 2
0x180033cc5  mov     dword ptr [rsp+160h+var_10C], r13d
0x180033cca  mov     qword ptr [rsp+160h+var_100.Data1], rdi
0x180033ccf  jz      short loc_180033CF6
0x180033cd1  mov     ebx, 80090003h
0x180033cd6  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033cdd  mov     ecx, ebx
0x180033cdf  lea     rdx, aDwlasterror; "dwLastError"
0x180033ce6  mov     r9d, 1725h
0x180033cec  call    DebugTraceError
0x180033cf1  jmp     loc_180034332
0x180033cf6  mov     r14d, [rsi+4]
0x180033cfa  lea     r15, [rsi+1Ch]
0x180033cfe  mov     edx, r14d; unsigned int
0x180033d01  mov     [rsp+160h+cbInput], r14d
0x180033d06  mov     rcx, r15; unsigned __int8 *
0x180033d09  call    ?FMyReverseBytes@@YAXPEAEK@Z; FMyReverseBytes(uchar *,ulong)
0x180033d0e  mov     r8d, [rsp+160h+cbInput]; cbInput
0x180033d13  lea     rax, [rsp+160h+cbInput]
0x180033d18  mov     rcx, [rbp+60h+hKey]; hKey
0x180033d1c  xor     r9d, r9d; pPaddingInfo
0x180033d1f  mov     [rsp+160h+dwFlags], 2; dwFlags
0x180033d27  mov     rdx, r15; pbInput
0x180033d2a  mov     [rsp+160h+pcbResult], rax; pcbResult
0x180033d2f  mov     [rsp+160h+cbOutput], r8d; cbOutput
0x180033d34  mov     [rsp+160h+pbOutput], r15; pbOutput
0x180033d39  mov     [rsp+160h+cbIV], 0; cbIV
0x180033d41  mov     [rsp+160h+pbIV], 0; pbIV
0x180033d4a  call    cs:__imp_BCryptDecrypt
0x180033d51  nop     dword ptr [rax+rax+00h]
0x180033d56  mov     ebx, eax
0x180033d58  test    eax, eax
0x180033d5a  jns     short loc_180033D96
0x180033d5c  mov     r9d, 1741h
0x180033d62  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033d69  lea     rdx, aNtstatus; "ntStatus"
0x180033d70  mov     ecx, eax
0x180033d72  call    DebugTraceError
0x180033d77  mov     ecx, ebx; Status
0x180033d79  call    cs:__imp_RtlNtStatusToDosError
0x180033d80  nop     dword ptr [rax+rax+00h]
0x180033d85  mov     ebx, eax
0x180033d87  mov     r14, qword ptr [rsp+160h+var_10C+4]
0x180033d8c  mov     r15d, [rsp+160h+var_110]
0x180033d91  jmp     loc_180034332
0x180033d96  mov     eax, 0FFFFh
0x180033d9b  cmp     [r15], eax
0x180033d9e  ja      loc_1800342EC
0x180033da4  mov     edx, [r15+4]
0x180033da8  cmp     edx, eax
0x180033daa  ja      loc_1800342EC
0x180033db0  cmp     dword ptr [rsi], 3
0x180033db3  mov     r11d, 6610h
0x180033db9  mov     r9d, 800Eh
0x180033dbf  jnz     short loc_180033E2E
0x180033dc1  cmp     [r15+8], r11d
0x180033dc5  jnz     short loc_180033E07
0x180033dc7  cmp     [r15+0Ch], r9d
0x180033dcb  jnz     short loc_180033E07
0x180033dcd  mov     r8d, [r15]
0x180033dd0  lea     rcx, [rdx+10h]
0x180033dd4  mov     eax, [rsp+160h+cbInput]
0x180033dd8  add     rcx, r8
0x180033ddb  cmp     rcx, rax
0x180033dde  jbe     short loc_180033DE8
0x180033de0  mov     r9d, 1761h
0x180033de6  jmp     short loc_180033E0D
0x180033de8  cmp     edx, 30h ; '0'
0x180033deb  jz      short loc_180033DF5
0x180033ded  mov     r9d, 1770h
0x180033df3  jmp     short loc_180033E0D
0x180033df5  mov     r10d, 40h ; '@'
0x180033dfb  mov     r13d, r9d
0x180033dfe  mov     edx, r11d
0x180033e01  lea     r9d, [r10-30h]
0x180033e05  jmp     short loc_180033E6B
0x180033e07  mov     r9d, 1758h
0x180033e0d  mov     eax, 0Dh
0x180033e12  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033e19  mov     ecx, eax
0x180033e1b  lea     rdx, aDwlasterror; "dwLastError"
0x180033e22  mov     ebx, eax
0x180033e24  call    DebugTraceError
0x180033e29  jmp     loc_180033D87
0x180033e2e  mov     r8d, [r15]
0x180033e31  lea     rcx, [rdx+8]
0x180033e35  mov     eax, [rsp+160h+cbInput]
0x180033e39  add     rcx, r8
0x180033e3c  cmp     rcx, rax
0x180033e3f  jbe     short loc_180033E49
0x180033e41  mov     r9d, 177Dh
0x180033e47  jmp     short loc_180033E0D
0x180033e49  cmp     edx, 20h ; ' '
0x180033e4c  jz      short loc_180033E56
0x180033e4e  mov     r9d, 1784h
0x180033e54  jmp     short loc_180033E0D
0x180033e56  mov     r10d, 14h
0x180033e5c  mov     edx, 6603h
0x180033e61  mov     r13d, 8009h
0x180033e67  lea     r9d, [r10-0Ch]
0x180033e6b  mov     ecx, [rsi+8]
0x180033e6e  mov     r12d, r10d
0x180033e71  mov     [rsp+160h+var_EC], r10d
0x180033e76  mov     [rbp+60h+var_B8], r12
0x180033e7a  lea     rax, [r12+8]
0x180033e7f  cmp     rcx, rax
0x180033e82  jnb     short loc_180033EBA
0x180033e84  mov     eax, 0Dh
0x180033e89  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033e90  mov     ecx, eax
0x180033e92  lea     rdx, aDwlasterror; "dwLastError"
0x180033e99  mov     r9d, 1790h
0x180033e9f  mov     ebx, eax
0x180033ea1  call    DebugTraceError
0x180033ea6  mov     r14, qword ptr [rsp+160h+var_10C+4]
0x180033eab  mov     r12, qword ptr [rsp+160h+var_100.Data4]
0x180033eb0  mov     r15d, [rsp+160h+var_110]
0x180033eb5  jmp     loc_18003432D
0x180033eba  lea     rax, [r15+r9]
0x180033ebe  xor     ebx, ebx
0x180033ec0  mov     [rbp+60h+Src], rax
0x180033ec4  lea     rdi, [r15+r14]
0x180033ec8  lea     r14, [rax+r8]
0x180033ecc  mov     [rbp+60h+var_C0], r14
0x180033ed0  cmp     edx, r11d
0x180033ed3  jnz     loc_180033FFB
0x180033ed9  mov     r12d, ecx
0x180033edc  mov     [rbp+60h+phKey], rbx
0x180033ee0  and     r12d, 0FFFFFFF0h
0x180033ee4  mov     [rsp+160h+var_E4], ebx
0x180033ee8  cmp     r12d, ecx
0x180033eeb  jnz     loc_18003431B
0x180033ef1  xor     r8d, r8d
0x180033ef4  xor     edx, edx
0x180033ef6  mov     ecx, r11d; unsigned int
0x180033ef9  call    GetBCryptProviderHandle
0x180033efe  test    rax, rax
0x180033f01  jnz     short loc_180033F2F
0x180033f03  mov     r9d, 17B3h
0x180033f09  mov     eax, 0Dh
0x180033f0e  mov     ebx, eax
0x180033f10  mov     ecx, eax
0x180033f12  lea     rdx, aDwlasterror; "dwLastError"
0x180033f19  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033f20  call    DebugTraceError
0x180033f25  mov     r15d, [rsp+160h+var_110]
0x180033f2a  jmp     loc_18003431E
0x180033f2f  mov     dword ptr [rsp+160h+pbOutput], ebx; dwFlags
0x180033f33  lea     rdx, [rbp+60h+phKey]; phKey
0x180033f37  mov     [rsp+160h+cbIV], 20h ; ' '; cbSecret
0x180033f3f  xor     r9d, r9d; cbKeyObject
0x180033f42  xor     r8d, r8d; pbKeyObject
0x180033f45  mov     [rsp+160h+pbIV], r14; pbSecret
0x180033f4a  mov     rcx, rax; hAlgorithm
0x180033f4d  call    cs:__imp_BCryptGenerateSymmetricKey
0x180033f54  nop     dword ptr [rax+rax+00h]
0x180033f59  mov     r14d, eax
0x180033f5c  test    eax, eax
0x180033f5e  jns     short loc_180033F85
0x180033f60  mov     r9d, 17C1h
0x180033f66  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033f6d  mov     ecx, r14d
0x180033f70  lea     rdx, aNtstatus; "ntStatus"
0x180033f77  call    DebugTraceError
0x180033f7c  mov     ebx, r14d
0x180033f7f  bts     ebx, 1Ch
0x180033f83  jmp     short loc_180033F25
0x180033f85  mov     rax, [rbp+60h+var_C0]
0x180033f89  xor     r9d, r9d; pPaddingInfo
0x180033f8c  mov     rcx, [rbp+60h+phKey]; hKey
0x180033f90  mov     r8d, r12d; cbInput
0x180033f93  mov     [rsp+160h+dwFlags], ebx; dwFlags
0x180033f97  mov     rdx, rdi; pbInput
0x180033f9a  movups  xmm0, xmmword ptr [rax+20h]
0x180033f9e  lea     rax, [rsp+160h+var_E4]
0x180033fa3  mov     [rsp+160h+pcbResult], rax; pcbResult
0x180033fa8  lea     rax, [rbp+60h+var_90]
0x180033fac  mov     [rsp+160h+cbOutput], r12d; cbOutput
0x180033fb1  mov     [rsp+160h+pbOutput], rdi; pbOutput
0x180033fb6  mov     [rsp+160h+cbIV], 10h; cbIV
0x180033fbe  mov     [rsp+160h+pbIV], rax; pbIV
0x180033fc3  movdqu  xmmword ptr [rbp+60h+var_90], xmm0
0x180033fc8  call    cs:__imp_BCryptDecrypt
0x180033fcf  nop     dword ptr [rax+rax+00h]
0x180033fd4  mov     rcx, [rbp+60h+phKey]; hKey
0x180033fd8  mov     r14d, eax
0x180033fdb  call    cs:__imp_BCryptDestroyKey
0x180033fe2  nop     dword ptr [rax+rax+00h]
0x180033fe7  test    r14d, r14d
0x180033fea  jns     loc_1800340E9
0x180033ff0  mov     r9d, 17D9h
0x180033ff6  jmp     loc_180033F66
0x180033ffb  mov     eax, 6603h
0x180034000  cmp     edx, eax
0x180034002  jnz     loc_1800340F2
  ... truncated ...
```
