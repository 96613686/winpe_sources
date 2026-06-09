# ATL::CComObjectCached<DataStoreComServer>::Release(void)

- ea: `0x1800058a0`
- end: `0x180005921`
- name: `?Release@?$CComObjectCached@VDataStoreComServer@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(DataStoreComServer *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800058a0`
- `0x1800068dc`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x1800058f4`
- `msvcrt!free` at `0x1800058f4`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<DataStoreComServer>::Release(DataStoreComServer *this)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)this + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, i - 1, i);
        i = *((_DWORD *)this + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( this )
    {
      *((_DWORD *)this + 2) = -1073741823;
      *(_QWORD *)this = &ATL::CComObjectCached<DataStoreComServer>::`vftable';
      DataStoreComServer::~DataStoreComServer(this);
      free(this);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x1800058a0  mov     [rsp+arg_0], rbx
0x1800058a5  push    rdi
0x1800058a6  sub     rsp, 20h
0x1800058aa  mov     rbx, rcx
0x1800058ad  mov     r8d, 7FFFFFFFh
0x1800058b3  mov     ecx, [rcx+8]
0x1800058b6  jmp     short loc_1800058C7
0x1800058b8  lea     edx, [rcx-1]
0x1800058bb  mov     eax, ecx
0x1800058bd  lock cmpxchg [rbx+8], edx
0x1800058c2  jz      short loc_1800058CC
0x1800058c4  mov     ecx, [rbx+8]
0x1800058c7  cmp     ecx, r8d
0x1800058ca  jnz     short loc_1800058B8
0x1800058cc  lea     edi, [rcx-1]
0x1800058cf  test    edi, edi
0x1800058d1  jnz     short loc_1800058FC
0x1800058d3  test    rbx, rbx
0x1800058d6  jz      short loc_180005914
0x1800058d8  lea     rax, ??_7?$CComObjectCached@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObjectCached<DataStoreComServer>::`vftable'
0x1800058df  mov     dword ptr [rbx+8], 0C0000001h
0x1800058e6  mov     rcx, rbx; this
0x1800058e9  mov     [rbx], rax
0x1800058ec  call    ??1DataStoreComServer@@QEAA@XZ; DataStoreComServer::~DataStoreComServer(void)
0x1800058f1  mov     rcx, rbx; Block
0x1800058f4  call    cs:__imp_free
0x1800058fa  jmp     short loc_180005914
0x1800058fc  cmp     edi, 1
0x1800058ff  jnz     short loc_180005914
0x180005901  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005908  mov     rdx, [rcx]
0x18000590b  mov     rax, [rdx+10h]
0x18000590f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005914  mov     rbx, [rsp+28h+arg_0]
0x180005919  mov     eax, edi
0x18000591b  add     rsp, 20h
0x18000591f  pop     rdi
0x180005920  retn
```
