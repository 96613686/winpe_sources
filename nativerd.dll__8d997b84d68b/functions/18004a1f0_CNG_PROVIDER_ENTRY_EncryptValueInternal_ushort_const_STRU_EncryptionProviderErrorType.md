# CNG_PROVIDER_ENTRY::EncryptValueInternal(ushort const *,STRU *,EncryptionProviderErrorType *)

- ea: `0x18004a1f0`
- end: `0x18004a63c`
- name: `?EncryptValueInternal@CNG_PROVIDER_ENTRY@@UEAAJPEBGPEAVSTRU@@PEAW4EncryptionProviderErrorType@@@Z`
- size: `1100`
- prototype: `int(CNG_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004a1f0`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004a3f4`
- `msvcrt!memcpy_s` at `0x18004a3f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a58f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a58f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004a2a5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004a2a5`
- `bcrypt!BCryptEncrypt` at `0x18004a484`
- `bcrypt!BCryptEncrypt` at `0x18004a546`
- `bcrypt!BCryptEncrypt` at `0x18004a484`
- `bcrypt!BCryptEncrypt` at `0x18004a546`
- `bcrypt!BCryptGenRandom` at `0x18004a34d`
- `bcrypt!BCryptGenRandom` at `0x18004a34d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004a5f0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004a5f0`
- `iisutil!PuDbgPrintError` at `0x18004a323`
- `iisutil!PuDbgPrintError` at `0x18004a323`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18004a5ce`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18004a5ce`
- `iisutil!uuencode` at `0x18004a57e`
- `iisutil!uuencode` at `0x18004a57e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a5ff`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a60a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a614`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a5ff`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a60a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a614`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a339`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a3ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a3e3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a445`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a4f6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a50d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a56c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a5c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a339`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a3ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a3e3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a445`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a4f6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a50d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a56c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a5c0`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18004a237`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18004a242`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18004a24c`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18004a237`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18004a242`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18004a24c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004a2cc`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004a378`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004a4ad`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004a2cc`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004a378`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004a4ad`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004a5aa`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004a5aa`

## string_xrefs

- `0x18004a318`: `servercommon\inetsrv\iis\iisrearc\core\nativereader\dll\cngproviderentry.cxx`

## pseudocode

```c
__int64 __fastcall CNG_PROVIDER_ENTRY::EncryptValueInternal(
        CNG_PROVIDER_ENTRY *this,
        UCHAR *a2,
        struct STRU *a3,
        enum EncryptionProviderErrorType *a4)
{
  __int64 v8; // rdi
  NTSTATUS v9; // ebx
  int v10; // ebx
  signed int v11; // eax
  const char *v12; // rax
  __int64 v13; // r8
  ULONG v14; // ebx
  UCHAR *Ptr; // rax
  signed int v16; // eax
  unsigned int v17; // esi
  ULONG v18; // r13d
  void *v19; // rax
  unsigned int v20; // edi
  const void *v21; // rbx
  void *v22; // rax
  int v23; // esi
  int v24; // edi
  ULONG cbIV; // ebx
  UCHAR *pbIV; // rax
  NTSTATUS v27; // ebx
  int v28; // r13d
  signed int v29; // eax
  ULONG cbOutput; // esi
  char *v31; // rax
  ULONG v32; // edi
  UCHAR *pbOutput; // rbx
  UCHAR *v34; // rax
  unsigned int v35; // ebx
  unsigned __int8 *v36; // rax
  signed int LastError; // eax
  const char *v38; // rax
  ULONG pcbResult; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  ULONG cbInput; // [rsp+60h] [rbp-A0h]
  STRU *v43; // [rsp+68h] [rbp-98h]
  _BYTE v44[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v46[48]; // [rsp+D0h] [rbp-30h] BYREF

  v43 = a3;
  pcbResult = 0;
  phAlgorithm = 0;
  BUFFER::BUFFER((BUFFER *)v45);
  BUFFER::BUFFER((BUFFER *)v44);
  BUFFER::BUFFER((BUFFER *)v46);
  if ( a2 && a3 )
  {
    if ( *((_QWORD *)this + 5) && *((_QWORD *)this + 6) && *((_DWORD *)this + 81) )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&a2[2 * v8] );
      v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
      if ( v9 < 0 )
      {
        *(_DWORD *)a4 = 22;
LABEL_10:
        v10 = v9 | 0x10000000;
        goto LABEL_44;
      }
      if ( BUFFER::Resize((BUFFER *)v45, *((_DWORD *)this + 80)) )
      {
        v14 = *((_DWORD *)this + 80);
        Ptr = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
        v9 = BCryptGenRandom(phAlgorithm, Ptr, v14, 0);
        if ( v9 < 0 )
        {
          *(_DWORD *)a4 = 16;
          goto LABEL_10;
        }
        if ( BUFFER::Resize((BUFFER *)v44, *((_DWORD *)this + 83) + *((_DWORD *)this + 80)) )
        {
          v17 = *((_DWORD *)this + 80);
          v18 = 2 * v8 + 2;
          cbInput = v18;
          v19 = BUFFER::QueryPtr((BUFFER *)v45);
          v20 = *((_DWORD *)this + 80);
          v21 = v19;
          v22 = BUFFER::QueryPtr((BUFFER *)v44);
          memcpy_s(v22, v20, v21, v17);
          v23 = *((_DWORD *)this + 80);
          v10 = (*(__int64 (__fastcall **)(CNG_PROVIDER_ENTRY *, UCHAR *, _QWORD, _BYTE *, int))(*(_QWORD *)this + 48LL))(
                  this,
                  a2,
                  v18,
                  v44,
                  v23);
          if ( v10 >= 0 )
          {
            v24 = *((_DWORD *)this + 83);
            cbIV = *((_DWORD *)this + 80);
            pbIV = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
            v27 = BCryptEncrypt(*((BCRYPT_KEY_HANDLE *)this + 6), a2, v18, 0, pbIV, cbIV, 0, 0, &pcbResult, 1u);
            if ( v27 >= 0 )
            {
              v28 = v24 + v23;
              if ( BUFFER::Resize((BUFFER *)v44, v24 + v23 + pcbResult) )
              {
                cbOutput = pcbResult;
                v31 = (char *)BUFFER::QueryPtr((BUFFER *)v44);
                v32 = *((_DWORD *)this + 80);
                pbOutput = (UCHAR *)&v31[v28];
                v34 = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
                v9 = BCryptEncrypt(
                       *((BCRYPT_KEY_HANDLE *)this + 6),
                       a2,
                       cbInput,
                       0,
                       v34,
                       v32,
                       pbOutput,
                       cbOutput,
                       &pcbResult,
                       1u);
                if ( v9 < 0 )
                {
                  *(_DWORD *)a4 = 13;
                  goto LABEL_10;
                }
                v35 = v28 + pcbResult;
                v36 = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v44);
                if ( uuencode(v36, v35, (struct BUFFER *)v46, 0) )
                {
                  if ( BUFFER::QuerySize((BUFFER *)v46) >= 8 )
                  {
                    v38 = (const char *)BUFFER::QueryPtr((BUFFER *)v46);
                    v10 = STRU::CopyA(v43, v38);
                  }
                  else
                  {
                    v10 = -2147024883;
                  }
                }
                else
                {
                  *(_DWORD *)a4 = 2;
                  LastError = GetLastError();
                  v10 = LastError;
                  if ( LastError > 0 )
                    v10 = (unsigned __int16)LastError | 0x80070000;
                }
              }
              else
              {
                v29 = GetLastError();
                v10 = v29;
                if ( v29 > 0 )
                  v10 = (unsigned __int16)v29 | 0x80070000;
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v12 = "Failed to allocate buffEncryptedBlob buffer.\n";
                  v13 = 613;
                  goto LABEL_16;
                }
              }
            }
            else
            {
              *(_DWORD *)a4 = 13;
              v10 = v27 | 0x10000000;
            }
          }
          else
          {
            *(_DWORD *)a4 = 17;
          }
        }
        else
        {
          v16 = GetLastError();
          v10 = v16;
          if ( v16 > 0 )
            v10 = (unsigned __int16)v16 | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v12 = "Failed to allocate buffEncryptedBlob buffer.\n";
            v13 = 552;
            goto LABEL_16;
          }
        }
      }
      else
      {
        v11 = GetLastError();
        v10 = v11;
        if ( v11 > 0 )
          v10 = (unsigned __int16)v11 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v12 = "Failed to allocate IV buffer.\n";
          v13 = 523;
LABEL_16:
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\nativereader\\dll\\cngproviderentry.cxx",
            v13,
            "CNG_PROVIDER_ENTRY::EncryptValueInternal",
            v10,
            v12);
        }
      }
    }
    else
    {
      v10 = -2146893802;
    }
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_44:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v46);
  BUFFER::~BUFFER((BUFFER *)v44);
  BUFFER::~BUFFER((BUFFER *)v45);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004a1f0  push    rbp
0x18004a1f2  push    rbx
0x18004a1f3  push    rsi
0x18004a1f4  push    rdi
0x18004a1f5  push    r12
0x18004a1f7  push    r13
0x18004a1f9  push    r14
0x18004a1fb  push    r15
0x18004a1fd  lea     rbp, [rsp-18h]
0x18004a202  sub     rsp, 118h
0x18004a209  mov     rax, cs:__security_cookie
0x18004a210  xor     rax, rsp
0x18004a213  mov     [rbp+50h+var_50], rax
0x18004a217  mov     rbx, r8
0x18004a21a  mov     r14, rcx
0x18004a21d  xor     esi, esi
0x18004a21f  mov     [rsp+150h+var_E8], rbx
0x18004a224  lea     rcx, [rbp+50h+var_B0]
0x18004a228  mov     [rsp+150h+var_100], esi
0x18004a22c  mov     [rsp+150h+phAlgorithm], rsi
0x18004a231  mov     r15, r9
0x18004a234  mov     r12, rdx
0x18004a237  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18004a23d  lea     rcx, [rsp+150h+var_E0]
0x18004a242  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18004a248  lea     rcx, [rbp+50h+var_80]
0x18004a24c  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18004a252  test    r12, r12
0x18004a255  jz      loc_18004A5DF
0x18004a25b  test    rbx, rbx
0x18004a25e  jz      loc_18004A5DF
0x18004a264  cmp     [r14+28h], rsi
0x18004a268  jz      loc_18004A5D8
0x18004a26e  cmp     [r14+30h], rsi
0x18004a272  jz      loc_18004A5D8
0x18004a278  cmp     [r14+144h], esi
0x18004a27f  jz      loc_18004A5D8
0x18004a285  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004a289  inc     rdi
0x18004a28c  cmp     [r12+rdi*2], si
0x18004a291  jnz     short loc_18004A289
0x18004a293  xor     r9d, r9d; dwFlags
0x18004a296  lea     rdx, aRng; "RNG"
0x18004a29d  xor     r8d, r8d; pszImplementation
0x18004a2a0  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x18004a2a5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004a2ab  mov     ebx, eax
0x18004a2ad  test    eax, eax
0x18004a2af  jns     short loc_18004A2C1
0x18004a2b1  mov     dword ptr [r15], 16h
0x18004a2b8  bts     ebx, 1Ch
0x18004a2bc  jmp     loc_18004A5E4
0x18004a2c1  mov     edx, [r14+140h]
0x18004a2c8  lea     rcx, [rbp+50h+var_B0]
0x18004a2cc  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004a2d2  test    al, al
0x18004a2d4  jnz     short loc_18004A32E
0x18004a2d6  call    cs:__imp_GetLastError
0x18004a2dc  mov     ebx, eax
0x18004a2de  test    eax, eax
0x18004a2e0  jle     short loc_18004A2EB
0x18004a2e2  movzx   ebx, ax
0x18004a2e5  or      ebx, 80070000h
0x18004a2eb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a2f2  jz      loc_18004A5E4
0x18004a2f8  lea     rax, aFailedToAlloca; "Failed to allocate IV buffer.\n"
0x18004a2ff  mov     r8d, 20Bh
0x18004a305  mov     rcx, cs:g_pDebug
0x18004a30c  lea     r9, aCngProviderEnt_0; "CNG_PROVIDER_ENTRY::EncryptValueInterna"...
0x18004a313  mov     qword ptr [rsp+150h+cbIV], rax
0x18004a318  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004a31f  mov     dword ptr [rsp+150h+pbIV], ebx
0x18004a323  call    cs:__imp_PuDbgPrintError
0x18004a329  jmp     loc_18004A5E4
0x18004a32e  mov     ebx, [r14+140h]
0x18004a335  lea     rcx, [rbp+50h+var_B0]
0x18004a339  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a33f  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004a344  xor     r9d, r9d; dwFlags
0x18004a347  mov     rdx, rax; pbBuffer
0x18004a34a  mov     r8d, ebx; cbBuffer
0x18004a34d  call    cs:__imp_BCryptGenRandom
0x18004a353  mov     ebx, eax
0x18004a355  test    eax, eax
0x18004a357  jns     short loc_18004A365
0x18004a359  mov     dword ptr [r15], 10h
0x18004a360  jmp     loc_18004A2B8
0x18004a365  mov     edx, [r14+140h]
0x18004a36c  lea     rcx, [rsp+150h+var_E0]
0x18004a371  add     edx, [r14+14Ch]
0x18004a378  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004a37e  test    al, al
0x18004a380  jnz     short loc_18004A3B6
0x18004a382  call    cs:__imp_GetLastError
0x18004a388  mov     ebx, eax
0x18004a38a  test    eax, eax
0x18004a38c  jle     short loc_18004A397
0x18004a38e  movzx   ebx, ax
0x18004a391  or      ebx, 80070000h
0x18004a397  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a39e  jz      loc_18004A5E4
0x18004a3a4  lea     rax, aFailedToAlloca_0; "Failed to allocate buffEncryptedBlob bu"...
0x18004a3ab  mov     r8d, 228h
0x18004a3b1  jmp     loc_18004A305
0x18004a3b6  mov     esi, [r14+140h]
0x18004a3bd  lea     r13d, ds:2[rdi*2]
0x18004a3c5  lea     rcx, [rbp+50h+var_B0]
0x18004a3c9  mov     [rsp+150h+cbInput], r13d
0x18004a3ce  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a3d4  mov     edi, [r14+140h]
0x18004a3db  lea     rcx, [rsp+150h+var_E0]
0x18004a3e0  mov     rbx, rax
0x18004a3e3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a3e9  mov     r9d, esi; SourceSize
0x18004a3ec  mov     r8, rbx; Source
0x18004a3ef  mov     rcx, rax; Destination
0x18004a3f2  mov     edx, edi; DestinationSize
0x18004a3f4  call    cs:__imp_memcpy_s
0x18004a3fa  mov     rax, [r14]
0x18004a3fd  lea     r9, [rsp+150h+var_E0]
0x18004a402  mov     esi, [r14+140h]
0x18004a409  mov     r8d, r13d
0x18004a40c  mov     rdx, r12
0x18004a40f  mov     dword ptr [rsp+150h+pbIV], esi
0x18004a413  mov     rcx, r14
0x18004a416  mov     rax, [rax+30h]
0x18004a41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a41f  mov     ebx, eax
0x18004a421  test    eax, eax
0x18004a423  jns     short loc_18004A433
0x18004a425  mov     dword ptr [r15], 11h
0x18004a42c  xor     esi, esi
0x18004a42e  jmp     loc_18004A5E4
0x18004a433  mov     edi, [r14+14Ch]
0x18004a43a  lea     rcx, [rbp+50h+var_B0]
0x18004a43e  mov     ebx, [r14+140h]
0x18004a445  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a44b  mov     [rsp+150h+dwFlags], 1; dwFlags
0x18004a453  lea     rcx, [rsp+150h+var_100]
0x18004a458  mov     [rsp+150h+pcbResult], rcx; pcbResult
0x18004a45d  xor     r9d, r9d; pPaddingInfo
0x18004a460  mov     rcx, [r14+30h]; hKey
0x18004a464  mov     r8d, r13d; cbInput
0x18004a467  mov     [rsp+150h+cbOutput], 0; cbOutput
0x18004a46f  mov     rdx, r12; pbInput
0x18004a472  mov     [rsp+150h+pbOutput], 0; pbOutput
0x18004a47b  mov     [rsp+150h+cbIV], ebx; cbIV
0x18004a47f  mov     [rsp+150h+pbIV], rax; pbIV
0x18004a484  call    cs:__imp_BCryptEncrypt
0x18004a48a  mov     ebx, eax
0x18004a48c  test    eax, eax
0x18004a48e  jns     short loc_18004A49D
0x18004a490  mov     dword ptr [r15], 0Dh
0x18004a497  bts     ebx, 1Ch
0x18004a49b  jmp     short loc_18004A42C
0x18004a49d  mov     edx, [rsp+150h+var_100]
0x18004a4a1  lea     r13d, [rdi+rsi]
0x18004a4a5  add     edx, r13d
0x18004a4a8  lea     rcx, [rsp+150h+var_E0]
0x18004a4ad  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004a4b3  xor     esi, esi
0x18004a4b5  test    al, al
0x18004a4b7  jnz     short loc_18004A4ED
0x18004a4b9  call    cs:__imp_GetLastError
0x18004a4bf  mov     ebx, eax
0x18004a4c1  test    eax, eax
0x18004a4c3  jle     short loc_18004A4CE
0x18004a4c5  movzx   ebx, ax
0x18004a4c8  or      ebx, 80070000h
0x18004a4ce  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a4d5  jz      loc_18004A5E4
0x18004a4db  lea     rax, aFailedToAlloca_0; "Failed to allocate buffEncryptedBlob bu"...
0x18004a4e2  mov     r8d, 265h
0x18004a4e8  jmp     loc_18004A305
0x18004a4ed  mov     esi, [rsp+150h+var_100]
0x18004a4f1  lea     rcx, [rsp+150h+var_E0]
0x18004a4f6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a4fc  mov     edi, [r14+140h]
0x18004a503  lea     rcx, [rbp+50h+var_B0]
0x18004a507  mov     ebx, r13d
0x18004a50a  add     rbx, rax
0x18004a50d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a513  mov     r8d, [rsp+150h+cbInput]; cbInput
0x18004a518  lea     rcx, [rsp+150h+var_100]
0x18004a51d  mov     [rsp+150h+dwFlags], 1; dwFlags
0x18004a525  xor     r9d, r9d; pPaddingInfo
0x18004a528  mov     [rsp+150h+pcbResult], rcx; pcbResult
0x18004a52d  mov     rdx, r12; pbInput
0x18004a530  mov     rcx, [r14+30h]; hKey
0x18004a534  mov     [rsp+150h+cbOutput], esi; cbOutput
0x18004a538  mov     [rsp+150h+pbOutput], rbx; pbOutput
0x18004a53d  mov     [rsp+150h+cbIV], edi; cbIV
0x18004a541  mov     [rsp+150h+pbIV], rax; pbIV
0x18004a546  call    cs:__imp_BCryptEncrypt
0x18004a54c  xor     esi, esi
0x18004a54e  mov     ebx, eax
0x18004a550  test    eax, eax
0x18004a552  jns     short loc_18004A560
0x18004a554  mov     dword ptr [r15], 0Dh
0x18004a55b  jmp     loc_18004A2B8
0x18004a560  mov     ebx, [rsp+150h+var_100]
0x18004a564  lea     rcx, [rsp+150h+var_E0]
0x18004a569  add     ebx, r13d
0x18004a56c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a572  xor     r9d, r9d
0x18004a575  lea     r8, [rbp+50h+var_80]
0x18004a579  mov     rcx, rax
0x18004a57c  mov     edx, ebx
0x18004a57e  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x18004a584  test    eax, eax
0x18004a586  jnz     short loc_18004A5A6
0x18004a588  mov     dword ptr [r15], 2
0x18004a58f  call    cs:__imp_GetLastError
0x18004a595  mov     ebx, eax
0x18004a597  test    eax, eax
0x18004a599  jle     short loc_18004A5E4
0x18004a59b  movzx   ebx, ax
0x18004a59e  or      ebx, 80070000h
0x18004a5a4  jmp     short loc_18004A5E4
0x18004a5a6  lea     rcx, [rbp+50h+var_80]
0x18004a5aa  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18004a5b0  cmp     eax, 8
0x18004a5b3  jnb     short loc_18004A5BC
0x18004a5b5  mov     ebx, 8007000Dh
0x18004a5ba  jmp     short loc_18004A5E4
0x18004a5bc  lea     rcx, [rbp+50h+var_80]
0x18004a5c0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a5c6  mov     rcx, [rsp+150h+var_E8]
0x18004a5cb  mov     rdx, rax
0x18004a5ce  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18004a5d4  mov     ebx, eax
0x18004a5d6  jmp     short loc_18004A5E4
0x18004a5d8  mov     ebx, 80090016h
0x18004a5dd  jmp     short loc_18004A5E4
0x18004a5df  mov     ebx, 80070057h
0x18004a5e4  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004a5e9  test    rcx, rcx
0x18004a5ec  jz      short loc_18004A5FB
0x18004a5ee  xor     edx, edx; dwFlags
0x18004a5f0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004a5f6  mov     [rsp+150h+phAlgorithm], rsi
0x18004a5fb  lea     rcx, [rbp+50h+var_80]
0x18004a5ff  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a605  lea     rcx, [rsp+150h+var_E0]
0x18004a60a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a610  lea     rcx, [rbp+50h+var_B0]
0x18004a614  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a61a  mov     eax, ebx
0x18004a61c  mov     rcx, [rbp+50h+var_50]
0x18004a620  xor     rcx, rsp; StackCookie
0x18004a623  call    __security_check_cookie
0x18004a628  add     rsp, 118h
0x18004a62f  pop     r15
0x18004a631  pop     r14
0x18004a633  pop     r13
0x18004a635  pop     r12
0x18004a637  pop     rdi
0x18004a638  pop     rsi
0x18004a639  pop     rbx
0x18004a63a  pop     rbp
0x18004a63b  retn
```
