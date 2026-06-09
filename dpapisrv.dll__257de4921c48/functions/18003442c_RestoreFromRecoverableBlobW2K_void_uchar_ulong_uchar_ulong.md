# RestoreFromRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18003442c`
- end: `0x1800349dd`
- name: `?RestoreFromRecoverableBlobW2K@@YAHPEAXPEAEKPEAPEAEPEAK@Z`
- size: `1457`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800362c0`

## callees

- `0x180002310`
- `0x1800029d0`
- `0x180007f10`
- `0x18001d810`
- `0x180032084`
- `0x18003442c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180034720`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180034720`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800346dd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800346dd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800347bd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800347bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800349ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800349ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034939`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034998`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034939`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034998`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800344ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003483d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800344ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003483d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003461f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003461f`
- `bcrypt!BCryptDecrypt` at `0x180034665`
- `bcrypt!BCryptDecrypt` at `0x180034665`
- `bcrypt!BCryptDestroyKey` at `0x18003467d`
- `bcrypt!BCryptDestroyKey` at `0x1800348cb`
- `bcrypt!BCryptDestroyKey` at `0x18003467d`
- `bcrypt!BCryptDestroyKey` at `0x1800348cb`

## string_xrefs

- `0x18003456f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800347e3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180034858`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800348b1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall RestoreFromRecoverableBlobW2K(
        void *a1,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  UCHAR *v7; // r13
  unsigned int v8; // esi
  HLOCAL *v9; // r14
  void *BCryptProviderHandle; // rax
  unsigned int v11; // edx
  unsigned __int8 *v12; // r12
  DWORD LastError; // ebx
  __int64 v14; // rsi
  __int64 v15; // r14
  unsigned __int8 *v16; // rax
  DWORD v17; // ecx
  __int64 v18; // rcx
  unsigned int v19; // r15d
  unsigned int i; // eax
  DWORD LengthSid; // eax
  int v22; // ecx
  __int64 v23; // r9
  __int64 v24; // r15
  __int64 v25; // rcx
  __int64 v26; // r9
  SIZE_T v27; // rdx
  unsigned int *v28; // rdi
  unsigned __int8 *v29; // rax
  __int64 v30; // rdi
  UCHAR *v31; // rax
  __int64 v32; // rcx
  UCHAR *v33; // rax
  UCHAR *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  unsigned __int8 *v37; // rcx
  unsigned int v39; // [rsp+60h] [rbp-A0h]
  unsigned int v40; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 **v41; // [rsp+70h] [rbp-90h]
  WINBOOL IsMember; // [rsp+78h] [rbp-88h] BYREF
  _DWORD uBytes[3]; // [rsp+7Ch] [rbp-84h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+88h] [rbp-78h] BYREF
  ULONG pcbResult; // [rsp+90h] [rbp-70h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+98h] [rbp-68h]
  HANDLE TokenHandle; // [rsp+A0h] [rbp-60h]
  unsigned int *v48; // [rsp+A8h] [rbp-58h]
  UCHAR v49[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h]
  int v51; // [rsp+C0h] [rbp-40h]
  UCHAR pbOutput[24]; // [rsp+C8h] [rbp-38h] BYREF
  UCHAR v53[24]; // [rsp+E0h] [rbp-20h] BYREF

  uBytes[0] = a3;
  TokenHandle = a1;
  v7 = 0;
  v8 = 0;
  v48 = a5;
  *(_QWORD *)&uBytes[1] = 0;
  v40 = 0;
  v41 = a4;
  v9 = (HLOCAL *)a4;
  IsMember = 0;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6801u);
  hAlgorithm = BCryptProviderHandle;
  phKey = 0;
  pcbResult = 0;
  if ( !a2 || !a3 || !v9 || !a5 )
    goto LABEL_73;
  v11 = 0;
  v12 = 0;
  v39 = 0;
  LastError = 0;
  if ( !BCryptProviderHandle )
  {
    v19 = 0;
    goto LABEL_52;
  }
  v14 = uBytes[0];
  *v9 = 0;
  v15 = (unsigned int)v14;
  v16 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)v14);
  v12 = v16;
  if ( !v16 )
  {
    v17 = 1130;
LABEL_74:
    SetLastError(v17);
    return 0;
  }
  memcpy_0(v16, a2, (unsigned int)v14);
  if ( (unsigned int)v14 < 0x94
    || *(_DWORD *)a2 != 1
    || (v18 = *((unsigned int *)a2 + 2), v18 != v14 - 96)
    || *((_DWORD *)a2 + 1) > (unsigned int)v18 )
  {
LABEL_73:
    v17 = 87;
    goto LABEL_74;
  }
  if ( (unsigned int)GetBackupKey(1u, (const struct _GUID *)(a2 + 12), (unsigned __int8 **)&uBytes[1], &v40, 0) )
  {
    v7 = *(UCHAR **)&uBytes[1];
    v8 = v40;
    if ( **(_DWORD **)&uBytes[1] == 1 )
    {
      for ( i = 0; ; v39 = i )
      {
        if ( i )
          a2 = v12;
        if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v7 + 4, v8 - 4, a2 + 28, 0x44u, 0, 0, pbOutput, 0x14u) )
        {
          v23 = 1118;
          goto LABEL_45;
        }
        if ( BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbOutput, 0x14u, 0) < 0 )
          goto LABEL_47;
        if ( BCryptDecrypt(phKey, a2 + 96, *((_DWORD *)a2 + 2), 0, 0, 0, a2 + 96, *((_DWORD *)a2 + 2), &pcbResult, 0) < 0 )
        {
          BCryptDestroyKey(phKey);
LABEL_47:
          v19 = 0;
LABEL_48:
          v9 = (HLOCAL *)v41;
          goto LABEL_49;
        }
        BCryptDestroyKey(phKey);
        if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v7 + 4, v8 - 4, a2 + 96, 0x20u, 0, 0, v53, 0x14u) )
        {
          v23 = 1179;
          goto LABEL_45;
        }
        *(_QWORD *)&uBytes[1] = a2 + 148;
        if ( IsValidSid(a2 + 148) )
          break;
        if ( (unsigned __int64)v8 - 4 <= 0x40 )
        {
          LastError = 1337;
LABEL_27:
          v19 = 0;
          goto LABEL_48;
        }
        i = v8;
        v8 = 68;
      }
      LengthSid = GetLengthSid(a2 + 148);
      v22 = *((_DWORD *)a2 + 2);
      v40 = LengthSid;
      if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v53, 0x14u, a2 + 148, v22 - 52, 0, 0, v49, 0x14u) )
      {
        v23 = 1229;
LABEL_45:
        DebugTraceError(2147500037LL, "E_FAIL", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v23);
        goto LABEL_47;
      }
      if ( *((_QWORD *)a2 + 16) == *(_QWORD *)v49 && *((_QWORD *)a2 + 17) == v50 && *((_DWORD *)a2 + 36) == v51 )
      {
        v24 = *(_QWORD *)&uBytes[1];
        if ( CheckTokenMembership(TokenHandle, *(PSID *)&uBytes[1], &IsMember) )
        {
          if ( IsMember )
          {
            v27 = *((unsigned int *)a2 + 1);
            if ( v27 == v15 - v40 - 148 )
            {
              v28 = v48;
              *v48 = v27;
              v29 = (unsigned __int8 *)LocalAlloc(0, v27);
              v9 = (HLOCAL *)v41;
              *v41 = v29;
              if ( v29 )
              {
                memcpy_0(v29, (const void *)(v24 + v40), *v28);
                v19 = 1;
              }
              else
              {
                *v28 = 0;
                LastError = 1130;
                DebugTraceError(
                  1130,
                  "dwLastError",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
                  1289);
                v19 = 0;
              }
LABEL_49:
              v11 = v39;
              goto LABEL_52;
            }
            LastError = 87;
            v26 = 1274;
            v25 = 87;
          }
          else
          {
            v25 = 12;
            v26 = 1259;
            LastError = 12;
          }
        }
        else
        {
          LastError = GetLastError();
          v25 = LastError;
          v26 = 1252;
        }
      }
      else
      {
        v25 = 12;
        v26 = 1240;
        LastError = 12;
      }
      DebugTraceError(v25, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v26);
      goto LABEL_27;
    }
  }
  else
  {
    DebugTraceError(2147500037LL, "E_FAIL", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 1084);
    v7 = *(UCHAR **)&uBytes[1];
    v8 = v40;
  }
  v9 = (HLOCAL *)v41;
  v19 = 0;
  v11 = 0;
LABEL_52:
  v30 = 20;
  v31 = pbOutput;
  v32 = 20;
  do
  {
    *v31++ = 0;
    --v32;
  }
  while ( v32 );
  v33 = v53;
  do
  {
    *v33++ = 0;
    --v30;
  }
  while ( v30 );
  if ( v7 )
  {
    v34 = v7;
    if ( v11 )
      v8 = v11;
    v35 = v8;
    if ( v8 )
    {
      do
      {
        *v34++ = 0;
        --v35;
      }
      while ( v35 );
    }
    LocalFree(v7);
  }
  if ( !v19 )
  {
    if ( *v9 )
    {
      LocalFree(*v9);
      *v9 = 0;
    }
    if ( !LastError )
      LastError = 13;
    SetLastError(LastError);
  }
  if ( v12 )
  {
    v36 = uBytes[0];
    v37 = v12;
    do
    {
      *v37++ = 0;
      --v36;
    }
    while ( v36 );
    LocalFree(v12);
  }
  return v19;
}

```

## disassembly

```asm
0x18003442c  push    rbp
0x18003442e  push    rbx
0x18003442f  push    rsi
0x180034430  push    rdi
0x180034431  push    r12
0x180034433  push    r13
0x180034435  push    r14
0x180034437  push    r15
0x180034439  lea     rbp, [rsp-8]
0x18003443e  sub     rsp, 108h
0x180034445  mov     rax, cs:__security_cookie
0x18003444c  xor     rax, rsp
0x18003444f  mov     [rbp+40h+var_48], rax
0x180034453  mov     rbx, [rbp+40h+arg_20]
0x180034457  mov     r15d, r8d
0x18003445a  mov     dword ptr [rsp+140h+uBytes], r8d
0x18003445f  mov     rdi, rdx
0x180034462  mov     [rbp+40h+TokenHandle], rcx
0x180034466  xor     r13d, r13d
0x180034469  xor     esi, esi
0x18003446b  mov     [rbp+40h+var_98], rbx
0x18003446f  xor     r8d, r8d
0x180034472  mov     qword ptr [rbp+40h+uBytes+4], r13
0x180034476  xor     edx, edx
0x180034478  mov     [rsp+140h+var_D8], esi
0x18003447c  mov     ecx, 6801h; unsigned int
0x180034481  mov     [rsp+140h+var_D0], r9
0x180034486  mov     r14, r9
0x180034489  mov     [rsp+140h+IsMember], 0
0x180034491  call    GetBCryptProviderHandle
0x180034496  mov     [rbp+40h+hAlgorithm], rax
0x18003449a  mov     [rbp+40h+phKey], rsi
0x18003449e  mov     [rbp+40h+var_B0], esi
0x1800344a1  test    rdi, rdi
0x1800344a4  jz      loc_1800349A9
0x1800344aa  test    r15d, r15d
0x1800344ad  jz      loc_1800349A9
0x1800344b3  test    r14, r14
0x1800344b6  jz      loc_1800349A9
0x1800344bc  test    rbx, rbx
0x1800344bf  jz      loc_1800349A9
0x1800344c5  xor     edx, edx
0x1800344c7  lea     r15d, [r13+14h]
0x1800344cb  xor     r12d, r12d
0x1800344ce  mov     [rsp+140h+var_E0], edx
0x1800344d2  xor     ebx, ebx
0x1800344d4  mov     [rsp+140h+var_DC], edx
0x1800344d8  test    rax, rax
0x1800344db  jz      loc_1800348ED
0x1800344e1  mov     esi, dword ptr [rsp+140h+uBytes]
0x1800344e5  xor     ecx, ecx; uFlags
0x1800344e7  mov     [r14], rdx
0x1800344ea  mov     edx, esi; uBytes
0x1800344ec  mov     r14d, esi
0x1800344ef  call    cs:__imp_LocalAlloc
0x1800344f6  nop     dword ptr [rax+rax+00h]
0x1800344fb  mov     r12, rax
0x1800344fe  test    rax, rax
0x180034501  jnz     short loc_18003450D
0x180034503  mov     ecx, 46Ah
0x180034508  jmp     loc_1800349AE
0x18003450d  mov     r8, r14; Size
0x180034510  mov     rdx, rdi; Src
0x180034513  mov     rcx, r12; void *
0x180034516  call    memcpy_0
0x18003451b  cmp     esi, 94h
0x180034521  jb      loc_1800349A9
0x180034527  cmp     dword ptr [rdi], 1
0x18003452a  jnz     loc_1800349A9
0x180034530  mov     ecx, [rdi+8]
0x180034533  lea     rax, [rsi-60h]
0x180034537  cmp     rcx, rax
0x18003453a  jnz     loc_1800349A9
0x180034540  cmp     [rdi+4], ecx
0x180034543  ja      loc_1800349A9
0x180034549  lea     rdx, [rdi+0Ch]; struct _GUID *
0x18003454d  mov     [rsp+140h+pbSecret], rbx; phKey
0x180034552  lea     r9, [rsp+140h+var_D8]; unsigned int *
0x180034557  mov     ecx, 1; unsigned int
0x18003455c  lea     r8, [rbp+40h+uBytes+4]; unsigned __int8 **
0x180034560  call    ?GetBackupKey@@YAHKPEBU_GUID@@PEAPEAEPEAKPEAPEAX@Z; GetBackupKey(ulong,_GUID const *,uchar * *,ulong *,void * *)
0x180034565  test    eax, eax
0x180034567  jnz     short loc_18003459E
0x180034569  mov     r9d, 43Ch
0x18003456f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180034576  lea     rdx, aEFail; "E_FAIL"
0x18003457d  mov     ecx, 80004005h
0x180034582  call    DebugTraceError
0x180034587  mov     r13, qword ptr [rbp+40h+uBytes+4]
0x18003458b  mov     esi, [rsp+140h+var_D8]
0x18003458f  mov     r14, [rsp+140h+var_D0]
0x180034594  mov     r15d, ebx
0x180034597  mov     edx, ebx
0x180034599  jmp     loc_1800348F0
0x18003459e  mov     r13, qword ptr [rbp+40h+uBytes+4]
0x1800345a2  mov     esi, [rsp+140h+var_D8]
0x1800345a6  cmp     dword ptr [r13+0], 1
0x1800345ab  jnz     short loc_18003458F
0x1800345ad  mov     eax, ebx
0x1800345af  mov     [rsp+140h+var_F0], r15d; unsigned int
0x1800345b4  lea     r8, [rbp+40h+pbOutput]
0x1800345b8  mov     qword ptr [rsp+140h+var_F8], r8; pbOutput
0x1800345bd  lea     ecx, [rsi-4]
0x1800345c0  mov     dword ptr [rsp+140h+pcbResult], ebx; cbHashObject
0x1800345c4  lea     r9, [r13+4]; pbSecret
0x1800345c8  test    eax, eax
0x1800345ca  mov     qword ptr [rsp+140h+cbOutput], rbx; pbHashObject
0x1800345cf  mov     [rsp+140h+dwFlags], 44h ; 'D'; cbInput
0x1800345d7  mov     r8d, 8009h; unsigned int
0x1800345dd  cmovnz  rdi, r12
0x1800345e1  xor     edx, edx; hHash
0x1800345e3  lea     rax, [rdi+1Ch]
0x1800345e7  mov     qword ptr [rsp+140h+cbSecret], rax; pbInput
0x1800345ec  mov     dword ptr [rsp+140h+pbSecret], ecx; ULONG
0x1800345f0  xor     ecx, ecx; hAlgorithm
0x1800345f2  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x1800345f7  test    eax, eax
0x1800345f9  jz      loc_1800348E5
0x1800345ff  mov     rcx, [rbp+40h+hAlgorithm]; hAlgorithm
0x180034603  lea     rax, [rbp+40h+pbOutput]
0x180034607  mov     [rsp+140h+dwFlags], ebx; dwFlags
0x18003460b  lea     rdx, [rbp+40h+phKey]; phKey
0x18003460f  mov     [rsp+140h+cbSecret], r15d; cbSecret
0x180034614  xor     r9d, r9d; cbKeyObject
0x180034617  xor     r8d, r8d; pbKeyObject
0x18003461a  mov     [rsp+140h+pbSecret], rax; pbSecret
0x18003461f  call    cs:__imp_BCryptGenerateSymmetricKey
0x180034626  nop     dword ptr [rax+rax+00h]
0x18003462b  test    eax, eax
0x18003462d  js      loc_1800348D7
0x180034633  mov     r8d, [rdi+8]; cbInput
0x180034637  lea     rax, [rbp+40h+var_B0]
0x18003463b  mov     rcx, [rbp+40h+phKey]; hKey
0x18003463f  lea     r15, [rdi+60h]
0x180034643  mov     [rsp+140h+var_F8], ebx; dwFlags
0x180034647  xor     r9d, r9d; pPaddingInfo
0x18003464a  mov     [rsp+140h+pcbResult], rax; pcbResult
0x18003464f  mov     rdx, r15; pbInput
0x180034652  mov     [rsp+140h+cbOutput], r8d; cbOutput
0x180034657  mov     qword ptr [rsp+140h+dwFlags], r15; pbOutput
0x18003465c  mov     [rsp+140h+cbSecret], ebx; cbIV
0x180034660  mov     [rsp+140h+pbSecret], rbx; pbIV
0x180034665  call    cs:__imp_BCryptDecrypt
0x18003466c  nop     dword ptr [rax+rax+00h]
0x180034671  mov     rcx, [rbp+40h+phKey]; hKey
0x180034675  test    eax, eax
0x180034677  js      loc_1800348CB
0x18003467d  call    cs:__imp_BCryptDestroyKey
0x180034684  nop     dword ptr [rax+rax+00h]
0x180034689  mov     [rsp+140h+var_F0], 14h; unsigned int
0x180034691  lea     rax, [rbp+40h+var_60]
0x180034695  mov     qword ptr [rsp+140h+var_F8], rax; pbOutput
0x18003469a  lea     r9, [r13+4]; pbSecret
0x18003469e  mov     dword ptr [rsp+140h+pcbResult], ebx; cbHashObject
0x1800346a2  lea     eax, [rsi-4]
0x1800346a5  mov     qword ptr [rsp+140h+cbOutput], rbx; pbHashObject
0x1800346aa  xor     edx, edx; hHash
0x1800346ac  mov     [rsp+140h+dwFlags], 20h ; ' '; cbInput
0x1800346b4  xor     ecx, ecx; hAlgorithm
0x1800346b6  mov     qword ptr [rsp+140h+cbSecret], r15; pbInput
0x1800346bb  mov     r8d, 8009h; unsigned int
0x1800346c1  mov     dword ptr [rsp+140h+pbSecret], eax; ULONG
0x1800346c5  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x1800346ca  test    eax, eax
0x1800346cc  jz      loc_1800348AB
0x1800346d2  lea     rax, [r15+34h]
0x1800346d6  mov     rcx, rax; pSid
0x1800346d9  mov     qword ptr [rbp+40h+uBytes+4], rax
0x1800346dd  call    cs:__imp_IsValidSid
0x1800346e4  nop     dword ptr [rax+rax+00h]
0x1800346e9  test    eax, eax
0x1800346eb  jnz     short loc_18003471C
0x1800346ed  mov     eax, esi
0x1800346ef  sub     rax, 4
0x1800346f3  cmp     rax, 40h ; '@'
0x1800346f7  jbe     short loc_18003470D
0x1800346f9  mov     eax, esi
0x1800346fb  mov     esi, 44h ; 'D'
0x180034700  mov     [rsp+140h+var_E0], eax
0x180034704  lea     r15d, [rsi-30h]
0x180034708  jmp     loc_1800345AF
0x18003470d  mov     ebx, 539h
0x180034712  mov     r15d, [rsp+140h+var_DC]
0x180034717  jmp     loc_1800348DA
0x18003471c  lea     rcx, [r15+34h]; pSid
0x180034720  call    cs:__imp_GetLengthSid
0x180034727  nop     dword ptr [rax+rax+00h]
0x18003472c  mov     ecx, [rdi+8]
0x18003472f  lea     r9, [rbp+40h+var_60]; pbSecret
0x180034733  mov     [rsp+140h+var_D8], eax
0x180034737  mov     edx, 14h
0x18003473c  mov     [rsp+140h+var_F0], edx; unsigned int
0x180034740  lea     rax, [rbp+40h+var_90]
0x180034744  mov     qword ptr [rsp+140h+var_F8], rax; pbOutput
0x180034749  sub     ecx, 34h ; '4'
0x18003474c  mov     dword ptr [rsp+140h+pcbResult], ebx; cbHashObject
0x180034750  lea     rax, [r15+34h]
0x180034754  mov     qword ptr [rsp+140h+cbOutput], rbx; pbHashObject
0x180034759  mov     r8d, 8009h; unsigned int
0x18003475f  mov     [rsp+140h+dwFlags], ecx; cbInput
0x180034763  xor     ecx, ecx; hAlgorithm
0x180034765  mov     qword ptr [rsp+140h+cbSecret], rax; pbInput
0x18003476a  mov     dword ptr [rsp+140h+pbSecret], edx; ULONG
0x18003476e  xor     edx, edx; hHash
0x180034770  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180034775  test    eax, eax
0x180034777  jnz     short loc_180034784
0x180034779  mov     r9d, 4CDh
0x18003477f  jmp     loc_1800348B1
0x180034784  mov     rax, [r15+20h]
0x180034788  cmp     rax, qword ptr [rbp+40h+var_90]
0x18003478c  jnz     loc_180034899
0x180034792  mov     rax, [r15+28h]
0x180034796  cmp     rax, [rbp+40h+var_88]
0x18003479a  jnz     loc_180034899
0x1800347a0  mov     eax, [r15+30h]
0x1800347a4  cmp     eax, [rbp+40h+var_80]
0x1800347a7  jnz     loc_180034899
0x1800347ad  mov     r15, qword ptr [rbp+40h+uBytes+4]
0x1800347b1  lea     r8, [rsp+140h+IsMember]; IsMember
0x1800347b6  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x1800347ba  mov     rdx, r15; SidToCheck
0x1800347bd  call    cs:__imp_CheckTokenMembership
0x1800347c4  nop     dword ptr [rax+rax+00h]
0x1800347c9  test    eax, eax
0x1800347cb  jnz     short loc_1800347FB
0x1800347cd  call    cs:__imp_GetLastError
0x1800347d4  nop     dword ptr [rax+rax+00h]
0x1800347d9  mov     ebx, eax
0x1800347db  mov     ecx, eax
0x1800347dd  mov     r9d, 4E4h
0x1800347e3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800347ea  lea     rdx, aDwlasterror; "dwLastError"
0x1800347f1  call    DebugTraceError
0x1800347f6  jmp     loc_180034712
0x1800347fb  cmp     [rsp+140h+IsMember], ebx
0x1800347ff  jnz     short loc_180034810
0x180034801  mov     ecx, 0Ch
0x180034806  mov     r9d, 4EBh
0x18003480c  mov     ebx, ecx
0x18003480e  jmp     short loc_1800347E3
0x180034810  mov     eax, [rsp+140h+var_D8]
0x180034814  mov     edx, [rdi+4]; uBytes
0x180034817  sub     r14, rax
0x18003481a  sub     r14, 94h
0x180034821  cmp     rdx, r14
0x180034824  jz      short loc_180034835
0x180034826  mov     ebx, 57h ; 'W'
0x18003482b  mov     r9d, 4FAh
0x180034831  mov     ecx, ebx
0x180034833  jmp     short loc_1800347E3
0x180034835  mov     rdi, [rbp+40h+var_98]
0x180034839  xor     ecx, ecx; uFlags
0x18003483b  mov     [rdi], edx
0x18003483d  call    cs:__imp_LocalAlloc
0x180034844  nop     dword ptr [rax+rax+00h]
0x180034849  mov     r14, [rsp+140h+var_D0]
0x18003484e  mov     [r14], rax
0x180034851  test    rax, rax
0x180034854  jnz     short loc_18003487F
0x180034856  mov     [rdi], ebx
0x180034858  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003485f  mov     ebx, 46Ah
0x180034864  lea     rdx, aDwlasterror; "dwLastError"
0x18003486b  mov     ecx, ebx
0x18003486d  mov     r9d, 509h
0x180034873  call    DebugTraceError
0x180034878  mov     r15d, [rsp+140h+var_DC]
0x18003487d  jmp     short loc_1800348DF
0x18003487f  mov     edx, [rsp+140h+var_D8]
0x180034883  mov     rcx, rax; void *
0x180034886  mov     r8d, [rdi]; Size
0x180034889  add     rdx, r15; Src
0x18003488c  call    memcpy_0
0x180034891  mov     r15d, 1
0x180034897  jmp     short loc_1800348DF
0x180034899  mov     ecx, 0Ch
0x18003489e  mov     r9d, 4D8h
0x1800348a4  mov     ebx, ecx
0x1800348a6  jmp     loc_1800347E3
0x1800348ab  mov     r9d, 49Bh
0x1800348b1  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800348b8  mov     ecx, 80004005h
0x1800348bd  lea     rdx, aEFail; "E_FAIL"
0x1800348c4  call    DebugTraceError
0x1800348c9  jmp     short loc_1800348D7
0x1800348cb  call    cs:__imp_BCryptDestroyKey
0x1800348d2  nop     dword ptr [rax+rax+00h]
0x1800348d7  mov     r15d, ebx
0x1800348da  mov     r14, [rsp+140h+var_D0]
0x1800348df  mov     edx, [rsp+140h+var_E0]
0x1800348e3  jmp     short loc_1800348F0
0x1800348e5  mov     r9d, 45Eh
0x1800348eb  jmp     short loc_1800348B1
0x1800348ed  mov     r15d, edx
0x1800348f0  mov     edi, 14h
0x1800348f5  lea     rax, [rbp+40h+pbOutput]
0x1800348f9  mov     ecx, edi
0x1800348fb  mov     byte ptr [rax], 0
0x1800348fe  inc     rax
  ... truncated ...
```
