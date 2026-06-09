# CreateBIPalette(tagBITMAPINFOHEADER *)

- ea: `0x18001d5bc`
- end: `0x18001d631`
- name: `?CreateBIPalette@@YAPEAUHPALETTE__@@PEAUtagBITMAPINFOHEADER@@@Z`
- size: `117`
- prototype: `HPALETTE __fastcall(struct tagBITMAPINFOHEADER *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cab4`

## callees

- `0x18001d5bc`

## import_xrefs

- `msvcrt!malloc` at `0x18001d5ce`
- `msvcrt!malloc` at `0x18001d5ce`
- `msvcrt!free` at `0x18001d61d`
- `msvcrt!free` at `0x18001d61d`
- `GDI32!CreatePalette` at `0x18001d611`
- `GDI32!CreatePalette` at `0x18001d611`

## pseudocode

```c
HPALETTE __fastcall CreateBIPalette(struct tagBITMAPINFOHEADER *a1)
{
  LOGPALETTE *v2; // rax
  char *v3; // rcx
  LOGPALETTE *v4; // rdi
  __int64 v5; // rdx
  HPALETTE Palette; // rbx

  v2 = (LOGPALETTE *)malloc(0x408u);
  v3 = (char *)a1 + a1->biSize;
  v4 = v2;
  v5 = 0;
  *(_DWORD *)&v2->palVersion = 16777984;
  do
  {
    v2->palPalEntry[v5].peRed = v3[4 * v5 + 2];
    v2->palPalEntry[v5].peGreen = v3[4 * v5 + 1];
    v2->palPalEntry[v5].peBlue = v3[4 * v5];
    v2->palPalEntry[v5++].peFlags = 0;
  }
  while ( v5 != 256 );
  Palette = CreatePalette(v2);
  free(v4);
  return Palette;
}

```

## disassembly

```asm
0x18001d5bc  mov     [rsp+arg_0], rbx
0x18001d5c1  push    rdi
0x18001d5c2  sub     rsp, 20h
0x18001d5c6  mov     rbx, rcx
0x18001d5c9  mov     ecx, 408h; Size
0x18001d5ce  call    cs:__imp_malloc
0x18001d5d4  mov     ecx, [rbx]
0x18001d5d6  mov     r8d, 100h
0x18001d5dc  add     rcx, rbx
0x18001d5df  mov     rdi, rax
0x18001d5e2  xor     edx, edx
0x18001d5e4  mov     dword ptr [rax], 1000300h
0x18001d5ea  mov     al, [rcx+rdx*4+2]
0x18001d5ee  mov     [rdi+rdx*4+4], al
0x18001d5f2  mov     al, [rcx+rdx*4+1]
0x18001d5f6  mov     [rdi+rdx*4+5], al
0x18001d5fa  mov     al, [rcx+rdx*4]
0x18001d5fd  mov     [rdi+rdx*4+6], al
0x18001d601  mov     byte ptr [rdi+rdx*4+7], 0
0x18001d606  inc     rdx
0x18001d609  cmp     rdx, r8
0x18001d60c  jnz     short loc_18001D5EA
0x18001d60e  mov     rcx, rdi; plpal
0x18001d611  call    cs:__imp_CreatePalette
0x18001d617  mov     rcx, rdi; Block
0x18001d61a  mov     rbx, rax
0x18001d61d  call    cs:__imp_free
0x18001d623  mov     rax, rbx
0x18001d626  mov     rbx, [rsp+28h+arg_0]
0x18001d62b  add     rsp, 20h
0x18001d62f  pop     rdi
0x18001d630  retn
```
