# WriteXmlFormatFile(ISequentialStream *,wchar_t const *,IXmlFmtExceptionPoster *,BCP_COL_INFO *)

- ea: `0x180146070`
- end: `0x1801463d4`
- name: `?WriteXmlFormatFile@@YAJPEAUISequentialStream@@PEB_WPEAVIXmlFmtExceptionPoster@@PEAUBCP_COL_INFO@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(struct ISequentialStream *, const wchar_t *, struct IXmlFmtExceptionPoster *, struct BCP_COL_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18011acf0`

## callees

- `0x180003090`
- `0x180003d20`
- `0x180003d80`
- `0x180146070`
- `0x180146490`
- `0x180146c90`
- `0x1801482e0`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801461a0`
- `KERNEL32!GetLastError` at `0x1801461aa`
- `KERNEL32!GetLastError` at `0x180146327`
- `KERNEL32!GetLastError` at `0x1801461a0`
- `KERNEL32!GetLastError` at `0x1801461aa`
- `KERNEL32!GetLastError` at `0x180146327`
- `KERNEL32!WriteFile` at `0x18014631d`
- `KERNEL32!WriteFile` at `0x18014631d`
- `KERNEL32!GetFileSize` at `0x18014618a`
- `KERNEL32!GetFileSize` at `0x18014618a`
- `KERNEL32!CreateFileW` at `0x18014616b`
- `KERNEL32!CreateFileW` at `0x18014616b`
- `KERNEL32!CloseHandle` at `0x1801461f4`
- `KERNEL32!CloseHandle` at `0x1801463a4`
- `KERNEL32!CloseHandle` at `0x1801461f4`
- `KERNEL32!CloseHandle` at `0x1801463a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WriteXmlFormatFile(
        struct ISequentialStream *a1,
        const wchar_t *a2,
        struct IXmlFmtExceptionPoster *a3,
        struct BCP_COL_INFO *a4)
{
  unsigned int v7; // esi
  signed int v8; // edi
  void *v9; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  void (__fastcall *v12)(CFileReadStream *__hidden); // rax
  _QWORD *XMLFormatStreamFromBCP; // rax
  __int64 v14; // rbx
  bool v15; // zf
  signed int v16; // eax
  __int64 v18; // rdx
  struct ISequentialStream *v19; // [rsp+40h] [rbp-1148h] BYREF
  struct IXmlFmtExceptionPoster *v20; // [rsp+48h] [rbp-1140h]
  __int64 v21; // [rsp+50h] [rbp-1138h] BYREF
  __int64 v22; // [rsp+58h] [rbp-1130h]
  const CHRESULTException *v23; // [rsp+60h] [rbp-1128h] BYREF
  const CMSXMLLoadException *v24; // [rsp+68h] [rbp-1120h] BYREF
  const CBcpFmtException *v25; // [rsp+70h] [rbp-1118h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp-1110h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+7Ch] [rbp-110Ch] BYREF
  _QWORD v28[2]; // [rsp+80h] [rbp-1108h] BYREF
  DWORD FileSizeHigh[4]; // [rsp+90h] [rbp-10F8h] BYREF
  _BYTE v30[160]; // [rsp+A0h] [rbp-10E8h] BYREF
  _BYTE Buffer[4096]; // [rsp+140h] [rbp-1048h] BYREF

  v20 = a3;
  v7 = 0;
  v28[0] = &CFileWriteStream::`vftable';
  v28[1] = 1;
  *(__m128i *)FileSizeHigh = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  memset_0(v30, 0, sizeof(v30));
  try
  {
    CBulkFormat::CBulkFormat((CBulkFormat *)v30);
    v22 = 0;
    v8 = 0;
    if ( a2 && *a2 )
    {
      v9 = *(void **)FileSizeHigh;
      if ( *(_QWORD *)FileSizeHigh != -1 )
      {
        v8 = -2147221302;
        goto LABEL_15;
      }
      FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
      *(_QWORD *)FileSizeHigh = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSizeHigh[2] = GetFileSize(FileW, &FileSizeHigh[3]);
        if ( FileSizeHigh[2] != -1 || !GetLastError() )
          goto LABEL_20;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
      {
LABEL_24:
        v19 = a1;
        if ( a1 )
          ((void (__fastcall *)(struct ISequentialStream *))a1->lpVtbl->AddRef)(a1);
        XMLFormatStreamFromBCP = (_QWORD *)CBulkFormat::GetXMLFormatStreamFromBCP(v30, &v21, &v19, a4);
        v14 = *XMLFormatStreamFromBCP;
        if ( *XMLFormatStreamFromBCP )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 8LL))(*XMLFormatStreamFromBCP);
        v22 = v14;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        while ( 1 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, DWORD *))(*(_QWORD *)v14 + 24LL))(
                 v14,
                 Buffer,
                 4096,
                 &nNumberOfBytesToWrite);
          v15 = v8 == 0;
          if ( v8 >= 0 )
          {
            v7 = 0;
            NumberOfBytesWritten = 0;
            if ( *(_QWORD *)FileSizeHigh == -1 )
            {
              v7 = -2147221301;
            }
            else if ( !WriteFile(*(HANDLE *)FileSizeHigh, Buffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
            {
              v16 = GetLastError();
              v7 = v16;
              if ( v16 > 0 )
                v7 = (unsigned __int16)v16 | 0x80070000;
            }
            v15 = v8 == 0;
          }
          if ( !v15 )
            break;
          if ( v7 )
            goto LABEL_42;
        }
        if ( v8 != 1 )
          goto LABEL_44;
        if ( !v7 )
          goto LABEL_43;
LABEL_42:
        v8 = v7;
        if ( v7 != 1 )
          goto LABEL_44;
LABEL_43:
        v8 = 0;
LABEL_44:
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        CBulkFormat::~CBulkFormat((CBulkFormat *)v30);
        goto LABEL_87;
      }
    }
    else
    {
      v8 = -2147221303;
    }
    v9 = *(void **)FileSizeHigh;
LABEL_15:
    v12 = *(void (__fastcall **)(CFileReadStream *__hidden))(v28[0] + 56LL);
    if ( v12 == CFileReadStream::Close )
    {
      if ( v9 != (void *)-1LL )
      {
        CloseHandle(v9);
        *(_QWORD *)FileSizeHigh = -1;
      }
      *(_QWORD *)&FileSizeHigh[2] = -1;
    }
    else
    {
      v12((CFileReadStream *)v28);
    }
LABEL_20:
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(off_180260790[0], 347145);
      CBulkFormat::~CBulkFormat((CBulkFormat *)v30);
      goto LABEL_87;
    }
    goto LABEL_24;
  }
  catch ( const CMSXMLLoadException *v24 )
  {
    if ( *((_DWORD *)v24 + 2) == 1 )
    {
      LODWORD(v19) = -2147221215;
      (*(void (__fastcall **)(struct IXmlFmtExceptionPoster *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2147746081LL);
    }
    else if ( *((_DWORD *)v24 + 2) == 2 )
    {
      LODWORD(v19) = -2147221213;
      (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD, _QWORD))v20)(
        v20,
        2147746083LL,
        *((unsigned int *)v24 + 1),
        *(unsigned int *)v24);
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      LODWORD(v19) = bidTraceHR(off_180260790[0], 389129, 2147500037LL);
    }
    else
    {
      LODWORD(v19) = -2147467259;
    }
    v8 = (int)v19;
  }
  catch ( const CBcpFmtException *v25 )
  {
    switch ( *(_DWORD *)v25 )
    {
      case 0:
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        v18 = 399369;
        goto LABEL_74;
      case 1:
        LODWORD(v19) = -2147221234;
        (*(void (__fastcall **)(struct IXmlFmtExceptionPoster *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2147746062LL);
        goto LABEL_76;
      case 2:
        LODWORD(v19) = -2147221233;
        (*(void (__fastcall **)(struct IXmlFmtExceptionPoster *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2147746063LL);
        goto LABEL_76;
      case 3:
        LODWORD(v19) = -2147221232;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746064LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 4:
        LODWORD(v19) = -2147221214;
        (*(void (__fastcall **)(struct IXmlFmtExceptionPoster *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2147746082LL);
        goto LABEL_76;
      case 5:
        LODWORD(v19) = -2147221231;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746065LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 6:
        LODWORD(v19) = -2147221230;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746066LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 7:
        LODWORD(v19) = -2147221229;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746067LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 8:
        LODWORD(v19) = -2147221228;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746068LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 9:
        LODWORD(v19) = -2147221227;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746069LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 0xA:
        LODWORD(v19) = -2147221225;
        (**(void (__fastcall ***)(struct IXmlFmtExceptionPoster *, __int64, _QWORD))v20)(
          v20,
          2147746071LL,
          *((unsigned int *)v25 + 1));
        goto LABEL_76;
      case 0xB:
        LODWORD(v19) = -2147221226;
        (*(void (__fastcall **)(struct IXmlFmtExceptionPoster *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2147746070LL);
        goto LABEL_76;
      default:
        if ( (bidGblFlags & 2) != 0 )
        {
          v18 = 448521;
LABEL_74:
          LODWORD(v19) = bidTraceHR(off_180260790[0], v18, 2147500037LL);
        }
        else
        {
LABEL_75:
          LODWORD(v19) = -2147467259;
        }
LABEL_76:
        v8 = (int)v19;
        goto LABEL_87;
    }
  }
  catch ( const CHRESULTException *v23 )
  {
    if ( (bidGblFlags & 2) != 0 )
      LODWORD(v19) = bidTraceHR(off_180260790[0], 455689, *(unsigned int *)v23);
    else
      LODWORD(v19) = *(_DWORD *)v23;
    v8 = (int)v19;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 )
      LODWORD(v19) = bidTraceHR(off_180260790[0], 459785, 2147500037LL);
    else
      LODWORD(v19) = -2147467259;
    v8 = (int)v19;
  }
LABEL_87:
  v28[0] = &CFileWriteStream::`vftable';
  if ( *(_QWORD *)FileSizeHigh != -1 )
    CloseHandle(*(HANDLE *)FileSizeHigh);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180146070  push    rbx
0x180146072  push    rsi
0x180146073  push    rdi
0x180146074  push    r12
0x180146076  push    r13
0x180146078  push    r14
0x18014607a  push    r15
0x18014607c  mov     eax, 1150h
0x180146081  call    _alloca_probe
0x180146086  sub     rsp, rax
0x180146089  mov     rax, cs:__security_cookie
0x180146090  xor     rax, rsp
0x180146093  mov     [rsp+1188h+var_48], rax
0x18014609b  mov     r15, r9
0x18014609e  mov     rbx, rdx
0x1801460a1  mov     r14, rcx
0x1801460a4  mov     [rsp+1188h+var_1140], r8
0x1801460a9  xor     r13d, r13d
0x1801460ac  mov     esi, r13d
0x1801460af  xorps   xmm0, xmm0
0x1801460b2  movups  [rsp+1188h+var_1108], xmm0
0x1801460ba  lea     r12, ??_7CFileWriteStream@@6B@; const CFileWriteStream::`vftable'
0x1801460c1  mov     qword ptr [rsp+1188h+var_1108], r12
0x1801460c9  mov     dword ptr [rsp+1188h+var_1108+8], 1
0x1801460d4  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1801460dc  movdqu  xmmword ptr [rsp+1188h+FileSizeHigh], xmm0
0x1801460e5  mov     [rsp+1188h+nNumberOfBytesToWrite], r13d
0x1801460ea  mov     [rsp+1188h+NumberOfBytesWritten], r13d
0x1801460ef  xor     edx, edx; Val
0x1801460f1  mov     r8d, 0A0h; Size
0x1801460f7  lea     rcx, [rsp+1188h+var_10E8]; void *
0x1801460ff  call    memset_0
0x180146104  lea     rcx, [rsp+1188h+var_10E8]; this
0x18014610c  call    ??0CBulkFormat@@QEAA@XZ; CBulkFormat::CBulkFormat(void)
0x180146111  nop
0x180146112  mov     [rsp+1188h+var_1130], r13
0x180146117  mov     edi, r13d
0x18014611a  test    rbx, rbx
0x18014611d  jz      loc_1801461C9
0x180146123  cmp     [rbx], r13w
0x180146127  jz      loc_1801461C9
0x18014612d  mov     rcx, qword ptr [rsp+1188h+FileSizeHigh]
0x180146135  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180146139  jz      short loc_180146145
0x18014613b  mov     edi, 800400CAh
0x180146140  jmp     loc_1801461D6
0x180146145  mov     [rsp+1188h+hTemplateFile], r13; hTemplateFile
0x18014614a  mov     [rsp+1188h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180146152  mov     [rsp+1188h+dwCreationDisposition], 2; dwCreationDisposition
0x18014615a  xor     r9d, r9d; lpSecurityAttributes
0x18014615d  mov     edx, 0C0000000h; dwDesiredAccess
0x180146162  mov     r8d, 1; dwShareMode
0x180146168  mov     rcx, rbx; lpFileName
0x18014616b  call    cs:__imp_CreateFileW
0x180146171  mov     qword ptr [rsp+1188h+FileSizeHigh], rax
0x180146179  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18014617d  jz      short loc_1801461AA
0x18014617f  lea     rdx, [rsp+1188h+FileSizeHigh+0Ch]; lpFileSizeHigh
0x180146187  mov     rcx, rax; hFile
0x18014618a  call    cs:__imp_GetFileSize
0x180146190  mov     [rsp+1188h+FileSizeHigh+8], eax
0x180146197  cmp     eax, 0FFFFFFFFh
0x18014619a  jnz     loc_180146222
0x1801461a0  call    cs:__imp_GetLastError
0x1801461a6  test    eax, eax
0x1801461a8  jz      short loc_180146222
0x1801461aa  call    cs:__imp_GetLastError
0x1801461b0  test    eax, eax
0x1801461b2  mov     edi, eax
0x1801461b4  jle     short loc_1801461BF
0x1801461b6  movzx   edi, ax
0x1801461b9  or      edi, 80070000h
0x1801461bf  test    edi, edi
0x1801461c1  jns     loc_180146254
0x1801461c7  jmp     short loc_1801461CE
0x1801461c9  mov     edi, 800400C9h
0x1801461ce  mov     rcx, qword ptr [rsp+1188h+FileSizeHigh]; hObject
0x1801461d6  mov     rax, qword ptr [rsp+1188h+var_1108]
0x1801461de  mov     rax, [rax+38h]
0x1801461e2  lea     rdx, ?Close@CFileReadStream@@UEAAXXZ; CFileReadStream::Close(void)
0x1801461e9  cmp     rax, rdx
0x1801461ec  jnz     short loc_180146214
0x1801461ee  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801461f2  jz      short loc_180146206
0x1801461f4  call    cs:__imp_CloseHandle
0x1801461fa  mov     qword ptr [rsp+1188h+FileSizeHigh], 0FFFFFFFFFFFFFFFFh
0x180146206  mov     qword ptr [rsp+1188h+FileSizeHigh+8], 0FFFFFFFFFFFFFFFFh
0x180146212  jmp     short loc_180146222
0x180146214  lea     rcx, [rsp+1188h+var_1108]
0x18014621c  call    cs:__guard_dispatch_icall_fptr
0x180146222  test    edi, edi
0x180146224  jns     short loc_180146254
0x180146226  test    byte ptr cs:_bidGblFlags, 2
0x18014622d  jz      short loc_180146241
0x18014622f  mov     edx, 54C09h
0x180146234  mov     rcx, cs:off_180260790; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\cl"...
0x18014623b  call    _bidTraceMark
0x180146240  nop
0x180146241  lea     rcx, [rsp+1188h+var_10E8]; this
0x180146249  call    ??1CBulkFormat@@QEAA@XZ; CBulkFormat::~CBulkFormat(void)
0x18014624e  nop
0x18014624f  jmp     loc_18014638E
0x180146254  mov     [rsp+1188h+var_1148], r14
0x180146259  test    r14, r14
0x18014625c  jz      short loc_18014626E
0x18014625e  mov     rax, [r14]
0x180146261  mov     rcx, r14
0x180146264  mov     rax, [rax+8]
0x180146268  call    cs:__guard_dispatch_icall_fptr
0x18014626e  mov     r9, r15
0x180146271  lea     r8, [rsp+1188h+var_1148]
0x180146276  lea     rdx, [rsp+1188h+var_1138]
0x18014627b  lea     rcx, [rsp+1188h+var_10E8]
0x180146283  call    ?GetXMLFormatStreamFromBCP@CBulkFormat@@QEAA?AV?$CComPtr@UISequentialStream@@@@V2@PEAUBCP_COL_INFO@@@Z; CBulkFormat::GetXMLFormatStreamFromBCP(CComPtr<ISequentialStream>,BCP_COL_INFO *)
0x180146288  nop
0x180146289  mov     rbx, [rax]
0x18014628c  test    rbx, rbx
0x18014628f  jz      short loc_1801462A1
0x180146291  mov     rax, [rbx]
0x180146294  mov     rcx, rbx
0x180146297  mov     rax, [rax+8]
0x18014629b  call    cs:__guard_dispatch_icall_fptr
0x1801462a1  mov     [rsp+1188h+var_1130], rbx
0x1801462a6  mov     rcx, [rsp+1188h+var_1138]
0x1801462ab  test    rcx, rcx
0x1801462ae  jz      short loc_1801462BE
0x1801462b0  mov     rax, [rcx]
0x1801462b3  mov     rax, [rax+10h]
0x1801462b7  call    cs:__guard_dispatch_icall_fptr
0x1801462bd  nop
0x1801462be  xchg    ax, ax
0x1801462c0  mov     rax, [rbx]
0x1801462c3  lea     r9, [rsp+1188h+nNumberOfBytesToWrite]
0x1801462c8  mov     r8d, 1000h
0x1801462ce  lea     rdx, [rsp+1188h+Buffer]
0x1801462d6  mov     rcx, rbx
0x1801462d9  mov     rax, [rax+18h]
0x1801462dd  call    cs:__guard_dispatch_icall_fptr
0x1801462e3  mov     edi, eax
0x1801462e5  test    eax, eax
0x1801462e7  js      short loc_18014633E
0x1801462e9  mov     esi, r13d
0x1801462ec  mov     [rsp+1188h+NumberOfBytesWritten], r13d
0x1801462f1  mov     rcx, qword ptr [rsp+1188h+FileSizeHigh]; hFile
0x1801462f9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801462fd  jnz     short loc_180146306
0x1801462ff  mov     esi, 800400CBh
0x180146304  jmp     short loc_18014633C
0x180146306  mov     qword ptr [rsp+1188h+dwCreationDisposition], r13; lpOverlapped
0x18014630b  lea     r9, [rsp+1188h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180146310  mov     r8d, [rsp+1188h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180146315  lea     rdx, [rsp+1188h+Buffer]; lpBuffer
0x18014631d  call    cs:__imp_WriteFile
0x180146323  test    eax, eax
0x180146325  jnz     short loc_18014633C
0x180146327  call    cs:__imp_GetLastError
0x18014632d  mov     esi, eax
0x18014632f  test    eax, eax
0x180146331  jle     short loc_18014633C
0x180146333  movzx   esi, ax
0x180146336  or      esi, 80070000h
0x18014633c  test    edi, edi
0x18014633e  jnz     short loc_18014634A
0x180146340  test    esi, esi
0x180146342  jz      loc_1801462C0
0x180146348  jmp     short loc_180146353
0x18014634a  cmp     edi, 1
0x18014634d  jnz     short loc_18014635D
0x18014634f  test    esi, esi
0x180146351  jz      short loc_18014635A
0x180146353  cmp     esi, 1
0x180146356  mov     edi, esi
0x180146358  jnz     short loc_18014635D
0x18014635a  mov     edi, r13d
0x18014635d  test    rbx, rbx
0x180146360  jz      short loc_180146373
0x180146362  mov     rax, [rbx]
0x180146365  mov     rcx, rbx
0x180146368  mov     rax, [rax+10h]
0x18014636c  call    cs:__guard_dispatch_icall_fptr
0x180146372  nop
0x180146373  lea     rcx, [rsp+1188h+var_10E8]; this
0x18014637b  call    ??1CBulkFormat@@QEAA@XZ; CBulkFormat::~CBulkFormat(void)
0x180146380  nop
0x180146381  jmp     short loc_18014638E
0x180146383  mov     edi, dword ptr [rsp+1188h+var_1148]
0x180146387  lea     r12, ??_7CFileWriteStream@@6B@; const CFileWriteStream::`vftable'
0x18014638e  mov     qword ptr [rsp+1188h+var_1108], r12
0x180146396  mov     rcx, qword ptr [rsp+1188h+FileSizeHigh]; hObject
0x18014639e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801463a2  jz      short loc_1801463AA
0x1801463a4  call    cs:__imp_CloseHandle
0x1801463aa  mov     eax, edi
0x1801463ac  mov     rcx, [rsp+1188h+var_48]
0x1801463b4  xor     rcx, rsp; StackCookie
0x1801463b7  call    __security_check_cookie
0x1801463bc  add     rsp, 1150h
0x1801463c3  pop     r15
0x1801463c5  pop     r14
0x1801463c7  pop     r13
0x1801463c9  pop     r12
0x1801463cb  pop     rdi
0x1801463cc  pop     rsi
0x1801463cd  pop     rbx
0x1801463ce  retn
0x1801463cf  jmp     short loc_180146383
0x1801463d1  jmp     short loc_180146383
```
