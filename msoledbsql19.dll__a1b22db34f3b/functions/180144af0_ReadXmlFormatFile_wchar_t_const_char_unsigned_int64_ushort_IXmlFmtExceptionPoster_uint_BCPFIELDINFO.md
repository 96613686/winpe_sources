# ReadXmlFormatFile(wchar_t const *,char *,unsigned __int64,ushort,IXmlFmtExceptionPoster *,uint *,BCPFIELDINFO * *)

- ea: `0x180144af0`
- end: `0x18014540a`
- name: `?ReadXmlFormatFile@@YAJPEB_WPEAD_KGPEAVIXmlFmtExceptionPoster@@PEAIPEAPEAUBCPFIELDINFO@@@Z`
- size: `2330`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, char *Dst@<rdx>, size_t DstSizeInBytes@<r8>, unsigned __int16@<r9w>, struct IXmlFmtExceptionPoster *, unsigned int *, struct BCPFIELDINFO **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callers

- `0x180112a70`

## callees

- `0x180001760`
- `0x180001910`
- `0x180003090`
- `0x180003488`
- `0x180003d80`
- `0x180143b20`
- `0x180143b40`
- `0x180143d70`
- `0x1801441e0`
- `0x180144af0`
- `0x1801463e0`
- `0x180146490`
- `0x180146c90`
- `0x180147900`
- `0x18014feb0`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180144c1e`
- `KERNEL32!GetLastError` at `0x180144c2c`
- `KERNEL32!GetLastError` at `0x180144c1e`
- `KERNEL32!GetLastError` at `0x180144c2c`
- `KERNEL32!GetFileSize` at `0x180144c08`
- `KERNEL32!GetFileSize` at `0x180144c08`
- `KERNEL32!CreateFileW` at `0x180144be9`
- `KERNEL32!CreateFileW` at `0x180144be9`
- `KERNEL32!CloseHandle` at `0x180144c72`
- `KERNEL32!CloseHandle` at `0x18014526e`
- `KERNEL32!CloseHandle` at `0x180144c72`
- `KERNEL32!CloseHandle` at `0x18014526e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=2
__int64 __fastcall ReadXmlFormatFile(
        LPCWSTR lpFileName,
        char *Dst,
        size_t DstSizeInBytes,
        unsigned __int16 a4,
        struct IXmlFmtExceptionPoster *a5,
        unsigned int *a6,
        struct BCPFIELDINFO **a7)
{
  void **v9; // rax
  signed int v10; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  void (__fastcall *v13)(CFileReadStream *__hidden); // rax
  wchar_t *v14; // rcx
  size_t v15; // rdx
  char *v16; // rcx
  char *v17; // r13
  unsigned int v18; // ecx
  char *v19; // rax
  __int64 v20; // rsi
  unsigned __int64 v21; // rax
  struct BCPFIELDINFO *v22; // rax
  unsigned int i; // esi
  char *v24; // r15
  char *v25; // rcx
  unsigned __int16 *v26; // rbx
  unsigned __int16 ColumnByID; // ax
  __int64 v28; // rdx
  const WCHAR *v29; // rax
  const wchar_t *v30; // rcx
  unsigned __int8 v31; // r11
  int v32; // eax
  unsigned int v33; // ecx
  int v34; // edx
  int v35; // r10d
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned __int64 v38; // kr50_8
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rax
  size_t v41; // rbx
  char *v42; // rdi
  wchar_t *v43; // rcx
  size_t v44; // rdx
  int v45; // r9d
  struct BCPFIELDINFO *v46; // r15
  const WCHAR *v47; // r8
  unsigned __int64 v48; // rax
  _WORD *v49; // rcx
  __int64 v50; // rdx
  signed __int64 v51; // r8
  __int16 v52; // ax
  _WORD *v53; // rax
  _QWORD *v54; // rdi
  __int64 v55; // rsi
  unsigned __int8 v58; // [rsp+50h] [rbp-1D8h]
  struct BCPFIELDINFO *v59; // [rsp+60h] [rbp-1C8h]
  unsigned int v60; // [rsp+68h] [rbp-1C0h]
  unsigned int v61; // [rsp+78h] [rbp-1B0h]
  int v62; // [rsp+7Ch] [rbp-1ACh]
  unsigned __int16 *v63; // [rsp+80h] [rbp-1A8h]
  char pExceptionObject[8]; // [rsp+88h] [rbp-1A0h] BYREF
  char v65[8]; // [rsp+90h] [rbp-198h] BYREF
  char v66[8]; // [rsp+98h] [rbp-190h] BYREF
  char v67[8]; // [rsp+A0h] [rbp-188h] BYREF
  char v68[8]; // [rsp+A8h] [rbp-180h] BYREF
  char v69[8]; // [rsp+B0h] [rbp-178h] BYREF
  char v70[8]; // [rsp+B8h] [rbp-170h] BYREF
  char v71[8]; // [rsp+C0h] [rbp-168h] BYREF
  unsigned int *v72; // [rsp+C8h] [rbp-160h]
  struct BCPFIELDINFO **v73; // [rsp+D0h] [rbp-158h]
  _BYTE v74[24]; // [rsp+F0h] [rbp-138h] BYREF
  struct CBulkColumn *v75; // [rsp+108h] [rbp-120h] BYREF
  _QWORD v76[2]; // [rsp+110h] [rbp-118h] BYREF
  DWORD FileSizeHigh[4]; // [rsp+120h] [rbp-108h] BYREF
  _BYTE v78[72]; // [rsp+140h] [rbp-E8h] BYREF
  char v79; // [rsp+188h] [rbp-A0h] BYREF
  char *v80; // [rsp+190h] [rbp-98h]
  wchar_t *v81; // [rsp+1D0h] [rbp-58h]

  v72 = a6;
  v73 = a7;
  v75 = 0;
  *a6 = 0;
  *a7 = 0;
  v9 = &CFileReadStream::`vftable';
  v76[0] = &CFileReadStream::`vftable';
  v76[1] = 1;
  *(__m128i *)FileSizeHigh = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v10 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = -2147221303;
LABEL_11:
    v13 = (void (__fastcall *)(CFileReadStream *__hidden))v9[7];
    if ( v13 == CFileReadStream::Close )
    {
      if ( *(_QWORD *)FileSizeHigh != -1 )
      {
        CloseHandle(*(HANDLE *)FileSizeHigh);
        *(_QWORD *)FileSizeHigh = -1;
      }
      *(_QWORD *)&FileSizeHigh[2] = -1;
    }
    else
    {
      v13((CFileReadStream *)v76);
    }
    goto LABEL_16;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
  *(_QWORD *)FileSizeHigh = FileW;
  if ( FileW == (HANDLE)-1LL
    || (FileSizeHigh[2] = GetFileSize(FileW, &FileSizeHigh[3]), FileSizeHigh[2] == -1) && GetLastError() )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
    {
      v9 = (void **)v76[0];
      goto LABEL_11;
    }
  }
LABEL_16:
  if ( v10 >= 0 )
  {
    memset_0(v78, 0, 0xA0u);
    CBulkFormat::CBulkFormat((CBulkFormat *)v78);
    CBulkFormat::ParseFormatFile((CBulkFormat *)v78, *(void **)FileSizeHigh);
    v14 = v81;
    if ( v81 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v81[v15] );
    }
    else
    {
      v15 = 0;
      v14 = (wchar_t *)&Class;
    }
    WstrToChar(v14, v15, Dst, DstSizeInBytes);
    v16 = v80;
    if ( v80 == &v79 )
      v16 = 0;
    v17 = 0;
    if ( v16 )
      v17 = v16 - 48;
    v18 = 0;
    v19 = 0;
    if ( v80 != &v79 )
      v19 = v80;
    if ( v19 )
    {
      do
      {
        ++v18;
        v19 = (char *)*((_QWORD *)v19 + 1);
      }
      while ( v19 != &v79 && v19 );
    }
    v60 = v18;
    if ( v18 - 1 > 0xFFF )
    {
      CBcpFmtException::CBcpFmtException(v71, 2);
      throw (CBcpFmtException *)v71;
    }
    _mm_lfence();
    v20 = v18;
    v21 = 288LL * v18;
    if ( !is_mul_ok(v18, 0x120u) )
      v21 = -1;
    try
    {
      v22 = (struct BCPFIELDINFO *)operator new[](v21);
    }
    catch ( std::bad_alloc )
    {
      v59 = 0;
      goto LABEL_104;
    }
    v59 = v22;
    if ( v22 )
    {
      memset_0(v22, 0, 288 * v20);
      for ( i = 0; ; ++i )
      {
        if ( i >= v60 || (v24 = v17) == 0 )
        {
          CBulkFormat::~CBulkFormat((CBulkFormat *)v78);
          *v72 = v60;
          *v73 = v59;
          goto LABEL_115;
        }
        v25 = (char *)*((_QWORD *)v17 + 7);
        if ( v25 == &v79 )
          v25 = 0;
        v17 = 0;
        if ( v25 )
          v17 = v25 - 48;
        v75 = 0;
        v26 = (unsigned __int16 *)((char *)v59 + 288 * i);
        v63 = v26;
        ColumnByID = CBulkFormat::GetColumnByID((CBulkFormat *)v78, (const struct CWStr *)(v24 + 8), &v75);
        if ( ColumnByID > a4 )
        {
          CBcpFmtException::CBcpFmtException(pExceptionObject, 9, i + 1);
          throw (CBcpFmtException *)pExceptionObject;
        }
        *v26 = ColumnByID;
        switch ( *((_DWORD *)v24 + 6) )
        {
          case 1:
            v30 = L"SQLCHAR";
            break;
          case 2:
            v30 = L"SQLNCHAR";
            break;
          case 3:
            if ( !ColumnByID )
              goto LABEL_54;
            v28 = *((_QWORD *)v75 + 4);
            v29 = &Class;
            if ( v28 )
              v29 = (const WCHAR *)*((_QWORD *)v75 + 4);
            if ( *v29 )
            {
              v30 = &Class;
              if ( v28 )
                v30 = (const wchar_t *)*((_QWORD *)v75 + 4);
            }
            else
            {
LABEL_54:
              v30 = L"SQLBINARY";
            }
            break;
          default:
            CBcpFmtException::CBcpFmtException(v65, 5, i + 1);
            throw (CBcpFmtException *)v65;
        }
        v31 = FieldNameToTDSType(v30);
        v58 = v31;
        if ( !v31 )
        {
          CBcpFmtException::CBcpFmtException(v66, 5, i + 1);
          throw (CBcpFmtException *)v66;
        }
        v32 = *((_DWORD *)v24 + 7);
        if ( v32 == 2 )
        {
          v33 = *((_DWORD *)v24 + 9);
          v61 = v33;
          if ( v33 > 8 || (v34 = 278, !_bittest(&v34, v33)) )
          {
            CBcpFmtException::CBcpFmtException(v67, 6, i + 1);
            throw (CBcpFmtException *)v67;
          }
        }
        else
        {
          v61 = 0;
        }
        v35 = *((_DWORD *)v24 + 8);
        v62 = v35;
        if ( v35 < 0 )
        {
          CBcpFmtException::CBcpFmtException(v68, 7, i + 1);
          throw (CBcpFmtException *)v68;
        }
        if ( v32 == 3 )
        {
          v36 = *((_QWORD *)v24 + 5);
          if ( v36 )
          {
            v37 = -1;
            do
              ++v37;
            while ( *(_WORD *)(v36 + 2 * v37) );
          }
          else
          {
            v37 = 0;
          }
          v38 = v37;
          v39 = 2 * v37;
          if ( is_mul_ok(v38, 2u) && (v40 = 2 * v39, is_mul_ok(v39, 2u)) && (v41 = v40 + 1, v40 + 1 >= v40) )
          {
            v42 = (char *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO
                                                                                                + 112LL))(
                            g_pMO,
                            v40 + 1);
            if ( !v42 )
            {
              std::bad_alloc::bad_alloc((std::bad_alloc *)v74);
              throw (std::bad_alloc *)v74;
            }
          }
          else
          {
            v41 = -1;
            v42 = 0;
          }
          if ( !v42 )
          {
            v46 = v59;
            v10 = -2147024882;
            CBulkFormat::~CBulkFormat((CBulkFormat *)v78);
            goto LABEL_108;
          }
          v43 = (wchar_t *)*((_QWORD *)v24 + 5);
          if ( v43 )
          {
            v44 = -1;
            do
              ++v44;
            while ( v43[v44] );
          }
          else
          {
            v44 = 0;
            v43 = (wchar_t *)&Class;
          }
          WstrToChar(v43, v44, v42, v41);
          v45 = ConvertTerminatorToBinary((const unsigned __int8 *)v42, (unsigned __int8 *)v42, v41);
          if ( v45 == -1 )
          {
            CBcpFmtException::CBcpFmtException(v69, 8, i + 1);
            throw (CBcpFmtException *)v69;
          }
          v26 = (unsigned __int16 *)((char *)v59 + 288 * i);
          v35 = v62;
          v31 = v58;
        }
        else
        {
          v42 = 0;
          v45 = 0;
        }
        v47 = (const WCHAR *)*((_QWORD *)v24 + 2);
        if ( v47 )
        {
          v48 = -1;
          do
            ++v48;
          while ( v47[v48] );
          if ( v48 > 0x80 )
          {
            CBcpFmtException::CBcpFmtException(v70, 10, i + 1);
            throw (CBcpFmtException *)v70;
          }
        }
        else
        {
          v47 = &Class;
        }
        v49 = v26 + 12;
        v50 = 129;
        v51 = (char *)v47 - (char *)(v26 + 12);
        do
        {
          if ( v50 == -2147483517 )
            break;
          v52 = *(_WORD *)((char *)v49 + v51);
          if ( !v52 )
            break;
          *v49++ = v52;
          --v50;
        }
        while ( v50 );
        v53 = v49 - 1;
        if ( v50 )
          v53 = v49;
        *v53 = 0;
        v10 = -2147024774;
        if ( !v50 )
          break;
        v10 = 0;
        *((_BYTE *)v63 + 2) = v31;
        *((_DWORD *)v63 + 1) = v61;
        *((_DWORD *)v63 + 2) = v35;
        *((_DWORD *)v63 + 3) = v45;
        *((_QWORD *)v63 + 2) = v42;
      }
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(off_180260790[0], 1377289);
      CBulkFormat::~CBulkFormat((CBulkFormat *)v78);
      if ( v42 )
        (*(void (__fastcall **)(struct ISOSHost_MemObj *, char *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v42);
    }
    else
    {
LABEL_104:
      v10 = -2147024882;
      CBulkFormat::~CBulkFormat((CBulkFormat *)v78);
    }
    v46 = v59;
    if ( v59 )
    {
LABEL_108:
      if ( v60 )
      {
        _mm_lfence();
        v54 = (_QWORD *)((char *)v46 + 16);
        v55 = v60;
        do
        {
          if ( *((_DWORD *)v54 - 1) && *v54 )
          {
            (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
            *v54 = 0;
          }
          v54 += 36;
          --v55;
        }
        while ( v55 );
      }
      (*(void (__fastcall **)(struct ISOSHost_MemObj *, struct BCPFIELDINFO *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v46);
    }
LABEL_115:
    v76[0] = &CFileReadStream::`vftable';
  }
  else
  {
    _mm_lfence();
    v76[0] = &CFileReadStream::`vftable';
  }
  if ( *(_QWORD *)FileSizeHigh != -1 )
    CloseHandle(*(HANDLE *)FileSizeHigh);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180144af0  push    rbx
0x180144af2  push    rsi
0x180144af3  push    rdi
0x180144af4  push    r12
0x180144af6  push    r13
0x180144af8  push    r14
0x180144afa  push    r15
0x180144afc  sub     rsp, 1F0h
0x180144b03  mov     rax, cs:__security_cookie
0x180144b0a  xor     rax, rsp
0x180144b0d  mov     [rsp+228h+var_40], rax
0x180144b15  mov     word ptr [rsp+228h+var_1E8], r9w
0x180144b1b  mov     r15, r8
0x180144b1e  mov     rsi, rdx
0x180144b21  mov     r10, rcx
0x180144b24  mov     rax, [rsp+228h+arg_20]
0x180144b2c  mov     [rsp+228h+var_1E0], rax
0x180144b31  mov     rcx, [rsp+228h+arg_28]
0x180144b39  mov     [rsp+228h+var_160], rcx
0x180144b41  mov     rax, [rsp+228h+arg_30]
0x180144b49  mov     [rsp+228h+var_158], rax
0x180144b51  xor     r14d, r14d
0x180144b54  mov     [rsp+228h+var_1C0], r14d
0x180144b59  mov     [rsp+228h+var_1B8], r14
0x180144b5e  mov     [rsp+228h+var_120], r14
0x180144b66  mov     edi, r14d
0x180144b69  mov     [rsp+228h+var_1D0], r14
0x180144b6e  mov     [rcx], r14d
0x180144b71  mov     [rax], r14
0x180144b74  xorps   xmm0, xmm0
0x180144b77  movups  [rsp+228h+var_118], xmm0
0x180144b7f  lea     r13, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x180144b86  mov     rax, r13
0x180144b89  mov     qword ptr [rsp+228h+var_118], rax
0x180144b91  mov     dword ptr [rsp+228h+var_118+8], 1
0x180144b9c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180144ba4  movdqu  xmmword ptr [rsp+228h+FileSizeHigh], xmm0
0x180144bad  mov     ebx, r14d
0x180144bb0  test    r10, r10
0x180144bb3  jz      loc_180144C4F
0x180144bb9  cmp     [r10], bx
0x180144bbd  jz      loc_180144C4F
0x180144bc3  mov     [rsp+228h+hTemplateFile], r14; hTemplateFile
0x180144bc8  mov     [rsp+228h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180144bd0  mov     [rsp+228h+dwCreationDisposition], 3; dwCreationDisposition
0x180144bd8  xor     r9d, r9d; lpSecurityAttributes
0x180144bdb  mov     edx, 80000000h; dwDesiredAccess
0x180144be0  mov     r8d, 1; dwShareMode
0x180144be6  mov     rcx, r10; lpFileName
0x180144be9  call    cs:__imp_CreateFileW
0x180144bef  mov     qword ptr [rsp+228h+FileSizeHigh], rax
0x180144bf7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180144bfb  jz      short loc_180144C2C
0x180144bfd  lea     rdx, [rsp+228h+FileSizeHigh+0Ch]; lpFileSizeHigh
0x180144c05  mov     rcx, rax; hFile
0x180144c08  call    cs:__imp_GetFileSize
0x180144c0e  mov     [rsp+228h+FileSizeHigh+8], eax
0x180144c15  cmp     eax, 0FFFFFFFFh
0x180144c18  jnz     loc_180144CB0
0x180144c1e  call    cs:__imp_GetLastError
0x180144c24  test    eax, eax
0x180144c26  jz      loc_180144CB0
0x180144c2c  call    cs:__imp_GetLastError
0x180144c32  test    eax, eax
0x180144c34  mov     ebx, eax
0x180144c36  jle     short loc_180144C41
0x180144c38  movzx   ebx, ax
0x180144c3b  or      ebx, 80070000h
0x180144c41  test    ebx, ebx
0x180144c43  jns     short loc_180144CB0
0x180144c45  mov     rax, qword ptr [rsp+228h+var_118]
0x180144c4d  jmp     short loc_180144C54
0x180144c4f  mov     ebx, 800400C9h
0x180144c54  mov     rax, [rax+38h]
0x180144c58  lea     rcx, ?Close@CFileReadStream@@UEAAXXZ; CFileReadStream::Close(void)
0x180144c5f  cmp     rax, rcx
0x180144c62  jnz     short loc_180144CA2
0x180144c64  mov     rcx, qword ptr [rsp+228h+FileSizeHigh]; hObject
0x180144c6c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180144c70  jz      short loc_180144C91
0x180144c72  call    cs:__imp_CloseHandle
0x180144c78  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180144c7f  mov     qword ptr [rsp+228h+FileSizeHigh], r12
0x180144c87  mov     qword ptr [rsp+228h+FileSizeHigh+8], r12
0x180144c8f  jmp     short loc_180144CB7
0x180144c91  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180144c98  mov     qword ptr [rsp+228h+FileSizeHigh+8], r12
0x180144ca0  jmp     short loc_180144CB7
0x180144ca2  lea     rcx, [rsp+228h+var_118]
0x180144caa  call    cs:__guard_dispatch_icall_fptr
0x180144cb0  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180144cb7  test    ebx, ebx
0x180144cb9  jns     short loc_180144CCB
0x180144cbb  lfence
0x180144cbe  mov     qword ptr [rsp+228h+var_118], r13
0x180144cc6  jmp     loc_180145260
0x180144ccb  xor     edx, edx; Val
0x180144ccd  mov     r8d, 0A0h; Size
0x180144cd3  lea     rcx, [rsp+228h+var_E8]; void *
0x180144cdb  call    memset_0
0x180144ce0  lea     rcx, [rsp+228h+var_E8]; this
0x180144ce8  call    ??0CBulkFormat@@QEAA@XZ; CBulkFormat::CBulkFormat(void)
0x180144ced  nop
0x180144cee  mov     rdx, qword ptr [rsp+228h+FileSizeHigh]; void *
0x180144cf6  lea     rcx, [rsp+228h+var_E8]; this
0x180144cfe  call    ?ParseFormatFile@CBulkFormat@@QEAAXPEAX@Z; CBulkFormat::ParseFormatFile(void *)
0x180144d03  mov     rcx, [rsp+228h+var_58]
0x180144d0b  test    rcx, rcx
0x180144d0e  jz      short loc_180144D24
0x180144d10  mov     rdx, r12
0x180144d13  inc     rdx
0x180144d16  cmp     word ptr [rcx+rdx*2], 0
0x180144d1b  jnz     short loc_180144D13
0x180144d1d  test    rcx, rcx
0x180144d20  jz      short loc_180144D27
0x180144d22  jmp     short loc_180144D2E
0x180144d24  mov     rdx, r14; MaxCountInBytes
0x180144d27  lea     rcx, Class; Src
0x180144d2e  mov     r9, r15; DstSizeInBytes
0x180144d31  mov     r8, rsi; Dst
0x180144d34  call    WstrToChar
0x180144d39  mov     rdx, [rsp+228h+var_98]
0x180144d41  mov     rcx, rdx
0x180144d44  lea     rax, [rsp+228h+var_A0]
0x180144d4c  cmp     rdx, rax
0x180144d4f  cmovz   rcx, r14
0x180144d53  lea     rax, [rcx-30h]
0x180144d57  mov     r13, r14
0x180144d5a  test    rcx, rcx
0x180144d5d  cmovnz  r13, rax
0x180144d61  mov     ecx, r14d
0x180144d64  mov     rax, r14
0x180144d67  lea     r8, [rsp+228h+var_A0]
0x180144d6f  cmp     rdx, r8
0x180144d72  cmovnz  rax, rdx
0x180144d76  test    rax, rax
0x180144d79  jz      short loc_180144D98
0x180144d7b  nop     dword ptr [rax+rax+00h]
0x180144d80  inc     ecx
0x180144d82  mov     rax, [rax+8]
0x180144d86  lea     rdx, [rsp+228h+var_A0]
0x180144d8e  cmp     rax, rdx
0x180144d91  jz      short loc_180144D98
0x180144d93  test    rax, rax
0x180144d96  jnz     short loc_180144D80
0x180144d98  mov     [rsp+228h+var_1C0], ecx
0x180144d9c  lea     eax, [rcx-1]
0x180144d9f  cmp     eax, 0FFFh
0x180144da4  ja      loc_1801453E2
0x180144daa  lfence
0x180144dad  mov     esi, ecx
0x180144daf  mov     eax, 120h
0x180144db4  mul     rsi
0x180144db7  cmovb   rax, r12
0x180144dbb  mov     rcx, rax; unsigned __int64
0x180144dbe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180144dc3  mov     [rsp+228h+var_1C8], rax
0x180144dc8  mov     [rsp+228h+var_1B8], rax
0x180144dcd  test    rax, rax
0x180144dd0  jz      loc_18014513D
0x180144dd6  lea     r8, [rsi+rsi*8]
0x180144dda  shl     r8, 5; Size
0x180144dde  xor     edx, edx; Val
0x180144de0  mov     rcx, rax; void *
0x180144de3  call    memset_0
0x180144de8  mov     esi, r14d
0x180144deb  nop     dword ptr [rax+rax+00h]
0x180144df0  cmp     esi, [rsp+228h+var_1C0]
0x180144df4  jnb     loc_180145120
0x180144dfa  mov     r15, r13
0x180144dfd  test    r13, r13
0x180144e00  jz      loc_180145120
0x180144e06  mov     rcx, [r13+38h]
0x180144e0a  lea     rax, [rsp+228h+var_A0]
0x180144e12  cmp     rcx, rax
0x180144e15  cmovz   rcx, r14
0x180144e19  lea     rax, [rcx-30h]
0x180144e1d  mov     r13, r14
0x180144e20  test    rcx, rcx
0x180144e23  cmovnz  r13, rax
0x180144e27  mov     [rsp+228h+var_120], r14
0x180144e2f  mov     eax, esi
0x180144e31  lea     rbx, [rax+rax*8]
0x180144e35  shl     rbx, 5
0x180144e39  add     rbx, [rsp+228h+var_1C8]
0x180144e3e  mov     [rsp+228h+var_1A8], rbx
0x180144e46  lea     rdx, [r15+8]; struct CWStr *
0x180144e4a  lea     r8, [rsp+228h+var_120]; struct CBulkColumn **
0x180144e52  lea     rcx, [rsp+228h+var_E8]; this
0x180144e5a  call    ?GetColumnByID@CBulkFormat@@QEAAJAEBVCWStr@@PEAPEAVCBulkColumn@@@Z; CBulkFormat::GetColumnByID(CWStr const &,CBulkColumn * *)
0x180144e5f  cmp     ax, word ptr [rsp+228h+var_1E8]
0x180144e64  ja      loc_180145299
0x180144e6a  mov     [rbx], ax
0x180144e6d  mov     ecx, [r15+18h]
0x180144e71  sub     ecx, 1
0x180144e74  jz      short loc_180144ECB
0x180144e76  sub     ecx, 1
0x180144e79  jz      short loc_180144EC2
0x180144e7b  cmp     ecx, 1
0x180144e7e  jnz     loc_1801452C3
0x180144e84  test    ax, ax
0x180144e87  jz      short loc_180144EB9
0x180144e89  mov     rax, [rsp+228h+var_120]
0x180144e91  mov     rdx, [rax+20h]
0x180144e95  lea     rax, Class
0x180144e9c  test    rdx, rdx
0x180144e9f  cmovnz  rax, rdx
0x180144ea3  cmp     word ptr [rax], 0
0x180144ea7  jz      short loc_180144EB9
0x180144ea9  lea     rcx, Class
0x180144eb0  test    rdx, rdx
0x180144eb3  cmovnz  rcx, rdx
0x180144eb7  jmp     short loc_180144ED2
0x180144eb9  lea     rcx, aSqlbinary_0; "SQLBINARY"
0x180144ec0  jmp     short loc_180144ED2
0x180144ec2  lea     rcx, aSqlnchar; "SQLNCHAR"
0x180144ec9  jmp     short loc_180144ED2
0x180144ecb  lea     rcx, aSqlchar; "SQLCHAR"
0x180144ed2  call    ?FieldNameToTDSType@@YAEPEB_W@Z; FieldNameToTDSType(wchar_t const *)
0x180144ed7  movzx   r11d, al
0x180144edb  mov     [rsp+228h+var_1D8], al
0x180144edf  test    al, al
0x180144ee1  jz      loc_1801452ED
0x180144ee7  mov     eax, [r15+1Ch]
0x180144eeb  cmp     eax, 2
0x180144eee  jnz     short loc_180144F11
0x180144ef0  mov     ecx, [r15+24h]
0x180144ef4  mov     [rsp+228h+var_1B0], ecx
0x180144ef8  cmp     ecx, 8
0x180144efb  ja      loc_180145317
0x180144f01  mov     edx, 116h
0x180144f06  bt      edx, ecx
0x180144f09  jnb     loc_180145317
0x180144f0f  jmp     short loc_180144F16
0x180144f11  mov     [rsp+228h+var_1B0], r14d
0x180144f16  mov     r10d, [r15+20h]
0x180144f1a  mov     [rsp+228h+var_1AC], r10d
0x180144f1f  test    r10d, r10d
0x180144f22  js      loc_180145341
0x180144f28  cmp     eax, 3
0x180144f2b  jnz     loc_180145021
0x180144f31  mov     rax, [r15+28h]
0x180144f35  test    rax, rax
0x180144f38  jz      short loc_180144F4C
0x180144f3a  mov     rcx, r12
0x180144f3d  nop     dword ptr [rax]
0x180144f40  inc     rcx
0x180144f43  cmp     word ptr [rax+rcx*2], 0
0x180144f48  jnz     short loc_180144F40
0x180144f4a  jmp     short loc_180144F4F
0x180144f4c  mov     rcx, r14
0x180144f4f  mov     eax, 2
0x180144f54  mul     rcx
0x180144f57  mov     rcx, rax
0x180144f5a  test    rdx, rdx
0x180144f5d  jnz     short loc_180144F9A
0x180144f5f  mov     eax, 2
0x180144f64  mul     rcx
0x180144f67  test    rdx, rdx
0x180144f6a  jnz     short loc_180144F9A
0x180144f6c  lea     rbx, [rax+1]
0x180144f70  cmp     rbx, rax
0x180144f73  jb      short loc_180144F9A
0x180144f75  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180144f7c  mov     rax, [rcx]
0x180144f7f  mov     rdx, rbx
0x180144f82  mov     rax, [rax+70h]
0x180144f86  call    cs:__guard_dispatch_icall_fptr
0x180144f8c  mov     rdi, rax
0x180144f8f  test    rax, rax
0x180144f92  jz      loc_18014536C
0x180144f98  jmp     short loc_180144FA0
0x180144f9a  mov     rbx, r12
0x180144f9d  mov     rdi, r14
0x180144fa0  mov     [rsp+228h+var_1D0], rdi
0x180144fa5  test    rdi, rdi
0x180144fa8  jz      short loc_180144FFD
0x180144faa  mov     rcx, [r15+28h]
0x180144fae  test    rcx, rcx
0x180144fb1  jz      short loc_180144FC2
0x180144fb3  mov     rdx, r12
0x180144fb6  inc     rdx
0x180144fb9  cmp     word ptr [rcx+rdx*2], 0
0x180144fbe  jnz     short loc_180144FB6
0x180144fc0  jmp     short loc_180144FCC
0x180144fc2  mov     rdx, r14; MaxCountInBytes
0x180144fc5  lea     rcx, Class; Src
0x180144fcc  mov     r9, rbx; DstSizeInBytes
0x180144fcf  mov     r8, rdi; Dst
0x180144fd2  call    WstrToChar
0x180144fd7  mov     r8, rbx; unsigned __int64
0x180144fda  mov     rdx, rdi; unsigned __int8 *
0x180144fdd  mov     rcx, rdi; unsigned __int8 *
0x180144fe0  call    ?ConvertTerminatorToBinary@@YAHPEBEPEAE_K@Z; ConvertTerminatorToBinary(uchar const *,uchar *,unsigned __int64)
0x180144fe5  mov     r9d, eax
0x180144fe8  cmp     eax, 0FFFFFFFFh
0x180144feb  jz      loc_18014538E
0x180144ff1  jmp     short loc_18014502E
0x180144ff3  xor     r14d, r14d
0x180144ff6  mov     r15, [rsp+228h+var_1B8]
  ... truncated ...
```
