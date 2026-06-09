# PAL_System_ThreadFree(void *)

- ea: `0x140018014`
- end: `0x14001813f`
- name: `?PAL_System_ThreadFree@@YAJPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017d98`
- `0x14001d150`

## callees

- `0x1400014d4`
- `0x1400015ec`
- `0x140018014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400180bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400180bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001809e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001809e`

## string_xrefs

- `0x140018049`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x1400180de`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140018030`: `PAL_System_ThreadFree`
- `0x1400180d3`: `PAL_System_ThreadFree`
- `0x1400180e9`: `Failed to CloseHandle on thread. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadFree(void *a1, __int64 a2, int a3, int a4)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
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
      if ( (unsigned int)dword_1400880C8 > 2 )
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
          (unsigned int)qword_14007DB90,
          v7,
          v8,
          (__int64)&v11,
          (__int64)&v14,
          (__int64)&v10,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v12);
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v12 = 1563;
      v14 = "PAL_System_ThreadFree";
      v15 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v13 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)byte_14007DBE5,
        a3,
        a4,
        (__int64)&v10,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v12,
        (__int64)&v14);
    }
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140018014  mov     r11, rsp
0x140018017  push    rbp
0x140018018  push    rbx
0x140018019  mov     rbp, rsp
0x14001801c  sub     rsp, 68h
0x140018020  test    rcx, rcx
0x140018023  jnz     short loc_14001809E
0x140018025  mov     eax, cs:dword_1400880C8
0x14001802b  cmp     eax, 2
0x14001802e  jbe     short loc_140018094
0x140018030  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x140018037  mov     [rbp+arg_0], 61Bh
0x14001803e  mov     [rbp+arg_10], rax
0x140018042  lea     rdx, byte_14007DBE5
0x140018049  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140018050  mov     ebx, 80004005h
0x140018055  mov     [rbp+arg_18], rax
0x140018059  lea     rax, aNullParameterP; "NULL parameter passed"
0x140018060  mov     [rbp+var_18], rax
0x140018064  lea     rax, [rbp+arg_10]
0x140018068  mov     [r11-38h], rax
0x14001806c  lea     rax, [rbp+arg_0]
0x140018070  mov     [r11-40h], rax
0x140018074  lea     rax, [rbp+arg_18]
0x140018078  mov     [r11-48h], rax
0x14001807c  lea     rax, [rbp+arg_8]
0x140018080  mov     [r11-50h], rax
0x140018084  lea     rax, [rbp+var_18]
0x140018088  mov     [r11-58h], rax
0x14001808c  mov     [rbp+arg_8], ebx
0x14001808f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140018094  mov     ebx, 80070057h
0x140018099  jmp     loc_140018136
0x14001809e  call    cs:__imp_CloseHandle
0x1400180a4  test    eax, eax
0x1400180a6  jnz     loc_140018134
0x1400180ac  mov     eax, cs:dword_1400880C8
0x1400180b2  mov     ebx, 80004005h
0x1400180b7  cmp     eax, 2
0x1400180ba  jbe     short loc_140018136
0x1400180bc  call    cs:__imp_GetLastError
0x1400180c2  lea     rdx, qword_14007DB90
0x1400180c9  mov     [rbp+arg_8], 622h
0x1400180d0  mov     [rbp+arg_0], eax
0x1400180d3  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x1400180da  mov     [rbp+arg_18], rax
0x1400180de  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400180e5  mov     [rbp+var_18], rax
0x1400180e9  lea     rax, aFailedToCloseh; "Failed to CloseHandle on thread. GetLas"...
0x1400180f0  mov     [rbp+var_10], rax
0x1400180f4  lea     rax, [rbp+arg_0]
0x1400180f8  mov     [rsp+68h+var_20], rax
0x1400180fd  lea     rax, [rbp+arg_18]
0x140018101  mov     [rsp+68h+var_28], rax
0x140018106  lea     rax, [rbp+arg_8]
0x14001810a  mov     [rsp+68h+var_30], rax
0x14001810f  lea     rax, [rbp+var_18]
0x140018113  mov     [rsp+68h+var_38], rax
0x140018118  lea     rax, [rbp+arg_10]
0x14001811c  mov     [rsp+68h+var_40], rax
0x140018121  lea     rax, [rbp+var_10]
0x140018125  mov     [rsp+68h+var_48], rax
0x14001812a  mov     dword ptr [rbp+arg_10], ebx
0x14001812d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140018132  jmp     short loc_140018136
0x140018134  xor     ebx, ebx
0x140018136  mov     eax, ebx
0x140018138  add     rsp, 68h
0x14001813c  pop     rbx
0x14001813d  pop     rbp
0x14001813e  retn
```
