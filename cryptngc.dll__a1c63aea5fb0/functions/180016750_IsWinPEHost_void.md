# IsWinPEHost(void)

- ea: `0x180016750`
- end: `0x1800167ef`
- name: `?IsWinPEHost@@YAHXZ`
- size: `159`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002bcdc`

## callees

- `0x1800073c0`
- `0x180016750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800167bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800167bd`

## string_xrefs

- `0x1800167ac`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`
- `0x1800167e1`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    return v1 == 0;
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Successfully opened reg key %s. Assuming the host is WinPE.",
      L"IsWinPEHost",
      L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT");
    RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x180016750  push    rbx
0x180016752  sub     rsp, 30h
0x180016756  lea     rax, [rsp+38h+hKey]
0x18001675b  mov     [rsp+38h+hKey], 0
0x180016764  mov     r9d, 20019h; samDesired
0x18001676a  mov     [rsp+38h+phkResult], rax; phkResult
0x18001676f  xor     r8d, r8d; ulOptions
0x180016772  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180016779  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016780  call    cs:__imp_RegOpenKeyExW
0x180016786  mov     ebx, eax
0x180016788  test    eax, eax
0x18001678a  jz      short loc_18001679E
0x18001678c  cmp     eax, 2
0x18001678f  jnz     short loc_1800167D0
0x180016791  xor     eax, eax
0x180016793  test    ebx, ebx
0x180016795  setz    al
0x180016798  add     rsp, 30h
0x18001679c  pop     rbx
0x18001679d  retn
0x18001679e  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x1800167a5  lea     rdx, aIswinpehost; "IsWinPEHost"
0x1800167ac  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x1800167b3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800167b8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800167bd  call    cs:__imp_RegCloseKey
0x1800167c3  xor     eax, eax
0x1800167c5  test    ebx, ebx
0x1800167c7  setz    al
0x1800167ca  add     rsp, 30h
0x1800167ce  pop     rbx
0x1800167cf  retn
0x1800167d0  mov     r9d, ebx
0x1800167d3  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x1800167da  lea     rdx, aIswinpehost; "IsWinPEHost"
0x1800167e1  lea     rcx, aSCannotOpenReg_3; "%s: Cannot open reg key %s. Assuming th"...
0x1800167e8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800167ed  jmp     short loc_180016791
```
