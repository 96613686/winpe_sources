# PAL_System_ThreadFree(void *)

- ea: `0x18001eb5c`
- end: `0x18001ec87`
- name: `?PAL_System_ThreadFree@@YAJPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e8e0`
- `0x180025a80`

## callees

- `0x18000160c`
- `0x180001f98`
- `0x18001eb5c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec04`

## string_xrefs

- `0x18001eb91`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ec26`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001eb78`: `PAL_System_ThreadFree`
- `0x18001ec1b`: `PAL_System_ThreadFree`
- `0x18001ec31`: `Failed to CloseHandle on thread. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadFree(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v10; // [rsp+50h] [rbp-18h] BYREF
  const char *v11; // [rsp+58h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF
  const char *v14; // [rsp+90h] [rbp+28h] BYREF
  const char *v15; // [rsp+98h] [rbp+30h] BYREF

  if ( a1 )
  {
    if ( CloseHandle(a1) )
    {
      return 0;
    }
    else
    {
      v4 = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LastError = GetLastError();
        v13 = 1570;
        v12 = LastError;
        v15 = "PAL_System_ThreadFree";
        v10 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v11 = "Failed to CloseHandle on thread. GetLastError: 0x%x";
        LODWORD(v14) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v6,
          (__int64)word_18003ED72,
          v7,
          v8,
          (const unsigned __int16 **)&v11,
          (__int64)&v14,
          (const unsigned __int16 **)&v10,
          (__int64)&v13,
          (const unsigned __int16 **)&v15,
          (__int64)&v12);
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v12 = 1563;
      v14 = "PAL_System_ThreadFree";
      v15 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v13 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (__int64)&byte_18003EDC7,
        a3,
        a4,
        (const unsigned __int16 **)&v10,
        (__int64)&v13,
        (const unsigned __int16 **)&v15,
        (__int64)&v12,
        (const unsigned __int16 **)&v14);
    }
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001eb5c  mov     r11, rsp
0x18001eb5f  push    rbp
0x18001eb60  push    rbx
0x18001eb61  mov     rbp, rsp
0x18001eb64  sub     rsp, 68h
0x18001eb68  test    rcx, rcx
0x18001eb6b  jnz     short loc_18001EBE6
0x18001eb6d  mov     eax, cs:dword_180044008
0x18001eb73  cmp     eax, 2
0x18001eb76  jbe     short loc_18001EBDC
0x18001eb78  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x18001eb7f  mov     [rbp+arg_0], 61Bh
0x18001eb86  mov     [rbp+arg_10], rax
0x18001eb8a  lea     rdx, byte_18003EDC7
0x18001eb91  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001eb98  mov     ebx, 80004005h
0x18001eb9d  mov     [rbp+arg_18], rax
0x18001eba1  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001eba8  mov     [rbp+var_18], rax
0x18001ebac  lea     rax, [rbp+arg_10]
0x18001ebb0  mov     [r11-38h], rax
0x18001ebb4  lea     rax, [rbp+arg_0]
0x18001ebb8  mov     [r11-40h], rax
0x18001ebbc  lea     rax, [rbp+arg_18]
0x18001ebc0  mov     [r11-48h], rax
0x18001ebc4  lea     rax, [rbp+arg_8]
0x18001ebc8  mov     [r11-50h], rax
0x18001ebcc  lea     rax, [rbp+var_18]
0x18001ebd0  mov     [r11-58h], rax
0x18001ebd4  mov     [rbp+arg_8], ebx
0x18001ebd7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ebdc  mov     ebx, 80070057h
0x18001ebe1  jmp     loc_18001EC7E
0x18001ebe6  call    cs:__imp_CloseHandle
0x18001ebec  test    eax, eax
0x18001ebee  jnz     loc_18001EC7C
0x18001ebf4  mov     eax, cs:dword_180044008
0x18001ebfa  mov     ebx, 80004005h
0x18001ebff  cmp     eax, 2
0x18001ec02  jbe     short loc_18001EC7E
0x18001ec04  call    cs:__imp_GetLastError
0x18001ec0a  lea     rdx, word_18003ED72
0x18001ec11  mov     [rbp+arg_8], 622h
0x18001ec18  mov     [rbp+arg_0], eax
0x18001ec1b  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x18001ec22  mov     [rbp+arg_18], rax
0x18001ec26  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ec2d  mov     [rbp+var_18], rax
0x18001ec31  lea     rax, aFailedToCloseh; "Failed to CloseHandle on thread. GetLas"...
0x18001ec38  mov     [rbp+var_10], rax
0x18001ec3c  lea     rax, [rbp+arg_0]
0x18001ec40  mov     [rsp+68h+var_20], rax
0x18001ec45  lea     rax, [rbp+arg_18]
0x18001ec49  mov     [rsp+68h+var_28], rax
0x18001ec4e  lea     rax, [rbp+arg_8]
0x18001ec52  mov     [rsp+68h+var_30], rax
0x18001ec57  lea     rax, [rbp+var_18]
0x18001ec5b  mov     [rsp+68h+var_38], rax
0x18001ec60  lea     rax, [rbp+arg_10]
0x18001ec64  mov     [rsp+68h+var_40], rax
0x18001ec69  lea     rax, [rbp+var_10]
0x18001ec6d  mov     [rsp+68h+var_48], rax
0x18001ec72  mov     dword ptr [rbp+arg_10], ebx
0x18001ec75  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ec7a  jmp     short loc_18001EC7E
0x18001ec7c  xor     ebx, ebx
0x18001ec7e  mov     eax, ebx
0x18001ec80  add     rsp, 68h
0x18001ec84  pop     rbx
0x18001ec85  pop     rbp
0x18001ec86  retn
```
