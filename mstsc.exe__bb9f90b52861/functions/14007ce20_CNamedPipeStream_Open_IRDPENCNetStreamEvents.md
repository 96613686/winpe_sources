# CNamedPipeStream::Open(IRDPENCNetStreamEvents *)

- ea: `0x14007ce20`
- end: `0x14007d0f1`
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
- `0x14003e0b4`
- `0x14005b6d8`
- `0x14005bc74`
- `0x14007ce20`
- `0x14007d614`
- `0x140114010`

## import_xrefs

- `KERNEL32!CreateThreadpoolIo` at `0x14007d06d`
- `KERNEL32!CreateThreadpoolIo` at `0x14007d06d`
- `KERNEL32!FreeLibrary` at `0x14007d0d3`
- `KERNEL32!FreeLibrary` at `0x14007d0d3`
- `KERNEL32!GetLastError` at `0x14007cfbe`
- `KERNEL32!GetLastError` at `0x14007d07c`
- `KERNEL32!GetLastError` at `0x14007cfbe`
- `KERNEL32!GetLastError` at `0x14007d07c`
- `KERNEL32!GetModuleHandleExW` at `0x14007cfb0`
- `KERNEL32!GetModuleHandleExW` at `0x14007cfb0`

## string_xrefs

- `0x14007d09c`: `Failed to associate I/O completion port with threadpool.`

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
      if ( (unsigned int)dword_140152118 > 3 )
      {
        v27 = v9;
        v28 = "Open";
        v26[0] = "Failed to generate a new named pipe";
        v25 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_140152118,
          (unsigned int)byte_1401416BB,
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
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v16 = "Failed to associate I/O completion port with threadpool.";
          v27 = 288;
          v17 = word_14014177A;
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
      if ( (unsigned int)dword_140152118 > 2 )
      {
        v16 = "Failed to get module handle to itself.";
        v27 = 277;
        v17 = word_14014166A;
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
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v27 = 258;
    v23 = "No valid pipe handle found and no pipe factory provided";
    LODWORD(v28) = -2147467260;
    v24 = "Open";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v26[0] = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)word_1401416FA,
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
0x14007ce20  push    rbp
0x14007ce22  push    rbx
0x14007ce23  push    rsi
0x14007ce24  push    rdi
0x14007ce25  push    r14
0x14007ce27  mov     rbp, rsp
0x14007ce2a  sub     rsp, 80h
0x14007ce31  mov     rdi, rcx
0x14007ce34  mov     r14, rdx
0x14007ce37  add     rcx, 50h ; 'P'; this
0x14007ce3b  xor     ebx, ebx
0x14007ce3d  mov     [rbp+arg_18], rcx
0x14007ce41  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14007ce46  mov     rcx, rdi; this
0x14007ce49  call    ?ReinitializeInternal@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::ReinitializeInternal(void)
0x14007ce4e  cmp     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x14007ce53  jnz     loc_14007CF81
0x14007ce59  mov     rax, [rdi+0E8h]
0x14007ce60  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x14007ce68  test    rax, rax
0x14007ce6b  jnz     loc_14007CF07
0x14007ce71  mov     eax, cs:dword_140152118
0x14007ce77  mov     ebx, 80004004h
0x14007ce7c  cmp     eax, 2
0x14007ce7f  jbe     short loc_14007CEF9
0x14007ce81  lea     rax, aNoValidPipeHan; "No valid pipe handle found and no pipe "...
0x14007ce88  mov     [rbp+arg_0], 102h
0x14007ce8f  mov     [rbp+var_28], rax
0x14007ce93  lea     rdx, word_1401416FA
0x14007ce9a  lea     rax, aOpen_0; "Open"
0x14007cea1  mov     dword ptr [rbp+arg_10], ebx
0x14007cea4  mov     [rbp+var_20], rax
0x14007cea8  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007ceaf  mov     [rbp+var_18], rax
0x14007ceb3  lea     rax, aErrorCondition; "Error condition failed"
0x14007ceba  mov     [rbp+var_10], rax
0x14007cebe  lea     rax, [rbp+var_28]
0x14007cec2  mov     [rsp+80h+var_38], rax
0x14007cec7  lea     rax, [rbp+var_20]
0x14007cecb  mov     [rsp+80h+var_40], rax
0x14007ced0  lea     rax, [rbp+arg_0]
0x14007ced4  mov     [rsp+80h+var_48], rax
0x14007ced9  lea     rax, [rbp+var_18]
0x14007cedd  mov     [rsp+80h+var_50], rax
0x14007cee2  lea     rax, [rbp+arg_10]
0x14007cee6  mov     [rsp+80h+var_58], rax
0x14007ceeb  lea     rax, [rbp+var_10]
0x14007ceef  mov     [rsp+80h+var_60], rax
0x14007cef4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007cef9  lea     rcx, [rbp+arg_18]; this
0x14007cefd  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14007cf02  jmp     loc_14007D0CA
0x14007cf07  lea     rdx, [rbp+var_30]
0x14007cf0b  xor     ecx, ecx
0x14007cf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007cf12  mov     ebx, eax
0x14007cf14  test    eax, eax
0x14007cf16  jns     short loc_14007CF79
0x14007cf18  mov     ecx, cs:dword_140152118
0x14007cf1e  cmp     ecx, 3
0x14007cf21  jbe     short loc_14007CEF9
0x14007cf23  lea     rax, aOpen_0; "Open"
0x14007cf2a  mov     [rbp+arg_0], ebx
0x14007cf2d  mov     [rbp+arg_10], rax
0x14007cf31  lea     rdx, byte_1401416BB
0x14007cf38  lea     rax, aFailedToGenera; "Failed to generate a new named pipe"
0x14007cf3f  mov     [rbp+var_10], rax
0x14007cf43  lea     rax, aWarningHresult; "Warning HResult failed"
0x14007cf4a  mov     [rbp+var_18], rax
0x14007cf4e  lea     rax, [rbp+arg_10]
0x14007cf52  mov     [rsp+80h+var_48], rax
0x14007cf57  lea     rax, [rbp+arg_0]
0x14007cf5b  mov     [rsp+80h+var_50], rax
0x14007cf60  lea     rax, [rbp+var_10]
0x14007cf64  mov     [rsp+80h+var_58], rax
0x14007cf69  lea     rax, [rbp+var_18]
0x14007cf6d  mov     [rsp+80h+var_60], rax
0x14007cf72  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007cf77  jmp     short loc_14007CEF9
0x14007cf79  mov     rax, [rbp+var_30]
0x14007cf7d  mov     [rdi+38h], rax
0x14007cf81  lea     rsi, [rdi+0D8h]
0x14007cf88  cmp     r14, [rsi]
0x14007cf8b  jz      short loc_14007CFA0
0x14007cf8d  mov     rcx, rsi
0x14007cf90  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007cf95  mov     rcx, rsi
0x14007cf98  mov     [rsi], r14
0x14007cf9b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14007cfa0  lea     r8, [rdi+48h]; phModule
0x14007cfa4  mov     ecx, 4; dwFlags
0x14007cfa9  lea     rdx, ?WT_CompleteNamedPipeIo@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; lpModuleName
0x14007cfb0  call    cs:__imp_GetModuleHandleExW
0x14007cfb6  test    eax, eax
0x14007cfb8  jnz     loc_14007D05C
0x14007cfbe  call    cs:__imp_GetLastError
0x14007cfc4  mov     ebx, eax
0x14007cfc6  test    eax, eax
0x14007cfc8  jle     short loc_14007CFD3
0x14007cfca  movzx   ebx, ax
0x14007cfcd  or      ebx, 80070000h
0x14007cfd3  mov     eax, cs:dword_140152118
0x14007cfd9  cmp     eax, 2
0x14007cfdc  jbe     loc_14007D0BD
0x14007cfe2  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x14007cfe9  mov     [rbp+arg_0], 115h
0x14007cff0  lea     rdx, word_14014166A
0x14007cff7  mov     [rbp+var_10], rax
0x14007cffb  lea     rax, aOpen_0; "Open"
0x14007d002  mov     [rbp+var_18], rax
0x14007d006  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007d00d  mov     [rbp+var_20], rax
0x14007d011  lea     rax, aErrorCondition; "Error condition failed"
0x14007d018  mov     [rbp+var_28], rax
0x14007d01c  lea     rax, [rbp+var_10]
0x14007d020  mov     [rsp+80h+var_38], rax
0x14007d025  lea     rax, [rbp+var_18]
0x14007d029  mov     [rsp+80h+var_40], rax
0x14007d02e  lea     rax, [rbp+arg_0]
0x14007d032  mov     [rsp+80h+var_48], rax
0x14007d037  lea     rax, [rbp+var_20]
0x14007d03b  mov     [rsp+80h+var_50], rax
0x14007d040  lea     rax, [rbp+arg_10]
0x14007d044  mov     [rsp+80h+var_58], rax
0x14007d049  lea     rax, [rbp+var_28]
0x14007d04d  mov     [rsp+80h+var_60], rax
0x14007d052  mov     dword ptr [rbp+arg_10], ebx
0x14007d055  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007d05a  jmp     short loc_14007D0BD
0x14007d05c  mov     rcx, [rdi+38h]; fl
0x14007d060  lea     rdx, ?WT_CompleteNamedPipeIo@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x14007d067  xor     r9d, r9d; pcbe
0x14007d06a  mov     r8, rdi; pv
0x14007d06d  call    cs:__imp_CreateThreadpoolIo
0x14007d073  mov     [rdi+40h], rax
0x14007d077  test    rax, rax
0x14007d07a  jnz     short loc_14007D0B6
0x14007d07c  call    cs:__imp_GetLastError
0x14007d082  mov     ebx, eax
0x14007d084  test    eax, eax
0x14007d086  jle     short loc_14007D091
0x14007d088  movzx   ebx, ax
0x14007d08b  or      ebx, 80070000h
0x14007d091  mov     eax, cs:dword_140152118
0x14007d097  cmp     eax, 2
0x14007d09a  jbe     short loc_14007D0BD
0x14007d09c  lea     rax, aFailedToAssoci_0; "Failed to associate I/O completion port"...
0x14007d0a3  mov     [rbp+arg_0], 120h
0x14007d0aa  lea     rdx, word_14014177A
0x14007d0b1  jmp     loc_14007CFF7
0x14007d0b6  mov     dword ptr [rdi+60h], 1
0x14007d0bd  lea     rcx, [rbp+arg_18]; this
0x14007d0c1  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14007d0c6  test    ebx, ebx
0x14007d0c8  jns     short loc_14007D0E1
0x14007d0ca  mov     rcx, [rdi+48h]; hLibModule
0x14007d0ce  test    rcx, rcx
0x14007d0d1  jz      short loc_14007D0E1
0x14007d0d3  call    cs:__imp_FreeLibrary
0x14007d0d9  mov     qword ptr [rdi+48h], 0
0x14007d0e1  mov     eax, ebx
0x14007d0e3  add     rsp, 80h
0x14007d0ea  pop     r14
0x14007d0ec  pop     rdi
0x14007d0ed  pop     rsi
0x14007d0ee  pop     rbx
0x14007d0ef  pop     rbp
0x14007d0f0  retn
```
