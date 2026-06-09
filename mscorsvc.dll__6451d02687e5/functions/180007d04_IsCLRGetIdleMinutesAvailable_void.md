# IsCLRGetIdleMinutesAvailable(void)

- ea: `0x180007d04`
- end: `0x180007d54`
- name: `?IsCLRGetIdleMinutesAvailable@@YA_NXZ`
- size: `80`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180007050`

## callees

- `0x180007d04`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007d1d`
- `KERNEL32!LoadLibraryExW` at `0x180007d1d`
- `KERNEL32!GetProcAddress` at `0x180007d30`
- `KERNEL32!GetProcAddress` at `0x180007d30`

## string_xrefs

- `0x180007d14`: `msidle.dll`

## pseudocode

```c
bool IsCLRGetIdleMinutesAvailable(void)
{
  HMODULE Library; // rax

  if ( !bGetIdleMinutesProbed )
  {
    Library = LoadLibraryExW(L"msidle.dll", 0, 0);
    if ( Library )
      qword_18006FF50 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(Library, (LPCSTR)8);
    bGetIdleMinutesProbed = 1;
  }
  return qword_18006FF50 != 0;
}

```

## disassembly

```asm
0x180007d04  sub     rsp, 28h
0x180007d08  cmp     cs:?bGetIdleMinutesProbed@@3_NA, 0; bool bGetIdleMinutesProbed
0x180007d0f  jnz     short loc_180007D44
0x180007d11  xor     r8d, r8d; dwFlags
0x180007d14  lea     rcx, aMsidleDll; "msidle.dll"
0x180007d1b  xor     edx, edx; hFile
0x180007d1d  call    cs:__imp_LoadLibraryExW
0x180007d23  test    rax, rax
0x180007d26  jz      short loc_180007D3D
0x180007d28  mov     edx, 8; lpProcName
0x180007d2d  mov     rcx, rax; hModule
0x180007d30  call    cs:__imp_GetProcAddress
0x180007d36  mov     cs:qword_18006FF50, rax
0x180007d3d  mov     cs:?bGetIdleMinutesProbed@@3_NA, 1; bool bGetIdleMinutesProbed
0x180007d44  cmp     cs:qword_18006FF50, 0
0x180007d4c  setnz   al
0x180007d4f  add     rsp, 28h
0x180007d53  retn
```
