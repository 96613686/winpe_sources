# DSA_Create

- ea: `0x180017f54`
- end: `0x180017fa0`
- name: `DSA_Create`
- size: `76`
- prototype: `HDSA __stdcall(int cbItem, int cItemGrow)`
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

- `0x180017f54`
- `0x1800183e4`
- `0x180019010`

## pseudocode

```c
HDSA __stdcall DSA_Create(int cbItem, int cItemGrow)
{
  HDSA result; // rax

  result = (HDSA)qword_180021410;
  if ( qword_180021410 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180021410, (const CHAR *)0x140);
    result = (HDSA)qword_180021410;
  }
  if ( result )
    return (HDSA)((__int64 (__fastcall *)(_QWORD, _QWORD))result)((unsigned int)cbItem, (unsigned int)cItemGrow);
  return result;
}

```

## disassembly

```asm
0x180017f54  mov     [rsp+arg_0], rbx
0x180017f59  push    rdi
0x180017f5a  sub     rsp, 20h
0x180017f5e  mov     rax, cs:qword_180021410
0x180017f65  mov     ebx, edx
0x180017f67  mov     edi, ecx
0x180017f69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017f6d  jnz     short loc_180017F87
0x180017f6f  mov     edx, 140h
0x180017f74  lea     rcx, qword_180021410
0x180017f7b  call    _GetProcFromComCtl32
0x180017f80  mov     rax, cs:qword_180021410
0x180017f87  test    rax, rax
0x180017f8a  jz      short loc_180017F95
0x180017f8c  mov     edx, ebx
0x180017f8e  mov     ecx, edi
0x180017f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f95  mov     rbx, [rsp+28h+arg_0]
0x180017f9a  add     rsp, 20h
0x180017f9e  pop     rdi
0x180017f9f  retn
```
