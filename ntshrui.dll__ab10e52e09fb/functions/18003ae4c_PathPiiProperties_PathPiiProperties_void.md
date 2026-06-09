# PathPiiProperties::~PathPiiProperties(void)

- ea: `0x18003ae4c`
- end: `0x18003ae87`
- name: `??1PathPiiProperties@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(PathPiiProperties *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003af44`

## callees

- `0x18003ae4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae7b`

## pseudocode

```c
void __fastcall PathPiiProperties::~PathPiiProperties(PathPiiProperties *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *(_QWORD *)this )
    CoTaskMemFree(*(LPVOID *)this);
}

```

## disassembly

```asm
0x18003ae4c  push    rbx
0x18003ae4e  sub     rsp, 20h
0x18003ae52  mov     rbx, rcx
0x18003ae55  mov     rcx, [rcx+10h]; pv
0x18003ae59  test    rcx, rcx
0x18003ae5c  jz      short loc_18003AE64
0x18003ae5e  call    cs:__imp_CoTaskMemFree
0x18003ae64  mov     rcx, [rbx+8]; pv
0x18003ae68  test    rcx, rcx
0x18003ae6b  jz      short loc_18003AE73
0x18003ae6d  call    cs:__imp_CoTaskMemFree
0x18003ae73  mov     rcx, [rbx]; pv
0x18003ae76  test    rcx, rcx
0x18003ae79  jz      short loc_18003AE81
0x18003ae7b  call    cs:__imp_CoTaskMemFree
0x18003ae81  add     rsp, 20h
0x18003ae85  pop     rbx
0x18003ae86  retn
```
