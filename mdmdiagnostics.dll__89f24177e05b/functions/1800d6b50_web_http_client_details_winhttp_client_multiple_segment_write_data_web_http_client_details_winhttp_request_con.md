# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x1800d6b50`
- end: `0x1800d6fbf`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `1135`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7f10`

## callees

- `0x180016ca3`
- `0x180016caf`
- `0x180019000`
- `0x180019024`
- `0x180019508`
- `0x180019ff4`
- `0x180020470`
- `0x18004c230`
- `0x1800bd230`
- `0x1800be450`
- `0x1800be5c0`
- `0x1800be670`
- `0x1800d2f10`
- `0x1800d6a60`
- `0x1800d6b50`
- `0x1800d79d0`
- `0x1800e66dc`
- `0x18013e8bc`
- `0x180191010`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800d6d26`
- `WINHTTP!WinHttpWriteData` at `0x1800d6d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6d34`

## string_xrefs

- `0x1800d6d61`: `WinHttpWriteData`
- `0x1800d6c20`: `Error reading outgoing HTTP body from its stream.`

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
0x1800d6b50  push    rbp
0x1800d6b52  push    rbx
0x1800d6b53  push    rsi
0x1800d6b54  push    rdi
0x1800d6b55  push    r14
0x1800d6b57  push    r15
0x1800d6b59  lea     rbp, [rsp-2Fh]
0x1800d6b5e  sub     rsp, 0C8h
0x1800d6b65  mov     rax, cs:__security_cookie
0x1800d6b6c  xor     rax, rsp
0x1800d6b6f  mov     [rbp+57h+var_38], rax
0x1800d6b73  mov     rdi, rcx
0x1800d6b76  xor     r15d, r15d
0x1800d6b79  lea     rdx, [rbp+57h+var_B0]
0x1800d6b7d  call    ?_get_readbuffer@winhttp_request_context@details@client@http@web@@UEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::winhttp_request_context::_get_readbuffer(void)
0x1800d6b82  nop
0x1800d6b83  mov     rbx, [rdi+90h]
0x1800d6b8a  mov     rcx, [rdi+8]; this
0x1800d6b8e  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800d6b93  mov     rcx, [rax+1A0h]
0x1800d6b9a  mov     eax, 10000h
0x1800d6b9f  test    rcx, rcx
0x1800d6ba2  cmovz   rcx, rax
0x1800d6ba6  cmp     rbx, rcx
0x1800d6ba9  cmova   rbx, rcx
0x1800d6bad  mov     [rbp+57h+var_B8], r15
0x1800d6bb1  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], r15
0x1800d6bb5  mov     rsi, [rbp+57h+var_A8]
0x1800d6bb9  test    rsi, rsi
0x1800d6bbc  jz      loc_1800D6F9E
0x1800d6bc2  mov     rax, [rsi]
0x1800d6bc5  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x1800d6bc9  lea     rdx, [rbp+57h+var_B8]
0x1800d6bcd  mov     rcx, rsi
0x1800d6bd0  mov     rax, [rax+0F0h]
0x1800d6bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6bdc  test    al, al
0x1800d6bde  jz      loc_1800D6E2E
0x1800d6be4  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800d6be8  test    rax, rax
0x1800d6beb  jnz     loc_1800D6CB7
0x1800d6bf1  mov     rax, [rsi]
0x1800d6bf4  lea     rdx, [rbp+57h+Block]
0x1800d6bf8  mov     rcx, rsi
0x1800d6bfb  mov     rax, [rax+100h]
0x1800d6c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c07  lea     rcx, [rbp+57h+Block]; void *
0x1800d6c0b  call    ?__ExceptionPtrToBool@@YA_NPEBX@Z_0; __ExceptionPtrToBool(void const *)
0x1800d6c10  movzx   ebx, al
0x1800d6c13  lea     rcx, [rbp+57h+Block]; void *
0x1800d6c17  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800d6c1c  test    bl, bl
0x1800d6c1e  jnz     short loc_1800D6C90
0x1800d6c20  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x1800d6c27  lea     rcx, [rbp+57h+var_58]
0x1800d6c2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d6c30  nop
0x1800d6c31  call    cs:__imp_GetLastError
0x1800d6c37  mov     edx, eax
0x1800d6c39  lea     r8, [rbp+57h+var_58]
0x1800d6c3d  mov     rcx, rdi
0x1800d6c40  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x1800d6c45  nop
0x1800d6c46  mov     rdx, [rbp+57h+var_40]
0x1800d6c4a  cmp     rdx, 7
0x1800d6c4e  jbe     loc_1800D6F79
0x1800d6c54  mov     rax, [rbp+57h+var_58]
0x1800d6c58  lea     rdx, ds:2[rdx*2]
0x1800d6c60  cmp     rdx, 1000h
0x1800d6c67  jb      loc_1800D6E21
0x1800d6c6d  mov     rcx, [rax-8]; Block
0x1800d6c71  sub     rax, rcx
0x1800d6c74  sub     rax, 8
0x1800d6c78  cmp     rax, 1Fh
0x1800d6c7c  ja      loc_1800D6E1A
0x1800d6c82  add     rdx, 27h ; '''
0x1800d6c86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6c8b  jmp     loc_1800D6F79
0x1800d6c90  mov     rax, [rsi]
0x1800d6c93  lea     rdx, [rbp+57h+Block]
0x1800d6c97  mov     rcx, rsi
0x1800d6c9a  mov     rax, [rax+100h]
0x1800d6ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ca6  lea     rdx, [rbp+57h+Block]
0x1800d6caa  mov     rcx, rdi
0x1800d6cad  call    ?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z; web::http::client::details::request_context::report_exception(std::exception_ptr)
0x1800d6cb2  jmp     loc_1800D6F79
0x1800d6cb7  mov     rdx, [rbp+57h+var_B8]
0x1800d6cbb  test    rdx, rdx
0x1800d6cbe  jnz     short loc_1800D6CEB
0x1800d6cc0  mov     rcx, [rdi+0E8h]
0x1800d6cc7  sub     rcx, [rdi+0E0h]
0x1800d6cce  cmp     rax, rcx
0x1800d6cd1  jbe     short loc_1800D6CE6
0x1800d6cd3  mov     rdx, rax
0x1800d6cd6  lea     rcx, [rdi+0E0h]
0x1800d6cdd  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800d6ce2  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800d6ce6  mov     rdx, r15
0x1800d6ce9  jmp     short loc_1800D6CF2
0x1800d6ceb  mov     [rdi+0F8h], rax
0x1800d6cf2  mov     [rdi+0D8h], rdx
0x1800d6cf9  cmp     rbx, rax
0x1800d6cfc  cmova   rbx, rax
0x1800d6d00  sub     [rdi+90h], rbx
0x1800d6d07  jnz     short loc_1800D6D10
0x1800d6d09  mov     [rdi+88h], r15d
0x1800d6d10  test    rdx, rdx
0x1800d6d13  jnz     short loc_1800D6D1C
0x1800d6d15  mov     rdx, [rdi+0E0h]; lpBuffer
0x1800d6d1c  mov     r8d, ebx; dwNumberOfBytesToWrite
0x1800d6d1f  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800d6d22  mov     rcx, [rdi+68h]; hRequest
0x1800d6d26  call    cs:__imp_WinHttpWriteData
0x1800d6d2c  test    eax, eax
0x1800d6d2e  jnz     loc_1800D6F79
0x1800d6d34  call    cs:__imp_GetLastError
0x1800d6d3a  mov     ebx, eax
0x1800d6d3c  xorps   xmm0, xmm0
0x1800d6d3f  movups  [rbp+57h+pExceptionObject], xmm0
0x1800d6d43  mov     ecx, 20h ; ' '; Size
0x1800d6d48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6d4d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800d6d51  mov     [rbp+57h+var_68], 10h
0x1800d6d59  mov     [rbp+57h+var_60], 1Fh
0x1800d6d61  movups  xmm0, xmmword ptr cs:aWinhttpwriteda; "WinHttpWriteData"
0x1800d6d68  movups  xmmword ptr [rax], xmm0
0x1800d6d6b  mov     byte ptr [rax+10h], 0
0x1800d6d6f  lea     r8, [rbp+57h+pExceptionObject]
0x1800d6d73  mov     edx, ebx
0x1800d6d75  lea     rcx, [rbp+57h+Block]; Src
0x1800d6d79  call    web__http__client__details__build_error_msg
0x1800d6d7e  nop
0x1800d6d7f  mov     r8, rax
0x1800d6d82  mov     edx, ebx
0x1800d6d84  mov     rcx, rdi
0x1800d6d87  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d6d8c  nop
0x1800d6d8d  mov     rdx, [rbp+57h+var_80]
0x1800d6d91  cmp     rdx, 0Fh
0x1800d6d95  jbe     short loc_1800D6DCD
0x1800d6d97  mov     rax, [rbp+57h+Block]
0x1800d6d9b  inc     rdx
0x1800d6d9e  cmp     rdx, 1000h
0x1800d6da5  jb      short loc_1800D6DC5
0x1800d6da7  mov     rcx, [rax-8]
0x1800d6dab  sub     rax, rcx
0x1800d6dae  sub     rax, 8
0x1800d6db2  cmp     rax, 1Fh
0x1800d6db6  ja      short loc_1800D6DBE
0x1800d6db8  add     rdx, 27h ; '''
0x1800d6dbc  jmp     short loc_1800D6DC8
0x1800d6dbe  mov     ecx, 5
0x1800d6dc3  int     29h; Win8: RtlFailFast(ecx)
0x1800d6dc5  mov     rcx, rax; Block
0x1800d6dc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6dcd  mov     [rbp+57h+var_88], r15
0x1800d6dd1  mov     [rbp+57h+var_80], 0Fh
0x1800d6dd9  mov     byte ptr [rbp+57h+Block], 0
0x1800d6ddd  mov     rdx, [rbp+57h+var_60]
0x1800d6de1  cmp     rdx, 0Fh
0x1800d6de5  jbe     loc_1800D6F79
0x1800d6deb  mov     rax, qword ptr [rbp+57h+pExceptionObject]
0x1800d6def  inc     rdx
0x1800d6df2  cmp     rdx, 1000h
0x1800d6df9  jb      short loc_1800D6E21
0x1800d6dfb  mov     rcx, [rax-8]; Block
0x1800d6dff  sub     rax, rcx
0x1800d6e02  sub     rax, 8
0x1800d6e06  cmp     rax, 1Fh
0x1800d6e0a  ja      short loc_1800D6E1A
0x1800d6e0c  add     rdx, 27h ; '''
0x1800d6e10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6e15  jmp     loc_1800D6F79
0x1800d6e1a  mov     ecx, 5
0x1800d6e1f  int     29h; Win8: RtlFailFast(ecx)
0x1800d6e21  mov     rcx, rax; Block
0x1800d6e24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6e29  jmp     loc_1800D6F79
0x1800d6e2e  mov     rax, [rdi+0E8h]
0x1800d6e35  sub     rax, [rdi+0E0h]
0x1800d6e3c  cmp     rbx, rax
0x1800d6e3f  jbe     short loc_1800D6E50
0x1800d6e41  mov     rdx, rbx
0x1800d6e44  lea     rcx, [rdi+0E0h]
0x1800d6e4b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800d6e50  mov     [rdi+0D8h], r15
0x1800d6e57  mov     [rbp+57h+var_58], rdi
0x1800d6e5b  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x1800d6e62  mov     [rbp+57h+var_50], rax
0x1800d6e66  mov     rax, [rbp+57h+var_A0]
0x1800d6e6a  test    rax, rax
0x1800d6e6d  jz      short loc_1800D6E73
0x1800d6e6f  lock inc dword ptr [rax+8]
0x1800d6e73  mov     [rbp+57h+var_48], rsi
0x1800d6e77  mov     [rbp+57h+var_40], rax
0x1800d6e7b  mov     r8, [rdi+0D8h]
0x1800d6e82  test    r8, r8
0x1800d6e85  jnz     short loc_1800D6E8E
0x1800d6e87  mov     r8, [rdi+0E0h]
0x1800d6e8e  mov     rax, [rsi]
0x1800d6e91  mov     r9, rbx
0x1800d6e94  lea     rdx, [rbp+57h+Block]
0x1800d6e98  mov     rcx, rsi
0x1800d6e9b  mov     rax, [rax+0A8h]
0x1800d6ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ea7  nop
0x1800d6ea8  lea     r8, [rbp+57h+var_58]
0x1800d6eac  lea     rdx, [rbp+57h+pExceptionObject]
0x1800d6eb0  lea     rcx, [rbp+57h+Block]
0x1800d6eb4  call    ??$then@V_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@4567@@Z@@?$task@_K@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@6789@@Z@@Z; pplx::task<unsigned __int64>::then<`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_>(`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_ &&)
0x1800d6eb9  mov     rbx, qword ptr [rbp+57h+pExceptionObject+8]
0x1800d6ebd  mov     edi, 0FFFFFFFFh
0x1800d6ec2  test    rbx, rbx
0x1800d6ec5  jz      short loc_1800D6EFD
0x1800d6ec7  mov     eax, edi
0x1800d6ec9  lock xadd [rbx+8], eax
0x1800d6ece  cmp     eax, 1
0x1800d6ed1  jnz     short loc_1800D6EFD
0x1800d6ed3  mov     rax, [rbx]
0x1800d6ed6  mov     rcx, rbx
0x1800d6ed9  mov     rax, [rax]
0x1800d6edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ee1  mov     eax, edi
0x1800d6ee3  lock xadd [rbx+0Ch], eax
0x1800d6ee8  cmp     eax, 1
0x1800d6eeb  jnz     short loc_1800D6EFD
0x1800d6eed  mov     rax, [rbx]
0x1800d6ef0  mov     rcx, rbx
0x1800d6ef3  mov     rax, [rax+8]
0x1800d6ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6efc  nop
0x1800d6efd  mov     rbx, [rbp+57h+var_90]
0x1800d6f01  test    rbx, rbx
0x1800d6f04  jz      short loc_1800D6F3C
0x1800d6f06  mov     eax, edi
0x1800d6f08  lock xadd [rbx+8], eax
0x1800d6f0d  cmp     eax, 1
0x1800d6f10  jnz     short loc_1800D6F3C
0x1800d6f12  mov     rax, [rbx]
0x1800d6f15  mov     rcx, rbx
0x1800d6f18  mov     rax, [rax]
0x1800d6f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f20  mov     eax, edi
0x1800d6f22  lock xadd [rbx+0Ch], eax
0x1800d6f27  cmp     eax, 1
0x1800d6f2a  jnz     short loc_1800D6F3C
0x1800d6f2c  mov     rax, [rbx]
0x1800d6f2f  mov     rcx, rbx
0x1800d6f32  mov     rax, [rax+8]
0x1800d6f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f3b  nop
0x1800d6f3c  mov     rbx, [rbp+57h+var_40]
0x1800d6f40  test    rbx, rbx
0x1800d6f43  jz      short loc_1800D6F79
0x1800d6f45  mov     eax, edi
0x1800d6f47  lock xadd [rbx+8], eax
0x1800d6f4c  cmp     eax, 1
0x1800d6f4f  jnz     short loc_1800D6F79
0x1800d6f51  mov     rax, [rbx]
0x1800d6f54  mov     rcx, rbx
0x1800d6f57  mov     rax, [rax]
0x1800d6f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f5f  lock xadd [rbx+0Ch], edi
0x1800d6f64  cmp     edi, 1
0x1800d6f67  jnz     short loc_1800D6F79
0x1800d6f69  mov     rax, [rbx]
0x1800d6f6c  mov     rcx, rbx
0x1800d6f6f  mov     rax, [rax+8]
0x1800d6f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f78  nop
0x1800d6f79  lea     rcx, [rbp+57h+var_B0]
0x1800d6f7d  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800d6f82  mov     rcx, [rbp+57h+var_38]
0x1800d6f86  xor     rcx, rsp; StackCookie
0x1800d6f89  call    __security_check_cookie
0x1800d6f8e  add     rsp, 0C8h
0x1800d6f95  pop     r15
0x1800d6f97  pop     r14
0x1800d6f99  pop     rdi
0x1800d6f9a  pop     rsi
0x1800d6f9b  pop     rbx
0x1800d6f9c  pop     rbp
0x1800d6f9d  retn
0x1800d6f9e  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x1800d6fa5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800d6fa9  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800d6fae  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800d6fb5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d6fb9  call    _CxxThrowException_0
```
