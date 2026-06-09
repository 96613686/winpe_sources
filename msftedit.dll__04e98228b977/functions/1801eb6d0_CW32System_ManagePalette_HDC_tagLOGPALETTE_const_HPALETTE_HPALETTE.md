# CW32System::ManagePalette(HDC__ *,tagLOGPALETTE const *,HPALETTE__ * &,HPALETTE__ * &)

- ea: `0x1801eb6d0`
- end: `0x1801eb759`
- name: `?ManagePalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEBUtagLOGPALETTE@@AEAPEAU2@2@Z`
- size: `137`
- prototype: `HPALETTE __fastcall(HDC, LOGPALETTE *plpal, HPALETTE *, HPALETTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a7a1c`

## callees

- `0x1801eb6d0`
- `0x1801eb760`
- `0x1801eb774`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!CreatePalette` at `0x1801eb6f1`
- `ext-ms-win-gdi-dc-l1-2-0!CreatePalette` at `0x1801eb6f1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801eb733`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801eb733`

## pseudocode

```c
HPALETTE __fastcall CW32System::ManagePalette(HDC a1, LOGPALETTE *plpal, HPALETTE *a3, HPALETTE *a4)
{
  HPALETTE Palette; // rax
  int v8; // r8d

  if ( *a4 )
  {
    CW32System::SelectPalette(a1, *a3, (int)a3);
    CW32System::RealizePalette(a1);
    DeleteObject(*a4);
    *a4 = 0;
  }
  else
  {
    Palette = CreatePalette(plpal);
    *a4 = Palette;
    if ( Palette )
    {
      *a3 = CW32System::SelectPalette(a1, Palette, v8);
      CW32System::RealizePalette(a1);
      return *a4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801eb6d0  mov     [rsp+arg_0], rbx
0x1801eb6d5  mov     [rsp+arg_8], rsi
0x1801eb6da  push    rdi
0x1801eb6db  sub     rsp, 20h
0x1801eb6df  cmp     qword ptr [r9], 0
0x1801eb6e3  mov     rbx, r9
0x1801eb6e6  mov     rsi, r8
0x1801eb6e9  mov     rdi, rcx
0x1801eb6ec  jnz     short loc_1801EB720
0x1801eb6ee  mov     rcx, rdx; plpal
0x1801eb6f1  call    cs:__imp_CreatePalette
0x1801eb6f8  nop     dword ptr [rax+rax+00h]
0x1801eb6fd  mov     [rbx], rax
0x1801eb700  test    rax, rax
0x1801eb703  jz      short loc_1801EB746
0x1801eb705  mov     rdx, rax; HPALETTE
0x1801eb708  mov     rcx, rdi; HDC
0x1801eb70b  call    ?SelectPalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAU2@H@Z; CW32System::SelectPalette(HDC__ *,HPALETTE__ *,int)
0x1801eb710  mov     rcx, rdi; HDC
0x1801eb713  mov     [rsi], rax
0x1801eb716  call    ?RealizePalette@CW32System@@SAIPEAUHDC__@@@Z; CW32System::RealizePalette(HDC__ *)
0x1801eb71b  mov     rax, [rbx]
0x1801eb71e  jmp     short loc_1801EB748
0x1801eb720  mov     rdx, [r8]; HPALETTE
0x1801eb723  call    ?SelectPalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAU2@H@Z; CW32System::SelectPalette(HDC__ *,HPALETTE__ *,int)
0x1801eb728  mov     rcx, rdi; HDC
0x1801eb72b  call    ?RealizePalette@CW32System@@SAIPEAUHDC__@@@Z; CW32System::RealizePalette(HDC__ *)
0x1801eb730  mov     rcx, [rbx]; ho
0x1801eb733  call    cs:__imp_DeleteObject
0x1801eb73a  nop     dword ptr [rax+rax+00h]
0x1801eb73f  mov     qword ptr [rbx], 0
0x1801eb746  xor     eax, eax
0x1801eb748  mov     rbx, [rsp+28h+arg_0]
0x1801eb74d  mov     rsi, [rsp+28h+arg_8]
0x1801eb752  add     rsp, 20h
0x1801eb756  pop     rdi
0x1801eb757  retn
```
