# LoadProperSetupDLL

- ea: `0x1005471e0`
- end: `0x10054726d`
- name: `LoadProperSetupDLL`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x100547280`

## callees

- `0x1005471e0`
- `0x1005473c0`
- `0x100548210`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x10054724a`
- `KERNEL32!LoadLibraryExW` at `0x10054724a`
- `KERNEL32!GetSystemDirectoryW` at `0x10054720e`
- `KERNEL32!GetSystemDirectoryW` at `0x10054720e`

## string_xrefs

- `0x100547226`: `\odbccp32.dll`

## pseudocode

```c
HMODULE LoadProperSetupDLL()
{
  UINT SystemDirectoryW; // eax
  WCHAR Buffer[528]; // [rsp+20h] [rbp-438h] BYREF

  Buffer[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x20Au);
  if ( SystemDirectoryW - 1 > 0x208
    || StringCchCopyW(&Buffer[SystemDirectoryW], 522LL - SystemDirectoryW, L"\\odbccp32.dll") < 0 )
  {
    return 0;
  }
  else
  {
    return LoadLibraryExW(Buffer, 0, 0);
  }
}

```

## disassembly

```asm
0x1005471e0  push    rbx
0x1005471e2  sub     rsp, 450h
0x1005471e9  mov     rax, cs:__security_cookie
0x1005471f0  xor     rax, rsp
0x1005471f3  mov     [rsp+458h+var_18], rax
0x1005471fb  xor     eax, eax
0x1005471fd  mov     ebx, 20Ah
0x100547202  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x100547207  mov     edx, ebx; uSize
0x100547209  mov     [rsp+458h+Buffer], ax
0x10054720e  call    cs:__imp_GetSystemDirectoryW
0x100547214  lea     ecx, [rax-1]
0x100547217  cmp     ecx, 208h
0x10054721d  ja      short loc_100547252
0x10054721f  mov     eax, eax
0x100547221  lea     rcx, [rsp+458h+Buffer]
0x100547226  lea     r8, aOdbccp32Dll; "\\odbccp32.dll"
0x10054722d  sub     rbx, rax
0x100547230  lea     rcx, [rcx+rax*2]; pszDest
0x100547234  mov     rdx, rbx; cchDest
0x100547237  call    StringCchCopyW
0x10054723c  test    eax, eax
0x10054723e  js      short loc_100547252
0x100547240  lea     rcx, [rsp+458h+Buffer]; lpLibFileName
0x100547245  xor     r8d, r8d; dwFlags
0x100547248  xor     edx, edx; hFile
0x10054724a  call    cs:__imp_LoadLibraryExW
0x100547250  jmp     short loc_100547254
0x100547252  xor     eax, eax
0x100547254  mov     rcx, [rsp+458h+var_18]
0x10054725c  xor     rcx, rsp; StackCookie
0x10054725f  call    __security_check_cookie
0x100547264  add     rsp, 450h
0x10054726b  pop     rbx
0x10054726c  retn
```
