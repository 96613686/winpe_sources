# _RTC_Terminate

- ea: `0x180001904`
- end: `0x18000193f`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x180001904`
- `0x180004010`

## pseudocode

```c
void __cdecl RTC_Terminate()
{
  void (**i)(void); // rbx

  for ( i = (void (**)(void))&_rtc_tzz; i < (void (**)(void))&_rtc_tzz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x180001904  mov     [rsp+arg_0], rbx
0x180001909  push    rdi
0x18000190a  sub     rsp, 20h
0x18000190e  lea     rbx, __rtc_tzz
0x180001915  lea     rdi, __rtc_tzz
0x18000191c  jmp     short loc_18000192F
0x18000191e  mov     rax, [rbx]
0x180001921  test    rax, rax
0x180001924  jz      short loc_18000192B
0x180001926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000192b  add     rbx, 8
0x18000192f  cmp     rbx, rdi
0x180001932  jb      short loc_18000191E
0x180001934  mov     rbx, [rsp+28h+arg_0]
0x180001939  add     rsp, 20h
0x18000193d  pop     rdi
0x18000193e  retn
```
