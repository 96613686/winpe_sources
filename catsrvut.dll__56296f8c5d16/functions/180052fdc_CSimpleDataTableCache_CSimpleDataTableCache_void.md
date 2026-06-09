# CSimpleDataTableCache::~CSimpleDataTableCache(void)

- ea: `0x180052fdc`
- end: `0x18005303c`
- name: `??1CSimpleDataTableCache@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CSimpleDataTableCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800530a0`

## callees

- `0x180052fdc`
- `0x1800533a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052ff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005300a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052ff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005300a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053024`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSimpleDataTableCache::~CSimpleDataTableCache(CSimpleDataTableCache *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  CSimpleDataTableCache::CleanupCaches(this);
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x180052fdc  push    rbx
0x180052fde  sub     rsp, 20h
0x180052fe2  mov     rbx, rcx
0x180052fe5  call    ?CleanupCaches@CSimpleDataTableCache@@IEAAXXZ; CSimpleDataTableCache::CleanupCaches(void)
0x180052fea  mov     rcx, [rbx+18h]; pv
0x180052fee  test    rcx, rcx
0x180052ff1  jz      short loc_180053001
0x180052ff3  call    cs:__imp_CoTaskMemFree
0x180052ff9  mov     qword ptr [rbx+18h], 0
0x180053001  mov     rcx, [rbx+20h]; pv
0x180053005  test    rcx, rcx
0x180053008  jz      short loc_180053018
0x18005300a  call    cs:__imp_CoTaskMemFree
0x180053010  mov     qword ptr [rbx+20h], 0
0x180053018  mov     rcx, [rbx+80h]; pv
0x18005301f  test    rcx, rcx
0x180053022  jz      short loc_180053036
0x180053024  call    cs:__imp_CoTaskMemFree
0x18005302a  nop
0x18005302b  mov     qword ptr [rbx+80h], 0
0x180053036  add     rsp, 20h
0x18005303a  pop     rbx
0x18005303b  retn
```
