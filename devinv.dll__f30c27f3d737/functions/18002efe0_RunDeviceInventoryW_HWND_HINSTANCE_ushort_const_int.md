# RunDeviceInventoryW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x18002efe0`
- end: `0x18002f0eb`
- name: `?RunDeviceInventoryW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `267`
- prototype: `void __fastcall(HWND, HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006d02`
- `0x180007014`
- `0x18002efe0`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002efe6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002f046`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002f094`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002f0b4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002efe6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002f046`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002f094`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18002f0b4`

## string_xrefs

- `0x18002efec`: `RunDeviceInventoryW was called. Command line: %ws [%#x]`
- `0x18002f05f`: `RunDeviceInventoryW was called. Command line: %ws [%#x]`
- `0x18002f0a0`: `RunDeviceInventoryW was called. Command line: %ws [%#x]`
- `0x18002f0ba`: `RunDeviceInventoryW was called. Command line: %ws [%#x]`

## pseudocode

```c
void __fastcall RunDeviceInventoryW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  LPWSTR CommandLineW; // rax
  FILE *v4; // rax
  LPWSTR v5; // rbx
  FILE *v6; // rax
  FILE *v7; // rax
  LPWSTR v8; // rax
  LPWSTR v9; // rax
  int v10; // [rsp+28h] [rbp-10h]
  __int64 v11; // [rsp+28h] [rbp-10h]

  CommandLineW = GetCommandLineW();
  v10 = -2147418113;
  AslLogCallPrintf(
    2,
    "RunDeviceInventoryW",
    441,
    "RunDeviceInventoryW was called. Command line: %ws [%#x]",
    CommandLineW,
    v10);
  if ( EnableDevInvStdErrLog )
  {
    v4 = o___acrt_iob_func_0(2u);
    fprintf(v4, "Error: %s, %u: ", "RunDeviceInventoryW", 441);
    v5 = GetCommandLineW();
    v6 = o___acrt_iob_func_0(2u);
    fprintf(v6, "RunDeviceInventoryW was called. Command line: %ws [%#x]", v5, 2147549183LL);
    v7 = o___acrt_iob_func_0(2u);
    fprintf(v7, "\n");
  }
  if ( g_DeviceMapLogFunction )
  {
    v8 = GetCommandLineW();
    TraceMessageCallback(0x2000000, "RunDeviceInventoryW was called. Command line: %ws [%#x]", v8, 2147549183LL);
  }
  v9 = GetCommandLineW();
  LODWORD(v11) = -2147418113;
  AslLogCallPrintf(1, "RunDeviceInventoryW", 441, "RunDeviceInventoryW was called. Command line: %ws [%#x]", v9, v11);
}

```

## disassembly

```asm
0x18002efe0  push    rbx
0x18002efe2  sub     rsp, 30h
0x18002efe6  call    cs:__imp_GetCommandLineW
0x18002efec  lea     r9, aRundeviceinven_0; "RunDeviceInventoryW was called. Command"...
0x18002eff3  mov     [rsp+38h+var_10], 8000FFFFh
0x18002effb  mov     r8d, 1B9h
0x18002f001  mov     [rsp+38h+var_18], rax
0x18002f006  lea     rdx, aRundeviceinven_1; "RunDeviceInventoryW"
0x18002f00d  mov     ecx, 2
0x18002f012  call    AslLogCallPrintf
0x18002f017  cmp     cs:EnableDevInvStdErrLog, 0
0x18002f01e  jz      short loc_18002F08A
0x18002f020  mov     ecx, 2; Ix
0x18002f025  call    _o___acrt_iob_func_0
0x18002f02a  mov     rcx, rax; Stream
0x18002f02d  lea     r8, aRundeviceinven_1; "RunDeviceInventoryW"
0x18002f034  mov     r9d, 1B9h
0x18002f03a  lea     rdx, Format; "Error: %s, %u: "
0x18002f041  call    fprintf
0x18002f046  call    cs:__imp_GetCommandLineW
0x18002f04c  mov     ecx, 2; Ix
0x18002f051  mov     rbx, rax
0x18002f054  call    _o___acrt_iob_func_0
0x18002f059  mov     r9d, 8000FFFFh
0x18002f05f  lea     rdx, aRundeviceinven_0; "RunDeviceInventoryW was called. Command"...
0x18002f066  mov     r8, rbx
0x18002f069  mov     rcx, rax; Stream
0x18002f06c  call    fprintf
0x18002f071  mov     ecx, 2; Ix
0x18002f076  call    _o___acrt_iob_func_0
0x18002f07b  mov     rcx, rax; Stream
0x18002f07e  lea     rdx, asc_18011EAD8; "\n"
0x18002f085  call    fprintf
0x18002f08a  cmp     cs:g_DeviceMapLogFunction, 0
0x18002f092  jz      short loc_18002F0B4
0x18002f094  call    cs:__imp_GetCommandLineW
0x18002f09a  mov     r9d, 8000FFFFh
0x18002f0a0  lea     rdx, aRundeviceinven_0; "RunDeviceInventoryW was called. Command"...
0x18002f0a7  mov     r8, rax
0x18002f0aa  mov     ecx, 2000000h
0x18002f0af  call    TraceMessageCallback
0x18002f0b4  call    cs:__imp_GetCommandLineW
0x18002f0ba  lea     r9, aRundeviceinven_0; "RunDeviceInventoryW was called. Command"...
0x18002f0c1  mov     [rsp+38h+var_10], 8000FFFFh
0x18002f0c9  mov     r8d, 1B9h
0x18002f0cf  mov     [rsp+38h+var_18], rax
0x18002f0d4  lea     rdx, aRundeviceinven_1; "RunDeviceInventoryW"
0x18002f0db  mov     ecx, 1
0x18002f0e0  call    AslLogCallPrintf
0x18002f0e5  add     rsp, 30h
0x18002f0e9  pop     rbx
0x18002f0ea  retn
```
