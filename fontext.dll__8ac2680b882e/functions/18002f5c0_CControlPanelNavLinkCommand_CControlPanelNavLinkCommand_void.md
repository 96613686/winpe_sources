# CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)

- ea: `0x18002f5c0`
- end: `0x18002f5fb`
- name: `??1CControlPanelNavLinkCommand@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CControlPanelNavLinkCommand *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002f584`

## callees

- `0x18001c0fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f5df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f5df`

## pseudocode

```c
void __fastcall CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(LPVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CoTaskMemFree(this[1]);
  v2 = this[2];
  this[1] = 0;
  CoTaskMemFree(v2);
  v3 = this[5];
  this[2] = 0;
  operator delete(v3);
}

```

## disassembly

```asm
0x18002f5c0  push    rbx
0x18002f5c2  sub     rsp, 20h
0x18002f5c6  mov     rbx, rcx
0x18002f5c9  mov     rcx, [rcx+8]; pv
0x18002f5cd  call    cs:__imp_CoTaskMemFree
0x18002f5d3  mov     rcx, [rbx+10h]; pv
0x18002f5d7  mov     qword ptr [rbx+8], 0
0x18002f5df  call    cs:__imp_CoTaskMemFree
0x18002f5e5  mov     rcx, [rbx+28h]; lpMem
0x18002f5e9  mov     qword ptr [rbx+10h], 0
0x18002f5f1  add     rsp, 20h
0x18002f5f5  pop     rbx
0x18002f5f6  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
