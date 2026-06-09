# IsWinPEHost(void)

- ea: `0x180022fcc`
- end: `0x18002305e`
- name: `?IsWinPEHost@@YAHXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180077838`

## callees

- `0x180022fcc`
- `0x18002cb48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023027`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023027`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022ffc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022ffc`

## string_xrefs

- `0x180023016`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`
- `0x180023045`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`

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
0x180022fcc  push    rbx
0x180022fce  sub     rsp, 30h
0x180022fd2  lea     rax, [rsp+38h+hKey]
0x180022fd7  mov     [rsp+38h+hKey], 0
0x180022fe0  mov     r9d, 20019h; samDesired
0x180022fe6  mov     [rsp+38h+phkResult], rax; phkResult
0x180022feb  xor     r8d, r8d; ulOptions
0x180022fee  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180022ff5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022ffc  call    cs:__imp_RegOpenKeyExW
0x180023002  mov     ebx, eax
0x180023004  test    eax, eax
0x180023006  jnz     short loc_18002302F
0x180023008  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18002300f  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180023016  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x18002301d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180023022  mov     rcx, [rsp+38h+hKey]; hKey
0x180023027  call    cs:__imp_RegCloseKey
0x18002302d  jmp     short loc_180023051
0x18002302f  cmp     ebx, 2
0x180023032  jz      short loc_180023051
0x180023034  mov     r9d, ebx
0x180023037  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18002303e  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180023045  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open reg key %s. Assuming th"...
0x18002304c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180023051  xor     eax, eax
0x180023053  test    ebx, ebx
0x180023055  setz    al
0x180023058  add     rsp, 30h
0x18002305c  pop     rbx
0x18002305d  retn
```
