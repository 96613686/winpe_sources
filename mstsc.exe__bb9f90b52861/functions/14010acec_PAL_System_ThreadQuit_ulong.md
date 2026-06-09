# PAL_System_ThreadQuit(ulong)

- ea: `0x14010acec`
- end: `0x14010ae1f`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140104340`

## callees

- `0x1400019e8`
- `0x14010acec`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14010ad16`
- `USER32!PostThreadMessageW` at `0x14010ad16`
- `KERNEL32!Sleep` at `0x14010ada8`
- `KERNEL32!Sleep` at `0x14010ada8`
- `KERNEL32!GetLastError` at `0x14010ad24`
- `KERNEL32!GetLastError` at `0x14010ad24`

## string_xrefs

- `0x14010ad03`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x14010ad4d`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x14010acfc`: `PAL_System_ThreadQuit`
- `0x14010adb8`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_140146044,
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
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)byte_140146183,
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
0x14010acec  push    rbp
0x14010acee  push    rbx
0x14010acef  push    rsi
0x14010acf0  push    rdi
0x14010acf1  push    r14
0x14010acf3  mov     rbp, rsp
0x14010acf6  sub     rsp, 60h
0x14010acfa  mov     edi, ecx
0x14010acfc  lea     rsi, aPalSystemThrea_6; "PAL_System_ThreadQuit"
0x14010ad03  lea     r14, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010ad0a  xor     r9d, r9d; lParam
0x14010ad0d  xor     r8d, r8d; wParam
0x14010ad10  mov     ecx, edi; idThread
0x14010ad12  lea     edx, [r9+12h]; Msg
0x14010ad16  call    cs:__imp_PostThreadMessageW
0x14010ad1c  test    eax, eax
0x14010ad1e  jnz     loc_14010AE10
0x14010ad24  call    cs:__imp_GetLastError
0x14010ad2a  test    eax, eax
0x14010ad2c  jg      short loc_14010AD32
0x14010ad2e  mov     ebx, eax
0x14010ad30  jmp     short loc_14010AD3B
0x14010ad32  movzx   ebx, ax
0x14010ad35  or      ebx, 80070000h
0x14010ad3b  cmp     eax, 718h
0x14010ad40  mov     eax, cs:dword_140152118
0x14010ad46  jnz     short loc_14010ADB3
0x14010ad48  cmp     eax, 2
0x14010ad4b  jbe     short loc_14010ADA3
0x14010ad4d  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x14010ad54  mov     [rbp+arg_18], rsi
0x14010ad58  mov     [rbp+var_8], rax
0x14010ad5c  lea     rdx, dword_140146044
0x14010ad63  lea     rax, [rbp+arg_18]
0x14010ad67  mov     [rbp+arg_8], 31Ch
0x14010ad6e  mov     [rsp+60h+var_20], rax
0x14010ad73  lea     rax, [rbp+arg_8]
0x14010ad77  mov     [rsp+60h+var_28], rax
0x14010ad7c  lea     rax, [rbp+var_10]
0x14010ad80  mov     [rsp+60h+var_30], rax
0x14010ad85  lea     rax, [rbp+arg_10]
0x14010ad89  mov     [rsp+60h+var_38], rax
0x14010ad8e  lea     rax, [rbp+var_8]
0x14010ad92  mov     [rsp+60h+var_40], rax
0x14010ad97  mov     [rbp+var_10], r14
0x14010ad9b  mov     [rbp+arg_10], ebx
0x14010ad9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010ada3  mov     ecx, 3E8h; dwMilliseconds
0x14010ada8  call    cs:__imp_Sleep
0x14010adae  jmp     loc_14010AD0A
0x14010adb3  cmp     eax, 2
0x14010adb6  jbe     short loc_14010AE12
0x14010adb8  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x14010adbf  mov     [rbp+arg_18], rsi
0x14010adc3  mov     [rbp+var_10], rax
0x14010adc7  lea     rdx, byte_140146183
0x14010adce  lea     rax, [rbp+arg_18]
0x14010add2  mov     [rbp+arg_8], 31Fh
0x14010add9  mov     [rsp+60h+var_20], rax
0x14010adde  lea     rax, [rbp+arg_8]
0x14010ade2  mov     [rsp+60h+var_28], rax
0x14010ade7  lea     rax, [rbp+var_8]
0x14010adeb  mov     [rsp+60h+var_30], rax
0x14010adf0  lea     rax, [rbp+arg_10]
0x14010adf4  mov     [rsp+60h+var_38], rax
0x14010adf9  lea     rax, [rbp+var_10]
0x14010adfd  mov     [rsp+60h+var_40], rax
0x14010ae02  mov     [rbp+var_8], r14
0x14010ae06  mov     [rbp+arg_10], ebx
0x14010ae09  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010ae0e  jmp     short loc_14010AE12
0x14010ae10  xor     ebx, ebx
0x14010ae12  mov     eax, ebx
0x14010ae14  add     rsp, 60h
0x14010ae18  pop     r14
0x14010ae1a  pop     rdi
0x14010ae1b  pop     rsi
0x14010ae1c  pop     rbx
0x14010ae1d  pop     rbp
0x14010ae1e  retn
```
