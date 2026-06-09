# ALLOC_NONPAGED

- ea: `0x140001b70`
- end: `0x140001bd1`
- name: `ALLOC_NONPAGED`
- size: `97`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140001fc0`
- `0x1400024e0`
- `0x140010d20`
- `0x140011144`
- `0x140011518`
- `0x1400154b8`
- `0x140018998`
- `0x14001b8a0`
- `0x14001d940`
- `0x14001dbc8`
- `0x14001dc40`
- `0x14001ddf0`
- `0x14001e3c0`

## callees

- `0x140001b70`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x140001ba8`
- `ntoskrnl!ExAllocatePool3` at `0x140001ba8`

## pseudocode

```c
unsigned int *__fastcall ALLOC_NONPAGED(unsigned int a1, unsigned int a2)
{
  unsigned int *Pool3; // rax
  _QWORD v5[3]; // [rsp+30h] [rbp-18h] BYREF

  v5[1] = 16;
  v5[0] = 1;
  if ( a1 + 16 < a1 )
    return 0;
  Pool3 = (unsigned int *)ExAllocatePool3(64, a1 + 16, a2, v5, 1);
  if ( !Pool3 )
    return 0;
  *Pool3 = a1;
  Pool3[1] = -1061437218;
  return Pool3 + 4;
}

```

## disassembly

```asm
0x140001b70  push    rbx
0x140001b72  sub     rsp, 40h
0x140001b76  lea     eax, [rcx+10h]
0x140001b79  mov     [rsp+48h+var_10], 10h
0x140001b82  mov     [rsp+48h+var_18], 1
0x140001b8b  mov     r8d, edx
0x140001b8e  mov     ebx, ecx
0x140001b90  cmp     eax, ecx
0x140001b92  jb      short loc_140001BC8
0x140001b94  mov     edx, eax
0x140001b96  lea     r9, [rsp+48h+var_18]
0x140001b9b  mov     ecx, 40h ; '@'
0x140001ba0  mov     [rsp+48h+var_28], 1
0x140001ba8  call    cs:__imp_ExAllocatePool3
0x140001baf  nop     dword ptr [rax+rax+00h]
0x140001bb4  test    rax, rax
0x140001bb7  jz      short loc_140001BC8
0x140001bb9  mov     [rax], ebx
0x140001bbb  mov     dword ptr [rax+4], 0C0BBC0DEh
0x140001bc2  add     rax, 10h
0x140001bc6  jmp     short loc_140001BCA
0x140001bc8  xor     eax, eax
0x140001bca  add     rsp, 40h
0x140001bce  pop     rbx
0x140001bcf  retn
```
