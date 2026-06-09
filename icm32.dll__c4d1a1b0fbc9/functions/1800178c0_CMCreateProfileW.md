# CMCreateProfileW

- ea: `0x1800178c0`
- end: `0x1800178f0`
- name: `CMCreateProfileW`
- size: `48`
- prototype: `BOOL __stdcall(LPLOGCOLORSPACEW lpColorSpace, LPDEVCHARACTER *lpProfileData)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800178c0`
- `0x1800178f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178e1`

## pseudocode

```c
BOOL __stdcall CMCreateProfileW(LPLOGCOLORSPACEW lpColorSpace, LPDEVCHARACTER *lpProfileData)
{
  DWORD v3; // eax

  if ( lpColorSpace->lcsFilename[0] )
    return 0;
  v3 = MyNewAbstractW(lpColorSpace, lpProfileData);
  if ( v3 )
  {
    SetLastError(v3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800178c0  push    rbx
0x1800178c2  sub     rsp, 20h
0x1800178c6  xor     ebx, ebx
0x1800178c8  cmp     [rcx+44h], bx
0x1800178cc  jz      short loc_1800178D6
0x1800178ce  xor     eax, eax
0x1800178d0  add     rsp, 20h
0x1800178d4  pop     rbx
0x1800178d5  retn
0x1800178d6  call    MyNewAbstractW
0x1800178db  test    eax, eax
0x1800178dd  jz      short loc_1800178E9
0x1800178df  mov     ecx, eax; dwErrCode
0x1800178e1  call    cs:__imp_SetLastError
0x1800178e7  jmp     short loc_1800178CE
0x1800178e9  mov     eax, 1
0x1800178ee  jmp     short loc_1800178D0
```
