# RdsDWMDirectUpdateProcessor::Terminate(void)

- ea: `0x1800129e4`
- end: `0x180012b76`
- name: `?Terminate@RdsDWMDirectUpdateProcessor@@IEAAXXZ`
- size: `402`
- prototype: `void __fastcall(RdsDWMDirectUpdateProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180012080`

## callees

- `0x1800010f8`
- `0x180001f98`
- `0x180005f6c`
- `0x18000f068`
- `0x18000f08c`
- `0x180012924`
- `0x1800129e4`
- `0x180019d58`
- `0x18002c010`

## import_xrefs

- `GDI32!D3DKMTVailDisconnect` at `0x180012a8d`
- `GDI32!D3DKMTVailDisconnect` at `0x180012a8d`

## string_xrefs

- `0x180012aca`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800129fd`: `Cleaning up update processor.`

## pseudocode

```c
void __fastcall RdsDWMDirectUpdateProcessor::Terminate(
        RdsDWMDirectUpdateProcessor *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  bool v5; // zf
  int v6; // eax
  unsigned __int16 *v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  const char *v10; // [rsp+50h] [rbp-10h] BYREF
  const char *v11; // [rsp+58h] [rbp-8h] BYREF
  const char *v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF
  int v14; // [rsp+90h] [rbp+30h] BYREF
  const char *v15; // [rsp+98h] [rbp+38h] BYREF

  if ( (unsigned int)dword_180044008 > 5 )
  {
    v12 = "Cleaning up update processor.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)word_18003B5DA,
      a3,
      a4,
      (const unsigned __int16 **)&v12);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8);
  if ( *((_QWORD *)this + 5) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 40);
  }
  if ( *((_QWORD *)this + 6) )
  {
    TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease((char *)this + 48);
    *((_QWORD *)this + 6) = 0;
    TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef((char *)this + 48);
  }
  v5 = *((_DWORD *)this + 42) == 0;
  *((_DWORD *)this + 28) = 1;
  *((_DWORD *)this + 41) = 0;
  if ( !v5 )
  {
    v6 = D3DKMTVailDisconnect();
    v9 = v6 + 0x80000000;
    if ( (int)v9 >= 0 && v6 != -2147483611 )
    {
      v9 = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v12) = v6;
        v15 = "Terminate";
        v14 = v6 | 0x10000000;
        v13 = 451;
        v11 = "D3DKMTVailDisconnect failed! Error: %!STATUS!";
        v10 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (__int64)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp",
          (__int64)byte_18003B58D,
          (__int64)v7,
          v8,
          (const unsigned __int16 **)&v11,
          (__int64)&v14,
          (const unsigned __int16 **)&v10,
          (__int64)&v13,
          (const unsigned __int16 **)&v15,
          (__int64)&v12);
      }
    }
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v12 = "VAIL mode disconnected";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (__int64)&dword_18003B56C,
        (__int64)v7,
        v8,
        (const unsigned __int16 **)&v12);
    }
    RDSDWMDirectTraceLogging::LogVAILModeState(
      (RdsDWMDirectUpdateProcessor *)((char *)this + 92),
      (struct _GUID *)&stru_1800316E8,
      v7);
    *((_DWORD *)this + 42) = 0;
  }
}

```

## disassembly

```asm
0x1800129e4  push    rbp
0x1800129e6  push    rbx
0x1800129e7  push    rdi
0x1800129e8  mov     rbp, rsp
0x1800129eb  sub     rsp, 60h
0x1800129ef  mov     eax, cs:dword_180044008
0x1800129f5  mov     rbx, rcx
0x1800129f8  cmp     eax, 5
0x1800129fb  jbe     short loc_180012A1D
0x1800129fd  lea     rax, aCleaningUpUpda; "Cleaning up update processor."
0x180012a04  mov     [rbp+arg_0], rax
0x180012a08  lea     rdx, word_18003B5DA
0x180012a0f  lea     rax, [rbp+arg_0]
0x180012a13  mov     [rsp+60h+var_40], rax
0x180012a18  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180012a1d  lea     rcx, [rbx+8]
0x180012a21  mov     rax, [rcx]
0x180012a24  mov     rax, [rax+18h]
0x180012a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a2d  lea     rdi, [rbx+28h]
0x180012a31  cmp     qword ptr [rdi], 0
0x180012a35  jz      short loc_180012A4E
0x180012a37  mov     rcx, rdi
0x180012a3a  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180012a3f  mov     rcx, rdi
0x180012a42  mov     qword ptr [rdi], 0
0x180012a49  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180012a4e  lea     rdi, [rbx+30h]
0x180012a52  cmp     qword ptr [rdi], 0
0x180012a56  jz      short loc_180012A6F
0x180012a58  mov     rcx, rdi
0x180012a5b  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x180012a60  mov     rcx, rdi
0x180012a63  mov     qword ptr [rdi], 0
0x180012a6a  call    ?SafeAddRef@?$TCntPtr@VRdpRemoteAppAuxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(void)
0x180012a6f  cmp     dword ptr [rbx+0A8h], 0
0x180012a76  mov     dword ptr [rbx+70h], 1
0x180012a7d  mov     dword ptr [rbx+0A4h], 0
0x180012a87  jz      loc_180012B6E
0x180012a8d  call    cs:__imp_D3DKMTVailDisconnect
0x180012a93  mov     edx, 80000000h
0x180012a98  lea     ecx, [rax+rdx]
0x180012a9b  test    edx, ecx
0x180012a9d  jnz     loc_180012B29
0x180012aa3  cmp     eax, 80000025h
0x180012aa8  jz      short loc_180012B29
0x180012aaa  mov     ecx, cs:dword_180044008
0x180012ab0  cmp     ecx, 2
0x180012ab3  jbe     short loc_180012B29
0x180012ab5  mov     dword ptr [rbp+arg_0], eax
0x180012ab8  lea     rcx, aTerminate; "Terminate"
0x180012abf  bts     eax, 1Ch
0x180012ac3  mov     [rbp+arg_18], rcx
0x180012ac7  mov     [rbp+arg_10], eax
0x180012aca  lea     rcx, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180012ad1  lea     rax, aD3dkmtvaildisc; "D3DKMTVailDisconnect failed! Error: %!S"...
0x180012ad8  mov     [rbp+arg_8], 1C3h
0x180012adf  mov     [rbp+var_8], rax
0x180012ae3  lea     rdx, byte_18003B58D
0x180012aea  lea     rax, [rbp+arg_0]
0x180012aee  mov     [rbp+var_10], rcx
0x180012af2  mov     [rsp+60h+var_18], rax
0x180012af7  lea     rax, [rbp+arg_18]
0x180012afb  mov     [rsp+60h+var_20], rax
0x180012b00  lea     rax, [rbp+arg_8]
0x180012b04  mov     [rsp+60h+var_28], rax
0x180012b09  lea     rax, [rbp+var_10]
0x180012b0d  mov     [rsp+60h+var_30], rax
0x180012b12  lea     rax, [rbp+arg_10]
0x180012b16  mov     [rsp+60h+var_38], rax
0x180012b1b  lea     rax, [rbp+var_8]
0x180012b1f  mov     [rsp+60h+var_40], rax
0x180012b24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180012b29  mov     eax, cs:dword_180044008
0x180012b2f  cmp     eax, 4
0x180012b32  jbe     short loc_180012B54
0x180012b34  lea     rax, aVailModeDiscon; "VAIL mode disconnected"
0x180012b3b  mov     [rbp+arg_0], rax
0x180012b3f  lea     rdx, dword_18003B56C
0x180012b46  lea     rax, [rbp+arg_0]
0x180012b4a  mov     [rsp+60h+var_40], rax
0x180012b4f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180012b54  lea     rcx, [rbx+5Ch]; this
0x180012b58  lea     rdx, stru_1800316E8; struct _GUID *
0x180012b5f  call    ?LogVAILModeState@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAG@Z; RDSDWMDirectTraceLogging::LogVAILModeState(_GUID *,ushort *)
0x180012b64  mov     dword ptr [rbx+0A8h], 0
0x180012b6e  add     rsp, 60h
0x180012b72  pop     rdi
0x180012b73  pop     rbx
0x180012b74  pop     rbp
0x180012b75  retn
```
