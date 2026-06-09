# DPA_DeletePtr

- ea: `0x18001c4f0`
- end: `0x18001c53e`
- name: `DPA_DeletePtr`
- size: `78`
- prototype: `PVOID __stdcall(HDPA hdpa, int i)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001127c`

## callees

- `0x18001c4f0`
- `0x18001cc10`
- `0x18001f010`

## pseudocode

```c
PVOID __stdcall DPA_DeletePtr(HDPA hdpa, int i)
{
  PVOID result; // rax

  result = (PVOID)qword_180028270;
  if ( qword_180028270 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180028270, (const CHAR *)0x150);
    result = (PVOID)qword_180028270;
  }
  if ( result )
    return (PVOID)((__int64 (__fastcall *)(HDPA, _QWORD))result)(hdpa, (unsigned int)i);
  return result;
}

```

## disassembly

```asm
0x18001c4f0  mov     [rsp+arg_0], rbx
0x18001c4f5  push    rdi
0x18001c4f6  sub     rsp, 20h
0x18001c4fa  mov     rax, cs:qword_180028270
0x18001c501  mov     ebx, edx
0x18001c503  mov     rdi, rcx
0x18001c506  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c50a  jnz     short loc_18001C524
0x18001c50c  mov     edx, 150h
0x18001c511  lea     rcx, qword_180028270
0x18001c518  call    _GetProcFromComCtl32
0x18001c51d  mov     rax, cs:qword_180028270
0x18001c524  test    rax, rax
0x18001c527  jz      short loc_18001C533
0x18001c529  mov     edx, ebx
0x18001c52b  mov     rcx, rdi
0x18001c52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c533  mov     rbx, [rsp+28h+arg_0]
0x18001c538  add     rsp, 20h
0x18001c53c  pop     rdi
0x18001c53d  retn
```
