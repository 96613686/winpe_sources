# _RTC_Initialize

- ea: `0x140002584`
- end: `0x1400025bf`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e10`

## callees

- `0x140002584`
- `0x140006010`

## pseudocode

```c
void __cdecl RTC_Initialize()
{
  void (**i)(void); // rbx

  for ( i = (void (**)(void))&_rtc_izz; i < (void (**)(void))&_rtc_izz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x140002584  mov     [rsp+arg_0], rbx
0x140002589  push    rdi
0x14000258a  sub     rsp, 20h
0x14000258e  lea     rbx, __rtc_izz
0x140002595  lea     rdi, __rtc_izz
0x14000259c  jmp     short loc_1400025AF
0x14000259e  mov     rax, [rbx]
0x1400025a1  test    rax, rax
0x1400025a4  jz      short loc_1400025AB
0x1400025a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025ab  add     rbx, 8
0x1400025af  cmp     rbx, rdi
0x1400025b2  jb      short loc_14000259E
0x1400025b4  mov     rbx, [rsp+28h+arg_0]
0x1400025b9  add     rsp, 20h
0x1400025bd  pop     rdi
0x1400025be  retn
```
