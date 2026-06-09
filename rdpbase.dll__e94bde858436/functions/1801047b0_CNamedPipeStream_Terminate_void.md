# CNamedPipeStream::Terminate(void)

- ea: `0x1801047b0`
- end: `0x180104a10`
- name: `?Terminate@CNamedPipeStream@@UEAAJXZ`
- size: `608`
- prototype: `__int64 __fastcall(CNamedPipeStream *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180103bdc`
- `0x180103f58`
- `0x180104a20`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180019a80`
- `0x180019ab0`
- `0x18001cc0c`
- `0x18003bcfc`
- `0x1800787d4`
- `0x180078820`
- `0x180103d20`
- `0x1801047b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801049f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801049f7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801048f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801048f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010499c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010499c`

## string_xrefs

- `0x180104926`: `Creation of the transport worker shutdown thread failed`
- `0x18010483c`: `SHUTDOWN_THREADPOOLIO_INFO allocation failed`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::Terminate(CNamedPipeStream *this)
{
  void *v2; // rdi
  int v3; // r9d
  _QWORD *v4; // rax
  int v5; // ecx
  int v6; // r8d
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v9; // r8d
  unsigned int v10; // ecx
  HMODULE v11; // rcx
  const char *v13; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+58h] [rbp-10h] BYREF
  const char *v15; // [rsp+90h] [rbp+28h] BYREF
  int v16; // [rsp+98h] [rbp+30h] BYREF
  const char *v17; // [rsp+A0h] [rbp+38h] BYREF
  const char *v18; // [rsp+A8h] [rbp+40h] BYREF

  v2 = 0;
  CNamedPipeStream::CloseEx((char *)this - 16, 0, 0);
  if ( *((_QWORD *)this + 18) )
  {
    TCntPtr<CTSCoreEventSource>::SafeRelease((char *)this + 144);
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
    v4 = operator new(0x10u);
    v2 = v4;
    if ( v4 )
    {
      *v4 = *((_QWORD *)this + 7);
      v4[1] = *((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CRdpEncTransportWorker::STATIC_ShutdownThreadpoolIo, v4, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
        v2 = 0;
        *((_QWORD *)this + 7) = 0;
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v15) = 116;
          v17 = "Creation of the transport worker shutdown thread failed";
          v16 = v10;
          v18 = "Terminate";
          v14[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
          v13 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v10,
            (unsigned int)&byte_1801C738F,
            v9,
            v3,
            (__int64)&v13,
            (__int64)&v16,
            (__int64)v14,
            (__int64)&v15,
            (__int64)&v18,
            (__int64)&v17);
        }
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v15) = 101;
      v17 = "SHUTDOWN_THREADPOOLIO_INFO allocation failed";
      v16 = -2147024882;
      v18 = "Terminate";
      v13 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
      v14[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&word_1801C733E,
        v6,
        v3,
        (__int64)v14,
        (__int64)&v16,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)&v17);
    }
  }
  *((_DWORD *)this + 5) |= 4u;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v15 = "CNamedPipeStream terminated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)&dword_1801C731C,
      0,
      v3,
      (__int64)&v15);
  }
  if ( v2 )
    operator delete(v2);
  v11 = (HMODULE)*((_QWORD *)this + 7);
  if ( v11 )
  {
    FreeLibrary(v11);
    *((_QWORD *)this + 7) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1801047b0  push    rbp
0x1801047b2  push    rbx
0x1801047b3  push    rsi
0x1801047b4  push    rdi
0x1801047b5  mov     rbp, rsp
0x1801047b8  sub     rsp, 68h
0x1801047bc  mov     rbx, rcx
0x1801047bf  xor     r8d, r8d; unsigned int
0x1801047c2  add     rcx, 0FFFFFFFFFFFFFFF0h; pv
0x1801047c6  xor     edx, edx; int
0x1801047c8  xor     edi, edi
0x1801047ca  call    ?CloseEx@CNamedPipeStream@@UEAAJHK@Z; CNamedPipeStream::CloseEx(int,ulong)
0x1801047cf  lea     rsi, [rbx+90h]
0x1801047d6  cmp     [rsi], rdi
0x1801047d9  jz      short loc_1801047EE
0x1801047db  mov     rcx, rsi
0x1801047de  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSource@@@@AEAAXXZ; TCntPtr<CTSCoreEventSource>::SafeRelease(void)
0x1801047e3  mov     rcx, rsi
0x1801047e6  mov     [rsi], rdi
0x1801047e9  call    ?SafeAddRef@?$TCntPtr@VCNamedPipeStream@@@@AEAAXXZ; TCntPtr<CNamedPipeStream>::SafeAddRef(void)
0x1801047ee  lea     rsi, [rbx+98h]
0x1801047f5  cmp     [rsi], rdi
0x1801047f8  jz      short loc_18010480D
0x1801047fa  mov     rcx, rsi; void *
0x1801047fd  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180104802  mov     rcx, rsi
0x180104805  mov     [rsi], rdi
0x180104808  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010480d  cmp     [rbx+30h], rdi
0x180104811  jz      loc_1801049A8
0x180104817  mov     ecx, 10h; Size
0x18010481c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180104821  mov     rdi, rax
0x180104824  test    rax, rax
0x180104827  jnz     loc_1801048BD
0x18010482d  mov     eax, cs:CallbackContext
0x180104833  cmp     eax, 2
0x180104836  jbe     loc_1801049A8
0x18010483c  lea     rax, aShutdownThread_0; "SHUTDOWN_THREADPOOLIO_INFO allocation f"...
0x180104843  mov     dword ptr [rbp+arg_0], 65h ; 'e'
0x18010484a  mov     [rbp+arg_10], rax
0x18010484e  lea     rdx, word_1801C733E
0x180104855  lea     rax, aTerminate; "Terminate"
0x18010485c  mov     [rbp+arg_8], 8007000Eh
0x180104863  mov     [rbp+arg_18], rax
0x180104867  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010486e  mov     [rbp+var_18], rax
0x180104872  lea     rax, aErrorCondition; "Error condition failed"
0x180104879  mov     [rbp+var_10], rax
0x18010487d  lea     rax, [rbp+arg_10]
0x180104881  mov     [rsp+68h+var_20], rax
0x180104886  lea     rax, [rbp+arg_18]
0x18010488a  mov     [rsp+68h+var_28], rax
0x18010488f  lea     rax, [rbp+arg_0]
0x180104893  mov     [rsp+68h+var_30], rax
0x180104898  lea     rax, [rbp+var_18]
0x18010489c  mov     [rsp+68h+var_38], rax
0x1801048a1  lea     rax, [rbp+arg_8]
0x1801048a5  mov     [rsp+68h+lpThreadId], rax
0x1801048aa  lea     rax, [rbp+var_10]
0x1801048ae  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x1801048b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801048b8  jmp     loc_1801049A8
0x1801048bd  mov     rax, [rbx+38h]
0x1801048c1  lea     r8, ?STATIC_ShutdownThreadpoolIo@CRdpEncTransportWorker@@KAKPEAX@Z; lpStartAddress
0x1801048c8  mov     [rdi], rax
0x1801048cb  mov     r9, rdi; lpParameter
0x1801048ce  mov     rax, [rbx+30h]
0x1801048d2  xor     edx, edx; dwStackSize
0x1801048d4  mov     [rdi+8], rax
0x1801048d8  xor     ecx, ecx; lpThreadAttributes
0x1801048da  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1801048e3  mov     qword ptr [rbx+30h], 0
0x1801048eb  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1801048f3  call    cs:__imp_CreateThread
0x1801048f9  test    rax, rax
0x1801048fc  jnz     loc_180104999
0x180104902  call    cs:__imp_GetLastError
0x180104908  mov     ecx, eax
0x18010490a  test    eax, eax
0x18010490c  jle     short loc_180104917
0x18010490e  movzx   ecx, ax
0x180104911  or      ecx, 80070000h
0x180104917  mov     eax, cs:CallbackContext
0x18010491d  cmp     eax, 2
0x180104920  jbe     loc_1801049A8
0x180104926  lea     rax, aCreationOfTheT; "Creation of the transport worker shutdo"...
0x18010492d  mov     dword ptr [rbp+arg_0], 74h ; 't'
0x180104934  mov     [rbp+arg_10], rax
0x180104938  lea     rdx, byte_1801C738F
0x18010493f  lea     rax, aTerminate; "Terminate"
0x180104946  mov     [rbp+arg_8], ecx
0x180104949  mov     [rbp+arg_18], rax
0x18010494d  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180104954  mov     [rbp+var_10], rax
0x180104958  lea     rax, aErrorCondition; "Error condition failed"
0x18010495f  mov     [rbp+var_18], rax
0x180104963  lea     rax, [rbp+arg_10]
0x180104967  mov     [rsp+68h+var_20], rax
0x18010496c  lea     rax, [rbp+arg_18]
0x180104970  mov     [rsp+68h+var_28], rax
0x180104975  lea     rax, [rbp+arg_0]
0x180104979  mov     [rsp+68h+var_30], rax
0x18010497e  lea     rax, [rbp+var_10]
0x180104982  mov     [rsp+68h+var_38], rax
0x180104987  lea     rax, [rbp+arg_8]
0x18010498b  mov     [rsp+68h+lpThreadId], rax
0x180104990  lea     rax, [rbp+var_18]
0x180104994  jmp     loc_1801048AE
0x180104999  mov     rcx, rax; hObject
0x18010499c  call    cs:__imp_CloseHandle
0x1801049a2  xor     edi, edi
0x1801049a4  mov     [rbx+38h], rdi
0x1801049a8  or      dword ptr [rbx+14h], 4
0x1801049ac  mov     eax, cs:CallbackContext
0x1801049b2  cmp     eax, 4
0x1801049b5  jbe     short loc_1801049E1
0x1801049b7  lea     rax, aCnamedpipestre_0; "CNamedPipeStream terminated"
0x1801049be  xor     r8d, r8d
0x1801049c1  mov     [rbp+arg_0], rax
0x1801049c5  lea     rdx, dword_1801C731C
0x1801049cc  lea     rax, [rbp+arg_0]
0x1801049d0  lea     rcx, CallbackContext
0x1801049d7  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x1801049dc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801049e1  test    rdi, rdi
0x1801049e4  jz      short loc_1801049EE
0x1801049e6  mov     rcx, rdi; Block
0x1801049e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801049ee  mov     rcx, [rbx+38h]; hLibModule
0x1801049f2  test    rcx, rcx
0x1801049f5  jz      short loc_180104A05
0x1801049f7  call    cs:__imp_FreeLibrary
0x1801049fd  mov     qword ptr [rbx+38h], 0
0x180104a05  xor     eax, eax
0x180104a07  add     rsp, 68h
0x180104a0b  pop     rdi
0x180104a0c  pop     rsi
0x180104a0d  pop     rbx
0x180104a0e  pop     rbp
0x180104a0f  retn
```
