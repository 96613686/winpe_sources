# NewDriverForInstalledDevice(_PSETUP_LOCAL_DATA *,ushort *,ushort *)

- ea: `0x1800156c4`
- end: `0x18001582b`
- name: `?NewDriverForInstalledDevice@@YAHPEAU_PSETUP_LOCAL_DATA@@PEAG1@Z`
- size: `359`
- prototype: `int(struct _PSETUP_LOCAL_DATA *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180013804`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x1800156c4`
- `0x180015904`
- `0x18001598c`
- `0x180015a7c`
- `0x1800162c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800157f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800157f5`
- `WINSPOOL!SetPrinterW` at `0x1800157ab`
- `WINSPOOL!SetPrinterW` at `0x1800157ab`
- `WINSPOOL!OpenPrinterW` at `0x180015783`
- `WINSPOOL!OpenPrinterW` at `0x180015783`
- `WINSPOOL!ClosePrinter` at `0x1800157de`
- `WINSPOOL!ClosePrinter` at `0x1800157de`

## string_xrefs

- `0x1800156f7`: `NewDriverForInstalledDevice - Enter.`
- `0x180015701`: `NewDriverForInstalledDevice`
- `0x1800157ca`: `NewDriverForInstalledDevice`
- `0x180015802`: `NewDriverForInstalledDevice`
- `0x1800157fb`: `NewDriverForInstalledDevice: Exit`

## pseudocode

```c
__int64 __fastcall NewDriverForInstalledDevice(
        struct _PSETUP_LOCAL_DATA *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned int v5; // r14d
  unsigned int v7; // eax
  unsigned int v8; // edi
  struct _PRINTER_INFO_2W *v9; // rbx
  DWORD LastError; // [rsp+20h] [rbp-40h]
  LPBYTE pPrinter; // [rsp+30h] [rbp-30h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-28h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+A8h] [rbp+48h] BYREF

  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  pPrinter = 0;
  v5 = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  v15 = 0;
  phPrinter = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo("NewDriverForInstalledDevice", L"NewDriverForInstalledDevice - Enter.");
  if ( PrinterInfo2s((struct _PRINTER_INFO_2W **)&pPrinter, &v15) )
  {
    v7 = v15;
    v8 = 0;
    v9 = (struct _PRINTER_INFO_2W *)pPrinter;
    if ( v15 )
    {
      while ( !PrinterGoingToPort(v9, a2) || !(unsigned int)PrinterPnPDataSame(a3, v9->pPrinterName) )
      {
        v7 = v15;
        ++v8;
        ++v9;
        if ( v8 >= v15 )
          goto LABEL_8;
      }
      v7 = v15;
    }
LABEL_8:
    if ( v8 != v7 && OpenPrinterW(v9->pPrinterName, &phPrinter, &pDefault) )
    {
      v9->pDriverName = (LPWSTR)*((_QWORD *)a1 + 1);
      v9->pPrintProcessor = 0;
      v9->pDatatype = 0;
      if ( !SetPrinterW(phPrinter, 2u, (LPBYTE)v9, 0) )
      {
        LastError = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceWarning(
          "NewDriverForInstalledDevice",
          L"Failed to change printer '%ws' to driver '%ws': %d",
          v9->pPrinterName,
          v9->pDriverName,
          LastError);
      }
      ClosePrinter(phPrinter);
      v5 = 1;
    }
  }
  if ( pPrinter )
    LocalFree(pPrinter);
  ClassInstallerTelemetry::WriteDbgTraceError("NewDriverForInstalledDevice", L"NewDriverForInstalledDevice: Exit");
  return v5;
}

```

## disassembly

```asm
0x1800156c4  mov     [rsp-28h+arg_0], rbx
0x1800156c9  mov     [rsp-28h+arg_8], rdi
0x1800156ce  push    rbp
0x1800156cf  push    r12
0x1800156d1  push    r13
0x1800156d3  push    r14
0x1800156d5  push    r15
0x1800156d7  mov     rbp, rsp
0x1800156da  sub     rsp, 60h
0x1800156de  mov     r12, rdx
0x1800156e1  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x1800156e9  mov     r13, rcx
0x1800156ec  mov     [rbp+pPrinter], 0
0x1800156f4  xorps   xmm0, xmm0
0x1800156f7  lea     rdx, aNewdriverforin_1; "NewDriverForInstalledDevice - Enter."
0x1800156fe  xor     r14d, r14d
0x180015701  lea     rcx, aNewdriverforin; "NewDriverForInstalledDevice"
0x180015708  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18001570d  mov     [rbp+arg_18], r14d
0x180015711  mov     r15, r8
0x180015714  mov     [rbp+phPrinter], r14
0x180015718  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001571d  lea     rdx, [rbp+arg_18]; unsigned int *
0x180015721  lea     rcx, [rbp+pPrinter]; struct _PRINTER_INFO_2W **
0x180015725  call    ?PrinterInfo2s@@YAHPEAPEAU_PRINTER_INFO_2W@@PEAK@Z; PrinterInfo2s(_PRINTER_INFO_2W * *,ulong *)
0x18001572a  test    eax, eax
0x18001572c  jz      loc_1800157EA
0x180015732  mov     eax, [rbp+arg_18]
0x180015735  xor     edi, edi
0x180015737  mov     rbx, [rbp+pPrinter]
0x18001573b  test    eax, eax
0x18001573d  jz      short loc_180015773
0x18001573f  mov     rdx, r12; unsigned __int16 *
0x180015742  mov     rcx, rbx; struct _PRINTER_INFO_2W *
0x180015745  call    ?PrinterGoingToPort@@YAHPEAU_PRINTER_INFO_2W@@PEBG@Z; PrinterGoingToPort(_PRINTER_INFO_2W *,ushort const *)
0x18001574a  test    eax, eax
0x18001574c  jz      short loc_18001575E
0x18001574e  mov     rdx, [rbx+8]; pPrinterName
0x180015752  mov     rcx, r15; lpString2
0x180015755  call    ?PrinterPnPDataSame@@YAHPEAG0@Z; PrinterPnPDataSame(ushort *,ushort *)
0x18001575a  test    eax, eax
0x18001575c  jnz     short loc_180015770
0x18001575e  mov     eax, [rbp+arg_18]
0x180015761  inc     edi
0x180015763  add     rbx, 88h
0x18001576a  cmp     edi, eax
0x18001576c  jb      short loc_18001573F
0x18001576e  jmp     short loc_180015773
0x180015770  mov     eax, [rbp+arg_18]
0x180015773  cmp     edi, eax
0x180015775  jz      short loc_1800157EA
0x180015777  mov     rcx, [rbx+8]; pPrinterName
0x18001577b  lea     r8, [rbp+pDefault]; pDefault
0x18001577f  lea     rdx, [rbp+phPrinter]; phPrinter
0x180015783  call    cs:__imp_OpenPrinterW
0x180015789  test    eax, eax
0x18001578b  jz      short loc_1800157EA
0x18001578d  mov     rax, [r13+8]
0x180015791  xor     r9d, r9d; Command
0x180015794  mov     [rbx+20h], rax
0x180015798  mov     r8, rbx; pPrinter
0x18001579b  mov     [rbx+48h], r14
0x18001579f  mov     [rbx+50h], r14
0x1800157a3  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800157a7  lea     edx, [r9+2]; Level
0x1800157ab  call    cs:__imp_SetPrinterW
0x1800157b1  test    eax, eax
0x1800157b3  jnz     short loc_1800157DA
0x1800157b5  call    cs:__imp_GetLastError
0x1800157bb  mov     r9, [rbx+20h]
0x1800157bf  lea     rdx, aFailedToChange; "Failed to change printer '%ws' to drive"...
0x1800157c6  mov     r8, [rbx+8]
0x1800157ca  lea     rcx, aNewdriverforin; "NewDriverForInstalledDevice"
0x1800157d1  mov     [rsp+60h+var_40], eax
0x1800157d5  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800157da  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800157de  call    cs:__imp_ClosePrinter
0x1800157e4  mov     r14d, 1
0x1800157ea  cmp     [rbp+pPrinter], 0
0x1800157ef  jz      short loc_1800157FB
0x1800157f1  mov     rcx, [rbp+pPrinter]; hMem
0x1800157f5  call    cs:__imp_LocalFree
0x1800157fb  lea     rdx, aNewdriverforin_0; "NewDriverForInstalledDevice: Exit"
0x180015802  lea     rcx, aNewdriverforin; "NewDriverForInstalledDevice"
0x180015809  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001580e  lea     r11, [rsp+60h+var_s0]
0x180015813  mov     eax, r14d
0x180015816  mov     rbx, [r11+30h]
0x18001581a  mov     rdi, [r11+38h]
0x18001581e  mov     rsp, r11
0x180015821  pop     r15
0x180015823  pop     r14
0x180015825  pop     r13
0x180015827  pop     r12
0x180015829  pop     rbp
0x18001582a  retn
```
