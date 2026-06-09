# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x1800a39b0`
- end: `0x1800a3a6d`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800a39b0`
- `0x1801a65f0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x1800a3a4b`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x1800a3a4b`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a3a02`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a3a02`
- `MSVCP140!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800a3a21`
- `MSVCP140!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800a3a21`
- `MSVCP140!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800a39e5`
- `MSVCP140!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800a39e5`
- `MSVCP140!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1800a39d1`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, signed __int64 a3)
{
  signed __int64 v3; // rbx
  __int64 v8; // rax
  size_t v9; // rbp
  void *v10; // rax

  v3 = a3;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = std::streambuf::_Pnavail();
  v9 = v8;
  if ( v3 > 0 )
  {
    if ( v8 <= 0 )
      goto LABEL_13;
    if ( v3 < v8 )
      v9 = v3;
    v10 = (void *)std::streambuf::pptr(a1);
    memcpy_0(v10, a2, v9);
    a2 += v9;
    v3 -= v9;
    std::streambuf::pbump(a1, (unsigned int)v9);
    if ( v3 > 0 )
    {
LABEL_13:
      if ( *(_QWORD *)(a1 + 128) )
      {
        _mm_lfence();
        v3 -= fwrite(a2, 1u, v3, *(FILE **)(a1 + 128));
      }
    }
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x1800a39b0  push    rbx
0x1800a39b2  push    rdi
0x1800a39b3  push    r14
0x1800a39b5  sub     rsp, 20h
0x1800a39b9  cmp     qword ptr [rcx+68h], 0
0x1800a39be  mov     rbx, r8
0x1800a39c1  mov     r14, rdx
0x1800a39c4  mov     rdi, rcx
0x1800a39c7  jz      short loc_1800A39D8
0x1800a39c9  add     rsp, 20h
0x1800a39cd  pop     r14
0x1800a39cf  pop     rdi
0x1800a39d0  pop     rbx
0x1800a39d1  jmp     cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x1800a39d8  mov     [rsp+38h+arg_0], rbp
0x1800a39dd  mov     [rsp+38h+arg_8], rsi
0x1800a39e2  mov     rsi, rbx
0x1800a39e5  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x1800a39eb  mov     rbp, rax
0x1800a39ee  test    rbx, rbx
0x1800a39f1  jle     short loc_1800A3A54
0x1800a39f3  test    rax, rax
0x1800a39f6  jle     short loc_1800A3A2C
0x1800a39f8  cmp     rbx, rax
0x1800a39fb  mov     rcx, rdi
0x1800a39fe  cmovl   rbp, rbx
0x1800a3a02  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800a3a08  mov     r8, rbp; Size
0x1800a3a0b  mov     rdx, r14; Src
0x1800a3a0e  mov     rcx, rax; void *
0x1800a3a11  call    memcpy_0
0x1800a3a16  mov     edx, ebp
0x1800a3a18  mov     rcx, rdi
0x1800a3a1b  add     r14, rbp
0x1800a3a1e  sub     rbx, rbp
0x1800a3a21  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x1800a3a27  test    rbx, rbx
0x1800a3a2a  jle     short loc_1800A3A54
0x1800a3a2c  cmp     qword ptr [rdi+80h], 0
0x1800a3a34  jz      short loc_1800A3A54
0x1800a3a36  lfence
0x1800a3a39  mov     r9, [rdi+80h]; Stream
0x1800a3a40  mov     r8, rbx; ElementCount
0x1800a3a43  mov     edx, 1; ElementSize
0x1800a3a48  mov     rcx, r14; Buffer
0x1800a3a4b  call    cs:__imp_fwrite
0x1800a3a51  sub     rbx, rax
0x1800a3a54  mov     rbp, [rsp+38h+arg_0]
0x1800a3a59  sub     rsi, rbx
0x1800a3a5c  mov     rax, rsi
0x1800a3a5f  mov     rsi, [rsp+38h+arg_8]
0x1800a3a64  add     rsp, 20h
0x1800a3a68  pop     r14
0x1800a3a6a  pop     rdi
0x1800a3a6b  pop     rbx
0x1800a3a6c  retn
```
