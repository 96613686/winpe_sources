# PAL_System_ThreadQuit(ulong)

- ea: `0x18006796c`
- end: `0x180067a9f`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006c870`

## callees

- `0x1800018a4`
- `0x18006796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800679a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800679a4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180067a28`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180067a28`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x180067996`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x180067996`

## string_xrefs

- `0x180067983`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x1800679cd`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x18006797c`: `PAL_System_ThreadQuit`
- `0x180067a38`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadQuit(DWORD idThread)
{
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
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
    if ( (unsigned int)CallbackContext > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_1801CBD63,
        v4,
        v5,
        (__int64)&v9,
        (__int64)&v11,
        (__int64)&v8,
        (__int64)&v10,
        (__int64)&v12);
    }
    Sleep(0x3E8u);
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)&word_1801CBFB6,
      v4,
      v5,
      (__int64)&v8,
      (__int64)&v11,
      (__int64)&v9,
      (__int64)&v10,
      (__int64)&v12);
  }
  return v6;
}

```

## disassembly

```asm
0x18006796c  push    rbp
0x18006796e  push    rbx
0x18006796f  push    rsi
0x180067970  push    rdi
0x180067971  push    r14
0x180067973  mov     rbp, rsp
0x180067976  sub     rsp, 60h
0x18006797a  mov     edi, ecx
0x18006797c  lea     rsi, aPalSystemThrea_7; "PAL_System_ThreadQuit"
0x180067983  lea     r14, aOnecoreTermsrv_43; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18006798a  xor     r9d, r9d; lParam
0x18006798d  xor     r8d, r8d; wParam
0x180067990  mov     ecx, edi; idThread
0x180067992  lea     edx, [r9+12h]; Msg
0x180067996  call    cs:__imp_PostThreadMessageW
0x18006799c  test    eax, eax
0x18006799e  jnz     loc_180067A90
0x1800679a4  call    cs:__imp_GetLastError
0x1800679aa  test    eax, eax
0x1800679ac  jg      short loc_1800679B2
0x1800679ae  mov     ebx, eax
0x1800679b0  jmp     short loc_1800679BB
0x1800679b2  movzx   ebx, ax
0x1800679b5  or      ebx, 80070000h
0x1800679bb  cmp     eax, 718h
0x1800679c0  mov     eax, cs:CallbackContext
0x1800679c6  jnz     short loc_180067A33
0x1800679c8  cmp     eax, 2
0x1800679cb  jbe     short loc_180067A23
0x1800679cd  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x1800679d4  mov     [rbp+arg_18], rsi
0x1800679d8  mov     [rbp+var_8], rax
0x1800679dc  lea     rdx, byte_1801CBD63
0x1800679e3  lea     rax, [rbp+arg_18]
0x1800679e7  mov     [rbp+arg_8], 31Ch
0x1800679ee  mov     [rsp+60h+var_20], rax
0x1800679f3  lea     rax, [rbp+arg_8]
0x1800679f7  mov     [rsp+60h+var_28], rax
0x1800679fc  lea     rax, [rbp+var_10]
0x180067a00  mov     [rsp+60h+var_30], rax
0x180067a05  lea     rax, [rbp+arg_10]
0x180067a09  mov     [rsp+60h+var_38], rax
0x180067a0e  lea     rax, [rbp+var_8]
0x180067a12  mov     [rsp+60h+var_40], rax
0x180067a17  mov     [rbp+var_10], r14
0x180067a1b  mov     [rbp+arg_10], ebx
0x180067a1e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180067a23  mov     ecx, 3E8h; dwMilliseconds
0x180067a28  call    cs:__imp_Sleep
0x180067a2e  jmp     loc_18006798A
0x180067a33  cmp     eax, 2
0x180067a36  jbe     short loc_180067A92
0x180067a38  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x180067a3f  mov     [rbp+arg_18], rsi
0x180067a43  mov     [rbp+var_10], rax
0x180067a47  lea     rdx, word_1801CBFB6
0x180067a4e  lea     rax, [rbp+arg_18]
0x180067a52  mov     [rbp+arg_8], 31Fh
0x180067a59  mov     [rsp+60h+var_20], rax
0x180067a5e  lea     rax, [rbp+arg_8]
0x180067a62  mov     [rsp+60h+var_28], rax
0x180067a67  lea     rax, [rbp+var_8]
0x180067a6b  mov     [rsp+60h+var_30], rax
0x180067a70  lea     rax, [rbp+arg_10]
0x180067a74  mov     [rsp+60h+var_38], rax
0x180067a79  lea     rax, [rbp+var_10]
0x180067a7d  mov     [rsp+60h+var_40], rax
0x180067a82  mov     [rbp+var_8], r14
0x180067a86  mov     [rbp+arg_10], ebx
0x180067a89  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180067a8e  jmp     short loc_180067A92
0x180067a90  xor     ebx, ebx
0x180067a92  mov     eax, ebx
0x180067a94  add     rsp, 60h
0x180067a98  pop     r14
0x180067a9a  pop     rdi
0x180067a9b  pop     rsi
0x180067a9c  pop     rbx
0x180067a9d  pop     rbp
0x180067a9e  retn
```
