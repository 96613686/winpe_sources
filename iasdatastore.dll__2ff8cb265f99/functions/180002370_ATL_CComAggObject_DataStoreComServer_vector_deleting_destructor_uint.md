# ATL::CComAggObject<DataStoreComServer>::`vector deleting destructor'(uint)

- ea: `0x180002370`
- end: `0x1800023c8`
- name: `??_E?$CComAggObject@VDataStoreComServer@@@ATL@@UEAAPEAXI@Z`
- size: `88`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002370`
- `0x1800068dc`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x1800023b4`
- `msvcrt!free` at `0x1800023b4`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<DataStoreComServer>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<DataStoreComServer>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DataStoreComServer::~DataStoreComServer((DataStoreComServer *)(Block + 6));
  if ( (a2 & 1) != 0 )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x180002370  mov     [rsp+arg_0], rbx
0x180002375  push    rdi
0x180002376  sub     rsp, 20h
0x18000237a  mov     dword ptr [rcx+8], 0C0000001h
0x180002381  lea     rax, ??_7?$CComAggObject@VDataStoreComServer@@@ATL@@6B@; const ATL::CComAggObject<DataStoreComServer>::`vftable'
0x180002388  mov     [rcx], rax
0x18000238b  mov     rdi, rcx
0x18000238e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002395  mov     ebx, edx
0x180002397  mov     rax, [rcx]
0x18000239a  mov     rax, [rax+10h]
0x18000239e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a3  lea     rcx, [rdi+18h]; this
0x1800023a7  call    ??1DataStoreComServer@@QEAA@XZ; DataStoreComServer::~DataStoreComServer(void)
0x1800023ac  test    bl, 1
0x1800023af  jz      short loc_1800023BA
0x1800023b1  mov     rcx, rdi; Block
0x1800023b4  call    cs:__imp_free
0x1800023ba  mov     rbx, [rsp+28h+arg_0]
0x1800023bf  mov     rax, rdi
0x1800023c2  add     rsp, 20h
0x1800023c6  pop     rdi
0x1800023c7  retn
```
