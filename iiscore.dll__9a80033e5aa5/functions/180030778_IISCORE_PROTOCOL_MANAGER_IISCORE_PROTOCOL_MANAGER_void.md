# IISCORE_PROTOCOL_MANAGER::~IISCORE_PROTOCOL_MANAGER(void)

- ea: `0x180030778`
- end: `0x180030842`
- name: `??1IISCORE_PROTOCOL_MANAGER@@AEAA@XZ`
- size: `202`
- prototype: `void __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031190`

## callees

- `0x180030778`
- `0x180035010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18003083b`

## pseudocode

```c
void __fastcall IISCORE_PROTOCOL_MANAGER::~IISCORE_PROTOCOL_MANAGER(IISCORE_PROTOCOL_MANAGER *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *((_DWORD *)this + 14) = 1483764585;
  *(_QWORD *)this = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'};
  *((_QWORD *)this + 1) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'};
  *((_QWORD *)this + 2) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'};
  *((_QWORD *)this + 3) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'};
  *((_QWORD *)this + 4) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'};
  *((_QWORD *)this + 5) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'};
  *((_QWORD *)this + 6) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IIisCoreRequestCounters'};
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 10) = 0;
  }
  v3 = *((_QWORD *)this + 11);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 24LL))(v3, 1);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 8LL))(*((_QWORD *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  if ( *((_QWORD *)this + 8) )
    *((_QWORD *)this + 8) = 0;
  CReaderWriterLock3::~CReaderWriterLock3((IISCORE_PROTOCOL_MANAGER *)((char *)this + 104));
}

```

## disassembly

```asm
0x180030778  push    rbx
0x18003077a  sub     rsp, 20h
0x18003077e  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIProtocolManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'}
0x180030785  mov     dword ptr [rcx+38h], 58707369h
0x18003078c  mov     [rcx], rax
0x18003078f  mov     rbx, rcx
0x180030792  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmCustomActions@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'}
0x180030799  mov     [rcx+8], rax
0x18003079d  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmHealthAndIdleMonitor@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'}
0x1800307a4  mov     [rcx+10h], rax
0x1800307a8  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmListenerChannelManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'}
0x1800307af  mov     [rcx+18h], rax
0x1800307b3  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmApplicationPreload@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'}
0x1800307ba  mov     [rcx+20h], rax
0x1800307be  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmIdleTimeOutAction@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'}
0x1800307c5  mov     [rcx+28h], rax
0x1800307c9  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIIisCoreRequestCounters@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IIisCoreRequestCounters'}
0x1800307d0  mov     [rcx+30h], rax
0x1800307d4  mov     rcx, [rcx+50h]
0x1800307d8  test    rcx, rcx
0x1800307db  jz      short loc_1800307F1
0x1800307dd  mov     rax, [rcx]
0x1800307e0  mov     rax, [rax+8]
0x1800307e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307e9  mov     qword ptr [rbx+50h], 0
0x1800307f1  mov     rcx, [rbx+58h]
0x1800307f5  test    rcx, rcx
0x1800307f8  jz      short loc_180030823
0x1800307fa  mov     rax, [rcx]
0x1800307fd  mov     edx, 1
0x180030802  mov     rax, [rax+18h]
0x180030806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003080b  mov     rcx, [rbx+58h]
0x18003080f  mov     rax, [rcx]
0x180030812  mov     rax, [rax+8]
0x180030816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003081b  mov     qword ptr [rbx+58h], 0
0x180030823  cmp     qword ptr [rbx+40h], 0
0x180030828  jz      short loc_180030832
0x18003082a  mov     qword ptr [rbx+40h], 0
0x180030832  lea     rcx, [rbx+68h]
0x180030836  add     rsp, 20h
0x18003083a  pop     rbx
0x18003083b  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
