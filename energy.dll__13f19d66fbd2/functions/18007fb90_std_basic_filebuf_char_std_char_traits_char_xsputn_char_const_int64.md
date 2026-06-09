# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x18007fb90`
- end: `0x18007fc2e`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004d8e4`
- `0x18007fb90`

## import_xrefs

- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18007fbb6`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18007fbb6`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18007fbef`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18007fbef`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007fbd3`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007fbd3`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18007fbab`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18007fbab`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007fc14`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007fc14`

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
0x18007fb90  push    rbx
0x18007fb92  push    rbp
0x18007fb93  push    rsi
0x18007fb94  push    rdi
0x18007fb95  push    r14
0x18007fb97  sub     rsp, 20h
0x18007fb9b  cmp     qword ptr [rcx+68h], 0
0x18007fba0  mov     rbx, r8
0x18007fba3  mov     rsi, rdx
0x18007fba6  mov     rdi, rcx
0x18007fba9  jz      short loc_18007FBB3
0x18007fbab  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x18007fbb1  jmp     short loc_18007FC23
0x18007fbb3  mov     r14, rbx
0x18007fbb6  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x18007fbbc  mov     rbp, rax
0x18007fbbf  test    rbx, rbx
0x18007fbc2  jle     short loc_18007FC1D
0x18007fbc4  test    rax, rax
0x18007fbc7  jle     short loc_18007FBFD
0x18007fbc9  cmp     rbx, rax
0x18007fbcc  mov     rcx, rdi
0x18007fbcf  cmovl   rbp, rbx
0x18007fbd3  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18007fbd9  mov     r8, rbp; Size
0x18007fbdc  mov     rdx, rsi; Src
0x18007fbdf  mov     rcx, rax; void *
0x18007fbe2  call    memcpy_0
0x18007fbe7  mov     edx, ebp
0x18007fbe9  mov     rcx, rdi
0x18007fbec  sub     rbx, rbp
0x18007fbef  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x18007fbf5  test    rbx, rbx
0x18007fbf8  jle     short loc_18007FC1D
0x18007fbfa  add     rsi, rbp
0x18007fbfd  mov     r9, [rdi+80h]
0x18007fc04  test    r9, r9
0x18007fc07  jz      short loc_18007FC1D
0x18007fc09  mov     r8, rbx
0x18007fc0c  mov     edx, 1
0x18007fc11  mov     rcx, rsi
0x18007fc14  call    cs:__imp__o_fwrite
0x18007fc1a  sub     rbx, rax
0x18007fc1d  sub     r14, rbx
0x18007fc20  mov     rax, r14
0x18007fc23  add     rsp, 20h
0x18007fc27  pop     r14
0x18007fc29  pop     rdi
0x18007fc2a  pop     rsi
0x18007fc2b  pop     rbp
0x18007fc2c  pop     rbx
0x18007fc2d  retn
```
