# CopyPalette

- ea: `0x18000f8ec`
- end: `0x18000f99f`
- name: `CopyPalette`
- size: `179`
- prototype: `__int64 __fastcall(HPALETTE hpal)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010578`

## callees

- `0x18000f8ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f987`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f930`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f930`
- `GDI32!GetObjectW` at `0x18000f914`
- `GDI32!GetObjectW` at `0x18000f914`
- `GDI32!CreatePalette` at `0x18000f97b`
- `GDI32!CreatePalette` at `0x18000f97b`
- `GDI32!GetPaletteEntries` at `0x18000f95a`
- `GDI32!GetPaletteEntries` at `0x18000f95a`

## pseudocode

```c
HPALETTE __fastcall CopyPalette(HPALETTE hpal)
{
  LOGPALETTE *v2; // rax
  LOGPALETTE *v3; // rdi
  signed int i; // ecx
  __int64 v5; // rax
  HPALETTE Palette; // rbx
  signed int pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  if ( !hpal )
    return 0;
  GetObjectW(hpal, 4, &pv);
  if ( !pv )
    return 0;
  v2 = (LOGPALETTE *)LocalAlloc(0x40u, 4LL * pv + 8);
  v3 = v2;
  if ( !v2 )
    return 0;
  v2->palVersion = 768;
  v2->palNumEntries = pv;
  GetPaletteEntries(hpal, 0, pv, v2->palPalEntry);
  for ( i = 0; i < pv; v3->palPalEntry[v5].peFlags = 0 )
    v5 = i++;
  Palette = CreatePalette(v3);
  LocalFree(v3);
  return Palette;
}

```

## disassembly

```asm
0x18000f8ec  mov     [rsp+arg_8], rbx
0x18000f8f1  push    rdi
0x18000f8f2  sub     rsp, 20h
0x18000f8f6  mov     [rsp+28h+pv], 0
0x18000f8fe  mov     rbx, rcx
0x18000f901  test    rcx, rcx
0x18000f904  jz      loc_18000F992
0x18000f90a  lea     r8, [rsp+28h+pv]; pv
0x18000f90f  mov     edx, 4; c
0x18000f914  call    cs:__imp_GetObjectW
0x18000f91a  movsxd  rax, [rsp+28h+pv]
0x18000f91f  test    eax, eax
0x18000f921  jz      short loc_18000F992
0x18000f923  lea     rdx, ds:8[rax*4]; uBytes
0x18000f92b  mov     ecx, 40h ; '@'; uFlags
0x18000f930  call    cs:__imp_LocalAlloc
0x18000f936  mov     rdi, rax
0x18000f939  test    rax, rax
0x18000f93c  jz      short loc_18000F992
0x18000f93e  mov     word ptr [rax], 300h
0x18000f943  lea     r9, [rdi+4]; pPalEntries
0x18000f947  movzx   eax, word ptr [rsp+28h+pv]
0x18000f94c  xor     edx, edx; iStart
0x18000f94e  mov     [rdi+2], ax
0x18000f952  mov     rcx, rbx; hpal
0x18000f955  mov     r8d, [rsp+28h+pv]; cEntries
0x18000f95a  call    cs:__imp_GetPaletteEntries
0x18000f960  xor     ecx, ecx
0x18000f962  cmp     [rsp+28h+pv], ecx
0x18000f966  jle     short loc_18000F978
0x18000f968  movsxd  rax, ecx
0x18000f96b  inc     ecx
0x18000f96d  mov     byte ptr [rdi+rax*4+7], 0
0x18000f972  cmp     ecx, [rsp+28h+pv]
0x18000f976  jl      short loc_18000F968
0x18000f978  mov     rcx, rdi; plpal
0x18000f97b  call    cs:__imp_CreatePalette
0x18000f981  mov     rcx, rdi; hMem
0x18000f984  mov     rbx, rax
0x18000f987  call    cs:__imp_LocalFree
0x18000f98d  mov     rax, rbx
0x18000f990  jmp     short loc_18000F994
0x18000f992  xor     eax, eax
0x18000f994  mov     rbx, [rsp+28h+arg_8]
0x18000f999  add     rsp, 20h
0x18000f99d  pop     rdi
0x18000f99e  retn
```
