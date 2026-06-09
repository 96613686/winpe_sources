# _attributes_array_t::FreeAll(void)

- ea: `0x18000d458`
- end: `0x18000d484`
- name: `?FreeAll@_attributes_array_t@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c8f8`
- `0x18000c920`
- `0x18000cf88`
- `0x18000d274`
- `0x18000ef4c`
- `0x18000f560`
- `0x180017c3c`
- `0x180018040`
- `0x18001865c`

## callees

- `0x18000d48c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d46a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d46a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _attributes_array_t::FreeAll(LPVOID *this)
{
  _attributes_array_t::FreeElements((_attributes_array_t *)this);
  CoTaskMemFree(this[1]);
  this[1] = 0;
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x18000d458  push    rbx
0x18000d45a  sub     rsp, 20h
0x18000d45e  mov     rbx, rcx
0x18000d461  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000d466  mov     rcx, [rbx+8]; pv
0x18000d46a  call    cs:__imp_CoTaskMemFree
0x18000d470  mov     qword ptr [rbx+8], 0
0x18000d478  mov     dword ptr [rbx], 0
0x18000d47e  add     rsp, 20h
0x18000d482  pop     rbx
0x18000d483  retn
```
