# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Tidy(bool,unsigned __int64)

- ea: `0x140004f2c`
- end: `0x140004f94`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z`
- size: `104`
- prototype: `void __fastcall(__int64, char, rsize_t)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bf4`
- `0x140003d78`
- `0x140004784`
- `0x140004b18`
- `0x140010f70`
- `0x140011068`
- `0x1400127c0`
- `0x1400133e0`
- `0x14001d27a`

## callees

- `0x140004f2c`

## import_xrefs

- `msvcrt!free` at `0x140004f6c`
- `msvcrt!free` at `0x140004f6c`
- `msvcrt!memcpy_s` at `0x140004f62`
- `msvcrt!memcpy_s` at `0x140004f62`

## pseudocode

```c
void __fastcall std::string::_Tidy(__int64 a1, char a2, rsize_t a3)
{
  void **v5; // rcx
  void *v6; // rsi

  if ( a2 && *(_QWORD *)(a1 + 32) >= 0x10u )
  {
    v5 = (void **)(a1 + 8);
    v6 = *v5;
    if ( a3 )
      memcpy_s(v5, 0x10u, *v5, a3);
    free(v6);
  }
  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = a3;
  *(_BYTE *)(a3 + a1 + 8) = 0;
}

```

## disassembly

```asm
0x140004f2c  mov     [rsp+arg_0], rbx
0x140004f31  mov     [rsp+arg_8], rsi
0x140004f36  push    rdi
0x140004f37  sub     rsp, 20h
0x140004f3b  mov     rdi, r8
0x140004f3e  mov     rbx, rcx
0x140004f41  test    dl, dl
0x140004f43  jz      short loc_140004F73
0x140004f45  mov     edx, 10h; DestinationSize
0x140004f4a  cmp     [rcx+20h], rdx
0x140004f4e  jb      short loc_140004F73
0x140004f50  add     rcx, 8; Destination
0x140004f54  mov     rsi, [rcx]
0x140004f57  test    r8, r8
0x140004f5a  jz      short loc_140004F69
0x140004f5c  mov     r9, r8; SourceSize
0x140004f5f  mov     r8, rsi; Source
0x140004f62  call    cs:__imp_memcpy_s
0x140004f68  nop
0x140004f69  mov     rcx, rsi; Block
0x140004f6c  call    cs:__imp_free
0x140004f72  nop
0x140004f73  mov     qword ptr [rbx+20h], 0Fh
0x140004f7b  mov     [rbx+18h], rdi
0x140004f7f  mov     byte ptr [rdi+rbx+8], 0
0x140004f84  mov     rbx, [rsp+28h+arg_0]
0x140004f89  mov     rsi, [rsp+28h+arg_8]
0x140004f8e  add     rsp, 20h
0x140004f92  pop     rdi
0x140004f93  retn
```
