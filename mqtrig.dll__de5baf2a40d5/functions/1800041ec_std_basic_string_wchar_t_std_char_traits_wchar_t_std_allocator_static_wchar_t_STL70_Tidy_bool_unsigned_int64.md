# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)

- ea: `0x1800041ec`
- end: `0x180004258`
- name: `?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, char, __int64)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x180003118`
- `0x18000317c`
- `0x180003460`
- `0x180003640`
- `0x180003aa0`
- `0x180003ce8`
- `0x180004608`
- `0x18000a300`
- `0x18000aa80`
- `0x18000aea0`
- `0x18000b760`
- `0x18000bda0`
- `0x1800104c8`
- `0x180010590`
- `0x180011778`
- `0x180012770`
- `0x1800158cc`
- `0x180015d40`
- `0x180015db0`
- `0x1800164c8`
- `0x1800175dc`
- `0x1800176ec`
- `0x180019230`
- `0x18001ca10`
- `0x18001ea3d`

## callees

- `0x1800041ec`

## import_xrefs

- `msvcrt!free` at `0x18000422e`
- `msvcrt!free` at `0x18000422e`
- `msvcrt!memcpy_s` at `0x180004224`
- `msvcrt!memcpy_s` at `0x180004224`

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
0x1800041ec  mov     [rsp+arg_0], rbx
0x1800041f1  mov     [rsp+arg_8], rsi
0x1800041f6  push    rdi
0x1800041f7  sub     rsp, 20h
0x1800041fb  mov     rdi, r8
0x1800041fe  mov     rbx, rcx
0x180004201  test    dl, dl
0x180004203  jz      short loc_180004235
0x180004205  cmp     qword ptr [rcx+20h], 8
0x18000420a  jb      short loc_180004235
0x18000420c  add     rcx, 8; Destination
0x180004210  mov     rsi, [rcx]
0x180004213  test    r8, r8
0x180004216  jz      short loc_18000422B
0x180004218  lea     r9, [r8+r8]; SourceSize
0x18000421c  mov     r8, rsi; Source
0x18000421f  mov     edx, 10h; DestinationSize
0x180004224  call    cs:__imp_memcpy_s
0x18000422a  nop
0x18000422b  mov     rcx, rsi; Block
0x18000422e  call    cs:__imp_free
0x180004234  nop
0x180004235  mov     qword ptr [rbx+20h], 7
0x18000423d  mov     [rbx+18h], rdi
0x180004241  xor     eax, eax
0x180004243  mov     [rbx+rdi*2+8], ax
0x180004248  mov     rbx, [rsp+28h+arg_0]
0x18000424d  mov     rsi, [rsp+28h+arg_8]
0x180004252  add     rsp, 20h
0x180004256  pop     rdi
0x180004257  retn
```
