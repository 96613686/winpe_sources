# CDirMonitor::RemoveEntry(CDirMonitorEntry *)

- ea: `0x1800366b4`
- end: `0x180036740`
- name: `?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800361cc`
- `0x18003649c`

## callees

- `0x1800366b4`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18003671d`
- `iisutil!PuDbgPrint` at `0x18003671d`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800366c9`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800366c9`

## string_xrefs

- `0x180036706`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x1800366ec`: `[CDirMonitor] Removed DME(%08x), directory %ws\n`
- `0x1800366fa`: `CDirMonitor::RemoveEntry`

## pseudocode

```c
__int64 __fastcall CDirMonitor::RemoveEntry(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  bool v5; // zf
  unsigned int v6; // esi

  v4 = CLKRHashTable::DeleteRecord(a1, a2);
  v5 = (g_dwDebugFlags & 3) == 0;
  v6 = v4;
  *(_QWORD *)(a2 + 96) = 0;
  if ( !v5 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      923,
      "CDirMonitor::RemoveEntry",
      "[CDirMonitor] Removed DME(%08x), directory %ws\n",
      a2,
      *(_QWORD *)(a2 + 16));
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 112));
  return v6;
}

```

## disassembly

```asm
0x1800366b4  mov     [rsp+arg_0], rbx
0x1800366b9  mov     [rsp+arg_8], rsi
0x1800366be  push    rdi
0x1800366bf  sub     rsp, 40h
0x1800366c3  mov     rdi, rdx
0x1800366c6  mov     rbx, rcx
0x1800366c9  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x1800366d0  nop     dword ptr [rax+rax+00h]
0x1800366d5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800366dc  mov     esi, eax
0x1800366de  mov     qword ptr [rdi+60h], 0
0x1800366e6  jz      short loc_180036729
0x1800366e8  mov     r8, [rdi+10h]
0x1800366ec  lea     rax, aCdirmonitorRem_0; "[CDirMonitor] Removed DME(%08x), direct"...
0x1800366f3  mov     rcx, cs:g_pDebug
0x1800366fa  lea     r9, aCdirmonitorRem; "CDirMonitor::RemoveEntry"
0x180036701  mov     [rsp+48h+var_18], r8
0x180036706  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003670d  mov     [rsp+48h+var_20], rdi
0x180036712  mov     r8d, 39Bh
0x180036718  mov     [rsp+48h+var_28], rax
0x18003671d  call    cs:__imp_PuDbgPrint
0x180036724  nop     dword ptr [rax+rax+00h]
0x180036729  lock dec dword ptr [rbx+70h]
0x18003672d  mov     eax, esi
0x18003672f  mov     rbx, [rsp+48h+arg_0]
0x180036734  mov     rsi, [rsp+48h+arg_8]
0x180036739  add     rsp, 40h
0x18003673d  pop     rdi
0x18003673e  retn
```
