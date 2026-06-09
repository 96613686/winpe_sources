# RdpDWMDirectWindowContext::EnsureSurfaceBuffer(void)

- ea: `0x18000e0e8`
- end: `0x18000e730`
- name: `?EnsureSurfaceBuffer@RdpDWMDirectWindowContext@@IEAAJXZ`
- size: `1608`
- prototype: `__int64 __fastcall(__int64 this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000cf04`
- `0x18000ea10`

## callees

- `0x180001188`
- `0x18000160c`
- `0x180001724`
- `0x180001bfc`
- `0x180002844`
- `0x180002914`
- `0x18000d788`
- `0x18000dd74`
- `0x18000e0e8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5df`
- `USER32!IsWindowVisible` at `0x18000e1e7`
- `USER32!IsWindowVisible` at `0x18000e1e7`
- `GDI32!GetObjectW` at `0x18000e5d5`
- `GDI32!GetObjectW` at `0x18000e5d5`
- `GDI32!GetCurrentObject` at `0x18000e523`
- `GDI32!GetCurrentObject` at `0x18000e523`
- `dwmapi!DwmGetWindowAttribute` at `0x18000e207`
- `dwmapi!DwmGetWindowAttribute` at `0x18000e207`

## string_xrefs

- `0x18000e410`: `Failed to destroy the previously created surface`
- `0x18000e496`: `Failed to create a memory mapped DIB section`
- `0x18000e698`: `Failed to send the surface create notification to the driver`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::EnsureSurfaceBuffer(__int64 this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  int MemoryMappedDibSection; // ebx
  HWND *v6; // rbx
  unsigned int v7; // r14d
  unsigned int v8; // esi
  int v9; // r15d
  HWND v10; // rcx
  unsigned int v11; // eax
  char *v12; // rdx
  const char **v13; // rax
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  const char *v21; // rax
  __int64 *v22; // rdx
  HGDIOBJ CurrentObject; // rax
  signed int LastError; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int16 *v28; // rdx
  const char *v29; // rax
  signed int v30; // eax
  const char *v32; // [rsp+60h] [rbp-19h] BYREF
  const char *v33; // [rsp+68h] [rbp-11h] BYREF
  const char *v34; // [rsp+70h] [rbp-9h] BYREF
  _OWORD pv[5]; // [rsp+78h] [rbp-1h] BYREF
  HWND pvAttribute; // [rsp+E0h] [rbp+67h] BYREF
  const char *v37; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v38; // [rsp+F0h] [rbp+77h] BYREF
  const char *v39; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = this;
  MemoryMappedDibSection = 0;
  memset(pv, 0, 32);
  if ( !*(_DWORD *)(this + 672) )
    goto LABEL_69;
  v6 = (HWND *)(this + 64);
  v7 = *(_DWORD *)(this + 676);
  v8 = *(_DWORD *)(this + 680);
  v9 = *(_DWORD *)(this + 684);
  if ( (unsigned int)dword_180044008 > 4 )
  {
    pvAttribute = *v6;
    v37 = "Handling resize of surface buffer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      this,
      (__int64)byte_18003916B,
      a3,
      a4,
      (const unsigned __int16 **)&v37,
      (__int64)&pvAttribute);
  }
  if ( v7 == *(_DWORD *)(v4 + 88) && v8 == *(_DWORD *)(v4 + 92) && *(_DWORD *)(v4 + 124) == v9 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      pvAttribute = *v6;
      v37 = "Ignoring window resize - the size or alpha didn't change";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        this,
        (__int64)&dword_18003913C,
        a3,
        a4,
        (const unsigned __int16 **)&v37,
        (__int64)&pvAttribute);
    }
    MemoryMappedDibSection = 0;
    goto LABEL_69;
  }
  if ( *(_DWORD *)(v4 + 688) )
  {
    if ( !*(_DWORD *)(v4 + 88) && !*(_DWORD *)(v4 + 92) )
    {
      if ( !IsWindowVisible(*v6)
        || (v10 = *(HWND *)(v4 + 64), LODWORD(pvAttribute) = 0, DwmGetWindowAttribute(v10, 0xEu, &pvAttribute, 4u) >= 0)
        && (_DWORD)pvAttribute )
      {
        MemoryMappedDibSection = 1;
        if ( (unsigned int)dword_180044008 > 3 )
        {
          pvAttribute = *(HWND *)(v4 + 64);
          v37 = "EnsureSurfaceBuffer bailing out for non visible window 0x%p";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            this,
            (__int64)byte_18003910D,
            a3,
            a4,
            (const unsigned __int16 **)&v37,
            (__int64)&pvAttribute);
        }
        return (unsigned int)MemoryMappedDibSection;
      }
    }
  }
  if ( v7 <= 0x40
    || v8 <= 0x40
    || (v11 = *(_DWORD *)(v4 + 76), v8 >= v11)
    || (this = *(unsigned int *)(v4 + 72), v7 >= (unsigned int)this)
    || (this = (unsigned int)this - v7, (unsigned int)this <= 0x40) && v11 - v8 <= 0x40 )
  {
    if ( v7 <= *(_DWORD *)(v4 + 72) && v8 <= *(_DWORD *)(v4 + 76) && *(_DWORD *)(v4 + 124) == v9 )
    {
      if ( (unsigned int)dword_180044008 > 4 )
      {
        LODWORD(v37) = *(_DWORD *)(v4 + 76);
        LODWORD(v38) = *(_DWORD *)(v4 + 72);
        v33 = *(const char **)(v4 + 64);
        v34 = "Not resizing rendering context size for window, re-mapping";
        LODWORD(pvAttribute) = v9;
        LODWORD(v39) = v8;
        LODWORD(v32) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          this,
          (__int64)&unk_180039048,
          a3,
          a4,
          (const unsigned __int16 **)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&pvAttribute);
      }
LABEL_64:
      MemoryMappedDibSection = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(**(_QWORD **)(v4 + 656) + 56LL))(
                                 *(_QWORD *)(v4 + 656),
                                 *(_QWORD *)(v4 + 64),
                                 *(_QWORD *)(v4 + 56),
                                 v7,
                                 v8);
      if ( MemoryMappedDibSection < 0 )
      {
        if ( (unsigned int)dword_180044008 <= 2 )
          return (unsigned int)MemoryMappedDibSection;
        v21 = "Failed to send surface-to-window mappin notification to the driver";
        LODWORD(pvAttribute) = 822;
        v22 = (__int64 *)&dword_180038E4C;
        goto LABEL_43;
      }
      *(_DWORD *)(v4 + 88) = v7;
      *(_DWORD *)(v4 + 92) = v8;
      *(_DWORD *)(v4 + 124) = v9;
      goto LABEL_68;
    }
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v12 = (char *)&unk_180038FF8;
      v39 = *(const char **)(v4 + 64);
      v34 = "Increasing rendering context size for windowId=0x%p size:(%d,%d) alpha=%d.";
      v13 = &v34;
      goto LABEL_33;
    }
  }
  else if ( (unsigned int)dword_180044008 > 4 )
  {
    v12 = byte_1800390BD;
    v39 = *(const char **)(v4 + 64);
    v32 = "Shrinking rendering context size.";
    v13 = &v32;
LABEL_33:
    LODWORD(pvAttribute) = v9;
    LODWORD(v37) = v8;
    LODWORD(v38) = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      this,
      (__int64)v12,
      a3,
      a4,
      (const unsigned __int16 **)v13,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&pvAttribute);
  }
  v14 = RdpDWMDirectWindowContext::DestroySurface((RdpDWMDirectWindowContext *)v4);
  if ( v14 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    LODWORD(pvAttribute) = v14;
    v37 = "EnsureSurfaceBuffer";
    v38 = "Failed to destroy the previously created surface";
    v39 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)byte_180038FBD,
      v15,
      v16,
      (const unsigned __int16 **)&v39,
      (const unsigned __int16 **)&v38,
      (__int64)&pvAttribute,
      (const unsigned __int16 **)&v37);
  }
  if ( v7 != *(_DWORD *)(v4 + 88) || v8 != *(_DWORD *)(v4 + 92) || (v17 = v4 + 128, !*(_WORD *)(v4 + 128)) )
  {
    MemoryMappedDibSection = RdpDWMDirectWindowContext::CreateMemoryMappedDibSection(
                               (RdpDWMDirectWindowContext *)v4,
                               v7,
                               v8);
    if ( MemoryMappedDibSection < 0 )
    {
      v20 = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 <= 2 )
        return (unsigned int)MemoryMappedDibSection;
      v21 = "Failed to create a memory mapped DIB section";
      LODWORD(pvAttribute) = 785;
      v22 = qword_180038F70;
LABEL_43:
      v38 = v21;
      v39 = "EnsureSurfaceBuffer";
      v34 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      v33 = "Error HResult failed";
      LODWORD(v37) = MemoryMappedDibSection;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v20,
        (__int64)v22,
        v18,
        v19,
        (const unsigned __int16 **)&v33,
        (__int64)&v37,
        (const unsigned __int16 **)&v34,
        (__int64)&pvAttribute,
        (const unsigned __int16 **)&v39,
        (const unsigned __int16 **)&v38);
      return (unsigned int)MemoryMappedDibSection;
    }
    v17 = v4 + 128;
  }
  CurrentObject = GetCurrentObject(*(HDC *)(v4 + 56), 7u);
  if ( !CurrentObject )
  {
    LastError = GetLastError();
    MemoryMappedDibSection = LastError;
    if ( LastError > 0 )
      MemoryMappedDibSection = (unsigned __int16)LastError | 0x80070000;
    if ( MemoryMappedDibSection >= 0 )
      MemoryMappedDibSection = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(pvAttribute) = 792;
      v38 = "EnsureSurfaceBuffer";
      v28 = (__int16 *)byte_180038F2B;
      v39 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      v29 = "Failed to get the current bitmap object set on DC";
LABEL_52:
      v34 = v29;
      LODWORD(v37) = MemoryMappedDibSection;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v25,
        (__int64)v28,
        v26,
        v27,
        (const unsigned __int16 **)&v34,
        (__int64)&v37,
        (const unsigned __int16 **)&v39,
        (__int64)&pvAttribute,
        (const unsigned __int16 **)&v38);
LABEL_68:
      if ( MemoryMappedDibSection )
        return (unsigned int)MemoryMappedDibSection;
LABEL_69:
      *(_DWORD *)(v4 + 672) = 0;
      return (unsigned int)MemoryMappedDibSection;
    }
    return (unsigned int)MemoryMappedDibSection;
  }
  if ( GetObjectW(CurrentObject, 32, pv) )
  {
    MemoryMappedDibSection = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, int, _DWORD, _DWORD, int))(**(_QWORD **)(v4 + 656) + 40LL))(
                               *(_QWORD *)(v4 + 656),
                               *(_QWORD *)(v4 + 64),
                               v17,
                               *(_QWORD *)(v4 + 56),
                               HIDWORD(pv[0]),
                               DWORD2(pv[0]) * HIDWORD(pv[0]),
                               DWORD1(pv[0]),
                               DWORD2(pv[0]),
                               v9);
    if ( MemoryMappedDibSection < 0 )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        return (unsigned int)MemoryMappedDibSection;
      v21 = "Failed to send the surface create notification to the driver";
      LODWORD(pvAttribute) = 810;
      v22 = (__int64 *)byte_180038E99;
      goto LABEL_43;
    }
    *(_DWORD *)(v4 + 104) = 1;
    goto LABEL_64;
  }
  v30 = GetLastError();
  MemoryMappedDibSection = v30;
  if ( v30 > 0 )
    MemoryMappedDibSection = (unsigned __int16)v30 | 0x80070000;
  if ( MemoryMappedDibSection >= 0 )
    MemoryMappedDibSection = -2147467259;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(pvAttribute) = 795;
    v38 = "EnsureSurfaceBuffer";
    v28 = &word_180038EE6;
    v39 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    v29 = "Failed to get the current bitmap info";
    goto LABEL_52;
  }
  return (unsigned int)MemoryMappedDibSection;
}

```

## disassembly

```asm
0x18000e0e8  push    rbp
0x18000e0ea  push    rbx
0x18000e0eb  push    rsi
0x18000e0ec  push    rdi
0x18000e0ed  push    r12
0x18000e0ef  push    r14
0x18000e0f1  push    r15
0x18000e0f3  lea     rbp, [rsp-27h]
0x18000e0f8  sub     rsp, 0A0h
0x18000e0ff  xor     r12d, r12d
0x18000e102  xorps   xmm0, xmm0
0x18000e105  mov     rdi, rcx
0x18000e108  mov     ebx, r12d
0x18000e10b  movups  [rbp+57h+pv], xmm0
0x18000e10f  movups  [rbp+57h+var_48], xmm0
0x18000e113  cmp     [rcx+2A0h], r12d
0x18000e11a  jz      loc_18000E715
0x18000e120  mov     eax, cs:dword_180044008
0x18000e126  lea     rbx, [rcx+40h]
0x18000e12a  mov     r14d, [rcx+2A4h]
0x18000e131  mov     esi, [rcx+2A8h]
0x18000e137  mov     r15d, [rcx+2ACh]
0x18000e13e  cmp     eax, 4
0x18000e141  jbe     short loc_18000E173
0x18000e143  mov     rax, [rbx]
0x18000e146  lea     rdx, byte_18003916B
0x18000e14d  mov     [rbp+57h+pvAttribute], rax
0x18000e151  lea     rax, aHandlingResize; "Handling resize of surface buffer"
0x18000e158  mov     [rbp+57h+arg_8], rax
0x18000e15c  lea     rax, [rbp+57h+pvAttribute]
0x18000e160  mov     [rsp+0D0h+var_A8], rax
0x18000e165  lea     rax, [rbp+57h+arg_8]
0x18000e169  mov     [rsp+0D0h+var_B0], rax
0x18000e16e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e173  cmp     r14d, [rdi+58h]
0x18000e177  jnz     short loc_18000E1C7
0x18000e179  cmp     esi, [rdi+5Ch]
0x18000e17c  jnz     short loc_18000E1C7
0x18000e17e  cmp     [rdi+7Ch], r15d
0x18000e182  jnz     short loc_18000E1C7
0x18000e184  mov     eax, cs:dword_180044008
0x18000e18a  cmp     eax, 5
0x18000e18d  jbe     short loc_18000E1BF
0x18000e18f  mov     rax, [rbx]
0x18000e192  lea     rdx, dword_18003913C
0x18000e199  mov     [rbp+57h+pvAttribute], rax
0x18000e19d  lea     rax, aIgnoringWindow; "Ignoring window resize - the size or al"...
0x18000e1a4  mov     [rbp+57h+arg_8], rax
0x18000e1a8  lea     rax, [rbp+57h+pvAttribute]
0x18000e1ac  mov     [rsp+0D0h+var_A8], rax
0x18000e1b1  lea     rax, [rbp+57h+arg_8]
0x18000e1b5  mov     [rsp+0D0h+var_B0], rax
0x18000e1ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e1bf  mov     ebx, r12d
0x18000e1c2  jmp     loc_18000E715
0x18000e1c7  cmp     [rdi+2B0h], r12d
0x18000e1ce  jz      loc_18000E261
0x18000e1d4  cmp     [rdi+58h], r12d
0x18000e1d8  jnz     loc_18000E261
0x18000e1de  cmp     [rdi+5Ch], r12d
0x18000e1e2  jnz     short loc_18000E261
0x18000e1e4  mov     rcx, [rbx]; hWnd
0x18000e1e7  call    cs:__imp_IsWindowVisible
0x18000e1ed  test    eax, eax
0x18000e1ef  jz      short loc_18000E217
0x18000e1f1  mov     rcx, [rdi+40h]; hwnd
0x18000e1f5  lea     r8, [rbp+57h+pvAttribute]; pvAttribute
0x18000e1f9  mov     r9d, 4; cbAttribute
0x18000e1ff  mov     dword ptr [rbp+57h+pvAttribute], r12d
0x18000e203  lea     edx, [r9+0Ah]; dwAttribute
0x18000e207  call    cs:__imp_DwmGetWindowAttribute
0x18000e20d  test    eax, eax
0x18000e20f  js      short loc_18000E261
0x18000e211  cmp     dword ptr [rbp+57h+pvAttribute], r12d
0x18000e215  jz      short loc_18000E261
0x18000e217  mov     eax, cs:dword_180044008
0x18000e21d  mov     ebx, 1
0x18000e222  cmp     eax, 3
0x18000e225  jbe     loc_18000E71C
0x18000e22b  mov     rax, [rdi+40h]
0x18000e22f  lea     rdx, byte_18003910D
0x18000e236  mov     [rbp+57h+pvAttribute], rax
0x18000e23a  lea     rax, aEnsuresurfaceb; "EnsureSurfaceBuffer bailing out for non"...
0x18000e241  mov     [rbp+57h+arg_8], rax
0x18000e245  lea     rax, [rbp+57h+pvAttribute]
0x18000e249  mov     [rsp+0D0h+var_A8], rax
0x18000e24e  lea     rax, [rbp+57h+arg_8]
0x18000e252  mov     [rsp+0D0h+var_B0], rax
0x18000e257  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e25c  jmp     loc_18000E71C
0x18000e261  lea     rbx, aEnsuresurfaceb_0; "EnsureSurfaceBuffer"
0x18000e268  cmp     r14d, 40h ; '@'
0x18000e26c  jbe     short loc_18000E2E7
0x18000e26e  cmp     esi, 40h ; '@'
0x18000e271  jbe     short loc_18000E2E7
0x18000e273  mov     eax, [rdi+4Ch]
0x18000e276  cmp     esi, eax
0x18000e278  jnb     short loc_18000E2E7
0x18000e27a  mov     ecx, [rdi+48h]
0x18000e27d  cmp     r14d, ecx
0x18000e280  jnb     short loc_18000E2E7
0x18000e282  sub     ecx, r14d
0x18000e285  cmp     ecx, 40h ; '@'
0x18000e288  ja      short loc_18000E291
0x18000e28a  sub     eax, esi
0x18000e28c  cmp     eax, 40h ; '@'
0x18000e28f  jbe     short loc_18000E2E7
0x18000e291  mov     eax, cs:dword_180044008
0x18000e297  cmp     eax, 4
0x18000e29a  jbe     loc_18000E3EF
0x18000e2a0  mov     rax, [rdi+40h]
0x18000e2a4  lea     rdx, byte_1800390BD
0x18000e2ab  mov     [rbp+57h+arg_18], rax
0x18000e2af  lea     rax, aShrinkingRende; "Shrinking rendering context size."
0x18000e2b6  mov     [rbp+57h+var_70], rax
0x18000e2ba  lea     rax, [rbp+57h+pvAttribute]
0x18000e2be  mov     [rsp+0D0h+var_90], rax
0x18000e2c3  lea     rax, [rbp+57h+arg_8]
0x18000e2c7  mov     [rsp+0D0h+var_98], rax
0x18000e2cc  lea     rax, [rbp+57h+arg_10]
0x18000e2d0  mov     [rsp+0D0h+var_A0], rax
0x18000e2d5  lea     rax, [rbp+57h+arg_18]
0x18000e2d9  mov     [rsp+0D0h+var_A8], rax
0x18000e2de  lea     rax, [rbp+57h+var_70]
0x18000e2e2  jmp     loc_18000E3DA
0x18000e2e7  cmp     r14d, [rdi+48h]
0x18000e2eb  ja      loc_18000E38D
0x18000e2f1  cmp     esi, [rdi+4Ch]
0x18000e2f4  ja      loc_18000E38D
0x18000e2fa  cmp     [rdi+7Ch], r15d
0x18000e2fe  jnz     loc_18000E38D
0x18000e304  mov     eax, cs:dword_180044008
0x18000e30a  cmp     eax, 4
0x18000e30d  jbe     loc_18000E6B9
0x18000e313  mov     eax, [rdi+4Ch]
0x18000e316  lea     rdx, unk_180039048
0x18000e31d  mov     dword ptr [rbp+57h+arg_8], eax
0x18000e320  mov     eax, [rdi+48h]
0x18000e323  mov     dword ptr [rbp+57h+arg_10], eax
0x18000e326  mov     rax, [rdi+40h]
0x18000e32a  mov     [rbp+57h+var_68], rax
0x18000e32e  lea     rax, aNotResizingRen; "Not resizing rendering context size for"...
0x18000e335  mov     [rbp+57h+var_60], rax
0x18000e339  lea     rax, [rbp+57h+pvAttribute]
0x18000e33d  mov     [rsp+0D0h+var_80], rax
0x18000e342  lea     rax, [rbp+57h+arg_8]
0x18000e346  mov     [rsp+0D0h+var_88], rax
0x18000e34b  lea     rax, [rbp+57h+arg_10]
0x18000e34f  mov     [rsp+0D0h+var_90], rax
0x18000e354  lea     rax, [rbp+57h+arg_18]
0x18000e358  mov     [rsp+0D0h+var_98], rax
0x18000e35d  lea     rax, [rbp+57h+var_70]
0x18000e361  mov     [rsp+0D0h+var_A0], rax
0x18000e366  lea     rax, [rbp+57h+var_68]
0x18000e36a  mov     [rsp+0D0h+var_A8], rax
0x18000e36f  lea     rax, [rbp+57h+var_60]
0x18000e373  mov     [rsp+0D0h+var_B0], rax
0x18000e378  mov     dword ptr [rbp+57h+pvAttribute], r15d
0x18000e37c  mov     dword ptr [rbp+57h+arg_18], esi
0x18000e37f  mov     dword ptr [rbp+57h+var_70], r14d
0x18000e383  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e388  jmp     loc_18000E6B9
0x18000e38d  mov     eax, cs:dword_180044008
0x18000e393  cmp     eax, 4
0x18000e396  jbe     short loc_18000E3EF
0x18000e398  mov     rax, [rdi+40h]
0x18000e39c  lea     rdx, unk_180038FF8
0x18000e3a3  mov     [rbp+57h+arg_18], rax
0x18000e3a7  lea     rax, aIncreasingRend; "Increasing rendering context size for w"...
0x18000e3ae  mov     [rbp+57h+var_60], rax
0x18000e3b2  lea     rax, [rbp+57h+pvAttribute]
0x18000e3b6  mov     [rsp+0D0h+var_90], rax
0x18000e3bb  lea     rax, [rbp+57h+arg_8]
0x18000e3bf  mov     [rsp+0D0h+var_98], rax
0x18000e3c4  lea     rax, [rbp+57h+arg_10]
0x18000e3c8  mov     [rsp+0D0h+var_A0], rax
0x18000e3cd  lea     rax, [rbp+57h+arg_18]
0x18000e3d1  mov     [rsp+0D0h+var_A8], rax
0x18000e3d6  lea     rax, [rbp+57h+var_60]
0x18000e3da  mov     [rsp+0D0h+var_B0], rax
0x18000e3df  mov     dword ptr [rbp+57h+pvAttribute], r15d
0x18000e3e3  mov     dword ptr [rbp+57h+arg_8], esi
0x18000e3e6  mov     dword ptr [rbp+57h+arg_10], r14d
0x18000e3ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e3ef  mov     rcx, rdi; this
0x18000e3f2  call    ?DestroySurface@RdpDWMDirectWindowContext@@QEAAJXZ; RdpDWMDirectWindowContext::DestroySurface(void)
0x18000e3f7  test    eax, eax
0x18000e3f9  jns     short loc_18000E453
0x18000e3fb  mov     ecx, cs:dword_180044008
0x18000e401  cmp     ecx, 3
0x18000e404  jbe     short loc_18000E453
0x18000e406  mov     dword ptr [rbp+57h+pvAttribute], eax
0x18000e409  lea     rdx, byte_180038FBD
0x18000e410  lea     rax, aFailedToDestro; "Failed to destroy the previously create"...
0x18000e417  mov     [rbp+57h+arg_8], rbx
0x18000e41b  mov     [rbp+57h+arg_10], rax
0x18000e41f  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000e426  mov     [rbp+57h+arg_18], rax
0x18000e42a  lea     rax, [rbp+57h+arg_8]
0x18000e42e  mov     [rsp+0D0h+var_98], rax
0x18000e433  lea     rax, [rbp+57h+pvAttribute]
0x18000e437  mov     [rsp+0D0h+var_A0], rax
0x18000e43c  lea     rax, [rbp+57h+arg_10]
0x18000e440  mov     [rsp+0D0h+var_A8], rax
0x18000e445  lea     rax, [rbp+57h+arg_18]
0x18000e449  mov     [rsp+0D0h+var_B0], rax
0x18000e44e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e453  cmp     r14d, [rdi+58h]
0x18000e457  jnz     short loc_18000E46F
0x18000e459  cmp     esi, [rdi+5Ch]
0x18000e45c  jnz     short loc_18000E46F
0x18000e45e  lea     rbx, [rdi+80h]
0x18000e465  cmp     [rbx], r12w
0x18000e469  jnz     loc_18000E51A
0x18000e46f  mov     r8d, esi; unsigned int
0x18000e472  mov     edx, r14d; unsigned int
0x18000e475  mov     rcx, rdi; this
0x18000e478  call    ?CreateMemoryMappedDibSection@RdpDWMDirectWindowContext@@IEAAJII@Z; RdpDWMDirectWindowContext::CreateMemoryMappedDibSection(uint,uint)
0x18000e47d  mov     ebx, eax
0x18000e47f  test    eax, eax
0x18000e481  jns     loc_18000E513
0x18000e487  mov     ecx, cs:dword_180044008
0x18000e48d  cmp     ecx, 2
0x18000e490  jbe     loc_18000E71C
0x18000e496  lea     rax, aFailedToCreate_17; "Failed to create a memory mapped DIB se"...
0x18000e49d  mov     dword ptr [rbp+57h+pvAttribute], 311h
0x18000e4a4  lea     rdx, qword_180038F70
0x18000e4ab  mov     [rbp+57h+arg_10], rax
0x18000e4af  lea     rax, aEnsuresurfaceb_0; "EnsureSurfaceBuffer"
0x18000e4b6  mov     [rbp+57h+arg_18], rax
0x18000e4ba  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000e4c1  mov     [rbp+57h+var_60], rax
0x18000e4c5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000e4cc  mov     [rbp+57h+var_68], rax
0x18000e4d0  lea     rax, [rbp+57h+arg_10]
0x18000e4d4  mov     [rsp+0D0h+var_88], rax
0x18000e4d9  lea     rax, [rbp+57h+arg_18]
0x18000e4dd  mov     [rsp+0D0h+var_90], rax
0x18000e4e2  lea     rax, [rbp+57h+pvAttribute]
0x18000e4e6  mov     [rsp+0D0h+var_98], rax
0x18000e4eb  lea     rax, [rbp+57h+var_60]
0x18000e4ef  mov     [rsp+0D0h+var_A0], rax
0x18000e4f4  lea     rax, [rbp+57h+arg_8]
0x18000e4f8  mov     [rsp+0D0h+var_A8], rax
0x18000e4fd  lea     rax, [rbp+57h+var_68]
0x18000e501  mov     [rsp+0D0h+var_B0], rax
0x18000e506  mov     dword ptr [rbp+57h+arg_8], ebx
0x18000e509  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000e50e  jmp     loc_18000E71C
0x18000e513  lea     rbx, [rdi+80h]
0x18000e51a  mov     rcx, [rdi+38h]; hdc
0x18000e51e  mov     edx, 7; type
0x18000e523  call    cs:__imp_GetCurrentObject
0x18000e529  test    rax, rax
0x18000e52c  jnz     loc_18000E5C9
0x18000e532  call    cs:__imp_GetLastError
0x18000e538  mov     ebx, eax
0x18000e53a  test    eax, eax
0x18000e53c  jle     short loc_18000E547
0x18000e53e  movzx   ebx, ax
0x18000e541  or      ebx, 80070000h
0x18000e547  test    ebx, ebx
0x18000e549  mov     eax, 80004005h
0x18000e54e  cmovns  ebx, eax
0x18000e551  mov     eax, cs:dword_180044008
0x18000e557  cmp     eax, 2
0x18000e55a  jbe     loc_18000E71C
0x18000e560  lea     rax, aEnsuresurfaceb_0; "EnsureSurfaceBuffer"
0x18000e567  mov     dword ptr [rbp+57h+pvAttribute], 318h
0x18000e56e  mov     [rbp+57h+arg_10], rax
0x18000e572  lea     rdx, byte_180038F2B
0x18000e579  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000e580  mov     [rbp+57h+arg_18], rax
0x18000e584  lea     rax, aFailedToGetThe_1; "Failed to get the current bitmap object"...
0x18000e58b  mov     [rbp+57h+var_60], rax
0x18000e58f  lea     rax, [rbp+57h+arg_10]
0x18000e593  mov     [rsp+0D0h+var_90], rax
0x18000e598  lea     rax, [rbp+57h+pvAttribute]
0x18000e59c  mov     [rsp+0D0h+var_98], rax
0x18000e5a1  lea     rax, [rbp+57h+arg_18]
0x18000e5a5  mov     [rsp+0D0h+var_A0], rax
0x18000e5aa  lea     rax, [rbp+57h+arg_8]
0x18000e5ae  mov     [rsp+0D0h+var_A8], rax
0x18000e5b3  lea     rax, [rbp+57h+var_60]
0x18000e5b7  mov     [rsp+0D0h+var_B0], rax
0x18000e5bc  mov     dword ptr [rbp+57h+arg_8], ebx
0x18000e5bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e5c4  jmp     loc_18000E711
0x18000e5c9  lea     r8, [rbp+57h+pv]; pv
0x18000e5cd  mov     edx, 20h ; ' '; c
0x18000e5d2  mov     rcx, rax; h
0x18000e5d5  call    cs:__imp_GetObjectW
0x18000e5db  test    eax, eax
0x18000e5dd  jnz     short loc_18000E63D
0x18000e5df  call    cs:__imp_GetLastError
0x18000e5e5  mov     ebx, eax
0x18000e5e7  test    eax, eax
0x18000e5e9  jle     short loc_18000E5F4
0x18000e5eb  movzx   ebx, ax
0x18000e5ee  or      ebx, 80070000h
  ... truncated ...
```
