# WEB_ADMIN_SERVICE::FinishStateTransition(ulong,ulong)

- ea: `0x180004f34`
- end: `0x1800050a6`
- name: `?FinishStateTransition@WEB_ADMIN_SERVICE@@AEAAJKK@Z`
- size: `370`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004420`
- `0x180005aac`
- `0x180006490`

## callees

- `0x180004290`
- `0x180004f34`
- `0x180006e6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005058`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fdc`
- `iisutil!PuDbgPrint` at `0x180004fa1`
- `iisutil!PuDbgPrint` at `0x180004fa1`
- `iisutil!PuDbgPrintError` at `0x18000504f`
- `iisutil!PuDbgPrintError` at `0x18000509e`
- `iisutil!PuDbgPrintError` at `0x18000504f`
- `iisutil!PuDbgPrintError` at `0x18000509e`

## string_xrefs

- `0x180004f96`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005048`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005097`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180004f76`: `Not changing service state to: %lu, because current state is: %lu, was expected to be: %lu\n`
- `0x180004f8b`: `WEB_ADMIN_SERVICE::FinishStateTransition`
- `0x180005037`: `WEB_ADMIN_SERVICE::FinishStateTransition`
- `0x180005086`: `WEB_ADMIN_SERVICE::FinishStateTransition`
- `0x18000502b`: `Could not update service status\n`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::FinishStateTransition(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        int a3)
{
  LONG RecursionCount; // r9d
  int updated; // edi
  struct _RTL_CRITICAL_SECTION *v7; // rsi

  RecursionCount = this[28].RecursionCount;
  if ( RecursionCount != a3 )
  {
    updated = 0;
    if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        1942,
        "WEB_ADMIN_SERVICE::FinishStateTransition",
        "Not changing service state to: %lu, because current state is: %lu, was expected to be: %lu\n",
        a2,
        RecursionCount,
        a3);
    return (unsigned int)updated;
  }
  v7 = this + 29;
  if ( !this[29].DebugInfo )
    goto LABEL_7;
  updated = WEB_ADMIN_SERVICE::CancelTimer((WEB_ADMIN_SERVICE *)this, (struct _TP_TIMER **)&this[29]);
  if ( updated >= 0 )
  {
    v7->DebugInfo = 0;
LABEL_7:
    EnterCriticalSection(this + 27);
    LODWORD(this[28].OwningThread) = 7;
    updated = WEB_ADMIN_SERVICE::UpdateServiceStatus((WEB_ADMIN_SERVICE *)this, a2, 0, 0, 0, 0, 0);
    if ( updated < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        1990,
        "WEB_ADMIN_SERVICE::FinishStateTransition",
        updated,
        "Could not update service status\n");
    LeaveCriticalSection(this + 27);
    return (unsigned int)updated;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      1957,
      "WEB_ADMIN_SERVICE::FinishStateTransition",
      updated,
      "Could not cancel timer\n");
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180004f34  mov     r11, rsp
0x180004f37  push    rbp
0x180004f38  push    rsi
0x180004f39  push    rdi
0x180004f3a  push    r14
0x180004f3c  sub     rsp, 48h
0x180004f40  mov     r9d, [rcx+46Ch]
0x180004f47  mov     r14d, edx
0x180004f4a  mov     rbp, rcx
0x180004f4d  cmp     r9d, r8d
0x180004f50  jz      short loc_180004FAC
0x180004f52  mov     eax, cs:g_dwDebugFlags
0x180004f58  xor     edi, edi
0x180004f5a  test    eax, 30000h
0x180004f5f  setnz   cl
0x180004f62  test    al, 3
0x180004f64  setnz   al
0x180004f67  test    al, cl
0x180004f69  jz      loc_18000505E
0x180004f6f  mov     rcx, cs:g_pDebug
0x180004f76  lea     rax, aNotChangingSer; "Not changing service state to: %lu, bec"...
0x180004f7d  mov     [r11-30h], r8d
0x180004f81  mov     r8d, 796h
0x180004f87  mov     [r11-38h], r9d
0x180004f8b  lea     r9, aWebAdminServic_5; "WEB_ADMIN_SERVICE::FinishStateTransitio"...
0x180004f92  mov     [r11-40h], edx
0x180004f96  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180004f9d  mov     [r11-48h], rax
0x180004fa1  call    cs:__imp_PuDbgPrint
0x180004fa7  jmp     loc_18000505E
0x180004fac  lea     rsi, [rcx+488h]
0x180004fb3  cmp     qword ptr [rsi], 0
0x180004fb7  jz      short loc_180004FD2
0x180004fb9  mov     rdx, rsi; struct _TP_TIMER **
0x180004fbc  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180004fc1  mov     edi, eax
0x180004fc3  test    eax, eax
0x180004fc5  js      loc_18000506A
0x180004fcb  mov     qword ptr [rsi], 0
0x180004fd2  lea     rsi, [rbp+438h]
0x180004fd9  mov     rcx, rsi; lpCriticalSection
0x180004fdc  call    cs:__imp_EnterCriticalSection
0x180004fe2  mov     [rsp+68h+var_38], 0; int
0x180004fea  xor     r9d, r9d; unsigned int
0x180004fed  mov     [rsp+68h+var_40], 0; unsigned int
0x180004ff5  xor     r8d, r8d; unsigned int
0x180004ff8  mov     edx, r14d; unsigned int
0x180004ffb  mov     [rsp+68h+var_48], 0; unsigned int
0x180005003  mov     rcx, rbp; this
0x180005006  mov     dword ptr [rbp+470h], 7
0x180005010  call    ?UpdateServiceStatus@WEB_ADMIN_SERVICE@@AEAAJKKKKKH@Z; WEB_ADMIN_SERVICE::UpdateServiceStatus(ulong,ulong,ulong,ulong,ulong,int)
0x180005015  mov     edi, eax
0x180005017  test    eax, eax
0x180005019  jns     short loc_180005055
0x18000501b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005022  jz      short loc_180005055
0x180005024  mov     rcx, cs:g_pDebug
0x18000502b  lea     rax, aCouldNotUpdate; "Could not update service status\n"
0x180005032  mov     qword ptr [rsp+68h+var_40], rax
0x180005037  lea     r9, aWebAdminServic_5; "WEB_ADMIN_SERVICE::FinishStateTransitio"...
0x18000503e  mov     r8d, 7C6h
0x180005044  mov     [rsp+68h+var_48], edi
0x180005048  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000504f  call    cs:__imp_PuDbgPrintError
0x180005055  mov     rcx, rsi; lpCriticalSection
0x180005058  call    cs:__imp_LeaveCriticalSection
0x18000505e  mov     eax, edi
0x180005060  add     rsp, 48h
0x180005064  pop     r14
0x180005066  pop     rdi
0x180005067  pop     rsi
0x180005068  pop     rbp
0x180005069  retn
0x18000506a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005071  jz      short loc_18000505E
0x180005073  mov     rcx, cs:g_pDebug
0x18000507a  lea     rax, aCouldNotCancel_3; "Could not cancel timer\n"
0x180005081  mov     qword ptr [rsp+68h+var_40], rax
0x180005086  lea     r9, aWebAdminServic_5; "WEB_ADMIN_SERVICE::FinishStateTransitio"...
0x18000508d  mov     r8d, 7A5h
0x180005093  mov     [rsp+68h+var_48], edi
0x180005097  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000509e  call    cs:__imp_PuDbgPrintError
0x1800050a4  jmp     short loc_18000505E
```
