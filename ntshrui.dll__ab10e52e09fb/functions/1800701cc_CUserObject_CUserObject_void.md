# CUserObject::~CUserObject(void)

- ea: `0x1800701cc`
- end: `0x18007020c`
- name: `??1CUserObject@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CUserObject *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053fd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800701e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800701ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800701f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800701e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800701ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800701f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070205`

## pseudocode

```c
void __fastcall CUserObject::~CUserObject(HLOCAL *this)
{
  LocalFree(*this);
  CoTaskMemFree(this[1]);
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[4]);
}

```

## disassembly

```asm
0x1800701cc  push    rbx
0x1800701ce  sub     rsp, 20h
0x1800701d2  mov     rbx, rcx
0x1800701d5  mov     rcx, [rcx]; hMem
0x1800701d8  call    cs:__imp_LocalFree
0x1800701de  mov     rcx, [rbx+8]; pv
0x1800701e2  call    cs:__imp_CoTaskMemFree
0x1800701e8  mov     rcx, [rbx+10h]; pv
0x1800701ec  call    cs:__imp_CoTaskMemFree
0x1800701f2  mov     rcx, [rbx+18h]; pv
0x1800701f6  call    cs:__imp_CoTaskMemFree
0x1800701fc  mov     rcx, [rbx+20h]
0x180070200  add     rsp, 20h
0x180070204  pop     rbx
0x180070205  jmp     cs:__imp_CoTaskMemFree
```
