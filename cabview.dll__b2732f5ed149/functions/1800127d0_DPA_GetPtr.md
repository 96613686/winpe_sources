# DPA_GetPtr

- ea: `0x1800127d0`
- end: `0x180012820`
- name: `DPA_GetPtr`
- size: `80`
- prototype: `PVOID __stdcall(HDPA hdpa, INT_PTR i)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ba40`
- `0x18000bfa4`
- `0x18000cc80`
- `0x18000d130`
- `0x18000d968`
- `0x18000f000`

## callees

- `0x1800127d0`
- `0x1800128e4`
- `0x180013010`

## pseudocode

```c
PVOID __stdcall DPA_GetPtr(HDPA hdpa, INT_PTR i)
{
  PVOID result; // rax

  result = (PVOID)qword_18001A110;
  if ( qword_18001A110 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_18001A110, (const CHAR *)0x14C);
    result = (PVOID)qword_18001A110;
  }
  if ( result )
    return (PVOID)((__int64 (__fastcall *)(HDPA, INT_PTR))result)(hdpa, i);
  return result;
}

```

## disassembly

```asm
0x1800127d0  mov     [rsp+arg_0], rbx
0x1800127d5  push    rdi
0x1800127d6  sub     rsp, 20h
0x1800127da  mov     rax, cs:qword_18001A110
0x1800127e1  mov     rbx, rdx
0x1800127e4  mov     rdi, rcx
0x1800127e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800127eb  jnz     short loc_180012805
0x1800127ed  mov     edx, 14Ch
0x1800127f2  lea     rcx, qword_18001A110
0x1800127f9  call    _GetProcFromComCtl32
0x1800127fe  mov     rax, cs:qword_18001A110
0x180012805  test    rax, rax
0x180012808  jz      short loc_180012815
0x18001280a  mov     rdx, rbx
0x18001280d  mov     rcx, rdi
0x180012810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012815  mov     rbx, [rsp+28h+arg_0]
0x18001281a  add     rsp, 20h
0x18001281e  pop     rdi
0x18001281f  retn
```
