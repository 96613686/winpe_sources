# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x18002f584`
- end: `0x18002f5b9`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f644`

## callees

- `0x18002f5c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f59b`
- `USER32!DestroyIcon` at `0x18002f5a5`
- `USER32!DestroyIcon` at `0x18002f5a5`

## pseudocode

```c
void __fastcall CControlPanelNavLink::~CControlPanelNavLink(CControlPanelNavLink *this)
{
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 2));
  DestroyIcon(*((HICON *)this + 3));
  CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand((CControlPanelNavLink *)((char *)this + 32));
}

```

## disassembly

```asm
0x18002f584  push    rbx
0x18002f586  sub     rsp, 20h
0x18002f58a  mov     rbx, rcx
0x18002f58d  mov     rcx, [rcx+8]; pv
0x18002f591  call    cs:__imp_CoTaskMemFree
0x18002f597  mov     rcx, [rbx+10h]; pv
0x18002f59b  call    cs:__imp_CoTaskMemFree
0x18002f5a1  mov     rcx, [rbx+18h]; hIcon
0x18002f5a5  call    cs:__imp_DestroyIcon
0x18002f5ab  lea     rcx, [rbx+20h]; this
0x18002f5af  add     rsp, 20h
0x18002f5b3  pop     rbx
0x18002f5b4  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
