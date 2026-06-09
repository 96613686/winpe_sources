# _MyWriteEvProp

- ea: `0x18002a0a0`
- end: `0x18002a4f0`
- name: `_MyWriteEvProp`
- size: `1104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007d5c`
- `0x18002a0a0`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a110`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a1fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a266`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a3f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a110`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a1fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a266`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a3f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3ac`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a369`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a3e5`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a426`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a369`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a3e5`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a426`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a44a`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a44a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a1bb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a219`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a1bb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a219`
- `CRYPT32!CryptDecodeObject` at `0x18002a254`
- `CRYPT32!CryptDecodeObject` at `0x18002a298`
- `CRYPT32!CryptDecodeObject` at `0x18002a254`
- `CRYPT32!CryptDecodeObject` at `0x18002a298`

## pseudocode

```c
__int64 __fastcall MyWriteEvProp(__int64 a1, unsigned int a2, const CERT_CONTEXT *a3)
{
  __int64 v3; // rsi
  BYTE *v6; // rdi
  _QWORD *pvStructInfo; // r14
  __int128 *p_pvData; // r9
  HLOCAL v9; // rax
  signed int LastError; // ebx
  unsigned int i; // ebx
  char *v12; // r9
  unsigned int j; // r8d
  DWORD v14; // eax
  BYTE *v15; // rax
  unsigned int k; // edi
  __int64 v17; // rbx
  char *v18; // rcx
  unsigned int m; // edx
  __int64 v20; // r11
  unsigned __int8 *v21; // rax
  __int64 v22; // r15
  int v23; // r8d
  int v24; // r9d
  __int128 *v25; // rcx
  unsigned int v26; // edx
  unsigned int n; // edi
  void *v28; // rcx
  DWORD pcbStructInfo; // [rsp+40h] [rbp-49h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-41h] BYREF
  DWORD pcbEncoded; // [rsp+58h] [rbp-31h] BYREF
  HLOCAL pvEncoded; // [rsp+60h] [rbp-29h] BYREF
  __int128 pvData; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v35[3]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v36; // [rsp+90h] [rbp+7h] BYREF
  HLOCAL v37; // [rsp+A0h] [rbp+17h]
  char v38; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = a2;
  pcbData = 0;
  pcbStructInfo = 0;
  v37 = 0;
  pvEncoded = 0;
  v6 = 0;
  pvStructInfo = 0;
  *(_OWORD *)hMem = 0;
  pvData = 0;
  v36 = 0;
  if ( !a2 )
  {
    p_pvData = 0;
    goto LABEL_48;
  }
  v9 = LocalAlloc(0x40u, 24LL * a2);
  hMem[1] = v9;
  if ( !v9 )
  {
LABEL_4:
    LastError = 8;
    goto LABEL_50;
  }
  memset_0(v9, 0, 24 * v3);
  for ( i = 0; i < (unsigned int)v3; ++i )
  {
    v12 = CertUIMkMBStr(*(LPCWCH *)(a1 + 8LL * i));
    if ( !v12 )
      goto LABEL_4;
    for ( j = 0; j < LODWORD(hMem[0]); ++j )
    {
      if ( !strcmp(v12, *((const char **)hMem[1] + 3 * j)) )
      {
        LocalFree(v12);
        goto LABEL_14;
      }
    }
    *((_QWORD *)hMem[1] + 3 * LODWORD(hMem[0])) = v12;
    ++LODWORD(hMem[0]);
LABEL_14:
    ;
  }
  pcbData = 0;
  if ( CertGetCertificateContextProperty(a3, 0x53u, 0, &pcbData) )
  {
    v14 = pcbData;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != -2146885628 )
      goto LABEL_50;
    v14 = 0;
    pcbData = 0;
  }
  if ( v14 )
  {
    v15 = (BYTE *)LocalAlloc(0x40u, v14);
    v6 = v15;
    if ( !v15 )
      goto LABEL_4;
    if ( !CertGetCertificateContextProperty(a3, 0x53u, v15, &pcbData) )
      goto LABEL_22;
    pcbStructInfo = 0;
    if ( !CryptDecodeObject(0x10001u, (LPCSTR)0x10, v6, pcbData, 0, 0, &pcbStructInfo) )
      goto LABEL_22;
    pvStructInfo = LocalAlloc(0x40u, pcbStructInfo);
    if ( !pvStructInfo )
      goto LABEL_4;
    if ( !CryptDecodeObject(0x10001u, (LPCSTR)0x10, v6, pcbData, 0, pvStructInfo, &pcbStructInfo) )
    {
LABEL_22:
      LastError = GetLastError();
      goto LABEL_50;
    }
    LocalFree(v6);
    pcbData = 0;
  }
  for ( k = 0; k < LODWORD(hMem[0]); ++k )
  {
    v17 = 24LL * k;
    v18 = (char *)hMem[1];
    if ( pvStructInfo )
    {
      for ( m = 0; m < *(_DWORD *)pvStructInfo; ++m )
      {
        v20 = pvStructInfo[1];
        v21 = *(unsigned __int8 **)((char *)hMem[1] + v17);
        v22 = *(_QWORD *)(v20 + 24LL * m) - (_QWORD)v21;
        do
        {
          v23 = v21[v22];
          v24 = *v21 - v23;
          if ( v24 )
            break;
          ++v21;
        }
        while ( v23 );
        if ( !v24 )
        {
          *(_DWORD *)((char *)hMem[1] + v17 + 8) = *(_DWORD *)(v20 + 24LL * m + 8);
          v25 = *(__int128 **)(v20 + 24LL * m + 16);
          goto LABEL_42;
        }
      }
    }
    if ( !pvEncoded )
    {
      v38 = -64;
      v35[1] = &v38;
      v35[0] = 1;
      v35[2] = 0;
      pcbEncoded = 0;
      if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x1A, v35, 0x8000u, 0, &pvEncoded, &pcbEncoded) )
        goto LABEL_43;
      v18 = (char *)hMem[1];
      v37 = pvEncoded;
      DWORD2(v36) = pcbEncoded;
      *(_QWORD *)&v36 = "1.3.6.1.4.1.311.60.1.1";
    }
    *(_DWORD *)&v18[v17 + 8] = 1;
    v25 = &v36;
LABEL_42:
    *(_QWORD *)((char *)hMem[1] + v17 + 16) = v25;
  }
  if ( !CryptEncodeObjectEx(0x10001u, (LPCSTR)0x10, hMem, 0, 0, 0, &pcbData) )
  {
LABEL_43:
    LastError = GetLastError();
    v6 = 0;
    goto LABEL_50;
  }
  v6 = (BYTE *)LocalAlloc(0x40u, pcbData);
  if ( !v6 )
    goto LABEL_4;
  if ( !CryptEncodeObjectEx(0x10001u, (LPCSTR)0x10, hMem, 0, 0, v6, &pcbData) )
    goto LABEL_22;
  p_pvData = &pvData;
  LODWORD(pvData) = pcbData;
  *((_QWORD *)&pvData + 1) = v6;
LABEL_48:
  if ( !CertSetCertificateContextProperty(a3, 0x53u, 0, p_pvData) )
    goto LABEL_22;
  LastError = 0;
LABEL_50:
  if ( pvEncoded )
  {
    LocalFree(pvEncoded);
    pvEncoded = 0;
  }
  if ( pvStructInfo )
    LocalFree(pvStructInfo);
  if ( v6 )
    LocalFree(v6);
  if ( hMem[1] )
  {
    v26 = (unsigned int)hMem[0];
    for ( n = 0; n < v26; ++n )
    {
      v28 = (void *)*((_QWORD *)hMem[1] + 3 * n);
      if ( v28 )
      {
        LocalFree(v28);
        v26 = (unsigned int)hMem[0];
      }
    }
    LocalFree(hMem[1]);
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002a0a0  mov     [rsp-8+arg_0], rbx
0x18002a0a5  push    rbp
0x18002a0a6  push    rsi
0x18002a0a7  push    rdi
0x18002a0a8  push    r12
0x18002a0aa  push    r13
0x18002a0ac  push    r14
0x18002a0ae  push    r15
0x18002a0b0  lea     rbp, [rsp-27h]
0x18002a0b5  sub     rsp, 0B0h
0x18002a0bc  xor     r13d, r13d
0x18002a0bf  mov     esi, edx
0x18002a0c1  xor     eax, eax
0x18002a0c3  mov     [rbp+57h+pcbData], r13d
0x18002a0c7  mov     [rbp+57h+var_A0], r13d
0x18002a0cb  xorps   xmm0, xmm0
0x18002a0ce  mov     [rbp+57h+var_40], rax
0x18002a0d2  xorps   xmm1, xmm1
0x18002a0d5  mov     [rbp+57h+pvEncoded], r13
0x18002a0d9  mov     r12, r8
0x18002a0dc  mov     r15, rcx
0x18002a0df  mov     edi, r13d
0x18002a0e2  mov     r14d, r13d
0x18002a0e5  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x18002a0e9  movups  [rbp+57h+pvData], xmm1
0x18002a0ed  movups  [rbp+57h+var_50], xmm0
0x18002a0f1  test    edx, edx
0x18002a0f3  jnz     short loc_18002A100
0x18002a0f5  xor     r9d, r9d
0x18002a0f8  lea     edx, [rax+53h]
0x18002a0fb  jmp     loc_18002A444
0x18002a100  lea     rbx, [rsi+rsi*2]
0x18002a104  mov     ecx, 40h ; '@'; uFlags
0x18002a109  shl     rbx, 3
0x18002a10d  mov     rdx, rbx; uBytes
0x18002a110  call    cs:__imp_LocalAlloc
0x18002a116  mov     [rbp+57h+hMem+8], rax
0x18002a11a  test    rax, rax
0x18002a11d  jnz     short loc_18002A129
0x18002a11f  mov     ebx, 8
0x18002a124  jmp     loc_18002A45B
0x18002a129  mov     r8, rbx; Size
0x18002a12c  xor     edx, edx; Val
0x18002a12e  mov     rcx, rax; void *
0x18002a131  call    memset_0
0x18002a136  mov     ebx, r13d
0x18002a139  cmp     ebx, esi
0x18002a13b  jnb     short loc_18002A1A7
0x18002a13d  mov     ecx, ebx
0x18002a13f  mov     rcx, [r15+rcx*8]; lpWideCharStr
0x18002a143  call    ?CertUIMkMBStr@@YAPEADPEBG@Z; CertUIMkMBStr(ushort const *)
0x18002a148  mov     r9, rax
0x18002a14b  test    rax, rax
0x18002a14e  jz      short loc_18002A11F
0x18002a150  mov     r11, [rbp+57h+hMem+8]
0x18002a154  mov     r8d, r13d
0x18002a157  cmp     r8d, dword ptr [rbp+57h+hMem]
0x18002a15b  jnb     short loc_18002A195
0x18002a15d  mov     ecx, r8d
0x18002a160  mov     rax, r9
0x18002a163  lea     rdx, [rcx+rcx*2]
0x18002a167  mov     r10, [r11+rdx*8]
0x18002a16b  sub     r10, r9
0x18002a16e  movzx   edx, byte ptr [rax]
0x18002a171  movzx   ecx, byte ptr [rax+r10]
0x18002a176  sub     edx, ecx
0x18002a178  jnz     short loc_18002A181
0x18002a17a  inc     rax
0x18002a17d  test    ecx, ecx
0x18002a17f  jnz     short loc_18002A16E
0x18002a181  test    edx, edx
0x18002a183  jz      short loc_18002A18A
0x18002a185  inc     r8d
0x18002a188  jmp     short loc_18002A157
0x18002a18a  mov     rcx, r9; hMem
0x18002a18d  call    cs:__imp_LocalFree
0x18002a193  jmp     short loc_18002A1A3
0x18002a195  mov     eax, dword ptr [rbp+57h+hMem]
0x18002a198  lea     rcx, [rax+rax*2]
0x18002a19c  mov     [r11+rcx*8], r9
0x18002a1a0  inc     dword ptr [rbp+57h+hMem]
0x18002a1a3  inc     ebx
0x18002a1a5  jmp     short loc_18002A139
0x18002a1a7  xor     r8d, r8d; pvData
0x18002a1aa  mov     [rbp+57h+pcbData], r13d
0x18002a1ae  lea     r9, [rbp+57h+pcbData]; pcbData
0x18002a1b2  mov     rcx, r12; pCertContext
0x18002a1b5  lea     esi, [r8+53h]
0x18002a1b9  mov     edx, esi; dwPropId
0x18002a1bb  call    cs:__imp_CertGetCertificateContextProperty
0x18002a1c1  test    eax, eax
0x18002a1c3  jnz     short loc_18002A1E0
0x18002a1c5  call    cs:__imp_GetLastError
0x18002a1cb  mov     ebx, eax
0x18002a1cd  cmp     eax, 80092004h
0x18002a1d2  jnz     loc_18002A45B
0x18002a1d8  mov     eax, r13d
0x18002a1db  mov     [rbp+57h+pcbData], eax
0x18002a1de  jmp     short loc_18002A1E3
0x18002a1e0  mov     eax, [rbp+57h+pcbData]
0x18002a1e3  mov     ebx, 10h
0x18002a1e8  mov     r15d, 10001h
0x18002a1ee  test    eax, eax
0x18002a1f0  jz      loc_18002A2AF
0x18002a1f6  mov     edx, eax; uBytes
0x18002a1f8  lea     ecx, [rbx+30h]; uFlags
0x18002a1fb  call    cs:__imp_LocalAlloc
0x18002a201  mov     rdi, rax
0x18002a204  test    rax, rax
0x18002a207  jz      loc_18002A11F
0x18002a20d  lea     r9, [rbp+57h+pcbData]; pcbData
0x18002a211  mov     r8, rax; pvData
0x18002a214  mov     edx, esi; dwPropId
0x18002a216  mov     rcx, r12; pCertContext
0x18002a219  call    cs:__imp_CertGetCertificateContextProperty
0x18002a21f  test    eax, eax
0x18002a221  jnz     short loc_18002A230
0x18002a223  call    cs:__imp_GetLastError
0x18002a229  mov     ebx, eax
0x18002a22b  jmp     loc_18002A45B
0x18002a230  mov     r9d, [rbp+57h+pcbData]; cbEncoded
0x18002a234  lea     rax, [rbp+57h+var_A0]
0x18002a238  mov     [rsp+0E0h+pcbStructInfo], rax; pcbStructInfo
0x18002a23d  mov     r8, rdi; pbEncoded
0x18002a240  mov     [rsp+0E0h+pvStructInfo], r13; pvStructInfo
0x18002a245  mov     rdx, rbx; lpszStructType
0x18002a248  mov     ecx, r15d; dwCertEncodingType
0x18002a24b  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x18002a250  mov     [rbp+57h+var_A0], r13d
0x18002a254  call    cs:__imp_CryptDecodeObject
0x18002a25a  test    eax, eax
0x18002a25c  jz      short loc_18002A223
0x18002a25e  mov     edx, [rbp+57h+var_A0]; uBytes
0x18002a261  mov     ecx, 40h ; '@'; uFlags
0x18002a266  call    cs:__imp_LocalAlloc
0x18002a26c  mov     r14, rax
0x18002a26f  test    rax, rax
0x18002a272  jz      loc_18002A11F
0x18002a278  mov     r9d, [rbp+57h+pcbData]; cbEncoded
0x18002a27c  lea     rax, [rbp+57h+var_A0]
0x18002a280  mov     [rsp+0E0h+pcbStructInfo], rax; pcbStructInfo
0x18002a285  mov     r8, rdi; pbEncoded
0x18002a288  mov     [rsp+0E0h+pvStructInfo], r14; pvStructInfo
0x18002a28d  mov     rdx, rbx; lpszStructType
0x18002a290  mov     ecx, r15d; dwCertEncodingType
0x18002a293  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x18002a298  call    cs:__imp_CryptDecodeObject
0x18002a29e  test    eax, eax
0x18002a2a0  jz      short loc_18002A223
0x18002a2a2  mov     rcx, rdi; hMem
0x18002a2a5  call    cs:__imp_LocalFree
0x18002a2ab  mov     [rbp+57h+pcbData], r13d
0x18002a2af  mov     edi, r13d
0x18002a2b2  cmp     edi, dword ptr [rbp+57h+hMem]
0x18002a2b5  jnb     loc_18002A3BC
0x18002a2bb  mov     eax, edi
0x18002a2bd  lea     rcx, [rax+rax*2]
0x18002a2c1  lea     rbx, ds:0[rcx*8]
0x18002a2c9  mov     rcx, [rbp+57h+hMem+8]
0x18002a2cd  test    r14, r14
0x18002a2d0  jz      short loc_18002A31E
0x18002a2d2  mov     edx, r13d
0x18002a2d5  cmp     edx, [r14]
0x18002a2d8  jnb     short loc_18002A31E
0x18002a2da  mov     r11, [r14+8]
0x18002a2de  mov     eax, edx
0x18002a2e0  lea     r10, [rax+rax*2]
0x18002a2e4  mov     rax, [rbx+rcx]
0x18002a2e8  mov     r15, [r11+r10*8]
0x18002a2ec  sub     r15, rax
0x18002a2ef  movzx   r9d, byte ptr [rax]
0x18002a2f3  movzx   r8d, byte ptr [rax+r15]
0x18002a2f8  sub     r9d, r8d
0x18002a2fb  jnz     short loc_18002A305
0x18002a2fd  inc     rax
0x18002a300  test    r8d, r8d
0x18002a303  jnz     short loc_18002A2EF
0x18002a305  test    r9d, r9d
0x18002a308  jz      short loc_18002A30E
0x18002a30a  inc     edx
0x18002a30c  jmp     short loc_18002A2D5
0x18002a30e  mov     eax, [r11+r10*8+8]
0x18002a313  mov     [rbx+rcx+8], eax
0x18002a317  mov     rcx, [r11+r10*8+10h]
0x18002a31c  jmp     short loc_18002A39C
0x18002a31e  cmp     [rbp+57h+pvEncoded], r13
0x18002a322  jnz     short loc_18002A390
0x18002a324  lea     rax, [rbp+57h+arg_8]
0x18002a328  mov     [rbp+57h+arg_8], 0C0h
0x18002a32c  mov     [rbp+57h+var_60], rax
0x18002a330  lea     r8, [rbp+57h+var_68]; pvStructInfo
0x18002a334  lea     rax, [rbp+57h+pcbEncoded]
0x18002a338  mov     [rbp+57h+var_68], 1
0x18002a340  mov     [rsp+0E0h+pcbStructInfo], rax; pcbEncoded
0x18002a345  mov     edx, 1Ah; lpszStructType
0x18002a34a  lea     rax, [rbp+57h+pvEncoded]
0x18002a34e  mov     [rbp+57h+var_58], r13
0x18002a352  mov     [rsp+0E0h+pvStructInfo], rax; pvEncoded
0x18002a357  mov     r9d, 8000h; dwFlags
0x18002a35d  mov     qword ptr [rsp+0E0h+dwFlags], r13; pEncodePara
0x18002a362  lea     ecx, [rdx-19h]; dwCertEncodingType
0x18002a365  mov     [rbp+57h+pcbEncoded], r13d
0x18002a369  call    cs:__imp_CryptEncodeObjectEx
0x18002a36f  test    eax, eax
0x18002a371  jz      short loc_18002A3AC
0x18002a373  mov     rax, [rbp+57h+pvEncoded]
0x18002a377  mov     rcx, [rbp+57h+hMem+8]
0x18002a37b  mov     [rbp+57h+var_40], rax
0x18002a37f  mov     eax, [rbp+57h+pcbEncoded]
0x18002a382  mov     dword ptr [rbp+57h+var_50+8], eax
0x18002a385  lea     rax, a1361413116011; "1.3.6.1.4.1.311.60.1.1"
0x18002a38c  mov     qword ptr [rbp+57h+var_50], rax
0x18002a390  mov     dword ptr [rbx+rcx+8], 1
0x18002a398  lea     rcx, [rbp+57h+var_50]
0x18002a39c  mov     rax, [rbp+57h+hMem+8]
0x18002a3a0  inc     edi
0x18002a3a2  mov     [rbx+rax+10h], rcx
0x18002a3a7  jmp     loc_18002A2B2
0x18002a3ac  call    cs:__imp_GetLastError
0x18002a3b2  mov     ebx, eax
0x18002a3b4  mov     rdi, r13
0x18002a3b7  jmp     loc_18002A45B
0x18002a3bc  xor     r9d, r9d; dwFlags
0x18002a3bf  lea     rax, [rbp+57h+pcbData]
0x18002a3c3  mov     [rsp+0E0h+pcbStructInfo], rax; pcbEncoded
0x18002a3c8  lea     r8, [rbp+57h+hMem]; pvStructInfo
0x18002a3cc  mov     r15d, 10001h
0x18002a3d2  mov     [rsp+0E0h+pvStructInfo], r13; pvEncoded
0x18002a3d7  mov     ecx, r15d; dwCertEncodingType
0x18002a3da  mov     qword ptr [rsp+0E0h+dwFlags], r13; pEncodePara
0x18002a3df  lea     ebx, [r9+10h]
0x18002a3e3  mov     edx, ebx; lpszStructType
0x18002a3e5  call    cs:__imp_CryptEncodeObjectEx
0x18002a3eb  test    eax, eax
0x18002a3ed  jz      short loc_18002A3AC
0x18002a3ef  mov     edx, [rbp+57h+pcbData]; uBytes
0x18002a3f2  lea     ecx, [rbx+30h]; uFlags
0x18002a3f5  call    cs:__imp_LocalAlloc
0x18002a3fb  mov     rdi, rax
0x18002a3fe  test    rax, rax
0x18002a401  jz      loc_18002A11F
0x18002a407  lea     rax, [rbp+57h+pcbData]
0x18002a40b  xor     r9d, r9d; dwFlags
0x18002a40e  mov     [rsp+0E0h+pcbStructInfo], rax; pcbEncoded
0x18002a413  lea     r8, [rbp+57h+hMem]; pvStructInfo
0x18002a417  mov     [rsp+0E0h+pvStructInfo], rdi; pvEncoded
0x18002a41c  mov     edx, ebx; lpszStructType
0x18002a41e  mov     ecx, r15d; dwCertEncodingType
0x18002a421  mov     qword ptr [rsp+0E0h+dwFlags], r13; pEncodePara
0x18002a426  call    cs:__imp_CryptEncodeObjectEx
0x18002a42c  test    eax, eax
0x18002a42e  jz      loc_18002A223
0x18002a434  mov     eax, [rbp+57h+pcbData]
0x18002a437  lea     r9, [rbp+57h+pvData]; pvData
0x18002a43b  mov     dword ptr [rbp+57h+pvData], eax
0x18002a43e  mov     edx, esi; dwPropId
0x18002a440  mov     qword ptr [rbp+57h+pvData+8], rdi
0x18002a444  xor     r8d, r8d; dwFlags
0x18002a447  mov     rcx, r12; pCertContext
0x18002a44a  call    cs:__imp_CertSetCertificateContextProperty
0x18002a450  test    eax, eax
0x18002a452  jz      loc_18002A223
0x18002a458  mov     ebx, r13d
0x18002a45b  mov     rcx, [rbp+57h+pvEncoded]; hMem
0x18002a45f  test    rcx, rcx
0x18002a462  jz      short loc_18002A46E
0x18002a464  call    cs:__imp_LocalFree
0x18002a46a  mov     [rbp+57h+pvEncoded], r13
0x18002a46e  test    r14, r14
0x18002a471  jz      short loc_18002A47C
0x18002a473  mov     rcx, r14; hMem
0x18002a476  call    cs:__imp_LocalFree
0x18002a47c  test    rdi, rdi
0x18002a47f  jz      short loc_18002A48A
0x18002a481  mov     rcx, rdi; hMem
0x18002a484  call    cs:__imp_LocalFree
0x18002a48a  cmp     [rbp+57h+hMem+8], r13
0x18002a48e  jz      short loc_18002A4C6
0x18002a490  mov     edx, dword ptr [rbp+57h+hMem]
0x18002a493  mov     edi, r13d
0x18002a496  test    edx, edx
0x18002a498  jz      short loc_18002A4BC
0x18002a49a  mov     eax, edi
0x18002a49c  lea     rcx, [rax+rax*2]
0x18002a4a0  mov     rax, [rbp+57h+hMem+8]
0x18002a4a4  mov     rcx, [rax+rcx*8]; hMem
0x18002a4a8  test    rcx, rcx
0x18002a4ab  jz      short loc_18002A4B6
0x18002a4ad  call    cs:__imp_LocalFree
0x18002a4b3  mov     edx, dword ptr [rbp+57h+hMem]
0x18002a4b6  inc     edi
0x18002a4b8  cmp     edi, edx
0x18002a4ba  jb      short loc_18002A49A
0x18002a4bc  mov     rcx, [rbp+57h+hMem+8]; hMem
0x18002a4c0  call    cs:__imp_LocalFree
0x18002a4c6  test    ebx, ebx
0x18002a4c8  jle     short loc_18002A4D3
0x18002a4ca  movzx   ebx, bx
0x18002a4cd  or      ebx, 80070000h
0x18002a4d3  mov     eax, ebx
  ... truncated ...
```
