# DWMIndirect::UpdateMonitorSurface(HRGN__ *,_DWMIndirectMoveMetaData *,uint)

- ea: `0x180006240`
- end: `0x180006876`
- name: `?UpdateMonitorSurface@DWMIndirect@@IEAAJPEAUHRGN__@@PEAU_DWMIndirectMoveMetaData@@I@Z`
- size: `1590`
- prototype: `__int64 __fastcall(DWMIndirect *__hidden this, HRGN, struct _DWMIndirectMoveMetaData *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update`

## callers

- `0x180006950`

## callees

- `0x18000160c`
- `0x180001868`
- `0x18000192c`
- `0x180001bfc`
- `0x180004130`
- `0x180004248`
- `0x180004480`
- `0x180004728`
- `0x180004af8`
- `0x180005f20`
- `0x18000601c`
- `0x180006098`
- `0x180006240`
- `0x18000687c`
- `0x18001a3bc`
- `0x18002b93a`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006363`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006363`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000637e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000637e`
- `USER32!IsRectEmpty` at `0x1800062c6`
- `USER32!IsRectEmpty` at `0x1800062c6`
- `GDI32!BitBlt` at `0x1800065c1`
- `GDI32!BitBlt` at `0x1800065c1`
- `GDI32!SelectClipRgn` at `0x180006482`
- `GDI32!SelectClipRgn` at `0x180006782`
- `GDI32!SelectClipRgn` at `0x180006482`
- `GDI32!SelectClipRgn` at `0x180006782`
- `GDI32!GetRgnBox` at `0x1800062bc`
- `GDI32!GetRgnBox` at `0x180006511`
- `GDI32!GetRgnBox` at `0x1800062bc`
- `GDI32!GetRgnBox` at `0x180006511`

## string_xrefs

- `0x1800062e4`: `DWMIndirect[%p]::UpdateMonitorSurface - no updates received.`
- `0x180006328`: `DWMIndirect[%p]::UpdateMonitorSurface - monitor updates received.`
- `0x180006435`: `Copying full monitor of width %d and height %d in response to reset event from driver`
- `0x180006488`: `UpdateMonitorSurface`
- `0x180006545`: `DWMIndirect::UpdateMonitorSurface copy dirty region [%d, %d, %d, %d]`
- `0x180006709`: `Failed to write entire frame to file: NON FATAL`

## pseudocode

```c
__int64 __fastcall DWMIndirect::UpdateMonitorSurface(
        DWMIndirect *this,
        HRGN a2,
        struct _DWMIndirectMoveMetaData *a3,
        unsigned int a4)
{
  __int64 v5; // rcx
  int v9; // r13d
  __int64 HnsTime; // r12
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  unsigned int i; // ebx
  __int64 v16; // rax
  __int128 v17; // xmm1
  HDC v18; // rcx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rcx
  int v25; // r9d
  unsigned __int8 *v26; // rdx
  bool v27; // sf
  int v28; // eax
  __int64 v29; // r9
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rcx
  int y1; // [rsp+38h] [rbp-C8h]
  int rop; // [rsp+40h] [rbp-C0h]
  const char *v45; // [rsp+60h] [rbp-A0h] BYREF
  const char *v46; // [rsp+68h] [rbp-98h] BYREF
  const char *v47; // [rsp+70h] [rbp-90h] BYREF
  const char *v48; // [rsp+78h] [rbp-88h] BYREF
  const char *v49; // [rsp+80h] [rbp-80h] BYREF
  int v50; // [rsp+88h] [rbp-78h] BYREF
  __int128 v51; // [rsp+90h] [rbp-70h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-60h]
  tagRECT rc; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v54[8]; // [rsp+C0h] [rbp-40h] BYREF
  int v55; // [rsp+D0h] [rbp-30h]
  wchar_t FileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  v50 = 0;
  v5 = *((_QWORD *)this + 114);
  v9 = 1;
  if ( v5 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5) )
  {
    rc = 0;
    if ( a2 )
      GetRgnBox(a2, &rc);
    if ( IsRectEmpty(&rc) && !a4 )
    {
      if ( (unsigned int)dword_180044008 > 5 )
      {
        v45 = (const char *)this;
        v46 = "DWMIndirect[%p]::UpdateMonitorSurface - no updates received.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v5,
          (unsigned int)byte_1800375D5,
          (_DWORD)a3,
          a4,
          (__int64)&v46,
          (__int64)&v45);
      }
      return 0;
    }
    v9 = 0;
  }
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v45 = (const char *)this;
    v46 = "DWMIndirect[%p]::UpdateMonitorSurface - monitor updates received.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&word_1800375AE,
      (_DWORD)a3,
      a4,
      (__int64)&v46,
      (__int64)&v45);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  HnsTime = DWMIndirect::GetHnsTime(this, *((_QWORD *)this + 24));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v14 = *((_QWORD *)this + 114);
  if ( v14 && !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 56LL))(*((_QWORD *)this + 114)) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 114) + 32LL))(
      *((_QWORD *)this + 114),
      *((_QWORD *)this + 10),
      *((_QWORD *)this + 9));
    (*(void (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 114) + 40LL))(
      *((_QWORD *)this + 114),
      HnsTime,
      &v50);
  }
  for ( i = 0; i < a4; ++i )
  {
    v16 = 32LL * i;
    v17 = *(_OWORD *)((char *)a3 + v16 + 16);
    v51 = *(_OWORD *)((char *)a3 + v16);
    v52 = v17;
    DWMIndirect::CopyInTarget(this, &v51);
  }
  if ( v50 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      LODWORD(v47) = *((_DWORD *)this + 27);
      LODWORD(v48) = *((_DWORD *)this + 26);
      v45 = "Copying full monitor of width %d and height %d in response to reset event from driver";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&word_18003757E,
        v12,
        v13,
        (__int64)&v45,
        (__int64)&v48,
        (__int64)&v47);
    }
    a2 = (HRGN)*((_QWORD *)this + 103);
  }
  if ( a2 )
  {
    v18 = (HDC)*((_QWORD *)this + 9);
    rc = 0;
    if ( !SelectClipRgn(v18, a2) && (unsigned int)dword_180044008 > 2 )
    {
      v45 = "UpdateMonitorSurface";
      LODWORD(v48) = 900;
      v46 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
      LODWORD(v47) = -2147467259;
      v49 = "ERROR SelectClipRgn";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)"ERROR SelectClipRgn",
        (unsigned int)byte_180037539,
        v19,
        v20,
        (__int64)&v49,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v48,
        (__int64)&v45);
    }
    GetRgnBox(a2, &rc);
    if ( (unsigned int)dword_180044008 > 5 )
    {
      LODWORD(v48) = rc.bottom;
      LODWORD(v47) = rc.right;
      LODWORD(v46) = rc.top;
      LODWORD(v45) = rc.left;
      v49 = "DWMIndirect::UpdateMonitorSurface copy dirty region [%d, %d, %d, %d]";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&word_1800374FE,
        v22,
        v23,
        (__int64)&v49,
        (__int64)&v45,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v48);
    }
    BitBlt(
      *((HDC *)this + 9),
      rc.left,
      rc.top,
      rc.right - rc.left + 1,
      rc.bottom - rc.top + 1,
      *((HDC *)this + 10),
      rc.left,
      rc.top,
      0xCC0020u);
    v24 = *((_QWORD *)this + 114);
    if ( v24 )
    {
      *(_QWORD *)&v51 = *(_QWORD *)((char *)this + 900);
      *((_QWORD *)&v51 + 1) = *((unsigned int *)this + 227);
      v52 = *((_OWORD *)this + 6);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v24 + 64LL))(v24, &v51);
    }
    DWMIndirect::DrawDebugRects(this, a2);
    if ( *((_DWORD *)this + 74) )
    {
      v25 = *((_DWORD *)this + 26);
      v26 = (unsigned __int8 *)*((_QWORD *)this + 12);
      v27 = -*((_DWORD *)this + 27) < 0;
      v28 = -*((_DWORD *)this + 27);
      *(_QWORD *)&v51 = 0;
      if ( v27 )
        v28 = *((_DWORD *)this + 27);
      *((_QWORD *)&v51 + 1) = 0;
      v52 = 0;
      PixelMap::Attach((PixelMap *)&v51, v26, v28 * 4 * v25, v25, v28, 4 * v25, 0x20u, y1, rop, v25, v28);
      if ( *((int *)this + 27) > 0 )
        PixelMap::RevertIteration((PixelMap *)&v51);
      memset_0(FileName, 0, 0x208u);
      v29 = *((unsigned int *)this + 205);
      v55 = 0;
      *(_OWORD *)v54 = 0;
      StringCchPrintfW(v54, 0xAu, L"%d", v29);
      StringCchCatW(FileName, v30, (const unsigned __int16 *)this + 150);
      StringCchCatW(FileName, v31, v54);
      StringCchCatW(FileName, v32, L".bmp");
      if ( !SaveImageToFile((struct PixelMap *)&v51, FileName, v33, v34) && (unsigned int)dword_180044008 > 2 )
      {
        v49 = "UpdateMonitorSurface";
        v47 = "Failed to write entire frame to file: NON FATAL";
        LODWORD(v45) = 956;
        v48 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
        LODWORD(v46) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v35,
          (unsigned int)byte_1800374B9,
          v36,
          v37,
          (__int64)&v47,
          (__int64)&v46,
          (__int64)&v48,
          (__int64)&v45,
          (__int64)&v49);
      }
      ++*((_DWORD *)this + 205);
      PixelMap::~PixelMap((PixelMap *)&v51);
    }
    if ( !SelectClipRgn(*((HDC *)this + 9), *((HRGN *)this + 103)) && (unsigned int)dword_180044008 > 2 )
    {
      v49 = "UpdateMonitorSurface";
      v47 = "ERROR SelectClipRgn";
      LODWORD(v45) = 968;
      v48 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
      LODWORD(v46) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v38,
        (unsigned int)&dword_180037474,
        v39,
        v40,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v48,
        (__int64)&v45,
        (__int64)&v49);
    }
  }
  v41 = *((_QWORD *)this + 114);
  if ( v41 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v41 + 56LL))(v41) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 114) + 48LL))(*((_QWORD *)this + 114));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 114) + 32LL))(*((_QWORD *)this + 114), 0, 0);
  }
  if ( v9 )
    DWMIndirect::UpdatePresentStats(this);
  return 0;
}

```

## disassembly

```asm
0x180006240  mov     [rsp-8+arg_18], rbx
0x180006245  push    rbp
0x180006246  push    rsi
0x180006247  push    rdi
0x180006248  push    r12
0x18000624a  push    r13
0x18000624c  push    r14
0x18000624e  push    r15
0x180006250  lea     rbp, [rsp-200h]
0x180006258  sub     rsp, 300h
0x18000625f  mov     rax, cs:__security_cookie
0x180006266  xor     rax, rsp
0x180006269  mov     [rbp+230h+var_40], rax
0x180006270  mov     rdi, rcx
0x180006273  mov     [rbp+230h+var_2A8], 0
0x18000627a  mov     rcx, [rcx+390h]
0x180006281  mov     r14d, r9d
0x180006284  mov     r15, r8
0x180006287  mov     rsi, rdx
0x18000628a  mov     r13d, 1
0x180006290  test    rcx, rcx
0x180006293  jz      loc_18000631D
0x180006299  mov     rax, [rcx]
0x18000629c  mov     rax, [rax+38h]
0x1800062a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a5  test    eax, eax
0x1800062a7  jz      short loc_18000631D
0x1800062a9  xorps   xmm0, xmm0
0x1800062ac  movups  xmmword ptr [rbp+230h+rc.left], xmm0
0x1800062b0  test    rsi, rsi
0x1800062b3  jz      short loc_1800062C2
0x1800062b5  lea     rdx, [rbp+230h+rc]; lprc
0x1800062b9  mov     rcx, rsi; hrgn
0x1800062bc  call    cs:__imp_GetRgnBox
0x1800062c2  lea     rcx, [rbp+230h+rc]; lprc
0x1800062c6  call    cs:__imp_IsRectEmpty
0x1800062cc  test    eax, eax
0x1800062ce  jz      short loc_18000631A
0x1800062d0  test    r14d, r14d
0x1800062d3  jnz     short loc_18000631A
0x1800062d5  mov     eax, cs:dword_180044008
0x1800062db  cmp     eax, 5
0x1800062de  jbe     loc_18000684A
0x1800062e4  lea     rax, aDwmindirectPUp; "DWMIndirect[%p]::UpdateMonitorSurface -"...
0x1800062eb  mov     [rsp+330h+var_2D0], rdi
0x1800062f0  mov     [rsp+330h+var_2C8], rax
0x1800062f5  lea     rdx, byte_1800375D5
0x1800062fc  lea     rax, [rsp+330h+var_2D0]
0x180006301  mov     [rsp+330h+hdcSrc], rax
0x180006306  lea     rax, [rsp+330h+var_2C8]
0x18000630b  mov     qword ptr [rsp+330h+cy], rax
0x180006310  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180006315  jmp     loc_18000684A
0x18000631a  xor     r13d, r13d
0x18000631d  mov     eax, cs:dword_180044008
0x180006323  cmp     eax, 5
0x180006326  jbe     short loc_180006359
0x180006328  lea     rax, aDwmindirectPUp_0; "DWMIndirect[%p]::UpdateMonitorSurface -"...
0x18000632f  mov     [rsp+330h+var_2D0], rdi
0x180006334  mov     [rsp+330h+var_2C8], rax
0x180006339  lea     rdx, word_1800375AE
0x180006340  lea     rax, [rsp+330h+var_2D0]
0x180006345  mov     [rsp+330h+hdcSrc], rax
0x18000634a  lea     rax, [rsp+330h+var_2C8]
0x18000634f  mov     qword ptr [rsp+330h+cy], rax
0x180006354  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180006359  lea     rbx, [rdi+88h]
0x180006360  mov     rcx, rbx; lpCriticalSection
0x180006363  call    cs:__imp_EnterCriticalSection
0x180006369  mov     rdx, [rdi+0C0h]; __int64
0x180006370  mov     rcx, rdi; this
0x180006373  call    ?GetHnsTime@DWMIndirect@@IEAA_J_J@Z; DWMIndirect::GetHnsTime(__int64)
0x180006378  mov     rcx, rbx; lpCriticalSection
0x18000637b  mov     r12, rax
0x18000637e  call    cs:__imp_LeaveCriticalSection
0x180006384  mov     rdx, [rdi+390h]
0x18000638b  test    rdx, rdx
0x18000638e  jz      short loc_1800063D8
0x180006390  mov     rcx, [rdx]
0x180006393  mov     rax, [rcx+38h]
0x180006397  mov     rcx, rdx
0x18000639a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639f  test    eax, eax
0x1800063a1  jnz     short loc_1800063D8
0x1800063a3  mov     rcx, [rdi+390h]
0x1800063aa  mov     r8, [rdi+48h]
0x1800063ae  mov     rdx, [rdi+50h]
0x1800063b2  mov     rax, [rcx]
0x1800063b5  mov     rax, [rax+20h]
0x1800063b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063be  mov     rcx, [rdi+390h]
0x1800063c5  lea     r8, [rbp+230h+var_2A8]
0x1800063c9  mov     rdx, r12
0x1800063cc  mov     rax, [rcx]
0x1800063cf  mov     rax, [rax+28h]
0x1800063d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d8  xor     r12d, r12d
0x1800063db  mov     ebx, r12d
0x1800063de  test    r14d, r14d
0x1800063e1  jz      short loc_18000640F
0x1800063e3  mov     eax, ebx
0x1800063e5  lea     rdx, [rbp+230h+var_2A0]
0x1800063e9  shl     rax, 5
0x1800063ed  mov     rcx, rdi
0x1800063f0  movups  xmm0, xmmword ptr [rax+r15]
0x1800063f5  movups  xmm1, xmmword ptr [rax+r15+10h]
0x1800063fb  movaps  [rbp+230h+var_2A0], xmm0
0x1800063ff  movaps  [rbp+230h+var_290], xmm1
0x180006403  call    ?CopyInTarget@DWMIndirect@@IEAAJU_DWMIndirectMoveMetaData@@@Z; DWMIndirect::CopyInTarget(_DWMIndirectMoveMetaData)
0x180006408  inc     ebx
0x18000640a  cmp     ebx, r14d
0x18000640d  jb      short loc_1800063E3
0x18000640f  cmp     [rbp+230h+var_2A8], r12d
0x180006413  jz      short loc_18000646B
0x180006415  mov     eax, cs:dword_180044008
0x18000641b  cmp     eax, 4
0x18000641e  jbe     short loc_180006464
0x180006420  mov     eax, [rdi+6Ch]
0x180006423  lea     rdx, word_18003757E
0x18000642a  mov     dword ptr [rsp+330h+var_2C0], eax
0x18000642e  mov     eax, [rdi+68h]
0x180006431  mov     dword ptr [rsp+330h+var_2B8], eax
0x180006435  lea     rax, aCopyingFullMon; "Copying full monitor of width %d and he"...
0x18000643c  mov     [rsp+330h+var_2D0], rax
0x180006441  lea     rax, [rsp+330h+var_2C0]
0x180006446  mov     qword ptr [rsp+330h+x1], rax
0x18000644b  lea     rax, [rsp+330h+var_2B8]
0x180006450  mov     [rsp+330h+hdcSrc], rax
0x180006455  lea     rax, [rsp+330h+var_2D0]
0x18000645a  mov     qword ptr [rsp+330h+cy], rax
0x18000645f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006464  mov     rsi, [rdi+338h]
0x18000646b  test    rsi, rsi
0x18000646e  jz      loc_1800067F6
0x180006474  mov     rcx, [rdi+48h]; hdc
0x180006478  xorps   xmm0, xmm0
0x18000647b  mov     rdx, rsi; hrgn
0x18000647e  movups  xmmword ptr [rbp+230h+rc.left], xmm0
0x180006482  call    cs:__imp_SelectClipRgn
0x180006488  lea     rbx, aUpdatemonitors; "UpdateMonitorSurface"
0x18000648f  mov     r15d, 80004005h
0x180006495  lea     r14, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000649c  lea     rcx, aErrorSelectcli; "ERROR SelectClipRgn"
0x1800064a3  test    eax, eax
0x1800064a5  jnz     short loc_18000650A
0x1800064a7  mov     eax, cs:dword_180044008
0x1800064ad  cmp     eax, 2
0x1800064b0  jbe     short loc_18000650A
0x1800064b2  lea     rax, [rsp+330h+var_2D0]
0x1800064b7  mov     [rsp+330h+var_2D0], rbx
0x1800064bc  mov     qword ptr [rsp+330h+rop], rax
0x1800064c1  lea     rdx, byte_180037539
0x1800064c8  lea     rax, [rsp+330h+var_2B8]
0x1800064cd  mov     dword ptr [rsp+330h+var_2B8], 384h
0x1800064d5  mov     qword ptr [rsp+330h+y1], rax
0x1800064da  lea     rax, [rsp+330h+var_2C8]
0x1800064df  mov     qword ptr [rsp+330h+x1], rax
0x1800064e4  lea     rax, [rsp+330h+var_2C0]
0x1800064e9  mov     [rsp+330h+hdcSrc], rax
0x1800064ee  lea     rax, [rbp+230h+var_2B0]
0x1800064f2  mov     qword ptr [rsp+330h+cy], rax
0x1800064f7  mov     [rsp+330h+var_2C8], r14
0x1800064fc  mov     dword ptr [rsp+330h+var_2C0], r15d
0x180006501  mov     [rbp+230h+var_2B0], rcx
0x180006505  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000650a  lea     rdx, [rbp+230h+rc]; lprc
0x18000650e  mov     rcx, rsi; hrgn
0x180006511  call    cs:__imp_GetRgnBox
0x180006517  mov     eax, cs:dword_180044008
0x18000651d  cmp     eax, 5
0x180006520  jbe     short loc_180006586
0x180006522  mov     eax, [rbp+230h+rc.bottom]
0x180006525  lea     rdx, word_1800374FE
0x18000652c  mov     dword ptr [rsp+330h+var_2B8], eax
0x180006530  mov     eax, [rbp+230h+rc.right]
0x180006533  mov     dword ptr [rsp+330h+var_2C0], eax
0x180006537  mov     eax, [rbp+230h+rc.top]
0x18000653a  mov     dword ptr [rsp+330h+var_2C8], eax
0x18000653e  mov     eax, [rbp+230h+rc.left]
0x180006541  mov     dword ptr [rsp+330h+var_2D0], eax
0x180006545  lea     rax, aDwmindirectUpd_0; "DWMIndirect::UpdateMonitorSurface copy "...
0x18000654c  mov     [rbp+230h+var_2B0], rax
0x180006550  lea     rax, [rsp+330h+var_2B8]
0x180006555  mov     qword ptr [rsp+330h+rop], rax
0x18000655a  lea     rax, [rsp+330h+var_2C0]
0x18000655f  mov     qword ptr [rsp+330h+y1], rax
0x180006564  lea     rax, [rsp+330h+var_2C8]
0x180006569  mov     qword ptr [rsp+330h+x1], rax
0x18000656e  lea     rax, [rsp+330h+var_2D0]
0x180006573  mov     [rsp+330h+hdcSrc], rax
0x180006578  lea     rax, [rbp+230h+var_2B0]
0x18000657c  mov     qword ptr [rsp+330h+cy], rax
0x180006581  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006586  mov     ecx, [rbp+230h+rc.bottom]
0x180006589  mov     r8d, [rbp+230h+rc.top]; y
0x18000658d  sub     ecx, r8d
0x180006590  mov     edx, [rbp+230h+rc.left]; x
0x180006593  inc     ecx
0x180006595  mov     r9d, [rbp+230h+rc.right]
0x180006599  mov     rax, [rdi+50h]
0x18000659d  sub     r9d, edx
0x1800065a0  mov     [rsp+330h+rop], 0CC0020h; int
0x1800065a8  inc     r9d; cx
0x1800065ab  mov     [rsp+330h+y1], r8d; int
0x1800065b0  mov     [rsp+330h+x1], edx; x1
0x1800065b4  mov     [rsp+330h+hdcSrc], rax; hdcSrc
0x1800065b9  mov     [rsp+330h+cy], ecx; cy
0x1800065bd  mov     rcx, [rdi+48h]; hdc
0x1800065c1  call    cs:__imp_BitBlt
0x1800065c7  mov     rcx, [rdi+390h]
0x1800065ce  test    rcx, rcx
0x1800065d1  jz      short loc_180006610
0x1800065d3  mov     rax, [rdi+384h]
0x1800065da  lea     rdx, [rbp+230h+var_2A0]
0x1800065de  mov     qword ptr [rbp+230h+var_2A0], rax
0x1800065e2  mov     eax, [rdi+38Ch]
0x1800065e8  mov     dword ptr [rbp+230h+var_2A0+8], eax
0x1800065eb  xor     eax, eax
0x1800065ed  mov     dword ptr [rbp+230h+var_2A0+0Ch], eax
0x1800065f0  mov     rax, [rdi+60h]
0x1800065f4  mov     qword ptr [rbp+230h+var_290], rax
0x1800065f8  mov     eax, [rdi+68h]
0x1800065fb  mov     dword ptr [rbp+230h+var_290+8], eax
0x1800065fe  mov     eax, [rdi+6Ch]
0x180006601  mov     dword ptr [rbp+230h+var_290+0Ch], eax
0x180006604  mov     rax, [rcx]
0x180006607  mov     rax, [rax+40h]
0x18000660b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006610  mov     rdx, rsi; HRGN
0x180006613  mov     rcx, rdi; this
0x180006616  call    ?DrawDebugRects@DWMIndirect@@IEAAJPEAUHRGN__@@@Z; DWMIndirect::DrawDebugRects(HRGN__ *)
0x18000661b  cmp     [rdi+128h], r12d
0x180006622  jz      loc_180006777
0x180006628  mov     r9d, [rdi+68h]; int
0x18000662c  xorps   xmm0, xmm0
0x18000662f  mov     eax, [rdi+6Ch]
0x180006632  mov     rdx, [rdi+60h]; unsigned __int8 *
0x180006636  neg     eax
0x180006638  mov     qword ptr [rbp+230h+var_2A0], r12
0x18000663c  cmovs   eax, [rdi+6Ch]
0x180006640  lea     ecx, ds:0[r9*4]
0x180006648  mov     [rsp+330h+var_2E0], eax; int
0x18000664c  mov     r8d, ecx
0x18000664f  mov     [rsp+330h+var_2E8], r9d; int
0x180006654  mov     [rsp+330h+x1], 20h ; ' '; unsigned int
0x18000665c  mov     dword ptr [rsp+330h+hdcSrc], ecx; int
0x180006660  lea     rcx, [rbp+230h+var_2A0]; this
0x180006664  imul    r8d, eax; int
0x180006668  mov     qword ptr [rbp+230h+var_2A0+8], r12
0x18000666c  movdqu  [rbp+230h+var_290], xmm0
0x180006671  mov     [rsp+330h+cy], eax; unsigned int
0x180006675  call    ?Attach@PixelMap@@QEAA_NPEAEHHHHHHHHH@Z; PixelMap::Attach(uchar *,int,int,int,int,int,int,int,int,int)
0x18000667a  cmp     [rdi+6Ch], r12d
0x18000667e  jle     short loc_180006689
0x180006680  lea     rcx, [rbp+230h+var_2A0]; this
0x180006684  call    ?RevertIteration@PixelMap@@QEAAXXZ; PixelMap::RevertIteration(void)
0x180006689  xor     edx, edx; Val
0x18000668b  lea     rcx, [rbp+230h+FileName]; void *
0x18000668f  mov     r8d, 208h; Size
0x180006695  call    memset_0
0x18000669a  mov     r9d, [rdi+334h]
0x1800066a1  lea     r8, aD; "%d"
0x1800066a8  xor     eax, eax
0x1800066aa  lea     rcx, [rbp+230h+var_270]; unsigned __int16 *
0x1800066ae  xorps   xmm0, xmm0
0x1800066b1  mov     [rbp+230h+var_260], eax
0x1800066b4  movups  xmmword ptr [rbp+230h+var_270], xmm0
0x1800066b8  lea     edx, [rax+0Ah]; unsigned __int64
0x1800066bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800066c0  lea     r8, [rdi+12Ch]; unsigned __int16 *
0x1800066c7  lea     rcx, [rbp+230h+FileName]; unsigned __int16 *
0x1800066cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800066d0  lea     r8, [rbp+230h+var_270]; unsigned __int16 *
0x1800066d4  lea     rcx, [rbp+230h+FileName]; unsigned __int16 *
0x1800066d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800066dd  lea     r8, aBmp; ".bmp"
0x1800066e4  lea     rcx, [rbp+230h+FileName]; unsigned __int16 *
0x1800066e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800066ed  lea     rdx, [rbp+230h+FileName]; FileName
0x1800066f1  lea     rcx, [rbp+230h+var_2A0]; struct PixelMap *
0x1800066f5  call    SaveImageToFile
0x1800066fa  test    al, al
0x1800066fc  jnz     short loc_180006768
0x1800066fe  mov     eax, cs:dword_180044008
0x180006704  cmp     eax, 2
0x180006707  jbe     short loc_180006768
0x180006709  lea     rax, aFailedToWriteE; "Failed to write entire frame to file: N"...
0x180006710  mov     [rbp+230h+var_2B0], rbx
0x180006714  mov     [rsp+330h+var_2C0], rax
0x180006719  lea     rdx, byte_1800374B9
0x180006720  lea     rax, [rbp+230h+var_2B0]
0x180006724  mov     dword ptr [rsp+330h+var_2D0], 3BCh
0x18000672c  mov     qword ptr [rsp+330h+rop], rax
0x180006731  lea     rax, [rsp+330h+var_2D0]
0x180006736  mov     qword ptr [rsp+330h+y1], rax
0x18000673b  lea     rax, [rsp+330h+var_2B8]
0x180006740  mov     qword ptr [rsp+330h+x1], rax
0x180006745  lea     rax, [rsp+330h+var_2C8]
0x18000674a  mov     [rsp+330h+hdcSrc], rax
0x18000674f  lea     rax, [rsp+330h+var_2C0]
  ... truncated ...
```
