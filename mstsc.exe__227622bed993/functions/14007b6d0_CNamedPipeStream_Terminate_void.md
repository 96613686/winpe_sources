# CNamedPipeStream::Terminate(void)

- ea: `0x14007b6d0`
- end: `0x14007b92d`
- name: `?Terminate@CNamedPipeStream@@UEAAJXZ`
- size: `605`
- prototype: `__int64 __fastcall(CNamedPipeStream *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x140079bd0`
- `0x14007a7c0`
- `0x14007b980`

## callees

- `0x140001010`
- `0x1400026b0`
- `0x140003b08`
- `0x140003b2c`
- `0x14000dcac`
- `0x14003c0f0`
- `0x1400791cc`
- `0x140079f50`
- `0x14007b650`
- `0x14007b6d0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14007b813`
- `KERNEL32!CreateThread` at `0x14007b813`
- `KERNEL32!FreeLibrary` at `0x14007b914`
- `KERNEL32!FreeLibrary` at `0x14007b914`
- `KERNEL32!CloseHandle` at `0x14007b8bc`
- `KERNEL32!CloseHandle` at `0x14007b8bc`
- `KERNEL32!GetLastError` at `0x14007b822`
- `KERNEL32!GetLastError` at `0x14007b822`

## string_xrefs

- `0x14007b75c`: `SHUTDOWN_THREADPOOLIO_INFO allocation failed`
- `0x14007b846`: `Creation of the transport worker shutdown thread failed`

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
        if ( (unsigned int)dword_140150118 > 2 )
        {
          LODWORD(v14) = 116;
          v16 = "Creation of the transport worker shutdown thread failed";
          v15 = v9;
          v17 = "Terminate";
          v13[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
          v12 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v9,
            (unsigned int)byte_14013F8A1,
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
    else if ( (unsigned int)dword_140150118 > 2 )
    {
      LODWORD(v14) = 101;
      v16 = "SHUTDOWN_THREADPOOLIO_INFO allocation failed";
      v15 = -2147024882;
      v17 = "Terminate";
      v12 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
      v13[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)&dword_14013F794,
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
  if ( (unsigned int)dword_140150118 > 4 )
  {
    v14 = "CNamedPipeStream terminated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_140150118,
      (unsigned int)&byte_14013F87F,
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
0x14007b6d0  push    rbp
0x14007b6d2  push    rbx
0x14007b6d3  push    rsi
0x14007b6d4  push    rdi
0x14007b6d5  mov     rbp, rsp
0x14007b6d8  sub     rsp, 68h
0x14007b6dc  mov     rbx, rcx
0x14007b6df  xor     r8d, r8d; unsigned int
0x14007b6e2  add     rcx, 0FFFFFFFFFFFFFFF0h; pv
0x14007b6e6  xor     edx, edx; int
0x14007b6e8  xor     edi, edi
0x14007b6ea  call    ?CloseEx@CNamedPipeStream@@UEAAJHK@Z; CNamedPipeStream::CloseEx(int,ulong)
0x14007b6ef  lea     rsi, [rbx+90h]
0x14007b6f6  cmp     [rsi], rdi
0x14007b6f9  jz      short loc_14007B70E
0x14007b6fb  mov     rcx, rsi
0x14007b6fe  call    ?SafeRelease@?$TCntPtr@VCRdpSettingsMemoryStream@@@@AEAAXXZ; TCntPtr<CRdpSettingsMemoryStream>::SafeRelease(void)
0x14007b703  mov     rcx, rsi
0x14007b706  mov     [rsi], rdi
0x14007b709  call    ?SafeAddRef@?$TCntPtr@VCNamedPipeStream@@@@AEAAXXZ; TCntPtr<CNamedPipeStream>::SafeAddRef(void)
0x14007b70e  lea     rsi, [rbx+98h]
0x14007b715  cmp     [rsi], rdi
0x14007b718  jz      short loc_14007B72D
0x14007b71a  mov     rcx, rsi
0x14007b71d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007b722  mov     rcx, rsi
0x14007b725  mov     [rsi], rdi
0x14007b728  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14007b72d  cmp     [rbx+30h], rdi
0x14007b731  jz      loc_14007B8C8
0x14007b737  mov     ecx, 10h; Size
0x14007b73c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007b741  mov     rdi, rax
0x14007b744  test    rax, rax
0x14007b747  jnz     loc_14007B7DD
0x14007b74d  mov     eax, cs:dword_140150118
0x14007b753  cmp     eax, 2
0x14007b756  jbe     loc_14007B8C8
0x14007b75c  lea     rax, aShutdownThread_0; "SHUTDOWN_THREADPOOLIO_INFO allocation f"...
0x14007b763  mov     dword ptr [rbp+arg_0], 65h ; 'e'
0x14007b76a  mov     [rbp+arg_10], rax
0x14007b76e  lea     rdx, dword_14013F794
0x14007b775  lea     rax, aTerminate; "Terminate"
0x14007b77c  mov     [rbp+arg_8], 8007000Eh
0x14007b783  mov     [rbp+arg_18], rax
0x14007b787  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007b78e  mov     [rbp+var_18], rax
0x14007b792  lea     rax, aErrorCondition; "Error condition failed"
0x14007b799  mov     [rbp+var_10], rax
0x14007b79d  lea     rax, [rbp+arg_10]
0x14007b7a1  mov     [rsp+68h+var_20], rax
0x14007b7a6  lea     rax, [rbp+arg_18]
0x14007b7aa  mov     [rsp+68h+var_28], rax
0x14007b7af  lea     rax, [rbp+arg_0]
0x14007b7b3  mov     [rsp+68h+var_30], rax
0x14007b7b8  lea     rax, [rbp+var_18]
0x14007b7bc  mov     [rsp+68h+var_38], rax
0x14007b7c1  lea     rax, [rbp+arg_8]
0x14007b7c5  mov     [rsp+68h+lpThreadId], rax
0x14007b7ca  lea     rax, [rbp+var_10]
0x14007b7ce  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x14007b7d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14007b7d8  jmp     loc_14007B8C8
0x14007b7dd  mov     rax, [rbx+38h]
0x14007b7e1  lea     r8, ?STATIC_ShutdownThreadpoolIo@CRdpEncTransportWorker@@KAKPEAX@Z; lpStartAddress
0x14007b7e8  mov     [rdi], rax
0x14007b7eb  mov     r9, rdi; lpParameter
0x14007b7ee  mov     rax, [rbx+30h]
0x14007b7f2  xor     edx, edx; dwStackSize
0x14007b7f4  mov     [rdi+8], rax
0x14007b7f8  xor     ecx, ecx; lpThreadAttributes
0x14007b7fa  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x14007b803  mov     qword ptr [rbx+30h], 0
0x14007b80b  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x14007b813  call    cs:__imp_CreateThread
0x14007b819  test    rax, rax
0x14007b81c  jnz     loc_14007B8B9
0x14007b822  call    cs:__imp_GetLastError
0x14007b828  mov     ecx, eax
0x14007b82a  test    eax, eax
0x14007b82c  jle     short loc_14007B837
0x14007b82e  movzx   ecx, ax
0x14007b831  or      ecx, 80070000h
0x14007b837  mov     eax, cs:dword_140150118
0x14007b83d  cmp     eax, 2
0x14007b840  jbe     loc_14007B8C8
0x14007b846  lea     rax, aCreationOfTheT; "Creation of the transport worker shutdo"...
0x14007b84d  mov     dword ptr [rbp+arg_0], 74h ; 't'
0x14007b854  mov     [rbp+arg_10], rax
0x14007b858  lea     rdx, byte_14013F8A1
0x14007b85f  lea     rax, aTerminate; "Terminate"
0x14007b866  mov     [rbp+arg_8], ecx
0x14007b869  mov     [rbp+arg_18], rax
0x14007b86d  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14007b874  mov     [rbp+var_10], rax
0x14007b878  lea     rax, aErrorCondition; "Error condition failed"
0x14007b87f  mov     [rbp+var_18], rax
0x14007b883  lea     rax, [rbp+arg_10]
0x14007b887  mov     [rsp+68h+var_20], rax
0x14007b88c  lea     rax, [rbp+arg_18]
0x14007b890  mov     [rsp+68h+var_28], rax
0x14007b895  lea     rax, [rbp+arg_0]
0x14007b899  mov     [rsp+68h+var_30], rax
0x14007b89e  lea     rax, [rbp+var_10]
0x14007b8a2  mov     [rsp+68h+var_38], rax
0x14007b8a7  lea     rax, [rbp+arg_8]
0x14007b8ab  mov     [rsp+68h+lpThreadId], rax
0x14007b8b0  lea     rax, [rbp+var_18]
0x14007b8b4  jmp     loc_14007B7CE
0x14007b8b9  mov     rcx, rax; hObject
0x14007b8bc  call    cs:__imp_CloseHandle
0x14007b8c2  xor     edi, edi
0x14007b8c4  mov     [rbx+38h], rdi
0x14007b8c8  or      dword ptr [rbx+14h], 4
0x14007b8cc  mov     eax, cs:dword_140150118
0x14007b8d2  cmp     eax, 4
0x14007b8d5  jbe     short loc_14007B8FE
0x14007b8d7  lea     rax, aCnamedpipestre_0; "CNamedPipeStream terminated"
0x14007b8de  mov     [rbp+arg_0], rax
0x14007b8e2  lea     rdx, byte_14013F87F
0x14007b8e9  lea     rax, [rbp+arg_0]
0x14007b8ed  lea     rcx, dword_140150118
0x14007b8f4  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x14007b8f9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14007b8fe  test    rdi, rdi
0x14007b901  jz      short loc_14007B90B
0x14007b903  mov     rcx, rdi; Block
0x14007b906  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007b90b  mov     rcx, [rbx+38h]; hLibModule
0x14007b90f  test    rcx, rcx
0x14007b912  jz      short loc_14007B922
0x14007b914  call    cs:__imp_FreeLibrary
0x14007b91a  mov     qword ptr [rbx+38h], 0
0x14007b922  xor     eax, eax
0x14007b924  add     rsp, 68h
0x14007b928  pop     rdi
0x14007b929  pop     rsi
0x14007b92a  pop     rbx
0x14007b92b  pop     rbp
0x14007b92c  retn
```
