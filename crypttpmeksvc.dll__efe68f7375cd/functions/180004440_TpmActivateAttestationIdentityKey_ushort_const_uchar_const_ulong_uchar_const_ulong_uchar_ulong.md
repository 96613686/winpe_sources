# _TpmActivateAttestationIdentityKey(ushort const *,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180004440`
- end: `0x180004781`
- name: `?_TpmActivateAttestationIdentityKey@@YAJPEBGPEBEK1KPEAPEAEPEAK@Z`
- size: `833`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName, PBYTE pbData, DWORD cbData, BYTE *, DWORD cbInput, BYTE **pcbResult, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004ed0`
- `0x180005380`

## callees

- `0x180003750`
- `0x180004440`
- `0x180008f38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004600`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000471b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000473f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004748`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004600`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000471b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000473f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004748`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000459c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800046b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000459c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800046b8`
- `ncrypt!NCryptImportKey` at `0x1800044ed`
- `ncrypt!NCryptImportKey` at `0x180004632`
- `ncrypt!NCryptImportKey` at `0x1800044ed`
- `ncrypt!NCryptImportKey` at `0x180004632`
- `ncrypt!NCryptOpenStorageProvider` at `0x180004496`
- `ncrypt!NCryptOpenStorageProvider` at `0x180004496`
- `ncrypt!NCryptGetProperty` at `0x18000457c`
- `ncrypt!NCryptGetProperty` at `0x18000457c`
- `ncrypt!NCryptFreeObject` at `0x180004758`
- `ncrypt!NCryptFreeObject` at `0x180004768`
- `ncrypt!NCryptFreeObject` at `0x180004758`
- `ncrypt!NCryptFreeObject` at `0x180004768`
- `ncrypt!NCryptDecrypt` at `0x18000469a`
- `ncrypt!NCryptDecrypt` at `0x18000469a`

## string_xrefs

- `0x1800044a5`: `ERROR: NCryptOpenStorageProvider. Hr=%x\n`
- `0x180004535`: `ERROR: _OpenAikKey. Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _TpmActivateAttestationIdentityKey(
        LPCWSTR pszKeyName,
        PBYTE pbData,
        DWORD cbData,
        BYTE *a4,
        DWORD cbInput,
        BYTE **pcbResult,
        unsigned int *a7)
{
  BYTE **v7; // r14
  unsigned int *v8; // r15
  BYTE *v12; // rsi
  BYTE *v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // eax
  NCRYPT_HANDLE v18; // r13
  DWORD v19; // ebx
  BYTE *v20; // r12
  SECURITY_STATUS Property; // eax
  unsigned int v22; // ebp
  unsigned int v23; // eax
  DWORD v24; // r12d
  unsigned int v25; // eax
  NCRYPT_KEY_HANDLE *phKey; // [rsp+20h] [rbp-78h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-58h] BYREF
  NCRYPT_KEY_HANDLE hKey[10]; // [rsp+48h] [rbp-50h] BYREF

  v7 = pcbResult;
  v8 = a7;
  phProvider = 0;
  hKey[0] = 0;
  *pcbResult = 0;
  *v8 = 0;
  v12 = 0;
  v13 = 0;
  v14 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0x40u);
  v15 = v14;
  if ( v14 )
  {
    ekTraceFmt(0x48012C2u, 1u, "ERROR: NCryptOpenStorageProvider. Hr=%x\n", v14);
    goto LABEL_28;
  }
  if ( pbData && cbData )
  {
    v16 = NCryptImportKey(phProvider, 0, L"OpaqueKeyBlob", 0, hKey, pbData, cbData, 0x40u);
    v15 = v16;
    if ( v16 )
    {
      ekTraceFmt(0x49712C2u, 1u, "ERROR: NCryptImportKey. Hr=%x\n", v16);
      goto LABEL_28;
    }
LABEL_19:
    v24 = 0;
    while ( 1 )
    {
      LODWORD(a7) = 0;
      v25 = NCryptDecrypt(hKey[0], a4, cbInput, 0, v13, v24, (DWORD *)&a7, 0x20u);
      v15 = v25;
      if ( v25 )
        break;
      if ( v13 )
      {
        *v7 = v13;
        v13 = 0;
        *v8 = v24;
        goto LABEL_28;
      }
      v24 = (unsigned int)a7;
      v13 = (BYTE *)LocalAlloc(0, (unsigned int)a7);
      if ( !v13 )
      {
        v15 = -2147024882;
        ekTraceFmt(0x4E812C2u, 1u, "ERROR: LocalAlloc. Return=%d\n", 2147942414LL);
        goto LABEL_28;
      }
    }
    ekTraceFmt(0x4DC12C2u, 1u, "ERROR: NCryptDecrypt. Hr=%x\n", v25);
    goto LABEL_28;
  }
  if ( pszKeyName )
  {
    v17 = _OpenAikKey(phProvider, pszKeyName, hKey);
    v15 = v17;
    if ( v17 )
    {
      ekTraceFmt(0x4A012C2u, 1u, "ERROR: _OpenAikKey. Hr=%x\n", v17);
      goto LABEL_28;
    }
    goto LABEL_19;
  }
  v18 = phProvider;
  v19 = 0;
  v20 = 0;
  while ( 1 )
  {
    LODWORD(pcbResult) = 0;
    Property = NCryptGetProperty(v18, L"PCP_EKPUB", v20, v19, (DWORD *)&pcbResult, 0x40u);
    v22 = Property;
    if ( Property )
    {
      LODWORD(phKey) = Property;
      ekTraceFmt(0x4912C2u, 1u, "ERROR: NCryptGetProperty(%ws) Hr=%x\n", L"PCP_EKPUB", phKey);
      goto LABEL_27;
    }
    if ( v20 )
      break;
    v19 = (unsigned int)pcbResult;
    v20 = (BYTE *)LocalAlloc(0, (unsigned int)pcbResult);
    if ( !v20 )
    {
      v22 = -2147024882;
      ekTraceFmt(0x5C12C2u, 1u, "ERROR: LocalAlloc. Return=%d\n", -2147024882);
LABEL_27:
      LocalFree(v20);
      v15 = v22;
      ekTraceFmt(0x4AE12C2u, 1u, "ERROR: _GetNCryptBlobProperty(EKPUB). Hr=%x\n", v22);
      goto LABEL_28;
    }
  }
  if ( v19 != (_DWORD)pcbResult )
  {
    v22 = -2147024736;
    ekTraceFmt(0x5112C2u, 1u, "ERROR: cbProp != cbPropT. Hr=%x\n", -2147024736);
    goto LABEL_27;
  }
  v12 = v20;
  LocalFree(0);
  v23 = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, hKey, v20, v19, 0x40u);
  v15 = v23;
  if ( !v23 )
    goto LABEL_19;
  ekTraceFmt(0x4BF12C2u, 1u, "ERROR: NCryptImportKey. Hr=%x\n", v23);
LABEL_28:
  LocalFree(v12);
  LocalFree(v13);
  if ( hKey[0] )
    NCryptFreeObject(hKey[0]);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return v15;
}

```

## disassembly

```asm
0x180004440  mov     [rsp+pbInput], r9
0x180004445  push    rbx
0x180004446  push    rbp
0x180004447  push    rsi
0x180004448  push    rdi
0x180004449  push    r12
0x18000444b  push    r13
0x18000444d  push    r14
0x18000444f  push    r15
0x180004451  sub     rsp, 58h
0x180004455  mov     r14, [rsp+98h+pcbResult]
0x18000445d  xor     eax, eax
0x18000445f  mov     r15, qword ptr [rsp+98h+arg_30]
0x180004467  mov     r12d, r8d
0x18000446a  mov     r13, rdx
0x18000446d  mov     [rsp+98h+phProvider], rax
0x180004472  mov     rbp, rcx
0x180004475  mov     [rsp+98h+hKey], rax
0x18000447a  mov     r8d, 40h ; '@'; dwFlags
0x180004480  mov     [r14], rax
0x180004483  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18000448a  mov     [r15], eax
0x18000448d  lea     rcx, [rsp+98h+phProvider]; phProvider
0x180004492  mov     esi, eax
0x180004494  mov     edi, eax
0x180004496  call    cs:__imp_NCryptOpenStorageProvider
0x18000449c  mov     ebx, eax
0x18000449e  test    eax, eax
0x1800044a0  jz      short loc_1800044B6
0x1800044a2  mov     r9d, eax
0x1800044a5  lea     r8, aErrorNcryptope; "ERROR: NCryptOpenStorageProvider. Hr=%x"...
0x1800044ac  mov     ecx, 48012C2h
0x1800044b1  jmp     loc_180004732
0x1800044b6  test    r13, r13
0x1800044b9  jz      short loc_180004511
0x1800044bb  test    r12d, r12d
0x1800044be  jz      short loc_180004511
0x1800044c0  mov     rcx, [rsp+98h+phProvider]; hProvider
0x1800044c5  lea     rax, [rsp+98h+hKey]
0x1800044ca  mov     [rsp+98h+dwFlags], 40h ; '@'; dwFlags
0x1800044d2  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x1800044d9  mov     [rsp+98h+cbData], r12d; cbData
0x1800044de  xor     r9d, r9d; pParameterList
0x1800044e1  mov     [rsp+98h+pbData], r13; pbData
0x1800044e6  xor     edx, edx; hImportKey
0x1800044e8  mov     [rsp+98h+phKey], rax; phKey
0x1800044ed  call    cs:__imp_NCryptImportKey
0x1800044f3  mov     ebx, eax
0x1800044f5  test    eax, eax
0x1800044f7  jz      loc_180004652
0x1800044fd  mov     r9d, eax
0x180004500  lea     r8, aErrorNcryptimp; "ERROR: NCryptImportKey. Hr=%x\n"
0x180004507  mov     ecx, 49712C2h
0x18000450c  jmp     loc_180004732
0x180004511  test    rbp, rbp
0x180004514  jz      short loc_180004546
0x180004516  mov     rcx, [rsp+98h+phProvider]; hProvider
0x18000451b  lea     r8, [rsp+98h+hKey]; phKey
0x180004520  mov     rdx, rbp; pszKeyName
0x180004523  call    ?_OpenAikKey@@YAK_KPEBGPEA_K@Z; _OpenAikKey(unsigned __int64,ushort const *,unsigned __int64 *)
0x180004528  mov     ebx, eax
0x18000452a  test    eax, eax
0x18000452c  jz      loc_180004652
0x180004532  mov     r9d, eax
0x180004535  lea     r8, aErrorOpenaikke; "ERROR: _OpenAikKey. Hr=%x\n"
0x18000453c  mov     ecx, 4A012C2h
0x180004541  jmp     loc_180004732
0x180004546  mov     r13, [rsp+98h+phProvider]
0x18000454b  xor     ebx, ebx
0x18000454d  xor     r12d, r12d
0x180004550  lea     rax, [rsp+98h+pcbResult]
0x180004558  mov     dword ptr [rsp+98h+pbData], 40h ; '@'; dwFlags
0x180004560  mov     r9d, ebx; cbOutput
0x180004563  mov     [rsp+98h+phKey], rax; pcbResult
0x180004568  mov     r8, r12; pbOutput
0x18000456b  mov     dword ptr [rsp+98h+pcbResult], esi
0x180004572  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x180004579  mov     rcx, r13; hObject
0x18000457c  call    cs:__imp_NCryptGetProperty
0x180004582  mov     ebp, eax
0x180004584  test    eax, eax
0x180004586  jnz     loc_1800046F7
0x18000458c  test    r12, r12
0x18000458f  jnz     short loc_1800045CF
0x180004591  mov     ebx, dword ptr [rsp+98h+pcbResult]
0x180004598  xor     ecx, ecx; uFlags
0x18000459a  mov     edx, ebx; uBytes
0x18000459c  call    cs:__imp_LocalAlloc
0x1800045a2  mov     r12, rax
0x1800045a5  test    rax, rax
0x1800045a8  jnz     short loc_180004550
0x1800045aa  mov     ebx, 8007000Eh
0x1800045af  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x1800045b6  mov     r9d, ebx
0x1800045b9  mov     edx, 1; unsigned int
0x1800045be  mov     ecx, 5C12C2h; unsigned int
0x1800045c3  mov     ebp, ebx
0x1800045c5  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800045ca  jmp     loc_180004718
0x1800045cf  cmp     ebx, dword ptr [rsp+98h+pcbResult]
0x1800045d6  jz      short loc_1800045FB
0x1800045d8  mov     ebp, 800700A0h
0x1800045dd  lea     r8, aErrorCbpropCbp; "ERROR: cbProp != cbPropT. Hr=%x\n"
0x1800045e4  mov     r9d, ebp
0x1800045e7  mov     edx, 1; unsigned int
0x1800045ec  mov     ecx, 5112C2h; unsigned int
0x1800045f1  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800045f6  jmp     loc_180004718
0x1800045fb  xor     ecx, ecx; hMem
0x1800045fd  mov     rsi, r12
0x180004600  call    cs:__imp_LocalFree
0x180004606  mov     rcx, [rsp+98h+phProvider]; hProvider
0x18000460b  lea     rax, [rsp+98h+hKey]
0x180004610  mov     [rsp+98h+dwFlags], 40h ; '@'; dwFlags
0x180004618  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18000461f  mov     [rsp+98h+cbData], ebx; cbData
0x180004623  xor     r9d, r9d; pParameterList
0x180004626  mov     [rsp+98h+pbData], r12; pbData
0x18000462b  xor     edx, edx; hImportKey
0x18000462d  mov     [rsp+98h+phKey], rax; phKey
0x180004632  call    cs:__imp_NCryptImportKey
0x180004638  mov     ebx, eax
0x18000463a  test    eax, eax
0x18000463c  jz      short loc_180004652
0x18000463e  mov     r9d, eax
0x180004641  lea     r8, aErrorNcryptimp; "ERROR: NCryptImportKey. Hr=%x\n"
0x180004648  mov     ecx, 4BF12C2h
0x18000464d  jmp     loc_180004732
0x180004652  mov     rbp, [rsp+98h+pbInput]
0x18000465a  xor     r12d, r12d
0x18000465d  mov     r8d, [rsp+98h+cbInput]; cbInput
0x180004665  lea     rax, [rsp+98h+arg_30]
0x18000466d  mov     rcx, [rsp+98h+hKey]; hKey
0x180004672  xor     r9d, r9d; pPaddingInfo
0x180004675  mov     [rsp+98h+dwFlags], 20h ; ' '; dwFlags
0x18000467d  mov     rdx, rbp; pbInput
0x180004680  mov     qword ptr [rsp+98h+cbData], rax; pcbResult
0x180004685  mov     dword ptr [rsp+98h+pbData], r12d; cbOutput
0x18000468a  mov     [rsp+98h+phKey], rdi; pbOutput
0x18000468f  mov     [rsp+98h+arg_30], 0
0x18000469a  call    cs:__imp_NCryptDecrypt
0x1800046a0  mov     ebx, eax
0x1800046a2  test    eax, eax
0x1800046a4  jnz     short loc_1800046E6
0x1800046a6  test    rdi, rdi
0x1800046a9  jnz     short loc_1800046DC
0x1800046ab  mov     r12d, [rsp+98h+arg_30]
0x1800046b3  xor     ecx, ecx; uFlags
0x1800046b5  mov     edx, r12d; uBytes
0x1800046b8  call    cs:__imp_LocalAlloc
0x1800046be  mov     rdi, rax
0x1800046c1  test    rax, rax
0x1800046c4  jnz     short loc_18000465D
0x1800046c6  mov     ebx, 8007000Eh
0x1800046cb  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x1800046d2  mov     r9d, ebx
0x1800046d5  mov     ecx, 4E812C2h
0x1800046da  jmp     short loc_180004732
0x1800046dc  mov     [r14], rdi
0x1800046df  xor     edi, edi
0x1800046e1  mov     [r15], r12d
0x1800046e4  jmp     short loc_18000473C
0x1800046e6  mov     r9d, eax
0x1800046e9  lea     r8, aErrorNcryptdec; "ERROR: NCryptDecrypt. Hr=%x\n"
0x1800046f0  mov     ecx, 4DC12C2h
0x1800046f5  jmp     short loc_180004732
0x1800046f7  lea     r9, aPcpEkpub; "PCP_EKPUB"
0x1800046fe  mov     dword ptr [rsp+98h+phKey], eax
0x180004702  lea     r8, aErrorNcryptget; "ERROR: NCryptGetProperty(%ws) Hr=%x\n"
0x180004709  mov     edx, 1; unsigned int
0x18000470e  mov     ecx, 4912C2h; unsigned int
0x180004713  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004718  mov     rcx, r12; hMem
0x18000471b  call    cs:__imp_LocalFree
0x180004721  mov     r9d, ebp
0x180004724  lea     r8, aErrorGetncrypt; "ERROR: _GetNCryptBlobProperty(EKPUB). H"...
0x18000472b  mov     ecx, 4AE12C2h; unsigned int
0x180004730  mov     ebx, ebp
0x180004732  mov     edx, 1; unsigned int
0x180004737  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000473c  mov     rcx, rsi; hMem
0x18000473f  call    cs:__imp_LocalFree
0x180004745  mov     rcx, rdi; hMem
0x180004748  call    cs:__imp_LocalFree
0x18000474e  mov     rcx, [rsp+98h+hKey]; hObject
0x180004753  test    rcx, rcx
0x180004756  jz      short loc_18000475E
0x180004758  call    cs:__imp_NCryptFreeObject
0x18000475e  mov     rcx, [rsp+98h+phProvider]; hObject
0x180004763  test    rcx, rcx
0x180004766  jz      short loc_18000476E
0x180004768  call    cs:__imp_NCryptFreeObject
0x18000476e  mov     eax, ebx
0x180004770  add     rsp, 58h
0x180004774  pop     r15
0x180004776  pop     r14
0x180004778  pop     r13
0x18000477a  pop     r12
0x18000477c  pop     rdi
0x18000477d  pop     rsi
0x18000477e  pop     rbp
0x18000477f  pop     rbx
0x180004780  retn
```
