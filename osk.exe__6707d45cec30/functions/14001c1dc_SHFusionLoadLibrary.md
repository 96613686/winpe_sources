# SHFusionLoadLibrary

- ea: `0x14001c1dc`
- end: `0x14001c22c`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c234`

## callees

- `0x14001bf00`
- `0x14001bf68`
- `0x14001c1dc`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14001c210`
- `KERNEL32!LoadLibraryExW` at `0x14001c210`

## string_xrefs

- `0x14001c203`: `comctl32.dll`

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
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x14001c1dc  mov     [rsp+ulCookie], rcx
0x14001c1e1  push    rbx
0x14001c1e2  sub     rsp, 20h
0x14001c1e6  lea     rcx, [rsp+28h+ulCookie]
0x14001c1eb  mov     [rsp+28h+ulCookie], 0
0x14001c1f4  call    SHActivateContext
0x14001c1f9  test    eax, eax
0x14001c1fb  jnz     short loc_14001C201
0x14001c1fd  xor     eax, eax
0x14001c1ff  jmp     short loc_14001C226
0x14001c201  xor     edx, edx; hFile
0x14001c203  lea     rcx, aComctl32Dll; "comctl32.dll"
0x14001c20a  mov     r8d, 4000h; dwFlags
0x14001c210  call    cs:__imp_LoadLibraryExW
0x14001c216  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x14001c21b  mov     rbx, rax
0x14001c21e  call    SHDeactivateContext
0x14001c223  mov     rax, rbx
0x14001c226  add     rsp, 20h
0x14001c22a  pop     rbx
0x14001c22b  retn
```
