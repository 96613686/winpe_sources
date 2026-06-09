# CStatus::~CStatus(void)

- ea: `0x180004854`
- end: `0x180004886`
- name: `??1CStatus@@EEAA@XZ`
- size: `50`
- prototype: `void __fastcall(CStatus *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000487f`

## pseudocode

```c
void __fastcall CStatus::~CStatus(CStatus *this)
{
  *(_QWORD *)this = &CStatus::`vftable'{for `IHCStatus'};
  *((_QWORD *)this + 1) = &CStatus::`vftable'{for `CCommandImpl'};
  _InterlockedDecrement(&g_cLocks);
  *((_QWORD *)this + 1) = &CCommandImpl::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 2));
}

```

## disassembly

```asm
0x180004854  lea     rax, ??_7CStatus@@6BIHCStatus@@@; const CStatus::`vftable'{for `IHCStatus'}
0x18000485b  mov     [rcx], rax
0x18000485e  lea     rax, ??_7CStatus@@6BCCommandImpl@@@; const CStatus::`vftable'{for `CCommandImpl'}
0x180004865  mov     [rcx+8], rax
0x180004869  lea     rax, ??_7CCommandImpl@@6B@; const CCommandImpl::`vftable'
0x180004870  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180004877  mov     [rcx+8], rax
0x18000487b  mov     rcx, [rcx+10h]
0x18000487f  jmp     cs:__imp_CoTaskMemFree
```
