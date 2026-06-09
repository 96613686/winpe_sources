# LuafvCreateStreamHandleContext

- ea: `0x140021730`
- end: `0x14002177f`
- name: `LuafvCreateStreamHandleContext`
- size: `79`
- prototype: `NTSTATUS __fastcall(PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140025820`

## callees

- `0x140021730`

## import_xrefs

- `FLTMGR!FltAllocateContext` at `0x140021760`
- `FLTMGR!FltAllocateContext` at `0x140021760`

## pseudocode

```c
NTSTATUS __fastcall LuafvCreateStreamHandleContext(PFLT_CONTEXT *a1)
{
  NTSTATUS result; // eax
  PFLT_CONTEXT ReturnedContext; // [rsp+48h] [rbp+10h] BYREF

  ReturnedContext = 0;
  result = FltAllocateContext(LuafvDriverData, 0x10u, 0x38u, PagedPool, &ReturnedContext);
  if ( result >= 0 )
    *a1 = ReturnedContext;
  return result;
}

```

## disassembly

```asm
0x140021730  push    rbx
0x140021732  sub     rsp, 30h
0x140021736  mov     edx, 10h; ContextType
0x14002173b  mov     [rsp+38h+arg_8], 0
0x140021744  mov     rbx, rcx
0x140021747  lea     rax, [rsp+38h+arg_8]
0x14002174c  mov     rcx, cs:LuafvDriverData; Filter
0x140021753  mov     [rsp+38h+ReturnedContext], rax; ReturnedContext
0x140021758  lea     r9d, [rdx-0Fh]; PoolType
0x14002175c  lea     r8d, [rdx+28h]; ContextSize
0x140021760  call    cs:__imp_FltAllocateContext
0x140021767  nop     dword ptr [rax+rax+00h]
0x14002176c  test    eax, eax
0x14002176e  js      short loc_140021778
0x140021770  mov     rcx, [rsp+38h+arg_8]
0x140021775  mov     [rbx], rcx
0x140021778  add     rsp, 30h
0x14002177c  pop     rbx
0x14002177d  retn
```
