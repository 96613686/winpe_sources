# CAction::~CAction(void)

- ea: `0x180009bec`
- end: `0x180009c1e`
- name: `??1CAction@@EEAA@XZ`
- size: `50`
- prototype: `void __fastcall(CAction *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009c40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c17`

## pseudocode

```c
void __fastcall CAction::~CAction(CAction *this)
{
  *(_QWORD *)this = &CAction::`vftable'{for `IHCAction'};
  *((_QWORD *)this + 1) = &CAction::`vftable'{for `CCommandImpl'};
  _InterlockedDecrement(&g_cLocks);
  *((_QWORD *)this + 1) = &CCommandImpl::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 2));
}

```

## disassembly

```asm
0x180009bec  lea     rax, ??_7CAction@@6BIHCAction@@@; const CAction::`vftable'{for `IHCAction'}
0x180009bf3  mov     [rcx], rax
0x180009bf6  lea     rax, ??_7CAction@@6BCCommandImpl@@@; const CAction::`vftable'{for `CCommandImpl'}
0x180009bfd  mov     [rcx+8], rax
0x180009c01  lea     rax, ??_7CCommandImpl@@6B@; const CCommandImpl::`vftable'
0x180009c08  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180009c0f  mov     [rcx+8], rax
0x180009c13  mov     rcx, [rcx+10h]
0x180009c17  jmp     cs:__imp_CoTaskMemFree
```
