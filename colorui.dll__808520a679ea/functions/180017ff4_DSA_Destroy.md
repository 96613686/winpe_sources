# DSA_Destroy

- ea: `0x180017ff4`
- end: `0x18001803a`
- name: `DSA_Destroy`
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

- `0x180017ff4`
- `0x1800183e4`
- `0x180019010`

## pseudocode

```c
BOOL __stdcall DSA_Destroy(HDSA hdsa)
{
  __int64 (__fastcall *v1)(HDSA); // rax

  v1 = (__int64 (__fastcall *)(HDSA))qword_180021400;
  if ( qword_180021400 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180021400, (const CHAR *)0x141);
    v1 = (__int64 (__fastcall *)(HDSA))qword_180021400;
  }
  if ( v1 )
    LODWORD(v1) = v1(hdsa);
  return (int)v1;
}

```

## disassembly

```asm
0x180017ff4  push    rbx
0x180017ff6  sub     rsp, 20h
0x180017ffa  mov     rax, cs:qword_180021400
0x180018001  mov     rbx, rcx
0x180018004  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018008  jnz     short loc_180018022
0x18001800a  mov     edx, 141h
0x18001800f  lea     rcx, qword_180021400
0x180018016  call    _GetProcFromComCtl32
0x18001801b  mov     rax, cs:qword_180021400
0x180018022  test    rax, rax
0x180018025  jz      short loc_180018034
0x180018027  mov     rcx, rbx
0x18001802a  add     rsp, 20h
0x18001802e  pop     rbx
0x18001802f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180018034  add     rsp, 20h
0x180018038  pop     rbx
0x180018039  retn
```
