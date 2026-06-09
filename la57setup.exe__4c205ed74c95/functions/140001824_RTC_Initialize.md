# _RTC_Initialize

- ea: `0x140001824`
- end: `0x14000185f`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001090`

## callees

- `0x140001824`
- `0x140003010`

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
0x140001824  mov     [rsp+arg_0], rbx
0x140001829  push    rdi
0x14000182a  sub     rsp, 20h
0x14000182e  lea     rbx, __rtc_izz
0x140001835  lea     rdi, __rtc_izz
0x14000183c  jmp     short loc_14000184F
0x14000183e  mov     rax, [rbx]
0x140001841  test    rax, rax
0x140001844  jz      short loc_14000184B
0x140001846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000184b  add     rbx, 8
0x14000184f  cmp     rbx, rdi
0x140001852  jb      short loc_14000183E
0x140001854  mov     rbx, [rsp+28h+arg_0]
0x140001859  add     rsp, 20h
0x14000185d  pop     rdi
0x14000185e  retn
```
