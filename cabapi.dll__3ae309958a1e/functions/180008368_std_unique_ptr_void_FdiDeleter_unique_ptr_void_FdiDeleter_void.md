# std::unique_ptr<void *,FdiDeleter>::~unique_ptr<void *,FdiDeleter>(void)

- ea: `0x180008368`
- end: `0x180008391`
- name: `??1?$unique_ptr@PEAXUFdiDeleter@@@std@@QEAA@XZ`
- size: `41`
- prototype: `BOOL __fastcall(HFDI **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013fb8`

## callees

- `0x180008368`

## import_xrefs

- `Cabinet!__imp_FDIDestroy` at `0x18000837e`
- `Cabinet!__imp_FDIDestroy` at `0x18000837e`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<void *,FdiDeleter>::~unique_ptr<void *,FdiDeleter>(HFDI **a1)
{
  HFDI *v1; // rbx
  BOOL result; // eax

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
    {
      result = FDIDestroy(*v1);
      *v1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008368  push    rbx
0x18000836a  sub     rsp, 20h
0x18000836e  mov     rbx, [rcx]
0x180008371  test    rbx, rbx
0x180008374  jz      short loc_18000838B
0x180008376  mov     rcx, [rbx]; hfdi
0x180008379  test    rcx, rcx
0x18000837c  jz      short loc_18000838B
0x18000837e  call    cs:__imp_FDIDestroy
0x180008384  mov     qword ptr [rbx], 0
0x18000838b  add     rsp, 20h
0x18000838f  pop     rbx
0x180008390  retn
```
