# _RTC_Initialize

- ea: `0x1800018c0`
- end: `0x1800018fb`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800018c0`
- `0x180004010`

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
0x1800018c0  mov     [rsp+arg_0], rbx
0x1800018c5  push    rdi
0x1800018c6  sub     rsp, 20h
0x1800018ca  lea     rbx, __rtc_izz
0x1800018d1  lea     rdi, __rtc_izz
0x1800018d8  jmp     short loc_1800018EB
0x1800018da  mov     rax, [rbx]
0x1800018dd  test    rax, rax
0x1800018e0  jz      short loc_1800018E7
0x1800018e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e7  add     rbx, 8
0x1800018eb  cmp     rbx, rdi
0x1800018ee  jb      short loc_1800018DA
0x1800018f0  mov     rbx, [rsp+28h+arg_0]
0x1800018f5  add     rsp, 20h
0x1800018f9  pop     rdi
0x1800018fa  retn
```
