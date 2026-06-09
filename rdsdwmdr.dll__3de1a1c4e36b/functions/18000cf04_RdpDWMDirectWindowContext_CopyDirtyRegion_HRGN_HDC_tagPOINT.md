# RdpDWMDirectWindowContext::CopyDirtyRegion(HRGN__ *,HDC__ *,tagPOINT *)

- ea: `0x18000cf04`
- end: `0x18000d4ab`
- name: `?CopyDirtyRegion@RdpDWMDirectWindowContext@@QEAAJPEAUHRGN__@@PEAUHDC__@@PEAUtagPOINT@@@Z`
- size: `1447`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *__hidden this, HRGN, HDC, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001196c`

## callees

- `0x180001188`
- `0x18000160c`
- `0x180001724`
- `0x180001bfc`
- `0x180002720`
- `0x180002a04`
- `0x18000cc98`
- `0x18000cf04`
- `0x18000df3c`
- `0x18000e0e8`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d20a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d20a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d381`
- `USER32!IsRectEmpty` at `0x18000d175`
- `USER32!IsRectEmpty` at `0x18000d175`
- `GDI32!CombineRgn` at `0x18000d2a2`
- `GDI32!CombineRgn` at `0x18000d2a2`
- `GDI32!BitBlt` at `0x18000d377`
- `GDI32!BitBlt` at `0x18000d377`
- `GDI32!SelectClipRgn` at `0x18000d333`
- `GDI32!SelectClipRgn` at `0x18000d409`
- `GDI32!SelectClipRgn` at `0x18000d333`
- `GDI32!SelectClipRgn` at `0x18000d409`
- `GDI32!GetRgnBox` at `0x18000d033`
- `GDI32!GetRgnBox` at `0x18000d033`
- `GDI32!CreateRectRgn` at `0x18000d1f8`
- `GDI32!CreateRectRgn` at `0x18000d1f8`
- `GDI32!DeleteObject` at `0x18000d2ad`
- `GDI32!DeleteObject` at `0x18000d2ad`

## string_xrefs

- `0x18000cf6d`: `Skipping update for window 0x%p`
- `0x18000cfbd`: `CopyDirtyRegion`
- `0x18000d0e2`: `CopyDirtyRegion`
- `0x18000d07b`: `CopyDirtyRegion for windowId=0x%x: dst(%d, %d) src(%d, %d) size(%d, %d).`
- `0x18000d118`: `Received update rect that is outside bounds for windowId=0x%x`
- `0x18000d3ab`: `BitBlt failed for dirty region copy`
- `0x18000d446`: `Failed to send the driver notification for surface update`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::CopyDirtyRegion(
        RdpDWMDirectWindowContext *this,
        HRGN a2,
        HDC a3,
        struct tagPOINT *a4)
{
  struct tagPOINT *v4; // rbx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  char *v11; // rdx
  int *v12; // rax
  HDC v13; // r13
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  HRGN RectRgn; // rax
  HRGN v20; // r12
  signed int LastError; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int16 *v25; // rdx
  const char **v26; // rax
  unsigned int v27; // ebx
  signed int v28; // eax
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // r9
  const char **x1; // [rsp+30h] [rbp-79h]
  const char **y1; // [rsp+38h] [rbp-71h]
  const char **rop; // [rsp+40h] [rbp-69h]
  const unsigned __int16 **ropa; // [rsp+40h] [rbp-69h]
  const char **v37; // [rsp+48h] [rbp-61h]
  const char *v38; // [rsp+60h] [rbp-49h] BYREF
  const char *v39; // [rsp+68h] [rbp-41h] BYREF
  const char *v40; // [rsp+70h] [rbp-39h] BYREF
  const char *v41; // [rsp+78h] [rbp-31h] BYREF
  const char *v42; // [rsp+80h] [rbp-29h] BYREF
  const char *v43; // [rsp+88h] [rbp-21h] BYREF
  int v44; // [rsp+90h] [rbp-19h] BYREF
  int v45; // [rsp+94h] [rbp-15h] BYREF
  const char *v46; // [rsp+98h] [rbp-11h] BYREF
  HDC hdcSrc; // [rsp+A0h] [rbp-9h] BYREF
  struct tagRECT rc; // [rsp+A8h] [rbp-1h] BYREF

  v4 = a4;
  hdcSrc = a3;
  v46 = (const char *)a4;
  rc = 0;
  v7 = RdpDWMDirectWindowContext::EnsureSurfaceBuffer(this);
  v10 = (unsigned int)v7;
  if ( v7 == 1 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v38 = (const char *)*((_QWORD *)this + 8);
      v39 = "Skipping update for window 0x%p";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)v7,
        (__int64)byte_180039695,
        v8,
        v9,
        (const unsigned __int16 **)&v39,
        (__int64)&v38);
    }
    return 0;
  }
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_180044008 <= 2 )
      return 0;
    v44 = 348;
    v38 = "EnsureSurfaceBuffer failed";
    v39 = "CopyDirtyRegion";
    v42 = "Error HResult failed";
    v45 = v7;
    v37 = &v38;
    v11 = (char *)qword_180039648;
    rop = &v39;
    y1 = (const char **)&v44;
    v12 = &v45;
LABEL_7:
    v41 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v10,
      (__int64)v11,
      v8,
      v9,
      (const unsigned __int16 **)&v42,
      (__int64)v12,
      (const unsigned __int16 **)&v41,
      (__int64)y1,
      (const unsigned __int16 **)rop,
      (const unsigned __int16 **)v37);
    return 0;
  }
  v13 = (HDC)*((_QWORD *)this + 7);
  GetRgnBox(a2, &rc);
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v45 = rc.bottom - rc.top;
    LODWORD(v39) = rc.top;
    v44 = rc.right - rc.left;
    LODWORD(v42) = v4->y;
    LODWORD(v41) = v4->x;
    v43 = (const char *)*((_QWORD *)this + 8);
    v40 = "CopyDirtyRegion for windowId=0x%x: dst(%d, %d) src(%d, %d) size(%d, %d).";
    LODWORD(v38) = rc.left;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)rc.left,
      (__int64)byte_1800395C5,
      v14,
      v15,
      (const unsigned __int16 **)&v40,
      (__int64)&v43,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&v41,
      (__int64)&v42,
      (__int64)&v44,
      (__int64)&v45);
  }
  if ( (unsigned int)RdpDWMDirectWindowContext::ClipUpdateRectToWindow(this, &rc) )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v40 = (const char *)*((_QWORD *)this + 8);
      v42 = "Received update rect that is outside bounds for windowId=0x%x";
      v43 = "CopyDirtyRegion";
      LODWORD(v38) = 383;
      v41 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      LODWORD(v39) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v16,
        (__int64)word_180039572,
        v17,
        v18,
        (const unsigned __int16 **)&v42,
        (__int64)&v39,
        (const unsigned __int16 **)&v41,
        (__int64)&v38,
        (const unsigned __int16 **)&v43,
        (__int64)&v40);
    }
    if ( IsRectEmpty(&rc) )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        return 0;
      v43 = "CopyDirtyRegion";
      v40 = "The window/dirty rect intersection is empty - skipping dirty region encoding";
      v11 = byte_180039525;
      LODWORD(v38) = 390;
      v42 = "Error condition failed";
      v37 = &v40;
      rop = &v43;
      y1 = &v38;
      v12 = (int *)&v39;
      LODWORD(v39) = -2147418113;
      goto LABEL_7;
    }
    RectRgn = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
    v20 = RectRgn;
    if ( !RectRgn )
    {
      LastError = GetLastError();
      v24 = (unsigned int)LastError;
      if ( LastError > 0 )
        v24 = (unsigned __int16)LastError | 0x80070000;
      if ( (int)v24 >= 0 )
        v24 = 2147500037LL;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v40 = "CopyDirtyRegion";
        v41 = "Failed to allocate the clip region";
        v25 = (__int16 *)qword_1800394E0;
        LODWORD(v38) = 393;
        ropa = (const unsigned __int16 **)&v40;
        x1 = &v43;
        v26 = &v41;
        v43 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
LABEL_23:
        LODWORD(v39) = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v24,
          (__int64)v25,
          v22,
          v23,
          (const unsigned __int16 **)v26,
          (__int64)&v39,
          (const unsigned __int16 **)x1,
          (__int64)&v38,
          ropa);
        return 0;
      }
      return 0;
    }
    v27 = CombineRgn(a2, RectRgn, a2, 1);
    DeleteObject(v20);
    if ( v27 <= 1 )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        return 0;
      v43 = "CopyDirtyRegion";
      v40 = "Null or error region resulting from clipping - skipping dirty region encoding";
      v11 = byte_180039493;
      LODWORD(v38) = 404;
      v42 = "Error condition failed";
      v37 = &v40;
      rop = &v43;
      y1 = &v38;
      v12 = (int *)&v39;
      LODWORD(v39) = -2147418113;
      goto LABEL_7;
    }
    v4 = (struct tagPOINT *)v46;
  }
  SelectClipRgn(v13, a2);
  if ( BitBlt(v13, rc.left, rc.top, rc.right - rc.left + 1, rc.bottom - rc.top + 1, hdcSrc, v4->x, v4->y, 0xCC0020u) )
  {
    RdpDWMDirectWindowContext::DrawDebugRects(this, a2);
    SelectClipRgn(v13, 0);
    v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HDC, struct tagRECT *))(**((_QWORD **)this + 82) + 64LL))(
            *((_QWORD *)this + 82),
            *((_QWORD *)this + 8),
            v13,
            &rc);
    if ( v29 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      LODWORD(v38) = v29;
      hdcSrc = (HDC)"CopyDirtyRegion";
      v46 = "Failed to send the driver notification for surface update";
      v40 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)byte_180039413,
        v30,
        v31,
        (const unsigned __int16 **)&v40,
        (const unsigned __int16 **)&v46,
        (__int64)&v38,
        (const unsigned __int16 **)&hdcSrc);
    }
  }
  else
  {
    v28 = GetLastError();
    v24 = (unsigned int)v28;
    if ( v28 > 0 )
      v24 = (unsigned __int16)v28 | 0x80070000;
    if ( (int)v24 >= 0 )
      v24 = 2147500037LL;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      hdcSrc = (HDC)"CopyDirtyRegion";
      v40 = "BitBlt failed for dirty region copy";
      v25 = &word_18003944E;
      LODWORD(v38) = 424;
      ropa = (const unsigned __int16 **)&hdcSrc;
      x1 = &v46;
      v26 = &v40;
      v46 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      goto LABEL_23;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cf04  push    rbp
0x18000cf06  push    rbx
0x18000cf07  push    rsi
0x18000cf08  push    rdi
0x18000cf09  push    r12
0x18000cf0b  push    r13
0x18000cf0d  push    r14
0x18000cf0f  push    r15
0x18000cf11  lea     rbp, [rsp-1Fh]
0x18000cf16  sub     rsp, 0C8h
0x18000cf1d  mov     rax, cs:__security_cookie
0x18000cf24  xor     rax, rsp
0x18000cf27  mov     [rbp+57h+var_48], rax
0x18000cf2b  mov     rbx, r9
0x18000cf2e  mov     [rbp+57h+var_60], r8
0x18000cf32  xorps   xmm0, xmm0
0x18000cf35  mov     [rbp+57h+var_68], rbx
0x18000cf39  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18000cf3d  mov     r15, rdx
0x18000cf40  mov     rsi, rcx
0x18000cf43  call    ?EnsureSurfaceBuffer@RdpDWMDirectWindowContext@@IEAAJXZ; RdpDWMDirectWindowContext::EnsureSurfaceBuffer(void)
0x18000cf48  mov     ecx, eax
0x18000cf4a  cmp     eax, 1
0x18000cf4d  jnz     short loc_18000CF94
0x18000cf4f  mov     eax, cs:dword_180044008
0x18000cf55  cmp     eax, 4
0x18000cf58  jbe     loc_18000D489
0x18000cf5e  mov     rax, [rsi+40h]
0x18000cf62  lea     rdx, byte_180039695
0x18000cf69  mov     [rbp+57h+var_A0], rax
0x18000cf6d  lea     rax, aSkippingUpdate; "Skipping update for window 0x%p"
0x18000cf74  mov     [rbp+57h+var_98], rax
0x18000cf78  lea     rax, [rbp+57h+var_A0]
0x18000cf7c  mov     [rsp+100h+hdcSrc], rax
0x18000cf81  lea     rax, [rbp+57h+var_98]
0x18000cf85  mov     qword ptr [rsp+100h+cy], rax
0x18000cf8a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000cf8f  jmp     loc_18000D489
0x18000cf94  test    ecx, ecx
0x18000cf96  jns     loc_18000D028
0x18000cf9c  mov     eax, cs:dword_180044008
0x18000cfa2  cmp     eax, 2
0x18000cfa5  jbe     loc_18000D489
0x18000cfab  lea     rax, aEnsuresurfaceb_1; "EnsureSurfaceBuffer failed"
0x18000cfb2  mov     [rbp+57h+var_70], 15Ch
0x18000cfb9  mov     [rbp+57h+var_A0], rax
0x18000cfbd  lea     rdi, aCopydirtyregio; "CopyDirtyRegion"
0x18000cfc4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000cfcb  mov     [rbp+57h+var_98], rdi
0x18000cfcf  mov     [rbp+57h+var_80], rax
0x18000cfd3  lea     r14, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000cfda  lea     rax, [rbp+57h+var_A0]
0x18000cfde  mov     [rbp+57h+var_6C], ecx
0x18000cfe1  mov     [rsp+100h+var_B8], rax
0x18000cfe6  lea     rdx, qword_180039648
0x18000cfed  lea     rax, [rbp+57h+var_98]
0x18000cff1  mov     qword ptr [rsp+100h+rop], rax
0x18000cff6  lea     rax, [rbp+57h+var_70]
0x18000cffa  mov     qword ptr [rsp+100h+y1], rax
0x18000cfff  lea     rax, [rbp+57h+var_88]
0x18000d003  mov     qword ptr [rsp+100h+x1], rax
0x18000d008  lea     rax, [rbp+57h+var_6C]
0x18000d00c  mov     [rsp+100h+hdcSrc], rax
0x18000d011  lea     rax, [rbp+57h+var_80]
0x18000d015  mov     qword ptr [rsp+100h+cy], rax
0x18000d01a  mov     [rbp+57h+var_88], r14
0x18000d01e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000d023  jmp     loc_18000D489
0x18000d028  mov     r13, [rsi+38h]
0x18000d02c  lea     rdx, [rbp+57h+rc]; lprc
0x18000d030  mov     rcx, r15; hrgn
0x18000d033  call    cs:__imp_GetRgnBox
0x18000d039  mov     eax, cs:dword_180044008
0x18000d03f  cmp     eax, 5
0x18000d042  jbe     loc_18000D0D6
0x18000d048  mov     edx, [rbp+57h+rc.top]
0x18000d04b  mov     eax, [rbp+57h+rc.bottom]
0x18000d04e  mov     ecx, [rbp+57h+rc.left]
0x18000d051  sub     eax, edx
0x18000d053  mov     [rbp+57h+var_6C], eax
0x18000d056  mov     eax, [rbp+57h+rc.right]
0x18000d059  sub     eax, ecx
0x18000d05b  mov     dword ptr [rbp+57h+var_98], edx
0x18000d05e  mov     [rbp+57h+var_70], eax
0x18000d061  lea     rdx, byte_1800395C5
0x18000d068  mov     eax, [rbx+4]
0x18000d06b  mov     dword ptr [rbp+57h+var_80], eax
0x18000d06e  mov     eax, [rbx]
0x18000d070  mov     dword ptr [rbp+57h+var_88], eax
0x18000d073  mov     rax, [rsi+40h]
0x18000d077  mov     [rbp+57h+var_78], rax
0x18000d07b  lea     rax, aCopydirtyregio_0; "CopyDirtyRegion for windowId=0x%x: dst("...
0x18000d082  mov     [rbp+57h+var_90], rax
0x18000d086  lea     rax, [rbp+57h+var_6C]
0x18000d08a  mov     [rsp+100h+var_A8], rax
0x18000d08f  lea     rax, [rbp+57h+var_70]
0x18000d093  mov     [rsp+100h+var_B0], rax
0x18000d098  lea     rax, [rbp+57h+var_80]
0x18000d09c  mov     [rsp+100h+var_B8], rax
0x18000d0a1  lea     rax, [rbp+57h+var_88]
0x18000d0a5  mov     qword ptr [rsp+100h+rop], rax
0x18000d0aa  lea     rax, [rbp+57h+var_98]
0x18000d0ae  mov     qword ptr [rsp+100h+y1], rax
0x18000d0b3  lea     rax, [rbp+57h+var_A0]
0x18000d0b7  mov     qword ptr [rsp+100h+x1], rax
0x18000d0bc  lea     rax, [rbp+57h+var_78]
0x18000d0c0  mov     [rsp+100h+hdcSrc], rax
0x18000d0c5  lea     rax, [rbp+57h+var_90]
0x18000d0c9  mov     qword ptr [rsp+100h+cy], rax
0x18000d0ce  mov     dword ptr [rbp+57h+var_A0], ecx
0x18000d0d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d0d6  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x18000d0da  mov     rcx, rsi; this
0x18000d0dd  call    ?ClipUpdateRectToWindow@RdpDWMDirectWindowContext@@IEAAHPEAUtagRECT@@@Z; RdpDWMDirectWindowContext::ClipUpdateRectToWindow(tagRECT *)
0x18000d0e2  lea     rdi, aCopydirtyregio; "CopyDirtyRegion"
0x18000d0e9  mov     r12d, 80004005h
0x18000d0ef  lea     r14, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000d0f6  test    eax, eax
0x18000d0f8  jz      loc_18000D32D
0x18000d0fe  mov     eax, cs:dword_180044008
0x18000d104  cmp     eax, 2
0x18000d107  jbe     short loc_18000D171
0x18000d109  mov     rax, [rsi+40h]
0x18000d10d  lea     rdx, word_180039572
0x18000d114  mov     [rbp+57h+var_90], rax
0x18000d118  lea     rax, aReceivedUpdate; "Received update rect that is outside bo"...
0x18000d11f  mov     [rbp+57h+var_80], rax
0x18000d123  lea     rax, [rbp+57h+var_90]
0x18000d127  mov     [rsp+100h+var_B8], rax
0x18000d12c  lea     rax, [rbp+57h+var_78]
0x18000d130  mov     qword ptr [rsp+100h+rop], rax
0x18000d135  lea     rax, [rbp+57h+var_A0]
0x18000d139  mov     qword ptr [rsp+100h+y1], rax
0x18000d13e  lea     rax, [rbp+57h+var_88]
0x18000d142  mov     qword ptr [rsp+100h+x1], rax
0x18000d147  lea     rax, [rbp+57h+var_98]
0x18000d14b  mov     [rsp+100h+hdcSrc], rax
0x18000d150  lea     rax, [rbp+57h+var_80]
0x18000d154  mov     qword ptr [rsp+100h+cy], rax
0x18000d159  mov     [rbp+57h+var_78], rdi
0x18000d15d  mov     dword ptr [rbp+57h+var_A0], 17Fh
0x18000d164  mov     [rbp+57h+var_88], r14
0x18000d168  mov     dword ptr [rbp+57h+var_98], r12d
0x18000d16c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000d171  lea     rcx, [rbp+57h+rc]; lprc
0x18000d175  call    cs:__imp_IsRectEmpty
0x18000d17b  test    eax, eax
0x18000d17d  jz      short loc_18000D1EA
0x18000d17f  mov     eax, cs:dword_180044008
0x18000d185  cmp     eax, 2
0x18000d188  jbe     loc_18000D489
0x18000d18e  lea     rax, aTheWindowDirty; "The window/dirty rect intersection is e"...
0x18000d195  mov     [rbp+57h+var_78], rdi
0x18000d199  mov     [rbp+57h+var_90], rax
0x18000d19d  lea     rdx, byte_180039525
0x18000d1a4  lea     rax, aErrorCondition; "Error condition failed"
0x18000d1ab  mov     dword ptr [rbp+57h+var_A0], 186h
0x18000d1b2  mov     [rbp+57h+var_80], rax
0x18000d1b6  lea     rax, [rbp+57h+var_90]
0x18000d1ba  mov     [rsp+100h+var_B8], rax
0x18000d1bf  lea     rax, [rbp+57h+var_78]
0x18000d1c3  mov     qword ptr [rsp+100h+rop], rax
0x18000d1c8  lea     rax, [rbp+57h+var_A0]
0x18000d1cc  mov     qword ptr [rsp+100h+y1], rax
0x18000d1d1  lea     rax, [rbp+57h+var_88]
0x18000d1d5  mov     qword ptr [rsp+100h+x1], rax
0x18000d1da  lea     rax, [rbp+57h+var_98]
0x18000d1de  mov     dword ptr [rbp+57h+var_98], 8000FFFFh
0x18000d1e5  jmp     loc_18000D00C
0x18000d1ea  mov     r9d, [rbp+57h+rc.bottom]; y2
0x18000d1ee  mov     r8d, [rbp+57h+rc.right]; x2
0x18000d1f2  mov     edx, [rbp+57h+rc.top]; y1
0x18000d1f5  mov     ecx, [rbp+57h+rc.left]; x1
0x18000d1f8  call    cs:__imp_CreateRectRgn
0x18000d1fe  mov     r12, rax
0x18000d201  test    rax, rax
0x18000d204  jnz     loc_18000D293
0x18000d20a  call    cs:__imp_GetLastError
0x18000d210  mov     ecx, eax
0x18000d212  test    eax, eax
0x18000d214  jle     short loc_18000D21F
0x18000d216  movzx   ecx, ax
0x18000d219  or      ecx, 80070000h
0x18000d21f  test    ecx, ecx
0x18000d221  mov     eax, 80004005h
0x18000d226  cmovns  ecx, eax
0x18000d229  mov     eax, cs:dword_180044008
0x18000d22f  cmp     eax, 2
0x18000d232  jbe     loc_18000D489
0x18000d238  lea     rax, aFailedToAlloca_2; "Failed to allocate the clip region"
0x18000d23f  mov     [rbp+57h+var_90], rdi
0x18000d243  mov     [rbp+57h+var_88], rax
0x18000d247  lea     rdx, qword_1800394E0
0x18000d24e  lea     rax, [rbp+57h+var_90]
0x18000d252  mov     dword ptr [rbp+57h+var_A0], 189h
0x18000d259  mov     qword ptr [rsp+100h+rop], rax
0x18000d25e  lea     rax, [rbp+57h+var_A0]
0x18000d262  mov     qword ptr [rsp+100h+y1], rax
0x18000d267  lea     rax, [rbp+57h+var_78]
0x18000d26b  mov     qword ptr [rsp+100h+x1], rax
0x18000d270  lea     rax, [rbp+57h+var_98]
0x18000d274  mov     [rsp+100h+hdcSrc], rax
0x18000d279  lea     rax, [rbp+57h+var_88]
0x18000d27d  mov     [rbp+57h+var_78], r14
0x18000d281  mov     qword ptr [rsp+100h+cy], rax
0x18000d286  mov     dword ptr [rbp+57h+var_98], ecx
0x18000d289  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000d28e  jmp     loc_18000D489
0x18000d293  mov     r9d, 1; iMode
0x18000d299  mov     r8, r15; hrgnSrc2
0x18000d29c  mov     rdx, r12; hrgnSrc1
0x18000d29f  mov     rcx, r15; hrgnDst
0x18000d2a2  call    cs:__imp_CombineRgn
0x18000d2a8  mov     rcx, r12; ho
0x18000d2ab  mov     ebx, eax
0x18000d2ad  call    cs:__imp_DeleteObject
0x18000d2b3  cmp     ebx, 1
0x18000d2b6  ja      short loc_18000D323
0x18000d2b8  mov     eax, cs:dword_180044008
0x18000d2be  cmp     eax, 2
0x18000d2c1  jbe     loc_18000D489
0x18000d2c7  lea     rax, aNullOrErrorReg; "Null or error region resulting from cli"...
0x18000d2ce  mov     [rbp+57h+var_78], rdi
0x18000d2d2  mov     [rbp+57h+var_90], rax
0x18000d2d6  lea     rdx, byte_180039493
0x18000d2dd  lea     rax, aErrorCondition; "Error condition failed"
0x18000d2e4  mov     dword ptr [rbp+57h+var_A0], 194h
0x18000d2eb  mov     [rbp+57h+var_80], rax
0x18000d2ef  lea     rax, [rbp+57h+var_90]
0x18000d2f3  mov     [rsp+100h+var_B8], rax
0x18000d2f8  lea     rax, [rbp+57h+var_78]
0x18000d2fc  mov     qword ptr [rsp+100h+rop], rax
0x18000d301  lea     rax, [rbp+57h+var_A0]
0x18000d305  mov     qword ptr [rsp+100h+y1], rax
0x18000d30a  lea     rax, [rbp+57h+var_88]
0x18000d30e  mov     qword ptr [rsp+100h+x1], rax
0x18000d313  lea     rax, [rbp+57h+var_98]
0x18000d317  mov     dword ptr [rbp+57h+var_98], 8000FFFFh
0x18000d31e  jmp     loc_18000D00C
0x18000d323  mov     rbx, [rbp+57h+var_68]
0x18000d327  mov     r12d, 80004005h
0x18000d32d  mov     rdx, r15; hrgn
0x18000d330  mov     rcx, r13; hdc
0x18000d333  call    cs:__imp_SelectClipRgn
0x18000d339  mov     eax, [rbx+4]
0x18000d33c  mov     ecx, [rbp+57h+rc.bottom]
0x18000d33f  mov     r8d, [rbp+57h+rc.top]; y
0x18000d343  sub     ecx, r8d
0x18000d346  mov     r9d, [rbp+57h+rc.right]
0x18000d34a  inc     ecx
0x18000d34c  mov     edx, [rbp+57h+rc.left]; x
0x18000d34f  sub     r9d, edx
0x18000d352  mov     [rsp+100h+rop], 0CC0020h; rop
0x18000d35a  inc     r9d; cx
0x18000d35d  mov     [rsp+100h+y1], eax; y1
0x18000d361  mov     eax, [rbx]
0x18000d363  mov     [rsp+100h+x1], eax; x1
0x18000d367  mov     rax, [rbp+57h+var_60]
0x18000d36b  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x18000d370  mov     [rsp+100h+cy], ecx; cy
0x18000d374  mov     rcx, r13; hdc
0x18000d377  call    cs:__imp_BitBlt
0x18000d37d  test    eax, eax
0x18000d37f  jnz     short loc_18000D3F9
0x18000d381  call    cs:__imp_GetLastError
0x18000d387  mov     ecx, eax
0x18000d389  test    eax, eax
0x18000d38b  jle     short loc_18000D396
0x18000d38d  movzx   ecx, ax
0x18000d390  or      ecx, 80070000h
0x18000d396  mov     eax, cs:dword_180044008
0x18000d39c  test    ecx, ecx
0x18000d39e  cmovns  ecx, r12d
0x18000d3a2  cmp     eax, 2
0x18000d3a5  jbe     loc_18000D489
0x18000d3ab  lea     rax, aBitbltFailedFo; "BitBlt failed for dirty region copy"
0x18000d3b2  mov     [rbp+57h+var_60], rdi
0x18000d3b6  mov     [rbp+57h+var_90], rax
0x18000d3ba  lea     rdx, word_18003944E
0x18000d3c1  lea     rax, [rbp+57h+var_60]
0x18000d3c5  mov     dword ptr [rbp+57h+var_A0], 1A8h
0x18000d3cc  mov     qword ptr [rsp+100h+rop], rax
0x18000d3d1  lea     rax, [rbp+57h+var_A0]
0x18000d3d5  mov     qword ptr [rsp+100h+y1], rax
0x18000d3da  lea     rax, [rbp+57h+var_68]
0x18000d3de  mov     qword ptr [rsp+100h+x1], rax
0x18000d3e3  lea     rax, [rbp+57h+var_98]
0x18000d3e7  mov     [rsp+100h+hdcSrc], rax
0x18000d3ec  lea     rax, [rbp+57h+var_90]
0x18000d3f0  mov     [rbp+57h+var_68], r14
0x18000d3f4  jmp     loc_18000D281
0x18000d3f9  mov     rdx, r15; HRGN
0x18000d3fc  mov     rcx, rsi; this
0x18000d3ff  call    ?DrawDebugRects@RdpDWMDirectWindowContext@@IEAAXPEAUHRGN__@@@Z; RdpDWMDirectWindowContext::DrawDebugRects(HRGN__ *)
0x18000d404  xor     edx, edx; hrgn
0x18000d406  mov     rcx, r13; hdc
0x18000d409  call    cs:__imp_SelectClipRgn
0x18000d40f  mov     rcx, [rsi+290h]
0x18000d416  lea     r9, [rbp+57h+rc]
0x18000d41a  mov     rdx, [rsi+40h]
  ... truncated ...
```
