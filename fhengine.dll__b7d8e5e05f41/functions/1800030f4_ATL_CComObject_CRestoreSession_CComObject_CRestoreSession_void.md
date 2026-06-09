# ATL::CComObject<CRestoreSession>::~CComObject<CRestoreSession>(void)

- ea: `0x1800030f4`
- end: `0x180003133`
- name: `??1?$CComObject@VCRestoreSession@@@ATL@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(CRestoreSession *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x1800033d0`
- `0x180023fcc`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CComObject<CRestoreSession>::~CComObject<CRestoreSession>(CRestoreSession *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CRestoreSession>::`vftable';
  CRestoreSession::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CRestoreSession::~CRestoreSession(this);
}

```

## disassembly

```asm
0x1800030f4  push    rbx
0x1800030f6  sub     rsp, 20h
0x1800030fa  lea     rax, ??_7?$CComObject@VCRestoreSession@@@ATL@@6B@; const ATL::CComObject<CRestoreSession>::`vftable'
0x180003101  mov     dword ptr [rcx+8], 0C0000001h
0x180003108  mov     [rcx], rax
0x18000310b  mov     rbx, rcx
0x18000310e  call    ?FinalRelease@CRestoreSession@@QEAAXXZ; CRestoreSession::FinalRelease(void)
0x180003113  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000311a  mov     rax, [rcx]
0x18000311d  mov     rax, [rax+10h]
0x180003121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003126  mov     rcx, rbx; this
0x180003129  add     rsp, 20h
0x18000312d  pop     rbx
0x18000312e  jmp     ??1CRestoreSession@@QEAA@XZ; CRestoreSession::~CRestoreSession(void)
```
