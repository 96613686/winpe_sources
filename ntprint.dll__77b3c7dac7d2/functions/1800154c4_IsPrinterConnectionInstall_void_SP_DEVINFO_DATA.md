# IsPrinterConnectionInstall(void *,_SP_DEVINFO_DATA *)

- ea: `0x1800154c4`
- end: `0x1800155ec`
- name: `?IsPrinterConnectionInstall@@YAHPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180013804`

## callees

- `0x180002300`
- `0x18000d57c`
- `0x1800154c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015573`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155ac`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180015531`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180015531`

## string_xrefs

- `0x1800155bc`: `IsPrinterConnectionInstall`

## pseudocode

```c
__int64 __fastcall IsPrinterConnectionInstall(void *a1, struct _SP_DEVINFO_DATA *a2)
{
  unsigned int v3; // edi
  BYTE *i; // rbx
  __int64 v5; // rax
  DWORD LastError; // eax
  DWORD RequiredSize; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType[3]; // [rsp+44h] [rbp-BCh] BYREF
  BYTE PropertyBuffer[2048]; // [rsp+50h] [rbp-B0h] BYREF

  PropertyType[0] = 0;
  RequiredSize = 0;
  if ( !a2 )
    return 87;
  v3 = 0;
  if ( SetupDiGetDevicePropertyW(
         a1,
         a2,
         &DEVPKEY_Device_HardwareIds,
         PropertyType,
         PropertyBuffer,
         0x800u,
         &RequiredSize,
         0)
    && PropertyType[0] == 8210 )
  {
    for ( i = PropertyBuffer; i < &PropertyBuffer[RequiredSize & 0xFFFFFFFE]; i += 2 * v5 + 2 )
    {
      if ( !*(_WORD *)i )
        break;
      if ( !(unsigned int)_o__wcsicmp(i, L"PRINTENUM\\PrinterConnection") )
        v3 = 1;
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&i[2 * v5] );
    }
  }
  else
  {
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "IsPrinterConnectionInstall",
      L"Failed to get DEVPKEY_Device_HardwareIds: %d",
      LastError);
  }
  return v3;
}

```

## disassembly

```asm
0x1800154c4  mov     [rsp-8+arg_10], rbx
0x1800154c9  push    rbp
0x1800154ca  push    rsi
0x1800154cb  push    rdi
0x1800154cc  lea     rbp, [rsp-760h]
0x1800154d4  sub     rsp, 860h
0x1800154db  mov     rax, cs:__security_cookie
0x1800154e2  xor     rax, rsp
0x1800154e5  mov     [rbp+770h+var_20], rax
0x1800154ec  xor     esi, esi
0x1800154ee  mov     [rsp+870h+PropertyType], esi
0x1800154f2  mov     [rsp+870h+var_830], esi
0x1800154f6  test    rdx, rdx
0x1800154f9  jnz     short loc_180015503
0x1800154fb  lea     eax, [rsi+57h]
0x1800154fe  jmp     loc_1800155CA
0x180015503  mov     [rsp+870h+Flags], esi; Flags
0x180015507  lea     rax, [rsp+870h+var_830]
0x18001550c  mov     [rsp+870h+RequiredSize], rax; RequiredSize
0x180015511  lea     r9, [rsp+870h+PropertyType]; PropertyType
0x180015516  lea     rax, [rsp+870h+var_820]
0x18001551b  mov     [rsp+870h+PropertyBufferSize], 800h; PropertyBufferSize
0x180015523  lea     r8, DEVPKEY_Device_HardwareIds; PropertyKey
0x18001552a  mov     [rsp+870h+PropertyBuffer], rax; PropertyBuffer
0x18001552f  mov     edi, esi
0x180015531  call    cs:__imp_SetupDiGetDevicePropertyW
0x180015537  test    eax, eax
0x180015539  jz      short loc_1800155AC
0x18001553b  cmp     [rsp+870h+PropertyType], 2012h
0x180015543  jnz     short loc_1800155AC
0x180015545  mov     eax, [rsp+870h+var_830]
0x180015549  lea     rcx, [rsp+870h+var_820]
0x18001554e  and     rax, 0FFFFFFFFFFFFFFFEh
0x180015552  lea     rbx, [rsp+870h+var_820]
0x180015557  add     rax, rcx
0x18001555a  lea     rcx, [rsp+870h+var_820]
0x18001555f  cmp     rcx, rax
0x180015562  jnb     short loc_1800155C8
0x180015564  cmp     [rbx], si
0x180015567  jz      short loc_1800155C8
0x180015569  lea     rdx, aPrintenumPrint; "PRINTENUM\\PrinterConnection"
0x180015570  mov     rcx, rbx
0x180015573  call    cs:__imp__o__wcsicmp
0x180015579  test    eax, eax
0x18001557b  mov     ecx, 1
0x180015580  cmovz   edi, ecx
0x180015583  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015587  inc     rax
0x18001558a  cmp     [rbx+rax*2], si
0x18001558e  jnz     short loc_180015587
0x180015590  lea     rbx, [rbx+rax*2]
0x180015594  mov     eax, [rsp+870h+var_830]
0x180015598  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001559c  add     rbx, 2
0x1800155a0  lea     rax, [rsp+rax+870h+var_820]
0x1800155a5  cmp     rbx, rax
0x1800155a8  jb      short loc_180015564
0x1800155aa  jmp     short loc_1800155C8
0x1800155ac  call    cs:__imp_GetLastError
0x1800155b2  mov     r8d, eax
0x1800155b5  lea     rdx, aFailedToGetDev; "Failed to get DEVPKEY_Device_HardwareId"...
0x1800155bc  lea     rcx, aIsprinterconne; "IsPrinterConnectionInstall"
0x1800155c3  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800155c8  mov     eax, edi
0x1800155ca  mov     rcx, [rbp+770h+var_20]
0x1800155d1  xor     rcx, rsp; StackCookie
0x1800155d4  call    __security_check_cookie
0x1800155d9  mov     rbx, [rsp+870h+arg_10]
0x1800155e1  add     rsp, 860h
0x1800155e8  pop     rdi
0x1800155e9  pop     rsi
0x1800155ea  pop     rbp
0x1800155eb  retn
```
