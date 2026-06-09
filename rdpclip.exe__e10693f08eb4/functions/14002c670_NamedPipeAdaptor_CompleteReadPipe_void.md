# NamedPipeAdaptor::CompleteReadPipe(void)

- ea: `0x14002c670`
- end: `0x14002c97d`
- name: `?CompleteReadPipe@NamedPipeAdaptor@@AEAAJXZ`
- size: `781`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14002d770`

## callees

- `0x140002110`
- `0x140002204`
- `0x140002d6c`
- `0x140002d9d`
- `0x140008168`
- `0x140008188`
- `0x14002b864`
- `0x14002c014`
- `0x14002c2e0`
- `0x14002c670`
- `0x14002cc10`
- `0x14002dc20`
- `0x14002dca4`
- `0x14006b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14002c871`
- `msvcrt!memcpy_s` at `0x14002c871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c6aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002c709`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002c709`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002c6f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002c6f5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14002c6a0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14002c6a0`

## string_xrefs

- `0x14002c6e0`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002c7f7`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002c884`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::CompleteReadPipe(NamedPipeAdaptor *this)
{
  OverlappedState *v1; // r14
  DWORD LastError; // eax
  const char *v4; // r9
  __int64 v5; // rdx
  char v6; // al
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  _QWORD *v11; // rcx
  __int64 v12; // rsi
  _QWORD *v13; // rax
  __int64 v14; // rdx
  bool v15; // bl
  __int64 v16; // rdx
  unsigned int v17; // ebx
  DWORD v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  _QWORD *v22; // r8
  __int64 *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rax
  int v27; // [rsp+20h] [rbp-30h]
  char *v28; // [rsp+28h] [rbp-28h]
  int v29[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  _QWORD *v31; // [rsp+80h] [rbp+30h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+88h] [rbp+38h] BYREF
  const unsigned __int16 *v33; // [rsp+90h] [rbp+40h] BYREF
  const unsigned __int16 *ModeName; // [rsp+98h] [rbp+48h] BYREF

  v1 = (NamedPipeAdaptor *)((char *)this + 208);
  NumberOfBytesTransferred = 0;
  if ( GetOverlappedResult(*((HANDLE *)this + 25), (LPOVERLAPPED)((char *)this + 208), &NumberOfBytesTransferred, 0) )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 233 || LastError == 109 )
    {
      if ( *((_BYTE *)this + 336) )
      {
        v5 = 442;
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)v5,
                 (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
                 v4);
      }
      AcquireSRWLockExclusive((PSRWLOCK)this + 7);
      *((_DWORD *)this + 48) = 4;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
      return 0;
    }
    if ( LastError != 234 )
    {
      v5 = 447;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
               v4);
    }
    v6 = 1;
  }
  *((_BYTE *)this + 336) = v6;
  if ( (unsigned int)dword_140088090 > 5 )
  {
    LOBYTE(v31) = *((_BYTE *)this + 336);
    LODWORD(v33) = NumberOfBytesTransferred;
    ModeName = NamedPipeAdaptor::GetModeName(this);
    *(_QWORD *)v29 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v8,
      (unsigned int)byte_14007FD33,
      v9,
      v10,
      (__int64)v29,
      (__int64)&ModeName,
      (__int64)&v33,
      (__int64)&v31);
  }
  v11 = (_QWORD *)*((_QWORD *)this + 44);
  v12 = 0;
  if ( !v11 )
  {
    v13 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v13 )
    {
      *v13 = -1;
      v13[1] = -1;
      v13[2] = -1;
    }
    v14 = *((_QWORD *)this + 44);
    v31 = 0;
    *((_QWORD *)this + 44) = v13;
    if ( v14 )
      utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>::operator()();
    v15 = *((_QWORD *)this + 44) == 0;
    utl::unique_ptr<utl::vector<unsigned char,utl::allocator<unsigned char>>,utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>>::~unique_ptr<utl::vector<unsigned char,utl::allocator<unsigned char>>,utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>>(&v31);
    if ( v15 )
    {
      v16 = 466;
LABEL_21:
      v17 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)0x8007000ELL,
        v27);
      return v17;
    }
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(
                             *((_QWORD *)this + 44),
                             NumberOfBytesTransferred) )
    {
      v16 = 467;
      goto LABEL_21;
    }
    goto LABEL_28;
  }
  v18 = NumberOfBytesTransferred;
  if ( NumberOfBytesTransferred )
  {
    v12 = v11[1] - *v11;
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(
                             v11,
                             v12 + NumberOfBytesTransferred) )
    {
      v16 = 472;
      goto LABEL_21;
    }
LABEL_28:
    v18 = NumberOfBytesTransferred;
  }
  if ( memcpy_s(
         (void *const)(v12 + **((_QWORD **)this + 44)),
         *(_QWORD *)(*((_QWORD *)this + 44) + 8LL) - **((_QWORD **)this + 44) - v12,
         *((const void *const *)this + 30),
         v18) )
  {
    v17 = -2147418113;
    LODWORD(v28) = *errno_0();
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)0x8000FFFFLL,
      (int)"memcpy_s failed (%d)",
      v28);
    return v17;
  }
  if ( !*((_BYTE *)this + 336) )
  {
    if ( (unsigned int)dword_140088090 > 5 )
    {
      v31 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 44) + 8LL) - **((_QWORD **)this + 44));
      v33 = NamedPipeAdaptor::GetModeName(this);
      ModeName = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v19,
        (unsigned int)&unk_14007FCF0,
        v20,
        v21,
        (__int64)&ModeName,
        (__int64)&v33,
        (__int64)&v31);
    }
    v22 = (_QWORD *)*((_QWORD *)this + 44);
    v23 = (__int64 *)*((_QWORD *)this + 43);
    v24 = *((unsigned __int16 *)this + 68);
    *((_QWORD *)this + 44) = 0;
    v25 = *v22;
    v26 = *v23;
    v31 = v22;
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v26 + 24))(v23, v24, v22[1] - v25);
    utl::unique_ptr<utl::vector<unsigned char,utl::allocator<unsigned char>>,utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>>::~unique_ptr<utl::vector<unsigned char,utl::allocator<unsigned char>>,utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>>(&v31);
  }
  OverlappedState::Reset(v1);
  return 0;
}

```

## disassembly

```asm
0x14002c670  push    rbp
0x14002c672  push    rbx
0x14002c673  push    rsi
0x14002c674  push    rdi
0x14002c675  push    r14
0x14002c677  mov     rbp, rsp
0x14002c67a  sub     rsp, 50h
0x14002c67e  lea     r14, [rcx+0D0h]
0x14002c685  mov     [rbp+NumberOfBytesTransferred], 0
0x14002c68c  mov     rdi, rcx
0x14002c68f  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14002c693  mov     rcx, [rcx+0C8h]; hFile
0x14002c69a  mov     rdx, r14; lpOverlapped
0x14002c69d  xor     r9d, r9d; bWait
0x14002c6a0  call    cs:__imp_GetOverlappedResult
0x14002c6a6  test    eax, eax
0x14002c6a8  jnz     short loc_14002C714
0x14002c6aa  call    cs:__imp_GetLastError
0x14002c6b0  cmp     eax, 0E9h
0x14002c6b5  jz      short loc_14002C6CE
0x14002c6b7  cmp     eax, 6Dh ; 'm'
0x14002c6ba  jz      short loc_14002C6CE
0x14002c6bc  cmp     eax, 0EAh
0x14002c6c1  jz      short loc_14002C6CA
0x14002c6c3  mov     edx, 1BFh
0x14002c6c8  jmp     short loc_14002C6DC
0x14002c6ca  mov     al, 1
0x14002c6cc  jmp     short loc_14002C716
0x14002c6ce  cmp     byte ptr [rdi+150h], 0
0x14002c6d5  jz      short loc_14002C6F1
0x14002c6d7  mov     edx, 1BAh; void *
0x14002c6dc  mov     rcx, [rbp+28h]; this
0x14002c6e0  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002c6e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002c6ec  jmp     loc_14002C972
0x14002c6f1  lea     rcx, [rdi+38h]; SRWLock
0x14002c6f5  call    cs:__imp_AcquireSRWLockExclusive
0x14002c6fb  lea     rcx, [rdi+38h]; SRWLock
0x14002c6ff  mov     dword ptr [rdi+0C0h], 4
0x14002c709  call    cs:__imp_ReleaseSRWLockExclusive
0x14002c70f  jmp     loc_14002C970
0x14002c714  xor     al, al
0x14002c716  mov     [rdi+150h], al
0x14002c71c  mov     eax, cs:dword_140088090
0x14002c722  cmp     eax, 5
0x14002c725  jbe     short loc_14002C786
0x14002c727  mov     al, [rdi+150h]
0x14002c72d  mov     rcx, rdi; this
0x14002c730  mov     byte ptr [rbp+arg_0], al
0x14002c733  mov     eax, [rbp+NumberOfBytesTransferred]
0x14002c736  mov     dword ptr [rbp+arg_10], eax
0x14002c739  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002c73e  mov     [rbp+arg_18], rax
0x14002c742  lea     rcx, [rdi+30h]
0x14002c746  mov     rax, [rcx]
0x14002c749  mov     rax, [rax+30h]
0x14002c74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c752  mov     qword ptr [rbp+var_10], rax
0x14002c756  lea     rdx, byte_14007FD33
0x14002c75d  lea     rax, [rbp+arg_0]
0x14002c761  mov     [rsp+50h+var_18], rax
0x14002c766  lea     rax, [rbp+arg_10]
0x14002c76a  mov     [rsp+50h+var_20], rax
0x14002c76f  lea     rax, [rbp+arg_18]
0x14002c773  mov     [rsp+50h+var_28], rax
0x14002c778  lea     rax, [rbp+var_10]
0x14002c77c  mov     qword ptr [rsp+50h+var_30], rax; int
0x14002c781  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002c786  mov     rcx, [rdi+160h]
0x14002c78d  xor     esi, esi
0x14002c78f  test    rcx, rcx
0x14002c792  jnz     loc_14002C82C
0x14002c798  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002c79f  lea     ecx, [rsi+18h]; unsigned __int64
0x14002c7a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002c7a7  test    rax, rax
0x14002c7aa  jz      short loc_14002C7BB
0x14002c7ac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002c7b0  mov     [rax], rcx
0x14002c7b3  mov     [rax+8], rcx
0x14002c7b7  mov     [rax+10h], rcx
0x14002c7bb  mov     rdx, [rdi+160h]
0x14002c7c2  mov     [rbp+arg_0], rsi
0x14002c7c6  mov     [rdi+160h], rax
0x14002c7cd  test    rdx, rdx
0x14002c7d0  jz      short loc_14002C7D7
0x14002c7d2  call    ??R?$default_delete@V?$vector@EV?$allocator@E@utl@@@utl@@@utl@@QEBAXPEAV?$vector@EV?$allocator@E@utl@@@1@@Z; utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>::operator()(utl::vector<uchar,utl::allocator<uchar>> *)
0x14002c7d7  cmp     [rdi+160h], rsi
0x14002c7de  lea     rcx, [rbp+arg_0]
0x14002c7e2  setz    bl
0x14002c7e5  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@utl@@@utl@@U?$default_delete@V?$vector@EV?$allocator@E@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<uchar,utl::allocator<uchar>>,utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>>::~unique_ptr<utl::vector<uchar,utl::allocator<uchar>>,utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>>(void)
0x14002c7ea  test    bl, bl
0x14002c7ec  jz      short loc_14002C812
0x14002c7ee  mov     edx, 1D2h; void *
0x14002c7f3  mov     rcx, [rbp+28h]; this
0x14002c7f7  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002c7fe  mov     ebx, 8007000Eh
0x14002c803  mov     r9d, ebx; char *
0x14002c806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c80b  mov     eax, ebx
0x14002c80d  jmp     loc_14002C972
0x14002c812  mov     edx, [rbp+NumberOfBytesTransferred]
0x14002c815  mov     rcx, [rdi+160h]
0x14002c81c  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x14002c821  test    al, al
0x14002c823  jnz     short loc_14002C84D
0x14002c825  mov     edx, 1D3h
0x14002c82a  jmp     short loc_14002C7F3
0x14002c82c  mov     edx, [rbp+NumberOfBytesTransferred]
0x14002c82f  test    edx, edx
0x14002c831  jz      short loc_14002C850
0x14002c833  mov     rsi, [rcx+8]
0x14002c837  sub     rsi, [rcx]
0x14002c83a  add     rdx, rsi
0x14002c83d  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x14002c842  test    al, al
0x14002c844  jnz     short loc_14002C84D
0x14002c846  mov     edx, 1D8h
0x14002c84b  jmp     short loc_14002C7F3
0x14002c84d  mov     edx, [rbp+NumberOfBytesTransferred]
0x14002c850  mov     rax, [rdi+160h]
0x14002c857  mov     r8, [rdi+0F0h]; Source
0x14002c85e  mov     r9d, edx; SourceSize
0x14002c861  mov     rcx, [rax]
0x14002c864  mov     rdx, [rax+8]
0x14002c868  sub     rdx, rcx
0x14002c86b  add     rcx, rsi; Destination
0x14002c86e  sub     rdx, rsi; DestinationSize
0x14002c871  call    cs:__imp_memcpy_s
0x14002c877  test    eax, eax
0x14002c879  jz      short loc_14002C8B4
0x14002c87b  call    _errno_0
0x14002c880  mov     rcx, [rbp+28h]; this
0x14002c884  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002c88b  mov     ebx, 8000FFFFh
0x14002c890  mov     edx, 1DCh; void *
0x14002c895  mov     r9d, ebx; char *
0x14002c898  mov     eax, [rax]
0x14002c89a  mov     dword ptr [rsp+50h+var_28], eax; char *
0x14002c89e  lea     rax, aMemcpySFailedD; "memcpy_s failed (%d)"
0x14002c8a5  mov     qword ptr [rsp+50h+var_30], rax; int
0x14002c8aa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14002c8af  jmp     loc_14002C80B
0x14002c8b4  cmp     byte ptr [rdi+150h], 0
0x14002c8bb  jnz     loc_14002C968
0x14002c8c1  mov     eax, cs:dword_140088090
0x14002c8c7  cmp     eax, 5
0x14002c8ca  jbe     short loc_14002C925
0x14002c8cc  mov     rax, [rdi+160h]
0x14002c8d3  mov     rcx, [rax+8]
0x14002c8d7  sub     rcx, [rax]
0x14002c8da  mov     [rbp+arg_0], rcx
0x14002c8de  mov     rcx, rdi; this
0x14002c8e1  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002c8e6  mov     [rbp+arg_10], rax
0x14002c8ea  lea     rcx, [rdi+30h]
0x14002c8ee  mov     rax, [rcx]
0x14002c8f1  mov     rax, [rax+30h]
0x14002c8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8fa  mov     [rbp+arg_18], rax
0x14002c8fe  lea     rdx, unk_14007FCF0
0x14002c905  lea     rax, [rbp+arg_0]
0x14002c909  mov     [rsp+50h+var_20], rax
0x14002c90e  lea     rax, [rbp+arg_10]
0x14002c912  mov     [rsp+50h+var_28], rax
0x14002c917  lea     rax, [rbp+arg_18]
0x14002c91b  mov     qword ptr [rsp+50h+var_30], rax
0x14002c920  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14002c925  mov     r8, [rdi+160h]
0x14002c92c  mov     rcx, [rdi+158h]
0x14002c933  movzx   edx, word ptr [rdi+88h]
0x14002c93a  mov     qword ptr [rdi+160h], 0
0x14002c945  mov     r9, [r8]
0x14002c948  mov     rax, [rcx]
0x14002c94b  mov     [rbp+arg_0], r8
0x14002c94f  mov     r8, [r8+8]
0x14002c953  sub     r8, r9
0x14002c956  mov     rax, [rax+18h]
0x14002c95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c95f  lea     rcx, [rbp+arg_0]
0x14002c963  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@utl@@@utl@@U?$default_delete@V?$vector@EV?$allocator@E@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<uchar,utl::allocator<uchar>>,utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>>::~unique_ptr<utl::vector<uchar,utl::allocator<uchar>>,utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>>(void)
0x14002c968  mov     rcx, r14; this
0x14002c96b  call    ?Reset@OverlappedState@@QEAAXXZ; OverlappedState::Reset(void)
0x14002c970  xor     eax, eax
0x14002c972  add     rsp, 50h
0x14002c976  pop     r14
0x14002c978  pop     rdi
0x14002c979  pop     rsi
0x14002c97a  pop     rbx
0x14002c97b  pop     rbp
0x14002c97c  retn
```
