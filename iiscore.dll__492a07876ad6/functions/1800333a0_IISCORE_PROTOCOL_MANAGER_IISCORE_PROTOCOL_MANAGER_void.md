# IISCORE_PROTOCOL_MANAGER::IISCORE_PROTOCOL_MANAGER(void)

- ea: `0x1800333a0`
- end: `0x180033433`
- name: `??0IISCORE_PROTOCOL_MANAGER@@QEAA@XZ`
- size: `147`
- prototype: `IISCORE_PROTOCOL_MANAGER *__fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180033830`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180033416`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180033416`

## pseudocode

```c
IISCORE_PROTOCOL_MANAGER *__fastcall IISCORE_PROTOCOL_MANAGER::IISCORE_PROTOCOL_MANAGER(IISCORE_PROTOCOL_MANAGER *this)
{
  IISCORE_PROTOCOL_MANAGER *result; // rax

  *((_DWORD *)this + 15) = 1;
  *(_QWORD *)this = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'};
  *((_QWORD *)this + 1) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'};
  *((_QWORD *)this + 2) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'};
  *((_QWORD *)this + 3) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'};
  *((_QWORD *)this + 4) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'};
  *((_QWORD *)this + 5) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'};
  *((_QWORD *)this + 6) = &IISCORE_PROTOCOL_MANAGER::`vftable'{for `IIisCoreRequestCounters'};
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  CReaderWriterLock3::CReaderWriterLock3((IISCORE_PROTOCOL_MANAGER *)((char *)this + 104));
  result = this;
  *((_DWORD *)this + 14) = 1297109833;
  return result;
}

```

## disassembly

```asm
0x1800333a0  push    rbx
0x1800333a2  sub     rsp, 20h
0x1800333a6  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIProtocolManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'}
0x1800333ad  mov     dword ptr [rcx+3Ch], 1
0x1800333b4  mov     [rcx], rax
0x1800333b7  mov     rbx, rcx
0x1800333ba  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmCustomActions@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'}
0x1800333c1  mov     [rcx+8], rax
0x1800333c5  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmHealthAndIdleMonitor@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'}
0x1800333cc  mov     [rcx+10h], rax
0x1800333d0  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmListenerChannelManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'}
0x1800333d7  mov     [rcx+18h], rax
0x1800333db  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmApplicationPreload@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'}
0x1800333e2  mov     [rcx+20h], rax
0x1800333e6  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmIdleTimeOutAction@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'}
0x1800333ed  mov     [rcx+28h], rax
0x1800333f1  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIIisCoreRequestCounters@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IIisCoreRequestCounters'}
0x1800333f8  mov     [rcx+30h], rax
0x1800333fc  xor     eax, eax
0x1800333fe  mov     [rcx+40h], rax
0x180033402  mov     [rcx+48h], rax
0x180033406  mov     [rcx+50h], rax
0x18003340a  mov     [rcx+58h], rax
0x18003340e  mov     [rcx+60h], rax
0x180033412  add     rcx, 68h ; 'h'
0x180033416  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18003341d  nop     dword ptr [rax+rax+00h]
0x180033422  mov     rax, rbx
0x180033425  mov     dword ptr [rbx+38h], 4D505349h
0x18003342c  add     rsp, 20h
0x180033430  pop     rbx
0x180033431  retn
```
