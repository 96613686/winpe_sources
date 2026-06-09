# _RTC_Initialize

- ea: `0x1400018a4`
- end: `0x1400018df`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010e0`

## callees

- `0x1400018a4`
- `0x140004010`

## pseudocode

```c
void __cdecl RTC_Initialize()
{
  void (**i)(void); // rbx

  for ( i = &_rtc_izz; i < &_rtc_izz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x1400018a4  mov     [rsp+arg_0], rbx
0x1400018a9  push    rdi
0x1400018aa  sub     rsp, 20h
0x1400018ae  lea     rbx, __rtc_izz
0x1400018b5  lea     rdi, __rtc_izz
0x1400018bc  jmp     short loc_1400018CF
0x1400018be  mov     rax, [rbx]
0x1400018c1  test    rax, rax
0x1400018c4  jz      short loc_1400018CB
0x1400018c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400018cb  add     rbx, 8
0x1400018cf  cmp     rbx, rdi
0x1400018d2  jb      short loc_1400018BE
0x1400018d4  mov     rbx, [rsp+28h+arg_0]
0x1400018d9  add     rsp, 20h
0x1400018dd  pop     rdi
0x1400018de  retn
```
