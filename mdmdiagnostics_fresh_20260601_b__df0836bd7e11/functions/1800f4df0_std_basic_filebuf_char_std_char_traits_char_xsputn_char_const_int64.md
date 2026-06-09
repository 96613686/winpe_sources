# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x1800f4df0`
- end: `0x1800f4e8e`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019fac`
- `0x1800f4df0`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1800f4e0b`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1800f4e0b`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f4e16`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f4e16`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f4e4f`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f4e4f`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f4e33`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f4e33`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f4e74`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f4e74`

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
0x1800f4df0  push    rbx
0x1800f4df2  push    rbp
0x1800f4df3  push    rsi
0x1800f4df4  push    rdi
0x1800f4df5  push    r14
0x1800f4df7  sub     rsp, 20h
0x1800f4dfb  cmp     qword ptr [rcx+68h], 0
0x1800f4e00  mov     rbx, r8
0x1800f4e03  mov     rsi, rdx
0x1800f4e06  mov     rdi, rcx
0x1800f4e09  jz      short loc_1800F4E13
0x1800f4e0b  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x1800f4e11  jmp     short loc_1800F4E83
0x1800f4e13  mov     r14, rbx
0x1800f4e16  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x1800f4e1c  mov     rbp, rax
0x1800f4e1f  test    rbx, rbx
0x1800f4e22  jle     short loc_1800F4E7D
0x1800f4e24  test    rax, rax
0x1800f4e27  jle     short loc_1800F4E5D
0x1800f4e29  cmp     rbx, rax
0x1800f4e2c  mov     rcx, rdi
0x1800f4e2f  cmovl   rbp, rbx
0x1800f4e33  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800f4e39  mov     r8, rbp; Size
0x1800f4e3c  mov     rdx, rsi; Src
0x1800f4e3f  mov     rcx, rax; void *
0x1800f4e42  call    memcpy_0
0x1800f4e47  mov     edx, ebp
0x1800f4e49  mov     rcx, rdi
0x1800f4e4c  sub     rbx, rbp
0x1800f4e4f  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x1800f4e55  test    rbx, rbx
0x1800f4e58  jle     short loc_1800F4E7D
0x1800f4e5a  add     rsi, rbp
0x1800f4e5d  mov     r9, [rdi+80h]
0x1800f4e64  test    r9, r9
0x1800f4e67  jz      short loc_1800F4E7D
0x1800f4e69  mov     r8, rbx
0x1800f4e6c  mov     edx, 1
0x1800f4e71  mov     rcx, rsi
0x1800f4e74  call    cs:__imp__o_fwrite
0x1800f4e7a  sub     rbx, rax
0x1800f4e7d  sub     r14, rbx
0x1800f4e80  mov     rax, r14
0x1800f4e83  add     rsp, 20h
0x1800f4e87  pop     r14
0x1800f4e89  pop     rdi
0x1800f4e8a  pop     rsi
0x1800f4e8b  pop     rbp
0x1800f4e8c  pop     rbx
0x1800f4e8d  retn
```
