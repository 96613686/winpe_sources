# SHFusionLoadLibrary

- ea: `0x1800267d8`
- end: `0x180026830`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026dc4`

## callees

- `0x1800265cc`
- `0x1800267d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002680c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002680c`
- `KERNEL32!DeactivateActCtx` at `0x180026821`
- `KERNEL32!DeactivateActCtx` at `0x180026821`

## string_xrefs

- `0x1800267ff`: `comctl32.dll`

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
0x1800267d8  mov     [rsp+ulCookie], rcx
0x1800267dd  push    rbx
0x1800267de  sub     rsp, 20h
0x1800267e2  lea     rcx, [rsp+28h+ulCookie]
0x1800267e7  mov     [rsp+28h+ulCookie], 0
0x1800267f0  call    SHActivateContext
0x1800267f5  test    eax, eax
0x1800267f7  jnz     short loc_1800267FD
0x1800267f9  xor     eax, eax
0x1800267fb  jmp     short loc_18002682A
0x1800267fd  xor     edx, edx; hFile
0x1800267ff  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180026806  mov     r8d, 4000h; dwFlags
0x18002680c  call    cs:__imp_LoadLibraryExW
0x180026812  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180026817  mov     rbx, rax
0x18002681a  test    rdx, rdx
0x18002681d  jz      short loc_180026827
0x18002681f  xor     ecx, ecx; dwFlags
0x180026821  call    cs:__imp_DeactivateActCtx
0x180026827  mov     rax, rbx
0x18002682a  add     rsp, 20h
0x18002682e  pop     rbx
0x18002682f  retn
```
