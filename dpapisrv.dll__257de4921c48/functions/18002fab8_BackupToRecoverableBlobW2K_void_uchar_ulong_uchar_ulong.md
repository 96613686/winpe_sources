# BackupToRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18002fab8`
- end: `0x18002ffa4`
- name: `?BackupToRecoverableBlobW2K@@YAHPEAXPEAEKPEAPEAEPEAK@Z`
- size: `1260`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, unsigned int, HLOCAL *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800362c0`

## callees

- `0x180002310`
- `0x1800029d0`
- `0x180003080`
- `0x180007f10`
- `0x18001d810`
- `0x18002fab8`
- `0x180030ba8`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002fbb7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002fbb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fef1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fef1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fbd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fbd6`
- `bcrypt!BCryptEncrypt` at `0x18002fe96`
- `bcrypt!BCryptEncrypt` at `0x18002fe96`
- `bcrypt!BCryptGenRandom` at `0x18002fc9b`
- `bcrypt!BCryptGenRandom` at `0x18002fcd1`
- `bcrypt!BCryptGenRandom` at `0x18002fc9b`
- `bcrypt!BCryptGenRandom` at `0x18002fcd1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002fe43`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002fe43`
- `bcrypt!BCryptDestroyKey` at `0x18002fea8`
- `bcrypt!BCryptDestroyKey` at `0x18002fea8`

## string_xrefs

- `0x18002fb71`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18002fbf5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18002fc4d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18002fe10`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BackupToRecoverableBlobW2K(
        void *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        HLOCAL *a4,
        unsigned int *a5)
{
  size_t v5; // r12
  DWORD LastError; // eax
  __int64 v9; // r9
  unsigned int v10; // edi
  DWORD LengthSid; // eax
  unsigned __int8 *v12; // rax
  __int64 v13; // r14
  DWORD v14; // esi
  bool v15; // al
  UCHAR *v16; // r13
  int v17; // eax
  __int64 v18; // r9
  const char *v19; // rdx
  __int64 v20; // rcx
  char *v21; // rbx
  __int128 v22; // xmm0
  int v23; // eax
  UCHAR *v24; // rbx
  char *v25; // rdi
  __int64 v26; // rbx
  UCHAR *v27; // rbx
  __int64 v28; // r9
  const char *v29; // rdx
  __int64 v30; // rcx
  NTSTATUS v31; // eax
  NTSTATUS v32; // ebx
  __int64 v33; // rdx
  UCHAR *v34; // rax
  __int64 v35; // rcx
  UCHAR *v36; // rax
  UCHAR *v37; // rax
  ULONG v39; // [rsp+60h] [rbp-81h] BYREF
  size_t Size; // [rsp+64h] [rbp-7Dh]
  PSID pSid; // [rsp+70h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-69h] BYREF
  ULONG pcbResult; // [rsp+80h] [rbp-61h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+88h] [rbp-59h] BYREF
  PUCHAR pbOutput[2]; // [rsp+90h] [rbp-51h] BYREF
  void *Src; // [rsp+A0h] [rbp-41h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+A8h] [rbp-39h]
  char *v48; // [rsp+B0h] [rbp-31h]
  UCHAR pbSecret[24]; // [rsp+B8h] [rbp-29h] BYREF
  UCHAR v50[24]; // [rsp+D0h] [rbp-11h] BYREF

  v5 = a3;
  Src = a2;
  pSid = 0;
  phKey = 0;
  pcbResult = 0;
  hMem = 0;
  v39 = 0;
  *(GUID *)pbOutput = GUID_NULL;
  if ( !a2 || !a3 || !a4 || !a5 || a3 > 0x7FFFFFFF )
  {
    SetLastError(0x57u);
    return 0;
  }
  hAlgorithm = (BCRYPT_ALG_HANDLE)GetBCryptProviderHandle(0x6801u);
  if ( !hAlgorithm )
  {
    LastError = GetLastError();
    v9 = 764;
LABEL_8:
    DebugTraceError(LastError, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v9);
    return 0;
  }
  *a4 = 0;
  if ( !(unsigned int)GetTokenUserSid(a1, &pSid) )
  {
    LastError = GetLastError();
    v9 = 776;
    goto LABEL_8;
  }
  v10 = 0;
  LengthSid = GetLengthSid(pSid);
  LODWORD(Size) = LengthSid;
  *a5 = v5 + LengthSid + 148;
  v12 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)v5 + LengthSid + 148);
  *a4 = v12;
  v13 = 20;
  if ( v12 )
  {
    v14 = 0;
    v15 = CPreferredKeys::CopyLegacyKey((unsigned __int8 **)&hMem, &v39, (struct _GUID *)pbOutput);
    v16 = (UCHAR *)hMem;
    if ( !v15 )
    {
      v17 = GetLastError();
      v18 = 815;
      v19 = "GetLastError()";
LABEL_15:
      v20 = (unsigned int)v17;
LABEL_16:
      DebugTraceError(v20, v19, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v18);
      goto LABEL_35;
    }
    v21 = (char *)*a4;
    v22 = *(_OWORD *)pbOutput;
    v48 = v21;
    v23 = v5 + Size + 52;
    *(_DWORD *)v21 = 1;
    *((_DWORD *)v21 + 2) = v23;
    *((_DWORD *)v21 + 1) = v5;
    hMem = v21 + 28;
    *(_OWORD *)(v21 + 12) = v22;
    v17 = BCryptGenRandom(0, (PUCHAR)v21 + 28, 0x44u, 2u);
    if ( v17 < 0 )
    {
      v18 = 838;
LABEL_19:
      v19 = "ntStatus";
      goto LABEL_15;
    }
    v24 = (UCHAR *)(v21 + 96);
    pbOutput[0] = v24;
    v17 = BCryptGenRandom(0, v24, 0x20u, 2u);
    if ( v17 < 0 )
    {
      v18 = 852;
      goto LABEL_19;
    }
    if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v16, v39, (PUCHAR)hMem, 0x44u, 0, 0, pbSecret, 0x14u) )
    {
      v18 = 873;
LABEL_24:
      v19 = "E_FAIL";
      v20 = 2147500037LL;
      goto LABEL_16;
    }
    if ( !(unsigned int)ReusableHMAC(0, 0, 0x8009u, v16, v39, v24, 0x20u, 0, 0, v50, 0x14u) )
    {
      v18 = 894;
      goto LABEL_24;
    }
    v25 = (char *)(v24 + 52);
    v26 = (unsigned int)Size;
    memcpy_0(v25, pSid, (unsigned int)Size);
    memcpy_0(&v25[v26], Src, v5);
    v27 = pbOutput[0];
    if ( (unsigned int)ReusableHMAC(
                         0,
                         0,
                         0x8009u,
                         v50,
                         0x14u,
                         (PUCHAR)v25,
                         (int)v5 + (int)Size,
                         0,
                         0,
                         pbOutput[0] + 32,
                         0x14u) )
    {
      v31 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbSecret, 0x14u, 0);
      if ( v31 >= 0 )
      {
        v32 = BCryptEncrypt(phKey, v27, *((_DWORD *)v48 + 2), 0, 0, 0, v27, *((_DWORD *)v48 + 2), &pcbResult, 0);
        BCryptDestroyKey(phKey);
        if ( v32 >= 0 )
        {
          v10 = 1;
LABEL_35:
          if ( v16 )
          {
            v33 = v39;
            v34 = v16;
            if ( v39 )
            {
              do
              {
                *v34++ = 0;
                --v33;
              }
              while ( v33 );
            }
            LocalFree(v16);
          }
          goto LABEL_39;
        }
        v28 = 970;
        v29 = "ntStatus";
        v30 = (unsigned int)v32;
      }
      else
      {
        v28 = 947;
        v29 = "ntStatus";
        v30 = (unsigned int)v31;
      }
    }
    else
    {
      v28 = 923;
      v29 = "E_FAIL";
      v30 = 2147500037LL;
    }
    DebugTraceError(v30, v29, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v28);
    v10 = 0;
    goto LABEL_35;
  }
  v14 = 1130;
  DebugTraceError(1130, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 809);
LABEL_39:
  v35 = 20;
  v36 = pbSecret;
  do
  {
    *v36++ = 0;
    --v35;
  }
  while ( v35 );
  v37 = v50;
  do
  {
    *v37++ = 0;
    --v13;
  }
  while ( v13 );
  if ( pSid )
    LocalFree(pSid);
  if ( !v10 )
  {
    if ( *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
    if ( !v14 )
      v14 = 13;
    SetLastError(v14);
  }
  return v10;
}

```

## disassembly

```asm
0x18002fab8  push    rbp
0x18002faba  push    rbx
0x18002fabb  push    rsi
0x18002fabc  push    rdi
0x18002fabd  push    r12
0x18002fabf  push    r13
0x18002fac1  push    r14
0x18002fac3  push    r15
0x18002fac5  lea     rbp, [rsp-17h]
0x18002faca  sub     rsp, 0F8h
0x18002fad1  mov     rax, cs:__security_cookie
0x18002fad8  xor     rax, rsp
0x18002fadb  mov     [rbp+4Fh+var_48], rax
0x18002fadf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002fae6  mov     rbx, [rbp+4Fh+arg_20]
0x18002faea  xor     r13d, r13d
0x18002faed  mov     r12d, r8d
0x18002faf0  mov     r15, r9
0x18002faf3  mov     [rbp+4Fh+Src], rdx
0x18002faf7  mov     rdi, rcx
0x18002fafa  mov     [rbp+4Fh+pSid], r13
0x18002fafe  mov     [rbp+4Fh+phKey], r13
0x18002fb02  mov     [rbp+4Fh+var_B0], r13d
0x18002fb06  mov     [rbp+4Fh+hMem], r13
0x18002fb0a  mov     [rsp+130h+var_D0], r13d
0x18002fb0f  movdqu  xmmword ptr [rbp+4Fh+pbOutput], xmm0
0x18002fb14  test    rdx, rdx
0x18002fb17  jz      loc_18002FF70
0x18002fb1d  test    r8d, r8d
0x18002fb20  jz      loc_18002FF70
0x18002fb26  test    r9, r9
0x18002fb29  jz      loc_18002FF70
0x18002fb2f  test    rbx, rbx
0x18002fb32  jz      loc_18002FF70
0x18002fb38  cmp     r12d, 7FFFFFFFh
0x18002fb3f  ja      loc_18002FF70
0x18002fb45  xor     r8d, r8d
0x18002fb48  xor     edx, edx
0x18002fb4a  mov     ecx, 6801h; unsigned int
0x18002fb4f  call    GetBCryptProviderHandle
0x18002fb54  mov     [rbp+4Fh+hAlgorithm], rax
0x18002fb58  test    rax, rax
0x18002fb5b  jnz     short loc_18002FB89
0x18002fb5d  call    cs:__imp_GetLastError
0x18002fb64  nop     dword ptr [rax+rax+00h]
0x18002fb69  mov     r9d, 2FCh
0x18002fb6f  mov     ecx, eax
0x18002fb71  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002fb78  lea     rdx, aGetlasterror; "GetLastError()"
0x18002fb7f  call    DebugTraceError
0x18002fb84  jmp     loc_18002FF81
0x18002fb89  lea     rdx, [rbp+4Fh+pSid]
0x18002fb8d  mov     [r15], r13
0x18002fb90  mov     rcx, rdi
0x18002fb93  call    GetTokenUserSid
0x18002fb98  test    eax, eax
0x18002fb9a  jnz     short loc_18002FBB0
0x18002fb9c  call    cs:__imp_GetLastError
0x18002fba3  nop     dword ptr [rax+rax+00h]
0x18002fba8  mov     r9d, 308h
0x18002fbae  jmp     short loc_18002FB6F
0x18002fbb0  mov     rcx, [rbp+4Fh+pSid]; pSid
0x18002fbb4  mov     edi, r13d
0x18002fbb7  call    cs:__imp_GetLengthSid
0x18002fbbe  nop     dword ptr [rax+rax+00h]
0x18002fbc3  mov     dword ptr [rbp+4Fh+Size], eax
0x18002fbc6  lea     ecx, [r12+rax]
0x18002fbca  add     ecx, 94h
0x18002fbd0  mov     [rbx], ecx
0x18002fbd2  mov     edx, ecx; uBytes
0x18002fbd4  xor     ecx, ecx; uFlags
0x18002fbd6  call    cs:__imp_LocalAlloc
0x18002fbdd  nop     dword ptr [rax+rax+00h]
0x18002fbe2  mov     [r15], rax
0x18002fbe5  mov     r14d, 14h
0x18002fbeb  test    rax, rax
0x18002fbee  jnz     short loc_18002FC15
0x18002fbf0  mov     esi, 46Ah
0x18002fbf5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002fbfc  mov     ecx, esi
0x18002fbfe  lea     rdx, aDwlasterror; "dwLastError"
0x18002fc05  mov     r9d, 329h
0x18002fc0b  call    DebugTraceError
0x18002fc10  jmp     loc_18002FF00
0x18002fc15  lea     r8, [rbp+4Fh+pbOutput]; struct _GUID *
0x18002fc19  mov     esi, r13d
0x18002fc1c  lea     rdx, [rsp+130h+var_D0]; unsigned int *
0x18002fc21  lea     rcx, [rbp+4Fh+hMem]; unsigned __int8 **
0x18002fc25  call    ?CopyLegacyKey@CPreferredKeys@@SA_NPEAPEAEPEAKPEAU_GUID@@@Z; CPreferredKeys::CopyLegacyKey(uchar * *,ulong *,_GUID *)
0x18002fc2a  mov     r13, [rbp+4Fh+hMem]
0x18002fc2e  test    al, al
0x18002fc30  jnz     short loc_18002FC5E
0x18002fc32  call    cs:__imp_GetLastError
0x18002fc39  nop     dword ptr [rax+rax+00h]
0x18002fc3e  mov     r9d, 32Fh
0x18002fc44  lea     rdx, aGetlasterror; "GetLastError()"
0x18002fc4b  mov     ecx, eax
0x18002fc4d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002fc54  call    DebugTraceError
0x18002fc59  jmp     loc_18002FED1
0x18002fc5e  mov     rbx, [r15]
0x18002fc61  mov     r9d, 2; dwFlags
0x18002fc67  mov     eax, dword ptr [rbp+4Fh+Size]
0x18002fc6a  xor     ecx, ecx; hAlgorithm
0x18002fc6c  movups  xmm0, xmmword ptr [rbp+4Fh+pbOutput]
0x18002fc70  add     eax, 34h ; '4'
0x18002fc73  mov     [rbp+4Fh+var_80], rbx
0x18002fc77  add     eax, r12d
0x18002fc7a  mov     dword ptr [rbx], 1
0x18002fc80  mov     [rbx+8], eax
0x18002fc83  lea     r8d, [r9+42h]; cbBuffer
0x18002fc87  lea     rax, [rbx+1Ch]
0x18002fc8b  mov     [rbx+4], r12d
0x18002fc8f  mov     rdx, rax; pbBuffer
0x18002fc92  mov     [rbp+4Fh+hMem], rax
0x18002fc96  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x18002fc9b  call    cs:__imp_BCryptGenRandom
0x18002fca2  nop     dword ptr [rax+rax+00h]
0x18002fca7  test    eax, eax
0x18002fca9  jns     short loc_18002FCBA
0x18002fcab  mov     r9d, 346h
0x18002fcb1  lea     rdx, aNtstatus; "ntStatus"
0x18002fcb8  jmp     short loc_18002FC4B
0x18002fcba  mov     r9d, 2; dwFlags
0x18002fcc0  add     rbx, 60h ; '`'
0x18002fcc4  mov     rdx, rbx; pbBuffer
0x18002fcc7  mov     [rbp+4Fh+pbOutput], rbx
0x18002fccb  xor     ecx, ecx; hAlgorithm
0x18002fccd  lea     r8d, [r9+1Eh]; cbBuffer
0x18002fcd1  call    cs:__imp_BCryptGenRandom
0x18002fcd8  nop     dword ptr [rax+rax+00h]
0x18002fcdd  test    eax, eax
0x18002fcdf  jns     short loc_18002FCE9
0x18002fce1  mov     r9d, 354h
0x18002fce7  jmp     short loc_18002FCB1
0x18002fce9  mov     [rsp+130h+var_E0], r14d; unsigned int
0x18002fcee  lea     rax, [rbp+4Fh+var_78]
0x18002fcf2  mov     qword ptr [rsp+130h+var_E8], rax; pbOutput
0x18002fcf7  mov     r9, r13; pbSecret
0x18002fcfa  mov     rax, [rbp+4Fh+hMem]
0x18002fcfe  xor     edx, edx; hHash
0x18002fd00  mov     dword ptr [rsp+130h+pcbResult], esi; cbHashObject
0x18002fd04  xor     ecx, ecx; hAlgorithm
0x18002fd06  mov     qword ptr [rsp+130h+cbOutput], rsi; pbHashObject
0x18002fd0b  mov     r8d, 8009h; unsigned int
0x18002fd11  mov     [rsp+130h+dwFlags], 44h ; 'D'; cbInput
0x18002fd19  mov     qword ptr [rsp+130h+cbSecret], rax; pbInput
0x18002fd1e  mov     eax, [rsp+130h+var_D0]
0x18002fd22  mov     dword ptr [rsp+130h+pbSecret], eax; ULONG
0x18002fd26  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18002fd2b  test    eax, eax
0x18002fd2d  jnz     short loc_18002FD46
0x18002fd2f  mov     r9d, 369h
0x18002fd35  lea     rdx, aEFail; "E_FAIL"
0x18002fd3c  mov     ecx, 80004005h
0x18002fd41  jmp     loc_18002FC4D
0x18002fd46  mov     [rsp+130h+var_E0], r14d; unsigned int
0x18002fd4b  lea     rax, [rbp+4Fh+var_60]
0x18002fd4f  mov     qword ptr [rsp+130h+var_E8], rax; pbOutput
0x18002fd54  mov     r9, r13; pbSecret
0x18002fd57  mov     eax, [rsp+130h+var_D0]
0x18002fd5b  xor     edx, edx; hHash
0x18002fd5d  mov     dword ptr [rsp+130h+pcbResult], esi; cbHashObject
0x18002fd61  xor     ecx, ecx; hAlgorithm
0x18002fd63  mov     qword ptr [rsp+130h+cbOutput], rsi; pbHashObject
0x18002fd68  mov     r8d, 8009h; unsigned int
0x18002fd6e  mov     [rsp+130h+dwFlags], 20h ; ' '; cbInput
0x18002fd76  mov     qword ptr [rsp+130h+cbSecret], rbx; pbInput
0x18002fd7b  mov     dword ptr [rsp+130h+pbSecret], eax; ULONG
0x18002fd7f  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18002fd84  test    eax, eax
0x18002fd86  jnz     short loc_18002FD90
0x18002fd88  mov     r9d, 37Eh
0x18002fd8e  jmp     short loc_18002FD35
0x18002fd90  mov     rdx, [rbp+4Fh+pSid]; Src
0x18002fd94  lea     rdi, [rbx+34h]
0x18002fd98  mov     ebx, dword ptr [rbp+4Fh+Size]
0x18002fd9b  mov     rcx, rdi; void *
0x18002fd9e  mov     r8d, ebx; Size
0x18002fda1  call    memcpy_0
0x18002fda6  mov     rdx, [rbp+4Fh+Src]; Src
0x18002fdaa  lea     rcx, [rbx+rdi]; void *
0x18002fdae  mov     r8, r12; Size
0x18002fdb1  call    memcpy_0
0x18002fdb6  mov     rbx, [rbp+4Fh+pbOutput]
0x18002fdba  lea     r9, [rbp+4Fh+var_60]; pbSecret
0x18002fdbe  mov     [rsp+130h+var_E0], r14d; unsigned int
0x18002fdc3  xor     edx, edx; hHash
0x18002fdc5  xor     ecx, ecx; hAlgorithm
0x18002fdc7  mov     r8d, 8009h; unsigned int
0x18002fdcd  lea     rax, [rbx+20h]
0x18002fdd1  mov     qword ptr [rsp+130h+var_E8], rax; pbOutput
0x18002fdd6  mov     eax, dword ptr [rbp+4Fh+Size]
0x18002fdd9  mov     dword ptr [rsp+130h+pcbResult], esi; cbHashObject
0x18002fddd  add     eax, r12d
0x18002fde0  mov     qword ptr [rsp+130h+cbOutput], rsi; pbHashObject
0x18002fde5  mov     [rsp+130h+dwFlags], eax; cbInput
0x18002fde9  mov     qword ptr [rsp+130h+cbSecret], rdi; pbInput
0x18002fdee  mov     dword ptr [rsp+130h+pbSecret], r14d; ULONG
0x18002fdf3  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18002fdf8  xor     edi, edi
0x18002fdfa  test    eax, eax
0x18002fdfc  jnz     short loc_18002FE23
0x18002fdfe  mov     r9d, 39Bh
0x18002fe04  lea     rdx, aEFail; "E_FAIL"
0x18002fe0b  mov     ecx, 80004005h
0x18002fe10  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002fe17  call    DebugTraceError
0x18002fe1c  mov     edi, esi
0x18002fe1e  jmp     loc_18002FED1
0x18002fe23  mov     rcx, [rbp+4Fh+hAlgorithm]; hAlgorithm
0x18002fe27  lea     rax, [rbp+4Fh+var_78]
0x18002fe2b  mov     [rsp+130h+dwFlags], edi; dwFlags
0x18002fe2f  lea     rdx, [rbp+4Fh+phKey]; phKey
0x18002fe33  mov     [rsp+130h+cbSecret], r14d; cbSecret
0x18002fe38  xor     r9d, r9d; cbKeyObject
0x18002fe3b  xor     r8d, r8d; pbKeyObject
0x18002fe3e  mov     [rsp+130h+pbSecret], rax; pbSecret
0x18002fe43  call    cs:__imp_BCryptGenerateSymmetricKey
0x18002fe4a  nop     dword ptr [rax+rax+00h]
0x18002fe4f  test    eax, eax
0x18002fe51  jns     short loc_18002FE64
0x18002fe53  mov     r9d, 3B3h
0x18002fe59  lea     rdx, aNtstatus; "ntStatus"
0x18002fe60  mov     ecx, eax
0x18002fe62  jmp     short loc_18002FE10
0x18002fe64  mov     r8, [rbp+4Fh+var_80]
0x18002fe68  lea     rax, [rbp+4Fh+var_B0]
0x18002fe6c  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18002fe70  xor     r9d, r9d; pPaddingInfo
0x18002fe73  mov     [rsp+130h+var_E8], edi; dwFlags
0x18002fe77  mov     rdx, rbx; pbInput
0x18002fe7a  mov     [rsp+130h+pcbResult], rax; pcbResult
0x18002fe7f  mov     r8d, [r8+8]; cbInput
0x18002fe83  mov     [rsp+130h+cbOutput], r8d; cbOutput
0x18002fe88  mov     qword ptr [rsp+130h+dwFlags], rbx; pbOutput
0x18002fe8d  mov     [rsp+130h+cbSecret], edi; cbIV
0x18002fe91  mov     [rsp+130h+pbSecret], rdi; pbIV
0x18002fe96  call    cs:__imp_BCryptEncrypt
0x18002fe9d  nop     dword ptr [rax+rax+00h]
0x18002fea2  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18002fea6  mov     ebx, eax
0x18002fea8  call    cs:__imp_BCryptDestroyKey
0x18002feaf  nop     dword ptr [rax+rax+00h]
0x18002feb4  test    ebx, ebx
0x18002feb6  jns     short loc_18002FECC
0x18002feb8  mov     r9d, 3CAh
0x18002febe  lea     rdx, aNtstatus; "ntStatus"
0x18002fec5  mov     ecx, ebx
0x18002fec7  jmp     loc_18002FE10
0x18002fecc  mov     edi, 1
0x18002fed1  test    r13, r13
0x18002fed4  jz      short loc_18002FEFD
0x18002fed6  mov     edx, [rsp+130h+var_D0]
0x18002feda  mov     rax, r13
0x18002fedd  test    rdx, rdx
0x18002fee0  jz      short loc_18002FEEE
0x18002fee2  mov     [rax], sil
0x18002fee5  inc     rax
0x18002fee8  sub     rdx, 1
0x18002feec  jnz     short loc_18002FEE2
0x18002feee  mov     rcx, r13; hMem
0x18002fef1  call    cs:__imp_LocalFree
0x18002fef8  nop     dword ptr [rax+rax+00h]
0x18002fefd  xor     r13d, r13d
0x18002ff00  mov     rcx, r14
0x18002ff03  lea     rax, [rbp+4Fh+var_78]
0x18002ff07  mov     [rax], r13b
0x18002ff0a  inc     rax
0x18002ff0d  sub     rcx, 1
0x18002ff11  jnz     short loc_18002FF07
0x18002ff13  lea     rax, [rbp+4Fh+var_60]
0x18002ff17  mov     [rax], r13b
0x18002ff1a  inc     rax
0x18002ff1d  sub     r14, 1
0x18002ff21  jnz     short loc_18002FF17
0x18002ff23  cmp     [rbp+4Fh+pSid], r13
0x18002ff27  jz      short loc_18002FF39
0x18002ff29  mov     rcx, [rbp+4Fh+pSid]; hMem
0x18002ff2d  call    cs:__imp_LocalFree
0x18002ff34  nop     dword ptr [rax+rax+00h]
0x18002ff39  test    edi, edi
0x18002ff3b  jnz     short loc_18002FF6C
0x18002ff3d  mov     rcx, [r15]; hMem
0x18002ff40  test    rcx, rcx
0x18002ff43  jz      short loc_18002FF54
0x18002ff45  call    cs:__imp_LocalFree
0x18002ff4c  nop     dword ptr [rax+rax+00h]
0x18002ff51  mov     [r15], r13
0x18002ff54  test    esi, esi
0x18002ff56  mov     eax, 0Dh
0x18002ff5b  cmovz   esi, eax
0x18002ff5e  mov     ecx, esi; dwErrCode
0x18002ff60  call    cs:__imp_SetLastError
0x18002ff67  nop     dword ptr [rax+rax+00h]
0x18002ff6c  mov     eax, edi
0x18002ff6e  jmp     short loc_18002FF83
0x18002ff70  mov     ecx, 57h ; 'W'; dwErrCode
0x18002ff75  call    cs:__imp_SetLastError
0x18002ff7c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
