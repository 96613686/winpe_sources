# DownloadAndInstallOptionalFontsAsync(void)

- ea: `0x18002a110`
- end: `0x18002a140`
- name: `?DownloadAndInstallOptionalFontsAsync@@YAXXZ`
- size: `48`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016ff0`

## callees

- `0x18002a110`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18002a135`
- `SHLWAPI!__imp_SHCreateThread` at `0x18002a135`

## pseudocode

```c
void DownloadAndInstallOptionalFontsAsync(void)
{
  if ( !_InterlockedCompareExchange(&dword_180047060, 1, 0) )
    SHCreateThread(DownloadAndInstallOptionalFontsThreadEntry, 0, 0x1Cu, 0);
}

```

## disassembly

```asm
0x18002a110  sub     rsp, 28h
0x18002a114  mov     ecx, 1
0x18002a119  xor     eax, eax
0x18002a11b  lock cmpxchg cs:dword_180047060, ecx
0x18002a123  jnz     short loc_18002A13B
0x18002a125  lea     r8d, [rcx+1Bh]; flags
0x18002a129  xor     r9d, r9d; pfnCallback
0x18002a12c  lea     rcx, ?DownloadAndInstallOptionalFontsThreadEntry@@YAKPEAX@Z; pfnThreadProc
0x18002a133  xor     edx, edx; pData
0x18002a135  call    cs:__imp_SHCreateThread
0x18002a13b  add     rsp, 28h
0x18002a13f  retn
```
