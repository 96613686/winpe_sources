# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x18000d4d0`
- end: `0x18000d56e`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `158`
- prototype: `__int64 __fastcall(__int64, char *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800027d9`
- `0x18000d4d0`

## import_xrefs

- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000d513`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000d513`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18000d52f`
- `msvcp_win!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18000d52f`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18000d4f6`
- `msvcp_win!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18000d4f6`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18000d4eb`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18000d4eb`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000d554`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000d554`

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
0x18000d4d0  push    rbx
0x18000d4d2  push    rbp
0x18000d4d3  push    rsi
0x18000d4d4  push    rdi
0x18000d4d5  push    r14
0x18000d4d7  sub     rsp, 20h
0x18000d4db  cmp     qword ptr [rcx+68h], 0
0x18000d4e0  mov     rbx, r8
0x18000d4e3  mov     rsi, rdx
0x18000d4e6  mov     rdi, rcx
0x18000d4e9  jz      short loc_18000D4F3
0x18000d4eb  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x18000d4f1  jmp     short loc_18000D563
0x18000d4f3  mov     r14, rbx
0x18000d4f6  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x18000d4fc  mov     rbp, rax
0x18000d4ff  test    rbx, rbx
0x18000d502  jle     short loc_18000D55D
0x18000d504  test    rax, rax
0x18000d507  jle     short loc_18000D53D
0x18000d509  cmp     rbx, rax
0x18000d50c  mov     rcx, rdi
0x18000d50f  cmovl   rbp, rbx
0x18000d513  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18000d519  mov     r8, rbp; Size
0x18000d51c  mov     rdx, rsi; Src
0x18000d51f  mov     rcx, rax; void *
0x18000d522  call    memcpy_0
0x18000d527  mov     edx, ebp
0x18000d529  mov     rcx, rdi
0x18000d52c  sub     rbx, rbp
0x18000d52f  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x18000d535  test    rbx, rbx
0x18000d538  jle     short loc_18000D55D
0x18000d53a  add     rsi, rbp
0x18000d53d  mov     r9, [rdi+80h]
0x18000d544  test    r9, r9
0x18000d547  jz      short loc_18000D55D
0x18000d549  mov     r8, rbx
0x18000d54c  mov     edx, 1
0x18000d551  mov     rcx, rsi
0x18000d554  call    cs:__imp__o_fwrite
0x18000d55a  sub     rbx, rax
0x18000d55d  sub     r14, rbx
0x18000d560  mov     rax, r14
0x18000d563  add     rsp, 20h
0x18000d567  pop     r14
0x18000d569  pop     rdi
0x18000d56a  pop     rsi
0x18000d56b  pop     rbp
0x18000d56c  pop     rbx
0x18000d56d  retn
```
