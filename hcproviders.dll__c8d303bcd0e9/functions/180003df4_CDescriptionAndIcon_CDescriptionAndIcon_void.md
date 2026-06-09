# CDescriptionAndIcon::~CDescriptionAndIcon(void)

- ea: `0x180003df4`
- end: `0x180003e35`
- name: `??1CDescriptionAndIcon@@AEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CDescriptionAndIcon *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003db0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e1b`

## pseudocode

```c
void __fastcall CDescriptionAndIcon::~CDescriptionAndIcon(LPVOID *this)
{
  *this = &CDescriptionAndIcon::`vftable';
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[3]);
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x180003df4  push    rbx
0x180003df6  sub     rsp, 20h
0x180003dfa  lea     rax, ??_7CDescriptionAndIcon@@6B@; const CDescriptionAndIcon::`vftable'
0x180003e01  mov     rbx, rcx
0x180003e04  mov     [rcx], rax
0x180003e07  mov     rcx, [rcx+10h]; pv
0x180003e0b  call    cs:__imp_CoTaskMemFree
0x180003e12  nop     dword ptr [rax+rax+00h]
0x180003e17  mov     rcx, [rbx+18h]; pv
0x180003e1b  call    cs:__imp_CoTaskMemFree
0x180003e22  nop     dword ptr [rax+rax+00h]
0x180003e27  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180003e2e  add     rsp, 20h
0x180003e32  pop     rbx
0x180003e33  retn
```
