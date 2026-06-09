# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x1800d6cf0`
- end: `0x1800d715f`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `1135`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d80b0`

## callees

- `0x180016d23`
- `0x180016d2f`
- `0x180019080`
- `0x1800190a4`
- `0x180019588`
- `0x18001a084`
- `0x180020550`
- `0x18004c350`
- `0x1800bd3d0`
- `0x1800be5f0`
- `0x1800be760`
- `0x1800be810`
- `0x1800d30b0`
- `0x1800d6c00`
- `0x1800d6cf0`
- `0x1800d7b70`
- `0x1800e68b0`
- `0x180140cdc`
- `0x180193010`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800d6ec6`
- `WINHTTP!WinHttpWriteData` at `0x1800d6ec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6dd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6dd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6ed4`

## string_xrefs

- `0x1800d6f01`: `WinHttpWriteData`
- `0x1800d6dc0`: `Error reading outgoing HTTP body from its stream.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall web::http::client::details::winhttp_client::_multiple_segment_write_data(
        struct web::http::client::details::winhttp_request_context *a1)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rcx
  void *v4; // rsi
  unsigned __int64 v5; // rax
  bool v6; // bl
  DWORD v7; // eax
  void *v8; // rax
  void *v9; // rcx
  const void *v10; // rdx
  bool v11; // zf
  DWORD LastError; // ebx
  __int64 v13; // rax
  _BYTE *v14; // rcx
  unsigned __int64 v15; // rax
  __int64 v16; // r8
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  DWORD dwNumberOfBytesToWrite[2]; // [rsp+30h] [rbp-69h] BYREF
  const void *v21; // [rsp+38h] [rbp-61h] BYREF
  char v22[8]; // [rsp+40h] [rbp-59h] BYREF
  void *v23; // [rsp+48h] [rbp-51h]
  unsigned __int64 v24; // [rsp+50h] [rbp-49h]
  void *Block; // [rsp+58h] [rbp-41h] BYREF
  volatile signed __int32 *v26; // [rsp+60h] [rbp-39h]
  __int64 v27; // [rsp+68h] [rbp-31h]
  unsigned __int64 v28; // [rsp+70h] [rbp-29h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-21h] BYREF
  __int64 v30; // [rsp+88h] [rbp-11h]
  unsigned __int64 v31; // [rsp+90h] [rbp-9h]
  void *v32[3]; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 v33; // [rsp+B0h] [rbp+17h]

  web::http::client::details::winhttp_request_context::_get_readbuffer(a1, v22);
  v2 = *((_QWORD *)a1 + 18);
  v3 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)a1
                                                                                        + 1))
       + 52);
  if ( !v3 )
    v3 = 0x10000;
  if ( v2 > v3 )
    v2 = v3;
  v21 = 0;
  *(_QWORD *)dwNumberOfBytesToWrite = 0;
  v4 = v23;
  if ( !v23 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)&pExceptionObject, "Invalid streambuf object");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  if ( (*(unsigned __int8 (__fastcall **)(void *, const void **, DWORD *))(*(_QWORD *)v23 + 240LL))(
         v23,
         &v21,
         dwNumberOfBytesToWrite) )
  {
    v5 = *(_QWORD *)dwNumberOfBytesToWrite;
    if ( *(_QWORD *)dwNumberOfBytesToWrite )
    {
      v10 = v21;
      if ( v21 )
      {
        *((_QWORD *)a1 + 31) = *(_QWORD *)dwNumberOfBytesToWrite;
      }
      else
      {
        if ( *(_QWORD *)dwNumberOfBytesToWrite > *((_QWORD *)a1 + 29) - *((_QWORD *)a1 + 28) )
        {
          std::vector<unsigned char>::resize((char *)a1 + 224, *(_QWORD *)dwNumberOfBytesToWrite);
          v5 = *(_QWORD *)dwNumberOfBytesToWrite;
        }
        v10 = 0;
      }
      *((_QWORD *)a1 + 27) = v10;
      if ( v2 > v5 )
        v2 = v5;
      v11 = *((_QWORD *)a1 + 18) == v2;
      *((_QWORD *)a1 + 18) -= v2;
      if ( v11 )
        *((_DWORD *)a1 + 34) = 0;
      if ( !v10 )
        v10 = (const void *)*((_QWORD *)a1 + 28);
      if ( !WinHttpWriteData(*((HINTERNET *)a1 + 13), v10, v2, 0) )
      {
        LastError = GetLastError();
        pExceptionObject = 0;
        *(_QWORD *)&pExceptionObject = operator new(0x20u);
        v30 = 16;
        v31 = 31;
        strcpy((char *)pExceptionObject, "WinHttpWriteData");
        v13 = web::http::client::details::build_error_msg(&Block);
        web::http::client::details::request_context::report_error(a1, LastError, v13);
        if ( v28 > 0xF )
        {
          if ( v28 + 1 < 0x1000 )
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
        v27 = 0;
        v28 = 15;
        LOBYTE(Block) = 0;
        if ( v31 > 0xF )
        {
          v8 = (void *)pExceptionObject;
          if ( v31 + 1 >= 0x1000 )
          {
            v9 = *(void **)(pExceptionObject - 8);
            if ( (unsigned __int64)(pExceptionObject - (_QWORD)v9 - 8) <= 0x1F )
              goto LABEL_12;
            goto LABEL_35;
          }
LABEL_36:
          operator delete(v8);
        }
      }
    }
    else
    {
      (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v4 + 256LL))(v4, &Block);
      v6 = __ExceptionPtrToBool(&Block);
      __ExceptionPtrDestroy(&Block);
      if ( v6 )
      {
        (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v4 + 256LL))(v4, &Block);
        web::http::client::details::request_context::report_exception(a1, &Block);
        goto LABEL_55;
      }
      std::wstring::wstring(v32, L"Error reading outgoing HTTP body from its stream.");
      v7 = GetLastError();
      web::http::client::details::request_context::report_error(a1, v7, v32);
      if ( v33 > 7 )
      {
        v8 = v32[0];
        if ( 2 * v33 + 2 >= 0x1000 )
        {
          v9 = (void *)*((_QWORD *)v32[0] - 1);
          if ( (unsigned __int64)((char *)v32[0] - (char *)v9 - 8) <= 0x1F )
          {
LABEL_12:
            operator delete(v9);
            goto LABEL_55;
          }
LABEL_35:
          __fastfail(5u);
        }
        goto LABEL_36;
      }
    }
  }
  else
  {
    if ( v2 > *((_QWORD *)a1 + 29) - *((_QWORD *)a1 + 28) )
      std::vector<unsigned char>::resize((char *)a1 + 224, v2);
    *((_QWORD *)a1 + 27) = 0;
    v32[0] = a1;
    v32[1] = &Concurrency::streams::streambuf<unsigned char>::`vftable';
    v15 = v24;
    if ( v24 )
      _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
    v32[2] = v4;
    v33 = v15;
    v16 = *((_QWORD *)a1 + 27);
    if ( !v16 )
      v16 = *((_QWORD *)a1 + 28);
    (*(void (__fastcall **)(void *, void **, __int64, unsigned __int64))(*(_QWORD *)v4 + 168LL))(v4, &Block, v16, v2);
    ___then_V_lambda_1___BF____multiple_segment_write_data_winhttp_client_details_client_http_web__CAXPEAVwinhttp_request_context_4567__Z____task__K_pplx__QEBA_AV__task_X_1___QEAV_lambda_1___BF____multiple_segment_write_data_winhttp_client_details_client_http_web__CAXPEAVwinhttp_request_context_6789__Z__Z(
      &Block,
      &pExceptionObject,
      v32);
    v17 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject + 1);
    if ( *((_QWORD *)&pExceptionObject + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&pExceptionObject + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v18 = v26;
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v19 = (volatile signed __int32 *)v33;
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v33 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
LABEL_55:
  Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v22);
}

```

## disassembly

```asm
0x1800d6cf0  push    rbp
0x1800d6cf2  push    rbx
0x1800d6cf3  push    rsi
0x1800d6cf4  push    rdi
0x1800d6cf5  push    r14
0x1800d6cf7  push    r15
0x1800d6cf9  lea     rbp, [rsp-2Fh]
0x1800d6cfe  sub     rsp, 0C8h
0x1800d6d05  mov     rax, cs:__security_cookie
0x1800d6d0c  xor     rax, rsp
0x1800d6d0f  mov     [rbp+57h+var_38], rax
0x1800d6d13  mov     rdi, rcx
0x1800d6d16  xor     r15d, r15d
0x1800d6d19  lea     rdx, [rbp+57h+var_B0]
0x1800d6d1d  call    ?_get_readbuffer@winhttp_request_context@details@client@http@web@@UEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::winhttp_request_context::_get_readbuffer(void)
0x1800d6d22  nop
0x1800d6d23  mov     rbx, [rdi+90h]
0x1800d6d2a  mov     rcx, [rdi+8]; this
0x1800d6d2e  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800d6d33  mov     rcx, [rax+1A0h]
0x1800d6d3a  mov     eax, 10000h
0x1800d6d3f  test    rcx, rcx
0x1800d6d42  cmovz   rcx, rax
0x1800d6d46  cmp     rbx, rcx
0x1800d6d49  cmova   rbx, rcx
0x1800d6d4d  mov     [rbp+57h+var_B8], r15
0x1800d6d51  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], r15
0x1800d6d55  mov     rsi, [rbp+57h+var_A8]
0x1800d6d59  test    rsi, rsi
0x1800d6d5c  jz      loc_1800D713E
0x1800d6d62  mov     rax, [rsi]
0x1800d6d65  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x1800d6d69  lea     rdx, [rbp+57h+var_B8]
0x1800d6d6d  mov     rcx, rsi
0x1800d6d70  mov     rax, [rax+0F0h]
0x1800d6d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6d7c  test    al, al
0x1800d6d7e  jz      loc_1800D6FCE
0x1800d6d84  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800d6d88  test    rax, rax
0x1800d6d8b  jnz     loc_1800D6E57
0x1800d6d91  mov     rax, [rsi]
0x1800d6d94  lea     rdx, [rbp+57h+Block]
0x1800d6d98  mov     rcx, rsi
0x1800d6d9b  mov     rax, [rax+100h]
0x1800d6da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6da7  lea     rcx, [rbp+57h+Block]; void *
0x1800d6dab  call    ?__ExceptionPtrToBool@@YA_NPEBX@Z_0; __ExceptionPtrToBool(void const *)
0x1800d6db0  movzx   ebx, al
0x1800d6db3  lea     rcx, [rbp+57h+Block]; void *
0x1800d6db7  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800d6dbc  test    bl, bl
0x1800d6dbe  jnz     short loc_1800D6E30
0x1800d6dc0  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x1800d6dc7  lea     rcx, [rbp+57h+var_58]
0x1800d6dcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d6dd0  nop
0x1800d6dd1  call    cs:__imp_GetLastError
0x1800d6dd7  mov     edx, eax
0x1800d6dd9  lea     r8, [rbp+57h+var_58]
0x1800d6ddd  mov     rcx, rdi
0x1800d6de0  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x1800d6de5  nop
0x1800d6de6  mov     rdx, [rbp+57h+var_40]
0x1800d6dea  cmp     rdx, 7
0x1800d6dee  jbe     loc_1800D7119
0x1800d6df4  mov     rax, [rbp+57h+var_58]
0x1800d6df8  lea     rdx, ds:2[rdx*2]
0x1800d6e00  cmp     rdx, 1000h
0x1800d6e07  jb      loc_1800D6FC1
0x1800d6e0d  mov     rcx, [rax-8]; Block
0x1800d6e11  sub     rax, rcx
0x1800d6e14  sub     rax, 8
0x1800d6e18  cmp     rax, 1Fh
0x1800d6e1c  ja      loc_1800D6FBA
0x1800d6e22  add     rdx, 27h ; '''
0x1800d6e26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6e2b  jmp     loc_1800D7119
0x1800d6e30  mov     rax, [rsi]
0x1800d6e33  lea     rdx, [rbp+57h+Block]
0x1800d6e37  mov     rcx, rsi
0x1800d6e3a  mov     rax, [rax+100h]
0x1800d6e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e46  lea     rdx, [rbp+57h+Block]
0x1800d6e4a  mov     rcx, rdi
0x1800d6e4d  call    ?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z; web::http::client::details::request_context::report_exception(std::exception_ptr)
0x1800d6e52  jmp     loc_1800D7119
0x1800d6e57  mov     rdx, [rbp+57h+var_B8]
0x1800d6e5b  test    rdx, rdx
0x1800d6e5e  jnz     short loc_1800D6E8B
0x1800d6e60  mov     rcx, [rdi+0E8h]
0x1800d6e67  sub     rcx, [rdi+0E0h]
0x1800d6e6e  cmp     rax, rcx
0x1800d6e71  jbe     short loc_1800D6E86
0x1800d6e73  mov     rdx, rax
0x1800d6e76  lea     rcx, [rdi+0E0h]
0x1800d6e7d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800d6e82  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800d6e86  mov     rdx, r15
0x1800d6e89  jmp     short loc_1800D6E92
0x1800d6e8b  mov     [rdi+0F8h], rax
0x1800d6e92  mov     [rdi+0D8h], rdx
0x1800d6e99  cmp     rbx, rax
0x1800d6e9c  cmova   rbx, rax
0x1800d6ea0  sub     [rdi+90h], rbx
0x1800d6ea7  jnz     short loc_1800D6EB0
0x1800d6ea9  mov     [rdi+88h], r15d
0x1800d6eb0  test    rdx, rdx
0x1800d6eb3  jnz     short loc_1800D6EBC
0x1800d6eb5  mov     rdx, [rdi+0E0h]; lpBuffer
0x1800d6ebc  mov     r8d, ebx; dwNumberOfBytesToWrite
0x1800d6ebf  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800d6ec2  mov     rcx, [rdi+68h]; hRequest
0x1800d6ec6  call    cs:__imp_WinHttpWriteData
0x1800d6ecc  test    eax, eax
0x1800d6ece  jnz     loc_1800D7119
0x1800d6ed4  call    cs:__imp_GetLastError
0x1800d6eda  mov     ebx, eax
0x1800d6edc  xorps   xmm0, xmm0
0x1800d6edf  movups  [rbp+57h+pExceptionObject], xmm0
0x1800d6ee3  mov     ecx, 20h ; ' '; Size
0x1800d6ee8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6eed  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800d6ef1  mov     [rbp+57h+var_68], 10h
0x1800d6ef9  mov     [rbp+57h+var_60], 1Fh
0x1800d6f01  movups  xmm0, xmmword ptr cs:aWinhttpwriteda; "WinHttpWriteData"
0x1800d6f08  movups  xmmword ptr [rax], xmm0
0x1800d6f0b  mov     byte ptr [rax+10h], 0
0x1800d6f0f  lea     r8, [rbp+57h+pExceptionObject]
0x1800d6f13  mov     edx, ebx
0x1800d6f15  lea     rcx, [rbp+57h+Block]; Src
0x1800d6f19  call    web__http__client__details__build_error_msg
0x1800d6f1e  nop
0x1800d6f1f  mov     r8, rax
0x1800d6f22  mov     edx, ebx
0x1800d6f24  mov     rcx, rdi
0x1800d6f27  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d6f2c  nop
0x1800d6f2d  mov     rdx, [rbp+57h+var_80]
0x1800d6f31  cmp     rdx, 0Fh
0x1800d6f35  jbe     short loc_1800D6F6D
0x1800d6f37  mov     rax, [rbp+57h+Block]
0x1800d6f3b  inc     rdx
0x1800d6f3e  cmp     rdx, 1000h
0x1800d6f45  jb      short loc_1800D6F65
0x1800d6f47  mov     rcx, [rax-8]
0x1800d6f4b  sub     rax, rcx
0x1800d6f4e  sub     rax, 8
0x1800d6f52  cmp     rax, 1Fh
0x1800d6f56  ja      short loc_1800D6F5E
0x1800d6f58  add     rdx, 27h ; '''
0x1800d6f5c  jmp     short loc_1800D6F68
0x1800d6f5e  mov     ecx, 5
0x1800d6f63  int     29h; Win8: RtlFailFast(ecx)
0x1800d6f65  mov     rcx, rax; Block
0x1800d6f68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6f6d  mov     [rbp+57h+var_88], r15
0x1800d6f71  mov     [rbp+57h+var_80], 0Fh
0x1800d6f79  mov     byte ptr [rbp+57h+Block], 0
0x1800d6f7d  mov     rdx, [rbp+57h+var_60]
0x1800d6f81  cmp     rdx, 0Fh
0x1800d6f85  jbe     loc_1800D7119
0x1800d6f8b  mov     rax, qword ptr [rbp+57h+pExceptionObject]
0x1800d6f8f  inc     rdx
0x1800d6f92  cmp     rdx, 1000h
0x1800d6f99  jb      short loc_1800D6FC1
0x1800d6f9b  mov     rcx, [rax-8]; Block
0x1800d6f9f  sub     rax, rcx
0x1800d6fa2  sub     rax, 8
0x1800d6fa6  cmp     rax, 1Fh
0x1800d6faa  ja      short loc_1800D6FBA
0x1800d6fac  add     rdx, 27h ; '''
0x1800d6fb0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6fb5  jmp     loc_1800D7119
0x1800d6fba  mov     ecx, 5
0x1800d6fbf  int     29h; Win8: RtlFailFast(ecx)
0x1800d6fc1  mov     rcx, rax; Block
0x1800d6fc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6fc9  jmp     loc_1800D7119
0x1800d6fce  mov     rax, [rdi+0E8h]
0x1800d6fd5  sub     rax, [rdi+0E0h]
0x1800d6fdc  cmp     rbx, rax
0x1800d6fdf  jbe     short loc_1800D6FF0
0x1800d6fe1  mov     rdx, rbx
0x1800d6fe4  lea     rcx, [rdi+0E0h]
0x1800d6feb  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800d6ff0  mov     [rdi+0D8h], r15
0x1800d6ff7  mov     [rbp+57h+var_58], rdi
0x1800d6ffb  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x1800d7002  mov     [rbp+57h+var_50], rax
0x1800d7006  mov     rax, [rbp+57h+var_A0]
0x1800d700a  test    rax, rax
0x1800d700d  jz      short loc_1800D7013
0x1800d700f  lock inc dword ptr [rax+8]
0x1800d7013  mov     [rbp+57h+var_48], rsi
0x1800d7017  mov     [rbp+57h+var_40], rax
0x1800d701b  mov     r8, [rdi+0D8h]
0x1800d7022  test    r8, r8
0x1800d7025  jnz     short loc_1800D702E
0x1800d7027  mov     r8, [rdi+0E0h]
0x1800d702e  mov     rax, [rsi]
0x1800d7031  mov     r9, rbx
0x1800d7034  lea     rdx, [rbp+57h+Block]
0x1800d7038  mov     rcx, rsi
0x1800d703b  mov     rax, [rax+0A8h]
0x1800d7042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7047  nop
0x1800d7048  lea     r8, [rbp+57h+var_58]
0x1800d704c  lea     rdx, [rbp+57h+pExceptionObject]
0x1800d7050  lea     rcx, [rbp+57h+Block]
0x1800d7054  call    ??$then@V_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@4567@@Z@@?$task@_K@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@6789@@Z@@Z; pplx::task<unsigned __int64>::then<`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_>(`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_ &&)
0x1800d7059  mov     rbx, qword ptr [rbp+57h+pExceptionObject+8]
0x1800d705d  mov     edi, 0FFFFFFFFh
0x1800d7062  test    rbx, rbx
0x1800d7065  jz      short loc_1800D709D
0x1800d7067  mov     eax, edi
0x1800d7069  lock xadd [rbx+8], eax
0x1800d706e  cmp     eax, 1
0x1800d7071  jnz     short loc_1800D709D
0x1800d7073  mov     rax, [rbx]
0x1800d7076  mov     rcx, rbx
0x1800d7079  mov     rax, [rax]
0x1800d707c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7081  mov     eax, edi
0x1800d7083  lock xadd [rbx+0Ch], eax
0x1800d7088  cmp     eax, 1
0x1800d708b  jnz     short loc_1800D709D
0x1800d708d  mov     rax, [rbx]
0x1800d7090  mov     rcx, rbx
0x1800d7093  mov     rax, [rax+8]
0x1800d7097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d709c  nop
0x1800d709d  mov     rbx, [rbp+57h+var_90]
0x1800d70a1  test    rbx, rbx
0x1800d70a4  jz      short loc_1800D70DC
0x1800d70a6  mov     eax, edi
0x1800d70a8  lock xadd [rbx+8], eax
0x1800d70ad  cmp     eax, 1
0x1800d70b0  jnz     short loc_1800D70DC
0x1800d70b2  mov     rax, [rbx]
0x1800d70b5  mov     rcx, rbx
0x1800d70b8  mov     rax, [rax]
0x1800d70bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70c0  mov     eax, edi
0x1800d70c2  lock xadd [rbx+0Ch], eax
0x1800d70c7  cmp     eax, 1
0x1800d70ca  jnz     short loc_1800D70DC
0x1800d70cc  mov     rax, [rbx]
0x1800d70cf  mov     rcx, rbx
0x1800d70d2  mov     rax, [rax+8]
0x1800d70d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70db  nop
0x1800d70dc  mov     rbx, [rbp+57h+var_40]
0x1800d70e0  test    rbx, rbx
0x1800d70e3  jz      short loc_1800D7119
0x1800d70e5  mov     eax, edi
0x1800d70e7  lock xadd [rbx+8], eax
0x1800d70ec  cmp     eax, 1
0x1800d70ef  jnz     short loc_1800D7119
0x1800d70f1  mov     rax, [rbx]
0x1800d70f4  mov     rcx, rbx
0x1800d70f7  mov     rax, [rax]
0x1800d70fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70ff  lock xadd [rbx+0Ch], edi
0x1800d7104  cmp     edi, 1
0x1800d7107  jnz     short loc_1800D7119
0x1800d7109  mov     rax, [rbx]
0x1800d710c  mov     rcx, rbx
0x1800d710f  mov     rax, [rax+8]
0x1800d7113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7118  nop
0x1800d7119  lea     rcx, [rbp+57h+var_B0]
0x1800d711d  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800d7122  mov     rcx, [rbp+57h+var_38]
0x1800d7126  xor     rcx, rsp; StackCookie
0x1800d7129  call    __security_check_cookie
0x1800d712e  add     rsp, 0C8h
0x1800d7135  pop     r15
0x1800d7137  pop     r14
0x1800d7139  pop     rdi
0x1800d713a  pop     rsi
0x1800d713b  pop     rbx
0x1800d713c  pop     rbp
0x1800d713d  retn
0x1800d713e  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x1800d7145  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800d7149  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800d714e  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800d7155  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d7159  call    _CxxThrowException_0
```
