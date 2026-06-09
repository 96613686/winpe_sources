# CHtmlHelpControl::LoadContentsFile(char const *)

- ea: `0x18001a0ac`
- end: `0x18001a442`
- name: `?LoadContentsFile@CHtmlHelpControl@@QEAAHPEBD@Z`
- size: `918`
- prototype: `__int64 __fastcall(CHtmlHelpControl *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002efa0`

## callees

- `0x180001728`
- `0x180003fc0`
- `0x1800095c8`
- `0x180011900`
- `0x180012cd0`
- `0x180012f60`
- `0x180013174`
- `0x18001341c`
- `0x180018e24`
- `0x180019668`
- `0x18001a0ac`
- `0x18002fb58`
- `0x18003a9e0`
- `0x180056b00`
- `0x180068790`
- `0x18006e4b8`
- `0x180075c42`
- `0x180075c90`

## import_xrefs

- `msvcrt!_msize` at `0x18001a164`
- `msvcrt!_msize` at `0x18001a1af`
- `msvcrt!_msize` at `0x18001a164`
- `msvcrt!_msize` at `0x18001a1af`
- `SHLWAPI!StrStrA` at `0x18001a193`
- `SHLWAPI!StrStrA` at `0x18001a193`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHtmlHelpControl::LoadContentsFile(CHtmlHelpControl *this, char *a2)
{
  COleDispatchDriver *v4; // rcx
  int v5; // ecx
  __int64 v6; // rax
  PSTR v7; // rax
  char *v8; // rsi
  void *v9; // rax
  int v10; // ecx
  CToc *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int CodePage; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // rax
  CInfoType *v21; // rcx
  __int64 v22; // rcx
  const unsigned int *v23; // rdx
  CInfoType *v24; // rax
  void *Block[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v26[272]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !a2 || !*a2 )
    return 0;
  if ( !(unsigned int)CHtmlHelpControl::ConvertToCacheFile(this, a2, v26, 0x104u) )
  {
    v26[0] = 0;
    if ( !(unsigned int)IsCompiledHtmlFile(a2, 0) )
    {
      v4 = (COleDispatchDriver *)*((_QWORD *)this + 62);
      if ( v4 )
      {
        Block[0] = 0;
        COleDispatchDriver::InvokeHelper(v4, 211, 2u, 8u, Block, 0);
        v5 = (int)Block[0];
        if ( Block[0] )
          v5 = _msize(Block[0]);
        v6 = -1;
        do
          ++v6;
        while ( a2[v6] );
        CStr::ReSize((CStr *)Block, v6 + v5);
        v7 = StrStrA((PCSTR)Block[0], "::");
        if ( v7 )
        {
          v8 = v7 + 2;
          v9 = Block[0];
          if ( Block[0] )
          {
            v10 = _msize(Block[0]);
            v9 = Block[0];
          }
          else
          {
            v10 = 0;
          }
          if ( StringCchCopyA(v8, (unsigned __int64)v9 + v10 - (_QWORD)v8, a2) < 0 )
          {
            CWStr::~CWStr((CWStr *)Block);
            return 0;
          }
          StringCchCopyA(v26, 0x104u, (const char *)Block[0]);
        }
        CWStr::~CWStr((CWStr *)Block);
      }
    }
    if ( !v26[0] )
    {
      AuthorMsg(0x1D805u, a2);
      StringCchCopyA(v26, 0x104u, a2);
      v26[259] = 0;
    }
  }
  v12 = (CToc *)operator new(0x238u);
  Block[0] = v12;
  if ( v12 )
    v12 = CToc::CToc(v12, this, *((struct IUnknown **)this + 1), 0);
  *((_QWORD *)this + 75) = v12;
  if ( v12 && (v13 = *((_QWORD *)v12 + 67)) != 0 && (v14 = *(_QWORD *)(v13 + 608)) != 0 )
    CodePage = CTitleInformation::GetCodePage(*(CTitleInformation **)(v14 + 192));
  else
    CodePage = *((_DWORD *)this + 301);
  if ( !(unsigned int)CSiteMap::ReadFromFile((CSiteMap *)(*((_QWORD *)this + 75) + 32LL), v26, 0, this, CodePage) )
    return 0;
  v16 = *((_QWORD *)this + 75);
  if ( *(_DWORD *)(v16 + 64) != 1 )
  {
    *(_DWORD *)(v16 + 392) = 1;
    *(_DWORD *)(*((_QWORD *)this + 75) + 396LL) = 1;
  }
  v17 = *((_QWORD *)this + 75);
  if ( !*(_QWORD *)(v17 + 560) )
  {
    v18 = *(_QWORD *)(v17 + 536);
    if ( v18 && (v19 = *(_QWORD *)(v18 + 608)) != 0 && *(_QWORD *)(v19 + 24) )
    {
      v20 = operator new(0x70u);
      Block[0] = v20;
      if ( v20 )
        v21 = CInfoType::CInfoType((CInfoType *)v20);
      else
        v21 = 0;
      *(_QWORD *)(*((_QWORD *)this + 75) + 560LL) = v21;
      CInfoType::CopyTo(
        *(CInfoType **)(*((_QWORD *)this + 75) + 560LL),
        *(struct CHmData *const *)(*(_QWORD *)(*((_QWORD *)this + 75) + 536LL) + 608LL));
      v22 = *((_QWORD *)this + 75);
      v23 = *(const unsigned int **)(*(_QWORD *)(*(_QWORD *)(v22 + 536) + 608LL) + 32LL);
      if ( v23 )
      {
        if ( CInfoType::AnyInfoTypes(*(CInfoType **)(v22 + 560), v23) )
          memcpy_0(
            *(void **)(*(_QWORD *)(*((_QWORD *)this + 75) + 560LL) + 80LL),
            *(const void **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 75) + 536LL) + 608LL) + 32LL),
            4 * *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 75) + 560LL) + 44LL));
      }
    }
    else
    {
      v24 = (CInfoType *)operator new(0x70u);
      Block[0] = v24;
      if ( v24 )
        v24 = CInfoType::CInfoType(v24);
      *(_QWORD *)(*((_QWORD *)this + 75) + 560LL) = v24;
      CInfoType::operator=(*(CInfoType **)(*((_QWORD *)this + 75) + 560LL));
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001a0ac  mov     [rsp-8+arg_10], rbx
0x18001a0b1  mov     [rsp-8+arg_18], rsi
0x18001a0b6  push    rbp
0x18001a0b7  push    rdi
0x18001a0b8  push    r15
0x18001a0ba  lea     rbp, [rsp-60h]
0x18001a0bf  sub     rsp, 160h
0x18001a0c6  mov     rax, cs:__security_cookie
0x18001a0cd  xor     rax, rsp
0x18001a0d0  mov     [rbp+70h+var_20], rax
0x18001a0d4  mov     rdi, rdx
0x18001a0d7  mov     rbx, rcx
0x18001a0da  test    rdx, rdx
0x18001a0dd  jz      loc_18001A1E3
0x18001a0e3  cmp     byte ptr [rdx], 0
0x18001a0e6  jz      loc_18001A1E3
0x18001a0ec  mov     r15d, 104h
0x18001a0f2  mov     r9d, r15d; unsigned __int64
0x18001a0f5  lea     r8, [rsp+170h+var_130]; char *
0x18001a0fa  call    ?ConvertToCacheFile@CHtmlHelpControl@@QEAAHPEBDPEAD_K@Z; CHtmlHelpControl::ConvertToCacheFile(char const *,char *,unsigned __int64)
0x18001a0ff  test    eax, eax
0x18001a101  jnz     loc_18001A258
0x18001a107  mov     [rsp+170h+var_130], al
0x18001a10b  xor     edx, edx; this
0x18001a10d  mov     rcx, rdi; pszStart
0x18001a110  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x18001a115  test    eax, eax
0x18001a117  jnz     loc_18001A226
0x18001a11d  mov     rcx, [rbx+1F0h]; this
0x18001a124  test    rcx, rcx
0x18001a127  jz      loc_18001A226
0x18001a12d  mov     [rsp+170h+Block], 0
0x18001a136  lea     r9d, [rax+8]; unsigned __int16
0x18001a13a  lea     r8d, [rax+2]; unsigned __int16
0x18001a13e  mov     [rsp+170h+var_148], 0; unsigned __int8 *
0x18001a147  lea     rax, [rsp+170h+Block]
0x18001a14c  mov     [rsp+170h+var_150], rax; void *
0x18001a151  lea     edx, [r15-31h]; int
0x18001a155  call    ?InvokeHelper@COleDispatchDriver@@QEAAXJGGPEAXPEBEZZ; COleDispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x18001a15a  mov     rcx, [rsp+170h+Block]; Block
0x18001a15f  test    rcx, rcx
0x18001a162  jz      short loc_18001A16D
0x18001a164  call    cs:__imp__msize
0x18001a16a  mov     rcx, rax
0x18001a16d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a171  inc     rax
0x18001a174  cmp     byte ptr [rdi+rax], 0
0x18001a178  jnz     short loc_18001A171
0x18001a17a  lea     edx, [rax+rcx]; int
0x18001a17d  lea     rcx, [rsp+170h+Block]; this
0x18001a182  call    ?ReSize@CStr@@QEAAXH@Z; CStr::ReSize(int)
0x18001a187  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x18001a18e  mov     rcx, [rsp+170h+Block]; pszFirst
0x18001a193  call    cs:__imp_StrStrA
0x18001a199  test    rax, rax
0x18001a19c  jz      short loc_18001A21C
0x18001a19e  lea     rsi, [rax+2]
0x18001a1a2  mov     rax, [rsp+170h+Block]
0x18001a1a7  test    rax, rax
0x18001a1aa  jz      short loc_18001A1BF
0x18001a1ac  mov     rcx, rax; Block
0x18001a1af  call    cs:__imp__msize
0x18001a1b5  mov     rcx, rax
0x18001a1b8  mov     rax, [rsp+170h+Block]
0x18001a1bd  jmp     short loc_18001A1C1
0x18001a1bf  xor     ecx, ecx
0x18001a1c1  movsxd  rdx, ecx
0x18001a1c4  sub     rdx, rsi
0x18001a1c7  add     rdx, rax; unsigned __int64
0x18001a1ca  mov     r8, rdi; char *
0x18001a1cd  mov     rcx, rsi; char *
0x18001a1d0  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001a1d5  test    eax, eax
0x18001a1d7  jns     short loc_18001A209
0x18001a1d9  lea     rcx, [rsp+170h+Block]; this
0x18001a1de  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001a1e3  xor     eax, eax
0x18001a1e5  mov     rcx, [rbp+70h+var_20]
0x18001a1e9  xor     rcx, rsp; StackCookie
0x18001a1ec  call    __security_check_cookie
0x18001a1f1  lea     r11, [rsp+170h+var_10]
0x18001a1f9  mov     rbx, [r11+30h]
0x18001a1fd  mov     rsi, [r11+38h]
0x18001a201  mov     rsp, r11
0x18001a204  pop     r15
0x18001a206  pop     rdi
0x18001a207  pop     rbp
0x18001a208  retn
0x18001a209  mov     r8, [rsp+170h+Block]; char *
0x18001a20e  mov     rdx, r15; unsigned __int64
0x18001a211  lea     rcx, [rsp+170h+var_130]; char *
0x18001a216  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001a21b  nop
0x18001a21c  lea     rcx, [rsp+170h+Block]; this
0x18001a221  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001a226  cmp     [rsp+170h+var_130], 0
0x18001a22b  jnz     short loc_18001A258
0x18001a22d  mov     r9, rbx
0x18001a230  mov     r8, [rbx+0E8h]
0x18001a237  mov     rdx, rdi; char *
0x18001a23a  mov     ecx, 1D805h; unsigned int
0x18001a23f  call    AuthorMsg
0x18001a244  mov     r8, rdi; char *
0x18001a247  mov     rdx, r15; unsigned __int64
0x18001a24a  lea     rcx, [rsp+170h+var_130]; char *
0x18001a24f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001a254  mov     [rbp+70h+var_2D], 0
0x18001a258  mov     ecx, 238h; Size
0x18001a25d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a262  mov     [rsp+170h+Block], rax
0x18001a267  test    rax, rax
0x18001a26a  jz      short loc_18001A27E
0x18001a26c  xor     r9d, r9d; struct CHHWinType *
0x18001a26f  mov     r8, [rbx+8]; struct IUnknown *
0x18001a273  mov     rdx, rbx; struct CHtmlHelpControl *
0x18001a276  mov     rcx, rax; this
0x18001a279  call    ??0CToc@@QEAA@PEAVCHtmlHelpControl@@PEAUIUnknown@@PEAVCHHWinType@@@Z; CToc::CToc(CHtmlHelpControl *,IUnknown *,CHHWinType *)
0x18001a27e  mov     [rbx+258h], rax
0x18001a285  test    rax, rax
0x18001a288  jz      short loc_18001A2B0
0x18001a28a  mov     rcx, [rax+218h]
0x18001a291  test    rcx, rcx
0x18001a294  jz      short loc_18001A2B0
0x18001a296  mov     rcx, [rcx+260h]
0x18001a29d  test    rcx, rcx
0x18001a2a0  jz      short loc_18001A2B0
0x18001a2a2  mov     rcx, [rcx+0C0h]; this
0x18001a2a9  call    ?GetCodePage@CTitleInformation@@QEAAIXZ; CTitleInformation::GetCodePage(void)
0x18001a2ae  jmp     short loc_18001A2B6
0x18001a2b0  mov     eax, [rbx+4B4h]
0x18001a2b6  mov     rcx, [rbx+258h]
0x18001a2bd  add     rcx, 20h ; ' '; this
0x18001a2c1  mov     dword ptr [rsp+170h+var_150], eax; unsigned int
0x18001a2c5  mov     r9, rbx; struct CHtmlHelpControl *
0x18001a2c8  xor     r8d, r8d; int
0x18001a2cb  lea     rdx, [rsp+170h+var_130]; char *
0x18001a2d0  call    ?ReadFromFile@CSiteMap@@QEAAHPEBDHPEAVCHtmlHelpControl@@I@Z; CSiteMap::ReadFromFile(char const *,int,CHtmlHelpControl *,uint)
0x18001a2d5  test    eax, eax
0x18001a2d7  jz      loc_18001A1E3
0x18001a2dd  mov     rcx, [rbx+258h]
0x18001a2e4  mov     edi, 1
0x18001a2e9  cmp     [rcx+40h], edi
0x18001a2ec  jz      short loc_18001A301
0x18001a2ee  mov     [rcx+188h], edi
0x18001a2f4  mov     rax, [rbx+258h]
0x18001a2fb  mov     [rax+18Ch], edi
0x18001a301  mov     rax, [rbx+258h]
0x18001a308  cmp     qword ptr [rax+230h], 0
0x18001a310  jnz     loc_18001A43B
0x18001a316  mov     rax, [rax+218h]
0x18001a31d  test    rax, rax
0x18001a320  jz      loc_18001A3F9
0x18001a326  mov     rax, [rax+260h]
0x18001a32d  test    rax, rax
0x18001a330  jz      loc_18001A3F9
0x18001a336  cmp     qword ptr [rax+18h], 0
0x18001a33b  jz      loc_18001A3F9
0x18001a341  mov     ecx, 70h ; 'p'; Size
0x18001a346  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a34b  mov     [rsp+170h+Block], rax
0x18001a350  test    rax, rax
0x18001a353  jz      short loc_18001A362
0x18001a355  mov     rcx, rax; this
0x18001a358  call    ??0CInfoType@@QEAA@XZ; CInfoType::CInfoType(void)
0x18001a35d  mov     rcx, rax
0x18001a360  jmp     short loc_18001A364
0x18001a362  xor     ecx, ecx
0x18001a364  mov     rax, [rbx+258h]
0x18001a36b  mov     [rax+230h], rcx
0x18001a372  mov     rcx, [rbx+258h]
0x18001a379  mov     rdx, [rcx+218h]
0x18001a380  mov     rdx, [rdx+260h]; struct CHmData *
0x18001a387  mov     rcx, [rcx+230h]; this
0x18001a38e  call    ?CopyTo@CInfoType@@QEAAXQEAVCHmData@@@Z; CInfoType::CopyTo(CHmData * const)
0x18001a393  mov     rcx, [rbx+258h]
0x18001a39a  mov     rax, [rcx+218h]
0x18001a3a1  mov     rdx, [rax+260h]
0x18001a3a8  mov     rdx, [rdx+20h]; unsigned int *
0x18001a3ac  test    rdx, rdx
0x18001a3af  jz      loc_18001A43B
0x18001a3b5  mov     rcx, [rcx+230h]; this
0x18001a3bc  call    ?AnyInfoTypes@CInfoType@@QEBAHPEBI@Z; CInfoType::AnyInfoTypes(uint const *)
0x18001a3c1  test    eax, eax
0x18001a3c3  jz      short loc_18001A43B
0x18001a3c5  mov     rdx, [rbx+258h]
0x18001a3cc  mov     rcx, [rdx+230h]
0x18001a3d3  mov     eax, [rcx+2Ch]
0x18001a3d6  shl     eax, 2
0x18001a3d9  movsxd  r8, eax; Size
0x18001a3dc  mov     rax, [rdx+218h]
0x18001a3e3  mov     rdx, [rax+260h]
0x18001a3ea  mov     rdx, [rdx+20h]; Src
0x18001a3ee  mov     rcx, [rcx+50h]; void *
0x18001a3f2  call    memcpy_0
0x18001a3f7  jmp     short loc_18001A43B
0x18001a3f9  mov     ecx, 70h ; 'p'; Size
0x18001a3fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a403  mov     [rsp+170h+Block], rax
0x18001a408  test    rax, rax
0x18001a40b  jz      short loc_18001A416
0x18001a40d  mov     rcx, rax; this
0x18001a410  call    ??0CInfoType@@QEAA@XZ; CInfoType::CInfoType(void)
0x18001a415  nop
0x18001a416  mov     rcx, [rbx+258h]
0x18001a41d  mov     [rcx+230h], rax
0x18001a424  mov     rcx, [rbx+258h]
0x18001a42b  lea     rdx, [rcx+20h]
0x18001a42f  mov     rcx, [rcx+230h]; this
0x18001a436  call    ??4CInfoType@@QEAAAEBV0@AEBVCSiteMap@@@Z; CInfoType::operator=(CSiteMap const &)
0x18001a43b  mov     eax, edi
0x18001a43d  jmp     loc_18001A1E5
```
