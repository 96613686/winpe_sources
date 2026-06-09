# I_UrlCacheCreateMetaDataAndContentFiles

- ea: `0x180001c80`
- end: `0x1800021d8`
- name: `I_UrlCacheCreateMetaDataAndContentFiles`
- size: `1368`
- prototype: `__int64 __fastcall(_WORD *Src, _WORD *, __int64, int, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180001878`

## callees

- `0x180001c80`
- `0x1800021e0`
- `0x180003170`
- `0x18000a990`
- `0x18001fa58`
- `0x18001fa9c`
- `0x18001fae4`
- `0x180026552`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002117`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000218f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000218f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002078`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000219a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000219a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020b9`

## pseudocode

```c
__int64 __fastcall I_UrlCacheCreateMetaDataAndContentFiles(
        _WORD *Src,
        _WORD *a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        __int64 *a6)
{
  __int64 CacheFileFromUrlHash; // r12
  __int64 v10; // rsi
  __int64 v11; // r8
  _WORD *v12; // rax
  int v13; // r10d
  BCRYPT_HASH_HANDLE *v14; // r9
  __int16 v15; // cx
  unsigned int v16; // edx
  unsigned int v17; // r8d
  __int16 v18; // cx
  __int16 v19; // cx
  unsigned int v20; // r8d
  unsigned int v21; // edx
  __int16 v22; // cx
  unsigned int v23; // r8d
  __int16 v24; // cx
  __int16 v25; // cx
  unsigned int v26; // r8d
  unsigned int v27; // edx
  __int16 v28; // cx
  unsigned int v29; // r8d
  __int16 v30; // cx
  __int16 v31; // cx
  unsigned int v32; // r8d
  unsigned int v33; // edx
  __int16 v34; // cx
  unsigned int v35; // r8d
  __int16 v36; // cx
  __int16 v37; // cx
  unsigned int v38; // r8d
  unsigned int v39; // edx
  __int16 v40; // cx
  unsigned int v41; // r8d
  __int16 v42; // cx
  __int16 v43; // cx
  unsigned int v44; // r8d
  unsigned int v45; // edx
  __int16 v46; // cx
  unsigned int v47; // r8d
  __int16 v48; // cx
  __int16 v49; // cx
  unsigned int v50; // r8d
  __int16 v51; // cx
  unsigned int v52; // edx
  unsigned int v53; // r8d
  __int16 v54; // cx
  __int16 v55; // cx
  unsigned int v56; // r8d
  unsigned int v57; // edx
  __int16 v58; // cx
  unsigned int v59; // r8d
  __int16 v60; // cx
  __int64 v61; // rdi
  char *v62; // r14
  size_t v63; // rbx
  int v64; // edx
  __int128 v65; // xmm1
  char *v66; // rcx
  __int16 v67; // ax
  __int128 v68; // xmm0
  __int128 v69; // xmm1
  DWORD dwFlagsAndAttributes; // esi
  DWORD v71; // eax
  DWORD dwCreationDisposition; // ebx
  DWORD v73; // ecx
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  DWORD v76; // ebx
  __int64 result; // rax
  unsigned int v78; // edi
  bool v79; // cf
  DWORD v80; // ebx
  DWORD v81; // ecx
  unsigned int v83; // [rsp+44h] [rbp-E4h]
  DWORD v84; // [rsp+48h] [rbp-E0h]
  DWORD v85; // [rsp+50h] [rbp-D8h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v87; // [rsp+70h] [rbp-B8h]
  _OWORD v88[4]; // [rsp+80h] [rbp-A8h] BYREF
  __int16 v89; // [rsp+C0h] [rbp-68h]

  v87 = 0;
  CacheFileFromUrlHash = 0;
  *(_OWORD *)phHash = 0;
  CngRsa32Compat_MD5Init(phHash);
  v10 = -1;
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a3 + 2 * v11) );
  }
  else
  {
    LODWORD(v11) = 0;
  }
  CngRsa32Compat_MD5Update(phHash, a3, (unsigned int)(2 * v11));
  CngRsa32Compat_MD5Final(phHash);
  v12 = v88;
  v13 = 2;
  v14 = &phHash[1];
  do
  {
    v15 = 48;
    v16 = *(unsigned __int8 *)v14 >> 4;
    if ( v16 > 9 )
      v15 = 55;
    v17 = *(_BYTE *)v14 & 0xF;
    *v12 = v16 + v15;
    v18 = 48;
    if ( v17 > 9 )
      v18 = 55;
    v19 = v17 + v18;
    v20 = *((unsigned __int8 *)v14 + 1);
    v12[1] = v19;
    v21 = v20 >> 4;
    v22 = 48;
    if ( v20 >> 4 > 9 )
      v22 = 55;
    v23 = v20 & 0xF;
    v12[2] = v21 + v22;
    v24 = 48;
    if ( v23 > 9 )
      v24 = 55;
    v25 = v23 + v24;
    v26 = *((unsigned __int8 *)v14 + 2);
    v12[3] = v25;
    v27 = v26 >> 4;
    v28 = 48;
    if ( v26 >> 4 > 9 )
      v28 = 55;
    v29 = v26 & 0xF;
    v12[4] = v27 + v28;
    v30 = 48;
    if ( v29 > 9 )
      v30 = 55;
    v31 = v29 + v30;
    v32 = *((unsigned __int8 *)v14 + 3);
    v12[5] = v31;
    v33 = v32 >> 4;
    v34 = 48;
    if ( v32 >> 4 > 9 )
      v34 = 55;
    v35 = v32 & 0xF;
    v12[6] = v33 + v34;
    v36 = 48;
    if ( v35 > 9 )
      v36 = 55;
    v37 = v35 + v36;
    v38 = *((unsigned __int8 *)v14 + 4);
    v12[7] = v37;
    v39 = v38 >> 4;
    v40 = 48;
    if ( v38 >> 4 > 9 )
      v40 = 55;
    v41 = v38 & 0xF;
    v12[8] = v39 + v40;
    v42 = 48;
    if ( v41 > 9 )
      v42 = 55;
    v43 = v41 + v42;
    v44 = *((unsigned __int8 *)v14 + 5);
    v12[9] = v43;
    v45 = v44 >> 4;
    v46 = 48;
    if ( v44 >> 4 > 9 )
      v46 = 55;
    v47 = v44 & 0xF;
    v12[10] = v45 + v46;
    v48 = 48;
    if ( v47 > 9 )
      v48 = 55;
    v12 += 16;
    v49 = v47 + v48;
    v50 = *((unsigned __int8 *)v14 + 6);
    *(v12 - 5) = v49;
    ++v14;
    v51 = 48;
    v52 = v50 >> 4;
    if ( v50 >> 4 > 9 )
      v51 = 55;
    v53 = v50 & 0xF;
    *(v12 - 4) = v52 + v51;
    v54 = 48;
    if ( v53 > 9 )
      v54 = 55;
    v55 = v53 + v54;
    v56 = *((unsigned __int8 *)v14 - 1);
    *(v12 - 3) = v55;
    v57 = v56 >> 4;
    v58 = 48;
    if ( v56 >> 4 > 9 )
      v58 = 55;
    v59 = v56 & 0xF;
    *(v12 - 2) = v57 + v58;
    v60 = 48;
    if ( v59 > 9 )
      v60 = 55;
    *(v12 - 1) = v59 + v60;
    --v13;
  }
  while ( v13 );
  *v12 = 0;
  if ( Src )
  {
    v61 = -1;
    do
      ++v61;
    while ( Src[v61] );
  }
  else
  {
    LODWORD(v61) = 0;
  }
  if ( a2 )
  {
    do
      ++v10;
    while ( a2[v10] );
  }
  else
  {
    LODWORD(v10) = 0;
  }
  v62 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v61 + v10 + 42));
  if ( !v62 )
  {
    v81 = -2147024882;
LABEL_70:
    SetLastError(v81);
    FileW = 0;
    goto LABEL_59;
  }
  v63 = 2LL * (unsigned int)v61;
  memcpy_0(v62, Src, v63);
  v64 = a4;
  *(_OWORD *)&v62[v63] = *(_OWORD *)L"MetaData";
  *(_WORD *)&v62[v63 + 16] = aMetadata[8];
  if ( !a4 )
  {
LABEL_45:
    *(_WORD *)&v62[2 * (unsigned int)(v61 + 8)] = 92;
    if ( (_DWORD)v10 )
    {
      memcpy_0(&v62[2 * (unsigned int)v61 + 18], a2, 2LL * (unsigned int)v10);
      v64 = a4;
    }
    v65 = v88[1];
    v66 = &v62[2 * (unsigned int)v61 + 2 * (unsigned __int64)(unsigned int)v10];
    v67 = v89;
    *(_OWORD *)(v66 + 18) = v88[0];
    v68 = v88[2];
    *(_OWORD *)(v66 + 34) = v65;
    v69 = v88[3];
    *(_OWORD *)(v66 + 50) = v68;
    *(_OWORD *)(v66 + 66) = v69;
    *((_WORD *)v66 + 41) = v67;
    v83 = 0;
    dwFlagsAndAttributes = 4;
    if ( !v64 )
      dwFlagsAndAttributes = 128;
    v71 = -1073741824;
    dwCreationDisposition = (v64 != 0) + 3;
    v73 = v64 == 0;
    v84 = v73;
    if ( !v64 )
      v71 = 0x80000000;
    v85 = v71;
    while ( 1 )
    {
      FileW = CreateFileW((LPCWSTR)v62, v71, v73, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( LastError == 32 )
      {
        v78 = v83;
        v79 = v83 < 6;
      }
      else
      {
        if ( LastError != 5 )
        {
          if ( LastError == 3 )
            LastError = 2;
LABEL_57:
          SetLastError(LastError);
          FileW = 0;
          break;
        }
        v78 = v83;
        v79 = v83 == 0;
      }
      if ( !v79 )
        goto LABEL_57;
      Sleep(*((_DWORD *)qword_18002BA20 + v78));
      v71 = v85;
      v73 = v84;
      v83 = v78 + 1;
    }
    v76 = GetLastError();
    LocalFree(v62);
    SetLastError(v76);
    if ( !FileW )
      goto LABEL_59;
    CacheFileFromUrlHash = I_UrlCacheCreateCacheFileFromUrlHash(Src, L"Content", a2, a4);
    if ( CacheFileFromUrlHash )
    {
      result = 1;
      goto LABEL_60;
    }
    v80 = GetLastError();
    CloseHandle(FileW);
    v81 = v80;
    goto LABEL_70;
  }
  if ( (unsigned int)I_CryptRecursiveCreateLowIntegrityDirectory((LPCWSTR)v62) )
  {
    v64 = a4;
    goto LABEL_45;
  }
  operator delete(v62);
  FileW = 0;
LABEL_59:
  result = 0;
LABEL_60:
  *a5 = FileW;
  *a6 = CacheFileFromUrlHash;
  return result;
}

```

## disassembly

```asm
0x180001c80  push    rbx
0x180001c82  push    rbp
0x180001c83  push    rsi
0x180001c84  push    rdi
0x180001c85  push    r12
0x180001c87  push    r13
0x180001c89  push    r14
0x180001c8b  push    r15
0x180001c8d  sub     rsp, 0E8h
0x180001c94  mov     rax, cs:__security_cookie
0x180001c9b  xor     rax, rsp
0x180001c9e  mov     [rsp+128h+var_58], rax
0x180001ca6  mov     rax, [rsp+128h+arg_28]
0x180001cae  mov     r15, rcx
0x180001cb1  mov     r13, [rsp+128h+arg_20]
0x180001cb9  lea     rcx, [rsp+128h+phHash]; phHash
0x180001cbe  mov     [rsp+128h+var_D0], rax
0x180001cc3  xorps   xmm0, xmm0
0x180001cc6  xor     eax, eax
0x180001cc8  mov     [rsp+128h+var_E8], r9d
0x180001ccd  mov     [rsp+128h+var_B8], rax
0x180001cd2  mov     rbx, r8
0x180001cd5  mov     rbp, rdx
0x180001cd8  xor     r12d, r12d
0x180001cdb  movups  xmmword ptr [rsp+128h+phHash], xmm0
0x180001ce0  call    CngRsa32Compat_MD5Init
0x180001ce5  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180001cec  test    rbx, rbx
0x180001cef  jz      loc_1800021B9
0x180001cf5  mov     r8, rsi
0x180001cf8  nop     dword ptr [rax+rax+00000000h]
0x180001d00  inc     r8
0x180001d03  cmp     [rbx+r8*2], r12w
0x180001d08  jnz     short loc_180001D00
0x180001d0a  add     r8d, r8d
0x180001d0d  lea     rcx, [rsp+128h+phHash]
0x180001d12  mov     rdx, rbx
0x180001d15  call    CngRsa32Compat_MD5Update
0x180001d1a  lea     rcx, [rsp+128h+phHash]
0x180001d1f  call    CngRsa32Compat_MD5Final
0x180001d24  lea     rax, [rsp+128h+var_A8]
0x180001d2c  mov     r10d, 2
0x180001d32  lea     r9, [rsp+128h+phHash+8]
0x180001d37  mov     r11d, 37h ; '7'
0x180001d3d  nop     dword ptr [rax]
0x180001d40  movzx   r8d, byte ptr [r9]
0x180001d44  mov     ecx, 30h ; '0'
0x180001d49  mov     edx, r8d
0x180001d4c  shr     edx, 4
0x180001d4f  cmp     edx, 9
0x180001d52  cmova   cx, r11w
0x180001d57  and     r8d, 0Fh
0x180001d5b  add     cx, dx
0x180001d5e  mov     [rax], cx
0x180001d61  cmp     r8d, 9
0x180001d65  mov     ecx, 30h ; '0'
0x180001d6a  cmova   cx, r11w
0x180001d6f  add     cx, r8w
0x180001d73  movzx   r8d, byte ptr [r9+1]
0x180001d78  mov     [rax+2], cx
0x180001d7c  mov     edx, r8d
0x180001d7f  shr     edx, 4
0x180001d82  mov     ecx, 30h ; '0'
0x180001d87  cmp     edx, 9
0x180001d8a  cmova   cx, r11w
0x180001d8f  and     r8d, 0Fh
0x180001d93  add     cx, dx
0x180001d96  mov     [rax+4], cx
0x180001d9a  cmp     r8d, 9
0x180001d9e  mov     ecx, 30h ; '0'
0x180001da3  cmova   cx, r11w
0x180001da8  add     cx, r8w
0x180001dac  movzx   r8d, byte ptr [r9+2]
0x180001db1  mov     [rax+6], cx
0x180001db5  mov     edx, r8d
0x180001db8  shr     edx, 4
0x180001dbb  mov     ecx, 30h ; '0'
0x180001dc0  cmp     edx, 9
0x180001dc3  cmova   cx, r11w
0x180001dc8  and     r8d, 0Fh
0x180001dcc  add     cx, dx
0x180001dcf  mov     [rax+8], cx
0x180001dd3  cmp     r8d, 9
0x180001dd7  mov     ecx, 30h ; '0'
0x180001ddc  cmova   cx, r11w
0x180001de1  add     cx, r8w
0x180001de5  movzx   r8d, byte ptr [r9+3]
0x180001dea  mov     [rax+0Ah], cx
0x180001dee  mov     edx, r8d
0x180001df1  shr     edx, 4
0x180001df4  mov     ecx, 30h ; '0'
0x180001df9  cmp     edx, 9
0x180001dfc  cmova   cx, r11w
0x180001e01  and     r8d, 0Fh
0x180001e05  add     cx, dx
0x180001e08  mov     [rax+0Ch], cx
0x180001e0c  cmp     r8d, 9
0x180001e10  mov     ecx, 30h ; '0'
0x180001e15  cmova   cx, r11w
0x180001e1a  add     cx, r8w
0x180001e1e  movzx   r8d, byte ptr [r9+4]
0x180001e23  mov     [rax+0Eh], cx
0x180001e27  mov     edx, r8d
0x180001e2a  shr     edx, 4
0x180001e2d  mov     ecx, 30h ; '0'
0x180001e32  cmp     edx, 9
0x180001e35  cmova   cx, r11w
0x180001e3a  and     r8d, 0Fh
0x180001e3e  add     cx, dx
0x180001e41  mov     [rax+10h], cx
0x180001e45  cmp     r8d, 9
0x180001e49  mov     ecx, 30h ; '0'
0x180001e4e  cmova   cx, r11w
0x180001e53  add     cx, r8w
0x180001e57  movzx   r8d, byte ptr [r9+5]
0x180001e5c  mov     [rax+12h], cx
0x180001e60  mov     edx, r8d
0x180001e63  shr     edx, 4
0x180001e66  mov     ecx, 30h ; '0'
0x180001e6b  cmp     edx, 9
0x180001e6e  cmova   cx, r11w
0x180001e73  and     r8d, 0Fh
0x180001e77  add     cx, dx
0x180001e7a  mov     [rax+14h], cx
0x180001e7e  cmp     r8d, 9
0x180001e82  mov     ecx, 30h ; '0'
0x180001e87  cmova   cx, r11w
0x180001e8c  lea     rax, [rax+20h]
0x180001e90  add     cx, r8w
0x180001e94  movzx   r8d, byte ptr [r9+6]
0x180001e99  mov     [rax-0Ah], cx
0x180001e9d  lea     r9, [r9+8]
0x180001ea1  mov     edx, r8d
0x180001ea4  mov     ecx, 30h ; '0'
0x180001ea9  shr     edx, 4
0x180001eac  cmp     edx, 9
0x180001eaf  cmova   cx, r11w
0x180001eb4  and     r8d, 0Fh
0x180001eb8  add     cx, dx
0x180001ebb  mov     [rax-8], cx
0x180001ebf  cmp     r8d, 9
0x180001ec3  mov     ecx, 30h ; '0'
0x180001ec8  cmova   cx, r11w
0x180001ecd  add     cx, r8w
0x180001ed1  movzx   r8d, byte ptr [r9-1]
0x180001ed6  mov     [rax-6], cx
0x180001eda  mov     edx, r8d
0x180001edd  shr     edx, 4
0x180001ee0  mov     ecx, 30h ; '0'
0x180001ee5  cmp     edx, 9
0x180001ee8  cmova   cx, r11w
0x180001eed  and     r8d, 0Fh
0x180001ef1  add     cx, dx
0x180001ef4  mov     [rax-4], cx
0x180001ef8  cmp     r8d, 9
0x180001efc  mov     ecx, 30h ; '0'
0x180001f01  cmova   cx, r11w
0x180001f06  add     cx, r8w
0x180001f0a  mov     [rax-2], cx
0x180001f0e  add     r10d, 0FFFFFFFFh
0x180001f12  jnz     loc_180001D40
0x180001f18  xor     ecx, ecx; uFlags
0x180001f1a  mov     [rax], cx
0x180001f1d  test    r15, r15
0x180001f20  jz      loc_1800021C1
0x180001f26  mov     rdi, rsi
0x180001f29  nop     dword ptr [rax+00000000h]
0x180001f30  inc     rdi
0x180001f33  cmp     [r15+rdi*2], cx
0x180001f38  jnz     short loc_180001F30
0x180001f3a  test    rbp, rbp
0x180001f3d  jz      loc_180002130
0x180001f43  inc     rsi
0x180001f46  cmp     [rbp+rsi*2+0], cx
0x180001f4b  jnz     short loc_180001F43
0x180001f4d  lea     edx, [rsi+2Ah]
0x180001f50  add     edx, edi
0x180001f52  add     rdx, rdx; uBytes
0x180001f55  call    cs:__imp_LocalAlloc
0x180001f5b  mov     r14, rax
0x180001f5e  test    rax, rax
0x180001f61  jz      loc_1800021C8
0x180001f67  mov     eax, edi
0x180001f69  mov     rdx, r15; Src
0x180001f6c  mov     rcx, r14; void *
0x180001f6f  mov     [rsp+128h+var_E0], rax
0x180001f74  lea     rbx, [rax+rax]
0x180001f78  mov     r8, rbx; Size
0x180001f7b  call    memcpy_0
0x180001f80  movups  xmm0, xmmword ptr cs:aMetadata; "MetaData"
0x180001f87  mov     edx, [rsp+128h+var_E8]
0x180001f8b  movups  xmmword ptr [rbx+r14], xmm0
0x180001f90  movzx   eax, word ptr cs:aMetadata+10h; ""
0x180001f97  mov     [rbx+r14+10h], ax
0x180001f9d  test    edx, edx
0x180001f9f  jnz     loc_18000214A
0x180001fa5  mov     rbx, [rsp+128h+var_E0]
0x180001faa  lea     eax, [rdi+8]
0x180001fad  mov     word ptr [r14+rax*2], 5Ch ; '\'
0x180001fb4  test    esi, esi
0x180001fb6  jz      short loc_180001FD2
0x180001fb8  mov     r8d, esi
0x180001fbb  lea     rcx, [rbx+9]
0x180001fbf  add     r8, r8; Size
0x180001fc2  lea     rcx, [r14+rcx*2]; void *
0x180001fc6  mov     rdx, rbp; Src
0x180001fc9  call    memcpy_0
0x180001fce  mov     edx, [rsp+128h+var_E8]
0x180001fd2  movaps  xmm0, [rsp+128h+var_A8]
0x180001fda  movaps  xmm1, [rsp+128h+var_98]
0x180001fe2  mov     eax, esi
0x180001fe4  add     rax, rbx
0x180001fe7  lea     rcx, [r14+rax*2]
0x180001feb  movzx   eax, [rsp+128h+var_68]
0x180001ff3  movups  xmmword ptr [rcx+12h], xmm0
0x180001ff7  movaps  xmm0, [rsp+128h+var_88]
0x180001fff  movups  xmmword ptr [rcx+22h], xmm1
0x180002003  movaps  xmm1, [rsp+128h+var_78]
0x18000200b  movups  xmmword ptr [rcx+32h], xmm0
0x18000200f  movups  xmmword ptr [rcx+42h], xmm1
0x180002013  mov     [rcx+52h], ax
0x180002017  test    edx, edx
0x180002019  mov     [rsp+128h+var_E4], r12d
0x18000201e  mov     eax, 80h
0x180002023  mov     esi, 4
0x180002028  cmovz   esi, eax
0x18000202b  mov     r8d, 80000000h
0x180002031  xor     ebx, ebx
0x180002033  mov     eax, 0C0000000h
0x180002038  test    edx, edx
0x18000203a  setnz   bl
0x18000203d  xor     ecx, ecx
0x18000203f  add     ebx, 3
0x180002042  test    edx, edx
0x180002044  setz    cl
0x180002047  test    edx, edx
0x180002049  mov     dword ptr [rsp+128h+var_E0], ecx
0x18000204d  cmovz   eax, r8d
0x180002051  mov     [rsp+128h+var_D8], eax
0x180002055  nop     word ptr [rax+rax+00000000h]
0x180002060  mov     [rsp+128h+hTemplateFile], r12; hTemplateFile
0x180002065  mov     r8d, ecx; dwShareMode
0x180002068  mov     [rsp+128h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18000206c  mov     rcx, r14; lpFileName
0x18000206f  xor     r9d, r9d; lpSecurityAttributes
0x180002072  mov     [rsp+128h+dwCreationDisposition], ebx; dwCreationDisposition
0x180002076  mov     edx, eax; dwDesiredAccess
0x180002078  call    cs:__imp_CreateFileW
0x18000207e  mov     rdi, rax
0x180002081  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002085  jnz     short loc_1800020AE
0x180002087  call    cs:__imp_GetLastError
0x18000208d  cmp     eax, 20h ; ' '
0x180002090  jz      short loc_180002102
0x180002092  cmp     eax, 5
0x180002095  jz      loc_180002141
0x18000209b  cmp     eax, 3
0x18000209e  jz      loc_180002137
0x1800020a4  mov     ecx, eax; dwErrCode
0x1800020a6  call    cs:__imp_SetLastError
0x1800020ac  xor     edi, edi
0x1800020ae  call    cs:__imp_GetLastError
0x1800020b4  mov     rcx, r14; hMem
0x1800020b7  mov     ebx, eax
0x1800020b9  call    cs:__imp_LocalFree
0x1800020bf  mov     ecx, ebx; dwErrCode
0x1800020c1  call    cs:__imp_SetLastError
0x1800020c7  test    rdi, rdi
0x1800020ca  jnz     loc_180002165
0x1800020d0  xor     eax, eax
0x1800020d2  mov     rcx, [rsp+128h+var_D0]
0x1800020d7  mov     [r13+0], rdi
0x1800020db  mov     [rcx], r12
0x1800020de  mov     rcx, [rsp+128h+var_58]
0x1800020e6  xor     rcx, rsp; StackCookie
0x1800020e9  call    __security_check_cookie
0x1800020ee  add     rsp, 0E8h
0x1800020f5  pop     r15
0x1800020f7  pop     r14
0x1800020f9  pop     r13
0x1800020fb  pop     r12
0x1800020fd  pop     rdi
0x1800020fe  pop     rsi
0x1800020ff  pop     rbp
0x180002100  pop     rbx
0x180002101  retn
0x180002102  mov     edi, [rsp+128h+var_E4]
0x180002106  cmp     edi, 6
0x180002109  jnb     short loc_1800020A4
0x18000210b  mov     ecx, edi
0x18000210d  lea     rax, qword_18002BA20
0x180002114  mov     ecx, [rax+rcx*4]; dwMilliseconds
0x180002117  call    cs:__imp_Sleep
0x18000211d  mov     eax, [rsp+128h+var_D8]
0x180002121  inc     edi
0x180002123  mov     ecx, dword ptr [rsp+128h+var_E0]
0x180002127  mov     [rsp+128h+var_E4], edi
0x18000212b  jmp     loc_180002060
0x180002130  xor     esi, esi
0x180002132  jmp     loc_180001F4D
  ... truncated ...
```
