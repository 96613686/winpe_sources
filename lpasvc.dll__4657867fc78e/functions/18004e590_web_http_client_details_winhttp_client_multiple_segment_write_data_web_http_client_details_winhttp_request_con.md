# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x18004e590`
- end: `0x18004e9ff`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `1135`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180050120`

## callees

- `0x18000da96`
- `0x18000dac6`
- `0x18000df90`
- `0x18000e430`
- `0x18000e46c`
- `0x18000ec30`
- `0x180037dd0`
- `0x180038ff0`
- `0x180039160`
- `0x180039210`
- `0x180049990`
- `0x18004e230`
- `0x18004e590`
- `0x18004fbe0`
- `0x180063668`
- `0x180081190`
- `0x1800a64d8`
- `0x1800a7ebc`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e774`
- `WINHTTP!WinHttpWriteData` at `0x18004e766`
- `WINHTTP!WinHttpWriteData` at `0x18004e766`

## string_xrefs

- `0x18004e7a1`: `WinHttpWriteData`
- `0x18004e660`: `Error reading outgoing HTTP body from its stream.`

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
  unsigned __int64 v9; // rdx
  void *v10; // rcx
  const void *v11; // rdx
  bool v12; // zf
  DWORD LastError; // ebx
  __int64 v14; // rax
  const struct std::nothrow_t *v15; // rdx
  _BYTE *v16; // rcx
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  DWORD dwNumberOfBytesToWrite[2]; // [rsp+30h] [rbp-69h] BYREF
  const void *v23; // [rsp+38h] [rbp-61h] BYREF
  char v24[8]; // [rsp+40h] [rbp-59h] BYREF
  void *v25; // [rsp+48h] [rbp-51h]
  unsigned __int64 v26; // [rsp+50h] [rbp-49h]
  void *Src; // [rsp+58h] [rbp-41h] BYREF
  volatile signed __int32 *v28; // [rsp+60h] [rbp-39h]
  __int64 v29; // [rsp+68h] [rbp-31h]
  unsigned __int64 v30; // [rsp+70h] [rbp-29h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-21h] BYREF
  __int64 v32; // [rsp+88h] [rbp-11h]
  unsigned __int64 v33; // [rsp+90h] [rbp-9h]
  void *v34[3]; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 v35; // [rsp+B0h] [rbp+17h]

  web::http::client::details::winhttp_request_context::_get_readbuffer(a1, v24);
  v2 = *((_QWORD *)a1 + 18);
  v3 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)a1
                                                                                        + 1))
       + 53);
  if ( !v3 )
    v3 = 0x10000;
  if ( v2 > v3 )
    v2 = v3;
  v23 = 0;
  *(_QWORD *)dwNumberOfBytesToWrite = 0;
  v4 = v25;
  if ( !v25 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)&pExceptionObject, "Invalid streambuf object");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  if ( (*(unsigned __int8 (__fastcall **)(void *, const void **, DWORD *))(*(_QWORD *)v25 + 240LL))(
         v25,
         &v23,
         dwNumberOfBytesToWrite) )
  {
    v5 = *(_QWORD *)dwNumberOfBytesToWrite;
    if ( *(_QWORD *)dwNumberOfBytesToWrite )
    {
      v11 = v23;
      if ( v23 )
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
        v11 = 0;
      }
      *((_QWORD *)a1 + 27) = v11;
      if ( v2 > v5 )
        v2 = v5;
      v12 = *((_QWORD *)a1 + 18) == v2;
      *((_QWORD *)a1 + 18) -= v2;
      if ( v12 )
        *((_DWORD *)a1 + 34) = 0;
      if ( !v11 )
        v11 = (const void *)*((_QWORD *)a1 + 28);
      if ( !WinHttpWriteData(*((HINTERNET *)a1 + 13), v11, v2, 0) )
      {
        LastError = GetLastError();
        pExceptionObject = 0;
        *(_QWORD *)&pExceptionObject = operator new(0x20u);
        v32 = 16;
        v33 = 31;
        strcpy((char *)pExceptionObject, "WinHttpWriteData");
        v14 = web::http::client::details::build_error_msg(&Src);
        web::http::client::details::request_context::report_error(a1, LastError, v14);
        if ( v30 > 0xF )
        {
          v15 = (const struct std::nothrow_t *)(v30 + 1);
          if ( v30 + 1 < 0x1000 )
          {
            v16 = Src;
          }
          else
          {
            v16 = (_BYTE *)*((_QWORD *)Src - 1);
            if ( (unsigned __int64)((_BYTE *)Src - v16 - 8) > 0x1F )
              __fastfail(5u);
            v15 = (const struct std::nothrow_t *)(v30 + 40);
          }
          operator delete(v16, v15);
        }
        v29 = 0;
        v30 = 15;
        LOBYTE(Src) = 0;
        if ( v33 > 0xF )
        {
          v8 = (void *)pExceptionObject;
          v9 = v33 + 1;
          if ( v33 + 1 >= 0x1000 )
          {
            v10 = *(void **)(pExceptionObject - 8);
            if ( (unsigned __int64)(pExceptionObject - (_QWORD)v10 - 8) <= 0x1F )
              goto LABEL_12;
            goto LABEL_36;
          }
LABEL_37:
          operator delete(v8, (const struct std::nothrow_t *)v9);
        }
      }
    }
    else
    {
      (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v4 + 256LL))(v4, &Src);
      v6 = __ExceptionPtrToBool(&Src);
      __ExceptionPtrDestroy(&Src);
      if ( v6 )
      {
        (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v4 + 256LL))(v4, &Src);
        web::http::client::details::request_context::report_exception(a1, &Src);
        goto LABEL_56;
      }
      std::wstring::wstring(v34, L"Error reading outgoing HTTP body from its stream.");
      v7 = GetLastError();
      web::http::client::details::request_context::report_error(a1, v7, v34);
      if ( v35 > 7 )
      {
        v8 = v34[0];
        v9 = 2 * v35 + 2;
        if ( v9 >= 0x1000 )
        {
          v10 = (void *)*((_QWORD *)v34[0] - 1);
          if ( (unsigned __int64)((char *)v34[0] - (char *)v10 - 8) <= 0x1F )
          {
LABEL_12:
            operator delete(v10, (const struct std::nothrow_t *)(v9 + 39));
            goto LABEL_56;
          }
LABEL_36:
          __fastfail(5u);
        }
        goto LABEL_37;
      }
    }
  }
  else
  {
    if ( v2 > *((_QWORD *)a1 + 29) - *((_QWORD *)a1 + 28) )
      std::vector<unsigned char>::resize((char *)a1 + 224, v2);
    *((_QWORD *)a1 + 27) = 0;
    v34[0] = a1;
    v34[1] = &Concurrency::streams::streambuf<unsigned char>::`vftable';
    v17 = v26;
    if ( v26 )
      _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
    v34[2] = v4;
    v35 = v17;
    v18 = *((_QWORD *)a1 + 27);
    if ( !v18 )
      v18 = *((_QWORD *)a1 + 28);
    (*(void (__fastcall **)(void *, void **, __int64, unsigned __int64))(*(_QWORD *)v4 + 168LL))(v4, &Src, v18, v2);
    ___then_V_lambda_1___BF____multiple_segment_write_data_winhttp_client_details_client_http_web__CAXPEAVwinhttp_request_context_4567__Z____task__K_pplx__QEBA_AV__task_X_1___QEAV_lambda_1___BF____multiple_segment_write_data_winhttp_client_details_client_http_web__CAXPEAVwinhttp_request_context_6789__Z__Z(
      &Src,
      &pExceptionObject,
      v34);
    v19 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject + 1);
    if ( *((_QWORD *)&pExceptionObject + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&pExceptionObject + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v20 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v21 = (volatile signed __int32 *)v35;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v35 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
  }
LABEL_56:
  Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v24);
}

```

## disassembly

```asm
0x18004e590  push    rbp
0x18004e592  push    rbx
0x18004e593  push    rsi
0x18004e594  push    rdi
0x18004e595  push    r14
0x18004e597  push    r15
0x18004e599  lea     rbp, [rsp-2Fh]
0x18004e59e  sub     rsp, 0C8h
0x18004e5a5  mov     rax, cs:__security_cookie
0x18004e5ac  xor     rax, rsp
0x18004e5af  mov     [rbp+57h+var_38], rax
0x18004e5b3  mov     rdi, rcx
0x18004e5b6  xor     r15d, r15d
0x18004e5b9  lea     rdx, [rbp+57h+var_B0]
0x18004e5bd  call    ?_get_readbuffer@winhttp_request_context@details@client@http@web@@UEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::winhttp_request_context::_get_readbuffer(void)
0x18004e5c2  nop
0x18004e5c3  mov     rbx, [rdi+90h]
0x18004e5ca  mov     rcx, [rdi+8]; this
0x18004e5ce  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x18004e5d3  mov     rcx, [rax+1A8h]
0x18004e5da  mov     eax, 10000h
0x18004e5df  test    rcx, rcx
0x18004e5e2  cmovz   rcx, rax
0x18004e5e6  cmp     rbx, rcx
0x18004e5e9  cmova   rbx, rcx
0x18004e5ed  mov     [rbp+57h+var_B8], r15
0x18004e5f1  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], r15
0x18004e5f5  mov     rsi, [rbp+57h+var_A8]
0x18004e5f9  test    rsi, rsi
0x18004e5fc  jz      loc_18004E9DE
0x18004e602  mov     rax, [rsi]
0x18004e605  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x18004e609  lea     rdx, [rbp+57h+var_B8]
0x18004e60d  mov     rcx, rsi
0x18004e610  mov     rax, [rax+0F0h]
0x18004e617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e61c  test    al, al
0x18004e61e  jz      loc_18004E86E
0x18004e624  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x18004e628  test    rax, rax
0x18004e62b  jnz     loc_18004E6F7
0x18004e631  mov     rax, [rsi]
0x18004e634  lea     rdx, [rbp+57h+Src]
0x18004e638  mov     rcx, rsi
0x18004e63b  mov     rax, [rax+100h]
0x18004e642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e647  lea     rcx, [rbp+57h+Src]; void *
0x18004e64b  call    ?__ExceptionPtrToBool@@YA_NPEBX@Z_0; __ExceptionPtrToBool(void const *)
0x18004e650  movzx   ebx, al
0x18004e653  lea     rcx, [rbp+57h+Src]; void *
0x18004e657  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x18004e65c  test    bl, bl
0x18004e65e  jnz     short loc_18004E6D0
0x18004e660  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x18004e667  lea     rcx, [rbp+57h+var_58]
0x18004e66b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e670  nop
0x18004e671  call    cs:__imp_GetLastError
0x18004e677  mov     edx, eax
0x18004e679  lea     r8, [rbp+57h+var_58]
0x18004e67d  mov     rcx, rdi
0x18004e680  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x18004e685  nop
0x18004e686  mov     rdx, [rbp+57h+var_40]
0x18004e68a  cmp     rdx, 7
0x18004e68e  jbe     loc_18004E9B9
0x18004e694  mov     rax, [rbp+57h+var_58]
0x18004e698  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18004e6a0  cmp     rdx, 1000h
0x18004e6a7  jb      loc_18004E861
0x18004e6ad  mov     rcx, [rax-8]; void *
0x18004e6b1  sub     rax, rcx
0x18004e6b4  sub     rax, 8
0x18004e6b8  cmp     rax, 1Fh
0x18004e6bc  ja      loc_18004E85A
0x18004e6c2  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18004e6c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e6cb  jmp     loc_18004E9B9
0x18004e6d0  mov     rax, [rsi]
0x18004e6d3  lea     rdx, [rbp+57h+Src]
0x18004e6d7  mov     rcx, rsi
0x18004e6da  mov     rax, [rax+100h]
0x18004e6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6e6  lea     rdx, [rbp+57h+Src]
0x18004e6ea  mov     rcx, rdi
0x18004e6ed  call    ?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z; web::http::client::details::request_context::report_exception(std::exception_ptr)
0x18004e6f2  jmp     loc_18004E9B9
0x18004e6f7  mov     rdx, [rbp+57h+var_B8]
0x18004e6fb  test    rdx, rdx
0x18004e6fe  jnz     short loc_18004E72B
0x18004e700  mov     rcx, [rdi+0E8h]
0x18004e707  sub     rcx, [rdi+0E0h]
0x18004e70e  cmp     rax, rcx
0x18004e711  jbe     short loc_18004E726
0x18004e713  mov     rdx, rax
0x18004e716  lea     rcx, [rdi+0E0h]
0x18004e71d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18004e722  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x18004e726  mov     rdx, r15
0x18004e729  jmp     short loc_18004E732
0x18004e72b  mov     [rdi+0F8h], rax
0x18004e732  mov     [rdi+0D8h], rdx
0x18004e739  cmp     rbx, rax
0x18004e73c  cmova   rbx, rax
0x18004e740  sub     [rdi+90h], rbx
0x18004e747  jnz     short loc_18004E750
0x18004e749  mov     [rdi+88h], r15d
0x18004e750  test    rdx, rdx
0x18004e753  jnz     short loc_18004E75C
0x18004e755  mov     rdx, [rdi+0E0h]; lpBuffer
0x18004e75c  mov     r8d, ebx; dwNumberOfBytesToWrite
0x18004e75f  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x18004e762  mov     rcx, [rdi+68h]; hRequest
0x18004e766  call    cs:__imp_WinHttpWriteData
0x18004e76c  test    eax, eax
0x18004e76e  jnz     loc_18004E9B9
0x18004e774  call    cs:__imp_GetLastError
0x18004e77a  mov     ebx, eax
0x18004e77c  xorps   xmm0, xmm0
0x18004e77f  movups  [rbp+57h+pExceptionObject], xmm0
0x18004e783  mov     ecx, 20h ; ' '; Size
0x18004e788  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e78d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18004e791  mov     [rbp+57h+var_68], 10h
0x18004e799  mov     [rbp+57h+var_60], 1Fh
0x18004e7a1  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x18004e7a8  movups  xmmword ptr [rax], xmm0
0x18004e7ab  mov     byte ptr [rax+10h], 0
0x18004e7af  lea     r8, [rbp+57h+pExceptionObject]
0x18004e7b3  mov     edx, ebx
0x18004e7b5  lea     rcx, [rbp+57h+Src]; Src
0x18004e7b9  call    web__http__client__details__build_error_msg
0x18004e7be  nop
0x18004e7bf  mov     r8, rax
0x18004e7c2  mov     edx, ebx
0x18004e7c4  mov     rcx, rdi
0x18004e7c7  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18004e7cc  nop
0x18004e7cd  mov     rdx, [rbp+57h+var_80]
0x18004e7d1  cmp     rdx, 0Fh
0x18004e7d5  jbe     short loc_18004E80D
0x18004e7d7  mov     rax, [rbp+57h+Src]
0x18004e7db  inc     rdx; struct std::nothrow_t *
0x18004e7de  cmp     rdx, 1000h
0x18004e7e5  jb      short loc_18004E805
0x18004e7e7  mov     rcx, [rax-8]
0x18004e7eb  sub     rax, rcx
0x18004e7ee  sub     rax, 8
0x18004e7f2  cmp     rax, 1Fh
0x18004e7f6  ja      short loc_18004E7FE
0x18004e7f8  add     rdx, 27h ; '''
0x18004e7fc  jmp     short loc_18004E808
0x18004e7fe  mov     ecx, 5
0x18004e803  int     29h; Win8: RtlFailFast(ecx)
0x18004e805  mov     rcx, rax; void *
0x18004e808  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e80d  mov     [rbp+57h+var_88], r15
0x18004e811  mov     [rbp+57h+var_80], 0Fh
0x18004e819  mov     byte ptr [rbp+57h+Src], 0
0x18004e81d  mov     rdx, [rbp+57h+var_60]
0x18004e821  cmp     rdx, 0Fh
0x18004e825  jbe     loc_18004E9B9
0x18004e82b  mov     rax, qword ptr [rbp+57h+pExceptionObject]
0x18004e82f  inc     rdx
0x18004e832  cmp     rdx, 1000h
0x18004e839  jb      short loc_18004E861
0x18004e83b  mov     rcx, [rax-8]; void *
0x18004e83f  sub     rax, rcx
0x18004e842  sub     rax, 8
0x18004e846  cmp     rax, 1Fh
0x18004e84a  ja      short loc_18004E85A
0x18004e84c  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18004e850  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e855  jmp     loc_18004E9B9
0x18004e85a  mov     ecx, 5
0x18004e85f  int     29h; Win8: RtlFailFast(ecx)
0x18004e861  mov     rcx, rax; void *
0x18004e864  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e869  jmp     loc_18004E9B9
0x18004e86e  mov     rax, [rdi+0E8h]
0x18004e875  sub     rax, [rdi+0E0h]
0x18004e87c  cmp     rbx, rax
0x18004e87f  jbe     short loc_18004E890
0x18004e881  mov     rdx, rbx
0x18004e884  lea     rcx, [rdi+0E0h]
0x18004e88b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18004e890  mov     [rdi+0D8h], r15
0x18004e897  mov     [rbp+57h+var_58], rdi
0x18004e89b  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x18004e8a2  mov     [rbp+57h+var_50], rax
0x18004e8a6  mov     rax, [rbp+57h+var_A0]
0x18004e8aa  test    rax, rax
0x18004e8ad  jz      short loc_18004E8B3
0x18004e8af  lock inc dword ptr [rax+8]
0x18004e8b3  mov     [rbp+57h+var_48], rsi
0x18004e8b7  mov     [rbp+57h+var_40], rax
0x18004e8bb  mov     r8, [rdi+0D8h]
0x18004e8c2  test    r8, r8
0x18004e8c5  jnz     short loc_18004E8CE
0x18004e8c7  mov     r8, [rdi+0E0h]
0x18004e8ce  mov     rax, [rsi]
0x18004e8d1  mov     r9, rbx
0x18004e8d4  lea     rdx, [rbp+57h+Src]
0x18004e8d8  mov     rcx, rsi
0x18004e8db  mov     rax, [rax+0A8h]
0x18004e8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8e7  nop
0x18004e8e8  lea     r8, [rbp+57h+var_58]
0x18004e8ec  lea     rdx, [rbp+57h+pExceptionObject]
0x18004e8f0  lea     rcx, [rbp+57h+Src]
0x18004e8f4  call    ??$then@V_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@4567@@Z@@?$task@_K@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@6789@@Z@@Z; pplx::task<unsigned __int64>::then<`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_>(`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_ &&)
0x18004e8f9  mov     rbx, qword ptr [rbp+57h+pExceptionObject+8]
0x18004e8fd  mov     edi, 0FFFFFFFFh
0x18004e902  test    rbx, rbx
0x18004e905  jz      short loc_18004E93D
0x18004e907  mov     eax, edi
0x18004e909  lock xadd [rbx+8], eax
0x18004e90e  cmp     eax, 1
0x18004e911  jnz     short loc_18004E93D
0x18004e913  mov     rax, [rbx]
0x18004e916  mov     rcx, rbx
0x18004e919  mov     rax, [rax]
0x18004e91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e921  mov     eax, edi
0x18004e923  lock xadd [rbx+0Ch], eax
0x18004e928  cmp     eax, 1
0x18004e92b  jnz     short loc_18004E93D
0x18004e92d  mov     rax, [rbx]
0x18004e930  mov     rcx, rbx
0x18004e933  mov     rax, [rax+8]
0x18004e937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e93c  nop
0x18004e93d  mov     rbx, [rbp+57h+var_90]
0x18004e941  test    rbx, rbx
0x18004e944  jz      short loc_18004E97C
0x18004e946  mov     eax, edi
0x18004e948  lock xadd [rbx+8], eax
0x18004e94d  cmp     eax, 1
0x18004e950  jnz     short loc_18004E97C
0x18004e952  mov     rax, [rbx]
0x18004e955  mov     rcx, rbx
0x18004e958  mov     rax, [rax]
0x18004e95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e960  mov     eax, edi
0x18004e962  lock xadd [rbx+0Ch], eax
0x18004e967  cmp     eax, 1
0x18004e96a  jnz     short loc_18004E97C
0x18004e96c  mov     rax, [rbx]
0x18004e96f  mov     rcx, rbx
0x18004e972  mov     rax, [rax+8]
0x18004e976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e97b  nop
0x18004e97c  mov     rbx, [rbp+57h+var_40]
0x18004e980  test    rbx, rbx
0x18004e983  jz      short loc_18004E9B9
0x18004e985  mov     eax, edi
0x18004e987  lock xadd [rbx+8], eax
0x18004e98c  cmp     eax, 1
0x18004e98f  jnz     short loc_18004E9B9
0x18004e991  mov     rax, [rbx]
0x18004e994  mov     rcx, rbx
0x18004e997  mov     rax, [rax]
0x18004e99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e99f  lock xadd [rbx+0Ch], edi
0x18004e9a4  cmp     edi, 1
0x18004e9a7  jnz     short loc_18004E9B9
0x18004e9a9  mov     rax, [rbx]
0x18004e9ac  mov     rcx, rbx
0x18004e9af  mov     rax, [rax+8]
0x18004e9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9b8  nop
0x18004e9b9  lea     rcx, [rbp+57h+var_B0]
0x18004e9bd  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18004e9c2  mov     rcx, [rbp+57h+var_38]
0x18004e9c6  xor     rcx, rsp; StackCookie
0x18004e9c9  call    __security_check_cookie
0x18004e9ce  add     rsp, 0C8h
0x18004e9d5  pop     r15
0x18004e9d7  pop     r14
0x18004e9d9  pop     rdi
0x18004e9da  pop     rsi
0x18004e9db  pop     rbx
0x18004e9dc  pop     rbp
0x18004e9dd  retn
0x18004e9de  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x18004e9e5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004e9e9  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18004e9ee  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18004e9f5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004e9f9  call    _CxxThrowException_0
```
