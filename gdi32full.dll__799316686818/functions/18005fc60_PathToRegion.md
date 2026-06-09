# PathToRegion

- ea: `0x18005fc60`
- end: `0x18005fcf7`
- name: `PathToRegion`
- size: `151`
- prototype: `HRGN __stdcall(HDC hdc)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180017610`
- `0x180022b1c`
- `0x180026cf0`
- `0x18003baec`
- `0x18005fc60`

## import_xrefs

- `GDI32!pldcGet` at `0x18005fcc6`
- `GDI32!pldcGet` at `0x18005fcc6`
- `GDI32!GdiSetLastError` at `0x18005fcef`
- `GDI32!GdiSetLastError` at `0x18005fcef`
- `win32u!NtGdiPathToRegion` at `0x18005fc7e`
- `win32u!NtGdiPathToRegion` at `0x18005fc7e`

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
0x18005fc60  mov     [rsp+arg_0], rbx
0x18005fc65  push    rdi
0x18005fc66  sub     rsp, 20h
0x18005fc6a  mov     eax, ecx
0x18005fc6c  mov     rbx, rcx
0x18005fc6f  and     eax, 7F0000h
0x18005fc74  cmp     eax, 10000h
0x18005fc79  jnz     short loc_18005FCBB
0x18005fc7b  mov     rcx, rbx
0x18005fc7e  call    cs:__imp_NtGdiPathToRegion
0x18005fc84  mov     rdi, rax
0x18005fc87  test    rax, rax
0x18005fc8a  jnz     short loc_18005FC9F
0x18005fc8c  mov     rcx, rdi
0x18005fc8f  call    GdiTrackHCreate
0x18005fc94  mov     rbx, [rsp+28h+arg_0]
0x18005fc99  add     rsp, 20h
0x18005fc9d  pop     rdi
0x18005fc9e  retn
0x18005fc9f  mov     rcx, rbx; hdc
0x18005fca2  call    GetLayout
0x18005fca7  test    al, 1
0x18005fca9  jz      short loc_18005FC8C
0x18005fcab  xor     r8d, r8d
0x18005fcae  mov     rdx, rdi
0x18005fcb1  mov     rcx, rbx
0x18005fcb4  call    MirrorRgnDC
0x18005fcb9  jmp     short loc_18005FC8C
0x18005fcbb  cmp     eax, 660000h
0x18005fcc0  jnz     short loc_18005FCC6
0x18005fcc2  xor     eax, eax
0x18005fcc4  jmp     short loc_18005FC94
0x18005fcc6  call    cs:__imp_pldcGet
0x18005fccc  test    rax, rax
0x18005fccf  jz      short loc_18005FCEA
0x18005fcd1  cmp     dword ptr [rax+0Ch], 2
0x18005fcd5  jnz     short loc_18005FC7B
0x18005fcd7  mov     edx, 44h ; 'D'
0x18005fcdc  mov     rcx, rbx
0x18005fcdf  call    MF_Record
0x18005fce4  test    eax, eax
0x18005fce6  jnz     short loc_18005FC7B
0x18005fce8  jmp     short loc_18005FCC2
0x18005fcea  mov     ecx, 6
0x18005fcef  call    cs:__imp_GdiSetLastError
0x18005fcf5  jmp     short loc_18005FCC2
```
