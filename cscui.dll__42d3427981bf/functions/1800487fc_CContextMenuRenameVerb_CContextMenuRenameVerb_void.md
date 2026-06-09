# CContextMenuRenameVerb::~CContextMenuRenameVerb(void)

- ea: `0x1800487fc`
- end: `0x180048885`
- name: `??1CContextMenuRenameVerb@@MEAA@XZ`
- size: `137`
- prototype: `void __fastcall(CContextMenuRenameVerb *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048910`

## callees

- `0x180048614`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048872`

## pseudocode

```c
void __fastcall CContextMenuRenameVerb::~CContextMenuRenameVerb(CContextMenuRenameVerb *this)
{
  *(_QWORD *)this = &CContextMenuRenameVerb::`vftable'{for `IContextMenu3'};
  *((_QWORD *)this + 1) = &CContextMenuWithVerbs::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 2) = &CContextMenuRenameVerb::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 3) = &CContextMenuWithVerbs::`vftable'{for `IObjectWithSelection'};
  *((_QWORD *)this + 4) = &CContextMenuWithVerbs::`vftable'{for `IDefaultFolderMenuInitialize'};
  *((_QWORD *)this + 5) = &CContextMenuWithVerbs::`vftable'{for `IContextMenuForProgInvoke'};
  *((_QWORD *)this + 6) = &CContextMenuWithVerbs::`vftable'{for `IServiceProvider'};
  CoTaskMemFree(*((LPVOID *)this + 18));
  CoTaskMemFree(*((LPVOID *)this + 19));
  CoTaskMemFree(*((LPVOID *)this + 20));
  CContextMenuForwarder::~CContextMenuForwarder(this);
}

```

## disassembly

```asm
0x1800487fc  push    rbx
0x1800487fe  sub     rsp, 20h
0x180048802  lea     rax, ??_7CContextMenuRenameVerb@@6BIContextMenu3@@@; const CContextMenuRenameVerb::`vftable'{for `IContextMenu3'}
0x180048809  mov     rbx, rcx
0x18004880c  mov     [rcx], rax
0x18004880f  lea     rax, ??_7CContextMenuWithVerbs@@6BIObjectWithSite@@@; const CContextMenuWithVerbs::`vftable'{for `IObjectWithSite'}
0x180048816  mov     [rcx+8], rax
0x18004881a  lea     rax, ??_7CContextMenuRenameVerb@@6BIShellExtInit@@@; const CContextMenuRenameVerb::`vftable'{for `IShellExtInit'}
0x180048821  mov     [rcx+10h], rax
0x180048825  lea     rax, ??_7CContextMenuWithVerbs@@6BIObjectWithSelection@@@; const CContextMenuWithVerbs::`vftable'{for `IObjectWithSelection'}
0x18004882c  mov     [rcx+18h], rax
0x180048830  lea     rax, ??_7CContextMenuWithVerbs@@6BIDefaultFolderMenuInitialize@@@; const CContextMenuWithVerbs::`vftable'{for `IDefaultFolderMenuInitialize'}
0x180048837  mov     [rcx+20h], rax
0x18004883b  lea     rax, ??_7CContextMenuWithVerbs@@6BIContextMenuForProgInvoke@@@; const CContextMenuWithVerbs::`vftable'{for `IContextMenuForProgInvoke'}
0x180048842  mov     [rcx+28h], rax
0x180048846  lea     rax, ??_7CContextMenuWithVerbs@@6BIServiceProvider@@@; const CContextMenuWithVerbs::`vftable'{for `IServiceProvider'}
0x18004884d  mov     [rcx+30h], rax
0x180048851  mov     rcx, [rcx+90h]; pv
0x180048858  call    cs:__imp_CoTaskMemFree
0x18004885e  mov     rcx, [rbx+98h]; pv
0x180048865  call    cs:__imp_CoTaskMemFree
0x18004886b  mov     rcx, [rbx+0A0h]; pv
0x180048872  call    cs:__imp_CoTaskMemFree
0x180048878  mov     rcx, rbx; this
0x18004887b  add     rsp, 20h
0x18004887f  pop     rbx
0x180048880  jmp     ??1CContextMenuForwarder@@MEAA@XZ; CContextMenuForwarder::~CContextMenuForwarder(void)
```
