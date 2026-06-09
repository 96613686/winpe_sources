# RdpDWMDirectWindowContext::CreateDebugObjects(void)

- ea: `0x18000d56c`
- end: `0x18000d6a3`
- name: `?CreateDebugObjects@RdpDWMDirectWindowContext@@IEAAXXZ`
- size: `311`
- prototype: `void __fastcall(RdpDWMDirectWindowContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e738`

## callees

- `0x18000160c`
- `0x18000d56c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5f9`
- `GDI32!CreatePen` at `0x18000d590`
- `GDI32!CreatePen` at `0x18000d5aa`
- `GDI32!CreatePen` at `0x18000d5c4`
- `GDI32!CreatePen` at `0x18000d590`
- `GDI32!CreatePen` at `0x18000d5aa`
- `GDI32!CreatePen` at `0x18000d5c4`

## string_xrefs

- `0x18000d623`: `CreateDebugObjects`
- `0x18000d654`: `Failed to create the debug pens`

## pseudocode

```c
void __fastcall RdpDWMDirectWindowContext::CreateDebugObjects(RdpDWMDirectWindowContext *this)
{
  HPEN Pen; // rax
  bool v3; // zf
  signed int LastError; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  const char *v8; // [rsp+50h] [rbp-18h] BYREF
  const char *v9; // [rsp+58h] [rbp-10h] BYREF
  int v10; // [rsp+78h] [rbp+10h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF
  const char *v12; // [rsp+88h] [rbp+20h] BYREF

  if ( (g_uiDwmDirectRenderingFlags & 1) != 0 )
  {
    *((_QWORD *)this + 88) = CreatePen(0, 2, 0xFFu);
    *((_QWORD *)this + 89) = CreatePen(0, 2, 0xFF00u);
    Pen = CreatePen(0, 2, 0xFF0000u);
    v3 = *((_QWORD *)this + 88) == 0;
    *((_QWORD *)this + 90) = Pen;
    if ( !v3 && *((_QWORD *)this + 89) && Pen )
    {
      *((_DWORD *)this + 192) = 1;
    }
    else
    {
      LastError = GetLastError();
      v7 = (unsigned int)LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (int)v7 >= 0 )
        v7 = 2147500037LL;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v10 = 1022;
        v12 = "CreateDebugObjects";
        v11 = v7;
        v8 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
        v9 = "Failed to create the debug pens";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v7,
          (__int64)&word_180038C96,
          v5,
          v6,
          (const unsigned __int16 **)&v9,
          (__int64)&v11,
          (const unsigned __int16 **)&v8,
          (__int64)&v10,
          (const unsigned __int16 **)&v12);
      }
    }
  }
}

```

## disassembly

```asm
0x18000d56c  push    rbx
0x18000d56e  sub     rsp, 60h
0x18000d572  mov     eax, cs:?g_uiDwmDirectRenderingFlags@@3IA; uint g_uiDwmDirectRenderingFlags
0x18000d578  mov     rbx, rcx
0x18000d57b  test    al, 1
0x18000d57d  jz      loc_18000D69D
0x18000d583  mov     edx, 2; cWidth
0x18000d588  xor     ecx, ecx; iStyle
0x18000d58a  mov     r8d, 0FFh; color
0x18000d590  call    cs:__imp_CreatePen
0x18000d596  mov     edx, 2; cWidth
0x18000d59b  xor     ecx, ecx; iStyle
0x18000d59d  mov     r8d, 0FF00h; color
0x18000d5a3  mov     [rbx+2C0h], rax
0x18000d5aa  call    cs:__imp_CreatePen
0x18000d5b0  mov     edx, 2; cWidth
0x18000d5b5  xor     ecx, ecx; iStyle
0x18000d5b7  mov     r8d, 0FF0000h; color
0x18000d5bd  mov     [rbx+2C8h], rax
0x18000d5c4  call    cs:__imp_CreatePen
0x18000d5ca  cmp     qword ptr [rbx+2C0h], 0
0x18000d5d2  mov     [rbx+2D0h], rax
0x18000d5d9  jz      short loc_18000D5F9
0x18000d5db  cmp     qword ptr [rbx+2C8h], 0
0x18000d5e3  jz      short loc_18000D5F9
0x18000d5e5  test    rax, rax
0x18000d5e8  jz      short loc_18000D5F9
0x18000d5ea  mov     dword ptr [rbx+300h], 1
0x18000d5f4  jmp     loc_18000D69D
0x18000d5f9  call    cs:__imp_GetLastError
0x18000d5ff  mov     ecx, eax
0x18000d601  test    eax, eax
0x18000d603  jle     short loc_18000D60E
0x18000d605  movzx   ecx, ax
0x18000d608  or      ecx, 80070000h
0x18000d60e  test    ecx, ecx
0x18000d610  mov     eax, 80004005h
0x18000d615  cmovns  ecx, eax
0x18000d618  mov     eax, cs:dword_180044008
0x18000d61e  cmp     eax, 2
0x18000d621  jbe     short loc_18000D69D
0x18000d623  lea     rax, aCreatedebugobj; "CreateDebugObjects"
0x18000d62a  mov     [rsp+68h+arg_8], 3FEh
0x18000d632  mov     [rsp+68h+arg_18], rax
0x18000d63a  lea     rdx, word_180038C96
0x18000d641  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000d648  mov     [rsp+68h+arg_10], ecx
0x18000d64f  mov     [rsp+68h+var_18], rax
0x18000d654  lea     rax, aFailedToCreate_16; "Failed to create the debug pens"
0x18000d65b  mov     [rsp+68h+var_10], rax
0x18000d660  lea     rax, [rsp+68h+arg_18]
0x18000d668  mov     [rsp+68h+var_28], rax
0x18000d66d  lea     rax, [rsp+68h+arg_8]
0x18000d672  mov     [rsp+68h+var_30], rax
0x18000d677  lea     rax, [rsp+68h+var_18]
0x18000d67c  mov     [rsp+68h+var_38], rax
0x18000d681  lea     rax, [rsp+68h+arg_10]
0x18000d689  mov     [rsp+68h+var_40], rax
0x18000d68e  lea     rax, [rsp+68h+var_10]
0x18000d693  mov     [rsp+68h+var_48], rax
0x18000d698  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000d69d  add     rsp, 60h
0x18000d6a1  pop     rbx
0x18000d6a2  retn
```
