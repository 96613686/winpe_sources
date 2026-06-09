# RasLsaIsPasswordSavingDisabled

- ea: `0x18008842c`
- end: `0x1800884dd`
- name: `RasLsaIsPasswordSavingDisabled`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180088810`

## callees

- `0x18008842c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800884b0`
- `ADVAPI32!RegCloseKey` at `0x1800884b0`
- `ADVAPI32!RegOpenKeyExA` at `0x180088463`
- `ADVAPI32!RegOpenKeyExA` at `0x180088463`
- `ADVAPI32!RegQueryValueExA` at `0x18008849e`
- `ADVAPI32!RegQueryValueExA` at `0x18008849e`

## string_xrefs

- `0x18008844d`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
__int64 RasLsaIsPasswordSavingDisabled()
{
  unsigned int v0; // edi
  LSTATUS v1; // ebx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 0x20019u, &hKey) )
    return 0;
  cbData = 4;
  v1 = RegQueryValueExA(hKey, "DisableSavePassword", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( v1 )
    return 0;
  if ( Type == 4 )
    return Data != 0;
  return v0;
}

```

## disassembly

```asm
0x18008842c  push    rbp
0x18008842e  push    rbx
0x18008842f  push    rdi
0x180088430  mov     rbp, rsp
0x180088433  sub     rsp, 30h
0x180088437  xor     edi, edi
0x180088439  lea     rax, [rbp+hKey]
0x18008843d  mov     r9d, 20019h; samDesired
0x180088443  mov     [rbp+hKey], rdi
0x180088447  xor     r8d, r8d; ulOptions
0x18008844a  mov     [rbp+Type], edi
0x18008844d  lea     rdx, aSystemCurrentc_22; "System\\CurrentControlSet\\Services\\Ra"...
0x180088454  mov     [rbp+Data], edi
0x180088457  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008845e  mov     [rsp+30h+phkResult], rax; phkResult
0x180088463  call    cs:__imp_RegOpenKeyExA
0x18008846a  nop     dword ptr [rax+rax+00h]
0x18008846f  test    eax, eax
0x180088471  jnz     short loc_1800884D2
0x180088473  mov     rcx, [rbp+hKey]; hKey
0x180088477  lea     rax, [rbp+cbData]
0x18008847b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180088480  lea     r9, [rbp+Type]; lpType
0x180088484  lea     rax, [rbp+Data]
0x180088488  mov     [rbp+cbData], 4
0x18008848f  xor     r8d, r8d; lpReserved
0x180088492  mov     [rsp+30h+phkResult], rax; lpData
0x180088497  lea     rdx, aDisablesavepas; "DisableSavePassword"
0x18008849e  call    cs:__imp_RegQueryValueExA
0x1800884a5  nop     dword ptr [rax+rax+00h]
0x1800884aa  mov     rcx, [rbp+hKey]; hKey
0x1800884ae  mov     ebx, eax
0x1800884b0  call    cs:__imp_RegCloseKey
0x1800884b7  nop     dword ptr [rax+rax+00h]
0x1800884bc  test    ebx, ebx
0x1800884be  jnz     short loc_1800884D2
0x1800884c0  cmp     [rbp+Type], 4
0x1800884c4  jnz     short loc_1800884CE
0x1800884c6  cmp     [rbp+Data], edi
0x1800884c9  jz      short loc_1800884CE
0x1800884cb  lea     edi, [rbx+1]
0x1800884ce  mov     eax, edi
0x1800884d0  jmp     short loc_1800884D4
0x1800884d2  xor     eax, eax
0x1800884d4  add     rsp, 30h
0x1800884d8  pop     rdi
0x1800884d9  pop     rbx
0x1800884da  pop     rbp
0x1800884db  retn
```
