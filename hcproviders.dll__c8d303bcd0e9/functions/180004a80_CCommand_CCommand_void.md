# CCommand::~CCommand(void)

- ea: `0x180004a80`
- end: `0x180004ab1`
- name: `??1CCommand@@EEAA@XZ`
- size: `49`
- prototype: `void __fastcall(CCommand *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004aaa`

## pseudocode

```c
void __fastcall CCommand::~CCommand(CCommand *this)
{
  *(_QWORD *)this = &CCommand::`vftable'{for `CCommandImpl'};
  *((_QWORD *)this + 4) = &CCommand::`vftable'{for `IHCCommand'};
  _InterlockedDecrement(&g_cLocks);
  *(_QWORD *)this = &CCommandImpl::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 1));
}

```

## disassembly

```asm
0x180004a80  lea     rax, ??_7CCommand@@6BCCommandImpl@@@; const CCommand::`vftable'{for `CCommandImpl'}
0x180004a87  mov     [rcx], rax
0x180004a8a  lea     rax, ??_7CCommand@@6BIHCCommand@@@; const CCommand::`vftable'{for `IHCCommand'}
0x180004a91  mov     [rcx+20h], rax
0x180004a95  lea     rax, ??_7CCommandImpl@@6B@; const CCommandImpl::`vftable'
0x180004a9c  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180004aa3  mov     [rcx], rax
0x180004aa6  mov     rcx, [rcx+8]
0x180004aaa  jmp     cs:__imp_CoTaskMemFree
```
