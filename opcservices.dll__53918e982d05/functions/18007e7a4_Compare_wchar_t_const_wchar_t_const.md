# Compare(wchar_t const *,wchar_t const *)

- ea: `0x18007e7a4`
- end: `0x18007e84d`
- name: `?Compare@@YAHPEB_W0@Z`
- size: `169`
- prototype: `int(const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004ba74`
- `0x1800e1db0`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x18007e7a4`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e7d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e7d2`

## string_xrefs

- `0x18007e807`: `::CompareString returned invalid return value`

## pseudocode

```c
__int64 __fastcall Compare(const wchar_t *a1, const wchar_t *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  win_musl::detail *v4; // rcx
  int v6; // eax
  unsigned int LastErrorAsFailHR; // eax
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  v2 = 1;
  v3 = CompareStringOrdinal(a1, -1, a2, -1, 1) - 1;
  if ( v3 )
  {
    v6 = v3 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v4);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x5B4u,
          LastErrorAsFailHR,
          (struct win_musl::TStringEllipseBase *)L"::CompareString returned invalid return value");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    return (unsigned int)-1;
  }
  return v2;
}

```

## disassembly

```asm
0x18007e7a4  push    rbx
0x18007e7a6  sub     rsp, 0F0h
0x18007e7ad  mov     rax, cs:__security_cookie
0x18007e7b4  xor     rax, rsp
0x18007e7b7  mov     [rsp+0F8h+var_18], rax
0x18007e7bf  or      r9d, 0FFFFFFFFh; cchCount2
0x18007e7c3  mov     r8, rdx; lpString2
0x18007e7c6  mov     ebx, 1
0x18007e7cb  or      edx, r9d; cchCount1
0x18007e7ce  mov     [rsp+0F8h+bIgnoreCase], ebx; bIgnoreCase
0x18007e7d2  call    cs:__imp_CompareStringOrdinal
0x18007e7d8  sub     eax, ebx
0x18007e7da  jnz     short loc_18007E7FA
0x18007e7dc  or      ebx, 0FFFFFFFFh
0x18007e7df  mov     eax, ebx
0x18007e7e1  mov     rcx, [rsp+0F8h+var_18]
0x18007e7e9  xor     rcx, rsp; StackCookie
0x18007e7ec  call    __security_check_cookie
0x18007e7f1  add     rsp, 0F0h
0x18007e7f8  pop     rbx
0x18007e7f9  retn
0x18007e7fa  sub     eax, ebx
0x18007e7fc  jz      short loc_18007E849
0x18007e7fe  cmp     eax, ebx
0x18007e800  jz      short loc_18007E7DF
0x18007e802  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18007e807  lea     rcx, aComparestringR; "::CompareString returned invalid return"...
0x18007e80e  mov     [rsp+0F8h+var_C8], rcx; struct win_musl::TStringEllipseBase *
0x18007e813  lea     r9, word_180139126
0x18007e81a  mov     [rsp+0F8h+var_D0], eax; unsigned int
0x18007e81e  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18007e823  lea     r8, aNoFilename; "(no filename)"
0x18007e82a  mov     [rsp+0F8h+bIgnoreCase], 5B4h; unsigned int
0x18007e832  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18007e837  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007e83e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18007e843  call    _CxxThrowException_0
0x18007e849  xor     ebx, ebx
0x18007e84b  jmp     short loc_18007E7DF
```
