# _RTC_Terminate

- ea: `0x1800018d8`
- end: `0x180001913`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x1800018d8`
- `0x180005010`

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
0x1800018d8  mov     [rsp+arg_0], rbx
0x1800018dd  push    rdi
0x1800018de  sub     rsp, 20h
0x1800018e2  lea     rbx, __rtc_tzz
0x1800018e9  lea     rdi, __rtc_tzz
0x1800018f0  jmp     short loc_180001903
0x1800018f2  mov     rax, [rbx]
0x1800018f5  test    rax, rax
0x1800018f8  jz      short loc_1800018FF
0x1800018fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018ff  add     rbx, 8
0x180001903  cmp     rbx, rdi
0x180001906  jb      short loc_1800018F2
0x180001908  mov     rbx, [rsp+28h+arg_0]
0x18000190d  add     rsp, 20h
0x180001911  pop     rdi
0x180001912  retn
```
