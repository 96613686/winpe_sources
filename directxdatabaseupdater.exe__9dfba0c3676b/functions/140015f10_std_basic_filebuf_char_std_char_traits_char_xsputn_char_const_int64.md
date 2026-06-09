# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x140015f10`
- end: `0x140015fae`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `158`
- prototype: `__int64 __fastcall(__int64, char *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003aa0`
- `0x140015f10`

## import_xrefs

- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015f53`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015f53`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x140015f6f`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x140015f6f`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140015f36`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140015f36`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x140015f2b`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x140015f2b`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140015f94`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140015f94`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v8; // rax
  size_t v9; // rbp
  void *v10; // rax
  __int64 v11; // r9

  v3 = a3;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = std::streambuf::_Pnavail();
  v9 = v8;
  if ( v3 > 0 )
  {
    if ( v8 > 0 )
    {
      if ( v3 < v8 )
        v9 = v3;
      v10 = (void *)std::streambuf::pptr(a1);
      memcpy_0(v10, a2, v9);
      v3 -= v9;
      std::streambuf::pbump(a1, (unsigned int)v9);
      if ( v3 <= 0 )
        return a3 - v3;
      a2 += v9;
    }
    v11 = *(_QWORD *)(a1 + 128);
    if ( v11 )
      v3 -= _o_fwrite(a2, 1, v3, v11);
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x140015f10  push    rbx
0x140015f12  push    rbp
0x140015f13  push    rsi
0x140015f14  push    rdi
0x140015f15  push    r14
0x140015f17  sub     rsp, 20h
0x140015f1b  cmp     qword ptr [rcx+68h], 0
0x140015f20  mov     rbx, r8
0x140015f23  mov     rsi, rdx
0x140015f26  mov     rdi, rcx
0x140015f29  jz      short loc_140015F33
0x140015f2b  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x140015f31  jmp     short loc_140015FA3
0x140015f33  mov     r14, rbx
0x140015f36  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x140015f3c  mov     rbp, rax
0x140015f3f  test    rbx, rbx
0x140015f42  jle     short loc_140015F9D
0x140015f44  test    rax, rax
0x140015f47  jle     short loc_140015F7D
0x140015f49  cmp     rbx, rax
0x140015f4c  mov     rcx, rdi
0x140015f4f  cmovl   rbp, rbx
0x140015f53  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x140015f59  mov     r8, rbp; Size
0x140015f5c  mov     rdx, rsi; Src
0x140015f5f  mov     rcx, rax; void *
0x140015f62  call    memcpy_0
0x140015f67  mov     edx, ebp
0x140015f69  mov     rcx, rdi
0x140015f6c  sub     rbx, rbp
0x140015f6f  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x140015f75  test    rbx, rbx
0x140015f78  jle     short loc_140015F9D
0x140015f7a  add     rsi, rbp
0x140015f7d  mov     r9, [rdi+80h]
0x140015f84  test    r9, r9
0x140015f87  jz      short loc_140015F9D
0x140015f89  mov     r8, rbx
0x140015f8c  mov     edx, 1
0x140015f91  mov     rcx, rsi
0x140015f94  call    cs:__imp__o_fwrite
0x140015f9a  sub     rbx, rax
0x140015f9d  sub     r14, rbx
0x140015fa0  mov     rax, r14
0x140015fa3  add     rsp, 20h
0x140015fa7  pop     r14
0x140015fa9  pop     rdi
0x140015faa  pop     rsi
0x140015fab  pop     rbp
0x140015fac  pop     rbx
0x140015fad  retn
```
