# PAL_System_ThreadSignalDestroy(void *)

- ea: `0x18002afb0`
- end: `0x18002b0d3`
- name: `?PAL_System_ThreadSignalDestroy@@YAJPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028f20`

## callees

- `0x18000160c`
- `0x18002afb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b0c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b0c4`
- `USER32!DestroyWindow` at `0x18002b044`
- `USER32!DestroyWindow` at `0x18002b044`

## string_xrefs

- `0x18002afe8`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18002b072`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18002afcf`: `PAL_System_ThreadSignalDestroy`
- `0x18002b059`: `PAL_System_ThreadSignalDestroy`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalDestroy(HWND *hMem, __int64 a2, __int64 a3, __int64 a4)
{
  HWND v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const unsigned __int16 *v10[3]; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF
  int v12; // [rsp+88h] [rbp+20h] BYREF
  const char *v13; // [rsp+90h] [rbp+28h] BYREF
  const char *v14; // [rsp+98h] [rbp+30h] BYREF

  if ( hMem )
  {
    v6 = *hMem;
    if ( v6 && !DestroyWindow(v6) && (unsigned int)dword_180044008 > 2 )
    {
      v11 = 735;
      v13 = "PAL_System_ThreadSignalDestroy";
      v12 = -2147467259;
      v14 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v10[0] = (const unsigned __int16 *)"Failed to destroy window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (__int64)byte_18004044B,
        v8,
        v9,
        v10,
        (__int64)&v12,
        (const unsigned __int16 **)&v14,
        (__int64)&v11,
        (const unsigned __int16 **)&v13);
    }
    LocalFree(hMem);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v11 = 724;
      v13 = "PAL_System_ThreadSignalDestroy";
      v12 = -2147467259;
      v14 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v10[0] = (const unsigned __int16 *)"NULL parameter passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (__int64)byte_180040341,
        a3,
        a4,
        v10,
        (__int64)&v12,
        (const unsigned __int16 **)&v14,
        (__int64)&v11,
        (const unsigned __int16 **)&v13);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002afb0  mov     r11, rsp
0x18002afb3  push    rbp
0x18002afb4  push    rbx
0x18002afb5  mov     rbp, rsp
0x18002afb8  sub     rsp, 68h
0x18002afbc  mov     rbx, rcx
0x18002afbf  test    rcx, rcx
0x18002afc2  jnz     short loc_18002B03C
0x18002afc4  mov     eax, cs:dword_180044008
0x18002afca  cmp     eax, 2
0x18002afcd  jbe     short loc_18002B032
0x18002afcf  lea     rax, aPalSystemThrea_7; "PAL_System_ThreadSignalDestroy"
0x18002afd6  mov     [rbp+arg_0], 2D4h
0x18002afdd  mov     [rbp+arg_10], rax
0x18002afe1  lea     rdx, byte_180040341
0x18002afe8  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002afef  mov     [rbp+arg_8], 80004005h
0x18002aff6  mov     [rbp+arg_18], rax
0x18002affa  lea     rax, aNullParameterP; "NULL parameter passed"
0x18002b001  mov     [rbp+var_18], rax
0x18002b005  lea     rax, [rbp+arg_10]
0x18002b009  mov     [r11-38h], rax
0x18002b00d  lea     rax, [rbp+arg_0]
0x18002b011  mov     [r11-40h], rax
0x18002b015  lea     rax, [rbp+arg_18]
0x18002b019  mov     [r11-48h], rax
0x18002b01d  lea     rax, [rbp+arg_8]
0x18002b021  mov     [r11-50h], rax
0x18002b025  lea     rax, [rbp+var_18]
0x18002b029  mov     [r11-58h], rax
0x18002b02d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b032  mov     eax, 80070057h
0x18002b037  jmp     loc_18002B0CC
0x18002b03c  mov     rcx, [rcx]; hWnd
0x18002b03f  test    rcx, rcx
0x18002b042  jz      short loc_18002B0C1
0x18002b044  call    cs:__imp_DestroyWindow
0x18002b04a  test    eax, eax
0x18002b04c  jnz     short loc_18002B0C1
0x18002b04e  mov     eax, cs:dword_180044008
0x18002b054  cmp     eax, 2
0x18002b057  jbe     short loc_18002B0C1
0x18002b059  lea     rax, aPalSystemThrea_7; "PAL_System_ThreadSignalDestroy"
0x18002b060  mov     [rbp+arg_0], 2DFh
0x18002b067  mov     [rbp+arg_10], rax
0x18002b06b  lea     rdx, byte_18004044B
0x18002b072  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b079  mov     [rbp+arg_8], 80004005h
0x18002b080  mov     [rbp+arg_18], rax
0x18002b084  lea     rax, aFailedToDestro_1; "Failed to destroy window"
0x18002b08b  mov     [rbp+var_18], rax
0x18002b08f  lea     rax, [rbp+arg_10]
0x18002b093  mov     [rsp+68h+var_28], rax
0x18002b098  lea     rax, [rbp+arg_0]
0x18002b09c  mov     [rsp+68h+var_30], rax
0x18002b0a1  lea     rax, [rbp+arg_18]
0x18002b0a5  mov     [rsp+68h+var_38], rax
0x18002b0aa  lea     rax, [rbp+arg_8]
0x18002b0ae  mov     [rsp+68h+var_40], rax
0x18002b0b3  lea     rax, [rbp+var_18]
0x18002b0b7  mov     [rsp+68h+var_48], rax
0x18002b0bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b0c1  mov     rcx, rbx; hMem
0x18002b0c4  call    cs:__imp_LocalFree
0x18002b0ca  xor     eax, eax
0x18002b0cc  add     rsp, 68h
0x18002b0d0  pop     rbx
0x18002b0d1  pop     rbp
0x18002b0d2  retn
```
