# CDirMonitor::RemoveEntry(CDirMonitorEntry *)

- ea: `0x180033480`
- end: `0x1800334ff`
- name: `?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180033008`
- `0x1800332a8`

## callees

- `0x180033480`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800334e3`
- `iisutil!PuDbgPrint` at `0x1800334e3`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180033495`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180033495`

## string_xrefs

- `0x1800334cc`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x1800334b2`: `[CDirMonitor] Removed DME(%08x), directory %ws\n`
- `0x1800334c0`: `CDirMonitor::RemoveEntry`

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
0x180033480  mov     [rsp+arg_0], rbx
0x180033485  mov     [rsp+arg_8], rsi
0x18003348a  push    rdi
0x18003348b  sub     rsp, 40h
0x18003348f  mov     rdi, rdx
0x180033492  mov     rbx, rcx
0x180033495  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18003349b  test    byte ptr cs:g_dwDebugFlags, 3
0x1800334a2  mov     esi, eax
0x1800334a4  mov     qword ptr [rdi+60h], 0
0x1800334ac  jz      short loc_1800334E9
0x1800334ae  mov     r8, [rdi+10h]
0x1800334b2  lea     rax, aCdirmonitorRem_0; "[CDirMonitor] Removed DME(%08x), direct"...
0x1800334b9  mov     rcx, cs:g_pDebug
0x1800334c0  lea     r9, aCdirmonitorRem; "CDirMonitor::RemoveEntry"
0x1800334c7  mov     [rsp+48h+var_18], r8
0x1800334cc  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800334d3  mov     [rsp+48h+var_20], rdi
0x1800334d8  mov     r8d, 39Bh
0x1800334de  mov     [rsp+48h+var_28], rax
0x1800334e3  call    cs:__imp_PuDbgPrint
0x1800334e9  lock dec dword ptr [rbx+70h]
0x1800334ed  mov     eax, esi
0x1800334ef  mov     rbx, [rsp+48h+arg_0]
0x1800334f4  mov     rsi, [rsp+48h+arg_8]
0x1800334f9  add     rsp, 40h
0x1800334fd  pop     rdi
0x1800334fe  retn
```
