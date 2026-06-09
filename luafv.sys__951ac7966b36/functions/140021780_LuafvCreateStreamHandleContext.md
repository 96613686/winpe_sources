# LuafvCreateStreamHandleContext

- ea: `0x140021780`
- end: `0x1400217cf`
- name: `LuafvCreateStreamHandleContext`
- size: `79`
- prototype: `NTSTATUS __fastcall(PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400258a0`

## callees

- `0x140021780`

## import_xrefs

- `FLTMGR!FltAllocateContext` at `0x1400217b0`
- `FLTMGR!FltAllocateContext` at `0x1400217b0`

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
0x140021780  push    rbx
0x140021782  sub     rsp, 30h
0x140021786  mov     edx, 10h; ContextType
0x14002178b  mov     [rsp+38h+arg_8], 0
0x140021794  mov     rbx, rcx
0x140021797  lea     rax, [rsp+38h+arg_8]
0x14002179c  mov     rcx, cs:LuafvDriverData; Filter
0x1400217a3  mov     [rsp+38h+ReturnedContext], rax; ReturnedContext
0x1400217a8  lea     r9d, [rdx-0Fh]; PoolType
0x1400217ac  lea     r8d, [rdx+28h]; ContextSize
0x1400217b0  call    cs:__imp_FltAllocateContext
0x1400217b7  nop     dword ptr [rax+rax+00h]
0x1400217bc  test    eax, eax
0x1400217be  js      short loc_1400217C8
0x1400217c0  mov     rcx, [rsp+38h+arg_8]
0x1400217c5  mov     [rbx], rcx
0x1400217c8  add     rsp, 30h
0x1400217cc  pop     rbx
0x1400217cd  retn
```
