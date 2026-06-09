# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x18000e4b0`
- end: `0x18000e4bb`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034f85`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x18000e4b0  mov     rcx, [rcx+8]
0x18000e4b4  jmp     cs:__imp_CoTaskMemFree
```
