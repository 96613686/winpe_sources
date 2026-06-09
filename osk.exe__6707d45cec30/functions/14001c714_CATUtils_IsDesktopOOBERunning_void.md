# CATUtils::IsDesktopOOBERunning(void)

- ea: `0x14001c714`
- end: `0x14001c741`
- name: `?IsDesktopOOBERunning@CATUtils@@SA_NXZ`
- size: `45`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c748`
- `0x14001f728`

## callees

- `0x14001c714`

## import_xrefs

- `KERNEL32!OOBEComplete` at `0x14001c725`
- `KERNEL32!OOBEComplete` at `0x14001c725`

## pseudocode

```c
bool CATUtils::IsDesktopOOBERunning(void)
{
  int v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  return (unsigned int)OOBEComplete(&v1) && !v1;
}

```

## disassembly

```asm
0x14001c714  sub     rsp, 28h
0x14001c718  lea     rcx, [rsp+28h+arg_0]
0x14001c71d  mov     [rsp+28h+arg_0], 0
0x14001c725  call    cs:__imp_OOBEComplete
0x14001c72b  test    eax, eax
0x14001c72d  jz      short loc_14001C73A
0x14001c72f  cmp     [rsp+28h+arg_0], 0
0x14001c734  jnz     short loc_14001C73A
0x14001c736  mov     al, 1
0x14001c738  jmp     short loc_14001C73C
0x14001c73a  xor     al, al
0x14001c73c  add     rsp, 28h
0x14001c740  retn
```
