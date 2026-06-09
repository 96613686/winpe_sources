# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x18000267c`
- end: `0x180002687`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800102ce`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002680`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x18000267c  mov     rcx, [rcx+8]
0x180002680  jmp     cs:__imp_CoTaskMemFree
```
