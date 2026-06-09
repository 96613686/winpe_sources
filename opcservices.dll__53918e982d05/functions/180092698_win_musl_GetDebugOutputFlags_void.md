# win_musl::GetDebugOutputFlags(void)

- ea: `0x180092698`
- end: `0x180092755`
- name: `?GetDebugOutputFlags@win_musl@@YAKXZ`
- size: `189`
- prototype: `unsigned int __fastcall(win_musl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800124f4`

## callees

- `0x180092698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009274a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009274a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800926f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800926f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180092723`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180092723`

## string_xrefs

- `0x1800926d9`: `Software\Microsoft\Windows\CurrentVersion\DocumentServices`

## pseudocode

```c
__int64 __fastcall win_musl::GetDebugOutputFlags(win_musl *this)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( !_interlockedbittestandset(&dword_1801C5038, 0x1Eu) )
  {
    hKey = 0;
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\DocumentServices",
            0,
            1u,
            &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"DebugOutputFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
        dword_1801C5038 = Data | 0x40000000;
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)dword_1801C5038;
}

```

## disassembly

```asm
0x180092698  push    rbp
0x18009269a  mov     rbp, rsp
0x18009269d  sub     rsp, 30h
0x1800926a1  lock bts cs:dword_1801C5038, 1Eh
0x1800926aa  jnb     short loc_1800926B8
0x1800926ac  mov     eax, cs:dword_1801C5038
0x1800926b2  add     rsp, 30h
0x1800926b6  pop     rbp
0x1800926b7  retn
0x1800926b8  lea     rax, [rbp+hKey]
0x1800926bc  mov     [rbp+hKey], 0
0x1800926c4  mov     r9d, 1; samDesired
0x1800926ca  mov     [rsp+30h+phkResult], rax; phkResult
0x1800926cf  xor     r8d, r8d; ulOptions
0x1800926d2  mov     [rbp+Data], 0
0x1800926d9  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800926e0  mov     [rbp+cbData], 4
0x1800926e7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800926ee  mov     [rbp+Type], 0
0x1800926f5  call    cs:__imp_RegOpenKeyExW
0x1800926fb  test    eax, eax
0x1800926fd  jnz     short loc_1800926AC
0x1800926ff  mov     rcx, [rbp+hKey]; hKey
0x180092703  lea     rax, [rbp+cbData]
0x180092707  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18009270c  lea     r9, [rbp+Type]; lpType
0x180092710  lea     rax, [rbp+Data]
0x180092714  xor     r8d, r8d; lpReserved
0x180092717  lea     rdx, ValueName; "DebugOutputFlags"
0x18009271e  mov     [rsp+30h+phkResult], rax; lpData
0x180092723  call    cs:__imp_RegQueryValueExW
0x180092729  test    eax, eax
0x18009272b  jnz     short loc_180092746
0x18009272d  cmp     [rbp+Type], 4
0x180092731  jnz     short loc_180092746
0x180092733  cmp     [rbp+cbData], 4
0x180092737  jnz     short loc_180092746
0x180092739  mov     eax, [rbp+Data]
0x18009273c  bts     eax, 1Eh
0x180092740  mov     cs:dword_1801C5038, eax
0x180092746  mov     rcx, [rbp+hKey]; hKey
0x18009274a  call    cs:__imp_RegCloseKey
0x180092750  jmp     loc_1800926AC
```
