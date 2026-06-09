# CSDTIMetaData::~CSDTIMetaData(void)

- ea: `0x180040390`
- end: `0x180040464`
- name: `??1CSDTIMetaData@@QEAA@XZ`
- size: `212`
- prototype: `void __fastcall(CSDTIMetaData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040088`

## callees

- `0x180040390`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004041f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004044f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004041f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004044f`

## pseudocode

```c
void __fastcall CSDTIMetaData::~CSDTIMetaData(CSDTIMetaData *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CSDTIMetaData::`vftable'{for `IClassFactory'};
  *((_QWORD *)this + 1) = &CSDTIMetaData::`vftable'{for `ISimpleDataTableDispenser'};
  *((_QWORD *)this + 2) = &CSDTIMetaData::`vftable'{for `ISimpleTableWrite'};
  *((_QWORD *)this + 3) = &CSDTIMetaData::`vftable'{for `ISimpleTableControl'};
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 7) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 8) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 11) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 12);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 12) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 13);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 13) = 0;
  }
}

```

## disassembly

```asm
0x180040390  push    rbx
0x180040392  sub     rsp, 20h
0x180040396  mov     rbx, rcx
0x180040399  lea     rax, ??_7CSDTIMetaData@@6BIClassFactory@@@; const CSDTIMetaData::`vftable'{for `IClassFactory'}
0x1800403a0  mov     [rcx], rax
0x1800403a3  lea     rax, ??_7CSDTIMetaData@@6BISimpleDataTableDispenser@@@; const CSDTIMetaData::`vftable'{for `ISimpleDataTableDispenser'}
0x1800403aa  mov     [rcx+8], rax
0x1800403ae  lea     rax, ??_7CSDTIMetaData@@6BISimpleTableWrite@@@; const CSDTIMetaData::`vftable'{for `ISimpleTableWrite'}
0x1800403b5  mov     [rcx+10h], rax
0x1800403b9  lea     rax, ??_7CSDTIMetaData@@6BISimpleTableControl@@@; const CSDTIMetaData::`vftable'{for `ISimpleTableControl'}
0x1800403c0  mov     [rcx+18h], rax
0x1800403c4  mov     rcx, [rcx+30h]
0x1800403c8  test    rcx, rcx
0x1800403cb  jz      short loc_1800403E1
0x1800403cd  mov     rax, [rcx]
0x1800403d0  mov     rax, [rax+10h]
0x1800403d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403d9  mov     qword ptr [rbx+30h], 0
0x1800403e1  mov     rcx, [rbx+38h]
0x1800403e5  test    rcx, rcx
0x1800403e8  jz      short loc_1800403FE
0x1800403ea  mov     rax, [rcx]
0x1800403ed  mov     rax, [rax+10h]
0x1800403f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403f6  mov     qword ptr [rbx+38h], 0
0x1800403fe  mov     rcx, [rbx+40h]; pv
0x180040402  test    rcx, rcx
0x180040405  jz      short loc_180040416
0x180040407  call    cs:__imp_CoTaskMemFree
0x18004040d  nop
0x18004040e  mov     qword ptr [rbx+40h], 0
0x180040416  mov     rcx, [rbx+58h]; pv
0x18004041a  test    rcx, rcx
0x18004041d  jz      short loc_18004042E
0x18004041f  call    cs:__imp_CoTaskMemFree
0x180040425  nop
0x180040426  mov     qword ptr [rbx+58h], 0
0x18004042e  mov     rcx, [rbx+60h]; pv
0x180040432  test    rcx, rcx
0x180040435  jz      short loc_180040446
0x180040437  call    cs:__imp_CoTaskMemFree
0x18004043d  nop
0x18004043e  mov     qword ptr [rbx+60h], 0
0x180040446  mov     rcx, [rbx+68h]; pv
0x18004044a  test    rcx, rcx
0x18004044d  jz      short loc_18004045E
0x18004044f  call    cs:__imp_CoTaskMemFree
0x180040455  nop
0x180040456  mov     qword ptr [rbx+68h], 0
0x18004045e  add     rsp, 20h
0x180040462  pop     rbx
0x180040463  retn
```
