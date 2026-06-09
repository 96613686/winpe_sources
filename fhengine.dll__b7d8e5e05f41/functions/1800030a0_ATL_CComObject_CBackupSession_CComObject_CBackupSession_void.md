# ATL::CComObject<CBackupSession>::~CComObject<CBackupSession>(void)

- ea: `0x1800030a0`
- end: `0x1800030ed`
- name: `??1?$CComObject@VCBackupSession@@@ATL@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(CBackupSession *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003610`

## callees

- `0x18000326c`
- `0x18001868c`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CComObject<CBackupSession>::~CComObject<CBackupSession>(CBackupSession *this)
{
  *((_DWORD *)this + 72) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CBackupSession>::`vftable'{for `IFhEngineBackup'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CBackupSession>::`vftable'{for `CSessionBaseRW'};
  CBackupSession::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CBackupSession::~CBackupSession(this);
}

```

## disassembly

```asm
0x1800030a0  push    rbx
0x1800030a2  sub     rsp, 20h
0x1800030a6  lea     rax, ??_7?$CComObject@VCBackupSession@@@ATL@@6BIFhEngineBackup@@@; const ATL::CComObject<CBackupSession>::`vftable'{for `IFhEngineBackup'}
0x1800030ad  mov     dword ptr [rcx+120h], 0C0000001h
0x1800030b7  mov     [rcx], rax
0x1800030ba  mov     rbx, rcx
0x1800030bd  lea     rax, ??_7?$CComObject@VCBackupSession@@@ATL@@6BCSessionBaseRW@@@; const ATL::CComObject<CBackupSession>::`vftable'{for `CSessionBaseRW'}
0x1800030c4  mov     [rcx+8], rax
0x1800030c8  call    ?FinalRelease@CBackupSession@@QEAAXXZ; CBackupSession::FinalRelease(void)
0x1800030cd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800030d4  mov     rax, [rcx]
0x1800030d7  mov     rax, [rax+10h]
0x1800030db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e0  mov     rcx, rbx; this
0x1800030e3  add     rsp, 20h
0x1800030e7  pop     rbx
0x1800030e8  jmp     ??1CBackupSession@@QEAA@XZ; CBackupSession::~CBackupSession(void)
```
