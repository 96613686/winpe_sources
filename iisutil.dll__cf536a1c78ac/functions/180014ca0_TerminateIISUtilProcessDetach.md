# TerminateIISUtilProcessDetach

- ea: `0x180014ca0`
- end: `0x180014d88`
- name: `TerminateIISUtilProcessDetach`
- size: `232`
- prototype: `void()`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d770`
- `0x18001f740`

## callees

- `0x180008000`
- `0x18000fd74`
- `0x180014ca0`
- `0x1800209f0`
- `0x1800227a0`
- `0x18002d4f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014d3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014d59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014d6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014d3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014d59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014d6c`

## string_xrefs

- `0x180014cd8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

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
  if ( dword_18004F98C != 2 )
  {
    switch ( dword_18004F98C )
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
  dword_18004F98C = 0;
}

```

## disassembly

```asm
0x180014ca0  sub     rsp, 38h
0x180014ca4  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180014caa  test    al, 3
0x180014cac  setnz   cl
0x180014caf  test    al, 4
0x180014cb1  setnz   al
0x180014cb4  test    al, cl
0x180014cb6  jz      short loc_180014CE4
0x180014cb8  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180014cbf  lea     rax, aTerminateiisut_2; "TerminateIISUtilProcessDetach\n"
0x180014cc6  lea     r9, aTerminateiisut_3; "TerminateIISUtilProcessDetach"
0x180014ccd  mov     [rsp+38h+var_18], rax; char *
0x180014cd2  mov     r8d, 0E0h; unsigned int
0x180014cd8  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180014cdf  call    PuDbgPrint
0x180014ce4  mov     ecx, cs:dword_18004F98C
0x180014cea  sub     ecx, 2
0x180014ced  jz      loc_180014D78
0x180014cf3  sub     ecx, 1
0x180014cf6  jz      short loc_180014D65
0x180014cf8  sub     ecx, 1
0x180014cfb  jz      short loc_180014D52
0x180014cfd  sub     ecx, 1
0x180014d00  jz      short loc_180014D2C
0x180014d02  sub     ecx, 1
0x180014d05  jz      short loc_180014D25
0x180014d07  sub     ecx, 1
0x180014d0a  jz      short loc_180014D20
0x180014d0c  sub     ecx, 1
0x180014d0f  jz      short loc_180014D1B
0x180014d11  cmp     ecx, 1
0x180014d14  jnz     short loc_180014D78
0x180014d16  call    ?Terminate@EVENT_LOG@@SAXXZ; EVENT_LOG::Terminate(void)
0x180014d1b  call    ?TerminateStatic@BIG_REF_TRACE@@SAJXZ; BIG_REF_TRACE::TerminateStatic(void)
0x180014d20  call    LKRHashTableUninit
0x180014d25  xor     ecx, ecx; int
0x180014d27  call    ?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z; ALLOC_CACHE_HANDLER::Cleanup(int)
0x180014d2c  cmp     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x180014d33  jz      short loc_180014D52
0x180014d35  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014d3c  call    cs:__imp_DeleteCriticalSection
0x180014d43  nop     dword ptr [rax+rax+00h]
0x180014d48  mov     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x180014d52  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014d59  call    cs:__imp_DeleteCriticalSection
0x180014d60  nop     dword ptr [rax+rax+00h]
0x180014d65  lea     rcx, CriticalSection; lpCriticalSection
0x180014d6c  call    cs:__imp_DeleteCriticalSection
0x180014d73  nop     dword ptr [rax+rax+00h]
0x180014d78  mov     cs:dword_18004F98C, 0
0x180014d82  add     rsp, 38h
0x180014d86  retn
```
