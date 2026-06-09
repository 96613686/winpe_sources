# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x1800dd080`
- end: `0x1800dd3c9`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `841`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800d4ef0`
- `0x1800d5930`
- `0x1800d80b0`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x180019588`
- `0x18001a084`
- `0x180020550`
- `0x18004c350`
- `0x1800bcdf0`
- `0x1800bd3d0`
- `0x1800bd520`
- `0x1800be5f0`
- `0x1800d7b70`
- `0x1800dd080`
- `0x1800dd3d0`
- `0x180140cdc`
- `0x180193010`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x1800dd288`
- `WINHTTP!WinHttpReadData` at `0x1800dd288`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800dd0c5`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800dd0c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd296`

## string_xrefs

- `0x1800dd2b2`: `WinHttpReadData`

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
0x1800dd080  push    rbp
0x1800dd082  push    rbx
0x1800dd083  push    rsi
0x1800dd084  push    rdi
0x1800dd085  push    r14
0x1800dd087  push    r15
0x1800dd089  mov     rbp, rsp
0x1800dd08c  sub     rsp, 78h
0x1800dd090  mov     rax, cs:__security_cookie
0x1800dd097  xor     rax, rsp
0x1800dd09a  mov     [rbp+var_18], rax
0x1800dd09e  movzx   esi, r8b
0x1800dd0a2  mov     r15d, edx
0x1800dd0a5  mov     rdi, rcx
0x1800dd0a8  mov     rcx, [rcx+8]; this
0x1800dd0ac  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800dd0b1  cmp     qword ptr [rax+1A0h], 0
0x1800dd0b9  jnz     loc_1800DD18F
0x1800dd0bf  xor     edx, edx; lpdwNumberOfBytesAvailable
0x1800dd0c1  mov     rcx, [rdi+68h]; hRequest
0x1800dd0c5  call    cs:__imp_WinHttpQueryDataAvailable
0x1800dd0cb  test    eax, eax
0x1800dd0cd  jnz     loc_1800DD38F
0x1800dd0d3  call    cs:__imp_GetLastError
0x1800dd0d9  mov     ebx, eax
0x1800dd0db  xorps   xmm0, xmm0
0x1800dd0de  movups  xmmword ptr [rbp+pExceptionObject], xmm0
0x1800dd0e2  xor     r14d, r14d
0x1800dd0e5  mov     ecx, 20h ; ' '; Size
0x1800dd0ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd0ef  mov     [rbp+pExceptionObject], rax
0x1800dd0f3  mov     [rbp+var_48], 19h
0x1800dd0fb  mov     [rbp+var_40], 1Fh
0x1800dd103  movups  xmm0, xmmword ptr cs:aWinhttpqueryda; "WinHttpQueryDataAvaliable"
0x1800dd10a  movups  xmmword ptr [rax], xmm0
0x1800dd10d  movups  xmm1, xmmword ptr cs:aWinhttpqueryda+9; "eryDataAvaliable"
0x1800dd114  movups  xmmword ptr [rax+9], xmm1
0x1800dd118  mov     [rax+19h], r14b
0x1800dd11c  lea     r8, [rbp+pExceptionObject]
0x1800dd120  mov     edx, ebx
0x1800dd122  lea     rcx, [rbp+Block]; Src
0x1800dd126  call    web__http__client__details__build_error_msg
0x1800dd12b  nop
0x1800dd12c  mov     r8, rax
0x1800dd12f  mov     edx, ebx
0x1800dd131  mov     rcx, rdi
0x1800dd134  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800dd139  nop
0x1800dd13a  mov     rdx, [rbp+var_20]
0x1800dd13e  cmp     rdx, 0Fh
0x1800dd142  jbe     short loc_1800DD17A
0x1800dd144  mov     rax, [rbp+Block]
0x1800dd148  inc     rdx
0x1800dd14b  cmp     rdx, 1000h
0x1800dd152  jb      short loc_1800DD172
0x1800dd154  mov     rcx, [rax-8]
0x1800dd158  sub     rax, rcx
0x1800dd15b  sub     rax, 8
0x1800dd15f  cmp     rax, 1Fh
0x1800dd163  ja      short loc_1800DD16B
0x1800dd165  add     rdx, 27h ; '''
0x1800dd169  jmp     short loc_1800DD175
0x1800dd16b  mov     ecx, 5
0x1800dd170  int     29h; Win8: RtlFailFast(ecx)
0x1800dd172  mov     rcx, rax; Block
0x1800dd175  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd17a  mov     [rbp+var_28], r14
0x1800dd17e  mov     [rbp+var_20], 0Fh
0x1800dd186  mov     byte ptr [rbp+Block], 0
0x1800dd18a  jmp     loc_1800DD34F
0x1800dd18f  mov     rcx, [rdi+8]; this
0x1800dd193  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800dd198  mov     rbx, [rax+1A0h]
0x1800dd19f  mov     eax, 10000h
0x1800dd1a4  test    rbx, rbx
0x1800dd1a7  cmovz   rbx, rax
0x1800dd1ab  xor     r14d, r14d
0x1800dd1ae  cmp     [rdi+60h], r14
0x1800dd1b2  jnz     loc_1800DD252
0x1800dd1b8  cmp     r15, rbx
0x1800dd1bb  jnb     short loc_1800DD1D3
0x1800dd1bd  test    sil, sil
0x1800dd1c0  jnz     short loc_1800DD1D3
0x1800dd1c2  mov     rdx, [rdi+40h]; unsigned __int64
0x1800dd1c6  mov     rcx, rdi; this
0x1800dd1c9  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800dd1ce  jmp     loc_1800DD38F
0x1800dd1d3  lea     rdx, [rbp+Block]
0x1800dd1d7  mov     rcx, rdi
0x1800dd1da  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x1800dd1df  nop
0x1800dd1e0  mov     rcx, [rbp+var_30]
0x1800dd1e4  test    rcx, rcx
0x1800dd1e7  jz      loc_1800DD3A8
0x1800dd1ed  mov     rax, [rcx]
0x1800dd1f0  mov     rdx, rbx
0x1800dd1f3  mov     rax, [rax+0E0h]
0x1800dd1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd1ff  mov     rsi, rax
0x1800dd202  test    rax, rax
0x1800dd205  jnz     short loc_1800DD239
0x1800dd207  mov     rax, [rdi+0E8h]
0x1800dd20e  sub     rax, [rdi+0E0h]
0x1800dd215  cmp     rbx, rax
0x1800dd218  jbe     short loc_1800DD229
0x1800dd21a  mov     rdx, rbx
0x1800dd21d  lea     rcx, [rdi+0E0h]
0x1800dd224  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800dd229  mov     [rdi+0D8h], r14
0x1800dd230  mov     rsi, [rdi+0E0h]
0x1800dd237  jmp     short loc_1800DD247
0x1800dd239  mov     [rdi+0F8h], rbx
0x1800dd240  mov     [rdi+0D8h], rax
0x1800dd247  lea     rcx, [rbp+Block]
0x1800dd24b  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800dd250  jmp     short loc_1800DD27B
0x1800dd252  mov     rax, [rdi+110h]
0x1800dd259  sub     rax, [rdi+100h]
0x1800dd260  cmp     rax, rbx
0x1800dd263  jnb     short loc_1800DD274
0x1800dd265  mov     rdx, rbx
0x1800dd268  lea     rcx, [rdi+100h]
0x1800dd26f  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x1800dd274  mov     rsi, [rdi+100h]
0x1800dd27b  mov     r8d, ebx; dwNumberOfBytesToRead
0x1800dd27e  xor     r9d, r9d; lpdwNumberOfBytesRead
0x1800dd281  mov     rdx, rsi; lpBuffer
0x1800dd284  mov     rcx, [rdi+68h]; hRequest
0x1800dd288  call    cs:__imp_WinHttpReadData
0x1800dd28e  test    eax, eax
0x1800dd290  jnz     loc_1800DD38F
0x1800dd296  call    cs:__imp_GetLastError
0x1800dd29c  mov     ebx, eax
0x1800dd29e  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x1800dd2a2  mov     [rbp+var_48], 0Fh
0x1800dd2aa  mov     [rbp+var_40], 0Fh
0x1800dd2b2  movsd   xmm0, qword ptr cs:aWinhttpreaddat; "WinHttpReadData"
0x1800dd2ba  movsd   [rbp+pExceptionObject], xmm0
0x1800dd2bf  mov     ecx, dword ptr cs:aWinhttpreaddat+8; "eadData"
0x1800dd2c5  mov     dword ptr [rbp+pExceptionObject+8], ecx
0x1800dd2c8  movzx   ecx, word ptr cs:aWinhttpreaddat+0Ch; "ata"
0x1800dd2cf  mov     word ptr [rbp+pExceptionObject+0Ch], cx
0x1800dd2d3  movzx   eax, byte ptr cs:aWinhttpreaddat+0Eh; "a"
0x1800dd2da  mov     byte ptr [rbp+pExceptionObject+0Eh], al
0x1800dd2dd  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x1800dd2e1  lea     r8, [rbp+pExceptionObject]
0x1800dd2e5  mov     edx, ebx
0x1800dd2e7  lea     rcx, [rbp+Block]; Src
0x1800dd2eb  call    web__http__client__details__build_error_msg
0x1800dd2f0  nop
0x1800dd2f1  mov     r8, rax
0x1800dd2f4  mov     edx, ebx
0x1800dd2f6  mov     rcx, rdi
0x1800dd2f9  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800dd2fe  nop
0x1800dd2ff  mov     rdx, [rbp+var_20]
0x1800dd303  cmp     rdx, 0Fh
0x1800dd307  jbe     short loc_1800DD33F
0x1800dd309  mov     rax, [rbp+Block]
0x1800dd30d  inc     rdx
0x1800dd310  cmp     rdx, 1000h
0x1800dd317  jb      short loc_1800DD337
0x1800dd319  mov     rcx, [rax-8]
0x1800dd31d  sub     rax, rcx
0x1800dd320  sub     rax, 8
0x1800dd324  cmp     rax, 1Fh
0x1800dd328  ja      short loc_1800DD330
0x1800dd32a  add     rdx, 27h ; '''
0x1800dd32e  jmp     short loc_1800DD33A
0x1800dd330  mov     ecx, 5
0x1800dd335  int     29h; Win8: RtlFailFast(ecx)
0x1800dd337  mov     rcx, rax; Block
0x1800dd33a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd33f  mov     [rbp+var_28], r14
0x1800dd343  mov     [rbp+var_20], 0Fh
0x1800dd34b  mov     byte ptr [rbp+Block], 0
0x1800dd34f  mov     rdx, [rbp+var_40]
0x1800dd353  cmp     rdx, 0Fh
0x1800dd357  jbe     short loc_1800DD38F
0x1800dd359  mov     rax, [rbp+pExceptionObject]
0x1800dd35d  inc     rdx
0x1800dd360  cmp     rdx, 1000h
0x1800dd367  jb      short loc_1800DD387
0x1800dd369  mov     rcx, [rax-8]
0x1800dd36d  sub     rax, rcx
0x1800dd370  sub     rax, 8
0x1800dd374  cmp     rax, 1Fh
0x1800dd378  ja      short loc_1800DD380
0x1800dd37a  add     rdx, 27h ; '''
0x1800dd37e  jmp     short loc_1800DD38A
0x1800dd380  mov     ecx, 5
0x1800dd385  int     29h; Win8: RtlFailFast(ecx)
0x1800dd387  mov     rcx, rax; Block
0x1800dd38a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd38f  mov     rcx, [rbp+var_18]
0x1800dd393  xor     rcx, rsp; StackCookie
0x1800dd396  call    __security_check_cookie
0x1800dd39b  add     rsp, 78h
0x1800dd39f  pop     r15
0x1800dd3a1  pop     r14
0x1800dd3a3  pop     rdi
0x1800dd3a4  pop     rsi
0x1800dd3a5  pop     rbx
0x1800dd3a6  pop     rbp
0x1800dd3a7  retn
0x1800dd3a8  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x1800dd3af  lea     rcx, [rbp+pExceptionObject]; this
0x1800dd3b3  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800dd3b8  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800dd3bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800dd3c3  call    _CxxThrowException_0
```
