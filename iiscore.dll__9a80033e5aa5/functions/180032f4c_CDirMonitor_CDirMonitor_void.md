# CDirMonitor::CDirMonitor(void)

- ea: `0x180032f4c`
- end: `0x180032fd1`
- name: `??0CDirMonitor@@QEAA@XZ`
- size: `133`
- prototype: `CDirMonitor *__fastcall(CDirMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013690`

## import_xrefs

- `iisutil!IISInitializeCriticalSection` at `0x180032fba`
- `iisutil!IISInitializeCriticalSection` at `0x180032fba`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180032fa3`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180032fa3`
- `W3TP!ThreadPoolInitialize` at `0x180032fb0`
- `W3TP!ThreadPoolInitialize` at `0x180032fb0`

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
    (void (*)(const void *, int))guard_check_icall_nop,
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
0x180032f4c  mov     rax, rsp
0x180032f4f  push    rbx
0x180032f50  sub     rsp, 50h
0x180032f54  movsd   xmm0, cs:__real@4010000000000000
0x180032f5c  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCDirMonitor@@VCDirMonitorEntry@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<CDirMonitor,CDirMonitorEntry,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180032f63  mov     byte ptr [rax-10h], 0
0x180032f67  lea     r8, ?GetUrl@NOTIFICATION_MAP_PATH@@UEBAPEBGXZ; NOTIFICATION_MAP_PATH::GetUrl(void)
0x180032f6e  mov     dword ptr [rax-18h], 0
0x180032f75  lea     rdx, aDirmon; "DirMon"
0x180032f7c  mov     dword ptr [rax-20h], 1
0x180032f83  mov     rbx, rcx
0x180032f86  movsd   qword ptr [rax-28h], xmm0
0x180032f8b  lea     rax, _guard_check_icall_nop
0x180032f92  mov     [rsp+58h+var_30], rax
0x180032f97  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCDirMonitor@@VCDirMonitorEntry@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<CDirMonitor,CDirMonitorEntry,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180032f9e  mov     [rsp+58h+var_38], rax
0x180032fa3  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180032fa9  xor     r8d, r8d
0x180032fac  xor     edx, edx
0x180032fae  xor     ecx, ecx
0x180032fb0  call    cs:__imp_?ThreadPoolInitialize@@YAJKKK@Z; ThreadPoolInitialize(ulong,ulong,ulong)
0x180032fb6  lea     rcx, [rbx+48h]
0x180032fba  call    cs:__imp_IISInitializeCriticalSection
0x180032fc0  mov     rax, rbx
0x180032fc3  mov     qword ptr [rbx+70h], 1
0x180032fcb  add     rsp, 50h
0x180032fcf  pop     rbx
0x180032fd0  retn
```
