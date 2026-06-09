# _RTC_Terminate

- ea: `0x180001948`
- end: `0x180001983`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001258`

## callees

- `0x180001948`
- `0x180003010`

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
0x180001948  mov     [rsp+arg_0], rbx
0x18000194d  push    rdi
0x18000194e  sub     rsp, 20h
0x180001952  lea     rbx, __rtc_tzz
0x180001959  lea     rdi, __rtc_tzz
0x180001960  jmp     short loc_180001973
0x180001962  mov     rax, [rbx]
0x180001965  test    rax, rax
0x180001968  jz      short loc_18000196F
0x18000196a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000196f  add     rbx, 8
0x180001973  cmp     rbx, rdi
0x180001976  jb      short loc_180001962
0x180001978  mov     rbx, [rsp+28h+arg_0]
0x18000197d  add     rsp, 20h
0x180001981  pop     rdi
0x180001982  retn
```
