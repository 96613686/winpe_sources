# IsWinPEHost(void)

- ea: `0x180025b2c`
- end: `0x180025bcb`
- name: `?IsWinPEHost@@YAHXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18007cc34`

## callees

- `0x180025b2c`
- `0x18002f048`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025b8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025b8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025b5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025b5c`

## string_xrefs

- `0x180025b7c`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`
- `0x180025bb1`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`

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
0x180025b2c  push    rbx
0x180025b2e  sub     rsp, 30h
0x180025b32  lea     rax, [rsp+38h+hKey]
0x180025b37  mov     [rsp+38h+hKey], 0
0x180025b40  mov     r9d, 20019h; samDesired
0x180025b46  mov     [rsp+38h+phkResult], rax; phkResult
0x180025b4b  xor     r8d, r8d; ulOptions
0x180025b4e  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180025b55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025b5c  call    cs:__imp_RegOpenKeyExW
0x180025b63  nop     dword ptr [rax+rax+00h]
0x180025b68  mov     ebx, eax
0x180025b6a  test    eax, eax
0x180025b6c  jnz     short loc_180025B9B
0x180025b6e  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x180025b75  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180025b7c  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x180025b83  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180025b88  mov     rcx, [rsp+38h+hKey]; hKey
0x180025b8d  call    cs:__imp_RegCloseKey
0x180025b94  nop     dword ptr [rax+rax+00h]
0x180025b99  jmp     short loc_180025BBD
0x180025b9b  cmp     ebx, 2
0x180025b9e  jz      short loc_180025BBD
0x180025ba0  mov     r9d, ebx
0x180025ba3  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x180025baa  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180025bb1  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open reg key %s. Assuming th"...
0x180025bb8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180025bbd  xor     eax, eax
0x180025bbf  test    ebx, ebx
0x180025bc1  setz    al
0x180025bc4  add     rsp, 30h
0x180025bc8  pop     rbx
0x180025bc9  retn
```
