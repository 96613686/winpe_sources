# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x1800dcee0`
- end: `0x1800dd229`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `841`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800d4d50`
- `0x1800d5790`
- `0x1800d7f10`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019508`
- `0x180019ff4`
- `0x180020470`
- `0x18004c230`
- `0x1800bcc50`
- `0x1800bd230`
- `0x1800bd380`
- `0x1800be450`
- `0x1800d79d0`
- `0x1800dcee0`
- `0x1800dd230`
- `0x18013e8bc`
- `0x180191010`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x1800dd0e8`
- `WINHTTP!WinHttpReadData` at `0x1800dd0e8`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800dcf25`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800dcf25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcf33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcf33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd0f6`

## string_xrefs

- `0x1800dd112`: `WinHttpReadData`

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
  _BYTE *v8; // rcx
  unsigned __int64 v9; // rbx
  __int64 v10; // rax
  void *v11; // rsi
  DWORD v12; // ebx
  __int64 v13; // rax
  _BYTE *v14; // rcx
  void *v15; // rcx
  void *pExceptionObject[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h]
  unsigned __int64 v18; // [rsp+38h] [rbp-40h]
  void *Block; // [rsp+40h] [rbp-38h] BYREF
  __int64 v20; // [rsp+48h] [rbp-30h]
  __int64 v21; // [rsp+50h] [rbp-28h]
  unsigned __int64 v22; // [rsp+58h] [rbp-20h]

  v4 = a2;
  if ( !*((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)this
                                                                                         + 1))
        + 52) )
  {
    if ( WinHttpQueryDataAvailable(*((HINTERNET *)this + 13), 0) )
      return;
    LastError = GetLastError();
    *(_OWORD *)pExceptionObject = 0;
    pExceptionObject[0] = operator new(0x20u);
    v17 = 25;
    v18 = 31;
    strcpy((char *)pExceptionObject[0], "WinHttpQueryDataAvaliable");
    v7 = web::http::client::details::build_error_msg(&Block);
    web::http::client::details::request_context::report_error(this, LastError, v7);
    if ( v22 > 0xF )
    {
      if ( v22 + 1 < 0x1000 )
      {
        v8 = Block;
      }
      else
      {
        v8 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v8 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v8);
    }
    v21 = 0;
    v22 = 15;
    LOBYTE(Block) = 0;
    goto LABEL_34;
  }
  v9 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)this
                                                                                        + 1))
       + 52);
  if ( !v9 )
    v9 = 0x10000;
  if ( *((_QWORD *)this + 12) )
  {
    if ( *((_QWORD *)this + 34) - *((_QWORD *)this + 32) < v9 )
      std::vector<unsigned char>::reserve((char *)this + 256, v9);
    v11 = (void *)*((_QWORD *)this + 32);
  }
  else
  {
    if ( v4 < v9 && !a3 )
    {
      web::http::client::details::request_context::complete_request(this, *((_QWORD *)this + 8));
      return;
    }
    web::http::client::details::request_context::_get_writebuffer(this, &Block);
    if ( !v20 )
    {
      std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid streambuf object");
      throw (std::invalid_argument *)pExceptionObject;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v20 + 224LL))(v20, v9);
    v11 = (void *)v10;
    if ( v10 )
    {
      *((_QWORD *)this + 31) = v9;
      *((_QWORD *)this + 27) = v10;
    }
    else
    {
      if ( v9 > *((_QWORD *)this + 29) - *((_QWORD *)this + 28) )
        std::vector<unsigned char>::resize((char *)this + 224, v9);
      *((_QWORD *)this + 27) = 0;
      v11 = (void *)*((_QWORD *)this + 28);
    }
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(&Block);
  }
  if ( !WinHttpReadData(*((HINTERNET *)this + 13), v11, v9, 0) )
  {
    v12 = GetLastError();
    v17 = 15;
    v18 = 15;
    qmemcpy(pExceptionObject, "WinHttpReadDat", 14);
    HIWORD(pExceptionObject[1]) = (unsigned __int8)aWinhttpreaddat[14];
    v13 = web::http::client::details::build_error_msg(&Block);
    web::http::client::details::request_context::report_error(this, v12, v13);
    if ( v22 > 0xF )
    {
      if ( v22 + 1 < 0x1000 )
      {
        v14 = Block;
      }
      else
      {
        v14 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v14 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v14);
    }
    v21 = 0;
    v22 = 15;
    LOBYTE(Block) = 0;
LABEL_34:
    if ( v18 > 0xF )
    {
      if ( v18 + 1 < 0x1000 )
      {
        v15 = pExceptionObject[0];
      }
      else
      {
        v15 = (void *)*((_QWORD *)pExceptionObject[0] - 1);
        if ( (unsigned __int64)((char *)pExceptionObject[0] - (char *)v15 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v15);
    }
  }
}

```

## disassembly

```asm
0x1800dcee0  push    rbp
0x1800dcee2  push    rbx
0x1800dcee3  push    rsi
0x1800dcee4  push    rdi
0x1800dcee5  push    r14
0x1800dcee7  push    r15
0x1800dcee9  mov     rbp, rsp
0x1800dceec  sub     rsp, 78h
0x1800dcef0  mov     rax, cs:__security_cookie
0x1800dcef7  xor     rax, rsp
0x1800dcefa  mov     [rbp+var_18], rax
0x1800dcefe  movzx   esi, r8b
0x1800dcf02  mov     r15d, edx
0x1800dcf05  mov     rdi, rcx
0x1800dcf08  mov     rcx, [rcx+8]; this
0x1800dcf0c  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800dcf11  cmp     qword ptr [rax+1A0h], 0
0x1800dcf19  jnz     loc_1800DCFEF
0x1800dcf1f  xor     edx, edx; lpdwNumberOfBytesAvailable
0x1800dcf21  mov     rcx, [rdi+68h]; hRequest
0x1800dcf25  call    cs:__imp_WinHttpQueryDataAvailable
0x1800dcf2b  test    eax, eax
0x1800dcf2d  jnz     loc_1800DD1EF
0x1800dcf33  call    cs:__imp_GetLastError
0x1800dcf39  mov     ebx, eax
0x1800dcf3b  xorps   xmm0, xmm0
0x1800dcf3e  movups  xmmword ptr [rbp+pExceptionObject], xmm0
0x1800dcf42  xor     r14d, r14d
0x1800dcf45  mov     ecx, 20h ; ' '; Size
0x1800dcf4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dcf4f  mov     [rbp+pExceptionObject], rax
0x1800dcf53  mov     [rbp+var_48], 19h
0x1800dcf5b  mov     [rbp+var_40], 1Fh
0x1800dcf63  movups  xmm0, xmmword ptr cs:aWinhttpqueryda; "WinHttpQueryDataAvaliable"
0x1800dcf6a  movups  xmmword ptr [rax], xmm0
0x1800dcf6d  movups  xmm1, xmmword ptr cs:aWinhttpqueryda+9; "eryDataAvaliable"
0x1800dcf74  movups  xmmword ptr [rax+9], xmm1
0x1800dcf78  mov     [rax+19h], r14b
0x1800dcf7c  lea     r8, [rbp+pExceptionObject]
0x1800dcf80  mov     edx, ebx
0x1800dcf82  lea     rcx, [rbp+Block]; Src
0x1800dcf86  call    web__http__client__details__build_error_msg
0x1800dcf8b  nop
0x1800dcf8c  mov     r8, rax
0x1800dcf8f  mov     edx, ebx
0x1800dcf91  mov     rcx, rdi
0x1800dcf94  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800dcf99  nop
0x1800dcf9a  mov     rdx, [rbp+var_20]
0x1800dcf9e  cmp     rdx, 0Fh
0x1800dcfa2  jbe     short loc_1800DCFDA
0x1800dcfa4  mov     rax, [rbp+Block]
0x1800dcfa8  inc     rdx
0x1800dcfab  cmp     rdx, 1000h
0x1800dcfb2  jb      short loc_1800DCFD2
0x1800dcfb4  mov     rcx, [rax-8]
0x1800dcfb8  sub     rax, rcx
0x1800dcfbb  sub     rax, 8
0x1800dcfbf  cmp     rax, 1Fh
0x1800dcfc3  ja      short loc_1800DCFCB
0x1800dcfc5  add     rdx, 27h ; '''
0x1800dcfc9  jmp     short loc_1800DCFD5
0x1800dcfcb  mov     ecx, 5
0x1800dcfd0  int     29h; Win8: RtlFailFast(ecx)
0x1800dcfd2  mov     rcx, rax; Block
0x1800dcfd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dcfda  mov     [rbp+var_28], r14
0x1800dcfde  mov     [rbp+var_20], 0Fh
0x1800dcfe6  mov     byte ptr [rbp+Block], 0
0x1800dcfea  jmp     loc_1800DD1AF
0x1800dcfef  mov     rcx, [rdi+8]; this
0x1800dcff3  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800dcff8  mov     rbx, [rax+1A0h]
0x1800dcfff  mov     eax, 10000h
0x1800dd004  test    rbx, rbx
0x1800dd007  cmovz   rbx, rax
0x1800dd00b  xor     r14d, r14d
0x1800dd00e  cmp     [rdi+60h], r14
0x1800dd012  jnz     loc_1800DD0B2
0x1800dd018  cmp     r15, rbx
0x1800dd01b  jnb     short loc_1800DD033
0x1800dd01d  test    sil, sil
0x1800dd020  jnz     short loc_1800DD033
0x1800dd022  mov     rdx, [rdi+40h]; unsigned __int64
0x1800dd026  mov     rcx, rdi; this
0x1800dd029  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800dd02e  jmp     loc_1800DD1EF
0x1800dd033  lea     rdx, [rbp+Block]
0x1800dd037  mov     rcx, rdi
0x1800dd03a  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x1800dd03f  nop
0x1800dd040  mov     rcx, [rbp+var_30]
0x1800dd044  test    rcx, rcx
0x1800dd047  jz      loc_1800DD208
0x1800dd04d  mov     rax, [rcx]
0x1800dd050  mov     rdx, rbx
0x1800dd053  mov     rax, [rax+0E0h]
0x1800dd05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd05f  mov     rsi, rax
0x1800dd062  test    rax, rax
0x1800dd065  jnz     short loc_1800DD099
0x1800dd067  mov     rax, [rdi+0E8h]
0x1800dd06e  sub     rax, [rdi+0E0h]
0x1800dd075  cmp     rbx, rax
0x1800dd078  jbe     short loc_1800DD089
0x1800dd07a  mov     rdx, rbx
0x1800dd07d  lea     rcx, [rdi+0E0h]
0x1800dd084  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800dd089  mov     [rdi+0D8h], r14
0x1800dd090  mov     rsi, [rdi+0E0h]
0x1800dd097  jmp     short loc_1800DD0A7
0x1800dd099  mov     [rdi+0F8h], rbx
0x1800dd0a0  mov     [rdi+0D8h], rax
0x1800dd0a7  lea     rcx, [rbp+Block]
0x1800dd0ab  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800dd0b0  jmp     short loc_1800DD0DB
0x1800dd0b2  mov     rax, [rdi+110h]
0x1800dd0b9  sub     rax, [rdi+100h]
0x1800dd0c0  cmp     rax, rbx
0x1800dd0c3  jnb     short loc_1800DD0D4
0x1800dd0c5  mov     rdx, rbx
0x1800dd0c8  lea     rcx, [rdi+100h]
0x1800dd0cf  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x1800dd0d4  mov     rsi, [rdi+100h]
0x1800dd0db  mov     r8d, ebx; dwNumberOfBytesToRead
0x1800dd0de  xor     r9d, r9d; lpdwNumberOfBytesRead
0x1800dd0e1  mov     rdx, rsi; lpBuffer
0x1800dd0e4  mov     rcx, [rdi+68h]; hRequest
0x1800dd0e8  call    cs:__imp_WinHttpReadData
0x1800dd0ee  test    eax, eax
0x1800dd0f0  jnz     loc_1800DD1EF
0x1800dd0f6  call    cs:__imp_GetLastError
0x1800dd0fc  mov     ebx, eax
0x1800dd0fe  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x1800dd102  mov     [rbp+var_48], 0Fh
0x1800dd10a  mov     [rbp+var_40], 0Fh
0x1800dd112  movsd   xmm0, qword ptr cs:aWinhttpreaddat; "WinHttpReadData"
0x1800dd11a  movsd   [rbp+pExceptionObject], xmm0
0x1800dd11f  mov     ecx, dword ptr cs:aWinhttpreaddat+8; "eadData"
0x1800dd125  mov     dword ptr [rbp+pExceptionObject+8], ecx
0x1800dd128  movzx   ecx, word ptr cs:aWinhttpreaddat+0Ch; "ata"
0x1800dd12f  mov     word ptr [rbp+pExceptionObject+0Ch], cx
0x1800dd133  movzx   eax, byte ptr cs:aWinhttpreaddat+0Eh; "a"
0x1800dd13a  mov     byte ptr [rbp+pExceptionObject+0Eh], al
0x1800dd13d  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x1800dd141  lea     r8, [rbp+pExceptionObject]
0x1800dd145  mov     edx, ebx
0x1800dd147  lea     rcx, [rbp+Block]; Src
0x1800dd14b  call    web__http__client__details__build_error_msg
0x1800dd150  nop
0x1800dd151  mov     r8, rax
0x1800dd154  mov     edx, ebx
0x1800dd156  mov     rcx, rdi
0x1800dd159  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800dd15e  nop
0x1800dd15f  mov     rdx, [rbp+var_20]
0x1800dd163  cmp     rdx, 0Fh
0x1800dd167  jbe     short loc_1800DD19F
0x1800dd169  mov     rax, [rbp+Block]
0x1800dd16d  inc     rdx
0x1800dd170  cmp     rdx, 1000h
0x1800dd177  jb      short loc_1800DD197
0x1800dd179  mov     rcx, [rax-8]
0x1800dd17d  sub     rax, rcx
0x1800dd180  sub     rax, 8
0x1800dd184  cmp     rax, 1Fh
0x1800dd188  ja      short loc_1800DD190
0x1800dd18a  add     rdx, 27h ; '''
0x1800dd18e  jmp     short loc_1800DD19A
0x1800dd190  mov     ecx, 5
0x1800dd195  int     29h; Win8: RtlFailFast(ecx)
0x1800dd197  mov     rcx, rax; Block
0x1800dd19a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd19f  mov     [rbp+var_28], r14
0x1800dd1a3  mov     [rbp+var_20], 0Fh
0x1800dd1ab  mov     byte ptr [rbp+Block], 0
0x1800dd1af  mov     rdx, [rbp+var_40]
0x1800dd1b3  cmp     rdx, 0Fh
0x1800dd1b7  jbe     short loc_1800DD1EF
0x1800dd1b9  mov     rax, [rbp+pExceptionObject]
0x1800dd1bd  inc     rdx
0x1800dd1c0  cmp     rdx, 1000h
0x1800dd1c7  jb      short loc_1800DD1E7
0x1800dd1c9  mov     rcx, [rax-8]
0x1800dd1cd  sub     rax, rcx
0x1800dd1d0  sub     rax, 8
0x1800dd1d4  cmp     rax, 1Fh
0x1800dd1d8  ja      short loc_1800DD1E0
0x1800dd1da  add     rdx, 27h ; '''
0x1800dd1de  jmp     short loc_1800DD1EA
0x1800dd1e0  mov     ecx, 5
0x1800dd1e5  int     29h; Win8: RtlFailFast(ecx)
0x1800dd1e7  mov     rcx, rax; Block
0x1800dd1ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd1ef  mov     rcx, [rbp+var_18]
0x1800dd1f3  xor     rcx, rsp; StackCookie
0x1800dd1f6  call    __security_check_cookie
0x1800dd1fb  add     rsp, 78h
0x1800dd1ff  pop     r15
0x1800dd201  pop     r14
0x1800dd203  pop     rdi
0x1800dd204  pop     rsi
0x1800dd205  pop     rbx
0x1800dd206  pop     rbp
0x1800dd207  retn
0x1800dd208  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x1800dd20f  lea     rcx, [rbp+pExceptionObject]; this
0x1800dd213  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800dd218  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800dd21f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800dd223  call    _CxxThrowException_0
```
