# IISCORE_PROTOCOL_MANAGER::~IISCORE_PROTOCOL_MANAGER(void)

- ea: `0x18003343c`
- end: `0x18003350b`
- name: `??1IISCORE_PROTOCOL_MANAGER@@AEAA@XZ`
- size: `207`
- prototype: `void __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033f50`

## callees

- `0x18003343c`
- `0x180038010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800334ff`

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
0x18003343c  push    rbx
0x18003343e  sub     rsp, 20h
0x180033442  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIProtocolManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'}
0x180033449  mov     dword ptr [rcx+38h], 58707369h
0x180033450  mov     [rcx], rax
0x180033453  mov     rbx, rcx
0x180033456  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmCustomActions@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'}
0x18003345d  mov     [rcx+8], rax
0x180033461  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmHealthAndIdleMonitor@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'}
0x180033468  mov     [rcx+10h], rax
0x18003346c  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmListenerChannelManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'}
0x180033473  mov     [rcx+18h], rax
0x180033477  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmApplicationPreload@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'}
0x18003347e  mov     [rcx+20h], rax
0x180033482  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmIdleTimeOutAction@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'}
0x180033489  mov     [rcx+28h], rax
0x18003348d  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIIisCoreRequestCounters@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IIisCoreRequestCounters'}
0x180033494  mov     [rcx+30h], rax
0x180033498  mov     rcx, [rcx+50h]
0x18003349c  test    rcx, rcx
0x18003349f  jz      short loc_1800334B5
0x1800334a1  mov     rax, [rcx]
0x1800334a4  mov     rax, [rax+8]
0x1800334a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334ad  mov     qword ptr [rbx+50h], 0
0x1800334b5  mov     rcx, [rbx+58h]
0x1800334b9  test    rcx, rcx
0x1800334bc  jz      short loc_1800334E7
0x1800334be  mov     rax, [rcx]
0x1800334c1  mov     edx, 1
0x1800334c6  mov     rax, [rax+18h]
0x1800334ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334cf  mov     rcx, [rbx+58h]
0x1800334d3  mov     rax, [rcx]
0x1800334d6  mov     rax, [rax+8]
0x1800334da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334df  mov     qword ptr [rbx+58h], 0
0x1800334e7  cmp     qword ptr [rbx+40h], 0
0x1800334ec  jz      short loc_1800334F6
0x1800334ee  mov     qword ptr [rbx+40h], 0
0x1800334f6  lea     rcx, [rbx+68h]
0x1800334fa  add     rsp, 20h
0x1800334fe  pop     rbx
0x1800334ff  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
