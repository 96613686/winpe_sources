# IsWinPEHost(void)

- ea: `0x18000f8b8`
- end: `0x18000f94a`
- name: `?IsWinPEHost@@YAHXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013084`

## callees

- `0x18000f8b8`
- `0x18001029c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f8e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f913`

## string_xrefs

- `0x18000f902`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`
- `0x18000f931`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`

## pseudocode

```c
_BOOL8 IsWinPEHost(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 != 2 )
      Logger::TraceVerbose(
        L"%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.",
        L"IsWinPEHost",
        L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT",
        v0);
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Successfully opened reg key %s. Assuming the host is WinPE.",
      L"IsWinPEHost",
      L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT");
    RegCloseKey(hKey);
  }
  return v1 == 0;
}

```

## disassembly

```asm
0x18000f8b8  push    rbx
0x18000f8ba  sub     rsp, 30h
0x18000f8be  lea     rax, [rsp+38h+hKey]
0x18000f8c3  mov     [rsp+38h+hKey], 0
0x18000f8cc  mov     r9d, 20019h; samDesired
0x18000f8d2  mov     [rsp+38h+phkResult], rax; phkResult
0x18000f8d7  xor     r8d, r8d; ulOptions
0x18000f8da  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x18000f8e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f8e8  call    cs:__imp_RegOpenKeyExW
0x18000f8ee  mov     ebx, eax
0x18000f8f0  test    eax, eax
0x18000f8f2  jnz     short loc_18000F91B
0x18000f8f4  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18000f8fb  lea     rdx, aIswinpehost; "IsWinPEHost"
0x18000f902  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x18000f909  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000f90e  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f913  call    cs:__imp_RegCloseKey
0x18000f919  jmp     short loc_18000F93D
0x18000f91b  cmp     ebx, 2
0x18000f91e  jz      short loc_18000F93D
0x18000f920  mov     r9d, ebx
0x18000f923  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18000f92a  lea     rdx, aIswinpehost; "IsWinPEHost"
0x18000f931  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open reg key %s. Assuming th"...
0x18000f938  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000f93d  xor     eax, eax
0x18000f93f  test    ebx, ebx
0x18000f941  setz    al
0x18000f944  add     rsp, 30h
0x18000f948  pop     rbx
0x18000f949  retn
```
