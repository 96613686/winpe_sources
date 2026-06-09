# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)

- ea: `0x140004f9c`
- end: `0x140005008`
- name: `?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, char, __int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c10`
- `0x140003c2c`
- `0x140003f54`
- `0x140004868`
- `0x14000fabc`
- `0x14000fbcc`
- `0x1400115c8`
- `0x1400144f0`
- `0x14001d2df`

## callees

- `0x140004f9c`

## import_xrefs

- `msvcrt!free` at `0x140004fde`
- `msvcrt!free` at `0x140004fde`
- `msvcrt!memcpy_s` at `0x140004fd4`
- `msvcrt!memcpy_s` at `0x140004fd4`

## pseudocode

```c
__int64 __fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
        __int64 a1,
        char a2,
        __int64 a3)
{
  void **v5; // rcx
  void *v6; // rsi
  __int64 result; // rax

  if ( a2 && *(_QWORD *)(a1 + 32) >= 8u )
  {
    v5 = (void **)(a1 + 8);
    v6 = *v5;
    if ( a3 )
      memcpy_s(v5, 0x10u, *v5, 2 * a3);
    free(v6);
  }
  *(_QWORD *)(a1 + 32) = 7;
  *(_QWORD *)(a1 + 24) = a3;
  result = 0;
  *(_WORD *)(a1 + 2 * a3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x140004f9c  mov     [rsp+arg_0], rbx
0x140004fa1  mov     [rsp+arg_8], rsi
0x140004fa6  push    rdi
0x140004fa7  sub     rsp, 20h
0x140004fab  mov     rdi, r8
0x140004fae  mov     rbx, rcx
0x140004fb1  test    dl, dl
0x140004fb3  jz      short loc_140004FE5
0x140004fb5  cmp     qword ptr [rcx+20h], 8
0x140004fba  jb      short loc_140004FE5
0x140004fbc  add     rcx, 8; Destination
0x140004fc0  mov     rsi, [rcx]
0x140004fc3  test    r8, r8
0x140004fc6  jz      short loc_140004FDB
0x140004fc8  lea     r9, [r8+r8]; SourceSize
0x140004fcc  mov     r8, rsi; Source
0x140004fcf  mov     edx, 10h; DestinationSize
0x140004fd4  call    cs:__imp_memcpy_s
0x140004fda  nop
0x140004fdb  mov     rcx, rsi; Block
0x140004fde  call    cs:__imp_free
0x140004fe4  nop
0x140004fe5  mov     qword ptr [rbx+20h], 7
0x140004fed  mov     [rbx+18h], rdi
0x140004ff1  xor     eax, eax
0x140004ff3  mov     [rbx+rdi*2+8], ax
0x140004ff8  mov     rbx, [rsp+28h+arg_0]
0x140004ffd  mov     rsi, [rsp+28h+arg_8]
0x140005002  add     rsp, 20h
0x140005006  pop     rdi
0x140005007  retn
```
