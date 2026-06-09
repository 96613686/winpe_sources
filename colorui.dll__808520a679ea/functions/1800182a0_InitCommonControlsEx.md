# InitCommonControlsEx

- ea: `0x1800182a0`
- end: `0x1800182e8`
- name: `InitCommonControlsEx`
- size: `72`
- prototype: `BOOL __stdcall(const INITCOMMONCONTROLSEX *picce)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b8f0`

## callees

- `0x1800182a0`
- `0x1800183e4`
- `0x180019010`

## string_xrefs

- `0x1800182b6`: `InitCommonControlsEx`

## pseudocode

```c
BOOL __stdcall InitCommonControlsEx(const INITCOMMONCONTROLSEX *picce)
{
  __int64 (__fastcall *v1)(const INITCOMMONCONTROLSEX *); // rax

  v1 = (__int64 (__fastcall *)(const INITCOMMONCONTROLSEX *))qword_180021428;
  if ( qword_180021428 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180021428, "InitCommonControlsEx");
    v1 = (__int64 (__fastcall *)(const INITCOMMONCONTROLSEX *))qword_180021428;
  }
  if ( v1 )
    LODWORD(v1) = v1(picce);
  return (int)v1;
}

```

## disassembly

```asm
0x1800182a0  push    rbx
0x1800182a2  sub     rsp, 20h
0x1800182a6  mov     rax, cs:qword_180021428
0x1800182ad  mov     rbx, rcx
0x1800182b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800182b4  jnz     short loc_1800182D0
0x1800182b6  lea     rdx, aInitcommoncont; "InitCommonControlsEx"
0x1800182bd  lea     rcx, qword_180021428
0x1800182c4  call    _GetProcFromComCtl32
0x1800182c9  mov     rax, cs:qword_180021428
0x1800182d0  test    rax, rax
0x1800182d3  jz      short loc_1800182E2
0x1800182d5  mov     rcx, rbx
0x1800182d8  add     rsp, 20h
0x1800182dc  pop     rbx
0x1800182dd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e2  add     rsp, 20h
0x1800182e6  pop     rbx
0x1800182e7  retn
```
