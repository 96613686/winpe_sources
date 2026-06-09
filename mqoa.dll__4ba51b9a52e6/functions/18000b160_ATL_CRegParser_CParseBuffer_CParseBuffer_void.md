# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x18000b160`
- end: `0x18000b174`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(ATL::CRegParser::CParseBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180027c21`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000b168`
- `ole32!CoTaskMemFree` at `0x18000b168`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x18000b160  sub     rsp, 28h
0x18000b164  mov     rcx, [rcx+8]; pv
0x18000b168  call    cs:__imp_CoTaskMemFree
0x18000b16e  nop
0x18000b16f  add     rsp, 28h
0x18000b173  retn
```
