# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x1800041e0`
- end: `0x1800041eb`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18001fc1e`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800041e4`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x1800041e0  mov     rcx, [rcx+8]
0x1800041e4  jmp     cs:__imp_CoTaskMemFree
```
