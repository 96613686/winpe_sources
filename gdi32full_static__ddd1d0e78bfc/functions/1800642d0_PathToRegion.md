# PathToRegion

- ea: `0x1800642d0`
- end: `0x18006437a`
- name: `PathToRegion`
- size: `170`
- prototype: `HRGN __stdcall(HDC hdc)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000e3e0`
- `0x18002b9ec`
- `0x18002fda0`
- `0x1800473e4`
- `0x1800642d0`

## import_xrefs

- `GDI32!pldcGet` at `0x18006433d`
- `GDI32!pldcGet` at `0x18006433d`
- `GDI32!GdiSetLastError` at `0x18006436c`
- `GDI32!GdiSetLastError` at `0x18006436c`
- `win32u!NtGdiPathToRegion` at `0x1800642ee`
- `win32u!NtGdiPathToRegion` at `0x1800642ee`

## pseudocode

```c
HRGN __stdcall PathToRegion(HDC hdc)
{
  const BITMAPINFOHEADER *v2; // rdx
  HDC v3; // rdi
  DWORD v4; // r8d
  const void *v5; // r9
  __int64 v7; // rax

  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
    goto LABEL_2;
  if ( ((unsigned int)hdc & 0x7F0000) == 0x660000 )
    return 0;
  v7 = pldcGet(hdc);
  if ( !v7 )
  {
    GdiSetLastError(6);
    return 0;
  }
  if ( *(_DWORD *)(v7 + 12) == 2 && !(unsigned int)MF_Record(hdc, 68) )
    return 0;
LABEL_2:
  v3 = (HDC)NtGdiPathToRegion(hdc);
  if ( v3 )
  {
    if ( (GetLayout(hdc) & 1) != 0 )
      MirrorRgnDC(hdc, v3, 0);
  }
  return (HRGN)GdiTrackHCreate(v3, v2, v4, v5);
}

```

## disassembly

```asm
0x1800642d0  mov     [rsp+arg_0], rbx
0x1800642d5  push    rdi
0x1800642d6  sub     rsp, 20h
0x1800642da  mov     eax, ecx
0x1800642dc  mov     rbx, rcx
0x1800642df  and     eax, 7F0000h
0x1800642e4  cmp     eax, 10000h
0x1800642e9  jnz     short loc_180064332
0x1800642eb  mov     rcx, rbx
0x1800642ee  call    cs:__imp_NtGdiPathToRegion
0x1800642f5  nop     dword ptr [rax+rax+00h]
0x1800642fa  mov     rdi, rax
0x1800642fd  test    rax, rax
0x180064300  jnz     short loc_180064316
0x180064302  mov     rcx, rdi
0x180064305  call    GdiTrackHCreate
0x18006430a  mov     rbx, [rsp+28h+arg_0]
0x18006430f  add     rsp, 20h
0x180064313  pop     rdi
0x180064314  retn
0x180064316  mov     rcx, rbx; hdc
0x180064319  call    GetLayout
0x18006431e  test    al, 1
0x180064320  jz      short loc_180064302
0x180064322  xor     r8d, r8d
0x180064325  mov     rdx, rdi
0x180064328  mov     rcx, rbx
0x18006432b  call    MirrorRgnDC
0x180064330  jmp     short loc_180064302
0x180064332  cmp     eax, 660000h
0x180064337  jnz     short loc_18006433D
0x180064339  xor     eax, eax
0x18006433b  jmp     short loc_18006430A
0x18006433d  call    cs:__imp_pldcGet
0x180064344  nop     dword ptr [rax+rax+00h]
0x180064349  test    rax, rax
0x18006434c  jz      short loc_180064367
0x18006434e  cmp     dword ptr [rax+0Ch], 2
0x180064352  jnz     short loc_1800642EB
0x180064354  mov     edx, 44h ; 'D'
0x180064359  mov     rcx, rbx
0x18006435c  call    MF_Record
0x180064361  test    eax, eax
0x180064363  jnz     short loc_1800642EB
0x180064365  jmp     short loc_180064339
0x180064367  mov     ecx, 6
0x18006436c  call    cs:__imp_GdiSetLastError
0x180064373  nop     dword ptr [rax+rax+00h]
0x180064378  jmp     short loc_180064339
```
