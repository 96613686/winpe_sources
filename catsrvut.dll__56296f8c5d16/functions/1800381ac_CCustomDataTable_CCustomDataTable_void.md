# CCustomDataTable::~CCustomDataTable(void)

- ea: `0x1800381ac`
- end: `0x180038215`
- name: `??1CCustomDataTable@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(CCustomDataTable *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010d00`
- `0x180010d50`
- `0x180010e04`
- `0x180010ea4`
- `0x180035214`

## callees

- `0x1800381ac`
- `0x180053044`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038201`

## pseudocode

```c
void __fastcall CCustomDataTable::~CCustomDataTable(CCustomDataTable *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = *((_QWORD *)this + 25);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 26);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void *)*((_QWORD *)this + 24);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
    CoTaskMemFree(v5);
  CSimpleDataTableCursor::~CSimpleDataTableCursor((CCustomDataTable *)((char *)this + 40));
}

```

## disassembly

```asm
0x1800381ac  push    rbx
0x1800381ae  sub     rsp, 20h
0x1800381b2  mov     rbx, rcx
0x1800381b5  mov     rcx, [rcx+0C8h]
0x1800381bc  test    rcx, rcx
0x1800381bf  jz      short loc_1800381CD
0x1800381c1  mov     rax, [rcx]
0x1800381c4  mov     rax, [rax+10h]
0x1800381c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381cd  mov     rcx, [rbx+0D0h]
0x1800381d4  test    rcx, rcx
0x1800381d7  jz      short loc_1800381E5
0x1800381d9  mov     rax, [rcx]
0x1800381dc  mov     rax, [rax+10h]
0x1800381e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381e5  mov     rcx, [rbx+0C0h]; pv
0x1800381ec  test    rcx, rcx
0x1800381ef  jz      short loc_1800381F8
0x1800381f1  call    cs:__imp_CoTaskMemFree
0x1800381f7  nop
0x1800381f8  mov     rcx, [rbx+70h]; pv
0x1800381fc  test    rcx, rcx
0x1800381ff  jz      short loc_180038207
0x180038201  call    cs:__imp_CoTaskMemFree
0x180038207  lea     rcx, [rbx+28h]; this
0x18003820b  add     rsp, 20h
0x18003820f  pop     rbx
0x180038210  jmp     ??1CSimpleDataTableCursor@@QEAA@XZ; CSimpleDataTableCursor::~CSimpleDataTableCursor(void)
```
