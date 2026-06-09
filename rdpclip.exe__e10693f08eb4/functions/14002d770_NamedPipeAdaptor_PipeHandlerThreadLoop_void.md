# NamedPipeAdaptor::PipeHandlerThreadLoop(void)

- ea: `0x14002d770`
- end: `0x14002db81`
- name: `?PipeHandlerThreadLoop@NamedPipeAdaptor@@AEAAJXZ`
- size: `1041`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001e1c`
- `0x140008168`
- `0x140008188`
- `0x140010d18`
- `0x14002b7bc`
- `0x14002c3c4`
- `0x14002c470`
- `0x14002c544`
- `0x14002c670`
- `0x14002c984`
- `0x14002cc10`
- `0x14002cef0`
- `0x14002d304`
- `0x14002d534`
- `0x14002d770`
- `0x14002dca4`
- `0x14002dd04`
- `0x14002df68`
- `0x14002e020`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d8c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d8c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002d8b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002d8b4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeClientProcessId` at `0x14002d84d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeClientProcessId` at `0x14002d84d`

## string_xrefs

- `0x14002d7a8`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d85b`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d882`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002db52`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::PipeHandlerThreadLoop(NamedPipeAdaptor *this)
{
  int v2; // eax
  wil::details *v3; // rcx
  void *v4; // rdx
  int LastError; // ebx
  __int64 v6; // rdx
  void *v8; // rdx
  void *v9; // rcx
  const char *v10; // r9
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  int Pipe; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  wil::details *v22; // rcx
  void *v23; // rdx
  int v24; // [rsp+20h] [rbp-30h]
  char *v25; // [rsp+28h] [rbp-28h]
  __m128i si128; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  ULONG ClientProcessId; // [rsp+70h] [rbp+20h] BYREF
  const unsigned __int16 *ModeName; // [rsp+78h] [rbp+28h] BYREF
  const unsigned __int16 *v31; // [rsp+80h] [rbp+30h] BYREF
  __int64 v32; // [rsp+88h] [rbp+38h] BYREF

  v2 = NamedPipeAdaptor::InitializePipe(this);
  v3 = (wil::details *)*((_QWORD *)this + 45);
  *((_DWORD *)this + 92) = v2;
  wil::details::SetEvent(v3, v4);
  LastError = *((_DWORD *)this + 92);
  if ( LastError < 0 )
  {
    v6 = 225;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)(unsigned int)LastError,
      v24);
    return (unsigned int)LastError;
  }
  LastError = NamedPipeAdaptor::WaitForEvent(this, (char *)this + 376, 0xFFFFFFFFLL);
  if ( LastError < 0 )
  {
    v6 = 227;
    goto LABEL_3;
  }
  if ( !NamedPipeAdaptor::IsTerminating(this) )
  {
    *((_DWORD *)this + 98) = NamedPipeAdaptor::OpenPipeInternal(this);
    if ( !NamedPipeAdaptor::IsTerminating(this) )
    {
      wil::details::SetEvent(*((wil::details **)this + 48), v8);
      LastError = *((_DWORD *)this + 98);
      if ( LastError < 0 )
      {
        v6 = 233;
        goto LABEL_3;
      }
      if ( *((_DWORD *)this + 16) == 1 && *((_DWORD *)this + 36) )
      {
        v9 = (void *)*((_QWORD *)this + 25);
        ClientProcessId = 0;
        if ( !GetNamedPipeClientProcessId(v9, &ClientProcessId) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xF0,
                        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
                        v10);
LABEL_49:
          NamedPipeAdaptor::ClosePipe(this);
          return (unsigned int)LastError;
        }
        if ( *((_DWORD *)this + 36) != ClientProcessId )
        {
          LODWORD(v25) = ClientProcessId;
          LastError = -2147024891;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xF2,
            (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
            (const char *)0x80070005LL,
            (int)"Received connection from unexpected process %d",
            v25);
          goto LABEL_49;
        }
      }
      AcquireSRWLockExclusive((PSRWLOCK)this + 7);
      *((_DWORD *)this + 48) = 3;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 8LL))(
        *((_QWORD *)this + 43),
        *((unsigned __int16 *)this + 68));
      if ( (unsigned int)dword_140088090 > 5 )
      {
        ModeName = NamedPipeAdaptor::GetModeName(this);
        v31 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v11,
          (unsigned int)&word_14007FE6E,
          v12,
          v13,
          (__int64)&v31,
          (__int64)&ModeName);
      }
      v14 = (const unsigned __int16 *)*((_QWORD *)this + 53);
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      ModeName = v14;
      v27 = -1;
      if ( (unsigned __int8)utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(&si128, &ModeName) )
      {
        ModeName = (const unsigned __int16 *)*((_QWORD *)this + 50);
        if ( (unsigned __int8)utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(&si128, &ModeName) )
        {
          ModeName = (const unsigned __int16 *)*((_QWORD *)this + 33);
          if ( (unsigned __int8)utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(&si128, &ModeName) )
          {
            ModeName = (const unsigned __int16 *)*((_QWORD *)this + 41);
            if ( (unsigned __int8)utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(&si128, &ModeName) )
            {
              Pipe = NamedPipeAdaptor::BeginReadPipe(this);
              LastError = Pipe;
              if ( Pipe >= 0 )
              {
                while ( 1 )
                {
                  if ( NamedPipeAdaptor::IsTerminating(this) )
                  {
                    utl::vector<void *,utl::allocator<void *>>::_Uninit(&si128);
                    NamedPipeAdaptor::ClosePipe(this);
                    return 0;
                  }
                  LODWORD(ModeName) = 0;
                  Pipe = NamedPipeAdaptor::WaitInternal(this, &si128, 0xFFFFFFFFLL, &ModeName);
                  LastError = Pipe;
                  if ( Pipe < 0 )
                    break;
                  switch ( (_DWORD)ModeName )
                  {
                    case 1:
                      Pipe = NamedPipeAdaptor::BeginWritePipe(this);
                      LastError = Pipe;
                      if ( Pipe < 0 )
                      {
                        v15 = 270;
                        goto LABEL_47;
                      }
                      break;
                    case 2:
                      Pipe = NamedPipeAdaptor::CompleteReadPipe(this);
                      LastError = Pipe;
                      if ( Pipe < 0 )
                      {
                        v15 = 274;
                        goto LABEL_47;
                      }
                      if ( !NamedPipeAdaptor::IsTerminating(this) )
                      {
                        Pipe = NamedPipeAdaptor::BeginReadPipe(this);
                        LastError = Pipe;
                        if ( Pipe < 0 )
                        {
                          v15 = 277;
                          goto LABEL_47;
                        }
                      }
                      break;
                    case 3:
                      v21 = NamedPipeAdaptor::CompleteWritePipe(this);
                      v22 = (wil::details *)*((_QWORD *)this + 51);
                      *((_DWORD *)this + 104) = v21;
                      wil::details::SetEvent(v22, v23);
                      LastError = *((_DWORD *)this + 104);
                      if ( LastError < 0 )
                      {
                        v16 = (unsigned int)LastError;
                        v15 = 284;
                        goto LABEL_48;
                      }
                      break;
                    default:
                      if ( (unsigned int)dword_140088090 > 5 )
                      {
                        v31 = NamedPipeAdaptor::GetModeName(this);
                        v32 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                          v18,
                          (unsigned int)byte_14007FE39,
                          v19,
                          v20,
                          (__int64)&v32,
                          (__int64)&v31);
                      }
                      break;
                  }
                }
                v15 = 266;
              }
              else
              {
                v15 = 262;
              }
LABEL_47:
              v16 = (unsigned int)Pipe;
            }
            else
            {
              LastError = -2147024882;
              v15 = 260;
              v16 = 2147942414LL;
            }
          }
          else
          {
            LastError = -2147024882;
            v15 = 259;
            v16 = 2147942414LL;
          }
        }
        else
        {
          LastError = -2147024882;
          v15 = 258;
          v16 = 2147942414LL;
        }
      }
      else
      {
        LastError = -2147024882;
        v15 = 257;
        v16 = 2147942414LL;
      }
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)v16,
        v24);
      utl::vector<void *,utl::allocator<void *>>::_Uninit(&si128);
      goto LABEL_49;
    }
  }
  return 2147500036LL;
}

```

## disassembly

```asm
0x14002d770  push    rbp
0x14002d772  push    rbx
0x14002d773  push    rdi
0x14002d774  mov     rbp, rsp
0x14002d777  sub     rsp, 50h
0x14002d77b  mov     rdi, rcx
0x14002d77e  call    ?InitializePipe@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::InitializePipe(void)
0x14002d783  mov     rcx, [rdi+168h]; this
0x14002d78a  mov     [rdi+170h], eax
0x14002d790  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14002d795  mov     ebx, [rdi+170h]
0x14002d79b  test    ebx, ebx
0x14002d79d  jns     short loc_14002D7BE
0x14002d79f  mov     edx, 0E1h; void *
0x14002d7a4  mov     rcx, [rbp+18h]; this
0x14002d7a8  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d7af  mov     r9d, ebx; char *
0x14002d7b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d7b7  mov     eax, ebx
0x14002d7b9  jmp     loc_14002DB79
0x14002d7be  lea     rdx, [rdi+178h]
0x14002d7c5  or      r8d, 0FFFFFFFFh
0x14002d7c9  mov     rcx, rdi
0x14002d7cc  call    ?WaitForEvent@NamedPipeAdaptor@@AEAAJAEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@K@Z
0x14002d7d1  mov     ebx, eax
0x14002d7d3  test    eax, eax
0x14002d7d5  jns     short loc_14002D7DE
0x14002d7d7  mov     edx, 0E3h
0x14002d7dc  jmp     short loc_14002D7A4
0x14002d7de  mov     rcx, rdi; this
0x14002d7e1  call    ?IsTerminating@NamedPipeAdaptor@@AEAA_NXZ; NamedPipeAdaptor::IsTerminating(void)
0x14002d7e6  test    al, al
0x14002d7e8  jnz     loc_14002DB74
0x14002d7ee  mov     rcx, rdi; this
0x14002d7f1  call    ?OpenPipeInternal@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::OpenPipeInternal(void)
0x14002d7f6  mov     rcx, rdi; this
0x14002d7f9  mov     [rdi+188h], eax
0x14002d7ff  call    ?IsTerminating@NamedPipeAdaptor@@AEAA_NXZ; NamedPipeAdaptor::IsTerminating(void)
0x14002d804  test    al, al
0x14002d806  jnz     loc_14002DB74
0x14002d80c  mov     rcx, [rdi+180h]; this
0x14002d813  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14002d818  mov     ebx, [rdi+188h]
0x14002d81e  test    ebx, ebx
0x14002d820  jns     short loc_14002D82C
0x14002d822  mov     edx, 0E9h
0x14002d827  jmp     loc_14002D7A4
0x14002d82c  cmp     dword ptr [rdi+40h], 1
0x14002d830  jnz     short loc_14002D8B0
0x14002d832  cmp     dword ptr [rdi+90h], 0
0x14002d839  jz      short loc_14002D8B0
0x14002d83b  mov     rcx, [rdi+0C8h]; Pipe
0x14002d842  lea     rdx, [rbp+ClientProcessId]; ClientProcessId
0x14002d846  mov     [rbp+ClientProcessId], 0
0x14002d84d  call    cs:__imp_GetNamedPipeClientProcessId
0x14002d853  test    eax, eax
0x14002d855  jnz     short loc_14002D873
0x14002d857  mov     rcx, [rbp+18h]; this
0x14002d85b  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d862  mov     edx, 0F0h; void *
0x14002d867  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002d86c  mov     ebx, eax
0x14002d86e  jmp     loc_14002DB67
0x14002d873  mov     eax, [rbp+ClientProcessId]
0x14002d876  cmp     [rdi+90h], eax
0x14002d87c  jz      short loc_14002D8B0
0x14002d87e  mov     rcx, [rbp+18h]; this
0x14002d882  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d889  mov     dword ptr [rsp+50h+var_28], eax; char *
0x14002d88d  mov     ebx, 80070005h
0x14002d892  lea     rax, aReceivedConnec; "Received connection from unexpected pro"...
0x14002d899  mov     r9d, ebx; char *
0x14002d89c  mov     edx, 0F2h; void *
0x14002d8a1  mov     qword ptr [rsp+50h+var_30], rax; int
0x14002d8a6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14002d8ab  jmp     loc_14002DB67
0x14002d8b0  lea     rcx, [rdi+38h]; SRWLock
0x14002d8b4  call    cs:__imp_AcquireSRWLockExclusive
0x14002d8ba  lea     rcx, [rdi+38h]; SRWLock
0x14002d8be  mov     dword ptr [rdi+0C0h], 3
0x14002d8c8  call    cs:__imp_ReleaseSRWLockExclusive
0x14002d8ce  mov     rcx, [rdi+158h]
0x14002d8d5  movzx   edx, word ptr [rdi+88h]
0x14002d8dc  mov     rax, [rcx]
0x14002d8df  mov     rax, [rax+8]
0x14002d8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d8e8  mov     eax, cs:dword_140088090
0x14002d8ee  cmp     eax, 5
0x14002d8f1  jbe     short loc_14002D931
0x14002d8f3  mov     rcx, rdi; this
0x14002d8f6  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002d8fb  mov     [rbp+arg_8], rax
0x14002d8ff  lea     rcx, [rdi+30h]
0x14002d903  mov     rax, [rcx]
0x14002d906  mov     rax, [rax+30h]
0x14002d90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d90f  mov     [rbp+arg_10], rax
0x14002d913  lea     rdx, word_14007FE6E
0x14002d91a  lea     rax, [rbp+arg_8]
0x14002d91e  mov     [rsp+50h+var_28], rax
0x14002d923  lea     rax, [rbp+arg_10]
0x14002d927  mov     qword ptr [rsp+50h+var_30], rax
0x14002d92c  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002d931  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14002d939  lea     rdx, [rbp+arg_8]
0x14002d93d  mov     rax, [rdi+1A8h]
0x14002d944  lea     rcx, [rbp+var_20]
0x14002d948  movdqu  [rbp+var_20], xmm0
0x14002d94d  mov     [rbp+arg_8], rax
0x14002d951  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x14002d959  call    ??$_PushBackOne@PEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_N$$QEAPEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(void * &&)
0x14002d95e  test    al, al
0x14002d960  jnz     short loc_14002D974
0x14002d962  mov     ebx, 8007000Eh
0x14002d967  mov     edx, 101h
0x14002d96c  mov     r9d, ebx
0x14002d96f  jmp     loc_14002DB4E
0x14002d974  mov     rax, [rdi+190h]
0x14002d97b  lea     rdx, [rbp+arg_8]
0x14002d97f  lea     rcx, [rbp+var_20]
0x14002d983  mov     [rbp+arg_8], rax
0x14002d987  call    ??$_PushBackOne@PEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_N$$QEAPEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(void * &&)
0x14002d98c  test    al, al
0x14002d98e  jnz     short loc_14002D9A2
0x14002d990  mov     ebx, 8007000Eh
0x14002d995  mov     edx, 102h
0x14002d99a  mov     r9d, ebx
0x14002d99d  jmp     loc_14002DB4E
0x14002d9a2  mov     rax, [rdi+108h]
0x14002d9a9  lea     rdx, [rbp+arg_8]
0x14002d9ad  lea     rcx, [rbp+var_20]
0x14002d9b1  mov     [rbp+arg_8], rax
0x14002d9b5  call    ??$_PushBackOne@PEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_N$$QEAPEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(void * &&)
0x14002d9ba  test    al, al
0x14002d9bc  jnz     short loc_14002D9D0
0x14002d9be  mov     ebx, 8007000Eh
0x14002d9c3  mov     edx, 103h
0x14002d9c8  mov     r9d, ebx
0x14002d9cb  jmp     loc_14002DB4E
0x14002d9d0  mov     rax, [rdi+148h]
0x14002d9d7  lea     rdx, [rbp+arg_8]
0x14002d9db  lea     rcx, [rbp+var_20]
0x14002d9df  mov     [rbp+arg_8], rax
0x14002d9e3  call    ??$_PushBackOne@PEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_N$$QEAPEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne<void *>(void * &&)
0x14002d9e8  test    al, al
0x14002d9ea  jnz     short loc_14002D9FE
0x14002d9ec  mov     ebx, 8007000Eh
0x14002d9f1  mov     edx, 104h
0x14002d9f6  mov     r9d, ebx
0x14002d9f9  jmp     loc_14002DB4E
0x14002d9fe  mov     rcx, rdi; this
0x14002da01  call    ?BeginReadPipe@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::BeginReadPipe(void)
0x14002da06  mov     ebx, eax
0x14002da08  test    eax, eax
0x14002da0a  jns     loc_14002DB13
0x14002da10  mov     edx, 106h
0x14002da15  jmp     loc_14002DB4B
0x14002da1a  lea     r9, [rbp+arg_8]
0x14002da1e  mov     dword ptr [rbp+arg_8], 0
0x14002da25  or      r8d, 0FFFFFFFFh
0x14002da29  lea     rdx, [rbp+var_20]
0x14002da2d  mov     rcx, rdi
0x14002da30  call    ?WaitInternal@NamedPipeAdaptor@@AEAAJAEBV?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@KAEAI@Z; NamedPipeAdaptor::WaitInternal(utl::vector<void *,utl::allocator<void *>> const &,ulong,uint &)
0x14002da35  mov     ebx, eax
0x14002da37  test    eax, eax
0x14002da39  js      loc_14002DB46
0x14002da3f  mov     eax, dword ptr [rbp+arg_8]
0x14002da42  sub     eax, 1
0x14002da45  jz      loc_14002DB05
0x14002da4b  sub     eax, 1
0x14002da4e  jz      loc_14002DAD6
0x14002da54  cmp     eax, 1
0x14002da57  jz      short loc_14002DAA8
0x14002da59  mov     eax, cs:dword_140088090
0x14002da5f  cmp     eax, 5
0x14002da62  jbe     loc_14002DB13
0x14002da68  mov     rcx, rdi; this
0x14002da6b  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002da70  mov     [rbp+arg_10], rax
0x14002da74  lea     rcx, [rdi+30h]
0x14002da78  mov     rax, [rcx]
0x14002da7b  mov     rax, [rax+30h]
0x14002da7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002da84  mov     [rbp+arg_18], rax
0x14002da88  lea     rdx, byte_14007FE39
0x14002da8f  lea     rax, [rbp+arg_10]
0x14002da93  mov     [rsp+50h+var_28], rax
0x14002da98  lea     rax, [rbp+arg_18]
0x14002da9c  mov     qword ptr [rsp+50h+var_30], rax
0x14002daa1  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002daa6  jmp     short loc_14002DB13
0x14002daa8  mov     rcx, rdi; this
0x14002daab  call    ?CompleteWritePipe@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::CompleteWritePipe(void)
0x14002dab0  mov     rcx, [rdi+198h]; this
0x14002dab7  mov     [rdi+1A0h], eax
0x14002dabd  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14002dac2  mov     ebx, [rdi+1A0h]
0x14002dac8  test    ebx, ebx
0x14002daca  jns     short loc_14002DB13
0x14002dacc  mov     r9d, ebx
0x14002dacf  mov     edx, 11Ch
0x14002dad4  jmp     short loc_14002DB4E
0x14002dad6  mov     rcx, rdi; this
0x14002dad9  call    ?CompleteReadPipe@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::CompleteReadPipe(void)
0x14002dade  mov     ebx, eax
0x14002dae0  test    eax, eax
0x14002dae2  js      short loc_14002DB38
0x14002dae4  mov     rcx, rdi; this
0x14002dae7  call    ?IsTerminating@NamedPipeAdaptor@@AEAA_NXZ; NamedPipeAdaptor::IsTerminating(void)
0x14002daec  test    al, al
0x14002daee  jnz     short loc_14002DB13
0x14002daf0  mov     rcx, rdi; this
0x14002daf3  call    ?BeginReadPipe@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::BeginReadPipe(void)
0x14002daf8  mov     ebx, eax
0x14002dafa  test    eax, eax
0x14002dafc  jns     short loc_14002DB13
0x14002dafe  mov     edx, 115h
0x14002db03  jmp     short loc_14002DB4B
0x14002db05  mov     rcx, rdi; this
0x14002db08  call    ?BeginWritePipe@NamedPipeAdaptor@@AEAAJXZ; NamedPipeAdaptor::BeginWritePipe(void)
0x14002db0d  mov     ebx, eax
0x14002db0f  test    eax, eax
0x14002db11  js      short loc_14002DB3F
0x14002db13  mov     rcx, rdi; this
0x14002db16  call    ?IsTerminating@NamedPipeAdaptor@@AEAA_NXZ; NamedPipeAdaptor::IsTerminating(void)
0x14002db1b  test    al, al
0x14002db1d  jz      loc_14002DA1A
0x14002db23  lea     rcx, [rbp+var_20]
0x14002db27  call    ?_Uninit@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAAXXZ; utl::vector<void *,utl::allocator<void *>>::_Uninit(void)
0x14002db2c  mov     rcx, rdi; this
0x14002db2f  call    ?ClosePipe@NamedPipeAdaptor@@AEAAXXZ; NamedPipeAdaptor::ClosePipe(void)
0x14002db34  xor     eax, eax
0x14002db36  jmp     short loc_14002DB79
0x14002db38  mov     edx, 112h
0x14002db3d  jmp     short loc_14002DB4B
0x14002db3f  mov     edx, 10Eh
0x14002db44  jmp     short loc_14002DB4B
0x14002db46  mov     edx, 10Ah; void *
0x14002db4b  mov     r9d, eax; char *
0x14002db4e  mov     rcx, [rbp+18h]; this
0x14002db52  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002db59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002db5e  lea     rcx, [rbp+var_20]
0x14002db62  call    ?_Uninit@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAAXXZ; utl::vector<void *,utl::allocator<void *>>::_Uninit(void)
0x14002db67  mov     rcx, rdi; this
0x14002db6a  call    ?ClosePipe@NamedPipeAdaptor@@AEAAXXZ; NamedPipeAdaptor::ClosePipe(void)
0x14002db6f  jmp     loc_14002D7B7
0x14002db74  mov     eax, 80004004h
0x14002db79  add     rsp, 50h
0x14002db7d  pop     rdi
0x14002db7e  pop     rbx
0x14002db7f  pop     rbp
0x14002db80  retn
```
