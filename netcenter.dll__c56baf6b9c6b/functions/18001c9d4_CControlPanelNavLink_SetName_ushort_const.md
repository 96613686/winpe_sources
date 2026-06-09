# CControlPanelNavLink::SetName(ushort const *)

- ea: `0x18001c9d4`
- end: `0x18001ca05`
- name: `?SetName@CControlPanelNavLink@@QEAAJPEBG@Z`
- size: `49`
- prototype: `__int64 __fastcall(CControlPanelNavLink *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008a88`
- `0x180013404`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c9e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c9e8`
- `SHLWAPI!SHStrDupW` at `0x18001c9fe`

## pseudocode

```c
HRESULT __fastcall CControlPanelNavLink::SetName(LPVOID *this, const unsigned __int16 *a2)
{
  LPWSTR *v2; // rbx

  v2 = (LPWSTR *)(this + 1);
  CoTaskMemFree(this[1]);
  return SHStrDupW(a2, v2);
}

```

## disassembly

```asm
0x18001c9d4  mov     [rsp+arg_0], rbx
0x18001c9d9  push    rdi
0x18001c9da  sub     rsp, 20h
0x18001c9de  lea     rbx, [rcx+8]
0x18001c9e2  mov     rdi, rdx
0x18001c9e5  mov     rcx, [rbx]; pv
0x18001c9e8  call    cs:__imp_CoTaskMemFree
0x18001c9ee  mov     rdx, rbx
0x18001c9f1  mov     rcx, rdi
0x18001c9f4  mov     rbx, [rsp+28h+arg_0]
0x18001c9f9  add     rsp, 20h
0x18001c9fd  pop     rdi
0x18001c9fe  jmp     cs:__imp_SHStrDupW
```
