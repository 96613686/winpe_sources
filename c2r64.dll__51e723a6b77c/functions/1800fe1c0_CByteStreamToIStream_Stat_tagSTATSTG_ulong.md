# CByteStreamToIStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800fe1c0`
- end: `0x1800fe3da`
- name: `?Stat@CByteStreamToIStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `538`
- prototype: `int(CByteStreamToIStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180012bf8`
- `0x1800264b4`
- `0x18003651c`
- `0x18003e690`
- `0x180044b44`
- `0x180052cd0`
- `0x1800fe1c0`
- `0x1800fe3dc`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800fe1fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800fe1fe`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800fe291`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800fe390`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800fe291`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800fe390`
- `ole32!CoTaskMemAlloc` at `0x1800fe25a`
- `ole32!CoTaskMemAlloc` at `0x1800fe352`
- `ole32!CoTaskMemAlloc` at `0x1800fe25a`
- `ole32!CoTaskMemAlloc` at `0x1800fe352`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CByteStreamToIStream::Stat(CByteStreamToIStream *this, struct tagSTATSTG *a2, unsigned int a3)
{
  int v6; // edi
  __int64 v7; // rcx
  SIZE_T v8; // rax
  OLECHAR *v9; // rax
  const wchar_t *v10; // r8
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rbx
  rsize_t v12; // rbx
  SIZE_T v13; // rax
  OLECHAR *v14; // rax
  rsize_t *v15; // rax
  __int64 v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  rsize_t v19; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v20[16]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Source[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !*((_DWORD *)this - 4) || *((_DWORD *)this - 4) == GetCurrentThreadId() )
  {
    v6 = CByteStreamWrapperBase::StatInternal((CByteStreamToIStream *)((char *)this - 96), a2, a3, STGTY_STREAM);
    if ( v6 >= 0 && (a3 & 1) == 0 )
    {
      _mm_lfence();
      v7 = *((_QWORD *)this + 5);
      if ( v7 )
      {
        v8 = MsoCbBufSizeT<wchar_t>(v7);
        v9 = (OLECHAR *)CoTaskMemAlloc(v8);
        a2->pwcsName = v9;
        if ( v9 )
        {
          _mm_lfence();
          v6 = 0;
          v10 = (const wchar_t *)((char *)this + 24);
          if ( *((_QWORD *)this + 6) > 7u )
            v10 = *(const wchar_t **)v10;
          wcsncpy_s(v9, *((_QWORD *)this + 5) + 1LL, v10, *((_QWORD *)this + 5));
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        v18 = 0;
        if ( *((_QWORD *)this - 7) )
        {
          _mm_lfence();
          v11 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this - 56);
          if ( (**v11)(v11, &GUID_f687ca79_a127_4e8d_ac44_d207ebe40d3f, &v18) >= 0 )
          {
            if ( !v18 )
              CrashWithRecovery(0x1E3C3840u, 0);
            v6 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v18 + 32LL))(v18, Source, 260);
            if ( v6 >= 0 )
            {
              v12 = -1;
              do
                ++v12;
              while ( Source[v12] );
              v19 = v12;
              v13 = MsoCbBufSizeT<wchar_t>(v12);
              v14 = (OLECHAR *)CoTaskMemAlloc(v13);
              a2->pwcsName = v14;
              if ( v14 )
              {
                _mm_lfence();
                v6 = 0;
                v15 = (rsize_t *)SafeInt<unsigned __int64,safeint_exception_handlers::SafeInt_InvalidParameter>::operator+<int>(
                                   &v19,
                                   v20,
                                   1);
                wcsncpy_s(a2->pwcsName, *v15, Source, v12);
              }
              else
              {
                v6 = -2147024882;
              }
            }
          }
          v16 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
        }
      }
    }
  }
  else
  {
    MsoShipAssertTagProc(7116952);
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800fe1c0  mov     [rsp-8+arg_10], rbx
0x1800fe1c5  push    rbp
0x1800fe1c6  push    rsi
0x1800fe1c7  push    rdi
0x1800fe1c8  push    r14
0x1800fe1ca  push    r15
0x1800fe1cc  lea     rbp, [rsp-160h]
0x1800fe1d4  sub     rsp, 260h
0x1800fe1db  mov     rax, cs:__security_cookie
0x1800fe1e2  xor     rax, rsp
0x1800fe1e5  mov     [rbp+180h+var_30], rax
0x1800fe1ec  mov     esi, r8d
0x1800fe1ef  mov     r14, rdx
0x1800fe1f2  mov     rbx, rcx
0x1800fe1f5  xor     r15d, r15d
0x1800fe1f8  cmp     [rcx-10h], r15d
0x1800fe1fc  jz      short loc_1800FE21D
0x1800fe1fe  call    cs:__imp_GetCurrentThreadId
0x1800fe204  cmp     [rbx-10h], eax
0x1800fe207  jz      short loc_1800FE21D
0x1800fe209  mov     ecx, 6C9898h
0x1800fe20e  call    MsoShipAssertTagProc
0x1800fe213  mov     edi, 80004005h
0x1800fe218  jmp     loc_1800FE3B2
0x1800fe21d  mov     r9d, 2; enum tagSTGTY
0x1800fe223  mov     r8d, esi; unsigned int
0x1800fe226  mov     rdx, r14; struct tagSTATSTG *
0x1800fe229  lea     rcx, [rbx-60h]; this
0x1800fe22d  call    ?StatInternal@CByteStreamWrapperBase@@IEAAJPEAUtagSTATSTG@@KW4tagSTGTY@@@Z; CByteStreamWrapperBase::StatInternal(tagSTATSTG *,ulong,tagSTGTY)
0x1800fe232  mov     edi, eax
0x1800fe234  test    eax, eax
0x1800fe236  js      loc_1800FE3B2
0x1800fe23c  test    sil, 1
0x1800fe240  jnz     loc_1800FE3B2
0x1800fe246  lfence
0x1800fe249  mov     rcx, [rbx+28h]
0x1800fe24d  test    rcx, rcx
0x1800fe250  jz      short loc_1800FE29C
0x1800fe252  call    ??$MsoCbBufSizeT@_W@@YA_K_K00@Z; MsoCbBufSizeT<wchar_t>(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800fe257  mov     rcx, rax; cb
0x1800fe25a  call    cs:__imp_CoTaskMemAlloc
0x1800fe260  mov     [r14], rax
0x1800fe263  test    rax, rax
0x1800fe266  jnz     short loc_1800FE272
0x1800fe268  mov     edi, 8007000Eh
0x1800fe26d  jmp     loc_1800FE3B2
0x1800fe272  lfence
0x1800fe275  mov     edi, r15d
0x1800fe278  mov     r9, [rbx+28h]; MaxCount
0x1800fe27c  lea     r8, [rbx+18h]
0x1800fe280  cmp     qword ptr [r8+18h], 7
0x1800fe285  jbe     short loc_1800FE28A
0x1800fe287  mov     r8, [r8]; Source
0x1800fe28a  lea     rdx, [r9+1]; SizeInWords
0x1800fe28e  mov     rcx, rax; Destination
0x1800fe291  call    cs:__imp_wcsncpy_s
0x1800fe297  jmp     loc_1800FE3B2
0x1800fe29c  mov     [rsp+280h+var_260], r15
0x1800fe2a1  lea     rcx, [rbx-38h]
0x1800fe2a5  cmp     [rcx], r15
0x1800fe2a8  jz      loc_1800FE3B2
0x1800fe2ae  lfence
0x1800fe2b1  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800fe2b6  mov     rbx, rax
0x1800fe2b9  mov     rcx, [rax]
0x1800fe2bc  mov     rsi, [rcx]
0x1800fe2bf  mov     rcx, [rsp+280h+var_260]
0x1800fe2c4  test    rcx, rcx
0x1800fe2c7  jz      short loc_1800FE2D6
0x1800fe2c9  mov     rdx, [rcx]
0x1800fe2cc  mov     rax, [rdx+10h]
0x1800fe2d0  call    cs:__guard_dispatch_icall_fptr
0x1800fe2d6  lea     r8, [rsp+280h+var_260]
0x1800fe2db  lea     rdx, _GUID_f687ca79_a127_4e8d_ac44_d207ebe40d3f
0x1800fe2e2  mov     rcx, rbx
0x1800fe2e5  mov     rax, rsi
0x1800fe2e8  call    cs:__guard_dispatch_icall_fptr
0x1800fe2ee  test    eax, eax
0x1800fe2f0  js      loc_1800FE396
0x1800fe2f6  mov     rcx, [rsp+280h+var_260]
0x1800fe2fb  test    rcx, rcx
0x1800fe2fe  jnz     short loc_1800FE311
0x1800fe300  xor     edx, edx; struct CrashContext *
0x1800fe302  mov     ecx, 1E3C3840h; unsigned int
0x1800fe307  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fe311  mov     rax, [rcx]
0x1800fe314  mov     r8d, 104h
0x1800fe31a  lea     rdx, [rsp+280h+Source]
0x1800fe31f  mov     rax, [rax+20h]
0x1800fe323  call    cs:__guard_dispatch_icall_fptr
0x1800fe329  mov     edi, eax
0x1800fe32b  test    eax, eax
0x1800fe32d  js      short loc_1800FE396
0x1800fe32f  lea     rax, [rsp+280h+Source]
0x1800fe334  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe338  inc     rbx
0x1800fe33b  cmp     [rax+rbx*2], r15w
0x1800fe340  jnz     short loc_1800FE338
0x1800fe342  mov     [rsp+280h+var_258], rbx
0x1800fe347  mov     rcx, rbx
0x1800fe34a  call    ??$MsoCbBufSizeT@_W@@YA_K_K00@Z; MsoCbBufSizeT<wchar_t>(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800fe34f  mov     rcx, rax; cb
0x1800fe352  call    cs:__imp_CoTaskMemAlloc
0x1800fe358  mov     [r14], rax
0x1800fe35b  test    rax, rax
0x1800fe35e  jnz     short loc_1800FE367
0x1800fe360  mov     edi, 8007000Eh
0x1800fe365  jmp     short loc_1800FE396
0x1800fe367  lfence
0x1800fe36a  mov     edi, r15d
0x1800fe36d  mov     r8d, 1
0x1800fe373  lea     rdx, [rsp+280h+var_250]
0x1800fe378  lea     rcx, [rsp+280h+var_258]
0x1800fe37d  call    ??$?HH@?$SafeInt@_KVSafeInt_InvalidParameter@safeint_exception_handlers@@@@QEBA?AV0@H@Z; SafeInt<unsigned __int64,safeint_exception_handlers::SafeInt_InvalidParameter>::operator+<int>(int)
0x1800fe382  mov     r9, rbx; MaxCount
0x1800fe385  lea     r8, [rsp+280h+Source]; Source
0x1800fe38a  mov     rdx, [rax]; SizeInWords
0x1800fe38d  mov     rcx, [r14]; Destination
0x1800fe390  call    cs:__imp_wcsncpy_s
0x1800fe396  mov     rcx, [rsp+280h+var_260]
0x1800fe39b  test    rcx, rcx
0x1800fe39e  jz      short loc_1800FE3B2
0x1800fe3a0  mov     [rsp+280h+var_260], r15
0x1800fe3a5  mov     rax, [rcx]
0x1800fe3a8  mov     rax, [rax+10h]
0x1800fe3ac  call    cs:__guard_dispatch_icall_fptr
0x1800fe3b2  mov     eax, edi
0x1800fe3b4  mov     rcx, [rbp+180h+var_30]
0x1800fe3bb  xor     rcx, rsp; StackCookie
0x1800fe3be  call    __security_check_cookie
0x1800fe3c3  mov     rbx, [rsp+280h+arg_10]
0x1800fe3cb  add     rsp, 260h
0x1800fe3d2  pop     r15
0x1800fe3d4  pop     r14
0x1800fe3d6  pop     rdi
0x1800fe3d7  pop     rsi
0x1800fe3d8  pop     rbp
0x1800fe3d9  retn
```
