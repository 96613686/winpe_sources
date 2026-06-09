# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x1800023b8`
- end: `0x1800023c3`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180009f3e`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800023bc`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x1800023b8  mov     rcx, [rcx+8]
0x1800023bc  jmp     cs:__imp_CoTaskMemFree
```
