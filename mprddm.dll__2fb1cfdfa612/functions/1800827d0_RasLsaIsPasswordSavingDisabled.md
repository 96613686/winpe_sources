# RasLsaIsPasswordSavingDisabled

- ea: `0x1800827d0`
- end: `0x18008287b`
- name: `RasLsaIsPasswordSavingDisabled`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180082b60`

## callees

- `0x1800827d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180082858`
- `ADVAPI32!RegCloseKey` at `0x180082858`
- `ADVAPI32!RegOpenKeyExA` at `0x180082817`
- `ADVAPI32!RegOpenKeyExA` at `0x180082817`
- `ADVAPI32!RegQueryValueExA` at `0x18008284c`
- `ADVAPI32!RegQueryValueExA` at `0x18008284c`

## string_xrefs

- `0x1800827fb`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
_BOOL8 RasLsaIsPasswordSavingDisabled()
{
  LSTATUS v0; // ebx
  _BOOL8 result; // rax
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  result = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    v0 = RegQueryValueExA(hKey, "DisableSavePassword", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( !v0 && Type == 4 && Data )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800827d0  push    rbp
0x1800827d2  push    rbx
0x1800827d3  mov     rbp, rsp
0x1800827d6  sub     rsp, 38h
0x1800827da  lea     rax, [rbp+hKey]
0x1800827de  mov     [rbp+hKey], 0
0x1800827e6  mov     r9d, 20019h; samDesired
0x1800827ec  mov     [rsp+38h+phkResult], rax; phkResult
0x1800827f1  xor     r8d, r8d; ulOptions
0x1800827f4  mov     [rbp+Type], 0
0x1800827fb  lea     rdx, aSystemCurrentc_22; "System\\CurrentControlSet\\Services\\Ra"...
0x180082802  mov     [rbp+Data], 0
0x180082809  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180082810  mov     [rbp+cbData], 0
0x180082817  call    cs:__imp_RegOpenKeyExA
0x18008281d  test    eax, eax
0x18008281f  jnz     short loc_180082872
0x180082821  mov     rcx, [rbp+hKey]; hKey
0x180082825  lea     rax, [rbp+cbData]
0x180082829  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18008282e  lea     r9, [rbp+Type]; lpType
0x180082832  lea     rax, [rbp+Data]
0x180082836  mov     [rbp+cbData], 4
0x18008283d  xor     r8d, r8d; lpReserved
0x180082840  mov     [rsp+38h+phkResult], rax; lpData
0x180082845  lea     rdx, aDisablesavepas; "DisableSavePassword"
0x18008284c  call    cs:__imp_RegQueryValueExA
0x180082852  mov     rcx, [rbp+hKey]; hKey
0x180082856  mov     ebx, eax
0x180082858  call    cs:__imp_RegCloseKey
0x18008285e  test    ebx, ebx
0x180082860  jnz     short loc_180082872
0x180082862  cmp     [rbp+Type], 4
0x180082866  jnz     short loc_180082872
0x180082868  cmp     [rbp+Data], ebx
0x18008286b  jz      short loc_180082872
0x18008286d  lea     eax, [rbx+1]
0x180082870  jmp     short loc_180082874
0x180082872  xor     eax, eax
0x180082874  add     rsp, 38h
0x180082878  pop     rbx
0x180082879  pop     rbp
0x18008287a  retn
```
