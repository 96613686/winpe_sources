# ATL::CComAggObject<CBackupSession>::~CComAggObject<CBackupSession>(void)

- ea: `0x180002fbc`
- end: `0x180002fff`
- name: `??1?$CComAggObject@VCBackupSession@@@ATL@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003550`

## callees

- `0x18000326c`
- `0x18001868c`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CBackupSession>::~CComAggObject<CBackupSession>(__int64 a1)
{
  CBackupSession *v1; // rbx

  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = (CBackupSession *)(a1 + 24);
  *(_QWORD *)a1 = &ATL::CComAggObject<CBackupSession>::`vftable';
  CBackupSession::FinalRelease((CBackupSession *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CBackupSession::~CBackupSession(v1);
}

```

## disassembly

```asm
0x180002fbc  push    rbx
0x180002fbe  sub     rsp, 20h
0x180002fc2  lea     rax, ??_7?$CComAggObject@VCBackupSession@@@ATL@@6B@; const ATL::CComAggObject<CBackupSession>::`vftable'
0x180002fc9  mov     dword ptr [rcx+8], 0C0000001h
0x180002fd0  lea     rbx, [rcx+18h]
0x180002fd4  mov     [rcx], rax
0x180002fd7  mov     rcx, rbx; this
0x180002fda  call    ?FinalRelease@CBackupSession@@QEAAXXZ; CBackupSession::FinalRelease(void)
0x180002fdf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002fe6  mov     rax, [rcx]
0x180002fe9  mov     rax, [rax+10h]
0x180002fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff2  mov     rcx, rbx; this
0x180002ff5  add     rsp, 20h
0x180002ff9  pop     rbx
0x180002ffa  jmp     ??1CBackupSession@@QEAA@XZ; CBackupSession::~CBackupSession(void)
```
