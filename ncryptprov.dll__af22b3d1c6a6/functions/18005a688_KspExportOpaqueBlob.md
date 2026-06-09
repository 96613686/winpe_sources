# KspExportOpaqueBlob

- ea: `0x18005a688`
- end: `0x18005ac9a`
- name: `KspExportOpaqueBlob`
- size: `1554`
- prototype: `__int64 __fastcall(__int64, __int64, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029600`

## callees

- `0x180005290`
- `0x1800090c0`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180010530`
- `0x180038970`
- `0x1800398b0`
- `0x18005a084`
- `0x18005a554`
- `0x18005a688`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005aa83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005aa83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a92a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ac20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a92a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ac20`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005aa4d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005aa4d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18005a901`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18005a901`
- `RPCRT4!UuidToStringW` at `0x18005a835`
- `RPCRT4!UuidToStringW` at `0x18005a835`
- `RPCRT4!RpcStringFreeW` at `0x18005a86a`
- `RPCRT4!RpcStringFreeW` at `0x18005a8ab`
- `RPCRT4!RpcStringFreeW` at `0x18005a86a`
- `RPCRT4!RpcStringFreeW` at `0x18005a8ab`

## string_xrefs

- `0x18005a718`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005a76a`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`

## pseudocode

```c
__int64 __fastcall KspExportOpaqueBlob(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  void *v6; // r13
  DWORD v7; // r12d
  DWORD v8; // r15d
  DWORD LastError; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // eax
  int v13; // r8d
  DWORD v14; // eax
  DWORD DpapiUserDirectory; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // r13d
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned int v21; // eax
  DWORD FileSize; // eax
  __int64 v23; // r14
  bool v24; // zf
  __int64 v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // edx
  unsigned int v28; // ecx
  DWORD i; // edx
  unsigned int v30; // r8d
  void *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  _DWORD *v34; // r12
  char *v35; // rbx
  __int64 v36; // rax
  DWORD v37; // esi
  char *v38; // rbx
  unsigned int v39; // eax
  char *v40; // rdi
  unsigned int v41; // eax
  size_t v42; // r8
  __int64 v43; // rbx
  _DWORD *v44; // r13
  unsigned int v45; // r12d
  __int64 v46; // rax
  size_t v47; // r8
  HANDLE v48; // rdx
  DWORD v49; // edi
  HANDLE v50; // rcx
  HANDLE v51; // rcx
  __int64 v52; // rdx
  _BYTE *v53; // rax
  int lpOverlapped; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v58; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v60; // [rsp+70h] [rbp-90h]
  DWORD NumberOfBytesRead; // [rsp+74h] [rbp-8Ch] BYREF
  void *v62; // [rsp+78h] [rbp-88h]
  _WORD *v63; // [rsp+80h] [rbp-80h]
  __int64 v64; // [rsp+88h] [rbp-78h]
  unsigned int *v65; // [rsp+90h] [rbp-70h]
  __int128 v66; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hFile[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int nNumberOfBytesToRead[72]; // [rsp+C0h] [rbp-40h]
  _WORD v69[40]; // [rsp+1E0h] [rbp+E0h] BYREF

  v60 = a4;
  v6 = 0;
  v62 = a3;
  v7 = 0;
  v64 = a2;
  v8 = 0;
  v65 = a5;
  v63 = 0;
  NumberOfBytesRead = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v58 = 0;
  LODWORD(StringUuid) = 0;
  if ( !*(_QWORD *)(a2 + 224) )
  {
    LastError = -2146893813;
    v10 = 444;
    v11 = 2148073483LL;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v10);
    goto LABEL_68;
  }
  if ( *(_DWORD *)(a2 + 32) )
  {
    LastError = -2146893783;
    v10 = 451;
    v11 = 2148073513LL;
    goto LABEL_3;
  }
  v12 = ReadLegacyKeyFile(a1, a2, 0, *(_QWORD *)(a2 + 72), &StringUuid, &Src, &Size);
  if ( v12 )
  {
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 472);
    Src = 0;
  }
  else
  {
    v6 = Src;
  }
  v14 = BuildMasterKeyFileList(a2, (_DWORD)v6, v13, (unsigned int)&v66, lpOverlapped, (__int64)&v58);
  LastError = v14;
  if ( v14 )
  {
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 498);
    v8 = v58;
    goto LABEL_67;
  }
  DpapiUserDirectory = GetDpapiUserDirectory(*(void **)(a2 + 72));
  v8 = v58;
  LastError = DpapiUserDirectory;
  if ( DpapiUserDirectory )
  {
    v16 = 514;
    v17 = DpapiUserDirectory;
LABEL_64:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v16);
    goto LABEL_65;
  }
  LODWORD(StringUuid) = 1;
  if ( !v58 )
  {
LABEL_63:
    LastError = -2146893811;
    v16 = 563;
    v17 = 2148073485LL;
    goto LABEL_64;
  }
  v18 = (int)StringUuid;
  do
  {
    StringUuid = 0;
    v19 = UuidToStringW((const UUID *)&hFile[5 * v7 - 2], &StringUuid);
    if ( v19 )
      goto LABEL_21;
    LODWORD(v20) = 0;
    if ( StringUuid )
    {
      v20 = -1;
      do
        ++v20;
      while ( StringUuid[v20] );
      if ( (unsigned int)v20 >= 0x28 )
      {
        RpcStringFreeW(&StringUuid);
        v19 = -2146893784;
LABEL_21:
        DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 526);
        goto LABEL_28;
      }
    }
    memcpy_0(v69, StringUuid, 2LL * (unsigned int)(v20 + 1));
    RpcStringFreeW(&StringUuid);
    v21 = OpenFileInStorageArea(0, 0x80000000, v63, v69, &hFile[5 * v7]);
    if ( v21 )
    {
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 539);
      hFile[5 * v7] = (HANDLE)-1LL;
    }
    else
    {
      FileSize = GetFileSize(hFile[5 * v7], 0);
      nNumberOfBytesToRead[10 * v7] = FileSize;
      if ( FileSize == -1 || FileSize - 44 > 0xFFFD4 )
      {
        CloseHandle(hFile[5 * v7]);
        hFile[5 * v7] = (HANDLE)-1LL;
        nNumberOfBytesToRead[10 * v7] = 0;
      }
      else
      {
        v18 = 0;
      }
    }
LABEL_28:
    ++v7;
  }
  while ( v7 < v8 );
  v23 = v64;
  v24 = v18 == 0;
  v6 = Src;
  if ( !v24 )
    goto LABEL_63;
  v25 = -1;
  LastError = 0;
  do
    ++v25;
  while ( *(_WORD *)(*(_QWORD *)(v64 + 8) + 2 * v25) );
  v26 = 2 * v25 + 68;
  if ( (unsigned int)(2 * v25) >= 0xFFFFFFBC
    || (v27 = v26 + *(_DWORD *)(v64 + 232), v27 < v26)
    || (v28 = v27 + Size, v27 + (unsigned int)Size < v27) )
  {
    v17 = 534;
    LastError = 534;
    v16 = 578;
    goto LABEL_64;
  }
  for ( i = 0; i < v8; ++i )
  {
    if ( hFile[5 * i] != (HANDLE)-1LL )
    {
      v30 = v28 + 16;
      if ( v28 + 16 < v28 || (v28 = v30 + nNumberOfBytesToRead[10 * i], v28 < v30) )
      {
        v17 = 534;
        LastError = 534;
        v16 = 591;
        goto LABEL_64;
      }
    }
  }
  *v65 = v28;
  if ( v62 )
  {
    if ( v60 >= v28 )
    {
      while ( LastError < v8 )
      {
        if ( hFile[5 * LastError] != (HANDLE)-1LL )
        {
          v31 = (void *)SafeAllocaAllocateFromHeap(nNumberOfBytesToRead[10 * LastError]);
          hFile[5 * LastError + 1] = v31;
          if ( !v31 )
          {
            LastError = -2146893810;
            goto LABEL_65;
          }
          if ( !ReadFile(hFile[5 * LastError], v31, nNumberOfBytesToRead[10 * LastError], &NumberOfBytesRead, 0) )
          {
            LastError = GetLastError();
            DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 634);
            KspCryptAuditKeyFileOperation(0, v33, 0, 0, 0, 2458, LastError);
            goto LABEL_65;
          }
          KspCryptAuditKeyFileOperation(1, v32, 0, 0, 0, 2458, 0);
        }
        ++LastError;
      }
      v34 = v62;
      v35 = (char *)v62 + 68;
      memset_0(v62, 0, 0x44u);
      v36 = -1;
      *v34 = 826427725;
      v37 = 0;
      do
        ++v36;
      while ( *(_WORD *)(*(_QWORD *)(v23 + 8) + 2 * v36) );
      v34[1] = v36;
      memcpy_0(v35, *(const void **)(v23 + 8), 2LL * (unsigned int)v36);
      v38 = &v35[2 * v34[1]];
      v39 = *(_DWORD *)(v23 + 232);
      v34[3] = v39;
      memcpy_0(v38, *(const void **)(v23 + 224), v39);
      v40 = &v38[v34[3]];
      if ( v6 )
      {
        v41 = Size;
        v42 = (unsigned int)Size;
        v34[5] = Size;
        v43 = v41;
        memcpy_0(v40, v6, v42);
        v40 += v43;
      }
      v44 = v62;
      v45 = 0;
      do
      {
        if ( hFile[5 * v37] != (HANDLE)-1LL )
        {
          v46 = v45++;
          *(_OWORD *)v40 = *(_OWORD *)&hFile[5 * v37 - 2];
          v47 = nNumberOfBytesToRead[10 * v37];
          v48 = hFile[5 * v37 + 1];
          v44[v46 + 6] = v47;
          memcpy_0(v40 + 16, v48, v47);
          v40 += nNumberOfBytesToRead[10 * v37] + 16;
        }
        ++v37;
      }
      while ( v37 < v8 );
      v6 = Src;
      LastError = 0;
    }
    else
    {
      LastError = -2146893784;
    }
  }
LABEL_65:
  if ( v63 )
    MSCryptFree(v63);
LABEL_67:
  v7 = Size;
LABEL_68:
  v49 = 0;
  if ( v8 )
  {
    do
    {
      v50 = hFile[5 * v49];
      if ( v50 != (HANDLE)-1LL )
        CloseHandle(v50);
      v51 = hFile[5 * v49 + 1];
      if ( v51 )
        MSCryptFree(v51);
      ++v49;
    }
    while ( v49 < v8 );
    v7 = Size;
  }
  if ( v6 )
  {
    v52 = v7;
    v53 = v6;
    if ( v7 )
    {
      do
      {
        *v53++ = 0;
        --v52;
      }
      while ( v52 );
    }
    MSCryptFree(v6);
  }
  return LastError;
}

```

## disassembly

```asm
0x18005a688  mov     [rsp-8+arg_0], rbx
0x18005a68d  push    rbp
0x18005a68e  push    rsi
0x18005a68f  push    rdi
0x18005a690  push    r12
0x18005a692  push    r13
0x18005a694  push    r14
0x18005a696  push    r15
0x18005a698  lea     rbp, [rsp-140h]
0x18005a6a0  sub     rsp, 240h
0x18005a6a7  mov     rax, cs:__security_cookie
0x18005a6ae  xor     rax, rsp
0x18005a6b1  mov     [rbp+170h+var_40], rax
0x18005a6b8  mov     rax, [rbp+170h+arg_20]
0x18005a6bf  xor     ebx, ebx
0x18005a6c1  mov     r14, rdx
0x18005a6c4  mov     [rsp+270h+var_200], r9d
0x18005a6c9  mov     r13d, ebx
0x18005a6cc  mov     [rsp+270h+var_1F8], r8
0x18005a6d1  mov     r12d, ebx
0x18005a6d4  mov     [rbp+170h+var_1E8], rdx
0x18005a6d8  mov     r15d, ebx
0x18005a6db  mov     [rbp+170h+var_1E0], rax
0x18005a6df  mov     [rbp+170h+var_1F0], rbx
0x18005a6e3  mov     [rsp+270h+NumberOfBytesRead], ebx
0x18005a6e7  mov     [rsp+270h+Src], rbx
0x18005a6ec  mov     dword ptr [rsp+270h+Size], ebx
0x18005a6f0  mov     [rsp+270h+var_210], ebx
0x18005a6f4  mov     dword ptr [rsp+270h+StringUuid], ebx
0x18005a6f8  cmp     [rdx+0E0h], rbx
0x18005a6ff  jnz     short loc_18005A729
0x18005a701  mov     ebx, 8009000Bh
0x18005a706  mov     r9d, 1BCh
0x18005a70c  mov     ecx, 8009000Bh
0x18005a711  lea     rdx, aStatus; "Status"
0x18005a718  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a71f  call    DebugTraceError
0x18005a724  jmp     loc_18005AC06
0x18005a729  cmp     [rdx+20h], ebx
0x18005a72c  jz      short loc_18005A740
0x18005a72e  mov     ebx, 80090029h
0x18005a733  mov     r9d, 1C3h
0x18005a739  mov     ecx, 80090029h
0x18005a73e  jmp     short loc_18005A711
0x18005a740  mov     r9, [rdx+48h]
0x18005a744  lea     rax, [rsp+270h+Size]
0x18005a749  mov     [rsp+270h+var_240], rax
0x18005a74e  xor     r8d, r8d
0x18005a751  lea     rax, [rsp+270h+Src]
0x18005a756  mov     [rsp+270h+var_248], rax
0x18005a75b  lea     rax, [rsp+270h+StringUuid]
0x18005a760  mov     [rsp+270h+lpOverlapped], rax
0x18005a765  call    ReadLegacyKeyFile
0x18005a76a  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a771  lea     rsi, aStatus; "Status"
0x18005a778  test    eax, eax
0x18005a77a  jz      short loc_18005A796
0x18005a77c  mov     r9d, 1D8h
0x18005a782  mov     r8, rdi
0x18005a785  mov     rdx, rsi
0x18005a788  mov     ecx, eax
0x18005a78a  call    DebugTraceError
0x18005a78f  mov     [rsp+270h+Src], rbx
0x18005a794  jmp     short loc_18005A7A0
0x18005a796  mov     r13, [rsp+270h+Src]
0x18005a79b  mov     [rsp+270h+Src], r13
0x18005a7a0  lea     rax, [rsp+270h+var_210]
0x18005a7a5  mov     rdx, r13
0x18005a7a8  lea     r9, [rbp+170h+var_1D0]
0x18005a7ac  mov     [rsp+270h+var_248], rax
0x18005a7b1  mov     rcx, r14
0x18005a7b4  call    BuildMasterKeyFileList
0x18005a7b9  mov     ebx, eax
0x18005a7bb  test    eax, eax
0x18005a7bd  jz      short loc_18005A7DC
0x18005a7bf  mov     r9d, 1F2h
0x18005a7c5  mov     r8, rdi
0x18005a7c8  mov     rdx, rsi
0x18005a7cb  mov     ecx, eax
0x18005a7cd  call    DebugTraceError
0x18005a7d2  mov     r15d, [rsp+270h+var_210]
0x18005a7d7  jmp     loc_18005AC01
0x18005a7dc  mov     rcx, [r14+48h]; Src
0x18005a7e0  lea     rdx, [rbp+170h+var_1F0]
0x18005a7e4  call    GetDpapiUserDirectory
0x18005a7e9  mov     r15d, [rsp+270h+var_210]
0x18005a7ee  mov     ebx, eax
0x18005a7f0  xor     eax, eax
0x18005a7f2  test    ebx, ebx
0x18005a7f4  jz      short loc_18005A803
0x18005a7f6  mov     r9d, 202h
0x18005a7fc  mov     ecx, ebx
0x18005a7fe  jmp     loc_18005ABE5
0x18005a803  mov     dword ptr [rsp+270h+StringUuid], 1
0x18005a80b  test    r15d, r15d
0x18005a80e  jz      loc_18005ABD5
0x18005a814  mov     r13d, dword ptr [rsp+270h+StringUuid]
0x18005a819  xor     r14d, r14d
0x18005a81c  mov     eax, r12d
0x18005a81f  lea     rcx, [rbp+170h+var_1D0]
0x18005a823  lea     rdx, [rsp+270h+StringUuid]; StringUuid
0x18005a828  mov     [rsp+270h+StringUuid], r14
0x18005a82d  lea     rbx, [rax+rax*4]
0x18005a831  lea     rcx, [rcx+rbx*8]; Uuid
0x18005a835  call    cs:__imp_UuidToStringW
0x18005a83c  nop     dword ptr [rax+rax+00h]
0x18005a841  test    eax, eax
0x18005a843  jnz     short loc_18005A87B
0x18005a845  mov     rdx, [rsp+270h+StringUuid]; Src
0x18005a84a  mov     eax, r14d
0x18005a84d  test    rdx, rdx
0x18005a850  jz      short loc_18005A893
0x18005a852  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a856  inc     rax
0x18005a859  cmp     [rdx+rax*2], r14w
0x18005a85e  jnz     short loc_18005A856
0x18005a860  cmp     eax, 28h ; '('
0x18005a863  jb      short loc_18005A893
0x18005a865  lea     rcx, [rsp+270h+StringUuid]; String
0x18005a86a  call    cs:__imp_RpcStringFreeW
0x18005a871  nop     dword ptr [rax+rax+00h]
0x18005a876  mov     eax, 80090028h
0x18005a87b  mov     r9d, 20Eh
0x18005a881  mov     r8, rdi
0x18005a884  mov     rdx, rsi
0x18005a887  mov     ecx, eax
0x18005a889  call    DebugTraceError
0x18005a88e  jmp     loc_18005A944
0x18005a893  lea     r8d, [rax+1]
0x18005a897  add     r8, r8; Size
0x18005a89a  lea     rcx, [rbp+170h+var_90]; void *
0x18005a8a1  call    memcpy_0
0x18005a8a6  lea     rcx, [rsp+270h+StringUuid]; String
0x18005a8ab  call    cs:__imp_RpcStringFreeW
0x18005a8b2  nop     dword ptr [rax+rax+00h]
0x18005a8b7  mov     r8, [rbp+170h+var_1F0]
0x18005a8bb  lea     rax, [rbp+rbx*8+170h+hFile]
0x18005a8c0  lea     r9, [rbp+170h+var_90]
0x18005a8c7  mov     [rsp+270h+lpOverlapped], rax
0x18005a8cc  mov     edx, 80000000h
0x18005a8d1  xor     ecx, ecx
0x18005a8d3  call    OpenFileInStorageArea
0x18005a8d8  test    eax, eax
0x18005a8da  jz      short loc_18005A8FA
0x18005a8dc  mov     r9d, 21Bh
0x18005a8e2  mov     r8, rdi
0x18005a8e5  mov     rdx, rsi
0x18005a8e8  mov     ecx, eax
0x18005a8ea  call    DebugTraceError
0x18005a8ef  mov     [rbp+rbx*8+170h+hFile], 0FFFFFFFFFFFFFFFFh
0x18005a8f8  jmp     short loc_18005A944
0x18005a8fa  mov     rcx, [rbp+rbx*8+170h+hFile]; hFile
0x18005a8ff  xor     edx, edx; lpFileSizeHigh
0x18005a901  call    cs:__imp_GetFileSize
0x18005a908  nop     dword ptr [rax+rax+00h]
0x18005a90d  mov     [rbp+rbx*8+170h+nNumberOfBytesToRead], eax
0x18005a911  cmp     eax, 0FFFFFFFFh
0x18005a914  jz      short loc_18005A925
0x18005a916  add     eax, 0FFFFFFD4h
0x18005a919  cmp     eax, 0FFFD4h
0x18005a91e  ja      short loc_18005A925
0x18005a920  mov     r13d, r14d
0x18005a923  jmp     short loc_18005A944
0x18005a925  mov     rcx, [rbp+rbx*8+170h+hFile]; hObject
0x18005a92a  call    cs:__imp_CloseHandle
0x18005a931  nop     dword ptr [rax+rax+00h]
0x18005a936  mov     [rbp+rbx*8+170h+hFile], 0FFFFFFFFFFFFFFFFh
0x18005a93f  mov     [rbp+rbx*8+170h+nNumberOfBytesToRead], r14d
0x18005a944  inc     r12d
0x18005a947  cmp     r12d, r15d
0x18005a94a  jb      loc_18005A81C
0x18005a950  mov     r14, [rbp+170h+var_1E8]
0x18005a954  test    r13d, r13d
0x18005a957  mov     r13, [rsp+270h+Src]
0x18005a95c  jnz     loc_18005ABD5
0x18005a962  mov     rcx, [r14+8]
0x18005a966  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a96a  xor     ebx, ebx
0x18005a96c  inc     rax
0x18005a96f  cmp     [rcx+rax*2], bx
0x18005a973  jnz     short loc_18005A96C
0x18005a975  lea     ecx, ds:44h[rax*2]
0x18005a97c  cmp     ecx, 44h ; 'D'
0x18005a97f  jb      loc_18005ABC8
0x18005a985  mov     edx, [r14+0E8h]
0x18005a98c  add     edx, ecx
0x18005a98e  cmp     edx, ecx
0x18005a990  jb      loc_18005ABC8
0x18005a996  mov     ecx, dword ptr [rsp+270h+Size]
0x18005a99a  add     ecx, edx
0x18005a99c  cmp     ecx, edx
0x18005a99e  jb      loc_18005ABC8
0x18005a9a4  mov     edx, ebx
0x18005a9a6  cmp     edx, r15d
0x18005a9a9  jnb     short loc_18005A9E2
0x18005a9ab  mov     eax, edx
0x18005a9ad  lea     rax, [rax+rax*4]
0x18005a9b1  cmp     [rbp+rax*8+170h+hFile], 0FFFFFFFFFFFFFFFFh
0x18005a9b7  jz      short loc_18005A9CE
0x18005a9b9  lea     r8d, [rcx+10h]
0x18005a9bd  cmp     r8d, ecx
0x18005a9c0  jb      short loc_18005A9D2
0x18005a9c2  mov     ecx, [rbp+rax*8+170h+nNumberOfBytesToRead]
0x18005a9c6  add     ecx, r8d
0x18005a9c9  cmp     ecx, r8d
0x18005a9cc  jb      short loc_18005A9D2
0x18005a9ce  inc     edx
0x18005a9d0  jmp     short loc_18005A9A6
0x18005a9d2  mov     ecx, 216h
0x18005a9d7  mov     ebx, ecx
0x18005a9d9  lea     r9d, [rcx+39h]
0x18005a9dd  jmp     loc_18005ABE5
0x18005a9e2  mov     rax, [rbp+170h+var_1E0]
0x18005a9e6  mov     [rax], ecx
0x18005a9e8  cmp     [rsp+270h+var_1F8], rbx
0x18005a9ed  jz      loc_18005ABF0
0x18005a9f3  cmp     [rsp+270h+var_200], ecx
0x18005a9f7  jnb     short loc_18005AA03
0x18005a9f9  mov     ebx, 80090028h
0x18005a9fe  jmp     loc_18005ABF0
0x18005aa03  cmp     ebx, r15d
0x18005aa06  jnb     loc_18005AAD5
0x18005aa0c  mov     eax, ebx
0x18005aa0e  lea     r12, [rax+rax*4]
0x18005aa12  cmp     [rbp+r12*8+170h+hFile], 0FFFFFFFFFFFFFFFFh
0x18005aa18  jz      short loc_18005AA7F
0x18005aa1a  mov     ecx, [rbp+r12*8+170h+nNumberOfBytesToRead]
0x18005aa1f  call    SafeAllocaAllocateFromHeap
0x18005aa24  mov     [rbp+r12*8+170h+var_1B8], rax
0x18005aa29  test    rax, rax
0x18005aa2c  jz      loc_18005AACB
0x18005aa32  mov     r8d, [rbp+r12*8+170h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x18005aa37  lea     r9, [rsp+270h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005aa3c  mov     rcx, [rbp+r12*8+170h+hFile]; hFile
0x18005aa41  mov     rdx, rax; lpBuffer
0x18005aa44  mov     [rsp+270h+lpOverlapped], 0; lpOverlapped
0x18005aa4d  call    cs:__imp_ReadFile
0x18005aa54  nop     dword ptr [rax+rax+00h]
0x18005aa59  xor     ecx, ecx
0x18005aa5b  test    eax, eax
0x18005aa5d  jz      short loc_18005AA83
0x18005aa5f  mov     dword ptr [rsp+270h+var_240], ecx
0x18005aa63  xor     r9d, r9d
0x18005aa66  mov     dword ptr [rsp+270h+var_248], 99Ah
0x18005aa6e  xor     r8d, r8d
0x18005aa71  mov     [rsp+270h+lpOverlapped], rcx
0x18005aa76  lea     ecx, [r9+1]
0x18005aa7a  call    KspCryptAuditKeyFileOperation
0x18005aa7f  inc     ebx
0x18005aa81  jmp     short loc_18005AA03
0x18005aa83  call    cs:__imp_GetLastError
0x18005aa8a  nop     dword ptr [rax+rax+00h]
0x18005aa8f  mov     r9d, 27Ah
0x18005aa95  mov     r8, rdi
0x18005aa98  mov     ecx, eax
0x18005aa9a  mov     rdx, rsi
0x18005aa9d  mov     ebx, eax
0x18005aa9f  call    DebugTraceError
0x18005aaa4  mov     dword ptr [rsp+270h+var_240], ebx
0x18005aaa8  xor     r9d, r9d
0x18005aaab  mov     dword ptr [rsp+270h+var_248], 99Ah
0x18005aab3  xor     r8d, r8d
0x18005aab6  xor     ecx, ecx
0x18005aab8  mov     [rsp+270h+lpOverlapped], 0
0x18005aac1  call    KspCryptAuditKeyFileOperation
0x18005aac6  jmp     loc_18005ABF0
0x18005aacb  mov     ebx, 8009000Eh
0x18005aad0  jmp     loc_18005ABF0
0x18005aad5  mov     r12, [rsp+270h+var_1F8]
0x18005aada  xor     edx, edx; Val
0x18005aadc  mov     rcx, r12; void *
0x18005aadf  lea     r8d, [rdx+44h]; Size
0x18005aae3  lea     rbx, [r12+44h]
0x18005aae8  call    memset_0
0x18005aaed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005aaf1  mov     dword ptr [r12], 3142494Dh
0x18005aaf9  mov     rcx, [r14+8]
0x18005aafd  xor     esi, esi
0x18005aaff  inc     rax
0x18005ab02  cmp     [rcx+rax*2], si
0x18005ab06  jnz     short loc_18005AAFF
0x18005ab08  mov     r8d, eax
0x18005ab0b  mov     rcx, rbx; void *
0x18005ab0e  mov     [r12+4], r8d
0x18005ab13  add     r8, r8; Size
0x18005ab16  mov     rdx, [r14+8]; Src
0x18005ab1a  call    memcpy_0
0x18005ab1f  mov     eax, [r12+4]
0x18005ab24  lea     rbx, [rbx+rax*2]
0x18005ab28  mov     eax, [r14+0E8h]
0x18005ab2f  mov     [r12+0Ch], eax
0x18005ab34  mov     r8d, eax; Size
0x18005ab37  mov     rdx, [r14+0E0h]; Src
0x18005ab3e  mov     rcx, rbx; void *
0x18005ab41  call    memcpy_0
0x18005ab46  mov     edi, [r12+0Ch]
0x18005ab4b  add     rdi, rbx
0x18005ab4e  test    r13, r13
0x18005ab51  jz      short loc_18005AB6F
0x18005ab53  mov     eax, dword ptr [rsp+270h+Size]
  ... truncated ...
```
