# CleanupWebDriverStatics

- ea: `0x1800679d4`
- end: `0x180067a50`
- name: `CleanupWebDriverStatics`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008450`
- `0x18006784c`

## callees

- `0x18002b560`
- `0x1800679d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067a23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067a23`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1800679e4`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1800679e4`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180067a06`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180067a06`

## pseudocode

```c
void CleanupWebDriverStatics()
{
  if ( BoundaryDescriptor )
  {
    DeleteBoundaryDescriptor(BoundaryDescriptor);
    BoundaryDescriptor = 0;
  }
  if ( Handle )
  {
    ClosePrivateNamespace(Handle, 1u);
    Handle = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  operator delete(Block);
  Block = 0;
}

```

## disassembly

```asm
0x1800679d4  sub     rsp, 28h
0x1800679d8  mov     rcx, cs:BoundaryDescriptor; BoundaryDescriptor
0x1800679df  test    rcx, rcx
0x1800679e2  jz      short loc_1800679F5
0x1800679e4  call    cs:__imp_DeleteBoundaryDescriptor
0x1800679ea  mov     cs:BoundaryDescriptor, 0
0x1800679f5  mov     rcx, cs:Handle; Handle
0x1800679fc  test    rcx, rcx
0x1800679ff  jz      short loc_180067A17
0x180067a01  mov     edx, 1; Flags
0x180067a06  call    cs:__imp_ClosePrivateNamespace
0x180067a0c  mov     cs:Handle, 0
0x180067a17  mov     rcx, cs:hObject; hObject
0x180067a1e  test    rcx, rcx
0x180067a21  jz      short loc_180067A34
0x180067a23  call    cs:__imp_CloseHandle
0x180067a29  mov     cs:hObject, 0
0x180067a34  mov     rcx, cs:Block; Block
0x180067a3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067a40  mov     cs:Block, 0
0x180067a4b  add     rsp, 28h
0x180067a4f  retn
```
