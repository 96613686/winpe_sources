# _attribute_t::FreeAll(void)

- ea: `0x18000d42c`
- end: `0x18000d450`
- name: `?FreeAll@_attribute_t@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(_attribute_t *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d158`
- `0x18000d274`
- `0x18000d48c`
- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`

## callees

- `0x18000d4d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d43d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d43d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _attribute_t::FreeAll(_attribute_t *this)
{
  _attribute_t::FreeValue(this);
  CoTaskMemFree(*(LPVOID *)this);
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18000d42c  push    rbx
0x18000d42e  sub     rsp, 20h
0x18000d432  mov     rbx, rcx
0x18000d435  call    ?FreeValue@_attribute_t@@QEAAXXZ; _attribute_t::FreeValue(void)
0x18000d43a  mov     rcx, [rbx]; pv
0x18000d43d  call    cs:__imp_CoTaskMemFree
0x18000d443  mov     qword ptr [rbx], 0
0x18000d44a  add     rsp, 20h
0x18000d44e  pop     rbx
0x18000d44f  retn
```
