# Windows::Compat::Inventory::Service::DeviceAddHelper::AddDevice(ushort const *)

- ea: `0x1800c1510`
- end: `0x1800c1607`
- name: `?AddDevice@DeviceAddHelper@Service@Inventory@Compat@Windows@@QEAAXPEBG@Z`
- size: `247`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::DeviceAddHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c22f8`

## callees

- `0x1800152d0`
- `0x1800c1510`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c1593`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c1593`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c1538`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c1538`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c1554`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c1554`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c155c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c155c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c156b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c156b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15a2`

## string_xrefs

- `0x1800c1571`: `LoadLibraryExW failed [%d]`
- `0x1800c1531`: `devinv.dll`
- `0x1800c15f0`: `Windows::Compat::Inventory::Service::DeviceAddHelper::AddDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Compat::Inventory::Service::DeviceAddHelper::AddDevice(
        Windows::Compat::Inventory::Service::DeviceAddHelper *this,
        const unsigned __int16 *a2)
{
  HMODULE Library; // rdi
  HMODULE v5; // rbp
  DWORD LastError; // ebx
  DWORD v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  FARPROC ProcAddress; // rax

  Library = *(HMODULE *)this;
  if ( *(_QWORD *)this )
    goto LABEL_6;
  Library = LoadLibraryExW(L"devinv.dll", 0, 0x800u);
  v5 = *(HMODULE *)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    FreeLibrary(v5);
    SetLastError(LastError);
  }
  *(_QWORD *)this = Library;
  if ( Library )
  {
LABEL_6:
    ProcAddress = (FARPROC)*((_QWORD *)this + 1);
    if ( ProcAddress
      || (ProcAddress = GetProcAddress(Library, "ReportDeviceAdd"), (*((_QWORD *)this + 1) = ProcAddress) != 0) )
    {
      v7 = ((__int64 (__fastcall *)(const unsigned __int16 *))ProcAddress)(a2);
      if ( !v7 )
      {
        AslLogCallPrintf(3, "Windows::Compat::Inventory::Service::DeviceAddHelper::AddDevice", 588, "Added %ls", a2);
        return;
      }
      v8 = "ReportDeviceAdd failed [%d]";
      v9 = 592;
    }
    else
    {
      v7 = GetLastError();
      v8 = "GetProcAddress failed to find ReportDeviceAdd [%d]";
      v9 = 581;
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = "LoadLibraryExW failed [%d]";
    v9 = 598;
  }
  AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::DeviceAddHelper::AddDevice", v9, v8, v7);
}

```

## disassembly

```asm
0x1800c1510  push    rbx
0x1800c1512  push    rbp
0x1800c1513  push    rsi
0x1800c1514  push    rdi
0x1800c1515  push    r14
0x1800c1517  sub     rsp, 30h
0x1800c151b  mov     r14, rdx
0x1800c151e  mov     rsi, rcx
0x1800c1521  mov     rdi, [rcx]
0x1800c1524  test    rdi, rdi
0x1800c1527  jnz     short loc_1800C1580
0x1800c1529  xor     edx, edx; hFile
0x1800c152b  mov     r8d, 800h; dwFlags
0x1800c1531  lea     rcx, aDevinvDll; "devinv.dll"
0x1800c1538  call    cs:__imp_LoadLibraryExW
0x1800c153e  mov     rdi, rax
0x1800c1541  mov     rbp, [rsi]
0x1800c1544  test    rbp, rbp
0x1800c1547  jz      short loc_1800C1563
0x1800c1549  call    cs:__imp_GetLastError
0x1800c154f  mov     ebx, eax
0x1800c1551  mov     rcx, rbp; hLibModule
0x1800c1554  call    cs:__imp_FreeLibrary
0x1800c155a  mov     ecx, ebx; dwErrCode
0x1800c155c  call    cs:__imp_SetLastError
0x1800c1562  nop
0x1800c1563  mov     [rsi], rdi
0x1800c1566  test    rdi, rdi
0x1800c1569  jnz     short loc_1800C1580
0x1800c156b  call    cs:__imp_GetLastError
0x1800c1571  lea     r9, aLoadlibraryexw_1; "LoadLibraryExW failed [%d]"
0x1800c1578  mov     r8d, 256h
0x1800c157e  jmp     short loc_1800C15E7
0x1800c1580  mov     rax, [rsi+8]
0x1800c1584  test    rax, rax
0x1800c1587  jnz     short loc_1800C15B7
0x1800c1589  lea     rdx, aReportdevicead_0; "ReportDeviceAdd"
0x1800c1590  mov     rcx, rdi; hModule
0x1800c1593  call    cs:__imp_GetProcAddress
0x1800c1599  mov     [rsi+8], rax
0x1800c159d  test    rax, rax
0x1800c15a0  jnz     short loc_1800C15B7
0x1800c15a2  call    cs:__imp_GetLastError
0x1800c15a8  lea     r9, aGetprocaddress_0; "GetProcAddress failed to find ReportDev"...
0x1800c15af  mov     r8d, 245h
0x1800c15b5  jmp     short loc_1800C15E7
0x1800c15b7  mov     rcx, r14
0x1800c15ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c15bf  test    eax, eax
0x1800c15c1  jnz     short loc_1800C15DA
0x1800c15c3  mov     [rsp+58h+var_38], r14
0x1800c15c8  lea     r9, aAddedLs; "Added %ls"
0x1800c15cf  mov     r8d, 24Ch
0x1800c15d5  lea     ecx, [rax+3]
0x1800c15d8  jmp     short loc_1800C15F0
0x1800c15da  lea     r9, aReportdevicead; "ReportDeviceAdd failed [%d]"
0x1800c15e1  mov     r8d, 250h
0x1800c15e7  mov     dword ptr [rsp+58h+var_38], eax
0x1800c15eb  mov     ecx, 1
0x1800c15f0  lea     rdx, aWindowsCompatI_77; "Windows::Compat::Inventory::Service::De"...
0x1800c15f7  call    AslLogCallPrintf
0x1800c15fc  add     rsp, 30h
0x1800c1600  pop     r14
0x1800c1602  pop     rdi
0x1800c1603  pop     rsi
0x1800c1604  pop     rbp
0x1800c1605  pop     rbx
0x1800c1606  retn
```
