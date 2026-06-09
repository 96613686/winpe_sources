# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x1800551b0`
- end: `0x1800554f9`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `841`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004be60`
- `0x18004c8a0`
- `0x180050120`

## callees

- `0x18000df90`
- `0x18000e430`
- `0x18000e46c`
- `0x18000ec30`
- `0x1800377f0`
- `0x180037dd0`
- `0x180037f20`
- `0x180038ff0`
- `0x18004fbe0`
- `0x1800551b0`
- `0x1800719ec`
- `0x180081190`
- `0x1800a64d8`
- `0x1800a7ebc`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553c6`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800551f5`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800551f5`
- `WINHTTP!WinHttpReadData` at `0x1800553b8`
- `WINHTTP!WinHttpReadData` at `0x1800553b8`

## string_xrefs

- `0x1800553e2`: `WinHttpReadData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall web::http::client::details::winhttp_client::read_next_response_chunk(
        struct web::http::client::details::winhttp_request_context *this,
        unsigned int a2,
        char a3)
{
  unsigned __int64 v4; // r15
  DWORD LastError; // ebx
  __int64 v7; // rax
  const struct std::nothrow_t *v8; // rdx
  _BYTE *v9; // rcx
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  void *v12; // rsi
  DWORD v13; // ebx
  __int64 v14; // rax
  const struct std::nothrow_t *v15; // rdx
  _BYTE *v16; // rcx
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-48h]
  unsigned __int64 v21; // [rsp+38h] [rbp-40h]
  void *Src; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+48h] [rbp-30h]
  __int64 v24; // [rsp+50h] [rbp-28h]
  unsigned __int64 v25; // [rsp+58h] [rbp-20h]

  v4 = a2;
  if ( !*((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)this
                                                                                         + 1))
        + 53) )
  {
    if ( WinHttpQueryDataAvailable(*((HINTERNET *)this + 13), 0) )
      return;
    LastError = GetLastError();
    pExceptionObject = 0;
    *(_QWORD *)&pExceptionObject = operator new(0x20u);
    v20 = 25;
    v21 = 31;
    strcpy((char *)pExceptionObject, "WinHttpQueryDataAvaliable");
    v7 = web::http::client::details::build_error_msg(&Src);
    web::http::client::details::request_context::report_error(this, LastError, v7);
    if ( v25 > 0xF )
    {
      v8 = (const struct std::nothrow_t *)(v25 + 1);
      if ( v25 + 1 < 0x1000 )
      {
        v9 = Src;
      }
      else
      {
        v9 = (_BYTE *)*((_QWORD *)Src - 1);
        if ( (unsigned __int64)((_BYTE *)Src - v9 - 8) > 0x1F )
          __fastfail(5u);
        v8 = (const struct std::nothrow_t *)(v25 + 40);
      }
      operator delete(v9, v8);
    }
    v24 = 0;
    v25 = 15;
    LOBYTE(Src) = 0;
    goto LABEL_36;
  }
  v10 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)this
                                                                                         + 1))
        + 53);
  if ( !v10 )
    v10 = 0x10000;
  if ( *((_QWORD *)this + 12) )
  {
    if ( *((_QWORD *)this + 34) - *((_QWORD *)this + 32) < v10 )
      std::vector<unsigned char>::reserve((char *)this + 256, v10);
    v12 = (void *)*((_QWORD *)this + 32);
  }
  else
  {
    if ( v4 < v10 && !a3 )
    {
      web::http::client::details::request_context::complete_request(this, *((_QWORD *)this + 8));
      return;
    }
    web::http::client::details::request_context::_get_writebuffer(this, &Src);
    if ( !v23 )
    {
      std::invalid_argument::invalid_argument((std::invalid_argument *)&pExceptionObject, "Invalid streambuf object");
      throw (std::invalid_argument *)&pExceptionObject;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v23 + 224LL))(v23, v10);
    v12 = (void *)v11;
    if ( v11 )
    {
      *((_QWORD *)this + 31) = v10;
      *((_QWORD *)this + 27) = v11;
    }
    else
    {
      if ( v10 > *((_QWORD *)this + 29) - *((_QWORD *)this + 28) )
        std::vector<unsigned char>::resize((char *)this + 224, v10);
      *((_QWORD *)this + 27) = 0;
      v12 = (void *)*((_QWORD *)this + 28);
    }
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(&Src);
  }
  if ( !WinHttpReadData(*((HINTERNET *)this + 13), v12, v10, 0) )
  {
    v13 = GetLastError();
    v20 = 15;
    v21 = 15;
    qmemcpy(&pExceptionObject, "WinHttpReadDat", 14);
    HIWORD(pExceptionObject) = (unsigned __int8)aWinhttpreaddat_0[14];
    v14 = web::http::client::details::build_error_msg(&Src);
    web::http::client::details::request_context::report_error(this, v13, v14);
    if ( v25 > 0xF )
    {
      v15 = (const struct std::nothrow_t *)(v25 + 1);
      if ( v25 + 1 < 0x1000 )
      {
        v16 = Src;
      }
      else
      {
        v16 = (_BYTE *)*((_QWORD *)Src - 1);
        if ( (unsigned __int64)((_BYTE *)Src - v16 - 8) > 0x1F )
          __fastfail(5u);
        v15 = (const struct std::nothrow_t *)(v25 + 40);
      }
      operator delete(v16, v15);
    }
    v24 = 0;
    v25 = 15;
    LOBYTE(Src) = 0;
LABEL_36:
    if ( v21 > 0xF )
    {
      v17 = (const struct std::nothrow_t *)(v21 + 1);
      if ( v21 + 1 < 0x1000 )
      {
        v18 = (void *)pExceptionObject;
      }
      else
      {
        v18 = *(void **)(pExceptionObject - 8);
        if ( (unsigned __int64)(pExceptionObject - (_QWORD)v18 - 8) > 0x1F )
          __fastfail(5u);
        v17 = (const struct std::nothrow_t *)(v21 + 40);
      }
      operator delete(v18, v17);
    }
  }
}

```

## disassembly

```asm
0x1800551b0  push    rbp
0x1800551b2  push    rbx
0x1800551b3  push    rsi
0x1800551b4  push    rdi
0x1800551b5  push    r14
0x1800551b7  push    r15
0x1800551b9  mov     rbp, rsp
0x1800551bc  sub     rsp, 78h
0x1800551c0  mov     rax, cs:__security_cookie
0x1800551c7  xor     rax, rsp
0x1800551ca  mov     [rbp+var_18], rax
0x1800551ce  movzx   esi, r8b
0x1800551d2  mov     r15d, edx
0x1800551d5  mov     rdi, rcx
0x1800551d8  mov     rcx, [rcx+8]; this
0x1800551dc  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800551e1  cmp     qword ptr [rax+1A8h], 0
0x1800551e9  jnz     loc_1800552BF
0x1800551ef  xor     edx, edx; lpdwNumberOfBytesAvailable
0x1800551f1  mov     rcx, [rdi+68h]; hRequest
0x1800551f5  call    cs:__imp_WinHttpQueryDataAvailable
0x1800551fb  test    eax, eax
0x1800551fd  jnz     loc_1800554BF
0x180055203  call    cs:__imp_GetLastError
0x180055209  mov     ebx, eax
0x18005520b  xorps   xmm0, xmm0
0x18005520e  movups  [rbp+pExceptionObject], xmm0
0x180055212  xor     r14d, r14d
0x180055215  mov     ecx, 20h ; ' '; Size
0x18005521a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005521f  mov     qword ptr [rbp+pExceptionObject], rax
0x180055223  mov     [rbp+var_48], 19h
0x18005522b  mov     [rbp+var_40], 1Fh
0x180055233  movups  xmm0, xmmword ptr cs:aWinhttpqueryda_0; "WinHttpQueryDataAvaliable"
0x18005523a  movups  xmmword ptr [rax], xmm0
0x18005523d  movups  xmm1, xmmword ptr cs:aWinhttpqueryda_0+9; "eryDataAvaliable"
0x180055244  movups  xmmword ptr [rax+9], xmm1
0x180055248  mov     [rax+19h], r14b
0x18005524c  lea     r8, [rbp+pExceptionObject]
0x180055250  mov     edx, ebx
0x180055252  lea     rcx, [rbp+Src]; Src
0x180055256  call    web__http__client__details__build_error_msg
0x18005525b  nop
0x18005525c  mov     r8, rax
0x18005525f  mov     edx, ebx
0x180055261  mov     rcx, rdi
0x180055264  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180055269  nop
0x18005526a  mov     rdx, [rbp+var_20]
0x18005526e  cmp     rdx, 0Fh
0x180055272  jbe     short loc_1800552AA
0x180055274  mov     rax, [rbp+Src]
0x180055278  inc     rdx; struct std::nothrow_t *
0x18005527b  cmp     rdx, 1000h
0x180055282  jb      short loc_1800552A2
0x180055284  mov     rcx, [rax-8]
0x180055288  sub     rax, rcx
0x18005528b  sub     rax, 8
0x18005528f  cmp     rax, 1Fh
0x180055293  ja      short loc_18005529B
0x180055295  add     rdx, 27h ; '''
0x180055299  jmp     short loc_1800552A5
0x18005529b  mov     ecx, 5
0x1800552a0  int     29h; Win8: RtlFailFast(ecx)
0x1800552a2  mov     rcx, rax; void *
0x1800552a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800552aa  mov     [rbp+var_28], r14
0x1800552ae  mov     [rbp+var_20], 0Fh
0x1800552b6  mov     byte ptr [rbp+Src], 0
0x1800552ba  jmp     loc_18005547F
0x1800552bf  mov     rcx, [rdi+8]; this
0x1800552c3  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800552c8  mov     rbx, [rax+1A8h]
0x1800552cf  mov     eax, 10000h
0x1800552d4  test    rbx, rbx
0x1800552d7  cmovz   rbx, rax
0x1800552db  xor     r14d, r14d
0x1800552de  cmp     [rdi+60h], r14
0x1800552e2  jnz     loc_180055382
0x1800552e8  cmp     r15, rbx
0x1800552eb  jnb     short loc_180055303
0x1800552ed  test    sil, sil
0x1800552f0  jnz     short loc_180055303
0x1800552f2  mov     rdx, [rdi+40h]; unsigned __int64
0x1800552f6  mov     rcx, rdi; this
0x1800552f9  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800552fe  jmp     loc_1800554BF
0x180055303  lea     rdx, [rbp+Src]
0x180055307  mov     rcx, rdi
0x18005530a  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x18005530f  nop
0x180055310  mov     rcx, [rbp+var_30]
0x180055314  test    rcx, rcx
0x180055317  jz      loc_1800554D8
0x18005531d  mov     rax, [rcx]
0x180055320  mov     rdx, rbx
0x180055323  mov     rax, [rax+0E0h]
0x18005532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005532f  mov     rsi, rax
0x180055332  test    rax, rax
0x180055335  jnz     short loc_180055369
0x180055337  mov     rax, [rdi+0E8h]
0x18005533e  sub     rax, [rdi+0E0h]
0x180055345  cmp     rbx, rax
0x180055348  jbe     short loc_180055359
0x18005534a  mov     rdx, rbx
0x18005534d  lea     rcx, [rdi+0E0h]
0x180055354  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180055359  mov     [rdi+0D8h], r14
0x180055360  mov     rsi, [rdi+0E0h]
0x180055367  jmp     short loc_180055377
0x180055369  mov     [rdi+0F8h], rbx
0x180055370  mov     [rdi+0D8h], rax
0x180055377  lea     rcx, [rbp+Src]
0x18005537b  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x180055380  jmp     short loc_1800553AB
0x180055382  mov     rax, [rdi+110h]
0x180055389  sub     rax, [rdi+100h]
0x180055390  cmp     rax, rbx
0x180055393  jnb     short loc_1800553A4
0x180055395  mov     rdx, rbx
0x180055398  lea     rcx, [rdi+100h]
0x18005539f  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x1800553a4  mov     rsi, [rdi+100h]
0x1800553ab  mov     r8d, ebx; dwNumberOfBytesToRead
0x1800553ae  xor     r9d, r9d; lpdwNumberOfBytesRead
0x1800553b1  mov     rdx, rsi; lpBuffer
0x1800553b4  mov     rcx, [rdi+68h]; hRequest
0x1800553b8  call    cs:__imp_WinHttpReadData
0x1800553be  test    eax, eax
0x1800553c0  jnz     loc_1800554BF
0x1800553c6  call    cs:__imp_GetLastError
0x1800553cc  mov     ebx, eax
0x1800553ce  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x1800553d2  mov     [rbp+var_48], 0Fh
0x1800553da  mov     [rbp+var_40], 0Fh
0x1800553e2  movsd   xmm0, qword ptr cs:aWinhttpreaddat_0; "WinHttpReadData"
0x1800553ea  movsd   qword ptr [rbp+pExceptionObject], xmm0
0x1800553ef  mov     ecx, dword ptr cs:aWinhttpreaddat_0+8; "eadData"
0x1800553f5  mov     dword ptr [rbp+pExceptionObject+8], ecx
0x1800553f8  movzx   ecx, word ptr cs:aWinhttpreaddat_0+0Ch; "ata"
0x1800553ff  mov     word ptr [rbp+pExceptionObject+0Ch], cx
0x180055403  movzx   eax, byte ptr cs:aWinhttpreaddat_0+0Eh; "a"
0x18005540a  mov     byte ptr [rbp+pExceptionObject+0Eh], al
0x18005540d  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x180055411  lea     r8, [rbp+pExceptionObject]
0x180055415  mov     edx, ebx
0x180055417  lea     rcx, [rbp+Src]; Src
0x18005541b  call    web__http__client__details__build_error_msg
0x180055420  nop
0x180055421  mov     r8, rax
0x180055424  mov     edx, ebx
0x180055426  mov     rcx, rdi
0x180055429  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18005542e  nop
0x18005542f  mov     rdx, [rbp+var_20]
0x180055433  cmp     rdx, 0Fh
0x180055437  jbe     short loc_18005546F
0x180055439  mov     rax, [rbp+Src]
0x18005543d  inc     rdx; struct std::nothrow_t *
0x180055440  cmp     rdx, 1000h
0x180055447  jb      short loc_180055467
0x180055449  mov     rcx, [rax-8]
0x18005544d  sub     rax, rcx
0x180055450  sub     rax, 8
0x180055454  cmp     rax, 1Fh
0x180055458  ja      short loc_180055460
0x18005545a  add     rdx, 27h ; '''
0x18005545e  jmp     short loc_18005546A
0x180055460  mov     ecx, 5
0x180055465  int     29h; Win8: RtlFailFast(ecx)
0x180055467  mov     rcx, rax; void *
0x18005546a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005546f  mov     [rbp+var_28], r14
0x180055473  mov     [rbp+var_20], 0Fh
0x18005547b  mov     byte ptr [rbp+Src], 0
0x18005547f  mov     rdx, [rbp+var_40]
0x180055483  cmp     rdx, 0Fh
0x180055487  jbe     short loc_1800554BF
0x180055489  mov     rax, qword ptr [rbp+pExceptionObject]
0x18005548d  inc     rdx; struct std::nothrow_t *
0x180055490  cmp     rdx, 1000h
0x180055497  jb      short loc_1800554B7
0x180055499  mov     rcx, [rax-8]
0x18005549d  sub     rax, rcx
0x1800554a0  sub     rax, 8
0x1800554a4  cmp     rax, 1Fh
0x1800554a8  ja      short loc_1800554B0
0x1800554aa  add     rdx, 27h ; '''
0x1800554ae  jmp     short loc_1800554BA
0x1800554b0  mov     ecx, 5
0x1800554b5  int     29h; Win8: RtlFailFast(ecx)
0x1800554b7  mov     rcx, rax; void *
0x1800554ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800554bf  mov     rcx, [rbp+var_18]
0x1800554c3  xor     rcx, rsp; StackCookie
0x1800554c6  call    __security_check_cookie
0x1800554cb  add     rsp, 78h
0x1800554cf  pop     r15
0x1800554d1  pop     r14
0x1800554d3  pop     rdi
0x1800554d4  pop     rsi
0x1800554d5  pop     rbx
0x1800554d6  pop     rbp
0x1800554d7  retn
0x1800554d8  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x1800554df  lea     rcx, [rbp+pExceptionObject]; this
0x1800554e3  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800554e8  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800554ef  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800554f3  call    _CxxThrowException_0
```
