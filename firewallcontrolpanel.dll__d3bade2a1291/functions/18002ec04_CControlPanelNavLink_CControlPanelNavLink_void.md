# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x18002ec04`
- end: `0x18002ec39`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ed38`

## callees

- `0x18002ec40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec1b`
- `USER32!DestroyIcon` at `0x18002ec25`
- `USER32!DestroyIcon` at `0x18002ec25`

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
0x18002ec04  push    rbx
0x18002ec06  sub     rsp, 20h
0x18002ec0a  mov     rbx, rcx
0x18002ec0d  mov     rcx, [rcx+8]; pv
0x18002ec11  call    cs:__imp_CoTaskMemFree
0x18002ec17  mov     rcx, [rbx+10h]; pv
0x18002ec1b  call    cs:__imp_CoTaskMemFree
0x18002ec21  mov     rcx, [rbx+18h]; hIcon
0x18002ec25  call    cs:__imp_DestroyIcon
0x18002ec2b  lea     rcx, [rbx+20h]; this
0x18002ec2f  add     rsp, 20h
0x18002ec33  pop     rbx
0x18002ec34  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
