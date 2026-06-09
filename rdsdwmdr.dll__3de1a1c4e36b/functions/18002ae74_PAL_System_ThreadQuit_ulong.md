# PAL_System_ThreadQuit(ulong)

- ea: `0x18002ae74`
- end: `0x18002afa7`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028f40`

## callees

- `0x18000160c`
- `0x18002ae74`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002af30`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002af30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aeac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aeac`
- `USER32!PostThreadMessageW` at `0x18002ae9e`
- `USER32!PostThreadMessageW` at `0x18002ae9e`

## string_xrefs

- `0x18002ae8b`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18002ae84`: `PAL_System_ThreadQuit`
- `0x18002aed5`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x18002af40`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadQuit(DWORD idThread)
{
  signed int LastError; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx
  const char *v8; // [rsp+50h] [rbp-10h] BYREF
  const char *v9; // [rsp+58h] [rbp-8h] BYREF
  int v10; // [rsp+98h] [rbp+38h] BYREF
  unsigned int v11; // [rsp+A0h] [rbp+40h] BYREF
  const char *v12; // [rsp+A8h] [rbp+48h] BYREF

  while ( 1 )
  {
    if ( PostThreadMessageW(idThread, 0x12u, 0, 0) )
      return 0;
    LastError = GetLastError();
    v6 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( LastError != 1816 )
      break;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (__int64)byte_1800403DB,
        v4,
        v5,
        (const unsigned __int16 **)&v9,
        (__int64)&v11,
        (const unsigned __int16 **)&v8,
        (__int64)&v10,
        (const unsigned __int16 **)&v12);
    }
    Sleep(0x3E8u);
  }
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (__int64)byte_1800404D5,
      v4,
      v5,
      (const unsigned __int16 **)&v8,
      (__int64)&v11,
      (const unsigned __int16 **)&v9,
      (__int64)&v10,
      (const unsigned __int16 **)&v12);
  }
  return v6;
}

```

## disassembly

```asm
0x18002ae74  push    rbp
0x18002ae76  push    rbx
0x18002ae77  push    rsi
0x18002ae78  push    rdi
0x18002ae79  push    r14
0x18002ae7b  mov     rbp, rsp
0x18002ae7e  sub     rsp, 60h
0x18002ae82  mov     edi, ecx
0x18002ae84  lea     rsi, aPalSystemThrea_6; "PAL_System_ThreadQuit"
0x18002ae8b  lea     r14, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002ae92  xor     r9d, r9d; lParam
0x18002ae95  xor     r8d, r8d; wParam
0x18002ae98  mov     ecx, edi; idThread
0x18002ae9a  lea     edx, [r9+12h]; Msg
0x18002ae9e  call    cs:__imp_PostThreadMessageW
0x18002aea4  test    eax, eax
0x18002aea6  jnz     loc_18002AF98
0x18002aeac  call    cs:__imp_GetLastError
0x18002aeb2  test    eax, eax
0x18002aeb4  jg      short loc_18002AEBA
0x18002aeb6  mov     ebx, eax
0x18002aeb8  jmp     short loc_18002AEC3
0x18002aeba  movzx   ebx, ax
0x18002aebd  or      ebx, 80070000h
0x18002aec3  cmp     eax, 718h
0x18002aec8  mov     eax, cs:dword_180044008
0x18002aece  jnz     short loc_18002AF3B
0x18002aed0  cmp     eax, 2
0x18002aed3  jbe     short loc_18002AF2B
0x18002aed5  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x18002aedc  mov     [rbp+arg_18], rsi
0x18002aee0  mov     [rbp+var_8], rax
0x18002aee4  lea     rdx, byte_1800403DB
0x18002aeeb  lea     rax, [rbp+arg_18]
0x18002aeef  mov     [rbp+arg_8], 31Ch
0x18002aef6  mov     [rsp+60h+var_20], rax
0x18002aefb  lea     rax, [rbp+arg_8]
0x18002aeff  mov     [rsp+60h+var_28], rax
0x18002af04  lea     rax, [rbp+var_10]
0x18002af08  mov     [rsp+60h+var_30], rax
0x18002af0d  lea     rax, [rbp+arg_10]
0x18002af11  mov     [rsp+60h+var_38], rax
0x18002af16  lea     rax, [rbp+var_8]
0x18002af1a  mov     [rsp+60h+var_40], rax
0x18002af1f  mov     [rbp+var_10], r14
0x18002af23  mov     [rbp+arg_10], ebx
0x18002af26  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002af2b  mov     ecx, 3E8h; dwMilliseconds
0x18002af30  call    cs:__imp_Sleep
0x18002af36  jmp     loc_18002AE92
0x18002af3b  cmp     eax, 2
0x18002af3e  jbe     short loc_18002AF9A
0x18002af40  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x18002af47  mov     [rbp+arg_18], rsi
0x18002af4b  mov     [rbp+var_10], rax
0x18002af4f  lea     rdx, byte_1800404D5
0x18002af56  lea     rax, [rbp+arg_18]
0x18002af5a  mov     [rbp+arg_8], 31Fh
0x18002af61  mov     [rsp+60h+var_20], rax
0x18002af66  lea     rax, [rbp+arg_8]
0x18002af6a  mov     [rsp+60h+var_28], rax
0x18002af6f  lea     rax, [rbp+var_8]
0x18002af73  mov     [rsp+60h+var_30], rax
0x18002af78  lea     rax, [rbp+arg_10]
0x18002af7c  mov     [rsp+60h+var_38], rax
0x18002af81  lea     rax, [rbp+var_10]
0x18002af85  mov     [rsp+60h+var_40], rax
0x18002af8a  mov     [rbp+var_8], r14
0x18002af8e  mov     [rbp+arg_10], ebx
0x18002af91  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002af96  jmp     short loc_18002AF9A
0x18002af98  xor     ebx, ebx
0x18002af9a  mov     eax, ebx
0x18002af9c  add     rsp, 60h
0x18002afa0  pop     r14
0x18002afa2  pop     rdi
0x18002afa3  pop     rsi
0x18002afa4  pop     rbx
0x18002afa5  pop     rbp
0x18002afa6  retn
```
