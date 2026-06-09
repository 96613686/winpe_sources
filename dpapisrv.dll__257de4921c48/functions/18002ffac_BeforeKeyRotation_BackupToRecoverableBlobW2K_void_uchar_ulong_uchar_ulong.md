# BeforeKeyRotation::BackupToRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18002ffac`
- end: `0x18003040c`
- name: `?BackupToRecoverableBlobW2K@BeforeKeyRotation@@YAHPEAXPEAEKPEAPEAEPEAK@Z`
- size: `1120`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, void *, unsigned __int8 *, HLOCAL *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035dd4`

## callees

- `0x180002310`
- `0x1800029d0`
- `0x180003080`
- `0x180007f10`
- `0x18001d810`
- `0x18002ffac`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180030091`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180030091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800303c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800303dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800303c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800303dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030391`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800303a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030391`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800303a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800300b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800300b1`
- `bcrypt!BCryptEncrypt` at `0x18003033a`
- `bcrypt!BCryptEncrypt` at `0x18003033a`
- `bcrypt!BCryptGenRandom` at `0x18003011f`
- `bcrypt!BCryptGenRandom` at `0x18003014e`
- `bcrypt!BCryptGenRandom` at `0x18003011f`
- `bcrypt!BCryptGenRandom` at `0x18003014e`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800302eb`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800302eb`
- `bcrypt!BCryptDestroyKey` at `0x18003034c`
- `bcrypt!BCryptDestroyKey` at `0x18003034c`

## string_xrefs

- `0x180030070`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800300dc`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800302b8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::BackupToRecoverableBlobW2K(
        BeforeKeyRotation *this,
        void *a2,
        unsigned __int8 *a3,
        HLOCAL *a4,
        unsigned __int8 **a5)
{
  size_t v6; // r13
  PSID v7; // rbx
  void *BCryptProviderHandle; // rax
  DWORD v10; // esi
  __int64 v11; // r12
  unsigned int v12; // edi
  size_t v13; // rcx
  DWORD LastError; // eax
  DWORD LengthSid; // eax
  char *v16; // rax
  char *v17; // r14
  const char *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r9
  NTSTATUS v21; // eax
  __int64 v22; // rbx
  __int64 v23; // r9
  const char *v24; // rdx
  __int64 v25; // rcx
  NTSTATUS v26; // eax
  NTSTATUS v27; // ebx
  UCHAR *v28; // rax
  PSID pSid; // [rsp+68h] [rbp-59h] BYREF
  size_t Size; // [rsp+70h] [rbp-51h]
  ULONG pcbResult; // [rsp+78h] [rbp-49h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp-41h] BYREF
  void *Src; // [rsp+88h] [rbp-39h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+90h] [rbp-31h]
  UCHAR pbOutput[24]; // [rsp+98h] [rbp-29h] BYREF
  UCHAR v37[24]; // [rsp+B0h] [rbp-11h] BYREF

  v6 = (unsigned int)a3;
  v7 = 0;
  Src = a2;
  Size = (size_t)this;
  pSid = 0;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6801u);
  hAlgorithm = BCryptProviderHandle;
  phKey = 0;
  pcbResult = 0;
  if ( !a2 || !(_DWORD)v6 || !a4 || !a5 || (unsigned int)v6 > 0x7FFFFFFF )
  {
    SetLastError(0x57u);
    return 0;
  }
  v10 = 0;
  v11 = 20;
  v12 = 0;
  if ( BCryptProviderHandle )
  {
    v13 = Size;
    *a4 = 0;
    if ( !(unsigned int)GetTokenUserSid(v13, &pSid) )
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        5214);
      return 0;
    }
    v7 = pSid;
    LengthSid = GetLengthSid(pSid);
    LODWORD(Size) = LengthSid;
    *(_DWORD *)a5 = LengthSid + v6 + 148;
    v16 = (char *)LocalAlloc(0, LengthSid + (unsigned int)v6 + 148);
    *a4 = v16;
    v17 = v16;
    if ( !v16 )
    {
      v10 = 1130;
      v18 = "dwLastError";
      v19 = 1130;
      v20 = 5247;
LABEL_11:
      DebugTraceError(v19, v18, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v20);
      goto LABEL_32;
    }
    *(_DWORD *)v16 = 1;
    *((_DWORD *)v16 + 1) = v6;
    *((_DWORD *)v16 + 2) = v6 + Size + 52;
    *(GUID *)(v16 + 12) = BeforeKeyRotation::g_guidW2KPreferredKey;
    v21 = BCryptGenRandom(0, (PUCHAR)v16 + 28, 0x44u, 2u);
    if ( v21 < 0 )
    {
      v20 = 5269;
LABEL_14:
      v18 = "ntStatus";
      v19 = (unsigned int)v21;
      goto LABEL_11;
    }
    v21 = BCryptGenRandom(0, (PUCHAR)v17 + 96, 0x20u, 2u);
    if ( v21 < 0 )
    {
      v20 = 5283;
      goto LABEL_14;
    }
    if ( **(_DWORD **)&BeforeKeyRotation::g_pbW2KPreferredKey.Data1 == 1 )
    {
      if ( !(unsigned int)ReusableHMAC(
                            0,
                            0,
                            0x8009u,
                            (PUCHAR)(*(_QWORD *)&BeforeKeyRotation::g_pbW2KPreferredKey.Data1 + 4LL),
                            (int)BeforeKeyRotation::g_cbW2KPreferredKey - 4,
                            (PUCHAR)v17 + 28,
                            0x44u,
                            0,
                            0,
                            pbOutput,
                            0x14u) )
      {
        v20 = 5313;
LABEL_20:
        v18 = "E_FAIL";
        v19 = 2147500037LL;
        goto LABEL_11;
      }
      if ( !(unsigned int)ReusableHMAC(
                            0,
                            0,
                            0x8009u,
                            (PUCHAR)(*(_QWORD *)&BeforeKeyRotation::g_pbW2KPreferredKey.Data1 + 4LL),
                            (int)BeforeKeyRotation::g_cbW2KPreferredKey - 4,
                            (PUCHAR)v17 + 96,
                            0x20u,
                            0,
                            0,
                            v37,
                            0x14u) )
      {
        v20 = 5334;
        goto LABEL_20;
      }
      v22 = (unsigned int)Size;
      memcpy_0(v17 + 148, pSid, (unsigned int)Size);
      memcpy_0(&v17[v22 + 148], Src, v6);
      if ( (unsigned int)ReusableHMAC(
                           0,
                           0,
                           0x8009u,
                           v37,
                           0x14u,
                           (PUCHAR)v17 + 148,
                           (int)v6 + (int)Size,
                           0,
                           0,
                           (PUCHAR)v17 + 128,
                           0x14u) )
      {
        v26 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbOutput, 0x14u, 0);
        if ( v26 >= 0 )
        {
          v27 = BCryptEncrypt(
                  phKey,
                  (PUCHAR)v17 + 96,
                  *((_DWORD *)v17 + 2),
                  0,
                  0,
                  0,
                  (PUCHAR)v17 + 96,
                  *((_DWORD *)v17 + 2),
                  &pcbResult,
                  0);
          BCryptDestroyKey(phKey);
          if ( v27 >= 0 )
          {
            v12 = 1;
            goto LABEL_31;
          }
          v23 = 5410;
          v24 = "ntStatus";
          v25 = (unsigned int)v27;
        }
        else
        {
          v23 = 5387;
          v24 = "ntStatus";
          v25 = (unsigned int)v26;
        }
      }
      else
      {
        v23 = 5363;
        v24 = "E_FAIL";
        v25 = 2147500037LL;
      }
      DebugTraceError(v25, v24, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v23);
      v12 = 0;
LABEL_31:
      v7 = pSid;
    }
  }
LABEL_32:
  v28 = pbOutput;
  do
  {
    *v28++ = 0;
    --v11;
  }
  while ( v11 );
  if ( v7 )
    LocalFree(v7);
  if ( !v12 )
  {
    if ( *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
    if ( !v10 )
      v10 = 13;
    SetLastError(v10);
  }
  return v12;
}

```

## disassembly

```asm
0x18002ffac  push    rbp
0x18002ffae  push    rbx
0x18002ffaf  push    rsi
0x18002ffb0  push    rdi
0x18002ffb1  push    r12
0x18002ffb3  push    r13
0x18002ffb5  push    r14
0x18002ffb7  push    r15
0x18002ffb9  lea     rbp, [rsp-17h]
0x18002ffbe  sub     rsp, 0D8h
0x18002ffc5  mov     rax, cs:__security_cookie
0x18002ffcc  xor     rax, rsp
0x18002ffcf  mov     [rbp+4Fh+var_48], rax
0x18002ffd3  mov     r14, [rbp+4Fh+arg_20]
0x18002ffd7  mov     rdi, rdx
0x18002ffda  mov     r13d, r8d
0x18002ffdd  xor     ebx, ebx
0x18002ffdf  mov     [rbp+4Fh+Src], rdx
0x18002ffe3  xor     r8d, r8d
0x18002ffe6  mov     [rbp+4Fh+Size], rcx
0x18002ffea  xor     edx, edx
0x18002ffec  mov     ecx, 6801h; unsigned int
0x18002fff1  mov     [rbp+4Fh+pSid], rbx
0x18002fff5  mov     r15, r9
0x18002fff8  call    GetBCryptProviderHandle
0x18002fffd  mov     [rbp+4Fh+hAlgorithm], rax
0x180030001  mov     [rbp+4Fh+phKey], rbx
0x180030005  mov     [rbp+4Fh+var_98], ebx
0x180030008  test    rdi, rdi
0x18003000b  jz      loc_1800303D8
0x180030011  test    r13d, r13d
0x180030014  jz      loc_1800303D8
0x18003001a  test    r15, r15
0x18003001d  jz      loc_1800303D8
0x180030023  test    r14, r14
0x180030026  jz      loc_1800303D8
0x18003002c  cmp     r13d, 7FFFFFFFh
0x180030033  ja      loc_1800303D8
0x180030039  xor     esi, esi
0x18003003b  lea     r12d, [rbx+14h]
0x18003003f  xor     edi, edi
0x180030041  test    rax, rax
0x180030044  jz      loc_180030379
0x18003004a  mov     rcx, [rbp+4Fh+Size]
0x18003004e  lea     rdx, [rbp+4Fh+pSid]
0x180030052  mov     [r15], rbx
0x180030055  call    GetTokenUserSid
0x18003005a  test    eax, eax
0x18003005c  jnz     short loc_18003008A
0x18003005e  call    cs:__imp_GetLastError
0x180030065  nop     dword ptr [rax+rax+00h]
0x18003006a  mov     r9d, 145Eh
0x180030070  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030077  mov     ecx, eax
0x180030079  lea     rdx, aGetlasterror; "GetLastError()"
0x180030080  call    DebugTraceError
0x180030085  jmp     loc_1800303E9
0x18003008a  mov     rbx, [rbp+4Fh+pSid]
0x18003008e  mov     rcx, rbx; pSid
0x180030091  call    cs:__imp_GetLengthSid
0x180030098  nop     dword ptr [rax+rax+00h]
0x18003009d  mov     dword ptr [rbp+4Fh+Size], eax
0x1800300a0  lea     ecx, [rax+r13]
0x1800300a4  add     ecx, 94h
0x1800300aa  mov     [r14], ecx
0x1800300ad  mov     edx, ecx; uBytes
0x1800300af  xor     ecx, ecx; uFlags
0x1800300b1  call    cs:__imp_LocalAlloc
0x1800300b8  nop     dword ptr [rax+rax+00h]
0x1800300bd  mov     [r15], rax
0x1800300c0  mov     r14, rax
0x1800300c3  test    rax, rax
0x1800300c6  jnz     short loc_1800300ED
0x1800300c8  mov     esi, 46Ah
0x1800300cd  lea     rdx, aDwlasterror; "dwLastError"
0x1800300d4  mov     ecx, esi
0x1800300d6  mov     r9d, 147Fh
0x1800300dc  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800300e3  call    DebugTraceError
0x1800300e8  jmp     loc_180030379
0x1800300ed  mov     dword ptr [rax], 1
0x1800300f3  lea     rdx, [r14+1Ch]; pbBuffer
0x1800300f7  mov     [rax+4], r13d
0x1800300fb  xor     ecx, ecx; hAlgorithm
0x1800300fd  mov     eax, dword ptr [rbp+4Fh+Size]
0x180030100  add     eax, 34h ; '4'
0x180030103  add     eax, r13d
0x180030106  mov     [r14+8], eax
0x18003010a  lea     r9d, [rcx+2]; dwFlags
0x18003010e  movups  xmm0, xmmword ptr cs:?g_guidW2KPreferredKey@BeforeKeyRotation@@3U_GUID@@A.Data1; _GUID BeforeKeyRotation::g_guidW2KPreferredKey ...
0x180030115  lea     r8d, [rcx+44h]; cbBuffer
0x180030119  movdqu  xmmword ptr [r14+0Ch], xmm0
0x18003011f  call    cs:__imp_BCryptGenRandom
0x180030126  nop     dword ptr [rax+rax+00h]
0x18003012b  test    eax, eax
0x18003012d  jns     short loc_180030140
0x18003012f  mov     r9d, 1495h
0x180030135  lea     rdx, aNtstatus; "ntStatus"
0x18003013c  mov     ecx, eax
0x18003013e  jmp     short loc_1800300DC
0x180030140  xor     ecx, ecx; hAlgorithm
0x180030142  lea     rdx, [r14+60h]; pbBuffer
0x180030146  lea     r9d, [rcx+2]; dwFlags
0x18003014a  lea     r8d, [rcx+20h]; cbBuffer
0x18003014e  call    cs:__imp_BCryptGenRandom
0x180030155  nop     dword ptr [rax+rax+00h]
0x18003015a  test    eax, eax
0x18003015c  jns     short loc_180030166
0x18003015e  mov     r9d, 14A3h
0x180030164  jmp     short loc_180030135
0x180030166  mov     r9, qword ptr cs:?g_pbW2KPreferredKey@BeforeKeyRotation@@3PEAEEA.Data1; uchar * BeforeKeyRotation::g_pbW2KPreferredKey ...
0x18003016d  cmp     dword ptr [r9], 1
0x180030171  jnz     loc_180030379
0x180030177  mov     eax, cs:?g_cbW2KPreferredKey@BeforeKeyRotation@@3KA; ulong BeforeKeyRotation::g_cbW2KPreferredKey
0x18003017d  lea     rcx, [rbp+4Fh+pbOutput]
0x180030181  mov     [rsp+110h+var_C0], r12d; unsigned int
0x180030186  add     eax, 0FFFFFFFCh
0x180030189  mov     qword ptr [rsp+110h+var_C8], rcx; pbOutput
0x18003018e  add     r9, 4; pbSecret
0x180030192  mov     dword ptr [rsp+110h+pcbResult], esi; cbHashObject
0x180030196  lea     rcx, [r14+1Ch]
0x18003019a  mov     qword ptr [rsp+110h+cbOutput], rsi; pbHashObject
0x18003019f  xor     edx, edx; hHash
0x1800301a1  mov     [rsp+110h+dwFlags], 44h ; 'D'; cbInput
0x1800301a9  mov     r8d, 8009h; unsigned int
0x1800301af  mov     qword ptr [rsp+110h+cbSecret], rcx; pbInput
0x1800301b4  xor     ecx, ecx; hAlgorithm
0x1800301b6  mov     dword ptr [rsp+110h+pbSecret], eax; ULONG
0x1800301ba  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x1800301bf  test    eax, eax
0x1800301c1  jnz     short loc_1800301DA
0x1800301c3  mov     r9d, 14C1h
0x1800301c9  lea     rdx, aEFail; "E_FAIL"
0x1800301d0  mov     ecx, 80004005h
0x1800301d5  jmp     loc_1800300DC
0x1800301da  mov     eax, cs:?g_cbW2KPreferredKey@BeforeKeyRotation@@3KA; ulong BeforeKeyRotation::g_cbW2KPreferredKey
0x1800301e0  lea     rcx, [rbp+4Fh+var_60]
0x1800301e4  mov     r9, qword ptr cs:?g_pbW2KPreferredKey@BeforeKeyRotation@@3PEAEEA.Data1; uchar * BeforeKeyRotation::g_pbW2KPreferredKey ...
0x1800301eb  add     eax, 0FFFFFFFCh
0x1800301ee  mov     [rsp+110h+var_C0], r12d; unsigned int
0x1800301f3  add     r9, 4; pbSecret
0x1800301f7  mov     qword ptr [rsp+110h+var_C8], rcx; pbOutput
0x1800301fc  xor     edx, edx; hHash
0x1800301fe  mov     dword ptr [rsp+110h+pcbResult], esi; cbHashObject
0x180030202  lea     rcx, [r14+60h]
0x180030206  mov     qword ptr [rsp+110h+cbOutput], rsi; pbHashObject
0x18003020b  mov     r8d, 8009h; unsigned int
0x180030211  mov     [rsp+110h+dwFlags], 20h ; ' '; cbInput
0x180030219  mov     qword ptr [rsp+110h+cbSecret], rcx; pbInput
0x18003021e  xor     ecx, ecx; hAlgorithm
0x180030220  mov     dword ptr [rsp+110h+pbSecret], eax; ULONG
0x180030224  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180030229  test    eax, eax
0x18003022b  jnz     short loc_180030235
0x18003022d  mov     r9d, 14D6h
0x180030233  jmp     short loc_1800301C9
0x180030235  mov     ebx, dword ptr [rbp+4Fh+Size]
0x180030238  lea     rdi, [r14+94h]
0x18003023f  mov     rdx, [rbp+4Fh+pSid]; Src
0x180030243  mov     r8d, ebx; Size
0x180030246  mov     rcx, rdi; void *
0x180030249  call    memcpy_0
0x18003024e  mov     rdx, [rbp+4Fh+Src]; Src
0x180030252  lea     rcx, [rbx+rdi]; void *
0x180030256  mov     r8, r13; Size
0x180030259  call    memcpy_0
0x18003025e  mov     [rsp+110h+var_C0], r12d; unsigned int
0x180030263  lea     rbx, [r14+60h]
0x180030267  lea     rax, [rbx+20h]
0x18003026b  xor     edx, edx; hHash
0x18003026d  mov     qword ptr [rsp+110h+var_C8], rax; pbOutput
0x180030272  lea     r9, [rbp+4Fh+var_60]; pbSecret
0x180030276  mov     eax, dword ptr [rbp+4Fh+Size]
0x180030279  xor     ecx, ecx; hAlgorithm
0x18003027b  mov     dword ptr [rsp+110h+pcbResult], esi; cbHashObject
0x18003027f  add     eax, r13d
0x180030282  mov     qword ptr [rsp+110h+cbOutput], rsi; pbHashObject
0x180030287  mov     r8d, 8009h; unsigned int
0x18003028d  mov     [rsp+110h+dwFlags], eax; cbInput
0x180030291  mov     qword ptr [rsp+110h+cbSecret], rdi; pbInput
0x180030296  mov     dword ptr [rsp+110h+pbSecret], r12d; ULONG
0x18003029b  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x1800302a0  xor     edi, edi
0x1800302a2  test    eax, eax
0x1800302a4  jnz     short loc_1800302CB
0x1800302a6  mov     r9d, 14F3h
0x1800302ac  lea     rdx, aEFail; "E_FAIL"
0x1800302b3  mov     ecx, 80004005h
0x1800302b8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800302bf  call    DebugTraceError
0x1800302c4  mov     edi, esi
0x1800302c6  jmp     loc_180030375
0x1800302cb  mov     rcx, [rbp+4Fh+hAlgorithm]; hAlgorithm
0x1800302cf  lea     rax, [rbp+4Fh+pbOutput]
0x1800302d3  mov     [rsp+110h+dwFlags], edi; dwFlags
0x1800302d7  lea     rdx, [rbp+4Fh+phKey]; phKey
0x1800302db  mov     [rsp+110h+cbSecret], r12d; cbSecret
0x1800302e0  xor     r9d, r9d; cbKeyObject
0x1800302e3  xor     r8d, r8d; pbKeyObject
0x1800302e6  mov     [rsp+110h+pbSecret], rax; pbSecret
0x1800302eb  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800302f2  nop     dword ptr [rax+rax+00h]
0x1800302f7  test    eax, eax
0x1800302f9  jns     short loc_18003030C
0x1800302fb  mov     r9d, 150Bh
0x180030301  lea     rdx, aNtstatus; "ntStatus"
0x180030308  mov     ecx, eax
0x18003030a  jmp     short loc_1800302B8
0x18003030c  mov     r8d, [r14+8]; cbInput
0x180030310  lea     rax, [rbp+4Fh+var_98]
0x180030314  mov     rcx, [rbp+4Fh+phKey]; hKey
0x180030318  xor     r9d, r9d; pPaddingInfo
0x18003031b  mov     [rsp+110h+var_C8], edi; dwFlags
0x18003031f  mov     rdx, rbx; pbInput
0x180030322  mov     [rsp+110h+pcbResult], rax; pcbResult
0x180030327  mov     [rsp+110h+cbOutput], r8d; cbOutput
0x18003032c  mov     qword ptr [rsp+110h+dwFlags], rbx; pbOutput
0x180030331  mov     [rsp+110h+cbSecret], edi; cbIV
0x180030335  mov     [rsp+110h+pbSecret], rdi; pbIV
0x18003033a  call    cs:__imp_BCryptEncrypt
0x180030341  nop     dword ptr [rax+rax+00h]
0x180030346  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18003034a  mov     ebx, eax
0x18003034c  call    cs:__imp_BCryptDestroyKey
0x180030353  nop     dword ptr [rax+rax+00h]
0x180030358  test    ebx, ebx
0x18003035a  jns     short loc_180030370
0x18003035c  mov     r9d, 1522h
0x180030362  lea     rdx, aNtstatus; "ntStatus"
0x180030369  mov     ecx, ebx
0x18003036b  jmp     loc_1800302B8
0x180030370  mov     edi, 1
0x180030375  mov     rbx, [rbp+4Fh+pSid]
0x180030379  lea     rax, [rbp+4Fh+pbOutput]
0x18003037d  mov     byte ptr [rax], 0
0x180030380  inc     rax
0x180030383  sub     r12, 1
0x180030387  jnz     short loc_18003037D
0x180030389  test    rbx, rbx
0x18003038c  jz      short loc_18003039D
0x18003038e  mov     rcx, rbx; hMem
0x180030391  call    cs:__imp_LocalFree
0x180030398  nop     dword ptr [rax+rax+00h]
0x18003039d  test    edi, edi
0x18003039f  jnz     short loc_1800303D4
0x1800303a1  mov     rcx, [r15]; hMem
0x1800303a4  test    rcx, rcx
0x1800303a7  jz      short loc_1800303BC
0x1800303a9  call    cs:__imp_LocalFree
0x1800303b0  nop     dword ptr [rax+rax+00h]
0x1800303b5  mov     qword ptr [r15], 0
0x1800303bc  test    esi, esi
0x1800303be  mov     eax, 0Dh
0x1800303c3  cmovz   esi, eax
0x1800303c6  mov     ecx, esi; dwErrCode
0x1800303c8  call    cs:__imp_SetLastError
0x1800303cf  nop     dword ptr [rax+rax+00h]
0x1800303d4  mov     eax, edi
0x1800303d6  jmp     short loc_1800303EB
0x1800303d8  mov     ecx, 57h ; 'W'; dwErrCode
0x1800303dd  call    cs:__imp_SetLastError
0x1800303e4  nop     dword ptr [rax+rax+00h]
0x1800303e9  xor     eax, eax
0x1800303eb  mov     rcx, [rbp+4Fh+var_48]
0x1800303ef  xor     rcx, rsp; StackCookie
0x1800303f2  call    __security_check_cookie
0x1800303f7  add     rsp, 0D8h
0x1800303fe  pop     r15
0x180030400  pop     r14
0x180030402  pop     r13
0x180030404  pop     r12
0x180030406  pop     rdi
0x180030407  pop     rsi
0x180030408  pop     rbx
0x180030409  pop     rbp
0x18003040a  retn
```
