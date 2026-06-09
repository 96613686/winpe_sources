# CNamedPipeStream::Terminate(void)

- ea: `0x14007d840`
- end: `0x14007da9d`
- name: `?Terminate@CNamedPipeStream@@UEAAJXZ`
- size: `605`
- prototype: `__int64 __fastcall(CNamedPipeStream *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x14007bd40`
- `0x14007c930`
- `0x14007daf0`

## callees

- `0x140001010`
- `0x1400026b0`
- `0x140003b08`
- `0x140003b2c`
- `0x14000dcac`
- `0x14003e0b4`
- `0x14007b33c`
- `0x14007c0c0`
- `0x14007d7c0`
- `0x14007d840`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14007d983`
- `KERNEL32!CreateThread` at `0x14007d983`
- `KERNEL32!FreeLibrary` at `0x14007da84`
- `KERNEL32!FreeLibrary` at `0x14007da84`
- `KERNEL32!CloseHandle` at `0x14007da2c`
- `KERNEL32!CloseHandle` at `0x14007da2c`
- `KERNEL32!GetLastError` at `0x14007d992`
- `KERNEL32!GetLastError` at `0x14007d992`

## string_xrefs

- `0x14007d8cc`: `SHUTDOWN_THREADPOOLIO_INFO allocation failed`
- `0x14007d9b6`: `Creation of the transport worker shutdown thread failed`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::Terminate(CNamedPipeStream *this)
{
  void *v2; // rdi
  int v3; // r8d
  int v4; // r9d
  _QWORD *v5; // rax
  int v6; // ecx
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v9; // ecx
  HMODULE v10; // rcx
  const char *v12; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v13[2]; // [rsp+58h] [rbp-10h] BYREF
  const char *v14; // [rsp+90h] [rbp+28h] BYREF
  int v15; // [rsp+98h] [rbp+30h] BYREF
  const char *v16; // [rsp+A0h] [rbp+38h] BYREF
  const char *v17; // [rsp+A8h] [rbp+40h] BYREF

  v2 = 0;
  CNamedPipeStream::CloseEx((char *)this - 16, 0, 0);
  if ( *((_QWORD *)this + 18) )
  {
    TCntPtr<CRdpSettingsMemoryStream>::SafeRelease((char *)this + 144);
    *((_QWORD *)this + 18) = 0;
    TCntPtr<CNamedPipeStream>::SafeAddRef((char *)this + 144);
  }
  if ( *((_QWORD *)this + 19) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 152);
    *((_QWORD *)this + 19) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 152);
  }
  if ( *((_QWORD *)this + 6) )
  {
    v5 = operator new(0x10u);
    v2 = v5;
    if ( v5 )
    {
      *v5 = *((_QWORD *)this + 7);
      v5[1] = *((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CRdpEncTransportWorker::STATIC_ShutdownThreadpoolIo, v5, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
        v2 = 0;
        *((_QWORD *)this + 7) = 0;
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_140152118 > 2 )
        {
          LODWORD(v14) = 116;
          v16 = "Creation of the transport worker shutdown thread failed";
          v15 = v9;
          v17 = "Terminate";
          v13[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
          v12 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v9,
            (unsigned int)byte_1401419D9,
            v3,
            v4,
            (__int64)&v12,
            (__int64)&v15,
            (__int64)v13,
            (__int64)&v14,
            (__int64)&v17,
            (__int64)&v16);
        }
      }
    }
    else if ( (unsigned int)dword_140152118 > 2 )
    {
      LODWORD(v14) = 101;
      v16 = "SHUTDOWN_THREADPOOLIO_INFO allocation failed";
      v15 = -2147024882;
      v17 = "Terminate";
      v12 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
      v13[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)&dword_1401418CC,
        v3,
        v4,
        (__int64)v13,
        (__int64)&v15,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v17,
        (__int64)&v16);
    }
  }
  *((_DWORD *)this + 5) |= 4u;
  if ( (unsigned int)dword_140152118 > 4 )
  {
    v14 = "CNamedPipeStream terminated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_140152118,
      (unsigned int)&byte_1401419B7,
      v3,
      v4,
      (__int64)&v14);
  }
  if ( v2 )
    operator delete(v2);
  v10 = (HMODULE)*((_QWORD *)this + 7);
  if ( v10 )
  {
    FreeLibrary(v10);
    *((_QWORD *)this + 7) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14007d840  push    rbp
0x14007d842  push    rbx
0x14007d843  push    rsi
0x14007d844  push    rdi
0x14007d845  mov     rbp, rsp
0x14007d848  sub     rsp, 68h
0x14007d84c  mov     rbx, rcx
0x14007d84f  xor     r8d, r8d; unsigned int
0x14007d852  add     rcx, 0FFFFFFFFFFFFFFF0h; pv
0x14007d856  xor     edx, edx; int
0x14007d858  xor     edi, edi
0x14007d85a  call    ?CloseEx@CNamedPipeStream@@UEAAJHK@Z; CNamedPipeStream::CloseEx(int,ulong)
0x14007d85f  lea     rsi, [rbx+90h]
0x14007d866  cmp     [rsi], rdi
0x14007d869  jz      short loc_14007D87E
0x14007d86b  mov     rcx, rsi
0x14007d86e  call    ?SafeRelease@?$TCntPtr@VCRdpSettingsMemoryStream@@@@AEAAXXZ; TCntPtr<CRdpSettingsMemoryStream>::SafeRelease(void)
0x14007d873  mov     rcx, rsi
0x14007d876  mov     [rsi], rdi
0x14007d879  call    ?SafeAddRef@?$TCntPtr@VCNamedPipeStream@@@@AEAAXXZ; TCntPtr<CNamedPipeStream>::SafeAddRef(void)
0x14007d87e  lea     rsi, [rbx+98h]
0x14007d885  cmp     [rsi], rdi
0x14007d888  jz      short loc_14007D89D
0x14007d88a  mov     rcx, rsi
0x14007d88d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007d892  mov     rcx, rsi
0x14007d895  mov     [rsi], rdi
0x14007d898  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14007d89d  cmp     [rbx+30h], rdi
0x14007d8a1  jz      loc_14007DA38
0x14007d8a7  mov     ecx, 10h; Size
0x14007d8ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007d8b1  mov     rdi, rax
0x14007d8b4  test    rax, rax
0x14007d8b7  jnz     loc_14007D94D
0x14007d8bd  mov     eax, cs:dword_140152118
0x14007d8c3  cmp     eax, 2
0x14007d8c6  jbe     loc_14007DA38
0x14007d8cc  lea     rax, aShutdownThread_0; "SHUTDOWN_THREADPOOLIO_INFO allocation f"...
0x14007d8d3  mov     dword ptr [rbp+arg_0], 65h ; 'e'
0x14007d8da  mov     [rbp+arg_10], rax
0x14007d8de  lea     rdx, dword_1401418CC
0x14007d8e5  lea     rax, aTerminate; "Terminate"
0x14007d8ec  mov     [rbp+arg_8], 8007000Eh
0x14007d8f3  mov     [rbp+arg_18], rax
0x14007d8f7  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007d8fe  mov     [rbp+var_18], rax
0x14007d902  lea     rax, aErrorCondition; "Error condition failed"
0x14007d909  mov     [rbp+var_10], rax
0x14007d90d  lea     rax, [rbp+arg_10]
0x14007d911  mov     [rsp+68h+var_20], rax
0x14007d916  lea     rax, [rbp+arg_18]
0x14007d91a  mov     [rsp+68h+var_28], rax
0x14007d91f  lea     rax, [rbp+arg_0]
0x14007d923  mov     [rsp+68h+var_30], rax
0x14007d928  lea     rax, [rbp+var_18]
0x14007d92c  mov     [rsp+68h+var_38], rax
0x14007d931  lea     rax, [rbp+arg_8]
0x14007d935  mov     [rsp+68h+lpThreadId], rax
0x14007d93a  lea     rax, [rbp+var_10]
0x14007d93e  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x14007d943  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007d948  jmp     loc_14007DA38
0x14007d94d  mov     rax, [rbx+38h]
0x14007d951  lea     r8, ?STATIC_ShutdownThreadpoolIo@CRdpEncTransportWorker@@KAKPEAX@Z; lpStartAddress
0x14007d958  mov     [rdi], rax
0x14007d95b  mov     r9, rdi; lpParameter
0x14007d95e  mov     rax, [rbx+30h]
0x14007d962  xor     edx, edx; dwStackSize
0x14007d964  mov     [rdi+8], rax
0x14007d968  xor     ecx, ecx; lpThreadAttributes
0x14007d96a  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x14007d973  mov     qword ptr [rbx+30h], 0
0x14007d97b  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x14007d983  call    cs:__imp_CreateThread
0x14007d989  test    rax, rax
0x14007d98c  jnz     loc_14007DA29
0x14007d992  call    cs:__imp_GetLastError
0x14007d998  mov     ecx, eax
0x14007d99a  test    eax, eax
0x14007d99c  jle     short loc_14007D9A7
0x14007d99e  movzx   ecx, ax
0x14007d9a1  or      ecx, 80070000h
0x14007d9a7  mov     eax, cs:dword_140152118
0x14007d9ad  cmp     eax, 2
0x14007d9b0  jbe     loc_14007DA38
0x14007d9b6  lea     rax, aCreationOfTheT; "Creation of the transport worker shutdo"...
0x14007d9bd  mov     dword ptr [rbp+arg_0], 74h ; 't'
0x14007d9c4  mov     [rbp+arg_10], rax
0x14007d9c8  lea     rdx, byte_1401419D9
0x14007d9cf  lea     rax, aTerminate; "Terminate"
0x14007d9d6  mov     [rbp+arg_8], ecx
0x14007d9d9  mov     [rbp+arg_18], rax
0x14007d9dd  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007d9e4  mov     [rbp+var_10], rax
0x14007d9e8  lea     rax, aErrorCondition; "Error condition failed"
0x14007d9ef  mov     [rbp+var_18], rax
0x14007d9f3  lea     rax, [rbp+arg_10]
0x14007d9f7  mov     [rsp+68h+var_20], rax
0x14007d9fc  lea     rax, [rbp+arg_18]
0x14007da00  mov     [rsp+68h+var_28], rax
0x14007da05  lea     rax, [rbp+arg_0]
0x14007da09  mov     [rsp+68h+var_30], rax
0x14007da0e  lea     rax, [rbp+var_10]
0x14007da12  mov     [rsp+68h+var_38], rax
0x14007da17  lea     rax, [rbp+arg_8]
0x14007da1b  mov     [rsp+68h+lpThreadId], rax
0x14007da20  lea     rax, [rbp+var_18]
0x14007da24  jmp     loc_14007D93E
0x14007da29  mov     rcx, rax; hObject
0x14007da2c  call    cs:__imp_CloseHandle
0x14007da32  xor     edi, edi
0x14007da34  mov     [rbx+38h], rdi
0x14007da38  or      dword ptr [rbx+14h], 4
0x14007da3c  mov     eax, cs:dword_140152118
0x14007da42  cmp     eax, 4
0x14007da45  jbe     short loc_14007DA6E
0x14007da47  lea     rax, aCnamedpipestre_0; "CNamedPipeStream terminated"
0x14007da4e  mov     [rbp+arg_0], rax
0x14007da52  lea     rdx, byte_1401419B7
0x14007da59  lea     rax, [rbp+arg_0]
0x14007da5d  lea     rcx, dword_140152118
0x14007da64  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x14007da69  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14007da6e  test    rdi, rdi
0x14007da71  jz      short loc_14007DA7B
0x14007da73  mov     rcx, rdi; Block
0x14007da76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007da7b  mov     rcx, [rbx+38h]; hLibModule
0x14007da7f  test    rcx, rcx
0x14007da82  jz      short loc_14007DA92
0x14007da84  call    cs:__imp_FreeLibrary
0x14007da8a  mov     qword ptr [rbx+38h], 0
0x14007da92  xor     eax, eax
0x14007da94  add     rsp, 68h
0x14007da98  pop     rdi
0x14007da99  pop     rsi
0x14007da9a  pop     rbx
0x14007da9b  pop     rbp
0x14007da9c  retn
```
