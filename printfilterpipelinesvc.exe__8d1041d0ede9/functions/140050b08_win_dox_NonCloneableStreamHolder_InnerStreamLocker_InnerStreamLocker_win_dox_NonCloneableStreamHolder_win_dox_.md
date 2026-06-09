# win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(win_dox::NonCloneableStreamHolder *,win_dox::NonCloneableStreamHolder::MethodType)

- ea: `0x140050b08`
- end: `0x140050bd7`
- name: `??0InnerStreamLocker@NonCloneableStreamHolder@win_dox@@QEAA@PEAV12@W4MethodType@12@@Z`
- size: `207`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x140050f30`
- `0x1400515a0`
- `0x140051790`
- `0x1400518cc`
- `0x140051940`
- `0x140051bb0`
- `0x140051c24`
- `0x140051d80`
- `0x140051ee0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x14001b26c`
- `0x140050b08`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140050b54`
- `KERNEL32!GetCurrentThreadId` at `0x140050b54`
- `KERNEL32!EnterCriticalSection` at `0x140050b41`
- `KERNEL32!EnterCriticalSection` at `0x140050b41`

## string_xrefs

- `0x140050b70`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(
        __int64 a1,
        __int64 a2,
        int a3)
{
  __int64 v6; // rdx
  __int64 v7; // r9
  int v8; // ecx
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  *(_QWORD *)a1 = a2 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  v8 = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a2 + 52) = v8 + 1;
  if ( !v8 )
    *(_DWORD *)(a2 + 48) = GetCurrentThreadId();
  *(_BYTE *)(a1 + 8) = a3 == 1;
  *(_QWORD *)(a1 + 16) = a2;
  if ( !*(_BYTE *)(a2 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      v6,
      "(no filename)",
      v7,
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
0x140050b08  mov     [rsp+arg_8], rbx
0x140050b0d  mov     [rsp+arg_10], rsi
0x140050b12  push    rdi
0x140050b13  sub     rsp, 100h
0x140050b1a  mov     rax, cs:__security_cookie
0x140050b21  xor     rax, rsp
0x140050b24  mov     [rsp+108h+var_18], rax
0x140050b2c  mov     esi, r8d
0x140050b2f  mov     rdi, rdx
0x140050b32  mov     rbx, rcx
0x140050b35  mov     [rsp+108h+var_C8], rcx
0x140050b3a  lea     rcx, [rdx+8]; lpCriticalSection
0x140050b3e  mov     [rbx], rcx
0x140050b41  call    cs:__imp_EnterCriticalSection
0x140050b47  mov     ecx, [rdi+34h]
0x140050b4a  lea     eax, [rcx+1]
0x140050b4d  mov     [rdi+34h], eax
0x140050b50  test    ecx, ecx
0x140050b52  jnz     short loc_140050B5D
0x140050b54  call    cs:__imp_GetCurrentThreadId
0x140050b5a  mov     [rdi+30h], eax
0x140050b5d  cmp     esi, 1
0x140050b60  setz    al
0x140050b63  mov     [rbx+8], al
0x140050b66  mov     [rbx+10h], rdi
0x140050b6a  cmp     byte ptr [rdi+48h], 0
0x140050b6e  jnz     short loc_140050BAF
0x140050b70  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x140050b77  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x140050b7c  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x140050b84  mov     [rsp+108h+var_E8], 7Fh; unsigned int
0x140050b8c  lea     r8, aNoFilename; "(no filename)"
0x140050b93  lea     rcx, [rsp+108h+pExceptionObject]; this
0x140050b98  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x140050b9d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140050ba4  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x140050ba9  call    _CxxThrowException_0
0x140050baf  mov     rax, rbx
0x140050bb2  mov     rcx, [rsp+108h+var_18]
0x140050bba  xor     rcx, rsp; StackCookie
0x140050bbd  call    __security_check_cookie
0x140050bc2  lea     r11, [rsp+108h+var_8]
0x140050bca  mov     rbx, [r11+18h]
0x140050bce  mov     rsi, [r11+20h]
0x140050bd2  mov     rsp, r11
0x140050bd5  pop     rdi
0x140050bd6  retn
```
