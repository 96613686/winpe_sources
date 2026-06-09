# IsCLRWldpGetLockdownPolicyAvailable(void)

- ea: `0x180008488`
- end: `0x1800084da`
- name: `?IsCLRWldpGetLockdownPolicyAvailable@@YA_NXZ`
- size: `82`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f454`

## callees

- `0x180008488`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800084a1`
- `KERNEL32!LoadLibraryExW` at `0x1800084a1`
- `KERNEL32!GetProcAddress` at `0x1800084b6`
- `KERNEL32!GetProcAddress` at `0x1800084b6`

## string_xrefs

- `0x180008498`: `wldp.dll`

## pseudocode

```c
bool IsCLRWldpGetLockdownPolicyAvailable(void)
{
  HMODULE Library; // rax

  if ( !bWldpGetLockdownPolicyProbed )
  {
    Library = LoadLibraryExW(L"wldp.dll", 0, 0);
    if ( Library )
      qword_18006FFF8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(Library, "WldpGetLockdownPolicy");
    bWldpGetLockdownPolicyProbed = 1;
  }
  return qword_18006FFF8 != 0;
}

```

## disassembly

```asm
0x180008488  sub     rsp, 28h
0x18000848c  cmp     cs:?bWldpGetLockdownPolicyProbed@@3_NA, 0; bool bWldpGetLockdownPolicyProbed
0x180008493  jnz     short loc_1800084CA
0x180008495  xor     r8d, r8d; dwFlags
0x180008498  lea     rcx, aWldpDll; "wldp.dll"
0x18000849f  xor     edx, edx; hFile
0x1800084a1  call    cs:__imp_LoadLibraryExW
0x1800084a7  test    rax, rax
0x1800084aa  jz      short loc_1800084C3
0x1800084ac  lea     rdx, aWldpgetlockdow; "WldpGetLockdownPolicy"
0x1800084b3  mov     rcx, rax; hModule
0x1800084b6  call    cs:__imp_GetProcAddress
0x1800084bc  mov     cs:qword_18006FFF8, rax
0x1800084c3  mov     cs:?bWldpGetLockdownPolicyProbed@@3_NA, 1; bool bWldpGetLockdownPolicyProbed
0x1800084ca  cmp     cs:qword_18006FFF8, 0
0x1800084d2  setnz   al
0x1800084d5  add     rsp, 28h
0x1800084d9  retn
```
