# DPA_CreateEx

- ea: `0x18001c49c`
- end: `0x18001c4ea`
- name: `DPA_CreateEx`
- size: `78`
- prototype: `HDPA __stdcall(int cpGrow, HANDLE hheap)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010f20`

## callees

- `0x18001c49c`
- `0x18001cc10`
- `0x18001f010`

## pseudocode

```c
HDPA __stdcall DPA_CreateEx(int cpGrow, HANDLE hheap)
{
  HDPA result; // rax

  result = (HDPA)qword_180028298;
  if ( qword_180028298 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180028298, (const CHAR *)0x154);
    result = (HDPA)qword_180028298;
  }
  if ( result )
    return (HDPA)((__int64 (__fastcall *)(_QWORD, HANDLE))result)((unsigned int)cpGrow, hheap);
  return result;
}

```

## disassembly

```asm
0x18001c49c  mov     [rsp+arg_0], rbx
0x18001c4a1  push    rdi
0x18001c4a2  sub     rsp, 20h
0x18001c4a6  mov     rax, cs:qword_180028298
0x18001c4ad  mov     rbx, rdx
0x18001c4b0  mov     edi, ecx
0x18001c4b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c4b6  jnz     short loc_18001C4D0
0x18001c4b8  mov     edx, 154h
0x18001c4bd  lea     rcx, qword_180028298
0x18001c4c4  call    _GetProcFromComCtl32
0x18001c4c9  mov     rax, cs:qword_180028298
0x18001c4d0  test    rax, rax
0x18001c4d3  jz      short loc_18001C4DF
0x18001c4d5  mov     rdx, rbx
0x18001c4d8  mov     ecx, edi
0x18001c4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4df  mov     rbx, [rsp+28h+arg_0]
0x18001c4e4  add     rsp, 20h
0x18001c4e8  pop     rdi
0x18001c4e9  retn
```
