# DPA_Sort

- ea: `0x18001c6b0`
- end: `0x18001c710`
- name: `DPA_Sort`
- size: `96`
- prototype: `BOOL __stdcall(HDPA hdpa, PFNDACOMPARE pfnCompare, LPARAM lParam)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010238`

## callees

- `0x18001c6b0`
- `0x18001cc10`
- `0x18001f010`

## pseudocode

```c
BOOL __stdcall DPA_Sort(HDPA hdpa, PFNDACOMPARE pfnCompare, LPARAM lParam)
{
  __int64 (__fastcall *v3)(HDPA, PFNDACOMPARE, LPARAM); // rax

  v3 = (__int64 (__fastcall *)(HDPA, PFNDACOMPARE, LPARAM))qword_180028268;
  if ( qword_180028268 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180028268, (const CHAR *)0x152);
    v3 = (__int64 (__fastcall *)(HDPA, PFNDACOMPARE, LPARAM))qword_180028268;
  }
  if ( v3 )
    LODWORD(v3) = v3(hdpa, pfnCompare, lParam);
  return (int)v3;
}

```

## disassembly

```asm
0x18001c6b0  mov     [rsp+arg_0], rbx
0x18001c6b5  mov     [rsp+arg_8], rsi
0x18001c6ba  push    rdi
0x18001c6bb  sub     rsp, 20h
0x18001c6bf  mov     rax, cs:qword_180028268
0x18001c6c6  mov     rbx, r8
0x18001c6c9  mov     rdi, rdx
0x18001c6cc  mov     rsi, rcx
0x18001c6cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c6d3  jnz     short loc_18001C6ED
0x18001c6d5  mov     edx, 152h
0x18001c6da  lea     rcx, qword_180028268
0x18001c6e1  call    _GetProcFromComCtl32
0x18001c6e6  mov     rax, cs:qword_180028268
0x18001c6ed  test    rax, rax
0x18001c6f0  jz      short loc_18001C700
0x18001c6f2  mov     r8, rbx
0x18001c6f5  mov     rdx, rdi
0x18001c6f8  mov     rcx, rsi
0x18001c6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c700  mov     rbx, [rsp+28h+arg_0]
0x18001c705  mov     rsi, [rsp+28h+arg_8]
0x18001c70a  add     rsp, 20h
0x18001c70e  pop     rdi
0x18001c70f  retn
```
