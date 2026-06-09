# ATL::CComObject<DataStoreComServer>::`vector deleting destructor'(uint)

- ea: `0x1800023d0`
- end: `0x180002427`
- name: `??_E?$CComObject@VDataStoreComServer@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `__int64 __fastcall(DataStoreComServer *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800023d0`
- `0x1800068dc`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x180002413`
- `msvcrt!free` at `0x180002413`

## pseudocode

```c
DataStoreComServer *__fastcall ATL::CComObject<DataStoreComServer>::`vector deleting destructor'(
        DataStoreComServer *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<DataStoreComServer>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DataStoreComServer::~DataStoreComServer(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  push    rdi
0x1800023d6  sub     rsp, 20h
0x1800023da  mov     dword ptr [rcx+8], 0C0000001h
0x1800023e1  lea     rax, ??_7?$CComObject@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObject<DataStoreComServer>::`vftable'
0x1800023e8  mov     [rcx], rax
0x1800023eb  mov     rdi, rcx
0x1800023ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800023f5  mov     ebx, edx
0x1800023f7  mov     rax, [rcx]
0x1800023fa  mov     rax, [rax+10h]
0x1800023fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002403  mov     rcx, rdi; this
0x180002406  call    ??1DataStoreComServer@@QEAA@XZ; DataStoreComServer::~DataStoreComServer(void)
0x18000240b  test    bl, 1
0x18000240e  jz      short loc_180002419
0x180002410  mov     rcx, rdi; Block
0x180002413  call    cs:__imp_free
0x180002419  mov     rbx, [rsp+28h+arg_0]
0x18000241e  mov     rax, rdi
0x180002421  add     rsp, 20h
0x180002425  pop     rdi
0x180002426  retn
```
