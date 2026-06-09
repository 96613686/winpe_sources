# GetCanonicalPathInfoA

- ea: `0x1800042d0`
- end: `0x1800043de`
- name: `GetCanonicalPathInfoA`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001ce0`
- `0x1800042d0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x1800043a5`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x1800043a5`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180004318`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180004318`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x18000435f`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x180004381`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x18000435f`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x180004381`

## pseudocode

```c
__int64 __fastcall GetCanonicalPathInfoA(const CHAR *a1, CHAR *a2, unsigned int *a3, CHAR *a4, CHAR **a5)
{
  unsigned int CanonicalPathInfoW; // ebp
  signed __int64 v9; // rbx
  __int64 i; // rbx
  LPSTR v11; // rax
  char *v13; // [rsp+30h] [rbp-678h] BYREF
  WCHAR pwszSrc[264]; // [rsp+40h] [rbp-668h] BYREF
  WCHAR pwszDst[264]; // [rsp+250h] [rbp-458h] BYREF
  WCHAR v16[264]; // [rsp+460h] [rbp-248h] BYREF

  v13 = 0;
  SHAnsiToUnicode(a1, pwszDst, 260);
  CanonicalPathInfoW = GetCanonicalPathInfoW(pwszDst, pwszSrc, a3, v16, (unsigned __int16 **)&v13);
  if ( CanonicalPathInfoW )
  {
    SHUnicodeToAnsi(pwszSrc, a2, 260);
    if ( (*(_BYTE *)a3 & 1) != 0 )
      SHUnicodeToAnsi(v16, a4, 260);
    v9 = v13 - (char *)pwszSrc;
    *a5 = a2;
    for ( i = v9 >> 1; i; --i )
    {
      v11 = CharNextA(a2);
      *a5 = v11;
      a2 = v11;
    }
  }
  return CanonicalPathInfoW;
}

```

## disassembly

```asm
0x1800042d0  push    rbx; GetCanonicalPathInfo
0x1800042d2  push    rbp
0x1800042d3  push    rsi
0x1800042d4  push    rdi
0x1800042d5  push    r14
0x1800042d7  sub     rsp, 680h
0x1800042de  mov     rax, cs:__security_cookie
0x1800042e5  xor     rax, rsp
0x1800042e8  mov     [rsp+6A8h+var_38], rax
0x1800042f0  mov     rsi, [rsp+6A8h+arg_20]
0x1800042f8  mov     rbx, r8
0x1800042fb  mov     rdi, rdx
0x1800042fe  mov     [rsp+6A8h+var_678], 0
0x180004307  mov     r8d, 104h; cwchBuf
0x18000430d  lea     rdx, [rsp+6A8h+pwszDst]; pwszDst
0x180004315  mov     r14, r9
0x180004318  call    cs:__imp_SHAnsiToUnicode
0x18000431f  nop     dword ptr [rax+rax+00h]
0x180004324  lea     rax, [rsp+6A8h+var_678]
0x180004329  mov     r8, rbx
0x18000432c  lea     r9, [rsp+6A8h+var_248]
0x180004334  mov     [rsp+6A8h+var_688], rax
0x180004339  lea     rdx, [rsp+6A8h+pwszSrc]
0x18000433e  lea     rcx, [rsp+6A8h+pwszDst]
0x180004346  call    GetCanonicalPathInfoW
0x18000434b  mov     ebp, eax
0x18000434d  test    eax, eax
0x18000434f  jz      short loc_1800043BD
0x180004351  mov     r8d, 104h; cchBuf
0x180004357  lea     rcx, [rsp+6A8h+pwszSrc]; pwszSrc
0x18000435c  mov     rdx, rdi; pszDst
0x18000435f  call    cs:__imp_SHUnicodeToAnsi
0x180004366  nop     dword ptr [rax+rax+00h]
0x18000436b  test    byte ptr [rbx], 1
0x18000436e  jz      short loc_18000438D
0x180004370  mov     r8d, 104h; cchBuf
0x180004376  lea     rcx, [rsp+6A8h+var_248]; pwszSrc
0x18000437e  mov     rdx, r14; pszDst
0x180004381  call    cs:__imp_SHUnicodeToAnsi
0x180004388  nop     dword ptr [rax+rax+00h]
0x18000438d  mov     rbx, [rsp+6A8h+var_678]
0x180004392  lea     rax, [rsp+6A8h+pwszSrc]
0x180004397  sub     rbx, rax
0x18000439a  mov     [rsi], rdi
0x18000439d  sar     rbx, 1
0x1800043a0  jz      short loc_1800043BD
0x1800043a2  mov     rcx, rdi; lpsz
0x1800043a5  call    cs:__imp_CharNextA
0x1800043ac  nop     dword ptr [rax+rax+00h]
0x1800043b1  mov     [rsi], rax
0x1800043b4  mov     rdi, rax
0x1800043b7  sub     rbx, 1
0x1800043bb  jnz     short loc_1800043A2
0x1800043bd  mov     eax, ebp
0x1800043bf  mov     rcx, [rsp+6A8h+var_38]
0x1800043c7  xor     rcx, rsp; StackCookie
0x1800043ca  call    __security_check_cookie
0x1800043cf  add     rsp, 680h
0x1800043d6  pop     r14
0x1800043d8  pop     rdi
0x1800043d9  pop     rsi
0x1800043da  pop     rbp
0x1800043db  pop     rbx
0x1800043dc  retn
```
