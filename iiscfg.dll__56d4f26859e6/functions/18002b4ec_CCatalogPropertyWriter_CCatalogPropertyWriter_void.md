# CCatalogPropertyWriter::~CCatalogPropertyWriter(void)

- ea: `0x18002b4ec`
- end: `0x18002b523`
- name: `??1CCatalogPropertyWriter@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CCatalogPropertyWriter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002af50`

## callees

- `0x18002b4ec`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002b501`
- `ole32!CoTaskMemFree` at `0x18002b501`

## pseudocode

```c
void __fastcall CCatalogPropertyWriter::~CCatalogPropertyWriter(CCatalogPropertyWriter *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 29);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 29) = 0;
  }
  *((_QWORD *)this + 30) = 0;
}

```

## disassembly

```asm
0x18002b4ec  push    rbx
0x18002b4ee  sub     rsp, 20h
0x18002b4f2  mov     rbx, rcx
0x18002b4f5  mov     rcx, [rcx+0E8h]; pv
0x18002b4fc  test    rcx, rcx
0x18002b4ff  jz      short loc_18002B512
0x18002b501  call    cs:__imp_CoTaskMemFree
0x18002b507  mov     qword ptr [rbx+0E8h], 0
0x18002b512  mov     qword ptr [rbx+0F0h], 0
0x18002b51d  add     rsp, 20h
0x18002b521  pop     rbx
0x18002b522  retn
```
