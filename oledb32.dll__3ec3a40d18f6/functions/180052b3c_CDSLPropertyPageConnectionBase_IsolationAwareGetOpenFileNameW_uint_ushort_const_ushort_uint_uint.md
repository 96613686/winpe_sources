# CDSLPropertyPageConnectionBase::IsolationAwareGetOpenFileNameW(uint,ushort const *,ushort * &,uint,uint)

- ea: `0x180052b3c`
- end: `0x180052e7c`
- name: `?IsolationAwareGetOpenFileNameW@CDSLPropertyPageConnectionBase@@IEAAJIPEBGAEAPEAGII@Z`
- size: `832`
- prototype: `__int64 __fastcall(CDSLPropertyPageConnectionBase *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 **, UINT uID, UINT)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180053060`
- `0x18005318c`

## callees

- `0x180013870`
- `0x180029414`
- `0x180029560`
- `0x18004d88c`
- `0x18004da48`
- `0x18004ddc8`
- `0x180052b3c`
- `0x18007e6ca`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `msvcrt!wcschr` at `0x180052bd8`
- `msvcrt!wcschr` at `0x180052bd8`
- `msvcrt!_wsplitpath_s` at `0x180052c8c`
- `msvcrt!_wsplitpath_s` at `0x180052c8c`
- `MSDART!mpMalloc` at `0x180052c22`
- `MSDART!mpMalloc` at `0x180052c22`
- `MSDART!mpFree` at `0x180052e1d`
- `MSDART!mpFree` at `0x180052e1d`
- `USER32!LoadStringW` at `0x180052bbb`
- `USER32!LoadStringW` at `0x180052dc6`
- `USER32!LoadStringW` at `0x180052df8`
- `USER32!LoadStringW` at `0x180052bbb`
- `USER32!LoadStringW` at `0x180052dc6`
- `USER32!LoadStringW` at `0x180052df8`

## string_xrefs

- `0x180052d07`: `<CDSLPropertyPageConnectionBase::IsolationAwareGetOpenFileNameW|OLEDB|ERR> `
- `0x180052d26`: `<CDSLPropertyPageConnectionBase::IsolationAwareGetOpenFileNameW|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDSLPropertyPageConnectionBase::IsolationAwareGetOpenFileNameW(
        CDSLPropertyPageConnectionBase *this,
        UINT a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        UINT uID,
        UINT a6)
{
  WCHAR *i; // rcx
  wchar_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rcx
  unsigned __int16 *v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  unsigned int v23; // ebx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  unsigned __int16 v33[4]; // [rsp+50h] [rbp+0h] BYREF
  _QWORD v34[4]; // [rsp+58h] [rbp+8h] BYREF
  int v35; // [rsp+7Ch] [rbp+2Ch]
  unsigned __int16 *v36; // [rsp+80h] [rbp+30h]
  unsigned __int64 v37; // [rsp+88h] [rbp+38h]
  __int64 v38; // [rsp+90h] [rbp+40h]
  unsigned __int16 *v39; // [rsp+A0h] [rbp+50h]
  WCHAR *v40; // [rsp+A8h] [rbp+58h]
  int v41; // [rsp+B0h] [rbp+60h]
  WCHAR *v42; // [rsp+B8h] [rbp+68h]
  wchar_t Drive[8]; // [rsp+F0h] [rbp+A0h] BYREF
  wchar_t Dir[256]; // [rsp+100h] [rbp+B0h] BYREF
  wchar_t Ext[256]; // [rsp+300h] [rbp+2B0h] BYREF
  wchar_t Filename[256]; // [rsp+500h] [rbp+4B0h] BYREF
  WCHAR Buffer[512]; // [rsp+700h] [rbp+6B0h] BYREF
  WCHAR v48[512]; // [rsp+B00h] [rbp+AB0h] BYREF
  WCHAR v49[512]; // [rsp+F00h] [rbp+EB0h] BYREF

  *(_QWORD *)v33 = 152;
  *a4 = 0;
  memset_0(v34, 0, 0x90u);
  v34[0] = *((_QWORD *)this + 1);
  v34[1] = hModule;
  LoadStringW(hInstance, a2, Buffer, 512);
  for ( i = Buffer; ; i = v11 + 1 )
  {
    v11 = wcschr(i, 0x7Cu);
    if ( !v11 )
      break;
    *v11 = 0;
  }
  v34[3] = 0;
  v34[2] = Buffer;
  v13 = -1;
  v35 = 0;
  v14 = 260;
  LODWORD(v37) = 260;
  if ( a3 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    if ( (unsigned int)v15 > 0x104 )
      v14 = v15;
    LODWORD(v37) = v14;
  }
  v16 = (unsigned __int16 *)mpMalloc(2LL * (unsigned int)(v14 + 1), v12);
  *a4 = v16;
  if ( !v16 )
    return 2147942414LL;
  v36 = v16;
  *v16 = 0;
  v39 = 0;
  if ( !a3 )
  {
LABEL_25:
    v38 = 0;
    LoadStringW(hInstance, uID, v48, 512);
    v40 = v48;
    v41 = 6148;
    LoadStringW(hInstance, a6, v49, 512);
    v42 = v49;
    if ( (unsigned int)IsolationAwareGetOpenFileNameW(v33) )
      return 0;
    mpFree(*a4, v25, v26, v27);
    *a4 = 0;
    v28 = IsolationAwareCommDlgExtendedError();
    if ( !v28 )
      return 1;
    v29 = v28 - 2;
    if ( v29 )
    {
      v30 = v29 - 7;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          v32 = v31 - 2;
          if ( v32 )
          {
            if ( v32 != 12277 )
              return 2147500037LL;
          }
        }
      }
    }
    return 2147942414LL;
  }
  _wsplitpath_s(a3, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
  v17 = -1;
  do
    ++v17;
  while ( Dir[v17] );
  do
    ++v13;
  while ( Drive[v13] );
  v18 = v13 + v17 + 1;
  v19 = 2 * v18 + 15;
  if ( v19 <= 2 * v18 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  v39 = v33;
  if ( v33 )
  {
    StringCchPrintfW(v33, v18, L"%ls%ls", Drive, Dir);
    if ( (unsigned int)IsValidFileName(Filename) && (unsigned int)IsValidFileName(Ext) )
      StringCchPrintfW(v36, (unsigned int)v37, L"%ls%ls", Filename, Ext);
    goto LABEL_25;
  }
  v23 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CDSLPropertyPageConnectionBase::IsolationAwareGetOpenFileNameW|OLEDB|ERR> ", 0x3E4u);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(
                             off_1800C83E8[0],
                             1019913,
                             L"<CDSLPropertyPageConnectionBase::IsolationAwareGetOpenFileNameW|Trace|HR> ",
                             2147942414LL);
  }
  return v23;
}

```

## disassembly

```asm
0x180052b3c  push    rbp
0x180052b3e  push    rbx
0x180052b3f  push    rsi
0x180052b40  push    rdi
0x180052b41  push    r14
0x180052b43  push    r15
0x180052b45  mov     eax, 1318h
0x180052b4a  call    _alloca_probe
0x180052b4f  sub     rsp, rax
0x180052b52  lea     rbp, [rsp+50h]
0x180052b57  mov     rax, cs:__security_cookie
0x180052b5e  xor     rax, rbp
0x180052b61  mov     [rbp+12F0h+var_40], rax
0x180052b68  mov     rsi, r8
0x180052b6b  mov     qword ptr [rbp+12F0h+var_12F0], 98h
0x180052b73  mov     edi, edx
0x180052b75  mov     rbx, rcx
0x180052b78  xor     r15d, r15d
0x180052b7b  lea     rcx, [rbp+12F0h+var_12E8]; void *
0x180052b7f  xor     edx, edx; Val
0x180052b81  mov     [r9], r15
0x180052b84  mov     r8d, 90h; Size
0x180052b8a  mov     r14, r9
0x180052b8d  call    memset_0
0x180052b92  mov     rax, [rbx+8]
0x180052b96  lea     r8, [rbp+12F0h+Buffer]; lpBuffer
0x180052b9d  mov     rcx, cs:hInstance; hInstance
0x180052ba4  mov     r9d, 200h; cchBufferMax
0x180052baa  mov     [rbp+12F0h+var_12E8], rax
0x180052bae  mov     edx, edi; uID
0x180052bb0  mov     rax, cs:hModule
0x180052bb7  mov     [rbp+12F0h+var_12E0], rax
0x180052bbb  call    cs:__imp_LoadStringW
0x180052bc1  lea     rcx, [rbp+12F0h+Buffer]
0x180052bc8  lea     ebx, [r15+7Ch]
0x180052bcc  jmp     short loc_180052BD6
0x180052bce  mov     [rax], r15w
0x180052bd2  lea     rcx, [rax+2]; Str
0x180052bd6  mov     edx, ebx; Ch
0x180052bd8  call    cs:__imp_wcschr
0x180052bde  test    rax, rax
0x180052be1  jnz     short loc_180052BCE
0x180052be3  lea     rax, [rbp+12F0h+Buffer]
0x180052bea  mov     [rbp+12F0h+var_12D0], r15
0x180052bee  mov     [rbp+12F0h+var_12D8], rax
0x180052bf2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180052bf6  mov     [rbp+12F0h+var_12C4], r15d
0x180052bfa  mov     eax, 104h
0x180052bff  mov     dword ptr [rbp+12F0h+var_12B8], eax
0x180052c02  test    rsi, rsi
0x180052c05  jz      short loc_180052C1C
0x180052c07  mov     rcx, rbx
0x180052c0a  inc     rcx
0x180052c0d  cmp     [rsi+rcx*2], r15w
0x180052c12  jnz     short loc_180052C0A
0x180052c14  cmp     ecx, eax
0x180052c16  cmova   eax, ecx
0x180052c19  mov     dword ptr [rbp+12F0h+var_12B8], eax
0x180052c1c  lea     ecx, [rax+1]
0x180052c1f  add     rcx, rcx
0x180052c22  call    cs:__imp_mpMalloc
0x180052c28  mov     [r14], rax
0x180052c2b  test    rax, rax
0x180052c2e  jz      loc_180052E58
0x180052c34  mov     [rbp+12F0h+var_12C0], rax
0x180052c38  mov     [rax], r15w
0x180052c3c  mov     [rbp+12F0h+var_12A0], r15
0x180052c40  test    rsi, rsi
0x180052c43  jz      loc_180052DA8
0x180052c49  mov     ecx, 100h
0x180052c4e  lea     rax, [rbp+12F0h+var_1040]
0x180052c55  mov     [rsp+1340h+ExtCount], rcx; ExtCount
0x180052c5a  lea     r9, [rbp+12F0h+Dir]; Dir
0x180052c61  mov     [rsp+1340h+Ext], rax; Ext
0x180052c66  lea     rdx, [rbp+12F0h+Drive]; Drive
0x180052c6d  mov     [rsp+1340h+FilenameCount], rcx; FilenameCount
0x180052c72  lea     rax, [rbp+12F0h+var_E40]
0x180052c79  mov     [rsp+1340h+Filename], rax; Filename
0x180052c7e  mov     r8d, 3; DriveCount
0x180052c84  mov     [rsp+1340h+DirCount], rcx; DirCount
0x180052c89  mov     rcx, rsi; FullPath
0x180052c8c  call    cs:__imp__wsplitpath_s
0x180052c92  lea     rcx, [rbp+12F0h+Dir]
0x180052c99  mov     rax, rbx
0x180052c9c  inc     rax
0x180052c9f  cmp     [rcx+rax*2], r15w
0x180052ca4  jnz     short loc_180052C9C
0x180052ca6  lea     rcx, [rbp+12F0h+Drive]
0x180052cad  inc     rbx
0x180052cb0  cmp     [rcx+rbx*2], r15w
0x180052cb5  jnz     short loc_180052CAD
0x180052cb7  lea     rdx, [rax+1]
0x180052cbb  add     rdx, rbx
0x180052cbe  lea     rax, [rdx+rdx]
0x180052cc2  lea     rcx, [rax+0Fh]
0x180052cc6  cmp     rcx, rax
0x180052cc9  ja      short loc_180052CD5
0x180052ccb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180052cd5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180052cd9  mov     rax, rcx
0x180052cdc  call    _alloca_probe
0x180052ce1  sub     rsp, rcx
0x180052ce4  lea     rcx, [rsp+1340h+var_12F0]; unsigned __int16 *
0x180052ce9  mov     [rbp+12F0h+var_12A0], rcx
0x180052ced  test    rcx, rcx
0x180052cf0  jnz     short loc_180052D43
0x180052cf2  mov     eax, cs:_bidGblFlags
0x180052cf8  mov     ebx, 8007000Eh
0x180052cfd  test    al, 2
0x180052cff  jz      short loc_180052D3C
0x180052d01  mov     r8d, 3E4h; unsigned int
0x180052d07  lea     rdx, aCdslpropertypa; "<CDSLPropertyPageConnectionBase::Isolat"...
0x180052d0e  mov     ecx, ebx; int
0x180052d10  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180052d15  mov     eax, cs:_bidGblFlags
0x180052d1b  test    al, 2
0x180052d1d  jz      short loc_180052D3C
0x180052d1f  mov     rcx, cs:off_1800C83E8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180052d26  lea     r8, aCdslpropertypa_0; "<CDSLPropertyPageConnectionBase::Isolat"...
0x180052d2d  mov     r9d, ebx
0x180052d30  mov     edx, 0F9009h
0x180052d35  call    _bidTraceHR
0x180052d3a  mov     ebx, eax
0x180052d3c  mov     eax, ebx
0x180052d3e  jmp     loc_180052E5D
0x180052d43  lea     rax, [rbp+12F0h+Dir]
0x180052d4a  lea     r9, [rbp+12F0h+Drive]
0x180052d51  mov     [rsp+1340h+DirCount], rax
0x180052d56  lea     r8, aLsLs_1; "%ls%ls"
0x180052d5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052d62  lea     rcx, [rbp+12F0h+var_E40]; unsigned __int16 *
0x180052d69  call    ?IsValidFileName@@YAHPEBG@Z; IsValidFileName(ushort const *)
0x180052d6e  test    eax, eax
0x180052d70  jz      short loc_180052DA8
0x180052d72  lea     rcx, [rbp+12F0h+var_1040]; unsigned __int16 *
0x180052d79  call    ?IsValidFileName@@YAHPEBG@Z; IsValidFileName(ushort const *)
0x180052d7e  test    eax, eax
0x180052d80  jz      short loc_180052DA8
0x180052d82  mov     edx, dword ptr [rbp+12F0h+var_12B8]; unsigned __int64
0x180052d85  lea     rax, [rbp+12F0h+var_1040]
0x180052d8c  mov     rcx, [rbp+12F0h+var_12C0]; unsigned __int16 *
0x180052d90  lea     r9, [rbp+12F0h+var_E40]
0x180052d97  lea     r8, aLsLs_1; "%ls%ls"
0x180052d9e  mov     [rsp+1340h+DirCount], rax
0x180052da3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052da8  mov     edx, [rbp+12F0h+uID]; uID
0x180052dae  lea     r8, [rbp+12F0h+var_840]; lpBuffer
0x180052db5  mov     rcx, cs:hInstance; hInstance
0x180052dbc  mov     r9d, 200h; cchBufferMax
0x180052dc2  mov     [rbp+12F0h+var_12B0], r15
0x180052dc6  call    cs:__imp_LoadStringW
0x180052dcc  mov     edx, [rbp+12F0h+arg_28]; uID
0x180052dd2  lea     rax, [rbp+12F0h+var_840]
0x180052dd9  mov     rcx, cs:hInstance; hInstance
0x180052de0  lea     r8, [rbp+12F0h+var_440]; lpBuffer
0x180052de7  mov     r9d, 200h; cchBufferMax
0x180052ded  mov     [rbp+12F0h+var_1298], rax
0x180052df1  mov     [rbp+12F0h+var_1290], 1804h
0x180052df8  call    cs:__imp_LoadStringW
0x180052dfe  lea     rax, [rbp+12F0h+var_440]
0x180052e05  lea     rcx, [rbp+12F0h+var_12F0]
0x180052e09  mov     [rbp+12F0h+var_1288], rax
0x180052e0d  call    IsolationAwareGetOpenFileNameW
0x180052e12  test    eax, eax
0x180052e14  jz      short loc_180052E1A
0x180052e16  xor     eax, eax
0x180052e18  jmp     short loc_180052E5D
0x180052e1a  mov     rcx, [r14]
0x180052e1d  call    cs:__imp_mpFree
0x180052e23  mov     [r14], r15
0x180052e26  call    IsolationAwareCommDlgExtendedError
0x180052e2b  test    eax, eax
0x180052e2d  jz      short loc_180052E51
0x180052e2f  sub     eax, 2
0x180052e32  jz      short loc_180052E58
0x180052e34  sub     eax, 7
0x180052e37  jz      short loc_180052E58
0x180052e39  sub     eax, 1
0x180052e3c  jz      short loc_180052E58
0x180052e3e  sub     eax, 2
0x180052e41  jz      short loc_180052E58
0x180052e43  cmp     eax, 2FF5h
0x180052e48  jz      short loc_180052E58
0x180052e4a  mov     eax, 80004005h
0x180052e4f  jmp     short loc_180052E5D
0x180052e51  mov     eax, 1
0x180052e56  jmp     short loc_180052E5D
0x180052e58  mov     eax, 8007000Eh
0x180052e5d  mov     rcx, [rbp+12F0h+var_40]
0x180052e64  xor     rcx, rbp; StackCookie
0x180052e67  call    __security_check_cookie
0x180052e6c  lea     rsp, [rbp+12C8h]
0x180052e73  pop     r15
0x180052e75  pop     r14
0x180052e77  pop     rdi
0x180052e78  pop     rsi
0x180052e79  pop     rbx
0x180052e7a  pop     rbp
0x180052e7b  retn
```
