# ATL::CComObject<CNetworkDiagnostics>::`vector deleting destructor'(uint)

- ea: `0x1800116d0`
- end: `0x180011727`
- name: `??_E?$CComObject@VCNetworkDiagnostics@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CNetworkDiagnostics *__fastcall(CNetworkDiagnostics *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800112c0`
- `0x1800116d0`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011713`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011713`

## pseudocode

```c
CNetworkDiagnostics *__fastcall ATL::CComObject<CNetworkDiagnostics>::`vector deleting destructor'(
        CNetworkDiagnostics *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CNetworkDiagnostics>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CNetworkDiagnostics::~CNetworkDiagnostics(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800116d0  mov     [rsp+arg_0], rbx
0x1800116d5  push    rdi
0x1800116d6  sub     rsp, 20h
0x1800116da  mov     dword ptr [rcx+8], 0C0000001h
0x1800116e1  lea     rax, ??_7?$CComObject@VCNetworkDiagnostics@@@ATL@@6B@; const ATL::CComObject<CNetworkDiagnostics>::`vftable'
0x1800116e8  mov     [rcx], rax
0x1800116eb  mov     rdi, rcx
0x1800116ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800116f5  mov     ebx, edx
0x1800116f7  mov     rax, [rcx]
0x1800116fa  mov     rax, [rax+10h]
0x1800116fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011703  mov     rcx, rdi; this
0x180011706  call    ??1CNetworkDiagnostics@@QEAA@XZ; CNetworkDiagnostics::~CNetworkDiagnostics(void)
0x18001170b  test    bl, 1
0x18001170e  jz      short loc_180011719
0x180011710  mov     rcx, rdi
0x180011713  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011719  mov     rbx, [rsp+28h+arg_0]
0x18001171e  mov     rax, rdi
0x180011721  add     rsp, 20h
0x180011725  pop     rdi
0x180011726  retn
```
