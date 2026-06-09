# PAL_System_ThreadQuit(ulong)

- ea: `0x140108b7c`
- end: `0x140108caf`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1401021d0`

## callees

- `0x1400019e8`
- `0x140108b7c`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x140108ba6`
- `USER32!PostThreadMessageW` at `0x140108ba6`
- `KERNEL32!Sleep` at `0x140108c38`
- `KERNEL32!Sleep` at `0x140108c38`
- `KERNEL32!GetLastError` at `0x140108bb4`
- `KERNEL32!GetLastError` at `0x140108bb4`

## string_xrefs

- `0x140108b93`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140108bdd`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x140108b8c`: `PAL_System_ThreadQuit`
- `0x140108c48`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

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
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_140143F0C,
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
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)&word_140144006,
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
0x140108b7c  push    rbp
0x140108b7e  push    rbx
0x140108b7f  push    rsi
0x140108b80  push    rdi
0x140108b81  push    r14
0x140108b83  mov     rbp, rsp
0x140108b86  sub     rsp, 60h
0x140108b8a  mov     edi, ecx
0x140108b8c  lea     rsi, aPalSystemThrea_6; "PAL_System_ThreadQuit"
0x140108b93  lea     r14, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140108b9a  xor     r9d, r9d; lParam
0x140108b9d  xor     r8d, r8d; wParam
0x140108ba0  mov     ecx, edi; idThread
0x140108ba2  lea     edx, [r9+12h]; Msg
0x140108ba6  call    cs:__imp_PostThreadMessageW
0x140108bac  test    eax, eax
0x140108bae  jnz     loc_140108CA0
0x140108bb4  call    cs:__imp_GetLastError
0x140108bba  test    eax, eax
0x140108bbc  jg      short loc_140108BC2
0x140108bbe  mov     ebx, eax
0x140108bc0  jmp     short loc_140108BCB
0x140108bc2  movzx   ebx, ax
0x140108bc5  or      ebx, 80070000h
0x140108bcb  cmp     eax, 718h
0x140108bd0  mov     eax, cs:dword_140150118
0x140108bd6  jnz     short loc_140108C43
0x140108bd8  cmp     eax, 2
0x140108bdb  jbe     short loc_140108C33
0x140108bdd  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x140108be4  mov     [rbp+arg_18], rsi
0x140108be8  mov     [rbp+var_8], rax
0x140108bec  lea     rdx, dword_140143F0C
0x140108bf3  lea     rax, [rbp+arg_18]
0x140108bf7  mov     [rbp+arg_8], 31Ch
0x140108bfe  mov     [rsp+60h+var_20], rax
0x140108c03  lea     rax, [rbp+arg_8]
0x140108c07  mov     [rsp+60h+var_28], rax
0x140108c0c  lea     rax, [rbp+var_10]
0x140108c10  mov     [rsp+60h+var_30], rax
0x140108c15  lea     rax, [rbp+arg_10]
0x140108c19  mov     [rsp+60h+var_38], rax
0x140108c1e  lea     rax, [rbp+var_8]
0x140108c22  mov     [rsp+60h+var_40], rax
0x140108c27  mov     [rbp+var_10], r14
0x140108c2b  mov     [rbp+arg_10], ebx
0x140108c2e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140108c33  mov     ecx, 3E8h; dwMilliseconds
0x140108c38  call    cs:__imp_Sleep
0x140108c3e  jmp     loc_140108B9A
0x140108c43  cmp     eax, 2
0x140108c46  jbe     short loc_140108CA2
0x140108c48  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x140108c4f  mov     [rbp+arg_18], rsi
0x140108c53  mov     [rbp+var_10], rax
0x140108c57  lea     rdx, word_140144006
0x140108c5e  lea     rax, [rbp+arg_18]
0x140108c62  mov     [rbp+arg_8], 31Fh
0x140108c69  mov     [rsp+60h+var_20], rax
0x140108c6e  lea     rax, [rbp+arg_8]
0x140108c72  mov     [rsp+60h+var_28], rax
0x140108c77  lea     rax, [rbp+var_8]
0x140108c7b  mov     [rsp+60h+var_30], rax
0x140108c80  lea     rax, [rbp+arg_10]
0x140108c84  mov     [rsp+60h+var_38], rax
0x140108c89  lea     rax, [rbp+var_10]
0x140108c8d  mov     [rsp+60h+var_40], rax
0x140108c92  mov     [rbp+var_8], r14
0x140108c96  mov     [rbp+arg_10], ebx
0x140108c99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140108c9e  jmp     short loc_140108CA2
0x140108ca0  xor     ebx, ebx
0x140108ca2  mov     eax, ebx
0x140108ca4  add     rsp, 60h
0x140108ca8  pop     r14
0x140108caa  pop     rdi
0x140108cab  pop     rsi
0x140108cac  pop     rbx
0x140108cad  pop     rbp
0x140108cae  retn
```
