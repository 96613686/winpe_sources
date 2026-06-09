# CMachineSettings::~CMachineSettings(void)

- ea: `0x180035214`
- end: `0x1800352ba`
- name: `??1CMachineSettings@@QEAA@XZ`
- size: `166`
- prototype: `void __fastcall(CMachineSettings *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010d28`
- `0x180010e54`

## callees

- `0x1800065f0`
- `0x180035214`
- `0x1800352c0`
- `0x1800381ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800352a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800352a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMachineSettings::~CMachineSettings(CMachineSettings *this)
{
  void *v2; // rcx
  void *v3; // rdi
  void *v4; // rdi

  *(_QWORD *)this = &CMachineSettings::`vftable'{for `ISimpleTableWrite'};
  *((_QWORD *)this + 1) = &CMachineSettings::`vftable'{for `ISimpleDataTableDispenser'};
  *((_QWORD *)this + 2) = &CMachineSettings::`vftable'{for `ISimpleTableMarshall'};
  *((_QWORD *)this + 3) = &CMachineSettings::`vftable'{for `ISimpleLogicTableDispenser'};
  *((_QWORD *)this + 4) = &CProtocolsTable::`vftable'{for `ISimpleTableControl'};
  v2 = (void *)*((_QWORD *)this + 33);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>((__int64)v3 + 16);
    CoTaskMemFree(v3);
  }
  v4 = (void *)*((_QWORD *)this + 36);
  if ( v4 )
  {
    CTmpMemoryCache::~CTmpMemoryCache(*((CTmpMemoryCache **)this + 36));
    CoTaskMemFree(v4);
  }
  CCustomDataTable::~CCustomDataTable(this);
}

```

## disassembly

```asm
0x180035214  mov     [rsp+arg_0], rbx
0x180035219  push    rdi
0x18003521a  sub     rsp, 20h
0x18003521e  mov     rbx, rcx
0x180035221  lea     rax, ??_7CMachineSettings@@6BISimpleTableWrite@@@; const CMachineSettings::`vftable'{for `ISimpleTableWrite'}
0x180035228  mov     [rcx], rax
0x18003522b  lea     rax, ??_7CMachineSettings@@6BISimpleDataTableDispenser@@@; const CMachineSettings::`vftable'{for `ISimpleDataTableDispenser'}
0x180035232  mov     [rcx+8], rax
0x180035236  lea     rax, ??_7CMachineSettings@@6BISimpleTableMarshall@@@; const CMachineSettings::`vftable'{for `ISimpleTableMarshall'}
0x18003523d  mov     [rcx+10h], rax
0x180035241  lea     rax, ??_7CMachineSettings@@6BISimpleLogicTableDispenser@@@; const CMachineSettings::`vftable'{for `ISimpleLogicTableDispenser'}
0x180035248  mov     [rcx+18h], rax
0x18003524c  lea     rax, ??_7CProtocolsTable@@6BISimpleTableControl@@@; const CProtocolsTable::`vftable'{for `ISimpleTableControl'}
0x180035253  mov     [rcx+20h], rax
0x180035257  mov     rcx, [rcx+108h]; pv
0x18003525e  test    rcx, rcx
0x180035261  jz      short loc_180035269
0x180035263  call    cs:__imp_CoTaskMemFree
0x180035269  mov     rdi, [rbx+118h]
0x180035270  test    rdi, rdi
0x180035273  jz      short loc_180035289
0x180035275  lea     rcx, [rdi+10h]
0x180035279  call    ??1?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@QEAA@XZ; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>(void)
0x18003527e  nop
0x18003527f  mov     rcx, rdi; pv
0x180035282  call    cs:__imp_CoTaskMemFree
0x180035288  nop
0x180035289  mov     rdi, [rbx+120h]
0x180035290  test    rdi, rdi
0x180035293  jz      short loc_1800352A8
0x180035295  mov     rcx, rdi; this
0x180035298  call    ??1CTmpMemoryCache@@QEAA@XZ; CTmpMemoryCache::~CTmpMemoryCache(void)
0x18003529d  nop
0x18003529e  mov     rcx, rdi; pv
0x1800352a1  call    cs:__imp_CoTaskMemFree
0x1800352a7  nop
0x1800352a8  mov     rcx, rbx; this
0x1800352ab  mov     rbx, [rsp+28h+arg_0]
0x1800352b0  add     rsp, 20h
0x1800352b4  pop     rdi
0x1800352b5  jmp     ??1CCustomDataTable@@QEAA@XZ; CCustomDataTable::~CCustomDataTable(void)
```
