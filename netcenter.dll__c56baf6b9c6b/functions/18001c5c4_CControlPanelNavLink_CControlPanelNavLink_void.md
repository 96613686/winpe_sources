# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x18001c5c4`
- end: `0x18001c5f9`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x18001c600`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5db`
- `USER32!DestroyIcon` at `0x18001c5e5`
- `USER32!DestroyIcon` at `0x18001c5e5`

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
0x18001c5c4  push    rbx
0x18001c5c6  sub     rsp, 20h
0x18001c5ca  mov     rbx, rcx
0x18001c5cd  mov     rcx, [rcx+8]; pv
0x18001c5d1  call    cs:__imp_CoTaskMemFree
0x18001c5d7  mov     rcx, [rbx+10h]; pv
0x18001c5db  call    cs:__imp_CoTaskMemFree
0x18001c5e1  mov     rcx, [rbx+18h]; hIcon
0x18001c5e5  call    cs:__imp_DestroyIcon
0x18001c5eb  lea     rcx, [rbx+20h]; this
0x18001c5ef  add     rsp, 20h
0x18001c5f3  pop     rbx
0x18001c5f4  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
