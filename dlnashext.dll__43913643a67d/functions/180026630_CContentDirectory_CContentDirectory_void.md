# CContentDirectory::~CContentDirectory(void)

- ea: `0x180026630`
- end: `0x18002665d`
- name: `??1CContentDirectory@@UEAA@XZ`
- size: `45`
- prototype: `void __fastcall(CContentDirectory *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026664`
- `0x180026750`
- `0x180034560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026656`

## pseudocode

```c
void __fastcall CContentDirectory::~CContentDirectory(LPVOID *this)
{
  *this = &CContentDirectory::`vftable';
  CoTaskMemFree(this[1]);
  CoTaskMemFree(this[2]);
}

```

## disassembly

```asm
0x180026630  push    rbx
0x180026632  sub     rsp, 20h
0x180026636  lea     rax, ??_7CContentDirectory@@6B@; const CContentDirectory::`vftable'
0x18002663d  mov     rbx, rcx
0x180026640  mov     [rcx], rax
0x180026643  mov     rcx, [rcx+8]; pv
0x180026647  call    cs:__imp_CoTaskMemFree
0x18002664d  mov     rcx, [rbx+10h]
0x180026651  add     rsp, 20h
0x180026655  pop     rbx
0x180026656  jmp     cs:__imp_CoTaskMemFree
```
