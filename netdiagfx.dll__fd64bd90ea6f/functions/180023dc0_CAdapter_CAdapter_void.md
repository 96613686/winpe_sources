# CAdapter::~CAdapter(void)

- ea: `0x180023dc0`
- end: `0x180023de7`
- name: `??1CAdapter@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e3b5`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023dcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023dcc`

## pseudocode

```c
void __fastcall CAdapter::~CAdapter(LPVOID *this)
{
  CoTaskMemFree(*this);
  *this = 0;
  this[1] = 0;
}

```

## disassembly

```asm
0x180023dc0  push    rbx
0x180023dc2  sub     rsp, 20h
0x180023dc6  mov     rbx, rcx
0x180023dc9  mov     rcx, [rcx]; pv
0x180023dcc  call    cs:__imp_CoTaskMemFree
0x180023dd2  mov     qword ptr [rbx], 0
0x180023dd9  mov     qword ptr [rbx+8], 0
0x180023de1  add     rsp, 20h
0x180023de5  pop     rbx
0x180023de6  retn
```
