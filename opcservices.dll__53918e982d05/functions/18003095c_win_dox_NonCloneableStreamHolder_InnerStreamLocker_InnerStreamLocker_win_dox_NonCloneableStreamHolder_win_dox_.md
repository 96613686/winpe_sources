# win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(win_dox::NonCloneableStreamHolder *,win_dox::NonCloneableStreamHolder::MethodType)

- ea: `0x18003095c`
- end: `0x180030a3c`
- name: `??0InnerStreamLocker@NonCloneableStreamHolder@win_dox@@QEAA@PEAV12@W4MethodType@12@@Z`
- size: `224`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18002f858`
- `0x1800dfcd0`
- `0x1800dfd5c`
- `0x1800dfdf0`
- `0x1800dfeec`
- `0x1800dff50`
- `0x1800dffe0`
- `0x1800e0060`

## callees

- `0x18002db70`
- `0x18003095c`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800309b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800309b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003099f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003099f`

## string_xrefs

- `0x1800309f6`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v6; // ecx
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  *(_QWORD *)a1 = a2 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  v6 = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a2 + 52) = v6 + 1;
  if ( !v6 )
    *(_DWORD *)(a2 + 48) = GetCurrentThreadId();
  *(_BYTE *)(a1 + 8) = a3 == 1;
  *(_QWORD *)(a1 + 16) = a2;
  if ( !*(_BYTE *)(a2 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18003095c  mov     rax, rsp
0x18003095f  push    rdi
0x180030960  sub     rsp, 100h
0x180030967  mov     [rsp+108h+var_C8], 0FFFFFFFFFFFFFFFEh
0x180030970  mov     [rax+10h], rbx
0x180030974  mov     [rax+18h], rsi
0x180030978  mov     rax, cs:__security_cookie
0x18003097f  xor     rax, rsp
0x180030982  mov     [rsp+108h+var_18], rax
0x18003098a  mov     esi, r8d
0x18003098d  mov     rdi, rdx
0x180030990  mov     rbx, rcx
0x180030993  mov     [rsp+108h+var_C0], rcx
0x180030998  lea     rcx, [rdx+8]; lpCriticalSection
0x18003099c  mov     [rbx], rcx
0x18003099f  call    cs:__imp_EnterCriticalSection
0x1800309a5  mov     ecx, [rdi+34h]
0x1800309a8  lea     eax, [rcx+1]
0x1800309ab  mov     [rdi+34h], eax
0x1800309ae  test    ecx, ecx
0x1800309b0  jnz     short loc_1800309BB
0x1800309b2  call    cs:__imp_GetCurrentThreadId
0x1800309b8  mov     [rdi+30h], eax
0x1800309bb  cmp     esi, 1
0x1800309be  setz    al
0x1800309c1  mov     [rbx+8], al
0x1800309c4  mov     [rbx+10h], rdi
0x1800309c8  cmp     byte ptr [rdi+48h], 0
0x1800309cc  jz      short loc_1800309F6
0x1800309ce  mov     rax, rbx
0x1800309d1  mov     rcx, [rsp+108h+var_18]
0x1800309d9  xor     rcx, rsp; StackCookie
0x1800309dc  call    __security_check_cookie
0x1800309e1  lea     r11, [rsp+108h+var_8]
0x1800309e9  mov     rbx, [r11+18h]
0x1800309ed  mov     rsi, [r11+20h]
0x1800309f1  mov     rsp, r11
0x1800309f4  pop     rdi
0x1800309f5  retn
0x1800309f6  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x1800309fd  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x180030a02  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x180030a0a  mov     [rsp+108h+var_E8], 7Fh; unsigned int
0x180030a12  lea     r9, word_180139126
0x180030a19  lea     r8, aNoFilename; "(no filename)"
0x180030a20  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180030a25  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180030a2a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180030a31  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180030a36  call    _CxxThrowException_0
```
