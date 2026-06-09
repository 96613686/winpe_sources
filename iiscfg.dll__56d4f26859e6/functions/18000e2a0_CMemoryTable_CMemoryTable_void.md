# CMemoryTable::~CMemoryTable(void)

- ea: `0x18000e2a0`
- end: `0x18000e33b`
- name: `??1CMemoryTable@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMemoryTable *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001fe8`

## callees

- `0x18000e2a0`
- `0x18000e840`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e2e2`
- `ole32!CoTaskMemFree` at `0x18000e2f9`
- `ole32!CoTaskMemFree` at `0x18000e310`
- `ole32!CoTaskMemFree` at `0x18000e327`
- `ole32!CoTaskMemFree` at `0x18000e2e2`
- `ole32!CoTaskMemFree` at `0x18000e2f9`
- `ole32!CoTaskMemFree` at `0x18000e310`
- `ole32!CoTaskMemFree` at `0x18000e327`

## pseudocode

```c
void __fastcall CMemoryTable::~CMemoryTable(CMemoryTable *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CMemoryTable::`vftable'{for `ISimpleTableInterceptor'};
  *((_QWORD *)this + 1) = &CMemoryTable::`vftable'{for `ISimpleTableWrite2'};
  *((_QWORD *)this + 2) = &CMemoryTable::`vftable'{for `ISimpleTableController'};
  *((_QWORD *)this + 3) = &CMemoryTable::`vftable'{for `ISimpleTableMarshall'};
  CMemoryTable::CleanupCaches(this);
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 7) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 8) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x18000e2a0  push    rbx
0x18000e2a2  sub     rsp, 20h
0x18000e2a6  lea     rax, ??_7CMemoryTable@@6BISimpleTableInterceptor@@@; const CMemoryTable::`vftable'{for `ISimpleTableInterceptor'}
0x18000e2ad  mov     rbx, rcx
0x18000e2b0  mov     [rcx], rax
0x18000e2b3  lea     rax, ??_7CMemoryTable@@6BISimpleTableWrite2@@@; const CMemoryTable::`vftable'{for `ISimpleTableWrite2'}
0x18000e2ba  mov     [rcx+8], rax
0x18000e2be  lea     rax, ??_7CMemoryTable@@6BISimpleTableController@@@; const CMemoryTable::`vftable'{for `ISimpleTableController'}
0x18000e2c5  mov     [rcx+10h], rax
0x18000e2c9  lea     rax, ??_7CMemoryTable@@6BISimpleTableMarshall@@@; const CMemoryTable::`vftable'{for `ISimpleTableMarshall'}
0x18000e2d0  mov     [rcx+18h], rax
0x18000e2d4  call    ?CleanupCaches@CMemoryTable@@AEAAXXZ; CMemoryTable::CleanupCaches(void)
0x18000e2d9  mov     rcx, [rbx+38h]; pv
0x18000e2dd  test    rcx, rcx
0x18000e2e0  jz      short loc_18000E2F0
0x18000e2e2  call    cs:__imp_CoTaskMemFree
0x18000e2e8  mov     qword ptr [rbx+38h], 0
0x18000e2f0  mov     rcx, [rbx+40h]; pv
0x18000e2f4  test    rcx, rcx
0x18000e2f7  jz      short loc_18000E307
0x18000e2f9  call    cs:__imp_CoTaskMemFree
0x18000e2ff  mov     qword ptr [rbx+40h], 0
0x18000e307  mov     rcx, [rbx+48h]; pv
0x18000e30b  test    rcx, rcx
0x18000e30e  jz      short loc_18000E31E
0x18000e310  call    cs:__imp_CoTaskMemFree
0x18000e316  mov     qword ptr [rbx+48h], 0
0x18000e31e  mov     rcx, [rbx+50h]; pv
0x18000e322  test    rcx, rcx
0x18000e325  jz      short loc_18000E335
0x18000e327  call    cs:__imp_CoTaskMemFree
0x18000e32d  mov     qword ptr [rbx+50h], 0
0x18000e335  add     rsp, 20h
0x18000e339  pop     rbx
0x18000e33a  retn
```
