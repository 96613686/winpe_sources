# CDirMonitor::InsertEntry(CDirMonitorEntry *)

- ea: `0x1800363f0`
- end: `0x180036496`
- name: `?InsertEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003649c`

## callees

- `0x1800363f0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180036469`
- `iisutil!PuDbgPrint` at `0x180036469`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180036419`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180036419`

## string_xrefs

- `0x180036452`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180036438`: `[CDirMonitor] Inserting directory (DME %08x) %ws\n`

## pseudocode

```c
__int64 __fastcall CDirMonitor::InsertEntry(__int64 a1, __int64 a2)
{
  unsigned int inserted; // esi

  if ( *(_DWORD *)(a1 + 116) )
    return 4294967202LL;
  *(_QWORD *)(a2 + 96) = a1;
  inserted = CLKRHashTable::InsertRecord(a1, a2, 0);
  if ( inserted )
  {
    *(_QWORD *)(a2 + 96) = 0;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
        882,
        "CDirMonitor::InsertEntry",
        "[CDirMonitor] Inserting directory (DME %08x) %ws\n",
        a2,
        *(_QWORD *)(a2 + 16));
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 112));
  }
  return inserted;
}

```

## disassembly

```asm
0x1800363f0  mov     [rsp+arg_0], rbx
0x1800363f5  mov     [rsp+arg_8], rsi
0x1800363fa  push    rdi
0x1800363fb  sub     rsp, 40h
0x1800363ff  cmp     dword ptr [rcx+74h], 0
0x180036403  mov     rdi, rdx
0x180036406  mov     rbx, rcx
0x180036409  jz      short loc_180036412
0x18003640b  mov     eax, 0FFFFFFA2h
0x180036410  jmp     short loc_180036485
0x180036412  xor     r8d, r8d
0x180036415  mov     [rdx+60h], rbx
0x180036419  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180036420  nop     dword ptr [rax+rax+00h]
0x180036425  mov     esi, eax
0x180036427  test    eax, eax
0x180036429  jnz     short loc_18003647B
0x18003642b  test    byte ptr cs:g_dwDebugFlags, 3
0x180036432  jz      short loc_180036475
0x180036434  mov     rcx, [rdi+10h]
0x180036438  lea     rax, aCdirmonitorIns_0; "[CDirMonitor] Inserting directory (DME "...
0x18003643f  mov     [rsp+48h+var_18], rcx
0x180036444  lea     r9, aCdirmonitorIns; "CDirMonitor::InsertEntry"
0x18003644b  mov     rcx, cs:g_pDebug
0x180036452  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180036459  mov     [rsp+48h+var_20], rdi
0x18003645e  mov     r8d, 372h
0x180036464  mov     [rsp+48h+var_28], rax
0x180036469  call    cs:__imp_PuDbgPrint
0x180036470  nop     dword ptr [rax+rax+00h]
0x180036475  lock inc dword ptr [rbx+70h]
0x180036479  jmp     short loc_180036483
0x18003647b  mov     qword ptr [rdi+60h], 0
0x180036483  mov     eax, esi
0x180036485  mov     rbx, [rsp+48h+arg_0]
0x18003648a  mov     rsi, [rsp+48h+arg_8]
0x18003648f  add     rsp, 40h
0x180036493  pop     rdi
0x180036494  retn
```
