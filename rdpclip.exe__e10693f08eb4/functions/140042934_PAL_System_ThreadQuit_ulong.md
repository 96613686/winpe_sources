# PAL_System_ThreadQuit(ulong)

- ea: `0x140042934`
- end: `0x140042a67`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140020230`

## callees

- `0x1400014d4`
- `0x140042934`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14004295e`
- `USER32!PostThreadMessageW` at `0x14004295e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004296c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004296c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400429f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400429f0`

## string_xrefs

- `0x14004294b`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140042944`: `PAL_System_ThreadQuit`
- `0x140042995`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x140042a00`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

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
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_140080715,
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
  if ( (unsigned int)dword_1400880C8 > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)qword_140080968,
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
0x140042934  push    rbp
0x140042936  push    rbx
0x140042937  push    rsi
0x140042938  push    rdi
0x140042939  push    r14
0x14004293b  mov     rbp, rsp
0x14004293e  sub     rsp, 60h
0x140042942  mov     edi, ecx
0x140042944  lea     rsi, aPalSystemThrea_6; "PAL_System_ThreadQuit"
0x14004294b  lea     r14, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042952  xor     r9d, r9d; lParam
0x140042955  xor     r8d, r8d; wParam
0x140042958  mov     ecx, edi; idThread
0x14004295a  lea     edx, [r9+12h]; Msg
0x14004295e  call    cs:__imp_PostThreadMessageW
0x140042964  test    eax, eax
0x140042966  jnz     loc_140042A58
0x14004296c  call    cs:__imp_GetLastError
0x140042972  test    eax, eax
0x140042974  jg      short loc_14004297A
0x140042976  mov     ebx, eax
0x140042978  jmp     short loc_140042983
0x14004297a  movzx   ebx, ax
0x14004297d  or      ebx, 80070000h
0x140042983  cmp     eax, 718h
0x140042988  mov     eax, cs:dword_1400880C8
0x14004298e  jnz     short loc_1400429FB
0x140042990  cmp     eax, 2
0x140042993  jbe     short loc_1400429EB
0x140042995  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x14004299c  mov     [rbp+arg_18], rsi
0x1400429a0  mov     [rbp+var_8], rax
0x1400429a4  lea     rdx, byte_140080715
0x1400429ab  lea     rax, [rbp+arg_18]
0x1400429af  mov     [rbp+arg_8], 31Ch
0x1400429b6  mov     [rsp+60h+var_20], rax
0x1400429bb  lea     rax, [rbp+arg_8]
0x1400429bf  mov     [rsp+60h+var_28], rax
0x1400429c4  lea     rax, [rbp+var_10]
0x1400429c8  mov     [rsp+60h+var_30], rax
0x1400429cd  lea     rax, [rbp+arg_10]
0x1400429d1  mov     [rsp+60h+var_38], rax
0x1400429d6  lea     rax, [rbp+var_8]
0x1400429da  mov     [rsp+60h+var_40], rax
0x1400429df  mov     [rbp+var_10], r14
0x1400429e3  mov     [rbp+arg_10], ebx
0x1400429e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400429eb  mov     ecx, 3E8h; dwMilliseconds
0x1400429f0  call    cs:__imp_Sleep
0x1400429f6  jmp     loc_140042952
0x1400429fb  cmp     eax, 2
0x1400429fe  jbe     short loc_140042A5A
0x140042a00  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x140042a07  mov     [rbp+arg_18], rsi
0x140042a0b  mov     [rbp+var_10], rax
0x140042a0f  lea     rdx, qword_140080968
0x140042a16  lea     rax, [rbp+arg_18]
0x140042a1a  mov     [rbp+arg_8], 31Fh
0x140042a21  mov     [rsp+60h+var_20], rax
0x140042a26  lea     rax, [rbp+arg_8]
0x140042a2a  mov     [rsp+60h+var_28], rax
0x140042a2f  lea     rax, [rbp+var_8]
0x140042a33  mov     [rsp+60h+var_30], rax
0x140042a38  lea     rax, [rbp+arg_10]
0x140042a3c  mov     [rsp+60h+var_38], rax
0x140042a41  lea     rax, [rbp+var_10]
0x140042a45  mov     [rsp+60h+var_40], rax
0x140042a4a  mov     [rbp+var_8], r14
0x140042a4e  mov     [rbp+arg_10], ebx
0x140042a51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140042a56  jmp     short loc_140042A5A
0x140042a58  xor     ebx, ebx
0x140042a5a  mov     eax, ebx
0x140042a5c  add     rsp, 60h
0x140042a60  pop     r14
0x140042a62  pop     rdi
0x140042a63  pop     rsi
0x140042a64  pop     rbx
0x140042a65  pop     rbp
0x140042a66  retn
```
