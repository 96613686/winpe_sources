# CNamedPipeStream::WriteBuffer(IRDPENCNetStreamBuffer *)

- ea: `0x14007baf0`
- end: `0x14007beef`
- name: `?WriteBuffer@CNamedPipeStream@@UEAAJPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(PVOID pv, struct IRDPENCNetStreamBuffer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x14007a970`

## callees

- `0x1400019e8`
- `0x1400026b0`
- `0x140003b2c`
- `0x14000dcac`
- `0x14003c0f0`
- `0x140059b04`
- `0x14005a12c`
- `0x1400791cc`
- `0x140079dd0`
- `0x140079ee8`
- `0x140079fac`
- `0x14007b650`
- `0x14007b678`
- `0x14007baf0`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x14007bb2a`
- `KERNEL32!GetTickCount64` at `0x14007bb2a`
- `KERNEL32!WriteFile` at `0x14007bda5`
- `KERNEL32!WriteFile` at `0x14007bda5`
- `KERNEL32!GetLastError` at `0x14007bdaf`
- `KERNEL32!GetLastError` at `0x14007bdaf`

## string_xrefs

- `0x14007bcfc`: `Too many pending writes to a named pipe. Aborting the write.`
- `0x14007bbbe`: `WriteBuffer`
- `0x14007bc41`: `WriteBuffer`
- `0x14007bcd8`: `WriteBuffer`
- `0x14007bdf6`: `WriteBuffer`
- `0x14007be56`: `WriteBuffer`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::WriteBuffer(char *pv, struct IRDPENCNetStreamBuffer *a2)
{
  struct _OVERLAPPED *lpOverlapped; // rdi
  ULONGLONG TickCount64; // rbx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  DWORD v10; // ecx
  char *v11; // rdx
  const char *v12; // rax
  struct _OVERLAPPED *v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  _QWORD *p_InternalHigh; // r14
  signed int LastError; // r14d
  unsigned int v19; // edx
  int v21; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+58h] [rbp-28h] BYREF
  const char *v23; // [rsp+60h] [rbp-20h] BYREF
  const char *v24; // [rsp+68h] [rbp-18h] BYREF
  const char *v25; // [rsp+70h] [rbp-10h] BYREF
  const char *v26; // [rsp+78h] [rbp-8h] BYREF
  int v27; // [rsp+C0h] [rbp+40h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+C8h] [rbp+48h] BYREF
  signed int v29; // [rsp+D0h] [rbp+50h] BYREF
  int v30; // [rsp+D8h] [rbp+58h] BYREF

  v22 = 0;
  nNumberOfBytesToWrite = 0;
  v27 = 0;
  lpOverlapped = 0;
  v29 = 0;
  TickCount64 = GetTickCount64();
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(*(_QWORD *)a2 + 56LL))(a2, &v27);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, DWORD *))(*(_QWORD *)a2 + 40LL))(a2, &nNumberOfBytesToWrite);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v22);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, signed int *))(*(_QWORD *)a2 + 32LL))(a2, &v29);
  CTSCriticalSection::Lock((CTSCriticalSection *)(pv + 80));
  if ( !*((_DWORD *)pv + 24) )
  {
    v9 = -2147467259;
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v30 = 474;
      v23 = "SendBuffer: Stream closed";
      v21 = -2147467259;
      v24 = "WriteBuffer";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)byte_14013F355,
        v7,
        v8,
        (__int64)&v26,
        (__int64)&v21,
        (__int64)&v25,
        (__int64)&v30,
        (__int64)&v24,
        (__int64)&v23);
    }
    goto LABEL_28;
  }
  v10 = nNumberOfBytesToWrite + v27;
  if ( (int)(nNumberOfBytesToWrite + v27) > v29 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_28;
    v30 = 478;
    v26 = "WriteBuffer";
    v11 = &byte_14013F30F;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Buffer overflow detected";
LABEL_7:
    v24 = v12;
    v21 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v10,
      (_DWORD)v11,
      v7,
      v8,
      (__int64)&v24,
      (__int64)&v21,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26);
    goto LABEL_28;
  }
  if ( *((_DWORD *)pv + 26) > 0x3E8u && TickCount64 - *((_QWORD *)pv + 14) > 0xEA60 )
  {
    v9 = -2147014836;
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_28;
    v30 = 495;
    v26 = "WriteBuffer";
    v11 = byte_14013F2C9;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Too many pending writes to a named pipe. Aborting the write.";
    goto LABEL_7;
  }
  v9 = 1;
  ++*((_DWORD *)pv + 26);
  v13 = (struct _OVERLAPPED *)operator new(0x38u);
  lpOverlapped = v13;
  if ( v13 )
  {
    v13[1].InternalHigh = 0;
    p_InternalHigh = &v13[1].InternalHigh;
    v13[1].Pointer = 0;
    *(_OWORD *)&v13->Internal = 0;
    *(_OWORD *)&v13->Offset = 0;
    *(_OWORD *)&v13[1].Internal = 0;
    v13[1].Pointer = 0;
    if ( pv != (char *)v13[1].InternalHigh )
    {
      TCntPtr<CRdpSettingsMemoryStream>::SafeRelease(&v13[1].InternalHigh);
      *p_InternalHigh = pv;
      TCntPtr<CNamedPipeStream>::SafeAddRef(&lpOverlapped[1].InternalHigh);
    }
    if ( a2 != lpOverlapped[1].Pointer )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&lpOverlapped[1].Offset);
      lpOverlapped[1].Pointer = a2;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&lpOverlapped[1].Offset);
    }
    CNamedPipeStream::StartThreadpoolIo((CNamedPipeStream *)pv);
    if ( WriteFile(*((HANDLE *)pv + 7), (LPCVOID)(v22 + v27), nNumberOfBytesToWrite, 0, lpOverlapped) )
    {
      v9 = 0;
      goto LABEL_28;
    }
    LastError = GetLastError();
    if ( LastError == 997 )
      goto LABEL_28;
    --*((_DWORD *)pv + 26);
    CNamedPipeStream::CancelThreadpoolIo((CNamedPipeStream *)pv);
    v9 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_28;
    v30 = 541;
    v26 = "WriteBuffer";
    v11 = byte_14013F461;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Failed to post a send. Disconnecting stream.";
    goto LABEL_7;
  }
  v9 = -2147024882;
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v30 = 509;
    v26 = "NP_OVERLAPPED_CONTEXT allocation failed";
    v21 = -2147024882;
    v25 = "WriteBuffer";
    v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v23 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (unsigned int)byte_14013F27B,
      v15,
      v16,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v30,
      (__int64)&v25,
      (__int64)&v26);
  }
  lpOverlapped = 0;
LABEL_28:
  CTSCriticalSection::UnLock((CTSCriticalSection *)(pv + 80));
  if ( v9 < 0 )
  {
    CNamedPipeStream::CloseStream(pv, v9);
    if ( lpOverlapped )
      CNamedPipeStream::NP_OVERLAPPED_CONTEXT::`scalar deleting destructor'(
        (CNamedPipeStream::NP_OVERLAPPED_CONTEXT *)lpOverlapped,
        v19);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14007baf0  push    rbp
0x14007baf2  push    rbx
0x14007baf3  push    rsi
0x14007baf4  push    rdi
0x14007baf5  push    r12
0x14007baf7  push    r14
0x14007baf9  push    r15
0x14007bafb  mov     rbp, rsp
0x14007bafe  sub     rsp, 80h
0x14007bb05  mov     r15, rdx
0x14007bb08  mov     [rbp+var_28], 0
0x14007bb10  mov     rsi, rcx
0x14007bb13  mov     [rbp+nNumberOfBytesToWrite], 0
0x14007bb1a  mov     [rbp+arg_0], 0
0x14007bb21  xor     edi, edi
0x14007bb23  mov     [rbp+arg_10], 0
0x14007bb2a  call    cs:__imp_GetTickCount64
0x14007bb30  lea     rdx, [rbp+arg_0]
0x14007bb34  mov     rcx, r15
0x14007bb37  mov     rbx, rax
0x14007bb3a  mov     rax, [r15]
0x14007bb3d  mov     rax, [rax+38h]
0x14007bb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bb46  mov     rax, [r15]
0x14007bb49  lea     rdx, [rbp+nNumberOfBytesToWrite]
0x14007bb4d  mov     rcx, r15
0x14007bb50  mov     rax, [rax+28h]
0x14007bb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bb59  mov     rax, [r15]
0x14007bb5c  lea     rdx, [rbp+var_28]
0x14007bb60  mov     rcx, r15
0x14007bb63  mov     rax, [rax+18h]
0x14007bb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bb6c  mov     rax, [r15]
0x14007bb6f  lea     rdx, [rbp+arg_10]
0x14007bb73  mov     rcx, r15
0x14007bb76  mov     rax, [rax+20h]
0x14007bb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bb7f  lea     rcx, [rsi+50h]; this
0x14007bb83  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14007bb88  cmp     [rsi+60h], edi
0x14007bb8b  jnz     loc_14007BC22
0x14007bb91  mov     eax, cs:dword_140150118
0x14007bb97  mov     ebx, 80004005h
0x14007bb9c  cmp     eax, 2
0x14007bb9f  jbe     loc_14007BEB7
0x14007bba5  lea     rax, aSendbufferStre; "SendBuffer: Stream closed"
0x14007bbac  mov     [rbp+arg_18], 1DAh
0x14007bbb3  mov     [rbp+var_20], rax
0x14007bbb7  lea     rdx, byte_14013F355
0x14007bbbe  lea     rax, aWritebuffer; "WriteBuffer"
0x14007bbc5  mov     [rbp+var_30], ebx
0x14007bbc8  mov     [rbp+var_18], rax
0x14007bbcc  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007bbd3  mov     [rbp+var_10], rax
0x14007bbd7  lea     rax, aErrorCondition; "Error condition failed"
0x14007bbde  mov     [rbp+var_8], rax
0x14007bbe2  lea     rax, [rbp+var_20]
0x14007bbe6  mov     [rsp+80h+var_38], rax
0x14007bbeb  lea     rax, [rbp+var_18]
0x14007bbef  mov     [rsp+80h+var_40], rax
0x14007bbf4  lea     rax, [rbp+arg_18]
0x14007bbf8  mov     [rsp+80h+var_48], rax
0x14007bbfd  lea     rax, [rbp+var_10]
0x14007bc01  mov     [rsp+80h+var_50], rax
0x14007bc06  lea     rax, [rbp+var_30]
0x14007bc0a  mov     [rsp+80h+var_58], rax
0x14007bc0f  lea     rax, [rbp+var_8]
0x14007bc13  mov     [rsp+80h+lpOverlapped], rax
0x14007bc18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007bc1d  jmp     loc_14007BEB7
0x14007bc22  mov     ecx, [rbp+arg_0]
0x14007bc25  add     ecx, [rbp+nNumberOfBytesToWrite]
0x14007bc28  cmp     ecx, [rbp+arg_10]
0x14007bc2b  jle     short loc_14007BCAA
0x14007bc2d  mov     eax, cs:dword_140150118
0x14007bc33  mov     ebx, 80070057h
0x14007bc38  cmp     eax, 2
0x14007bc3b  jbe     loc_14007BEB7
0x14007bc41  lea     rax, aWritebuffer; "WriteBuffer"
0x14007bc48  mov     [rbp+arg_18], 1DEh
0x14007bc4f  mov     [rbp+var_8], rax
0x14007bc53  lea     rdx, byte_14013F30F
0x14007bc5a  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007bc61  mov     [rbp+var_10], rax
0x14007bc65  lea     rax, aBufferOverflow; "Buffer overflow detected"
0x14007bc6c  mov     [rbp+var_18], rax
0x14007bc70  lea     rax, [rbp+var_8]
0x14007bc74  mov     [rsp+80h+var_40], rax
0x14007bc79  lea     rax, [rbp+arg_18]
0x14007bc7d  mov     [rsp+80h+var_48], rax
0x14007bc82  lea     rax, [rbp+var_10]
0x14007bc86  mov     [rsp+80h+var_50], rax
0x14007bc8b  lea     rax, [rbp+var_30]
0x14007bc8f  mov     [rsp+80h+var_58], rax
0x14007bc94  lea     rax, [rbp+var_18]
0x14007bc98  mov     [rsp+80h+lpOverlapped], rax
0x14007bc9d  mov     [rbp+var_30], ebx
0x14007bca0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007bca5  jmp     loc_14007BEB7
0x14007bcaa  mov     eax, [rsi+68h]
0x14007bcad  cmp     eax, 3E8h
0x14007bcb2  jbe     short loc_14007BD08
0x14007bcb4  mov     rax, [rsi+70h]
0x14007bcb8  sub     rbx, rax
0x14007bcbb  cmp     rbx, 0EA60h
0x14007bcc2  jbe     short loc_14007BD08
0x14007bcc4  mov     eax, cs:dword_140150118
0x14007bcca  mov     ebx, 8007274Ch
0x14007bccf  cmp     eax, 2
0x14007bcd2  jbe     loc_14007BEB7
0x14007bcd8  lea     rax, aWritebuffer; "WriteBuffer"
0x14007bcdf  mov     [rbp+arg_18], 1EFh
0x14007bce6  mov     [rbp+var_8], rax
0x14007bcea  lea     rdx, byte_14013F2C9
0x14007bcf1  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007bcf8  mov     [rbp+var_10], rax
0x14007bcfc  lea     rax, aTooManyPending; "Too many pending writes to a named pipe"...
0x14007bd03  jmp     loc_14007BC6C
0x14007bd08  mov     eax, [rsi+68h]
0x14007bd0b  mov     ebx, 1
0x14007bd10  add     eax, ebx
0x14007bd12  mov     [rsi+68h], eax
0x14007bd15  lea     ecx, [rbx+37h]; Size
0x14007bd18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007bd1d  mov     rdi, rax
0x14007bd20  test    rax, rax
0x14007bd23  jz      loc_14007BE2D
0x14007bd29  mov     qword ptr [rax+28h], 0
0x14007bd31  lea     r14, [rdi+28h]
0x14007bd35  mov     qword ptr [rax+30h], 0
0x14007bd3d  xorps   xmm0, xmm0
0x14007bd40  movups  xmmword ptr [rdi], xmm0
0x14007bd43  xor     eax, eax
0x14007bd45  movups  xmmword ptr [rdi+10h], xmm0
0x14007bd49  movups  xmmword ptr [rdi+20h], xmm0
0x14007bd4d  mov     [rdi+30h], rax
0x14007bd51  cmp     rsi, [r14]
0x14007bd54  jz      short loc_14007BD69
0x14007bd56  mov     rcx, r14
0x14007bd59  call    ?SafeRelease@?$TCntPtr@VCRdpSettingsMemoryStream@@@@AEAAXXZ; TCntPtr<CRdpSettingsMemoryStream>::SafeRelease(void)
0x14007bd5e  mov     rcx, r14
0x14007bd61  mov     [r14], rsi
0x14007bd64  call    ?SafeAddRef@?$TCntPtr@VCNamedPipeStream@@@@AEAAXXZ; TCntPtr<CNamedPipeStream>::SafeAddRef(void)
0x14007bd69  lea     r14, [rdi+30h]
0x14007bd6d  cmp     r15, [r14]
0x14007bd70  jz      short loc_14007BD85
0x14007bd72  mov     rcx, r14
0x14007bd75  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007bd7a  mov     rcx, r14
0x14007bd7d  mov     [r14], r15
0x14007bd80  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14007bd85  mov     rcx, rsi; this
0x14007bd88  call    ?StartThreadpoolIo@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::StartThreadpoolIo(void)
0x14007bd8d  movsxd  rdx, [rbp+arg_0]
0x14007bd91  xor     r9d, r9d; lpNumberOfBytesWritten
0x14007bd94  add     rdx, [rbp+var_28]; lpBuffer
0x14007bd98  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x14007bd9c  mov     rcx, [rsi+38h]; hFile
0x14007bda0  mov     [rsp+80h+lpOverlapped], rdi; lpOverlapped
0x14007bda5  call    cs:__imp_WriteFile
0x14007bdab  test    eax, eax
0x14007bdad  jnz     short loc_14007BE26
0x14007bdaf  call    cs:__imp_GetLastError
0x14007bdb5  mov     r14d, eax
0x14007bdb8  cmp     eax, 3E5h
0x14007bdbd  jz      loc_14007BEB7
0x14007bdc3  mov     eax, [rsi+68h]
0x14007bdc6  mov     rcx, rsi; this
0x14007bdc9  sub     eax, ebx
0x14007bdcb  mov     [rsi+68h], eax
0x14007bdce  call    ?CancelThreadpoolIo@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::CancelThreadpoolIo(void)
0x14007bdd3  test    r14d, r14d
0x14007bdd6  jg      short loc_14007BDDD
0x14007bdd8  mov     ebx, r14d
0x14007bddb  jmp     short loc_14007BDE7
0x14007bddd  movzx   ebx, r14w
0x14007bde1  or      ebx, 80070000h
0x14007bde7  mov     eax, cs:dword_140150118
0x14007bded  cmp     eax, 2
0x14007bdf0  jbe     loc_14007BEB7
0x14007bdf6  lea     rax, aWritebuffer; "WriteBuffer"
0x14007bdfd  mov     [rbp+arg_18], 21Dh
0x14007be04  mov     [rbp+var_8], rax
0x14007be08  lea     rdx, byte_14013F461
0x14007be0f  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007be16  mov     [rbp+var_10], rax
0x14007be1a  lea     rax, aFailedToPostAS; "Failed to post a send. Disconnecting st"...
0x14007be21  jmp     loc_14007BC6C
0x14007be26  xor     ebx, ebx
0x14007be28  jmp     loc_14007BEB7
0x14007be2d  mov     eax, cs:dword_140150118
0x14007be33  mov     ebx, 8007000Eh
0x14007be38  cmp     eax, 2
0x14007be3b  jbe     short loc_14007BEB5
0x14007be3d  lea     rax, aNpOverlappedCo; "NP_OVERLAPPED_CONTEXT allocation failed"
0x14007be44  mov     [rbp+arg_18], 1FDh
0x14007be4b  mov     [rbp+var_8], rax
0x14007be4f  lea     rdx, byte_14013F27B
0x14007be56  lea     rax, aWritebuffer; "WriteBuffer"
0x14007be5d  mov     [rbp+var_30], ebx
0x14007be60  mov     [rbp+var_10], rax
0x14007be64  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007be6b  mov     [rbp+var_18], rax
0x14007be6f  lea     rax, aErrorCondition; "Error condition failed"
0x14007be76  mov     [rbp+var_20], rax
0x14007be7a  lea     rax, [rbp+var_8]
0x14007be7e  mov     [rsp+80h+var_38], rax
0x14007be83  lea     rax, [rbp+var_10]
0x14007be87  mov     [rsp+80h+var_40], rax
0x14007be8c  lea     rax, [rbp+arg_18]
0x14007be90  mov     [rsp+80h+var_48], rax
0x14007be95  lea     rax, [rbp+var_18]
0x14007be99  mov     [rsp+80h+var_50], rax
0x14007be9e  lea     rax, [rbp+var_30]
0x14007bea2  mov     [rsp+80h+var_58], rax
0x14007bea7  lea     rax, [rbp+var_20]
0x14007beab  mov     [rsp+80h+lpOverlapped], rax
0x14007beb0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007beb5  xor     edi, edi
0x14007beb7  lea     rcx, [rsi+50h]; this
0x14007bebb  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x14007bec0  test    ebx, ebx
0x14007bec2  jns     short loc_14007BEDB
0x14007bec4  mov     edx, ebx; int
0x14007bec6  mov     rcx, rsi; pv
0x14007bec9  call    ?CloseStream@CNamedPipeStream@@AEAAJJ@Z; CNamedPipeStream::CloseStream(long)
0x14007bece  test    rdi, rdi
0x14007bed1  jz      short loc_14007BEDB
0x14007bed3  mov     rcx, rdi; this
0x14007bed6  call    ??_GNP_OVERLAPPED_CONTEXT@CNamedPipeStream@@QEAAPEAXI@Z; CNamedPipeStream::NP_OVERLAPPED_CONTEXT::`scalar deleting destructor'(uint)
0x14007bedb  mov     eax, ebx
0x14007bedd  add     rsp, 80h
0x14007bee4  pop     r15
0x14007bee6  pop     r14
0x14007bee8  pop     r12
0x14007beea  pop     rdi
0x14007beeb  pop     rsi
0x14007beec  pop     rbx
0x14007beed  pop     rbp
0x14007beee  retn
```
