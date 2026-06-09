# SHFusionLoadLibrary

- ea: `0x18000fa14`
- end: `0x18000fa6c`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fa74`

## callees

- `0x18000f898`
- `0x18000fa14`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000fa48`
- `KERNEL32!LoadLibraryExW` at `0x18000fa48`
- `KERNEL32!DeactivateActCtx` at `0x18000fa5d`
- `KERNEL32!DeactivateActCtx` at `0x18000fa5d`

## string_xrefs

- `0x18000fa3b`: `comctl32.dll`

## pseudocode

```c
HMODULE SHFusionLoadLibrary()
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18000fa14  mov     [rsp+ulCookie], rcx
0x18000fa19  push    rbx
0x18000fa1a  sub     rsp, 20h
0x18000fa1e  lea     rcx, [rsp+28h+ulCookie]
0x18000fa23  mov     [rsp+28h+ulCookie], 0
0x18000fa2c  call    SHActivateContext
0x18000fa31  test    eax, eax
0x18000fa33  jnz     short loc_18000FA39
0x18000fa35  xor     eax, eax
0x18000fa37  jmp     short loc_18000FA66
0x18000fa39  xor     edx, edx; hFile
0x18000fa3b  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18000fa42  mov     r8d, 4000h; dwFlags
0x18000fa48  call    cs:__imp_LoadLibraryExW
0x18000fa4e  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18000fa53  mov     rbx, rax
0x18000fa56  test    rdx, rdx
0x18000fa59  jz      short loc_18000FA63
0x18000fa5b  xor     ecx, ecx; dwFlags
0x18000fa5d  call    cs:__imp_DeactivateActCtx
0x18000fa63  mov     rax, rbx
0x18000fa66  add     rsp, 20h
0x18000fa6a  pop     rbx
0x18000fa6b  retn
```
