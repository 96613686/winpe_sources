# _RTC_Terminate

- ea: `0x1800019a4`
- end: `0x1800019df`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001248`

## callees

- `0x1800019a4`
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
0x1800019a4  mov     [rsp+arg_0], rbx
0x1800019a9  push    rdi
0x1800019aa  sub     rsp, 20h
0x1800019ae  lea     rbx, __rtc_tzz
0x1800019b5  lea     rdi, __rtc_tzz
0x1800019bc  jmp     short loc_1800019CF
0x1800019be  mov     rax, [rbx]
0x1800019c1  test    rax, rax
0x1800019c4  jz      short loc_1800019CB
0x1800019c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019cb  add     rbx, 8
0x1800019cf  cmp     rbx, rdi
0x1800019d2  jb      short loc_1800019BE
0x1800019d4  mov     rbx, [rsp+28h+arg_0]
0x1800019d9  add     rsp, 20h
0x1800019dd  pop     rdi
0x1800019de  retn
```
