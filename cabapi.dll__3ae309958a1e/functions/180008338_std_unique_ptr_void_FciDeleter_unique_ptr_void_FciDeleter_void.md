# std::unique_ptr<void *,FciDeleter>::~unique_ptr<void *,FciDeleter>(void)

- ea: `0x180008338`
- end: `0x180008361`
- name: `??1?$unique_ptr@PEAXUFciDeleter@@@std@@QEAA@XZ`
- size: `41`
- prototype: `BOOL __fastcall(HFCI **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001407e`

## callees

- `0x180008338`

## import_xrefs

- `Cabinet!__imp_FCIDestroy` at `0x18000834e`
- `Cabinet!__imp_FCIDestroy` at `0x18000834e`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<void *,FciDeleter>::~unique_ptr<void *,FciDeleter>(HFCI **a1)
{
  HFCI *v1; // rbx
  BOOL result; // eax

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
    {
      result = FCIDestroy(*v1);
      *v1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008338  push    rbx
0x18000833a  sub     rsp, 20h
0x18000833e  mov     rbx, [rcx]
0x180008341  test    rbx, rbx
0x180008344  jz      short loc_18000835B
0x180008346  mov     rcx, [rbx]; hfci
0x180008349  test    rcx, rcx
0x18000834c  jz      short loc_18000835B
0x18000834e  call    cs:__imp_FCIDestroy
0x180008354  mov     qword ptr [rbx], 0
0x18000835b  add     rsp, 20h
0x18000835f  pop     rbx
0x180008360  retn
```
