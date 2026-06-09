# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x1800f5a50`
- end: `0x1800f5b10`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001a03c`
- `0x1800f5a50`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1800f5a6b`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1800f5a6b`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f5a7f`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f5a7f`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f5ac4`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f5ac4`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f5aa2`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f5aa2`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f5aef`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f5aef`

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
0x1800f5a50  push    rbx
0x1800f5a52  push    rbp
0x1800f5a53  push    rsi
0x1800f5a54  push    rdi
0x1800f5a55  push    r14
0x1800f5a57  sub     rsp, 20h
0x1800f5a5b  cmp     qword ptr [rcx+68h], 0
0x1800f5a60  mov     rbx, r8
0x1800f5a63  mov     rsi, rdx
0x1800f5a66  mov     rdi, rcx
0x1800f5a69  jz      short loc_1800F5A7C
0x1800f5a6b  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x1800f5a72  nop     dword ptr [rax+rax+00h]
0x1800f5a77  jmp     loc_1800F5B04
0x1800f5a7c  mov     r14, rbx
0x1800f5a7f  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x1800f5a86  nop     dword ptr [rax+rax+00h]
0x1800f5a8b  mov     rbp, rax
0x1800f5a8e  test    rbx, rbx
0x1800f5a91  jle     short loc_1800F5AFE
0x1800f5a93  test    rax, rax
0x1800f5a96  jle     short loc_1800F5AD8
0x1800f5a98  cmp     rbx, rax
0x1800f5a9b  mov     rcx, rdi
0x1800f5a9e  cmovl   rbp, rbx
0x1800f5aa2  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800f5aa9  nop     dword ptr [rax+rax+00h]
0x1800f5aae  mov     r8, rbp; Size
0x1800f5ab1  mov     rdx, rsi; Src
0x1800f5ab4  mov     rcx, rax; void *
0x1800f5ab7  call    memcpy_0
0x1800f5abc  mov     edx, ebp
0x1800f5abe  mov     rcx, rdi
0x1800f5ac1  sub     rbx, rbp
0x1800f5ac4  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x1800f5acb  nop     dword ptr [rax+rax+00h]
0x1800f5ad0  test    rbx, rbx
0x1800f5ad3  jle     short loc_1800F5AFE
0x1800f5ad5  add     rsi, rbp
0x1800f5ad8  mov     r9, [rdi+80h]
0x1800f5adf  test    r9, r9
0x1800f5ae2  jz      short loc_1800F5AFE
0x1800f5ae4  mov     r8, rbx
0x1800f5ae7  mov     edx, 1
0x1800f5aec  mov     rcx, rsi
0x1800f5aef  call    cs:__imp__o_fwrite
0x1800f5af6  nop     dword ptr [rax+rax+00h]
0x1800f5afb  sub     rbx, rax
0x1800f5afe  sub     r14, rbx
0x1800f5b01  mov     rax, r14
0x1800f5b04  add     rsp, 20h
0x1800f5b08  pop     r14
0x1800f5b0a  pop     rdi
0x1800f5b0b  pop     rsi
0x1800f5b0c  pop     rbp
0x1800f5b0d  pop     rbx
0x1800f5b0e  retn
```
