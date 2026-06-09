# CNamedPipeStream::WriteBuffer(IRDPENCNetStreamBuffer *)

- ea: `0x14007dc60`
- end: `0x14007e05f`
- name: `?WriteBuffer@CNamedPipeStream@@UEAAJPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(PVOID pv, struct IRDPENCNetStreamBuffer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x14007cae0`

## callees

- `0x1400019e8`
- `0x1400026b0`
- `0x140003b2c`
- `0x14000dcac`
- `0x14003e0b4`
- `0x14005bc74`
- `0x14005c29c`
- `0x14007b33c`
- `0x14007bf40`
- `0x14007c058`
- `0x14007c11c`
- `0x14007d7c0`
- `0x14007d7e8`
- `0x14007dc60`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x14007dc9a`
- `KERNEL32!GetTickCount64` at `0x14007dc9a`
- `KERNEL32!WriteFile` at `0x14007df15`
- `KERNEL32!WriteFile` at `0x14007df15`
- `KERNEL32!GetLastError` at `0x14007df1f`
- `KERNEL32!GetLastError` at `0x14007df1f`

## string_xrefs

- `0x14007dd2e`: `WriteBuffer`
- `0x14007ddb1`: `WriteBuffer`
- `0x14007de48`: `WriteBuffer`
- `0x14007df66`: `WriteBuffer`
- `0x14007dfc6`: `WriteBuffer`
- `0x14007de6c`: `Too many pending writes to a named pipe. Aborting the write.`

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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v30 = 474;
      v23 = "SendBuffer: Stream closed";
      v21 = -2147467259;
      v24 = "WriteBuffer";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)byte_1401414C9,
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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_28;
    v30 = 478;
    v26 = "WriteBuffer";
    v11 = byte_140141483;
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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_28;
    v30 = 495;
    v26 = "WriteBuffer";
    v11 = byte_14014143D;
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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_28;
    v30 = 541;
    v26 = "WriteBuffer";
    v11 = byte_140141599;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Failed to post a send. Disconnecting stream.";
    goto LABEL_7;
  }
  v9 = -2147024882;
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v30 = 509;
    v26 = "NP_OVERLAPPED_CONTEXT allocation failed";
    v21 = -2147024882;
    v25 = "WriteBuffer";
    v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v23 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (unsigned int)&byte_1401413EF,
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
0x14007dc60  push    rbp
0x14007dc62  push    rbx
0x14007dc63  push    rsi
0x14007dc64  push    rdi
0x14007dc65  push    r12
0x14007dc67  push    r14
0x14007dc69  push    r15
0x14007dc6b  mov     rbp, rsp
0x14007dc6e  sub     rsp, 80h
0x14007dc75  mov     r15, rdx
0x14007dc78  mov     [rbp+var_28], 0
0x14007dc80  mov     rsi, rcx
0x14007dc83  mov     [rbp+nNumberOfBytesToWrite], 0
0x14007dc8a  mov     [rbp+arg_0], 0
0x14007dc91  xor     edi, edi
0x14007dc93  mov     [rbp+arg_10], 0
0x14007dc9a  call    cs:__imp_GetTickCount64
0x14007dca0  lea     rdx, [rbp+arg_0]
0x14007dca4  mov     rcx, r15
0x14007dca7  mov     rbx, rax
0x14007dcaa  mov     rax, [r15]
0x14007dcad  mov     rax, [rax+38h]
0x14007dcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dcb6  mov     rax, [r15]
0x14007dcb9  lea     rdx, [rbp+nNumberOfBytesToWrite]
0x14007dcbd  mov     rcx, r15
0x14007dcc0  mov     rax, [rax+28h]
0x14007dcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dcc9  mov     rax, [r15]
0x14007dccc  lea     rdx, [rbp+var_28]
0x14007dcd0  mov     rcx, r15
0x14007dcd3  mov     rax, [rax+18h]
0x14007dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dcdc  mov     rax, [r15]
0x14007dcdf  lea     rdx, [rbp+arg_10]
0x14007dce3  mov     rcx, r15
0x14007dce6  mov     rax, [rax+20h]
0x14007dcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dcef  lea     rcx, [rsi+50h]; this
0x14007dcf3  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14007dcf8  cmp     [rsi+60h], edi
0x14007dcfb  jnz     loc_14007DD92
0x14007dd01  mov     eax, cs:dword_140152118
0x14007dd07  mov     ebx, 80004005h
0x14007dd0c  cmp     eax, 2
0x14007dd0f  jbe     loc_14007E027
0x14007dd15  lea     rax, aSendbufferStre; "SendBuffer: Stream closed"
0x14007dd1c  mov     [rbp+arg_18], 1DAh
0x14007dd23  mov     [rbp+var_20], rax
0x14007dd27  lea     rdx, byte_1401414C9
0x14007dd2e  lea     rax, aWritebuffer; "WriteBuffer"
0x14007dd35  mov     [rbp+var_30], ebx
0x14007dd38  mov     [rbp+var_18], rax
0x14007dd3c  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007dd43  mov     [rbp+var_10], rax
0x14007dd47  lea     rax, aErrorCondition; "Error condition failed"
0x14007dd4e  mov     [rbp+var_8], rax
0x14007dd52  lea     rax, [rbp+var_20]
0x14007dd56  mov     [rsp+80h+var_38], rax
0x14007dd5b  lea     rax, [rbp+var_18]
0x14007dd5f  mov     [rsp+80h+var_40], rax
0x14007dd64  lea     rax, [rbp+arg_18]
0x14007dd68  mov     [rsp+80h+var_48], rax
0x14007dd6d  lea     rax, [rbp+var_10]
0x14007dd71  mov     [rsp+80h+var_50], rax
0x14007dd76  lea     rax, [rbp+var_30]
0x14007dd7a  mov     [rsp+80h+var_58], rax
0x14007dd7f  lea     rax, [rbp+var_8]
0x14007dd83  mov     [rsp+80h+lpOverlapped], rax
0x14007dd88  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007dd8d  jmp     loc_14007E027
0x14007dd92  mov     ecx, [rbp+arg_0]
0x14007dd95  add     ecx, [rbp+nNumberOfBytesToWrite]
0x14007dd98  cmp     ecx, [rbp+arg_10]
0x14007dd9b  jle     short loc_14007DE1A
0x14007dd9d  mov     eax, cs:dword_140152118
0x14007dda3  mov     ebx, 80070057h
0x14007dda8  cmp     eax, 2
0x14007ddab  jbe     loc_14007E027
0x14007ddb1  lea     rax, aWritebuffer; "WriteBuffer"
0x14007ddb8  mov     [rbp+arg_18], 1DEh
0x14007ddbf  mov     [rbp+var_8], rax
0x14007ddc3  lea     rdx, byte_140141483
0x14007ddca  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007ddd1  mov     [rbp+var_10], rax
0x14007ddd5  lea     rax, aBufferOverflow; "Buffer overflow detected"
0x14007dddc  mov     [rbp+var_18], rax
0x14007dde0  lea     rax, [rbp+var_8]
0x14007dde4  mov     [rsp+80h+var_40], rax
0x14007dde9  lea     rax, [rbp+arg_18]
0x14007dded  mov     [rsp+80h+var_48], rax
0x14007ddf2  lea     rax, [rbp+var_10]
0x14007ddf6  mov     [rsp+80h+var_50], rax
0x14007ddfb  lea     rax, [rbp+var_30]
0x14007ddff  mov     [rsp+80h+var_58], rax
0x14007de04  lea     rax, [rbp+var_18]
0x14007de08  mov     [rsp+80h+lpOverlapped], rax
0x14007de0d  mov     [rbp+var_30], ebx
0x14007de10  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007de15  jmp     loc_14007E027
0x14007de1a  mov     eax, [rsi+68h]
0x14007de1d  cmp     eax, 3E8h
0x14007de22  jbe     short loc_14007DE78
0x14007de24  mov     rax, [rsi+70h]
0x14007de28  sub     rbx, rax
0x14007de2b  cmp     rbx, 0EA60h
0x14007de32  jbe     short loc_14007DE78
0x14007de34  mov     eax, cs:dword_140152118
0x14007de3a  mov     ebx, 8007274Ch
0x14007de3f  cmp     eax, 2
0x14007de42  jbe     loc_14007E027
0x14007de48  lea     rax, aWritebuffer; "WriteBuffer"
0x14007de4f  mov     [rbp+arg_18], 1EFh
0x14007de56  mov     [rbp+var_8], rax
0x14007de5a  lea     rdx, byte_14014143D
0x14007de61  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007de68  mov     [rbp+var_10], rax
0x14007de6c  lea     rax, aTooManyPending; "Too many pending writes to a named pipe"...
0x14007de73  jmp     loc_14007DDDC
0x14007de78  mov     eax, [rsi+68h]
0x14007de7b  mov     ebx, 1
0x14007de80  add     eax, ebx
0x14007de82  mov     [rsi+68h], eax
0x14007de85  lea     ecx, [rbx+37h]; Size
0x14007de88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007de8d  mov     rdi, rax
0x14007de90  test    rax, rax
0x14007de93  jz      loc_14007DF9D
0x14007de99  mov     qword ptr [rax+28h], 0
0x14007dea1  lea     r14, [rdi+28h]
0x14007dea5  mov     qword ptr [rax+30h], 0
0x14007dead  xorps   xmm0, xmm0
0x14007deb0  movups  xmmword ptr [rdi], xmm0
0x14007deb3  xor     eax, eax
0x14007deb5  movups  xmmword ptr [rdi+10h], xmm0
0x14007deb9  movups  xmmword ptr [rdi+20h], xmm0
0x14007debd  mov     [rdi+30h], rax
0x14007dec1  cmp     rsi, [r14]
0x14007dec4  jz      short loc_14007DED9
0x14007dec6  mov     rcx, r14
0x14007dec9  call    ?SafeRelease@?$TCntPtr@VCRdpSettingsMemoryStream@@@@AEAAXXZ; TCntPtr<CRdpSettingsMemoryStream>::SafeRelease(void)
0x14007dece  mov     rcx, r14
0x14007ded1  mov     [r14], rsi
0x14007ded4  call    ?SafeAddRef@?$TCntPtr@VCNamedPipeStream@@@@AEAAXXZ; TCntPtr<CNamedPipeStream>::SafeAddRef(void)
0x14007ded9  lea     r14, [rdi+30h]
0x14007dedd  cmp     r15, [r14]
0x14007dee0  jz      short loc_14007DEF5
0x14007dee2  mov     rcx, r14
0x14007dee5  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007deea  mov     rcx, r14
0x14007deed  mov     [r14], r15
0x14007def0  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14007def5  mov     rcx, rsi; this
0x14007def8  call    ?StartThreadpoolIo@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::StartThreadpoolIo(void)
0x14007defd  movsxd  rdx, [rbp+arg_0]
0x14007df01  xor     r9d, r9d; lpNumberOfBytesWritten
0x14007df04  add     rdx, [rbp+var_28]; lpBuffer
0x14007df08  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x14007df0c  mov     rcx, [rsi+38h]; hFile
0x14007df10  mov     [rsp+80h+lpOverlapped], rdi; lpOverlapped
0x14007df15  call    cs:__imp_WriteFile
0x14007df1b  test    eax, eax
0x14007df1d  jnz     short loc_14007DF96
0x14007df1f  call    cs:__imp_GetLastError
0x14007df25  mov     r14d, eax
0x14007df28  cmp     eax, 3E5h
0x14007df2d  jz      loc_14007E027
0x14007df33  mov     eax, [rsi+68h]
0x14007df36  mov     rcx, rsi; this
0x14007df39  sub     eax, ebx
0x14007df3b  mov     [rsi+68h], eax
0x14007df3e  call    ?CancelThreadpoolIo@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::CancelThreadpoolIo(void)
0x14007df43  test    r14d, r14d
0x14007df46  jg      short loc_14007DF4D
0x14007df48  mov     ebx, r14d
0x14007df4b  jmp     short loc_14007DF57
0x14007df4d  movzx   ebx, r14w
0x14007df51  or      ebx, 80070000h
0x14007df57  mov     eax, cs:dword_140152118
0x14007df5d  cmp     eax, 2
0x14007df60  jbe     loc_14007E027
0x14007df66  lea     rax, aWritebuffer; "WriteBuffer"
0x14007df6d  mov     [rbp+arg_18], 21Dh
0x14007df74  mov     [rbp+var_8], rax
0x14007df78  lea     rdx, byte_140141599
0x14007df7f  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007df86  mov     [rbp+var_10], rax
0x14007df8a  lea     rax, aFailedToPostAS; "Failed to post a send. Disconnecting st"...
0x14007df91  jmp     loc_14007DDDC
0x14007df96  xor     ebx, ebx
0x14007df98  jmp     loc_14007E027
0x14007df9d  mov     eax, cs:dword_140152118
0x14007dfa3  mov     ebx, 8007000Eh
0x14007dfa8  cmp     eax, 2
0x14007dfab  jbe     short loc_14007E025
0x14007dfad  lea     rax, aNpOverlappedCo; "NP_OVERLAPPED_CONTEXT allocation failed"
0x14007dfb4  mov     [rbp+arg_18], 1FDh
0x14007dfbb  mov     [rbp+var_8], rax
0x14007dfbf  lea     rdx, byte_1401413EF
0x14007dfc6  lea     rax, aWritebuffer; "WriteBuffer"
0x14007dfcd  mov     [rbp+var_30], ebx
0x14007dfd0  mov     [rbp+var_10], rax
0x14007dfd4  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007dfdb  mov     [rbp+var_18], rax
0x14007dfdf  lea     rax, aErrorCondition; "Error condition failed"
0x14007dfe6  mov     [rbp+var_20], rax
0x14007dfea  lea     rax, [rbp+var_8]
0x14007dfee  mov     [rsp+80h+var_38], rax
0x14007dff3  lea     rax, [rbp+var_10]
0x14007dff7  mov     [rsp+80h+var_40], rax
0x14007dffc  lea     rax, [rbp+arg_18]
0x14007e000  mov     [rsp+80h+var_48], rax
0x14007e005  lea     rax, [rbp+var_18]
0x14007e009  mov     [rsp+80h+var_50], rax
0x14007e00e  lea     rax, [rbp+var_30]
0x14007e012  mov     [rsp+80h+var_58], rax
0x14007e017  lea     rax, [rbp+var_20]
0x14007e01b  mov     [rsp+80h+lpOverlapped], rax
0x14007e020  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007e025  xor     edi, edi
0x14007e027  lea     rcx, [rsi+50h]; this
0x14007e02b  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x14007e030  test    ebx, ebx
0x14007e032  jns     short loc_14007E04B
0x14007e034  mov     edx, ebx; int
0x14007e036  mov     rcx, rsi; pv
0x14007e039  call    ?CloseStream@CNamedPipeStream@@AEAAJJ@Z; CNamedPipeStream::CloseStream(long)
0x14007e03e  test    rdi, rdi
0x14007e041  jz      short loc_14007E04B
0x14007e043  mov     rcx, rdi; this
0x14007e046  call    ??_GNP_OVERLAPPED_CONTEXT@CNamedPipeStream@@QEAAPEAXI@Z; CNamedPipeStream::NP_OVERLAPPED_CONTEXT::`scalar deleting destructor'(uint)
0x14007e04b  mov     eax, ebx
0x14007e04d  add     rsp, 80h
0x14007e054  pop     r15
0x14007e056  pop     r14
0x14007e058  pop     r12
0x14007e05a  pop     rdi
0x14007e05b  pop     rsi
0x14007e05c  pop     rbx
0x14007e05d  pop     rbp
0x14007e05e  retn
```
