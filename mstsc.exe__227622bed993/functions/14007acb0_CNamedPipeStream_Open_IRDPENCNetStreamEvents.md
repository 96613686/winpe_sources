# CNamedPipeStream::Open(IRDPENCNetStreamEvents *)

- ea: `0x14007acb0`
- end: `0x14007af81`
- name: `?Open@CNamedPipeStream@@UEAAJPEAUIRDPENCNetStreamEvents@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CNamedPipeStream *__hidden this, struct IRDPENCNetStreamEvents *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400025a8`
- `0x1400026b0`
- `0x14000dcac`
- `0x14003c0f0`
- `0x140059568`
- `0x140059b04`
- `0x14007acb0`
- `0x14007b4a4`
- `0x140112010`

## import_xrefs

- `KERNEL32!CreateThreadpoolIo` at `0x14007aefd`
- `KERNEL32!CreateThreadpoolIo` at `0x14007aefd`
- `KERNEL32!FreeLibrary` at `0x14007af63`
- `KERNEL32!FreeLibrary` at `0x14007af63`
- `KERNEL32!GetLastError` at `0x14007ae4e`
- `KERNEL32!GetLastError` at `0x14007af0c`
- `KERNEL32!GetLastError` at `0x14007ae4e`
- `KERNEL32!GetLastError` at `0x14007af0c`
- `KERNEL32!GetModuleHandleExW` at `0x14007ae40`
- `KERNEL32!GetModuleHandleExW` at `0x14007ae40`

## string_xrefs

- `0x14007af2c`: `Failed to associate I/O completion port with threadpool.`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::Open(CNamedPipeStream *this, struct IRDPENCNetStreamEvents *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 (__fastcall *v8)(_QWORD, __int64 *); // rax
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  signed int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rax
  __int16 *v17; // rdx
  PTP_IO ThreadpoolIo; // rax
  signed int LastError; // eax
  HMODULE v20; // rcx
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  const char *v23; // [rsp+58h] [rbp-28h] BYREF
  const char *v24; // [rsp+60h] [rbp-20h] BYREF
  const char *v25; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-10h] BYREF
  int v27; // [rsp+B0h] [rbp+30h] BYREF
  const char *v28; // [rsp+C0h] [rbp+40h] BYREF
  char *v29; // [rsp+C8h] [rbp+48h] BYREF

  v4 = 0;
  v29 = (char *)this + 80;
  CTSCriticalSection::Lock((CNamedPipeStream *)((char *)this + 80));
  CNamedPipeStream::ReinitializeInternal(this);
  if ( *((_QWORD *)this + 7) != -1 )
    goto LABEL_10;
  v8 = (__int64 (__fastcall *)(_QWORD, __int64 *))*((_QWORD *)this + 29);
  v22 = -1;
  if ( v8 )
  {
    v9 = v8(0, &v22);
    v4 = v9;
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_140150118 > 3 )
      {
        v27 = v9;
        v28 = "Open";
        v26[0] = "Failed to generate a new named pipe";
        v25 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_140150118,
          (unsigned int)byte_14013F583,
          v10,
          v11,
          (__int64)&v25,
          (__int64)v26,
          (__int64)&v27,
          (__int64)&v28);
      }
      goto LABEL_5;
    }
    *((_QWORD *)this + 7) = v22;
LABEL_10:
    if ( a2 != *((struct IRDPENCNetStreamEvents **)this + 27) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 216);
      *((_QWORD *)this + 27) = a2;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 216);
    }
    if ( GetModuleHandleExW(4u, (LPCWSTR)CNamedPipeStream::WT_CompleteNamedPipeIo, (HMODULE *)this + 9) )
    {
      ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)this + 7), CNamedPipeStream::WT_CompleteNamedPipeIo, this, 0);
      *((_QWORD *)this + 8) = ThreadpoolIo;
      if ( ThreadpoolIo )
      {
        *((_DWORD *)this + 24) = 1;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v16 = "Failed to associate I/O completion port with threadpool.";
          v27 = 288;
          v17 = word_14013F642;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( (unsigned int)dword_140150118 > 2 )
      {
        v16 = "Failed to get module handle to itself.";
        v27 = 277;
        v17 = word_14013F532;
LABEL_17:
        v26[0] = v16;
        v25 = "Open";
        v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
        v23 = "Error condition failed";
        LODWORD(v28) = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v13,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v23,
          (__int64)&v28,
          (__int64)&v24,
          (__int64)&v27,
          (__int64)&v25,
          (__int64)v26);
      }
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v29);
    if ( (v4 & 0x80000000) == 0 )
      return v4;
    goto LABEL_25;
  }
  v4 = -2147467260;
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v27 = 258;
    v23 = "No valid pipe handle found and no pipe factory provided";
    LODWORD(v28) = -2147467260;
    v24 = "Open";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v26[0] = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)word_14013F5C2,
      v6,
      v7,
      (__int64)v26,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)&v27,
      (__int64)&v24,
      (__int64)&v23);
  }
LABEL_5:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v29);
LABEL_25:
  v20 = (HMODULE)*((_QWORD *)this + 9);
  if ( v20 )
  {
    FreeLibrary(v20);
    *((_QWORD *)this + 9) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x14007acb0  push    rbp
0x14007acb2  push    rbx
0x14007acb3  push    rsi
0x14007acb4  push    rdi
0x14007acb5  push    r14
0x14007acb7  mov     rbp, rsp
0x14007acba  sub     rsp, 80h
0x14007acc1  mov     rdi, rcx
0x14007acc4  mov     r14, rdx
0x14007acc7  add     rcx, 50h ; 'P'; this
0x14007accb  xor     ebx, ebx
0x14007accd  mov     [rbp+arg_18], rcx
0x14007acd1  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14007acd6  mov     rcx, rdi; this
0x14007acd9  call    ?ReinitializeInternal@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::ReinitializeInternal(void)
0x14007acde  cmp     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x14007ace3  jnz     loc_14007AE11
0x14007ace9  mov     rax, [rdi+0E8h]
0x14007acf0  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x14007acf8  test    rax, rax
0x14007acfb  jnz     loc_14007AD97
0x14007ad01  mov     eax, cs:dword_140150118
0x14007ad07  mov     ebx, 80004004h
0x14007ad0c  cmp     eax, 2
0x14007ad0f  jbe     short loc_14007AD89
0x14007ad11  lea     rax, aNoValidPipeHan; "No valid pipe handle found and no pipe "...
0x14007ad18  mov     [rbp+arg_0], 102h
0x14007ad1f  mov     [rbp+var_28], rax
0x14007ad23  lea     rdx, word_14013F5C2
0x14007ad2a  lea     rax, aOpen_0; "Open"
0x14007ad31  mov     dword ptr [rbp+arg_10], ebx
0x14007ad34  mov     [rbp+var_20], rax
0x14007ad38  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007ad3f  mov     [rbp+var_18], rax
0x14007ad43  lea     rax, aErrorCondition; "Error condition failed"
0x14007ad4a  mov     [rbp+var_10], rax
0x14007ad4e  lea     rax, [rbp+var_28]
0x14007ad52  mov     [rsp+80h+var_38], rax
0x14007ad57  lea     rax, [rbp+var_20]
0x14007ad5b  mov     [rsp+80h+var_40], rax
0x14007ad60  lea     rax, [rbp+arg_0]
0x14007ad64  mov     [rsp+80h+var_48], rax
0x14007ad69  lea     rax, [rbp+var_18]
0x14007ad6d  mov     [rsp+80h+var_50], rax
0x14007ad72  lea     rax, [rbp+arg_10]
0x14007ad76  mov     [rsp+80h+var_58], rax
0x14007ad7b  lea     rax, [rbp+var_10]
0x14007ad7f  mov     [rsp+80h+var_60], rax
0x14007ad84  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007ad89  lea     rcx, [rbp+arg_18]; this
0x14007ad8d  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14007ad92  jmp     loc_14007AF5A
0x14007ad97  lea     rdx, [rbp+var_30]
0x14007ad9b  xor     ecx, ecx
0x14007ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007ada2  mov     ebx, eax
0x14007ada4  test    eax, eax
0x14007ada6  jns     short loc_14007AE09
0x14007ada8  mov     ecx, cs:dword_140150118
0x14007adae  cmp     ecx, 3
0x14007adb1  jbe     short loc_14007AD89
0x14007adb3  lea     rax, aOpen_0; "Open"
0x14007adba  mov     [rbp+arg_0], ebx
0x14007adbd  mov     [rbp+arg_10], rax
0x14007adc1  lea     rdx, byte_14013F583
0x14007adc8  lea     rax, aFailedToGenera; "Failed to generate a new named pipe"
0x14007adcf  mov     [rbp+var_10], rax
0x14007add3  lea     rax, aWarningHresult; "Warning HResult failed"
0x14007adda  mov     [rbp+var_18], rax
0x14007adde  lea     rax, [rbp+arg_10]
0x14007ade2  mov     [rsp+80h+var_48], rax
0x14007ade7  lea     rax, [rbp+arg_0]
0x14007adeb  mov     [rsp+80h+var_50], rax
0x14007adf0  lea     rax, [rbp+var_10]
0x14007adf4  mov     [rsp+80h+var_58], rax
0x14007adf9  lea     rax, [rbp+var_18]
0x14007adfd  mov     [rsp+80h+var_60], rax
0x14007ae02  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007ae07  jmp     short loc_14007AD89
0x14007ae09  mov     rax, [rbp+var_30]
0x14007ae0d  mov     [rdi+38h], rax
0x14007ae11  lea     rsi, [rdi+0D8h]
0x14007ae18  cmp     r14, [rsi]
0x14007ae1b  jz      short loc_14007AE30
0x14007ae1d  mov     rcx, rsi
0x14007ae20  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007ae25  mov     rcx, rsi
0x14007ae28  mov     [rsi], r14
0x14007ae2b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14007ae30  lea     r8, [rdi+48h]; phModule
0x14007ae34  mov     ecx, 4; dwFlags
0x14007ae39  lea     rdx, ?WT_CompleteNamedPipeIo@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; lpModuleName
0x14007ae40  call    cs:__imp_GetModuleHandleExW
0x14007ae46  test    eax, eax
0x14007ae48  jnz     loc_14007AEEC
0x14007ae4e  call    cs:__imp_GetLastError
0x14007ae54  mov     ebx, eax
0x14007ae56  test    eax, eax
0x14007ae58  jle     short loc_14007AE63
0x14007ae5a  movzx   ebx, ax
0x14007ae5d  or      ebx, 80070000h
0x14007ae63  mov     eax, cs:dword_140150118
0x14007ae69  cmp     eax, 2
0x14007ae6c  jbe     loc_14007AF4D
0x14007ae72  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x14007ae79  mov     [rbp+arg_0], 115h
0x14007ae80  lea     rdx, word_14013F532
0x14007ae87  mov     [rbp+var_10], rax
0x14007ae8b  lea     rax, aOpen_0; "Open"
0x14007ae92  mov     [rbp+var_18], rax
0x14007ae96  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007ae9d  mov     [rbp+var_20], rax
0x14007aea1  lea     rax, aErrorCondition; "Error condition failed"
0x14007aea8  mov     [rbp+var_28], rax
0x14007aeac  lea     rax, [rbp+var_10]
0x14007aeb0  mov     [rsp+80h+var_38], rax
0x14007aeb5  lea     rax, [rbp+var_18]
0x14007aeb9  mov     [rsp+80h+var_40], rax
0x14007aebe  lea     rax, [rbp+arg_0]
0x14007aec2  mov     [rsp+80h+var_48], rax
0x14007aec7  lea     rax, [rbp+var_20]
0x14007aecb  mov     [rsp+80h+var_50], rax
0x14007aed0  lea     rax, [rbp+arg_10]
0x14007aed4  mov     [rsp+80h+var_58], rax
0x14007aed9  lea     rax, [rbp+var_28]
0x14007aedd  mov     [rsp+80h+var_60], rax
0x14007aee2  mov     dword ptr [rbp+arg_10], ebx
0x14007aee5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007aeea  jmp     short loc_14007AF4D
0x14007aeec  mov     rcx, [rdi+38h]; fl
0x14007aef0  lea     rdx, ?WT_CompleteNamedPipeIo@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x14007aef7  xor     r9d, r9d; pcbe
0x14007aefa  mov     r8, rdi; pv
0x14007aefd  call    cs:__imp_CreateThreadpoolIo
0x14007af03  mov     [rdi+40h], rax
0x14007af07  test    rax, rax
0x14007af0a  jnz     short loc_14007AF46
0x14007af0c  call    cs:__imp_GetLastError
0x14007af12  mov     ebx, eax
0x14007af14  test    eax, eax
0x14007af16  jle     short loc_14007AF21
0x14007af18  movzx   ebx, ax
0x14007af1b  or      ebx, 80070000h
0x14007af21  mov     eax, cs:dword_140150118
0x14007af27  cmp     eax, 2
0x14007af2a  jbe     short loc_14007AF4D
0x14007af2c  lea     rax, aFailedToAssoci_0; "Failed to associate I/O completion port"...
0x14007af33  mov     [rbp+arg_0], 120h
0x14007af3a  lea     rdx, word_14013F642
0x14007af41  jmp     loc_14007AE87
0x14007af46  mov     dword ptr [rdi+60h], 1
0x14007af4d  lea     rcx, [rbp+arg_18]; this
0x14007af51  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14007af56  test    ebx, ebx
0x14007af58  jns     short loc_14007AF71
0x14007af5a  mov     rcx, [rdi+48h]; hLibModule
0x14007af5e  test    rcx, rcx
0x14007af61  jz      short loc_14007AF71
0x14007af63  call    cs:__imp_FreeLibrary
0x14007af69  mov     qword ptr [rdi+48h], 0
0x14007af71  mov     eax, ebx
0x14007af73  add     rsp, 80h
0x14007af7a  pop     r14
0x14007af7c  pop     rdi
0x14007af7d  pop     rsi
0x14007af7e  pop     rbx
0x14007af7f  pop     rbp
0x14007af80  retn
```
