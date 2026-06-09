# ClassInstall_RemoveDevice(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x18001442c`
- end: `0x1800145f4`
- name: `?ClassInstall_RemoveDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `456`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x18000d624`
- `0x18001442c`
- `0x18001598c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145a5`
- `KERNEL32!lstrcmpW` at `0x180014565`
- `KERNEL32!lstrcmpW` at `0x180014565`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800144c5`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800144c5`
- `WINSPOOL!DeletePrinter` at `0x1800145b7`
- `WINSPOOL!DeletePrinter` at `0x1800145b7`
- `WINSPOOL!GetPrinterDataExW` at `0x180014549`
- `WINSPOOL!GetPrinterDataExW` at `0x180014549`
- `WINSPOOL!OpenPrinterW` at `0x180014509`
- `WINSPOOL!OpenPrinterW` at `0x180014509`
- `WINSPOOL!ClosePrinter` at `0x180014574`
- `WINSPOOL!ClosePrinter` at `0x1800145c2`
- `WINSPOOL!ClosePrinter` at `0x180014574`
- `WINSPOOL!ClosePrinter` at `0x1800145c2`

## string_xrefs

- `0x180014478`: `ClassInstall_RemoveDevice - Enter`
- `0x180014488`: `ClassInstall_RemoveDevice`
- `0x180014594`: `ClassInstall_RemoveDevice`
- `0x18001458d`: `ClassInstall_RemoveDevice - Exit`

## pseudocode

```c
DWORD __fastcall ClassInstall_RemoveDevice(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  LPWSTR *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pType; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbNeeded; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pData[200]; // [rsp+210h] [rbp+110h] BYREF

  v8 = 0;
  pcbNeeded = 0;
  pType = 0;
  phPrinter = 0;
  hMem = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_RemoveDevice", L"ClassInstall_RemoveDevice - Enter", a3);
  if ( !SetupDiGetDeviceInstanceIdW(DeviceInfoSet, DeviceInfoData, DeviceInstanceId, 0xC8u, 0)
    || !PrinterInfo2s((struct _PRINTER_INFO_2W **)&hMem, &v8) )
  {
    return GetLastError();
  }
  v5 = (LPWSTR *)hMem;
  v6 = 0;
  if ( !v8 )
  {
LABEL_10:
    ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_RemoveDevice", L"ClassInstall_RemoveDevice - Exit");
    goto LABEL_11;
  }
  while ( !OpenPrinterW(v5[1], &phPrinter, &pDefault) )
  {
LABEL_9:
    ++v6;
    v5 += 17;
    if ( v6 >= v8 )
      goto LABEL_10;
  }
  if ( GetPrinterDataExW(phPrinter, L"PnPData", L"DeviceInstanceId", &pType, (LPBYTE)pData, 0x190u, &pcbNeeded)
    || pType != 1
    || lstrcmpW(pData, DeviceInstanceId) )
  {
    ClosePrinter(phPrinter);
    goto LABEL_9;
  }
  DeletePrinter(phPrinter);
  ClosePrinter(phPrinter);
LABEL_11:
  LocalFree(hMem);
  return -536870386;
}

```

## disassembly

```asm
0x18001442c  mov     [rsp-8+arg_10], rbx
0x180014431  mov     [rsp-8+arg_18], rdi
0x180014436  push    rbp
0x180014437  lea     rbp, [rsp-2B0h]
0x18001443f  sub     rsp, 3B0h
0x180014446  mov     rax, cs:__security_cookie
0x18001444d  xor     rax, rsp
0x180014450  mov     [rbp+2B0h+var_10], rax
0x180014457  mov     rdi, rdx
0x18001445a  mov     [rsp+3B0h+var_370], 0
0x180014462  mov     rbx, rcx
0x180014465  mov     [rsp+3B0h+var_360], 0
0x18001446d  xorps   xmm0, xmm0
0x180014470  mov     [rsp+3B0h+pType], 0
0x180014478  lea     rdx, aClassinstallRe; "ClassInstall_RemoveDevice - Enter"
0x18001447f  mov     [rsp+3B0h+phPrinter], 0
0x180014488  lea     rcx, aClassinstallRe_1; "ClassInstall_RemoveDevice"
0x18001448f  mov     [rsp+3B0h+hMem], 0
0x180014498  movdqu  xmmword ptr [rsp+3B0h+pDefault.pDatatype], xmm0
0x18001449e  mov     qword ptr [rsp+3B0h+pDefault.DesiredAccess], 0F000Ch
0x1800144a7  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800144ac  mov     r9d, 0C8h; DeviceInstanceIdSize
0x1800144b2  mov     [rsp+3B0h+RequiredSize], 0; RequiredSize
0x1800144bb  lea     r8, [rbp+2B0h+DeviceInstanceId]; DeviceInstanceId
0x1800144bf  mov     rdx, rdi; DeviceInfoData
0x1800144c2  mov     rcx, rbx; DeviceInfoSet
0x1800144c5  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x1800144cb  test    eax, eax
0x1800144cd  jz      loc_1800145CA
0x1800144d3  lea     rdx, [rsp+3B0h+var_370]; unsigned int *
0x1800144d8  lea     rcx, [rsp+3B0h+hMem]; struct _PRINTER_INFO_2W **
0x1800144dd  call    ?PrinterInfo2s@@YAHPEAPEAU_PRINTER_INFO_2W@@PEAK@Z; PrinterInfo2s(_PRINTER_INFO_2W * *,ulong *)
0x1800144e2  test    eax, eax
0x1800144e4  jz      loc_1800145CA
0x1800144ea  mov     rdi, [rsp+3B0h+hMem]
0x1800144ef  xor     ebx, ebx
0x1800144f1  cmp     [rsp+3B0h+var_370], ebx
0x1800144f5  jbe     loc_18001458D
0x1800144fb  mov     rcx, [rdi+8]; pPrinterName
0x1800144ff  lea     r8, [rsp+3B0h+pDefault]; pDefault
0x180014504  lea     rdx, [rsp+3B0h+phPrinter]; phPrinter
0x180014509  call    cs:__imp_OpenPrinterW
0x18001450f  test    eax, eax
0x180014511  jz      short loc_18001457A
0x180014513  mov     rcx, [rsp+3B0h+phPrinter]; hPrinter
0x180014518  lea     rax, [rsp+3B0h+var_360]
0x18001451d  mov     [rsp+3B0h+pcbNeeded], rax; pcbNeeded
0x180014522  lea     r9, [rsp+3B0h+pType]; pType
0x180014527  lea     rax, [rbp+2B0h+pData]
0x18001452e  mov     [rsp+3B0h+nSize], 190h; nSize
0x180014536  lea     r8, pValueName; "DeviceInstanceId"
0x18001453d  mov     [rsp+3B0h+RequiredSize], rax; pData
0x180014542  lea     rdx, pKeyName; "PnPData"
0x180014549  call    cs:__imp_GetPrinterDataExW
0x18001454f  test    eax, eax
0x180014551  jnz     short loc_18001456F
0x180014553  cmp     [rsp+3B0h+pType], 1
0x180014558  jnz     short loc_18001456F
0x18001455a  lea     rdx, [rbp+2B0h+DeviceInstanceId]; lpString2
0x18001455e  lea     rcx, [rbp+2B0h+pData]; lpString1
0x180014565  call    cs:__imp_lstrcmpW
0x18001456b  test    eax, eax
0x18001456d  jz      short loc_1800145B2
0x18001456f  mov     rcx, [rsp+3B0h+phPrinter]; hPrinter
0x180014574  call    cs:__imp_ClosePrinter
0x18001457a  inc     ebx
0x18001457c  add     rdi, 88h
0x180014583  cmp     ebx, [rsp+3B0h+var_370]
0x180014587  jb      loc_1800144FB
0x18001458d  lea     rdx, aClassinstallRe_0; "ClassInstall_RemoveDevice - Exit"
0x180014594  lea     rcx, aClassinstallRe_1; "ClassInstall_RemoveDevice"
0x18001459b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800145a0  mov     rcx, [rsp+3B0h+hMem]; hMem
0x1800145a5  call    cs:__imp_LocalFree
0x1800145ab  mov     eax, 0E000020Eh
0x1800145b0  jmp     short loc_1800145D0
0x1800145b2  mov     rcx, [rsp+3B0h+phPrinter]; hPrinter
0x1800145b7  call    cs:__imp_DeletePrinter
0x1800145bd  mov     rcx, [rsp+3B0h+phPrinter]; hPrinter
0x1800145c2  call    cs:__imp_ClosePrinter
0x1800145c8  jmp     short loc_1800145A0
0x1800145ca  call    cs:__imp_GetLastError
0x1800145d0  mov     rcx, [rbp+2B0h+var_10]
0x1800145d7  xor     rcx, rsp; StackCookie
0x1800145da  call    __security_check_cookie
0x1800145df  lea     r11, [rsp+3B0h+var_s0]
0x1800145e7  mov     rbx, [r11+20h]
0x1800145eb  mov     rdi, [r11+28h]
0x1800145ef  mov     rsp, r11
0x1800145f2  pop     rbp
0x1800145f3  retn
```
