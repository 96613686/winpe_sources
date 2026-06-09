# win_dox::CloneableStream::Read(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)

- ea: `0x1800763e0`
- end: `0x1800765ab`
- name: `?Read@CloneableStream@win_dox@@QEAAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b6980`

## callees

- `0x180012468`
- `0x18002db70`
- `0x1800763e0`
- `0x18007684c`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076442`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007642f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007642f`

## string_xrefs

- `0x180076557`: `Call to Read failed with HResult 0x%X.`
- `0x1800764fd`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_dox::CloneableStream::Read(__int64 *a1, unsigned int *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r15
  int v6; // ecx
  signed int v7; // esi
  __int64 v8; // rsi
  _QWORD v11[3]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+60h] [rbp-A8h]
  __int64 v13; // [rsp+68h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v15[512]; // [rsp+118h] [rbp+10h] BYREF

  v11[1] = -2;
  v4 = a1[2];
  v5 = *a1;
  v11[2] = v4 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v6 = *(_DWORD *)(v4 + 52);
  *(_DWORD *)(v4 + 52) = v6 + 1;
  if ( !v6 )
    *(_DWORD *)(v4 + 48) = GetCurrentThreadId();
  LOBYTE(v12) = 1;
  v13 = v4;
  if ( !*(_BYTE *)(v4 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(_QWORD *)v4 != v5 )
    win_dox::Stream::Seek(v4 + 64, v5, 0);
  LODWORD(v11[0]) = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))(**(_QWORD **)(v4 + 64) + 24LL))(
         *(_QWORD *)(v4 + 64),
         *((_QWORD *)a2 + 1),
         *a2,
         v11);
  if ( v7 < 0 )
  {
    memset_0(v15, 0, sizeof(v15));
    StringCchPrintfW(v15, 0x200u, L"Call to Read failed with HResult 0x%X.", (unsigned int)v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x60u,
      v7,
      (struct win_musl::TStringEllipseBase *)v15);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = LODWORD(v11[0]);
  *(_QWORD *)v4 = LODWORD(v11[0]) + v5;
  if ( v4 != -8 )
  {
    if ( (*(_DWORD *)(v4 + 52))-- == 1 )
      *(_DWORD *)(v4 + 48) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  }
  *a1 += v8;
  return LODWORD(v11[0]);
}

```

## disassembly

```asm
0x1800763e0  mov     rax, rsp
0x1800763e3  push    rbp
0x1800763e4  push    rsi
0x1800763e5  push    rdi
0x1800763e6  push    r14
0x1800763e8  push    r15
0x1800763ea  lea     rbp, [rax-448h]
0x1800763f1  sub     rsp, 520h
0x1800763f8  mov     [rsp+540h+var_4F8], 0FFFFFFFFFFFFFFFEh
0x180076401  mov     [rax+18h], rbx
0x180076405  mov     rax, cs:__security_cookie
0x18007640c  xor     rax, rsp
0x18007640f  mov     [rbp+440h+var_30], rax
0x180076416  mov     rsi, rdx
0x180076419  mov     r14, rcx
0x18007641c  mov     rdi, [rcx+10h]
0x180076420  mov     r15, [rcx]
0x180076423  lea     rbx, [rdi+8]
0x180076427  mov     qword ptr [rsp+540h+var_4F0], rbx
0x18007642c  mov     rcx, rbx; lpCriticalSection
0x18007642f  call    cs:__imp_EnterCriticalSection
0x180076435  mov     ecx, [rbx+2Ch]
0x180076438  lea     eax, [rcx+1]
0x18007643b  mov     [rbx+2Ch], eax
0x18007643e  test    ecx, ecx
0x180076440  jnz     short loc_18007644B
0x180076442  call    cs:__imp_GetCurrentThreadId
0x180076448  mov     [rbx+28h], eax
0x18007644b  mov     byte ptr [rsp+540h+var_4E8], 1
0x180076450  mov     [rsp+540h+var_4E0], rdi
0x180076455  cmp     byte ptr [rdi+48h], 0
0x180076459  jz      loc_1800764FD
0x18007645f  cmp     [rdi], r15
0x180076462  jnz     loc_1800764E9
0x180076468  mov     dword ptr [rsp+540h+var_500], 0
0x180076470  mov     rcx, [rdi+40h]
0x180076474  mov     rax, [rcx]
0x180076477  lea     r9, [rsp+540h+var_500]
0x18007647c  mov     r8d, [rsi]
0x18007647f  mov     rdx, [rsi+8]
0x180076483  mov     rax, [rax+18h]
0x180076487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007648c  mov     esi, eax
0x18007648e  test    eax, eax
0x180076490  js      loc_180076543
0x180076496  mov     esi, dword ptr [rsp+540h+var_500]
0x18007649a  lea     rax, [rsi+r15]
0x18007649e  mov     [rdi], rax
0x1800764a1  test    rbx, rbx
0x1800764a4  jz      short loc_1800764BC
0x1800764a6  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x1800764aa  jnz     short loc_1800764B3
0x1800764ac  mov     dword ptr [rbx+28h], 0
0x1800764b3  mov     rcx, rbx; lpCriticalSection
0x1800764b6  call    cs:__imp_LeaveCriticalSection
0x1800764bc  add     [r14], rsi
0x1800764bf  mov     eax, dword ptr [rsp+540h+var_500]
0x1800764c3  mov     rcx, [rbp+440h+var_30]
0x1800764ca  xor     rcx, rsp; StackCookie
0x1800764cd  call    __security_check_cookie
0x1800764d2  mov     rbx, [rsp+540h+arg_10]
0x1800764da  add     rsp, 520h
0x1800764e1  pop     r15
0x1800764e3  pop     r14
0x1800764e5  pop     rdi
0x1800764e6  pop     rsi
0x1800764e7  pop     rbp
0x1800764e8  retn
0x1800764e9  lea     rcx, [rdi+40h]
0x1800764ed  xor     r8d, r8d
0x1800764f0  mov     rdx, r15
0x1800764f3  call    ?Seek@Stream@win_dox@@QEAA_K_JW4Enum@SeekOrigin@2@@Z; win_dox::Stream::Seek(__int64,win_dox::SeekOrigin::Enum)
0x1800764f8  jmp     loc_180076468
0x1800764fd  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x180076504  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180076509  mov     [rsp+540h+var_518], 8000FFFFh; unsigned int
0x180076511  mov     [rsp+540h+var_520], 7Fh; unsigned int
0x180076519  lea     r9, word_180139126
0x180076520  lea     r8, aNoFilename; "(no filename)"
0x180076527  lea     rcx, [rsp+540h+pExceptionObject]; this
0x18007652c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180076531  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180076538  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x18007653d  call    _CxxThrowException_0
0x180076543  xor     edx, edx; Val
0x180076545  mov     r8d, 400h; Size
0x18007654b  lea     rcx, [rbp+440h+var_430]; void *
0x18007654f  call    memset_0
0x180076554  mov     r9d, esi
0x180076557  lea     r8, aCallToReadFail; "Call to Read failed with HResult 0x%X."
0x18007655e  mov     edx, 200h; unsigned __int64
0x180076563  lea     rcx, [rbp+440h+var_430]; wchar_t *
0x180076567  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18007656c  lea     rax, [rbp+440h+var_430]
0x180076570  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180076575  mov     [rsp+540h+var_518], esi; unsigned int
0x180076579  mov     [rsp+540h+var_520], 60h ; '`'; unsigned int
0x180076581  lea     r9, word_180139126
0x180076588  lea     r8, aNoFilename; "(no filename)"
0x18007658f  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180076594  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180076599  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800765a0  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x1800765a5  call    _CxxThrowException_0
```
