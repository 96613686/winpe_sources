# SHFusionLoadLibrary

- ea: `0x14000dabc`
- end: `0x14000db21`
- name: `SHFusionLoadLibrary`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000db28`

## callees

- `0x14000d920`
- `0x14000dabc`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000daf0`
- `KERNEL32!LoadLibraryExW` at `0x14000daf0`
- `KERNEL32!DeactivateActCtx` at `0x14000db0b`
- `KERNEL32!DeactivateActCtx` at `0x14000db0b`

## string_xrefs

- `0x14000dae3`: `comctl32.dll`

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
0x14000dabc  mov     [rsp+ulCookie], rcx
0x14000dac1  push    rbx
0x14000dac2  sub     rsp, 20h
0x14000dac6  lea     rcx, [rsp+28h+ulCookie]
0x14000dacb  mov     [rsp+28h+ulCookie], 0
0x14000dad4  call    SHActivateContext
0x14000dad9  test    eax, eax
0x14000dadb  jnz     short loc_14000DAE1
0x14000dadd  xor     eax, eax
0x14000dadf  jmp     short loc_14000DB1A
0x14000dae1  xor     edx, edx; hFile
0x14000dae3  lea     rcx, aComctl32Dll; "comctl32.dll"
0x14000daea  mov     r8d, 4000h; dwFlags
0x14000daf0  call    cs:__imp_LoadLibraryExW
0x14000daf7  nop     dword ptr [rax+rax+00h]
0x14000dafc  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x14000db01  mov     rbx, rax
0x14000db04  test    rdx, rdx
0x14000db07  jz      short loc_14000DB17
0x14000db09  xor     ecx, ecx; dwFlags
0x14000db0b  call    cs:__imp_DeactivateActCtx
0x14000db12  nop     dword ptr [rax+rax+00h]
0x14000db17  mov     rax, rbx
0x14000db1a  add     rsp, 20h
0x14000db1e  pop     rbx
0x14000db1f  retn
```
