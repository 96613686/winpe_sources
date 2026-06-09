# EtwpCacheMaxLogger(void)

- ea: `0x180008de0`
- end: `0x180008e35`
- name: `?EtwpCacheMaxLogger@@YAXXZ`
- size: `85`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000935c`
- `0x18000ad70`

## callees

- `0x180001eca`
- `0x180008de0`

## pseudocode

```c
void EtwpCacheMaxLogger(void)
{
  int v0; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  if ( !EtwpMaxLoggers && ((unsigned int)NtTraceControl_0(42, 0, 0, &EtwpMaxLoggers, 4, &v0) || v0 != 4) )
    EtwpMaxLoggers = 128;
}

```

## disassembly

```asm
0x180008de0  sub     rsp, 38h
0x180008de4  cmp     cs:?EtwpMaxLoggers@@3KA, 0; ulong EtwpMaxLoggers
0x180008deb  mov     [rsp+38h+arg_0], 0
0x180008df3  jnz     short loc_180008E30
0x180008df5  xor     edx, edx
0x180008df7  lea     rax, [rsp+38h+arg_0]
0x180008dfc  mov     [rsp+38h+var_10], rax
0x180008e01  lea     r9, ?EtwpMaxLoggers@@3KA; ulong EtwpMaxLoggers
0x180008e08  xor     r8d, r8d
0x180008e0b  mov     [rsp+38h+var_18], 4
0x180008e13  lea     ecx, [rdx+2Ah]
0x180008e16  call    NtTraceControl_0
0x180008e1b  test    eax, eax
0x180008e1d  jnz     short loc_180008E26
0x180008e1f  cmp     [rsp+38h+arg_0], 4
0x180008e24  jz      short loc_180008E30
0x180008e26  mov     cs:?EtwpMaxLoggers@@3KA, 80h; ulong EtwpMaxLoggers
0x180008e30  add     rsp, 38h
0x180008e34  retn
```
