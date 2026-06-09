# CRDPSecFilterEvent::GetInstanceOfRDPSecFilterEvent(CRDPSecFilterEvent * *)

- ea: `0x18005fdfc`
- end: `0x18005fffe`
- name: `?GetInstanceOfRDPSecFilterEvent@CRDPSecFilterEvent@@SAJPEAPEAV1@@Z`
- size: `514`
- prototype: `__int64 __fastcall(struct CRDPSecFilterEvent **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180060a40`

## callees

- `0x180001aa0`
- `0x18005fdfc`
- `0x1800787d4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fe2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fe2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005fe1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005fe1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ffe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ffe6`

## string_xrefs

- `0x18005fe59`: `CreateEvent failed`

## pseudocode

```c
__int64 __fastcall CRDPSecFilterEvent::GetInstanceOfRDPSecFilterEvent(struct CRDPSecFilterEvent **a1)
{
  signed int v2; // ebx
  HANDLE EventW; // rdi
  signed int LastError; // eax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  _DWORD *v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v13; // [rsp+50h] [rbp-20h] BYREF
  const char *v14; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-10h] BYREF
  int v16; // [rsp+98h] [rbp+28h] BYREF
  int v17; // [rsp+A0h] [rbp+30h] BYREF
  const char *v18; // [rsp+A8h] [rbp+38h] BYREF

  v2 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
    goto LABEL_7;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_7:
    v8 = operator new(0x38u);
    if ( v8 )
    {
      v8[6] = -607474739;
      *((_QWORD *)v8 + 2) = "CRDPSecFilterEvent";
      v8[7] = 1;
      *(_QWORD *)v8 = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v8 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
      *(_QWORD *)v8 = &SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v8 + 1) = &CRDPSecFilterEvent::`vftable'{for `CTSObject'};
      v8[10] = 0;
      *((_QWORD *)v8 + 4) = v8;
      *((_QWORD *)v8 + 6) = EventW;
      *a1 = (struct CRDPSecFilterEvent *)v8;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 4) + 8LL))(*((_QWORD *)v8 + 4));
    }
    else
    {
      *a1 = 0;
      v2 = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v16 = 4949;
        v18 = "CRDPSecFilterEvent allocation";
        v17 = -2147024882;
        v15[0] = "GetInstanceOfRDPSecFilterEvent";
        v14 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
        v13 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (unsigned int)&unk_1801BF1A8,
          v10,
          v11,
          (__int64)&v13,
          (__int64)&v17,
          (__int64)&v14,
          (__int64)&v16,
          (__int64)v15,
          (__int64)&v18);
      }
      if ( EventW )
        CloseHandle(EventW);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    v16 = 4945;
    v18 = "CreateEvent failed";
    v17 = v2;
    v13 = "GetInstanceOfRDPSecFilterEvent";
    v14 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
    v15[0] = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)byte_1801BF153,
      v6,
      v7,
      (__int64)v15,
      (__int64)&v17,
      (__int64)&v14,
      (__int64)&v16,
      (__int64)&v13,
      (__int64)&v18);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005fdfc  mov     [rsp-18h+arg_0], rbx
0x18005fe01  push    rbp
0x18005fe02  push    rsi
0x18005fe03  push    rdi
0x18005fe04  mov     rbp, rsp
0x18005fe07  sub     rsp, 70h
0x18005fe0b  mov     rsi, rcx
0x18005fe0e  xor     ebx, ebx
0x18005fe10  xor     r9d, r9d; lpName
0x18005fe13  xor     r8d, r8d; bInitialState
0x18005fe16  xor     ecx, ecx; lpEventAttributes
0x18005fe18  lea     edx, [rbx+1]; bManualReset
0x18005fe1b  call    cs:__imp_CreateEventW
0x18005fe21  mov     rdi, rax
0x18005fe24  test    rax, rax
0x18005fe27  jnz     loc_18005FED6
0x18005fe2d  call    cs:__imp_GetLastError
0x18005fe33  mov     ebx, eax
0x18005fe35  test    eax, eax
0x18005fe37  jle     short loc_18005FE42
0x18005fe39  movzx   ebx, ax
0x18005fe3c  or      ebx, 80070000h
0x18005fe42  test    ebx, ebx
0x18005fe44  jns     loc_18005FED6
0x18005fe4a  mov     eax, cs:CallbackContext
0x18005fe50  cmp     eax, 2
0x18005fe53  jbe     loc_18005FFEC
0x18005fe59  lea     rax, aCreateeventFai; "CreateEvent failed"
0x18005fe60  mov     [rbp+arg_8], 1351h
0x18005fe67  mov     [rbp+arg_18], rax
0x18005fe6b  lea     rdx, byte_1801BF153
0x18005fe72  lea     rax, aGetinstanceofr_0; "GetInstanceOfRDPSecFilterEvent"
0x18005fe79  mov     [rbp+arg_10], ebx
0x18005fe7c  mov     [rbp+var_20], rax
0x18005fe80  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005fe87  mov     [rbp+var_18], rax
0x18005fe8b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005fe92  mov     [rbp+var_10], rax
0x18005fe96  lea     rax, [rbp+arg_18]
0x18005fe9a  mov     [rsp+70h+var_28], rax
0x18005fe9f  lea     rax, [rbp+var_20]
0x18005fea3  mov     [rsp+70h+var_30], rax
0x18005fea8  lea     rax, [rbp+arg_8]
0x18005feac  mov     [rsp+70h+var_38], rax
0x18005feb1  lea     rax, [rbp+var_18]
0x18005feb5  mov     [rsp+70h+var_40], rax
0x18005feba  lea     rax, [rbp+arg_10]
0x18005febe  mov     [rsp+70h+var_48], rax
0x18005fec3  lea     rax, [rbp+var_10]
0x18005fec7  mov     [rsp+70h+var_50], rax
0x18005fecc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005fed1  jmp     loc_18005FFEC
0x18005fed6  mov     ecx, 38h ; '8'; Size
0x18005fedb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005fee0  test    rax, rax
0x18005fee3  jz      short loc_18005FF4F
0x18005fee5  mov     dword ptr [rax+18h], 0DBCAABCDh
0x18005feec  lea     rcx, aCrdpsecfiltere; "CRDPSecFilterEvent"
0x18005fef3  mov     [rax+10h], rcx
0x18005fef7  lea     rcx, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x18005fefe  mov     dword ptr [rax+1Ch], 1
0x18005ff05  mov     [rax], rcx
0x18005ff08  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x18005ff0f  mov     [rax+8], rcx
0x18005ff13  lea     rcx, ??_7?$SlidingStats@N$04$00@@6BINonDelegatingUnknown@@@; const SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'}
0x18005ff1a  mov     [rax], rcx
0x18005ff1d  lea     rcx, ??_7CRDPSecFilterEvent@@6BCTSObject@@@; const CRDPSecFilterEvent::`vftable'{for `CTSObject'}
0x18005ff24  mov     [rax+8], rcx
0x18005ff28  mov     dword ptr [rax+28h], 0
0x18005ff2f  mov     [rax+20h], rax
0x18005ff33  mov     [rax+30h], rdi
0x18005ff37  mov     [rsi], rax
0x18005ff3a  mov     rcx, [rax+20h]
0x18005ff3e  mov     rax, [rcx]
0x18005ff41  mov     rax, [rax+8]
0x18005ff45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff4a  jmp     loc_18005FFEC
0x18005ff4f  mov     qword ptr [rsi], 0
0x18005ff56  mov     ebx, 8007000Eh
0x18005ff5b  mov     eax, cs:CallbackContext
0x18005ff61  cmp     eax, 2
0x18005ff64  jbe     short loc_18005FFDE
0x18005ff66  lea     rax, aCrdpsecfiltere_0; "CRDPSecFilterEvent allocation"
0x18005ff6d  mov     [rbp+arg_8], 1355h
0x18005ff74  mov     [rbp+arg_18], rax
0x18005ff78  lea     rdx, unk_1801BF1A8
0x18005ff7f  lea     rax, aGetinstanceofr_0; "GetInstanceOfRDPSecFilterEvent"
0x18005ff86  mov     [rbp+arg_10], ebx
0x18005ff89  mov     [rbp+var_10], rax
0x18005ff8d  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005ff94  mov     [rbp+var_18], rax
0x18005ff98  lea     rax, aErrorCondition; "Error condition failed"
0x18005ff9f  mov     [rbp+var_20], rax
0x18005ffa3  lea     rax, [rbp+arg_18]
0x18005ffa7  mov     [rsp+70h+var_28], rax
0x18005ffac  lea     rax, [rbp+var_10]
0x18005ffb0  mov     [rsp+70h+var_30], rax
0x18005ffb5  lea     rax, [rbp+arg_8]
0x18005ffb9  mov     [rsp+70h+var_38], rax
0x18005ffbe  lea     rax, [rbp+var_18]
0x18005ffc2  mov     [rsp+70h+var_40], rax
0x18005ffc7  lea     rax, [rbp+arg_10]
0x18005ffcb  mov     [rsp+70h+var_48], rax
0x18005ffd0  lea     rax, [rbp+var_20]
0x18005ffd4  mov     [rsp+70h+var_50], rax
0x18005ffd9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005ffde  test    rdi, rdi
0x18005ffe1  jz      short loc_18005FFEC
0x18005ffe3  mov     rcx, rdi; hObject
0x18005ffe6  call    cs:__imp_CloseHandle
0x18005ffec  mov     eax, ebx
0x18005ffee  mov     rbx, [rsp+70h+arg_0]
0x18005fff6  add     rsp, 70h
0x18005fffa  pop     rdi
0x18005fffb  pop     rsi
0x18005fffc  pop     rbp
0x18005fffd  retn
```
