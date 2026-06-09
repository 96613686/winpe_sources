# TSmartPointer<CCatalogSchemaWriter>::~TSmartPointer<CCatalogSchemaWriter>(void)

- ea: `0x180023dc0`
- end: `0x180023df8`
- name: `??1?$TSmartPointer@VCCatalogSchemaWriter@@@@QEAA@XZ`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002ef23`

## callees

- `0x180023dc0`
- `0x18002ad50`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180023de0`
- `ole32!CoTaskMemFree` at `0x180023de0`

## pseudocode

```c
void __fastcall TSmartPointer<CCatalogSchemaWriter>::~TSmartPointer<CCatalogSchemaWriter>(LPVOID **a1)
{
  LPVOID *v2; // rbx

  v2 = *a1;
  if ( *a1 )
  {
    CCatalogSchemaWriter::~CCatalogSchemaWriter(*a1);
    CoTaskMemFree(v2);
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x180023dc0  mov     [rsp+arg_0], rbx
0x180023dc5  push    rdi
0x180023dc6  sub     rsp, 20h
0x180023dca  mov     rdi, rcx
0x180023dcd  mov     rbx, [rcx]
0x180023dd0  test    rbx, rbx
0x180023dd3  jz      short loc_180023DE6
0x180023dd5  mov     rcx, rbx; this
0x180023dd8  call    ??1CCatalogSchemaWriter@@QEAA@XZ; CCatalogSchemaWriter::~CCatalogSchemaWriter(void)
0x180023ddd  mov     rcx, rbx; pv
0x180023de0  call    cs:__imp_CoTaskMemFree
0x180023de6  mov     qword ptr [rdi], 0
0x180023ded  mov     rbx, [rsp+28h+arg_0]
0x180023df2  add     rsp, 20h
0x180023df6  pop     rdi
0x180023df7  retn
```
