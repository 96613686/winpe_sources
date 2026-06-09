# DSA_DeleteAllItems

- ea: `0x180017fa8`
- end: `0x180017fee`
- name: `DSA_DeleteAllItems`
- size: `70`
- prototype: `BOOL __stdcall(HDSA hdsa)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e244`
- `0x18000e558`
- `0x18000f9c0`
- `0x180010780`
- `0x1800173f8`

## callees

- `0x180017fa8`
- `0x1800183e4`
- `0x180019010`

## pseudocode

```c
BOOL __stdcall DSA_DeleteAllItems(HDSA hdsa)
{
  __int64 (__fastcall *v1)(HDSA); // rax

  v1 = (__int64 (__fastcall *)(HDSA))qword_1800213F0;
  if ( qword_1800213F0 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_1800213F0, (const CHAR *)0x147);
    v1 = (__int64 (__fastcall *)(HDSA))qword_1800213F0;
  }
  if ( v1 )
    LODWORD(v1) = v1(hdsa);
  return (int)v1;
}

```

## disassembly

```asm
0x180017fa8  push    rbx
0x180017faa  sub     rsp, 20h
0x180017fae  mov     rax, cs:qword_1800213F0
0x180017fb5  mov     rbx, rcx
0x180017fb8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017fbc  jnz     short loc_180017FD6
0x180017fbe  mov     edx, 147h
0x180017fc3  lea     rcx, qword_1800213F0
0x180017fca  call    _GetProcFromComCtl32
0x180017fcf  mov     rax, cs:qword_1800213F0
0x180017fd6  test    rax, rax
0x180017fd9  jz      short loc_180017FE8
0x180017fdb  mov     rcx, rbx
0x180017fde  add     rsp, 20h
0x180017fe2  pop     rbx
0x180017fe3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe8  add     rsp, 20h
0x180017fec  pop     rbx
0x180017fed  retn
```
