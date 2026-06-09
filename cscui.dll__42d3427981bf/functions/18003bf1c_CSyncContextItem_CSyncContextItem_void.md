# CSyncContextItem::~CSyncContextItem(void)

- ea: `0x18003bf1c`
- end: `0x18003bf65`
- name: `??1CSyncContextItem@@AEAA@XZ`
- size: `73`
- prototype: `void __fastcall(CSyncContextItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003bf94`

## callees

- `0x18003bf1c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf3d`

## pseudocode

```c
void __fastcall CSyncContextItem::~CSyncContextItem(LPVOID *this)
{
  LPVOID v2; // rcx

  *this = &CSyncContextItem::`vftable';
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[3]);
  v2 = this[5];
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x18003bf1c  push    rbx
0x18003bf1e  sub     rsp, 20h
0x18003bf22  lea     rax, ??_7CSyncContextItem@@6B@; const CSyncContextItem::`vftable'
0x18003bf29  mov     rbx, rcx
0x18003bf2c  mov     [rcx], rax
0x18003bf2f  mov     rcx, [rcx+10h]; pv
0x18003bf33  call    cs:__imp_CoTaskMemFree
0x18003bf39  mov     rcx, [rbx+18h]; pv
0x18003bf3d  call    cs:__imp_CoTaskMemFree
0x18003bf43  mov     rcx, [rbx+28h]
0x18003bf47  test    rcx, rcx
0x18003bf4a  jz      short loc_18003BF58
0x18003bf4c  mov     rax, [rcx]
0x18003bf4f  mov     rax, [rax+10h]
0x18003bf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf58  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x18003bf5f  add     rsp, 20h
0x18003bf63  pop     rbx
0x18003bf64  retn
```
