# WdipDeleteServerPortName(void)

- ea: `0x18000f45c`
- end: `0x18000f52b`
- name: `?WdipDeleteServerPortName@@YAJXZ`
- size: `207`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e024`

## callees

- `0x180009090`
- `0x18000f45c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f51d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f51d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f48c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f48c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f4d3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f4d3`

## string_xrefs

- `0x18000f47e`: `System\CurrentControlSet\Control\WDI\Config`
- `0x18000f500`: `WdipDeleteServerPortName`

## pseudocode

```c
__int64 WdipDeleteServerPortName(void)
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  int v2; // r8d
  LSTATUS v3; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Config", 0, 2u, &hKey);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 < 0 )
  {
    v2 = 2739;
LABEL_11:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"WdipDeleteServerPortName",
      v2,
      (int)L"Error = %d",
      v1);
    goto LABEL_12;
  }
  if ( !hKey )
  {
    v1 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"WdipDeleteServerPortName",
      2741,
      (int)L"Error = %d",
      5);
    goto LABEL_12;
  }
  v3 = RegDeleteValueW(hKey, L"ServerName");
  v1 = v3;
  if ( v3 > 0 )
    v1 = (unsigned __int16)v3 | 0x80070000;
  if ( v1 < 0 )
  {
    v2 = 2747;
    goto LABEL_11;
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000f45c  push    rbx
0x18000f45e  sub     rsp, 30h
0x18000f462  lea     rax, [rsp+38h+hKey]
0x18000f467  mov     [rsp+38h+hKey], 0
0x18000f470  mov     r9d, 2; samDesired
0x18000f476  mov     [rsp+38h+phkResult], rax; phkResult
0x18000f47b  xor     r8d, r8d; ulOptions
0x18000f47e  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\WDI"...
0x18000f485  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f48c  call    cs:__imp_RegOpenKeyExW
0x18000f492  mov     ebx, eax
0x18000f494  test    eax, eax
0x18000f496  jle     short loc_18000F4A1
0x18000f498  movzx   ebx, ax
0x18000f49b  or      ebx, 80070000h
0x18000f4a1  test    ebx, ebx
0x18000f4a3  jns     short loc_18000F4AD
0x18000f4a5  mov     r8d, 0AB3h
0x18000f4ab  jmp     short loc_18000F4F2
0x18000f4ad  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f4b2  test    rcx, rcx
0x18000f4b5  jnz     short loc_18000F4CC
0x18000f4b7  mov     ebx, 80004005h
0x18000f4bc  mov     dword ptr [rsp+38h+phkResult], 4005h
0x18000f4c4  mov     r8d, 0AB5h
0x18000f4ca  jmp     short loc_18000F4F9
0x18000f4cc  lea     rdx, aServername; "ServerName"
0x18000f4d3  call    cs:__imp_RegDeleteValueW
0x18000f4d9  mov     ebx, eax
0x18000f4db  test    eax, eax
0x18000f4dd  jle     short loc_18000F4E8
0x18000f4df  movzx   ebx, ax
0x18000f4e2  or      ebx, 80070000h
0x18000f4e8  test    ebx, ebx
0x18000f4ea  jns     short loc_18000F513
0x18000f4ec  mov     r8d, 0ABBh; int
0x18000f4f2  movzx   eax, bx
0x18000f4f5  mov     dword ptr [rsp+38h+phkResult], eax; Args
0x18000f4f9  lea     r9, aErrorD; "Error = %d"
0x18000f500  lea     rdx, aWdipdeleteserv; "WdipDeleteServerPortName"
0x18000f507  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f50e  call    WdipTraceError
0x18000f513  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f518  test    rcx, rcx
0x18000f51b  jz      short loc_18000F523
0x18000f51d  call    cs:__imp_RegCloseKey
0x18000f523  mov     eax, ebx
0x18000f525  add     rsp, 30h
0x18000f529  pop     rbx
0x18000f52a  retn
```
