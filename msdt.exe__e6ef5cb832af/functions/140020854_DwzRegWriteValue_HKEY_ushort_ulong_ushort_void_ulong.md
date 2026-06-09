# DwzRegWriteValue(HKEY__ *,ushort *,ulong,ushort *,void *,ulong)

- ea: `0x140020854`
- end: `0x140020952`
- name: `?DwzRegWriteValue@@YAJPEAUHKEY__@@PEAGK1PEAXK@Z`
- size: `254`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned int, unsigned __int16 *, BYTE *lpData, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003eb60`

## callees

- `0x140020420`
- `0x140020854`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002093d`
- `ADVAPI32!RegCloseKey` at `0x14002093d`
- `ADVAPI32!RegCreateKeyExW` at `0x1400208a4`
- `ADVAPI32!RegCreateKeyExW` at `0x1400208a4`
- `ADVAPI32!RegSetValueExW` at `0x1400208f2`
- `ADVAPI32!RegSetValueExW` at `0x1400208f2`

## string_xrefs

- `0x140020917`: `DwzRegWriteValue`

## pseudocode

```c
__int64 __fastcall DwzRegWriteValue(HKEY a1, unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4, BYTE *lpData)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  int v7; // r9d
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\ScriptedDiagnosticsProvider\\Policy",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 316;
LABEL_9:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzRegWriteValue", v7, v6);
    goto LABEL_10;
  }
  v8 = RegSetValueExW(hKey, L"EnableQueryRemoteServer", 0, 4u, lpData, 4u);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 325;
    goto LABEL_9;
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140020854  mov     r11, rsp
0x140020857  mov     [r11+20h], r9
0x14002085b  push    rbx
0x14002085c  sub     rsp, 50h
0x140020860  mov     qword ptr [r11-18h], 0
0x140020868  lea     rax, [r11+20h]
0x14002086c  mov     [r11-20h], rax
0x140020870  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\ScriptedD"...
0x140020877  mov     qword ptr [r11-28h], 0
0x14002087f  xor     r9d, r9d; lpClass
0x140020882  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x14002088a  xor     r8d, r8d; Reserved
0x14002088d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140020894  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14002089c  mov     qword ptr [r11+20h], 0
0x1400208a4  call    cs:__imp_RegCreateKeyExW
0x1400208ab  nop     dword ptr [rax+rax+00h]
0x1400208b0  mov     ebx, eax
0x1400208b2  test    eax, eax
0x1400208b4  jle     short loc_1400208BF
0x1400208b6  movzx   ebx, ax
0x1400208b9  or      ebx, 80070000h
0x1400208bf  test    ebx, ebx
0x1400208c1  jns     short loc_1400208CB
0x1400208c3  mov     r9d, 13Ch
0x1400208c9  jmp     short loc_140020917
0x1400208cb  mov     rax, [rsp+58h+lpData]
0x1400208d3  lea     rdx, ValueName; "EnableQueryRemoteServer"
0x1400208da  mov     rcx, [rsp+58h+hKey]; hKey
0x1400208df  mov     r9d, 4; dwType
0x1400208e5  mov     [rsp+58h+samDesired], r9d; cbData
0x1400208ea  xor     r8d, r8d; Reserved
0x1400208ed  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1400208f2  call    cs:__imp_RegSetValueExW
0x1400208f9  nop     dword ptr [rax+rax+00h]
0x1400208fe  mov     ebx, eax
0x140020900  test    eax, eax
0x140020902  jle     short loc_14002090D
0x140020904  movzx   ebx, ax
0x140020907  or      ebx, 80070000h
0x14002090d  test    ebx, ebx
0x14002090f  jns     short loc_140020933
0x140020911  mov     r9d, 145h
0x140020917  lea     r8, aDwzregwriteval; "DwzRegWriteValue"
0x14002091e  mov     [rsp+58h+dwOptions], ebx
0x140020922  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140020929  mov     ecx, 1; Level
0x14002092e  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140020933  mov     rcx, [rsp+58h+hKey]; hKey
0x140020938  test    rcx, rcx
0x14002093b  jz      short loc_140020949
0x14002093d  call    cs:__imp_RegCloseKey
0x140020944  nop     dword ptr [rax+rax+00h]
0x140020949  mov     eax, ebx
0x14002094b  add     rsp, 50h
0x14002094f  pop     rbx
0x140020950  retn
```
