# UpdateMiniportsEnabledRegistry

- ea: `0x1800469b0`
- end: `0x180046a64`
- name: `UpdateMiniportsEnabledRegistry`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180045ee8`

## callees

- `0x180046534`
- `0x1800469b0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180046a11`
- `ADVAPI32!RegOpenKeyExW` at `0x180046a11`
- `ADVAPI32!RegSetValueExW` at `0x180046a3f`
- `ADVAPI32!RegSetValueExW` at `0x180046a3f`
- `ADVAPI32!RegCloseKey` at `0x180046a4c`
- `ADVAPI32!RegCloseKey` at `0x180046a4c`

## string_xrefs

- `0x180046a03`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x180046a38`: `MiniportsInstalled`

## pseudocode

```c
__int64 __fastcall UpdateMiniportsEnabledRegistry(int a1, int a2)
{
  int MiniportsEnabledRegistry; // eax
  int v5; // ebx
  unsigned int v6; // edi
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  MiniportsEnabledRegistry = GetMiniportsEnabledRegistry();
  if ( a2 == 8 )
  {
    v5 = MiniportsEnabledRegistry & ~a1;
  }
  else
  {
    v6 = 0;
    if ( a2 != 1 )
      goto LABEL_7;
    v5 = MiniportsEnabledRegistry | a1;
  }
  Data = v5;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters", 0, 0x20006u, &hKey);
  if ( !v6 )
    v6 = RegSetValueExW(hKey, L"MiniportsInstalled", 0, 4u, (const BYTE *)&Data, 4u);
LABEL_7:
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800469b0  mov     rax, rsp
0x1800469b3  mov     [rax+8], rbx
0x1800469b7  mov     [rax+20h], rsi
0x1800469bb  push    rdi
0x1800469bc  sub     rsp, 30h
0x1800469c0  mov     esi, edx
0x1800469c2  mov     qword ptr [rax+18h], 0
0x1800469ca  mov     ebx, ecx
0x1800469cc  mov     dword ptr [rax+10h], 0
0x1800469d3  call    GetMiniportsEnabledRegistry
0x1800469d8  cmp     esi, 8
0x1800469db  jnz     short loc_1800469E3
0x1800469dd  not     ebx
0x1800469df  and     ebx, eax
0x1800469e1  jmp     short loc_1800469EC
0x1800469e3  xor     edi, edi
0x1800469e5  cmp     esi, 1
0x1800469e8  jnz     short loc_180046A47
0x1800469ea  or      ebx, eax
0x1800469ec  lea     rax, [rsp+38h+hKey]
0x1800469f1  mov     [rsp+38h+Data], ebx
0x1800469f5  mov     r9d, 20006h; samDesired
0x1800469fb  mov     [rsp+38h+phkResult], rax; phkResult
0x180046a00  xor     r8d, r8d; ulOptions
0x180046a03  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180046a0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046a11  call    cs:__imp_RegOpenKeyExW
0x180046a17  mov     edi, eax
0x180046a19  test    eax, eax
0x180046a1b  jnz     short loc_180046A47
0x180046a1d  mov     rcx, [rsp+38h+hKey]; hKey
0x180046a22  lea     r9d, [rax+4]; dwType
0x180046a26  lea     rax, [rsp+38h+Data]
0x180046a2b  mov     [rsp+38h+cbData], r9d; cbData
0x180046a30  xor     r8d, r8d; Reserved
0x180046a33  mov     [rsp+38h+phkResult], rax; lpData
0x180046a38  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x180046a3f  call    cs:__imp_RegSetValueExW
0x180046a45  mov     edi, eax
0x180046a47  mov     rcx, [rsp+38h+hKey]; hKey
0x180046a4c  call    cs:__imp_RegCloseKey
0x180046a52  mov     rbx, [rsp+38h+arg_0]
0x180046a57  mov     eax, edi
0x180046a59  mov     rsi, [rsp+38h+arg_18]
0x180046a5e  add     rsp, 30h
0x180046a62  pop     rdi
0x180046a63  retn
```
