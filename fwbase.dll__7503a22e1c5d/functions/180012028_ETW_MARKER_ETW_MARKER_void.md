# _ETW_MARKER::~_ETW_MARKER(void)

- ea: `0x180012028`
- end: `0x180012048`
- name: `??1_ETW_MARKER@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(_ETW_MARKER *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c420`
- `0x18002c560`
- `0x18002c6a0`
- `0x18002c840`
- `0x18002c980`
- `0x18002cac0`
- `0x18002cc00`
- `0x18002cd20`

## callees

- `0x180012028`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180012041`

## pseudocode

```c
void __fastcall _ETW_MARKER::~_ETW_MARKER(_ETW_MARKER *this)
{
  if ( g_Provider )
    EtwEventWrite(g_Provider, *(_QWORD *)this, 0, 0);
}

```

## disassembly

```asm
0x180012028  mov     rdx, rcx
0x18001202b  mov     rcx, cs:g_Provider
0x180012032  test    rcx, rcx
0x180012035  jnz     short loc_180012038
0x180012037  retn
0x180012038  mov     rdx, [rdx]
0x18001203b  xor     r9d, r9d
0x18001203e  xor     r8d, r8d
0x180012041  jmp     cs:__imp_EtwEventWrite
```
