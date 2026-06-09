# I_CryptRecursiveCreateLowIntegrityDirectory

- ea: `0x180003170`
- end: `0x1800031e0`
- name: `I_CryptRecursiveCreateLowIntegrityDirectory`
- size: `112`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001c80`
- `0x1800021e0`
- `0x180002a90`

## callees

- `0x180002df0`
- `0x180003170`
- `0x180003d30`
- `0x1800059b8`
- `0x1800263d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003185`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003185`

## pseudocode

```c
_BOOL8 __fastcall I_CryptRecursiveCreateLowIntegrityDirectory(LPCWSTR lpFileName)
{
  DWORD FileAttributesW; // eax

  FileAttributesW = GetFileAttributesW(lpFileName);
  return (FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 || (unsigned int)I_RecursiveCreateDirectory(lpFileName))
      && ((unsigned int)I_CryptIsAppContainerToken(0)
       || (unsigned int)CheckLowIntegrityDir(lpFileName) && (unsigned int)SetLowIntegrityFile(lpFileName));
}

```

## disassembly

```asm
0x180003170  mov     [rsp+arg_8], rdx
0x180003175  push    rbx
0x180003176  sub     rsp, 20h
0x18000317a  mov     rbx, rcx
0x18000317d  mov     dword ptr [rsp+28h+arg_8], 0
0x180003185  call    cs:__imp_GetFileAttributesW
0x18000318b  cmp     eax, 0FFFFFFFFh
0x18000318e  jz      short loc_1800031BE
0x180003190  test    al, 10h
0x180003192  jz      short loc_1800031BE
0x180003194  xor     ecx, ecx
0x180003196  call    I_CryptIsAppContainerToken
0x18000319b  test    eax, eax
0x18000319d  jnz     short loc_1800031B7
0x18000319f  lea     rdx, [rsp+28h+arg_8]
0x1800031a4  mov     rcx, rbx; lpFileName
0x1800031a7  call    _CheckLowIntegrityDir
0x1800031ac  test    eax, eax
0x1800031ae  jz      short loc_1800031CA
0x1800031b0  cmp     dword ptr [rsp+28h+arg_8], 0
0x1800031b5  jz      short loc_1800031D2
0x1800031b7  mov     eax, 1
0x1800031bc  jmp     short loc_1800031CC
0x1800031be  mov     rcx, rbx; lpFileName
0x1800031c1  call    I_RecursiveCreateDirectory
0x1800031c6  test    eax, eax
0x1800031c8  jnz     short loc_180003194
0x1800031ca  xor     eax, eax
0x1800031cc  add     rsp, 20h
0x1800031d0  pop     rbx
0x1800031d1  retn
0x1800031d2  mov     rcx, rbx; lpFileName
0x1800031d5  call    _SetLowIntegrityFile
0x1800031da  test    eax, eax
0x1800031dc  jz      short loc_1800031CA
0x1800031de  jmp     short loc_1800031B7
```
