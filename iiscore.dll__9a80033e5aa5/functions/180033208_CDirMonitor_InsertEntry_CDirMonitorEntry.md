# CDirMonitor::InsertEntry(CDirMonitorEntry *)

- ea: `0x180033208`
- end: `0x1800332a1`
- name: `?InsertEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800332a8`

## callees

- `0x180033208`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18003327b`
- `iisutil!PuDbgPrint` at `0x18003327b`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180033231`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180033231`

## string_xrefs

- `0x180033264`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x18003324a`: `[CDirMonitor] Inserting directory (DME %08x) %ws\n`

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
0x180033208  mov     [rsp+arg_0], rbx
0x18003320d  mov     [rsp+arg_8], rsi
0x180033212  push    rdi
0x180033213  sub     rsp, 40h
0x180033217  cmp     dword ptr [rcx+74h], 0
0x18003321b  mov     rdi, rdx
0x18003321e  mov     rbx, rcx
0x180033221  jz      short loc_18003322A
0x180033223  mov     eax, 0FFFFFFA2h
0x180033228  jmp     short loc_180033291
0x18003322a  xor     r8d, r8d
0x18003322d  mov     [rdx+60h], rbx
0x180033231  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180033237  mov     esi, eax
0x180033239  test    eax, eax
0x18003323b  jnz     short loc_180033287
0x18003323d  test    byte ptr cs:g_dwDebugFlags, 3
0x180033244  jz      short loc_180033281
0x180033246  mov     rcx, [rdi+10h]
0x18003324a  lea     rax, aCdirmonitorIns_0; "[CDirMonitor] Inserting directory (DME "...
0x180033251  mov     [rsp+48h+var_18], rcx
0x180033256  lea     r9, aCdirmonitorIns; "CDirMonitor::InsertEntry"
0x18003325d  mov     rcx, cs:g_pDebug
0x180033264  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003326b  mov     [rsp+48h+var_20], rdi
0x180033270  mov     r8d, 372h
0x180033276  mov     [rsp+48h+var_28], rax
0x18003327b  call    cs:__imp_PuDbgPrint
0x180033281  lock inc dword ptr [rbx+70h]
0x180033285  jmp     short loc_18003328F
0x180033287  mov     qword ptr [rdi+60h], 0
0x18003328f  mov     eax, esi
0x180033291  mov     rbx, [rsp+48h+arg_0]
0x180033296  mov     rsi, [rsp+48h+arg_8]
0x18003329b  add     rsp, 40h
0x18003329f  pop     rdi
0x1800332a0  retn
```
