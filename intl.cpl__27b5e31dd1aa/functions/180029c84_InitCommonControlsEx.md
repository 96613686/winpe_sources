# InitCommonControlsEx

- ea: `0x180029c84`
- end: `0x180029ccc`
- name: `InitCommonControlsEx`
- size: `72`
- prototype: `BOOL __stdcall(const INITCOMMONCONTROLSEX *picce)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a480`
- `0x1800141a0`

## callees

- `0x180029c84`
- `0x180029e64`
- `0x18002b010`

## string_xrefs

- `0x180029c9a`: `InitCommonControlsEx`

## pseudocode

```c
BOOL __stdcall InitCommonControlsEx(const INITCOMMONCONTROLSEX *picce)
{
  __int64 (__fastcall *v1)(const INITCOMMONCONTROLSEX *); // rax

  v1 = (__int64 (__fastcall *)(const INITCOMMONCONTROLSEX *))qword_18003A800;
  if ( qword_18003A800 == -1 )
  {
    GetProcFromComCtl32(&qword_18003A800, "InitCommonControlsEx");
    v1 = (__int64 (__fastcall *)(const INITCOMMONCONTROLSEX *))qword_18003A800;
  }
  if ( v1 )
    LODWORD(v1) = v1(picce);
  return (int)v1;
}

```

## disassembly

```asm
0x180029c84  push    rbx
0x180029c86  sub     rsp, 20h
0x180029c8a  mov     rax, cs:qword_18003A800
0x180029c91  mov     rbx, rcx
0x180029c94  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029c98  jnz     short loc_180029CB4
0x180029c9a  lea     rdx, aInitcommoncont; "InitCommonControlsEx"
0x180029ca1  lea     rcx, qword_18003A800
0x180029ca8  call    _GetProcFromComCtl32
0x180029cad  mov     rax, cs:qword_18003A800
0x180029cb4  test    rax, rax
0x180029cb7  jz      short loc_180029CC6
0x180029cb9  mov     rcx, rbx
0x180029cbc  add     rsp, 20h
0x180029cc0  pop     rbx
0x180029cc1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180029cc6  add     rsp, 20h
0x180029cca  pop     rbx
0x180029ccb  retn
```
