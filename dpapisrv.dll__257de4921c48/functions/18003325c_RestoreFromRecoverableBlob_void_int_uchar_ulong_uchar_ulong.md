# RestoreFromRecoverableBlob(void *,int,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18003325c`
- end: `0x180033afe`
- name: `?RestoreFromRecoverableBlob@@YAHPEAXHPEAEKPEAPEAEPEAK@Z`
- size: `2210`
- prototype: `__int64 __fastcall(void *, int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800362c0`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x18000c4a0`
- `0x18001d810`
- `0x18003048c`
- `0x180032084`
- `0x18003325c`
- `0x180036a18`
- `0x18003b41c`
- `0x18003c620`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800338be`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800338be`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180033886`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180033886`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800338f4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800338f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003339d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003339d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033981`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033a94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033ac8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033a94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033ac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ab2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800339a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800339a3`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180033608`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180033726`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180033608`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180033726`
- `bcrypt!BCryptDecrypt` at `0x180033416`
- `bcrypt!BCryptDecrypt` at `0x180033691`
- `bcrypt!BCryptDecrypt` at `0x180033787`
- `bcrypt!BCryptDecrypt` at `0x180033416`
- `bcrypt!BCryptDecrypt` at `0x180033691`
- `bcrypt!BCryptDecrypt` at `0x180033787`
- `bcrypt!BCryptDestroyKey` at `0x1800336a5`
- `bcrypt!BCryptDestroyKey` at `0x18003379b`
- `bcrypt!BCryptDestroyKey` at `0x180033a61`
- `bcrypt!BCryptDestroyKey` at `0x1800336a5`
- `bcrypt!BCryptDestroyKey` at `0x18003379b`
- `bcrypt!BCryptDestroyKey` at `0x180033a61`
- `ntdll!RtlNtStatusToDosError` at `0x180033445`
- `ntdll!RtlNtStatusToDosError` at `0x180033445`

## string_xrefs

- `0x18003342e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800334d5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033548`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800335c8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033621`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18003389b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033924`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180033a19`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall RestoreFromRecoverableBlob(
        void *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  HLOCAL *v6; // r14
  unsigned int v7; // r13d
  size_t v9; // rbx
  __int64 v10; // r15
  unsigned int *v11; // rax
  unsigned int *v12; // rdi
  DWORD v13; // ecx
  DWORD LastError; // ebx
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rsi
  unsigned int *v18; // r15
  NTSTATUS v19; // eax
  NTSTATUS v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // r10d
  int v25; // edx
  __int64 v26; // r9
  unsigned __int64 v27; // rcx
  size_t v28; // r13
  char *pbOutput; // rsi
  UCHAR *v30; // r14
  ULONG cbOutput; // r12d
  void *BCryptProviderHandle; // rax
  __int64 v33; // r9
  NTSTATUS v34; // r14d
  __int64 v35; // r9
  ULONG v36; // r12d
  void *v37; // rax
  unsigned int *v38; // r12
  unsigned __int64 v39; // r14
  __int64 v40; // rcx
  char *v41; // r14
  DWORD v42; // eax
  __int64 v43; // r9
  __int64 v44; // rcx
  unsigned int v45; // eax
  unsigned __int8 *v46; // rax
  void *v47; // rdx
  HLOCAL v48; // rcx
  __int64 v49; // rax
  _BYTE *v50; // rdx
  _BYTE *v51; // rcx
  __int64 v53; // [rsp+58h] [rbp-A8h]
  ULONG cbInput; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v55; // [rsp+6Ch] [rbp-94h]
  ULONG pcbResult; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp-88h] BYREF
  int v58; // [rsp+80h] [rbp-80h]
  WINBOOL IsMember; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v60; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+8Ch] [rbp-74h]
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+98h] [rbp-68h] BYREF
  UCHAR *v64; // [rsp+A0h] [rbp-60h]
  unsigned int *v65; // [rsp+A8h] [rbp-58h]
  void *Src; // [rsp+B0h] [rbp-50h]
  HANDLE TokenHandle; // [rsp+B8h] [rbp-48h]
  UCHAR pbIV[16]; // [rsp+C0h] [rbp-40h] BYREF
  UCHAR Buf1[64]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = (HLOCAL *)a5;
  v7 = 0;
  v9 = a4;
  v61 = a2;
  TokenHandle = a1;
  v65 = a6;
  IsMember = 0;
  cbInput = 0;
  hMem = 0;
  v60 = 0;
  hKey = 0;
  if ( !a3 || !a4 || !a5 || !a6 || a4 > 0x7FFFFFFF )
  {
    v13 = 87;
    goto LABEL_109;
  }
  *a5 = 0;
  v53 = a4;
  v10 = a4;
  v11 = (unsigned int *)LocalAlloc(0, a4);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 1130;
LABEL_109:
    SetLastError(v13);
    return 0;
  }
  memcpy_0(v11, a3, v9);
  if ( (unsigned int)v9 < 0x1C
    || v12[1] > 0xFFFF
    || v12[2] > 0xFFFF
    || v9 < v12[1] + (unsigned __int64)v12[2] + 28
    || *v12 - 2 > 1 )
  {
    LastError = 87;
    v16 = 1426;
    goto LABEL_92;
  }
  if ( !(unsigned int)GetBackupKey(2u, (const struct _GUID *)(v12 + 3), (unsigned __int8 **)&hMem, &v60, &hKey) )
  {
    LastError = GetLastError();
    v15 = LastError;
    v16 = 1433;
LABEL_93:
    DebugTraceError(v15, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v16);
    goto LABEL_94;
  }
  if ( *(_DWORD *)hMem != 2 )
  {
    LastError = -2146893821;
    v16 = 1445;
LABEL_92:
    v15 = LastError;
    goto LABEL_93;
  }
  v17 = v12[1];
  v18 = v12 + 7;
  cbInput = v12[1];
  FMyReverseBytes((unsigned __int8 *)v12 + 28, cbInput);
  v19 = BCryptDecrypt(hKey, (PUCHAR)v12 + 28, cbInput, 0, 0, 0, (PUCHAR)v12 + 28, cbInput, &cbInput, 2u);
  v20 = v19;
  if ( v19 < 0 )
  {
    DebugTraceError(
      (unsigned int)v19,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      1473);
    LastError = RtlNtStatusToDosError(v20);
LABEL_88:
    v10 = v53;
    goto LABEL_94;
  }
  if ( *v18 > 0xFFFF || (v21 = v12[8], (unsigned int)v21 > 0xFFFF) )
  {
    LastError = 13;
    goto LABEL_90;
  }
  if ( *v12 == 3 )
  {
    if ( v12[9] != 26128 || v12[10] != 32782 )
    {
      v23 = 1496;
      goto LABEL_30;
    }
    v22 = *v18;
    if ( v22 + v21 + 16 > (unsigned __int64)cbInput )
    {
      v23 = 1505;
LABEL_30:
      LastError = 13;
      DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v23);
LABEL_90:
      v10 = v53;
      goto LABEL_94;
    }
    if ( (_DWORD)v21 != 48 )
    {
      v23 = 1520;
      goto LABEL_30;
    }
    v24 = 64;
    v58 = 32782;
    v25 = 26128;
    v26 = 4;
  }
  else
  {
    v22 = *v18;
    if ( v22 + v21 + 8 > (unsigned __int64)cbInput )
    {
      v23 = 1533;
      goto LABEL_30;
    }
    if ( (_DWORD)v21 != 32 )
    {
      v23 = 1540;
      goto LABEL_30;
    }
    v24 = 20;
    v58 = 32777;
    v25 = 26115;
    v26 = 2;
  }
  v27 = v12[2];
  v28 = v24;
  v55 = v24;
  if ( v27 >= (unsigned __int64)v24 + 8 )
  {
    LastError = 0;
    pbOutput = (char *)v18 + v17;
    Src = &v18[v26];
    v30 = (UCHAR *)&v18[v26] + v22;
    v64 = v30;
    if ( v25 == 26128 )
    {
      phKey = 0;
      cbOutput = v27 & 0xFFFFFFF0;
      pcbResult = 0;
      if ( (v27 & 0xFFFFFFF0) == (_DWORD)v27 )
      {
        BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6610u);
        if ( !BCryptProviderHandle )
        {
          v33 = 1587;
LABEL_43:
          LastError = 13;
          DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v33);
          v6 = (HLOCAL *)a5;
          goto LABEL_38;
        }
        v34 = BCryptGenerateSymmetricKey(BCryptProviderHandle, &phKey, 0, 0, v30, 0x20u, 0);
        if ( v34 < 0 )
        {
          v35 = 1601;
LABEL_46:
          DebugTraceError(
            (unsigned int)v34,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            v35);
          LastError = v34 | 0x10000000;
LABEL_47:
          v6 = (HLOCAL *)a5;
          v7 = 0;
          goto LABEL_88;
        }
        *(_OWORD *)pbIV = *((_OWORD *)v64 + 2);
        v34 = BCryptDecrypt(
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
        if ( v34 < 0 )
        {
          v35 = 1625;
          goto LABEL_46;
        }
LABEL_58:
        v38 = v65;
        if ( v58 == 32782 )
        {
          if ( !(unsigned int)FMyPrimitiveSHA512((PUCHAR)pbOutput, v12[2] - v55, Buf1) )
          {
            v33 = 1716;
            goto LABEL_43;
          }
        }
        else if ( v58 == 32777 && !(unsigned int)FMyPrimitiveSHA((PUCHAR)pbOutput, v12[2] - v55, Buf1) )
        {
          v33 = 1730;
          goto LABEL_43;
        }
        v39 = v12[2];
        if ( memcmp_0(Buf1, &pbOutput[v39 - v28], v28) )
        {
          v33 = 1740;
          goto LABEL_43;
        }
        if ( *(_DWORD *)pbOutput != 1 )
        {
          v33 = 1747;
          goto LABEL_43;
        }
        v40 = *((unsigned int *)pbOutput + 1);
        if ( v28 + v40 + 8 > v39 )
        {
          v33 = 1756;
          goto LABEL_43;
        }
        v41 = &pbOutput[v40 + 8];
        if ( !IsValidSid(v41) )
        {
          LastError = 1337;
          DebugTraceError(1337, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 1770);
          goto LABEL_47;
        }
        if ( v28 + GetLengthSid(v41) + *((_DWORD *)pbOutput + 1) + 8LL > v12[2] )
        {
          v33 = 1782;
          goto LABEL_43;
        }
        v7 = 0;
        if ( !CheckTokenMembership(TokenHandle, v41, &IsMember) )
        {
          v42 = GetLastError();
          v43 = 1793;
LABEL_76:
          LastError = v42;
          v44 = v42;
LABEL_77:
          DebugTraceError(v44, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v43);
          v6 = (HLOCAL *)a5;
          goto LABEL_88;
        }
        if ( !IsMember )
        {
          LastError = 12;
          v43 = 1799;
          v44 = 12;
          goto LABEL_77;
        }
        if ( v61 )
        {
          if ( !ConvertRecoveredBlobToW2KBlob(
                  (unsigned __int8 *)Src,
                  *v18,
                  (unsigned __int8 *)pbOutput + 8,
                  *((_DWORD *)pbOutput + 1),
                  v41,
                  a5,
                  v38) )
          {
            v42 = GetLastError();
            v43 = 1816;
            goto LABEL_76;
          }
          v6 = (HLOCAL *)a5;
        }
        else
        {
          v45 = *v18 + 4;
          *v38 = v45;
          v46 = (unsigned __int8 *)LocalAlloc(0, v45);
          v6 = (HLOCAL *)a5;
          *a5 = v46;
          if ( !v46 )
          {
            *v38 = 0;
            LastError = 1130;
            goto LABEL_88;
          }
          v47 = Src;
          *(_DWORD *)v46 = 0;
          memcpy_0(*a5 + 4, v47, *v38 - 4LL);
        }
        v7 = 1;
        goto LABEL_88;
      }
    }
    else
    {
      phKey = 0;
      v36 = v27 & 0xFFFFFFF8;
      pcbResult = 0;
      if ( (v27 & 0xFFFFFFF8) == (_DWORD)v27 )
      {
        v37 = (void *)GetBCryptProviderHandle(0x6603u);
        if ( !v37 )
        {
          v33 = 1657;
          goto LABEL_43;
        }
        v34 = BCryptGenerateSymmetricKey(v37, &phKey, 0, 0, v30, 0x18u, 0);
        if ( v34 < 0 )
        {
          v35 = 1671;
          goto LABEL_46;
        }
        *(_QWORD *)pbIV = *((_QWORD *)v64 + 3);
        v34 = BCryptDecrypt(phKey, (PUCHAR)pbOutput, v36, 0, pbIV, 8u, (PUCHAR)pbOutput, v36, &pcbResult, 0);
        BCryptDestroyKey(phKey);
        if ( v34 < 0 )
        {
          v35 = 1695;
          goto LABEL_46;
        }
        goto LABEL_58;
      }
    }
    v6 = (HLOCAL *)a5;
    v7 = 0;
    goto LABEL_88;
  }
  LastError = 13;
  DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 1552);
LABEL_38:
  v10 = v53;
  v7 = 0;
LABEL_94:
  v48 = hMem;
  if ( hMem )
  {
    v49 = v60;
    v50 = hMem;
    if ( v60 )
    {
      do
      {
        *v50++ = 0;
        --v49;
      }
      while ( v49 );
    }
    LocalFree(v48);
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
  v51 = v12;
  do
  {
    *v51++ = 0;
    --v10;
  }
  while ( v10 );
  LocalFree(v12);
  return v7;
}

```

## disassembly

```asm
0x18003325c  mov     [rsp-8+arg_8], rbx
0x180033261  push    rbp
0x180033262  push    rsi
0x180033263  push    rdi
0x180033264  push    r12
0x180033266  push    r13
0x180033268  push    r14
0x18003326a  push    r15
0x18003326c  lea     rbp, [rsp-20h]
0x180033271  sub     rsp, 120h
0x180033278  mov     rax, cs:__security_cookie
0x18003327f  xor     rax, rsp
0x180033282  mov     [rbp+50h+var_40], rax
0x180033286  mov     r14, [rbp+50h+arg_20]
0x18003328d  xor     r13d, r13d
0x180033290  mov     r12, [rbp+50h+arg_28]
0x180033297  mov     rsi, r8
0x18003329a  mov     ebx, r9d
0x18003329d  mov     [rbp+50h+var_C4], edx
0x1800332a0  mov     [rbp+50h+TokenHandle], rcx
0x1800332a4  mov     [rsp+150h+var_F0], r14
0x1800332a9  mov     [rbp+50h+var_A8], r12
0x1800332ad  mov     [rbp+50h+IsMember], r13d
0x1800332b1  mov     [rsp+150h+cbInput], r13d
0x1800332b6  mov     [rbp+50h+hMem], r13
0x1800332ba  mov     [rbp+50h+var_C8], r13d
0x1800332be  mov     [rbp+50h+hKey], r13
0x1800332c2  test    r8, r8
0x1800332c5  jz      loc_180033AC3
0x1800332cb  test    r9d, r9d
0x1800332ce  jz      loc_180033AC3
0x1800332d4  test    r14, r14
0x1800332d7  jz      loc_180033AC3
0x1800332dd  test    r12, r12
0x1800332e0  jz      loc_180033AC3
0x1800332e6  cmp     ebx, 7FFFFFFFh
0x1800332ec  ja      loc_180033AC3
0x1800332f2  mov     edx, ebx; uBytes
0x1800332f4  mov     [r14], r13
0x1800332f7  xor     ecx, ecx; uFlags
0x1800332f9  mov     [rsp+150h+var_F8], rbx
0x1800332fe  mov     r15d, ebx
0x180033301  call    cs:__imp_LocalAlloc
0x180033308  nop     dword ptr [rax+rax+00h]
0x18003330d  mov     rdi, rax
0x180033310  test    rax, rax
0x180033313  jnz     short loc_18003331F
0x180033315  mov     ecx, 46Ah
0x18003331a  jmp     loc_180033AC8
0x18003331f  mov     r8, rbx; Size
0x180033322  mov     [rsp+150h+var_100], r13d
0x180033327  mov     rdx, rsi; Src
0x18003332a  mov     rcx, rdi; void *
0x18003332d  call    memcpy_0
0x180033332  mov     esi, 0Dh
0x180033337  cmp     ebx, 1Ch
0x18003333a  jb      loc_180033A0C
0x180033340  mov     eax, 0FFFFh
0x180033345  cmp     [rdi+4], eax
0x180033348  ja      loc_180033A0C
0x18003334e  cmp     [rdi+8], eax
0x180033351  ja      loc_180033A0C
0x180033357  mov     ecx, [rdi+8]
0x18003335a  mov     eax, [rdi+4]
0x18003335d  add     rcx, 1Ch
0x180033361  add     rcx, rax
0x180033364  cmp     rbx, rcx
0x180033367  jb      loc_180033A0C
0x18003336d  mov     eax, [rdi]
0x18003336f  lea     ebx, [rsi-0Bh]
0x180033372  sub     eax, ebx
0x180033374  cmp     eax, 1
0x180033377  ja      loc_180033A0C
0x18003337d  lea     rax, [rbp+50h+hKey]
0x180033381  mov     ecx, ebx; unsigned int
0x180033383  lea     rdx, [rdi+0Ch]; struct _GUID *
0x180033387  mov     [rsp+150h+pbIV], rax; phKey
0x18003338c  lea     r9, [rbp+50h+var_C8]; unsigned int *
0x180033390  lea     r8, [rbp+50h+hMem]; unsigned __int8 **
0x180033394  call    ?GetBackupKey@@YAHKPEBU_GUID@@PEAPEAEPEAKPEAPEAX@Z; GetBackupKey(ulong,_GUID const *,uchar * *,ulong *,void * *)
0x180033399  test    eax, eax
0x18003339b  jnz     short loc_1800333B8
0x18003339d  call    cs:__imp_GetLastError
0x1800333a4  nop     dword ptr [rax+rax+00h]
0x1800333a9  mov     ebx, eax
0x1800333ab  mov     ecx, eax
0x1800333ad  mov     r9d, 599h
0x1800333b3  jmp     loc_180033A19
0x1800333b8  mov     rax, [rbp+50h+hMem]
0x1800333bc  cmp     [rax], ebx
0x1800333be  jz      short loc_1800333D0
0x1800333c0  mov     ebx, 80090003h
0x1800333c5  mov     r9d, 5A5h
0x1800333cb  jmp     loc_180033A17
0x1800333d0  mov     esi, [rdi+4]
0x1800333d3  lea     r15, [rdi+1Ch]
0x1800333d7  mov     edx, esi; unsigned int
0x1800333d9  mov     [rsp+150h+cbInput], esi
0x1800333dd  mov     rcx, r15; unsigned __int8 *
0x1800333e0  call    ?FMyReverseBytes@@YAXPEAEK@Z; FMyReverseBytes(uchar *,ulong)
0x1800333e5  mov     r8d, [rsp+150h+cbInput]; cbInput
0x1800333ea  lea     rax, [rsp+150h+cbInput]
0x1800333ef  mov     rcx, [rbp+50h+hKey]; hKey
0x1800333f3  xor     r9d, r9d; pPaddingInfo
0x1800333f6  mov     [rsp+150h+dwFlags], ebx; dwFlags
0x1800333fa  mov     rdx, r15; pbInput
0x1800333fd  mov     [rsp+150h+pcbResult], rax; pcbResult
0x180033402  mov     [rsp+150h+cbOutput], r8d; cbOutput
0x180033407  mov     [rsp+150h+pbOutput], r15; pbOutput
0x18003340c  mov     [rsp+150h+cbIV], r13d; cbIV
0x180033411  mov     [rsp+150h+pbIV], r13; pbIV
0x180033416  call    cs:__imp_BCryptDecrypt
0x18003341d  nop     dword ptr [rax+rax+00h]
0x180033422  mov     ebx, eax
0x180033424  test    eax, eax
0x180033426  jns     short loc_180033458
0x180033428  mov     r9d, 5C1h
0x18003342e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033435  lea     rdx, aNtstatus; "ntStatus"
0x18003343c  mov     ecx, eax
0x18003343e  call    DebugTraceError
0x180033443  mov     ecx, ebx; Status
0x180033445  call    cs:__imp_RtlNtStatusToDosError
0x18003344c  nop     dword ptr [rax+rax+00h]
0x180033451  mov     ebx, eax
0x180033453  jmp     loc_1800339F2
0x180033458  mov     eax, 0FFFFh
0x18003345d  cmp     [r15], eax
0x180033460  ja      loc_1800339FE
0x180033466  mov     edx, [r15+4]
0x18003346a  cmp     edx, eax
0x18003346c  ja      loc_1800339FE
0x180033472  cmp     dword ptr [rdi], 3
0x180033475  mov     r11d, 6610h
0x18003347b  mov     r9d, 800Eh
0x180033481  jnz     short loc_1800334F1
0x180033483  cmp     [r15+8], r11d
0x180033487  jnz     short loc_1800334CA
0x180033489  cmp     [r15+0Ch], r9d
0x18003348d  jnz     short loc_1800334CA
0x18003348f  mov     r8d, [r15]
0x180033492  lea     rcx, [rdx+10h]
0x180033496  mov     eax, [rsp+150h+cbInput]
0x18003349a  add     rcx, r8
0x18003349d  cmp     rcx, rax
0x1800334a0  jbe     short loc_1800334AA
0x1800334a2  mov     r9d, 5E1h
0x1800334a8  jmp     short loc_1800334D0
0x1800334aa  cmp     edx, 30h ; '0'
0x1800334ad  jz      short loc_1800334B7
0x1800334af  mov     r9d, 5F0h
0x1800334b5  jmp     short loc_1800334D0
0x1800334b7  mov     r10d, 40h ; '@'
0x1800334bd  mov     [rbp+50h+var_D0], r9d
0x1800334c1  mov     edx, r11d
0x1800334c4  lea     r9d, [r10-30h]
0x1800334c8  jmp     short loc_18003352F
0x1800334ca  mov     r9d, 5D8h
0x1800334d0  mov     esi, 0Dh
0x1800334d5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800334dc  mov     ecx, esi
0x1800334de  lea     rdx, aDwlasterror; "dwLastError"
0x1800334e5  mov     ebx, esi
0x1800334e7  call    DebugTraceError
0x1800334ec  jmp     loc_180033A05
0x1800334f1  mov     r8d, [r15]
0x1800334f4  lea     rcx, [rdx+8]
0x1800334f8  mov     eax, [rsp+150h+cbInput]
0x1800334fc  add     rcx, r8
0x1800334ff  cmp     rcx, rax
0x180033502  jbe     short loc_18003350C
0x180033504  mov     r9d, 5FDh
0x18003350a  jmp     short loc_1800334D0
0x18003350c  cmp     edx, 20h ; ' '
0x18003350f  jz      short loc_180033519
0x180033511  mov     r9d, 604h
0x180033517  jmp     short loc_1800334D0
0x180033519  mov     r10d, 14h
0x18003351f  mov     [rbp+50h+var_D0], 8009h
0x180033526  mov     edx, 6603h
0x18003352b  lea     r9d, [r10-0Ch]
0x18003352f  mov     ecx, [rdi+8]
0x180033532  mov     r13d, r10d
0x180033535  mov     [rsp+150h+var_E4], r10d
0x18003353a  lea     rax, [r13+8]
0x18003353e  cmp     rcx, rax
0x180033541  jnb     short loc_180033574
0x180033543  mov     esi, 0Dh
0x180033548  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003354f  mov     ecx, esi
0x180033551  lea     rdx, aDwlasterror; "dwLastError"
0x180033558  mov     r9d, 610h
0x18003355e  mov     ebx, esi
0x180033560  call    DebugTraceError
0x180033565  mov     r15, [rsp+150h+var_F8]
0x18003356a  mov     r13d, [rsp+150h+var_100]
0x18003356f  jmp     loc_180033A2C
0x180033574  lea     rax, [r15+r9]
0x180033578  xor     ebx, ebx
0x18003357a  add     rsi, r15
0x18003357d  mov     [rbp+50h+Src], rax
0x180033581  lea     r14, [rax+r8]
0x180033585  mov     [rbp+50h+var_B0], r14
0x180033589  cmp     edx, r11d
0x18003358c  jnz     loc_1800336C5
0x180033592  mov     r12d, ecx
0x180033595  mov     [rsp+150h+phKey], rbx
0x18003359a  and     r12d, 0FFFFFFF0h
0x18003359e  mov     [rsp+150h+var_E0], ebx
0x1800335a2  cmp     r12d, ecx
0x1800335a5  jnz     loc_1800337B7
0x1800335ab  xor     r8d, r8d
0x1800335ae  xor     edx, edx
0x1800335b0  mov     ecx, r11d; unsigned int
0x1800335b3  call    GetBCryptProviderHandle
0x1800335b8  test    rax, rax
0x1800335bb  jnz     short loc_1800335E9
0x1800335bd  mov     r9d, 633h
0x1800335c3  mov     esi, 0Dh
0x1800335c8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800335cf  mov     ecx, esi
0x1800335d1  lea     rdx, aDwlasterror; "dwLastError"
0x1800335d8  mov     ebx, esi
0x1800335da  call    DebugTraceError
0x1800335df  mov     r14, [rsp+150h+var_F0]
0x1800335e4  jmp     loc_180033565
0x1800335e9  mov     dword ptr [rsp+150h+pbOutput], ebx; dwFlags
0x1800335ed  lea     rdx, [rsp+150h+phKey]; phKey
0x1800335f2  mov     [rsp+150h+cbIV], 20h ; ' '; cbSecret
0x1800335fa  xor     r9d, r9d; cbKeyObject
0x1800335fd  xor     r8d, r8d; pbKeyObject
0x180033600  mov     [rsp+150h+pbIV], r14; pbSecret
0x180033605  mov     rcx, rax; hAlgorithm
0x180033608  call    cs:__imp_BCryptGenerateSymmetricKey
0x18003360f  nop     dword ptr [rax+rax+00h]
0x180033614  mov     r14d, eax
0x180033617  test    eax, eax
0x180033619  jns     short loc_18003364D
0x18003361b  mov     r9d, 641h
0x180033621  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180033628  mov     ecx, r14d
0x18003362b  lea     rdx, aNtstatus; "ntStatus"
0x180033632  call    DebugTraceError
0x180033637  mov     ebx, r14d
0x18003363a  bts     ebx, 1Ch
0x18003363e  mov     r14, [rsp+150h+var_F0]
0x180033643  mov     r13d, [rsp+150h+var_100]
0x180033648  jmp     loc_1800339F2
0x18003364d  mov     rax, [rbp+50h+var_B0]
0x180033651  xor     r9d, r9d; pPaddingInfo
0x180033654  mov     rcx, [rsp+150h+phKey]; hKey
0x180033659  mov     r8d, r12d; cbInput
0x18003365c  mov     [rsp+150h+dwFlags], ebx; dwFlags
0x180033660  mov     rdx, rsi; pbInput
0x180033663  movups  xmm0, xmmword ptr [rax+20h]
0x180033667  lea     rax, [rsp+150h+var_E0]
0x18003366c  mov     [rsp+150h+pcbResult], rax; pcbResult
0x180033671  lea     rax, [rbp+50h+var_90]
0x180033675  mov     [rsp+150h+cbOutput], r12d; cbOutput
0x18003367a  mov     [rsp+150h+pbOutput], rsi; pbOutput
0x18003367f  mov     [rsp+150h+cbIV], 10h; cbIV
0x180033687  mov     [rsp+150h+pbIV], rax; pbIV
0x18003368c  movdqu  xmmword ptr [rbp+50h+var_90], xmm0
0x180033691  call    cs:__imp_BCryptDecrypt
0x180033698  nop     dword ptr [rax+rax+00h]
0x18003369d  mov     rcx, [rsp+150h+phKey]; hKey
0x1800336a2  mov     r14d, eax
0x1800336a5  call    cs:__imp_BCryptDestroyKey
0x1800336ac  nop     dword ptr [rax+rax+00h]
0x1800336b1  test    r14d, r14d
0x1800336b4  jns     loc_1800337C4
0x1800336ba  mov     r9d, 659h
0x1800336c0  jmp     loc_180033621
0x1800336c5  mov     eax, 6603h
0x1800336ca  cmp     edx, eax
0x1800336cc  jnz     loc_1800337CD
0x1800336d2  mov     r12d, ecx
0x1800336d5  mov     [rsp+150h+phKey], rbx
0x1800336da  and     r12d, 0FFFFFFF8h
0x1800336de  mov     [rsp+150h+var_E0], ebx
0x1800336e2  cmp     r12d, ecx
0x1800336e5  jnz     loc_1800337B7
0x1800336eb  xor     r8d, r8d
0x1800336ee  xor     edx, edx
0x1800336f0  mov     ecx, eax; unsigned int
0x1800336f2  call    GetBCryptProviderHandle
0x1800336f7  test    rax, rax
0x1800336fa  jnz     short loc_180033707
0x1800336fc  mov     r9d, 679h
0x180033702  jmp     loc_1800335C3
0x180033707  mov     dword ptr [rsp+150h+pbOutput], ebx; dwFlags
0x18003370b  lea     rdx, [rsp+150h+phKey]; phKey
0x180033710  mov     [rsp+150h+cbIV], 18h; cbSecret
0x180033718  xor     r9d, r9d; cbKeyObject
0x18003371b  xor     r8d, r8d; pbKeyObject
0x18003371e  mov     [rsp+150h+pbIV], r14; pbSecret
0x180033723  mov     rcx, rax; hAlgorithm
0x180033726  call    cs:__imp_BCryptGenerateSymmetricKey
0x18003372d  nop     dword ptr [rax+rax+00h]
0x180033732  mov     r14d, eax
  ... truncated ...
```
