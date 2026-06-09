# ServiceControlHandler(ulong)

- ea: `0x180001cf0`
- end: `0x180001e4f`
- name: `?ServiceControlHandler@@YAXK@Z`
- size: `351`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180001a0c`
- `0x180001c04`
- `0x180001cf0`
- `0x1800027a4`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180001d45`
- `IisRTL!PuDbgPrint` at `0x180001d8e`
- `IisRTL!PuDbgPrint` at `0x180001dfe`
- `IisRTL!PuDbgPrint` at `0x180001e3e`
- `IisRTL!PuDbgPrint` at `0x180001d45`
- `IisRTL!PuDbgPrint` at `0x180001d8e`
- `IisRTL!PuDbgPrint` at `0x180001dfe`
- `IisRTL!PuDbgPrint` at `0x180001e3e`

## string_xrefs

- `0x180001de5`: `Interrogating service status for %s\n`
- `0x180001dde`: `InterrogateService`
- `0x180001e17`: `IISAdmin Service received stop notice\n`
- `0x180001d2c`: `ServiceControlHandler`
- `0x180001d75`: `ServiceControlHandler`
- `0x180001e2b`: `ServiceControlHandler`
- `0x180001d6e`: `IISAdmin Service saving metabase\n`
- `0x180001da6`: `IISAdmin Service IGNORING shutdown notice\n`
- `0x180001d1e`: `Unrecognized Service Opcode %lu\n`

## pseudocode

```c
void __fastcall ServiceControlHandler(DWORD dwControl)
{
  switch ( dwControl )
  {
    case 1u:
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
          424,
          "ServiceControlHandler",
          "IISAdmin Service received stop notice\n");
      goto LABEL_17;
    case 4u:
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
          281,
          "InterrogateService",
          "Interrogating service status for %s\n",
          "IISADMIN");
      goto LABEL_14;
    case 5u:
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
          436,
          "ServiceControlHandler",
          "IISAdmin Service saving metabase\n");
      SaveMetabase();
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
          440,
          "ServiceControlHandler",
          "IISAdmin Service IGNORING shutdown notice\n");
LABEL_17:
      StopService();
      return;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
      456,
      "ServiceControlHandler",
      "Unrecognized Service Opcode %lu\n",
      dwControl);
  if ( ((dwControl - 1) & 0xFFFFFFFB) != 0 )
LABEL_14:
    ReportServiceStatus();
}

```

## disassembly

```asm
0x180001cf0  push    rbx
0x180001cf2  sub     rsp, 30h
0x180001cf6  mov     eax, ecx
0x180001cf8  mov     ebx, ecx
0x180001cfa  sub     eax, 1
0x180001cfd  jz      loc_180001E0E
0x180001d03  sub     eax, 3
0x180001d06  jz      loc_180001DB5
0x180001d0c  cmp     eax, 1
0x180001d0f  jz      short loc_180001D5E
0x180001d11  test    byte ptr cs:g_dwDebugFlags, 3
0x180001d18  jz      short loc_180001D4B
0x180001d1a  mov     dword ptr [rsp+38h+var_10], ecx
0x180001d1e  lea     rax, aUnrecognizedSe; "Unrecognized Service Opcode %lu\n"
0x180001d25  mov     rcx, cs:g_pDebug
0x180001d2c  lea     r9, aServicecontrol; "ServiceControlHandler"
0x180001d33  mov     r8d, 1C8h
0x180001d39  mov     [rsp+38h+var_18], rax
0x180001d3e  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180001d45  call    cs:__imp_PuDbgPrint
0x180001d4b  lea     eax, [rbx-1]
0x180001d4e  test    eax, 0FFFFFFFBh
0x180001d53  jz      loc_180001E49
0x180001d59  jmp     loc_180001E04
0x180001d5e  test    byte ptr cs:g_dwDebugFlags, 3
0x180001d65  jz      short loc_180001D94
0x180001d67  mov     rcx, cs:g_pDebug
0x180001d6e  lea     rax, aIisadminServic; "IISAdmin Service saving metabase\n"
0x180001d75  lea     r9, aServicecontrol; "ServiceControlHandler"
0x180001d7c  mov     [rsp+38h+var_18], rax
0x180001d81  mov     r8d, 1B4h
0x180001d87  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180001d8e  call    cs:__imp_PuDbgPrint
0x180001d94  call    ?SaveMetabase@@YAHXZ; SaveMetabase(void)
0x180001d99  test    byte ptr cs:g_dwDebugFlags, 3
0x180001da0  jz      loc_180001E44
0x180001da6  lea     rax, aIisadminServic_0; "IISAdmin Service IGNORING shutdown noti"...
0x180001dad  mov     r8d, 1B8h
0x180001db3  jmp     short loc_180001E24
0x180001db5  mov     eax, cs:g_dwDebugFlags
0x180001dbb  test    al, 3
0x180001dbd  setnz   cl
0x180001dc0  bt      eax, 15h
0x180001dc4  setb    al
0x180001dc7  test    al, cl
0x180001dc9  jz      short loc_180001E04
0x180001dcb  mov     rcx, cs:g_pDebug
0x180001dd2  lea     rax, ServiceName; "IISADMIN"
0x180001dd9  mov     [rsp+38h+var_10], rax
0x180001dde  lea     r9, aInterrogateser; "InterrogateService"
0x180001de5  lea     rax, aInterrogatingS; "Interrogating service status for %s\n"
0x180001dec  mov     r8d, 119h
0x180001df2  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180001df9  mov     [rsp+38h+var_18], rax
0x180001dfe  call    cs:__imp_PuDbgPrint
0x180001e04  add     rsp, 30h
0x180001e08  pop     rbx
0x180001e09  jmp     ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
0x180001e0e  test    byte ptr cs:g_dwDebugFlags, 3
0x180001e15  jz      short loc_180001E44
0x180001e17  lea     rax, aIisadminServic_1; "IISAdmin Service received stop notice\n"
0x180001e1e  mov     r8d, 1A8h
0x180001e24  mov     rcx, cs:g_pDebug
0x180001e2b  lea     r9, aServicecontrol; "ServiceControlHandler"
0x180001e32  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180001e39  mov     [rsp+38h+var_18], rax
0x180001e3e  call    cs:__imp_PuDbgPrint
0x180001e44  call    ?StopService@@YAXXZ; StopService(void)
0x180001e49  add     rsp, 30h
0x180001e4d  pop     rbx
0x180001e4e  retn
```
