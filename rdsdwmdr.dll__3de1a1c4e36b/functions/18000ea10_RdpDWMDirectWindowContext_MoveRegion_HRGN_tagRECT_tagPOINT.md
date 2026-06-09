# RdpDWMDirectWindowContext::MoveRegion(HRGN__ *,tagRECT *,tagPOINT *)

- ea: `0x18000ea10`
- end: `0x18000ef12`
- name: `?MoveRegion@RdpDWMDirectWindowContext@@QEAAJPEAUHRGN__@@PEAUtagRECT@@PEAUtagPOINT@@@Z`
- size: `1282`
- prototype: `__int64 __fastcall(HDC *this, HRGN hrgn, struct tagRECT *, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180010724`

## callees

- `0x180001188`
- `0x180001724`
- `0x180001bfc`
- `0x180002720`
- `0x180002a04`
- `0x180006db4`
- `0x18000cc98`
- `0x18000e0e8`
- `0x18000ea10`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `USER32!OffsetRect` at `0x18000ebea`
- `USER32!OffsetRect` at `0x18000ebea`
- `GDI32!BitBlt` at `0x18000edde`
- `GDI32!BitBlt` at `0x18000edde`
- `GDI32!SelectClipRgn` at `0x18000ed9c`
- `GDI32!SelectClipRgn` at `0x18000ee1b`
- `GDI32!SelectClipRgn` at `0x18000ed9c`
- `GDI32!SelectClipRgn` at `0x18000ee1b`

## string_xrefs

- `0x18000ea93`: `MoveRegion for window`
- `0x18000eb17`: `Skipping update for window 0x%p`
- `0x18000eb67`: `MoveRegion`
- `0x18000ebfc`: `MoveRegion`
- `0x18000ec27`: `The target of the move rect for windowId=0x%x exceeds the surface bounds.`
- `0x18000ecb2`: `The source of the move rect for windowId=0x%x exceeds the surface bounds.`
- `0x18000ed33`: `Received move metadata with non-null clip region for windowId=0x%x.`
- `0x18000ee69`: `Failed to send the driver notification for a surface update`
- `0x18000eead`: `Failed to send the driver notification for an in-surface move.`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::MoveRegion(HDC *this, HRGN hrgn, struct tagRECT *a3, struct tagPOINT *a4)
{
  const char **v4; // rsi
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  LONG y; // r8d
  LONG v13; // edx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  HDC v22; // rcx
  __int64 *v23; // rax
  HDC v24; // r8
  HDC v25; // rdx
  __int64 v26; // r10
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rcx
  int *v31; // rdx
  const char *v32; // rax
  int v33; // eax
  LONG x; // [rsp+60h] [rbp-59h] BYREF
  const char *v36; // [rsp+68h] [rbp-51h] BYREF
  const char *v37; // [rsp+70h] [rbp-49h] BYREF
  const char *v38; // [rsp+78h] [rbp-41h] BYREF
  const unsigned __int16 *v39[2]; // [rsp+80h] [rbp-39h] BYREF
  struct tagRECT v40; // [rsp+90h] [rbp-29h] BYREF
  LONG bottom; // [rsp+A0h] [rbp-19h] BYREF
  LONG v42[3]; // [rsp+A4h] [rbp-15h] BYREF
  struct tagRECT rc; // [rsp+B0h] [rbp-9h] BYREF

  v4 = (const char **)(this + 8);
  rc = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    bottom = a3->bottom;
    v42[0] = a3->right;
    LODWORD(v38) = a3->left;
    LODWORD(v39[0]) = a3->top;
    LODWORD(v37) = a4->y;
    x = a4->x;
    v36 = *v4;
    *(_QWORD *)&v40.left = "MoveRegion for window";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&byte_1800398AF,
      (__int64)a3,
      (__int64)a4,
      (const unsigned __int16 **)&v40,
      (__int64)&v36,
      (__int64)&x,
      (__int64)&v37,
      (__int64)v39,
      (__int64)&v38,
      (__int64)v42,
      (__int64)&bottom);
  }
  v9 = RdpDWMDirectWindowContext::EnsureSurfaceBuffer((__int64)this, (__int64)hrgn, (__int64)a3, (__int64)a4);
  if ( v9 == 1 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      *(_QWORD *)&v40.left = *v4;
      v36 = "Skipping update for window 0x%p";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)v9,
        (__int64)qword_180039880,
        v10,
        v11,
        (const unsigned __int16 **)&v36,
        (__int64)&v40);
    }
  }
  else
  {
    if ( v9 >= 0 )
    {
      y = a4->y;
      v13 = a4->x;
      v14 = 0;
      rc = *a3;
      OffsetRect(&rc, v13, y);
      if ( (unsigned int)RdpDWMDirectWindowContext::ClipUpdateRectToWindow((RdpDWMDirectWindowContext *)this, &rc) )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          *(_QWORD *)&v40.left = *v4;
          v38 = "The target of the move rect for windowId=0x%x exceeds the surface bounds.";
          v36 = "MoveRegion";
          x = 242;
          v39[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
          LODWORD(v37) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v15,
            (__int64)qword_1800397E0,
            v16,
            v17,
            (const unsigned __int16 **)&v38,
            (__int64)&v37,
            v39,
            (__int64)&x,
            (const unsigned __int16 **)&v36,
            (__int64)&v40);
        }
        v14 = 1;
      }
      if ( (unsigned int)RdpDWMDirectWindowContext::ClipUpdateRectToWindow((RdpDWMDirectWindowContext *)this, a3) )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          *(_QWORD *)&v40.left = this[8];
          v38 = "The source of the move rect for windowId=0x%x exceeds the surface bounds.";
          v36 = "MoveRegion";
          x = 253;
          v39[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
          LODWORD(v37) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v18,
            (__int64)byte_18003978D,
            v19,
            v20,
            (const unsigned __int16 **)&v38,
            (__int64)&v37,
            v39,
            (__int64)&x,
            (const unsigned __int16 **)&v36,
            (__int64)&v40);
        }
        v14 = 1;
      }
      if ( hrgn )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          *(_QWORD *)&v40.left = this[8];
          v38 = "Received move metadata with non-null clip region for windowId=0x%x.";
          v36 = "MoveRegion";
          x = 263;
          v39[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
          LODWORD(v37) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v18,
            (__int64)word_18003973A,
            v19,
            v20,
            (const unsigned __int16 **)&v38,
            (__int64)&v37,
            v39,
            (__int64)&x,
            (const unsigned __int16 **)&v36,
            (__int64)&v40);
        }
        v14 = 1;
      }
      SelectClipRgn(this[7], hrgn);
      BitBlt(this[7], rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, this[7], a3->left, a3->top, 0xCC0020u);
      if ( *((_DWORD *)this + 192) )
      {
        v21 = *((unsigned int *)this + 173);
        v22 = this[7];
        v40 = rc;
        DrawRectangleToDC(v22, &v40, (HPEN)this[v21 + 88], 2);
      }
      SelectClipRgn(this[7], 0);
      v23 = (__int64 *)this[82];
      v24 = this[7];
      v25 = this[8];
      v26 = *v23;
      if ( v14 )
      {
        v27 = (*(__int64 (__fastcall **)(__int64 *, HDC, HDC, struct tagRECT *))(v26 + 64))(v23, v25, v24, &rc);
        if ( v27 >= 0 )
          return 0;
        v30 = (unsigned int)dword_180044008;
        if ( (unsigned int)dword_180044008 <= 3 )
          return 0;
        x = v27;
        v31 = (int *)&byte_1800396FF;
        v32 = "Failed to send the driver notification for a surface update";
      }
      else
      {
        v33 = (*(__int64 (__fastcall **)(__int64 *, HDC, HDC, _QWORD, LONG, struct tagRECT *))(v26 + 72))(
                v23,
                v25,
                v24,
                (unsigned int)a3->left,
                a3->top,
                &rc);
        if ( v33 >= 0 )
          return 0;
        v30 = (unsigned int)dword_180044008;
        if ( (unsigned int)dword_180044008 <= 3 )
          return 0;
        x = v33;
        v31 = &dword_1800396C4;
        v32 = "Failed to send the driver notification for an in-surface move.";
      }
      v36 = v32;
      v37 = "HResult failed but continue";
      *(_QWORD *)&v40.left = "MoveRegion";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v30,
        (__int64)v31,
        v28,
        v29,
        (const unsigned __int16 **)&v37,
        (const unsigned __int16 **)&v36,
        (__int64)&x,
        (const unsigned __int16 **)&v40);
      return 0;
    }
    if ( (unsigned int)dword_180044008 > 2 )
    {
      x = 233;
      *(_QWORD *)&v40.left = "EnsureSurfaceBuffer failed";
      v36 = "MoveRegion";
      v38 = "Error HResult failed";
      v39[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      LODWORD(v37) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)v9,
        (__int64)byte_180039833,
        v10,
        v11,
        (const unsigned __int16 **)&v38,
        (__int64)&v37,
        v39,
        (__int64)&x,
        (const unsigned __int16 **)&v36,
        (const unsigned __int16 **)&v40);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ea10  push    rbp
0x18000ea12  push    rbx
0x18000ea13  push    rsi
0x18000ea14  push    rdi
0x18000ea15  push    r12
0x18000ea17  push    r13
0x18000ea19  push    r14
0x18000ea1b  push    r15
0x18000ea1d  lea     rbp, [rsp-1Fh]
0x18000ea22  sub     rsp, 0D8h
0x18000ea29  mov     rax, cs:__security_cookie
0x18000ea30  xor     rax, rsp
0x18000ea33  mov     [rbp+57h+var_50], rax
0x18000ea37  mov     eax, cs:dword_180044008
0x18000ea3d  lea     rsi, [rcx+40h]
0x18000ea41  xorps   xmm0, xmm0
0x18000ea44  mov     r15, r9
0x18000ea47  mov     r12, r8
0x18000ea4a  mov     r13, rdx
0x18000ea4d  mov     rbx, rcx
0x18000ea50  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18000ea54  cmp     eax, 5
0x18000ea57  jbe     loc_18000EAEB
0x18000ea5d  mov     eax, [r8+0Ch]
0x18000ea61  lea     rdx, byte_1800398AF
0x18000ea68  mov     [rbp+57h+var_70], eax
0x18000ea6b  mov     eax, [r8+8]
0x18000ea6f  mov     [rbp+57h+var_6C], eax
0x18000ea72  mov     eax, [r8]
0x18000ea75  mov     dword ptr [rbp+57h+var_98], eax
0x18000ea78  mov     eax, [r8+4]
0x18000ea7c  mov     dword ptr [rbp+57h+var_90], eax
0x18000ea7f  mov     eax, [r9+4]
0x18000ea83  mov     dword ptr [rbp+57h+var_A0], eax
0x18000ea86  mov     eax, [r9]
0x18000ea89  mov     [rbp+57h+var_B0], eax
0x18000ea8c  mov     rax, [rsi]
0x18000ea8f  mov     [rbp+57h+var_A8], rax
0x18000ea93  lea     rax, aMoveregionForW; "MoveRegion for window"
0x18000ea9a  mov     qword ptr [rbp+57h+var_80.left], rax
0x18000ea9e  lea     rax, [rbp+57h+var_70]
0x18000eaa2  mov     [rsp+110h+var_B8], rax
0x18000eaa7  lea     rax, [rbp+57h+var_6C]
0x18000eaab  mov     [rsp+110h+var_C0], rax
0x18000eab0  lea     rax, [rbp+57h+var_98]
0x18000eab4  mov     [rsp+110h+var_C8], rax
0x18000eab9  lea     rax, [rbp+57h+var_90]
0x18000eabd  mov     qword ptr [rsp+110h+rop], rax
0x18000eac2  lea     rax, [rbp+57h+var_A0]
0x18000eac6  mov     qword ptr [rsp+110h+y1], rax
0x18000eacb  lea     rax, [rbp+57h+var_B0]
0x18000eacf  mov     qword ptr [rsp+110h+x1], rax
0x18000ead4  lea     rax, [rbp+57h+var_A8]
0x18000ead8  mov     [rsp+110h+hdcSrc], rax
0x18000eadd  lea     rax, [rbp+57h+var_80]
0x18000eae1  mov     qword ptr [rsp+110h+cy], rax
0x18000eae6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000eaeb  mov     rcx, rbx; this
0x18000eaee  call    ?EnsureSurfaceBuffer@RdpDWMDirectWindowContext@@IEAAJXZ; RdpDWMDirectWindowContext::EnsureSurfaceBuffer(void)
0x18000eaf3  mov     ecx, eax
0x18000eaf5  cmp     eax, 1
0x18000eaf8  jnz     short loc_18000EB3E
0x18000eafa  mov     eax, cs:dword_180044008
0x18000eb00  cmp     eax, 4
0x18000eb03  jbe     loc_18000EEF0
0x18000eb09  mov     rax, [rsi]
0x18000eb0c  lea     rdx, qword_180039880
0x18000eb13  mov     qword ptr [rbp+57h+var_80.left], rax
0x18000eb17  lea     rax, aSkippingUpdate; "Skipping update for window 0x%p"
0x18000eb1e  mov     [rbp+57h+var_A8], rax
0x18000eb22  lea     rax, [rbp+57h+var_80]
0x18000eb26  mov     [rsp+110h+hdcSrc], rax
0x18000eb2b  lea     rax, [rbp+57h+var_A8]
0x18000eb2f  mov     qword ptr [rsp+110h+cy], rax
0x18000eb34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000eb39  jmp     loc_18000EEF0
0x18000eb3e  test    ecx, ecx
0x18000eb40  jns     loc_18000EBD2
0x18000eb46  mov     eax, cs:dword_180044008
0x18000eb4c  cmp     eax, 2
0x18000eb4f  jbe     loc_18000EEF0
0x18000eb55  lea     rax, aEnsuresurfaceb_1; "EnsureSurfaceBuffer failed"
0x18000eb5c  mov     [rbp+57h+var_B0], 0E9h
0x18000eb63  mov     qword ptr [rbp+57h+var_80.left], rax
0x18000eb67  lea     rdi, aMoveregion; "MoveRegion"
0x18000eb6e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000eb75  mov     [rbp+57h+var_A8], rdi
0x18000eb79  mov     [rbp+57h+var_98], rax
0x18000eb7d  lea     r15, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000eb84  lea     rax, [rbp+57h+var_80]
0x18000eb88  mov     [rbp+57h+var_90], r15
0x18000eb8c  mov     [rsp+110h+var_C8], rax
0x18000eb91  lea     rdx, byte_180039833
0x18000eb98  lea     rax, [rbp+57h+var_A8]
0x18000eb9c  mov     dword ptr [rbp+57h+var_A0], ecx
0x18000eb9f  mov     qword ptr [rsp+110h+rop], rax
0x18000eba4  lea     rax, [rbp+57h+var_B0]
0x18000eba8  mov     qword ptr [rsp+110h+y1], rax
0x18000ebad  lea     rax, [rbp+57h+var_90]
0x18000ebb1  mov     qword ptr [rsp+110h+x1], rax
0x18000ebb6  lea     rax, [rbp+57h+var_A0]
0x18000ebba  mov     [rsp+110h+hdcSrc], rax
0x18000ebbf  lea     rax, [rbp+57h+var_98]
0x18000ebc3  mov     qword ptr [rsp+110h+cy], rax
0x18000ebc8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000ebcd  jmp     loc_18000EEF0
0x18000ebd2  movups  xmm0, xmmword ptr [r12]
0x18000ebd7  mov     r8d, [r15+4]; dy
0x18000ebdb  lea     rcx, [rbp+57h+rc]; lprc
0x18000ebdf  mov     edx, [r15]; dx
0x18000ebe2  xor     r14d, r14d
0x18000ebe5  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x18000ebea  call    cs:__imp_OffsetRect
0x18000ebf0  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x18000ebf4  mov     rcx, rbx; this
0x18000ebf7  call    ?ClipUpdateRectToWindow@RdpDWMDirectWindowContext@@IEAAHPEAUtagRECT@@@Z; RdpDWMDirectWindowContext::ClipUpdateRectToWindow(tagRECT *)
0x18000ebfc  lea     rdi, aMoveregion; "MoveRegion"
0x18000ec03  lea     r15, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000ec0a  test    eax, eax
0x18000ec0c  jz      short loc_18000EC89
0x18000ec0e  mov     eax, cs:dword_180044008
0x18000ec14  cmp     eax, 2
0x18000ec17  jbe     short loc_18000EC83
0x18000ec19  mov     rax, [rsi]
0x18000ec1c  lea     rdx, qword_1800397E0
0x18000ec23  mov     qword ptr [rbp+57h+var_80.left], rax
0x18000ec27  lea     rax, aTheTargetOfThe; "The target of the move rect for windowI"...
0x18000ec2e  mov     [rbp+57h+var_98], rax
0x18000ec32  lea     rax, [rbp+57h+var_80]
0x18000ec36  mov     [rsp+110h+var_C8], rax
0x18000ec3b  lea     rax, [rbp+57h+var_A8]
0x18000ec3f  mov     qword ptr [rsp+110h+rop], rax
0x18000ec44  lea     rax, [rbp+57h+var_B0]
0x18000ec48  mov     qword ptr [rsp+110h+y1], rax
0x18000ec4d  lea     rax, [rbp+57h+var_90]
0x18000ec51  mov     qword ptr [rsp+110h+x1], rax
0x18000ec56  lea     rax, [rbp+57h+var_A0]
0x18000ec5a  mov     [rsp+110h+hdcSrc], rax
0x18000ec5f  lea     rax, [rbp+57h+var_98]
0x18000ec63  mov     qword ptr [rsp+110h+cy], rax
0x18000ec68  mov     [rbp+57h+var_A8], rdi
0x18000ec6c  mov     [rbp+57h+var_B0], 0F2h
0x18000ec73  mov     [rbp+57h+var_90], r15
0x18000ec77  mov     dword ptr [rbp+57h+var_A0], 80004005h
0x18000ec7e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000ec83  mov     r14d, 1
0x18000ec89  mov     rdx, r12; struct tagRECT *
0x18000ec8c  mov     rcx, rbx; this
0x18000ec8f  call    ?ClipUpdateRectToWindow@RdpDWMDirectWindowContext@@IEAAHPEAUtagRECT@@@Z; RdpDWMDirectWindowContext::ClipUpdateRectToWindow(tagRECT *)
0x18000ec94  test    eax, eax
0x18000ec96  jz      short loc_18000ED14
0x18000ec98  mov     eax, cs:dword_180044008
0x18000ec9e  cmp     eax, 2
0x18000eca1  jbe     short loc_18000ED0E
0x18000eca3  mov     rax, [rbx+40h]
0x18000eca7  lea     rdx, byte_18003978D
0x18000ecae  mov     qword ptr [rbp+57h+var_80.left], rax
0x18000ecb2  lea     rax, aTheSourceOfThe; "The source of the move rect for windowI"...
0x18000ecb9  mov     [rbp+57h+var_98], rax
0x18000ecbd  lea     rax, [rbp+57h+var_80]
0x18000ecc1  mov     [rsp+110h+var_C8], rax
0x18000ecc6  lea     rax, [rbp+57h+var_A8]
0x18000ecca  mov     qword ptr [rsp+110h+rop], rax
0x18000eccf  lea     rax, [rbp+57h+var_B0]
0x18000ecd3  mov     qword ptr [rsp+110h+y1], rax
0x18000ecd8  lea     rax, [rbp+57h+var_90]
0x18000ecdc  mov     qword ptr [rsp+110h+x1], rax
0x18000ece1  lea     rax, [rbp+57h+var_A0]
0x18000ece5  mov     [rsp+110h+hdcSrc], rax
0x18000ecea  lea     rax, [rbp+57h+var_98]
0x18000ecee  mov     qword ptr [rsp+110h+cy], rax
0x18000ecf3  mov     [rbp+57h+var_A8], rdi
0x18000ecf7  mov     [rbp+57h+var_B0], 0FDh
0x18000ecfe  mov     [rbp+57h+var_90], r15
0x18000ed02  mov     dword ptr [rbp+57h+var_A0], 80004005h
0x18000ed09  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000ed0e  mov     r14d, 1
0x18000ed14  test    r13, r13
0x18000ed17  jz      short loc_18000ED95
0x18000ed19  mov     eax, cs:dword_180044008
0x18000ed1f  cmp     eax, 2
0x18000ed22  jbe     short loc_18000ED8F
0x18000ed24  mov     rax, [rbx+40h]
0x18000ed28  lea     rdx, word_18003973A
0x18000ed2f  mov     qword ptr [rbp+57h+var_80.left], rax
0x18000ed33  lea     rax, aReceivedMoveMe; "Received move metadata with non-null cl"...
0x18000ed3a  mov     [rbp+57h+var_98], rax
0x18000ed3e  lea     rax, [rbp+57h+var_80]
0x18000ed42  mov     [rsp+110h+var_C8], rax
0x18000ed47  lea     rax, [rbp+57h+var_A8]
0x18000ed4b  mov     qword ptr [rsp+110h+rop], rax
0x18000ed50  lea     rax, [rbp+57h+var_B0]
0x18000ed54  mov     qword ptr [rsp+110h+y1], rax
0x18000ed59  lea     rax, [rbp+57h+var_90]
0x18000ed5d  mov     qword ptr [rsp+110h+x1], rax
0x18000ed62  lea     rax, [rbp+57h+var_A0]
0x18000ed66  mov     [rsp+110h+hdcSrc], rax
0x18000ed6b  lea     rax, [rbp+57h+var_98]
0x18000ed6f  mov     qword ptr [rsp+110h+cy], rax
0x18000ed74  mov     [rbp+57h+var_A8], rdi
0x18000ed78  mov     [rbp+57h+var_B0], 107h
0x18000ed7f  mov     [rbp+57h+var_90], r15
0x18000ed83  mov     dword ptr [rbp+57h+var_A0], 80004005h
0x18000ed8a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000ed8f  mov     r14d, 1
0x18000ed95  mov     rcx, [rbx+38h]; hdc
0x18000ed99  mov     rdx, r13; hrgn
0x18000ed9c  call    cs:__imp_SelectClipRgn
0x18000eda2  mov     eax, [r12+4]
0x18000eda7  mov     r10d, [rbp+57h+rc.bottom]
0x18000edab  mov     rcx, [rbx+38h]; hdc
0x18000edaf  mov     r8d, [rbp+57h+rc.top]; y
0x18000edb3  sub     r10d, r8d
0x18000edb6  mov     r9d, [rbp+57h+rc.right]
0x18000edba  mov     edx, [rbp+57h+rc.left]; x
0x18000edbd  sub     r9d, edx; cx
0x18000edc0  mov     [rsp+110h+rop], 0CC0020h; rop
0x18000edc8  mov     [rsp+110h+y1], eax; y1
0x18000edcc  mov     eax, [r12]
0x18000edd0  mov     [rsp+110h+x1], eax; x1
0x18000edd4  mov     [rsp+110h+hdcSrc], rcx; hdcSrc
0x18000edd9  mov     [rsp+110h+cy], r10d; cy
0x18000edde  call    cs:__imp_BitBlt
0x18000ede4  cmp     dword ptr [rbx+300h], 0
0x18000edeb  jz      short loc_18000EE15
0x18000eded  mov     r8d, [rbx+2B4h]
0x18000edf4  lea     rdx, [rbp+57h+var_80]; struct tagRECT
0x18000edf8  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x18000edfc  mov     r9b, 2; unsigned __int8
0x18000edff  mov     rcx, [rbx+38h]; hdc
0x18000ee03  movdqa  xmmword ptr [rbp+57h+var_80.left], xmm0
0x18000ee08  mov     r8, [rbx+r8*8+2C0h]; HPEN
0x18000ee10  call    ?DrawRectangleToDC@@YAXPEAUHDC__@@UtagRECT@@PEAUHPEN__@@E@Z; DrawRectangleToDC(HDC__ *,tagRECT,HPEN__ *,uchar)
0x18000ee15  mov     rcx, [rbx+38h]; hdc
0x18000ee19  xor     edx, edx; hrgn
0x18000ee1b  call    cs:__imp_SelectClipRgn
0x18000ee21  mov     rax, [rbx+290h]
0x18000ee28  mov     r8, [rbx+38h]
0x18000ee2c  mov     rdx, [rbx+40h]
0x18000ee30  mov     r10, [rax]
0x18000ee33  test    r14d, r14d
0x18000ee36  jz      short loc_18000EE72
0x18000ee38  mov     rcx, rax
0x18000ee3b  lea     r9, [rbp+57h+rc]
0x18000ee3f  mov     rax, [r10+40h]
0x18000ee43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee48  test    eax, eax
0x18000ee4a  jns     loc_18000EEF0
0x18000ee50  mov     ecx, cs:dword_180044008
0x18000ee56  cmp     ecx, 3
0x18000ee59  jbe     loc_18000EEF0
0x18000ee5f  mov     [rbp+57h+var_B0], eax
0x18000ee62  lea     rdx, byte_1800396FF
0x18000ee69  lea     rax, aFailedToSendTh_2; "Failed to send the driver notification "...
0x18000ee70  jmp     short loc_18000EEB4
0x18000ee72  mov     r9d, [r12]
0x18000ee76  lea     rcx, [rbp+57h+rc]
0x18000ee7a  mov     [rsp+110h+hdcSrc], rcx
0x18000ee7f  mov     ecx, [r12+4]
0x18000ee84  mov     [rsp+110h+cy], ecx
0x18000ee88  mov     rcx, rax
0x18000ee8b  mov     rax, [r10+48h]
0x18000ee8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee94  test    eax, eax
0x18000ee96  jns     short loc_18000EEF0
0x18000ee98  mov     ecx, cs:dword_180044008
0x18000ee9e  cmp     ecx, 3
0x18000eea1  jbe     short loc_18000EEF0
0x18000eea3  mov     [rbp+57h+var_B0], eax
0x18000eea6  lea     rdx, dword_1800396C4
0x18000eead  lea     rax, aFailedToSendTh_1; "Failed to send the driver notification "...
0x18000eeb4  mov     [rbp+57h+var_A8], rax
0x18000eeb8  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000eebf  mov     [rbp+57h+var_A0], rax
0x18000eec3  lea     rax, [rbp+57h+var_80]
0x18000eec7  mov     qword ptr [rsp+110h+y1], rax
0x18000eecc  lea     rax, [rbp+57h+var_B0]
0x18000eed0  mov     qword ptr [rsp+110h+x1], rax
0x18000eed5  lea     rax, [rbp+57h+var_A8]
0x18000eed9  mov     [rsp+110h+hdcSrc], rax
0x18000eede  lea     rax, [rbp+57h+var_A0]
0x18000eee2  mov     qword ptr [rsp+110h+cy], rax
0x18000eee7  mov     qword ptr [rbp+57h+var_80.left], rdi
0x18000eeeb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000eef0  xor     eax, eax
0x18000eef2  mov     rcx, [rbp+57h+var_50]
0x18000eef6  xor     rcx, rsp; StackCookie
0x18000eef9  call    __security_check_cookie
0x18000eefe  add     rsp, 0D8h
0x18000ef05  pop     r15
0x18000ef07  pop     r14
0x18000ef09  pop     r13
0x18000ef0b  pop     r12
0x18000ef0d  pop     rdi
0x18000ef0e  pop     rsi
0x18000ef0f  pop     rbx
0x18000ef10  pop     rbp
0x18000ef11  retn
```
