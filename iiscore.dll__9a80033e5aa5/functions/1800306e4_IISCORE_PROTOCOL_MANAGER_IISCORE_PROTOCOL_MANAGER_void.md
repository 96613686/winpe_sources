# IISCORE_PROTOCOL_MANAGER::IISCORE_PROTOCOL_MANAGER(void)

- ea: `0x1800306e4`
- end: `0x180030770`
- name: `??0IISCORE_PROTOCOL_MANAGER@@QEAA@XZ`
- size: `140`
- prototype: `IISCORE_PROTOCOL_MANAGER *__fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180030b30`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18003075a`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18003075a`

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
0x1800306e4  push    rbx
0x1800306e6  sub     rsp, 20h
0x1800306ea  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIProtocolManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'}
0x1800306f1  mov     dword ptr [rcx+3Ch], 1
0x1800306f8  mov     [rcx], rax
0x1800306fb  mov     rbx, rcx
0x1800306fe  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmCustomActions@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'}
0x180030705  mov     [rcx+8], rax
0x180030709  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmHealthAndIdleMonitor@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'}
0x180030710  mov     [rcx+10h], rax
0x180030714  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmListenerChannelManager@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'}
0x18003071b  mov     [rcx+18h], rax
0x18003071f  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmApplicationPreload@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'}
0x180030726  mov     [rcx+20h], rax
0x18003072a  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIPmIdleTimeOutAction@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'}
0x180030731  mov     [rcx+28h], rax
0x180030735  lea     rax, ??_7IISCORE_PROTOCOL_MANAGER@@6BIIisCoreRequestCounters@@@; const IISCORE_PROTOCOL_MANAGER::`vftable'{for `IIisCoreRequestCounters'}
0x18003073c  mov     [rcx+30h], rax
0x180030740  xor     eax, eax
0x180030742  mov     [rcx+40h], rax
0x180030746  mov     [rcx+48h], rax
0x18003074a  mov     [rcx+50h], rax
0x18003074e  mov     [rcx+58h], rax
0x180030752  mov     [rcx+60h], rax
0x180030756  add     rcx, 68h ; 'h'
0x18003075a  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180030760  mov     rax, rbx
0x180030763  mov     dword ptr [rbx+38h], 4D505349h
0x18003076a  add     rsp, 20h
0x18003076e  pop     rbx
0x18003076f  retn
```
