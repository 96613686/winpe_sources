# InitializeFonts(void)

- ea: `0x1800103b4`
- end: `0x1800103e5`
- name: `?InitializeFonts@@YAXXZ`
- size: `49`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000752c`
- `0x180013ce0`

## callees

- `0x180008714`
- `0x18000fbdc`
- `0x1800103b4`

## string_xrefs

- `0x1800103cb`: `onecore\windows\core\console\open\src\propsheet\misc.cpp`

## pseudocode

```c
void InitializeFonts(void)
{
  int v0; // eax
  int v1; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = EnumerateFonts(0x20u);
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\misc.cpp",
      (const char *)(unsigned int)v0,
      v1);
}

```

## disassembly

```asm
0x1800103b4  sub     rsp, 28h
0x1800103b8  mov     ecx, 20h ; ' '; unsigned int
0x1800103bd  call    ?EnumerateFonts@@YAJK@Z; EnumerateFonts(ulong)
0x1800103c2  test    eax, eax
0x1800103c4  jns     short loc_1800103DF
0x1800103c6  mov     rcx, [rsp+28h]; this
0x1800103cb  lea     r8, aOnecoreWindows_4; "onecore\\windows\\core\\console\\open\\"...
0x1800103d2  mov     r9d, eax; char *
0x1800103d5  mov     edx, 1B6h; void *
0x1800103da  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800103df  add     rsp, 28h
0x1800103e3  retn
```
