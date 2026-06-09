# ClassInstall_AllowInstall(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x18001349c`
- end: `0x180013554`
- name: `?ClassInstall_AllowInstall@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `184`
- prototype: `unsigned int __fastcall(void *, struct _SP_DEVINFO_DATA *, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x18000d624`
- `0x18001349c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013511`
- `WINSPOOL!EnumPrintProcessorsW` at `0x1800134fa`
- `WINSPOOL!EnumPrintProcessorsW` at `0x1800134fa`

## string_xrefs

- `0x1800134ab`: `ClassInstall_AllowInstall: Enter.`
- `0x1800134b7`: `ClassInstall_AllowInstall`
- `0x180013525`: `ClassInstall_AllowInstall`
- `0x180013540`: `ClassInstall_AllowInstall`
- `0x180013539`: `ClassInstall_AllowInstall Exit: %d`

## pseudocode

```c
__int64 __fastcall ClassInstall_AllowInstall(void *a1, struct _SP_DEVINFO_DATA *a2, struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  unsigned int v3; // ebx
  struct _SP_DEVINFO_DATA *pcbNeeded; // [rsp+58h] [rbp+10h] BYREF
  struct _SP_DEVINSTALL_PARAMS_W *pcReturned; // [rsp+60h] [rbp+18h] BYREF

  pcReturned = a3;
  pcbNeeded = a2;
  v3 = -536870386;
  ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_AllowInstall", L"ClassInstall_AllowInstall: Enter.");
  LODWORD(pcbNeeded) = 0;
  LODWORD(pcReturned) = 0;
  if ( !EnumPrintProcessorsW(0, 0, 1u, 0, 0, (LPDWORD)&pcbNeeded, (LPDWORD)&pcReturned)
    && (GetLastError() == 1722 || GetLastError() == 1753) )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_AllowInstall", L"The spooler is not runnning");
    v3 = -536870330;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_AllowInstall", L"ClassInstall_AllowInstall Exit: %d", v3);
  return v3;
}

```

## disassembly

```asm
0x18001349c  mov     [rsp+arg_10], r8
0x1800134a1  mov     [rsp+arg_8], rdx
0x1800134a6  push    rbx
0x1800134a7  sub     rsp, 40h
0x1800134ab  lea     rdx, aClassinstallAl_0; "ClassInstall_AllowInstall: Enter."
0x1800134b2  mov     ebx, 0E000020Eh
0x1800134b7  lea     rcx, aClassinstallAl_1; "ClassInstall_AllowInstall"
0x1800134be  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800134c3  lea     rax, [rsp+48h+arg_10]
0x1800134c8  mov     dword ptr [rsp+48h+arg_8], 0
0x1800134d0  mov     [rsp+48h+pcReturned], rax; pcReturned
0x1800134d5  xor     r9d, r9d; pPrintProcessorInfo
0x1800134d8  lea     rax, [rsp+48h+arg_8]
0x1800134dd  mov     dword ptr [rsp+48h+arg_10], 0
0x1800134e5  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x1800134ea  xor     edx, edx; pEnvironment
0x1800134ec  xor     ecx, ecx; pName
0x1800134ee  mov     [rsp+48h+cbBuf], 0; cbBuf
0x1800134f6  lea     r8d, [r9+1]; Level
0x1800134fa  call    cs:__imp_EnumPrintProcessorsW
0x180013500  test    eax, eax
0x180013502  jnz     short loc_180013536
0x180013504  call    cs:__imp_GetLastError
0x18001350a  cmp     eax, 6BAh
0x18001350f  jz      short loc_18001351E
0x180013511  call    cs:__imp_GetLastError
0x180013517  cmp     eax, 6D9h
0x18001351c  jnz     short loc_180013536
0x18001351e  lea     rdx, aTheSpoolerIsNo; "The spooler is not runnning"
0x180013525  lea     rcx, aClassinstallAl_1; "ClassInstall_AllowInstall"
0x18001352c  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013531  mov     ebx, 0E0000246h
0x180013536  mov     r8d, ebx
0x180013539  lea     rdx, aClassinstallAl; "ClassInstall_AllowInstall Exit: %d"
0x180013540  lea     rcx, aClassinstallAl_1; "ClassInstall_AllowInstall"
0x180013547  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001354c  mov     eax, ebx
0x18001354e  add     rsp, 40h
0x180013552  pop     rbx
0x180013553  retn
```
