# CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)

- ea: `0x18001c600`
- end: `0x18001c63b`
- name: `??1CControlPanelNavLinkCommand@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CControlPanelNavLinkCommand *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001c5c4`

## callees

- `0x180004038`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c61f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c61f`

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
0x18001c600  push    rbx
0x18001c602  sub     rsp, 20h
0x18001c606  mov     rbx, rcx
0x18001c609  mov     rcx, [rcx+8]; pv
0x18001c60d  call    cs:__imp_CoTaskMemFree
0x18001c613  mov     rcx, [rbx+10h]; pv
0x18001c617  mov     qword ptr [rbx+8], 0
0x18001c61f  call    cs:__imp_CoTaskMemFree
0x18001c625  mov     rcx, [rbx+28h]; lpMem
0x18001c629  mov     qword ptr [rbx+10h], 0
0x18001c631  add     rsp, 20h
0x18001c635  pop     rbx
0x18001c636  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
