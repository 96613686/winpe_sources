# CDirMonitor::CDirMonitor(void)

- ea: `0x1800360ec`
- end: `0x180036184`
- name: `??0CDirMonitor@@QEAA@XZ`
- size: `152`
- prototype: `CDirMonitor *__fastcall(CDirMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800147d0`

## import_xrefs

- `iisutil!IISInitializeCriticalSection` at `0x180036166`
- `iisutil!IISInitializeCriticalSection` at `0x180036166`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180036143`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180036143`
- `W3TP!ThreadPoolInitialize` at `0x180036156`
- `W3TP!ThreadPoolInitialize` at `0x180036156`

## pseudocode

```c
CDirMonitor *__fastcall CDirMonitor::CDirMonitor(CDirMonitor *this)
{
  CDirMonitor *result; // rax

  CLKRHashTable::CLKRHashTable(
    this,
    "DirMon",
    (unsigned __int64 (*)(const void *))NOTIFICATION_MAP_PATH::GetUrl,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<CDirMonitor,CDirMonitorEntry,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CDirMonitor,CDirMonitorEntry,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))NOTIFICATION_SEND_RESPONSE::SetupStateMachine,
    4.0,
    1u,
    0,
    0);
  ThreadPoolInitialize(0, 0, 0);
  IISInitializeCriticalSection((char *)this + 72);
  result = this;
  *((_QWORD *)this + 14) = 1;
  return result;
}

```

## disassembly

```asm
0x1800360ec  mov     rax, rsp
0x1800360ef  push    rbx
0x1800360f0  sub     rsp, 50h
0x1800360f4  movsd   xmm0, cs:__real@4010000000000000
0x1800360fc  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCDirMonitor@@VCDirMonitorEntry@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<CDirMonitor,CDirMonitorEntry,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180036103  mov     byte ptr [rax-10h], 0
0x180036107  lea     r8, ?GetUrl@NOTIFICATION_MAP_PATH@@UEBAPEBGXZ; NOTIFICATION_MAP_PATH::GetUrl(void)
0x18003610e  mov     dword ptr [rax-18h], 0
0x180036115  lea     rdx, aDirmon; "DirMon"
0x18003611c  mov     dword ptr [rax-20h], 1
0x180036123  mov     rbx, rcx
0x180036126  movsd   qword ptr [rax-28h], xmm0
0x18003612b  lea     rax, ?SetupStateMachine@NOTIFICATION_SEND_RESPONSE@@UEAAXXZ; NOTIFICATION_SEND_RESPONSE::SetupStateMachine(void)
0x180036132  mov     [rsp+58h+var_30], rax
0x180036137  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCDirMonitor@@VCDirMonitorEntry@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<CDirMonitor,CDirMonitorEntry,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18003613e  mov     [rsp+58h+var_38], rax
0x180036143  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18003614a  nop     dword ptr [rax+rax+00h]
0x18003614f  xor     r8d, r8d
0x180036152  xor     edx, edx
0x180036154  xor     ecx, ecx
0x180036156  call    cs:__imp_?ThreadPoolInitialize@@YAJKKK@Z; ThreadPoolInitialize(ulong,ulong,ulong)
0x18003615d  nop     dword ptr [rax+rax+00h]
0x180036162  lea     rcx, [rbx+48h]
0x180036166  call    cs:__imp_IISInitializeCriticalSection
0x18003616d  nop     dword ptr [rax+rax+00h]
0x180036172  mov     rax, rbx
0x180036175  mov     qword ptr [rbx+70h], 1
0x18003617d  add     rsp, 50h
0x180036181  pop     rbx
0x180036182  retn
```
