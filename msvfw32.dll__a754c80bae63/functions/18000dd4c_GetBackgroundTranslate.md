# GetBackgroundTranslate

- ea: `0x18000dd4c`
- end: `0x18000ddf7`
- name: `GetBackgroundTranslate`
- size: `171`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df3c`

## callees

- `0x18000dd4c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dde1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd67`
- `GDI32!GetSystemPaletteEntries` at `0x18000dd86`
- `GDI32!GetSystemPaletteEntries` at `0x18000dd86`
- `GDI32!GetNearestColor` at `0x18000dda7`
- `GDI32!GetNearestColor` at `0x18000dda7`

## pseudocode

```c
__int64 __fastcall GetBackgroundTranslate(HDC hdc, __int64 a2)
{
  struct tagPALETTEENTRY *v4; // rax
  struct tagPALETTEENTRY *v5; // rbx
  __int64 i; // rax
  __int64 v7; // rdi
  COLORREF v8; // edx
  char v9; // al
  __int64 v10; // rcx

  v4 = (struct tagPALETTEENTRY *)LocalAlloc(0x40u, 0x400u);
  v5 = v4;
  if ( v4 )
  {
    GetSystemPaletteEntries(hdc, 0, 0x100u, v4);
    for ( i = 0; i != 256; ++i )
      v5[i].peFlags = 0;
    v7 = 0;
    do
    {
      v8 = GetNearestColor(hdc, (unsigned __int16)v7 | 0x1000000) & 0xFFFFFF;
      if ( *(_DWORD *)&v5[v7] == v8 )
      {
        v9 = v7;
      }
      else
      {
        v10 = 0;
        do
        {
          if ( *(_DWORD *)&v5[v10] == v8 )
            break;
          v10 = (unsigned int)(v10 + 1);
        }
        while ( (int)v10 < 256 );
        v9 = 0;
        if ( (_DWORD)v10 != 256 )
          v9 = v10;
      }
      *(_BYTE *)(v7 + a2) = v9;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (int)v7 < 256 );
    LocalFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x18000dd4c  push    rbx
0x18000dd4e  push    rbp
0x18000dd4f  push    rsi
0x18000dd50  push    rdi
0x18000dd51  push    r14
0x18000dd53  sub     rsp, 20h
0x18000dd57  mov     rbp, rdx
0x18000dd5a  mov     rsi, rcx
0x18000dd5d  mov     edx, 400h; uBytes
0x18000dd62  mov     ecx, 40h ; '@'; uFlags
0x18000dd67  call    cs:__imp_LocalAlloc
0x18000dd6d  mov     rbx, rax
0x18000dd70  test    rax, rax
0x18000dd73  jz      short loc_18000DDE7
0x18000dd75  mov     r14d, 100h
0x18000dd7b  mov     r9, rax; pPalEntries
0x18000dd7e  mov     r8d, r14d; cEntries
0x18000dd81  xor     edx, edx; iStart
0x18000dd83  mov     rcx, rsi; hdc
0x18000dd86  call    cs:__imp_GetSystemPaletteEntries
0x18000dd8c  xor     eax, eax
0x18000dd8e  mov     byte ptr [rbx+rax*4+3], 0
0x18000dd93  inc     rax
0x18000dd96  cmp     rax, r14
0x18000dd99  jnz     short loc_18000DD8E
0x18000dd9b  xor     edi, edi
0x18000dd9d  movzx   edx, di
0x18000dda0  mov     rcx, rsi; hdc
0x18000dda3  bts     edx, 18h; color
0x18000dda7  call    cs:__imp_GetNearestColor
0x18000ddad  mov     edx, eax
0x18000ddaf  and     edx, 0FFFFFFh
0x18000ddb5  cmp     [rbx+rdi*4], edx
0x18000ddb8  jnz     short loc_18000DDBE
0x18000ddba  mov     eax, edi
0x18000ddbc  jmp     short loc_18000DDD4
0x18000ddbe  xor     ecx, ecx
0x18000ddc0  cmp     [rbx+rcx*4], edx
0x18000ddc3  jz      short loc_18000DDCC
0x18000ddc5  inc     ecx
0x18000ddc7  cmp     ecx, r14d
0x18000ddca  jl      short loc_18000DDC0
0x18000ddcc  xor     eax, eax
0x18000ddce  cmp     ecx, r14d
0x18000ddd1  cmovnz  eax, ecx
0x18000ddd4  mov     [rdi+rbp], al
0x18000ddd7  inc     edi
0x18000ddd9  cmp     edi, r14d
0x18000dddc  jl      short loc_18000DD9D
0x18000ddde  mov     rcx, rbx; hMem
0x18000dde1  call    cs:__imp_LocalFree
0x18000dde7  mov     eax, 1
0x18000ddec  add     rsp, 20h
0x18000ddf0  pop     r14
0x18000ddf2  pop     rdi
0x18000ddf3  pop     rsi
0x18000ddf4  pop     rbp
0x18000ddf5  pop     rbx
0x18000ddf6  retn
```
