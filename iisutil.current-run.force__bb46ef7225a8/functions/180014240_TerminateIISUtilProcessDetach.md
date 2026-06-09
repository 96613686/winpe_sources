# TerminateIISUtilProcessDetach

- ea: `0x180014240`
- end: `0x180014311`
- name: `TerminateIISUtilProcessDetach`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c770`
- `0x18001e5a0`

## callees

- `0x180007300`
- `0x18000eb00`
- `0x180014240`
- `0x18001f710`
- `0x1800211e0`
- `0x18002b570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142fc`

## string_xrefs

- `0x180014278`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
void TerminateIISUtilProcessDetach()
{
  char v0; // [rsp+28h] [rbp-10h]

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0xE0u,
      "TerminateIISUtilProcessDetach",
      "TerminateIISUtilProcessDetach\n",
      v0);
  if ( dword_18004D98C != 2 )
  {
    switch ( dword_18004D98C )
    {
      case 3:
LABEL_18:
        DeleteCriticalSection(&CriticalSection);
        break;
      case 4:
LABEL_17:
        DeleteCriticalSection(&g_SchedulerCritSec);
        goto LABEL_18;
      case 5:
LABEL_15:
        if ( g_fInitCsTimerWrap )
        {
          DeleteCriticalSection(&g_csTimerWrap);
          g_fInitCsTimerWrap = 0;
        }
        goto LABEL_17;
      case 6:
LABEL_14:
        ALLOC_CACHE_HANDLER::Cleanup(0);
        goto LABEL_15;
      case 7:
LABEL_13:
        LKRHashTableUninit();
        goto LABEL_14;
      case 8:
LABEL_12:
        BIG_REF_TRACE::TerminateStatic();
        goto LABEL_13;
      case 9:
        EVENT_LOG::Terminate();
        goto LABEL_12;
    }
  }
  dword_18004D98C = 0;
}

```

## disassembly

```asm
0x180014240  sub     rsp, 38h
0x180014244  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001424a  test    al, 3
0x18001424c  setnz   cl
0x18001424f  test    al, 4
0x180014251  setnz   al
0x180014254  test    al, cl
0x180014256  jz      short loc_180014284
0x180014258  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001425f  lea     rax, aTerminateiisut_2; "TerminateIISUtilProcessDetach\n"
0x180014266  lea     r9, aTerminateiisut_3; "TerminateIISUtilProcessDetach"
0x18001426d  mov     [rsp+38h+var_18], rax; char *
0x180014272  mov     r8d, 0E0h; unsigned int
0x180014278  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001427f  call    PuDbgPrint
0x180014284  mov     ecx, cs:dword_18004D98C
0x18001428a  sub     ecx, 2
0x18001428d  jz      short loc_180014302
0x18001428f  sub     ecx, 1
0x180014292  jz      short loc_1800142F5
0x180014294  sub     ecx, 1
0x180014297  jz      short loc_1800142E8
0x180014299  sub     ecx, 1
0x18001429c  jz      short loc_1800142C8
0x18001429e  sub     ecx, 1
0x1800142a1  jz      short loc_1800142C1
0x1800142a3  sub     ecx, 1
0x1800142a6  jz      short loc_1800142BC
0x1800142a8  sub     ecx, 1
0x1800142ab  jz      short loc_1800142B7
0x1800142ad  cmp     ecx, 1
0x1800142b0  jnz     short loc_180014302
0x1800142b2  call    ?Terminate@EVENT_LOG@@SAXXZ; EVENT_LOG::Terminate(void)
0x1800142b7  call    ?TerminateStatic@BIG_REF_TRACE@@SAJXZ; BIG_REF_TRACE::TerminateStatic(void)
0x1800142bc  call    LKRHashTableUninit
0x1800142c1  xor     ecx, ecx; int
0x1800142c3  call    ?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z; ALLOC_CACHE_HANDLER::Cleanup(int)
0x1800142c8  cmp     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x1800142cf  jz      short loc_1800142E8
0x1800142d1  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800142d8  call    cs:__imp_DeleteCriticalSection
0x1800142de  mov     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x1800142e8  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800142ef  call    cs:__imp_DeleteCriticalSection
0x1800142f5  lea     rcx, CriticalSection; lpCriticalSection
0x1800142fc  call    cs:__imp_DeleteCriticalSection
0x180014302  mov     cs:dword_18004D98C, 0
0x18001430c  add     rsp, 38h
0x180014310  retn
```
