# _RTC_Initialize

- ea: `0x180001960`
- end: `0x18000199b`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x180001960`
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
0x180001960  mov     [rsp+arg_0], rbx
0x180001965  push    rdi
0x180001966  sub     rsp, 20h
0x18000196a  lea     rbx, __rtc_izz
0x180001971  lea     rdi, __rtc_izz
0x180001978  jmp     short loc_18000198B
0x18000197a  mov     rax, [rbx]
0x18000197d  test    rax, rax
0x180001980  jz      short loc_180001987
0x180001982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001987  add     rbx, 8
0x18000198b  cmp     rbx, rdi
0x18000198e  jb      short loc_18000197A
0x180001990  mov     rbx, [rsp+28h+arg_0]
0x180001995  add     rsp, 20h
0x180001999  pop     rdi
0x18000199a  retn
```
