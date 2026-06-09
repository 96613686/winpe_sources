# IsIdentityPalette

- ea: `0x18000b928`
- end: `0x18000bbb7`
- name: `IsIdentityPalette`
- size: `655`
- prototype: `__int64 __fastcall(HGDIOBJ h)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180008400`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x18000b928`
- `0x1800162f1`

## import_xrefs

- `GDI32!UnrealizeObject` at `0x18000bb89`
- `GDI32!UnrealizeObject` at `0x18000bb89`
- `GDI32!GetObjectW` at `0x18000b9e1`
- `GDI32!GetObjectW` at `0x18000b9e1`
- `GDI32!SetPaletteEntries` at `0x18000bb80`
- `GDI32!SetPaletteEntries` at `0x18000bb80`
- `GDI32!GetSystemPaletteEntries` at `0x18000ba9e`
- `GDI32!GetSystemPaletteEntries` at `0x18000bab4`
- `GDI32!GetSystemPaletteEntries` at `0x18000bb1f`
- `GDI32!GetSystemPaletteEntries` at `0x18000bb39`
- `GDI32!GetSystemPaletteEntries` at `0x18000ba9e`
- `GDI32!GetSystemPaletteEntries` at `0x18000bab4`
- `GDI32!GetSystemPaletteEntries` at `0x18000bb1f`
- `GDI32!GetSystemPaletteEntries` at `0x18000bb39`
- `GDI32!GetPaletteEntries` at `0x18000b9ff`
- `GDI32!GetPaletteEntries` at `0x18000ba14`
- `GDI32!GetPaletteEntries` at `0x18000bafc`
- `GDI32!GetPaletteEntries` at `0x18000b9ff`
- `GDI32!GetPaletteEntries` at `0x18000ba14`
- `GDI32!GetPaletteEntries` at `0x18000bafc`
- `GDI32!GetDeviceCaps` at `0x18000b9b6`
- `GDI32!GetDeviceCaps` at `0x18000b9b6`
- `USER32!GetDC` at `0x18000b99e`
- `USER32!GetDC` at `0x18000ba7f`
- `USER32!GetDC` at `0x18000bb04`
- `USER32!GetDC` at `0x18000b99e`
- `USER32!GetDC` at `0x18000ba7f`
- `USER32!GetDC` at `0x18000bb04`
- `USER32!ReleaseDC` at `0x18000b9c5`
- `USER32!ReleaseDC` at `0x18000babf`
- `USER32!ReleaseDC` at `0x18000bb44`
- `USER32!ReleaseDC` at `0x18000b9c5`
- `USER32!ReleaseDC` at `0x18000babf`
- `USER32!ReleaseDC` at `0x18000bb44`

## pseudocode

```c
__int64 __fastcall IsIdentityPalette(HPALETTE h)
{
  HDC DC; // rax
  HDC v3; // rbx
  __int64 i; // rax
  HDC v5; // rax
  HDC v6; // rbx
  __int64 j; // rax
  __int64 v8; // rsi
  HDC v9; // rbx
  __int64 v10; // rdi
  __int64 k; // rax
  int pv[4]; // [rsp+20h] [rbp-E0h] BYREF
  struct tagPALETTEENTRY Buf2[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct tagPALETTEENTRY v15; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPALETTEENTRY pPalEntries[8]; // [rsp+70h] [rbp-90h] BYREF
  struct tagPALETTEENTRY v17; // [rsp+90h] [rbp-70h] BYREF
  struct tagPALETTEENTRY v18; // [rsp+448h] [rbp+348h] BYREF

  pv[0] = 0;
  if ( !h )
    return 0;
  if ( (gwRasterCaps & 0x100) == 0 )
    return 0;
  if ( gwScreenBitDepth != 8 )
    return 0;
  memset_0(pPalEntries, 0, 0x400u);
  DC = GetDC(0);
  v3 = DC;
  if ( !DC )
    return 0;
  pv[0] = GetDeviceCaps(DC, 106);
  ReleaseDC(0, v3);
  if ( pv[0] != 20 )
    return 0;
  GetObjectW(h, 4, pv);
  if ( pv[0] != 256 )
    return 0;
  GetPaletteEntries(h, 0, 8u, pPalEntries);
  GetPaletteEntries(h, 0xF8u, 8u, &v17);
  for ( i = 0; i != 16; pPalEntries[i++].peFlags = 0 )
    ;
  if ( memcmp_0(pPalEntries, &byte_18001D160, 0x40u) )
  {
    if ( memcmp_0(pPalEntries, &byte_18001D260, 0x40u) )
    {
      if ( memcmp_0(pPalEntries, qword_18001D2A0, 0x40u) )
      {
        v5 = GetDC(0);
        v6 = v5;
        if ( !v5 )
          return 0;
        GetSystemPaletteEntries(v5, 0, 8u, Buf2);
        GetSystemPaletteEntries(v6, 0xF8u, 8u, &v15);
        ReleaseDC(0, v6);
        for ( j = 0; j != 16; Buf2[j++].peFlags = 0 )
          ;
        if ( memcmp_0(pPalEntries, Buf2, 0x40u) )
          return 0;
      }
    }
  }
  GetPaletteEntries(h, 0, 0x100u, pPalEntries);
  v8 = 10;
  v9 = GetDC(0);
  GetSystemPaletteEntries(v9, 0, 0xAu, pPalEntries);
  v10 = 246;
  GetSystemPaletteEntries(v9, 0xF6u, 0xAu, &v18);
  ReleaseDC(0, v9);
  for ( k = 0; k != 10; ++k )
    pPalEntries[k].peFlags = 0;
  do
    pPalEntries[v8++].peFlags = 4;
  while ( v8 != 246 );
  do
    pPalEntries[v10++].peFlags = 0;
  while ( v10 != 256 );
  SetPaletteEntries(h, 0, 0x100u, pPalEntries);
  UnrealizeObject(h);
  return 1;
}

```

## disassembly

```asm
0x18000b928  push    rbp
0x18000b92a  push    rbx
0x18000b92b  push    rsi
0x18000b92c  push    rdi
0x18000b92d  push    r12
0x18000b92f  push    r14
0x18000b931  lea     rbp, [rsp-388h]
0x18000b939  sub     rsp, 488h
0x18000b940  mov     rax, cs:__security_cookie
0x18000b947  xor     rax, rsp
0x18000b94a  mov     [rbp+3B0h+var_40], rax
0x18000b951  mov     [rsp+4B0h+pv], 0
0x18000b959  mov     r14, rcx
0x18000b95c  test    rcx, rcx
0x18000b95f  jz      loc_18000BB96
0x18000b965  mov     r12d, 100h
0x18000b96b  test    cs:gwRasterCaps, r12d
0x18000b972  jz      loc_18000BB96
0x18000b978  mov     edi, 8
0x18000b97d  cmp     cs:gwScreenBitDepth, di
0x18000b984  jnz     loc_18000BB96
0x18000b98a  xor     edx, edx; Val
0x18000b98c  lea     rcx, [rsp+4B0h+pPalEntries]; void *
0x18000b991  mov     r8d, 400h; Size
0x18000b997  call    memset_0
0x18000b99c  xor     ecx, ecx; hWnd
0x18000b99e  call    cs:__imp_GetDC
0x18000b9a4  mov     rbx, rax
0x18000b9a7  test    rax, rax
0x18000b9aa  jz      loc_18000BB96
0x18000b9b0  lea     edx, [rdi+62h]; index
0x18000b9b3  mov     rcx, rax; hdc
0x18000b9b6  call    cs:__imp_GetDeviceCaps
0x18000b9bc  mov     rdx, rbx; hDC
0x18000b9bf  xor     ecx, ecx; hWnd
0x18000b9c1  mov     [rsp+4B0h+pv], eax
0x18000b9c5  call    cs:__imp_ReleaseDC
0x18000b9cb  cmp     [rsp+4B0h+pv], 14h
0x18000b9d0  jnz     loc_18000BB96
0x18000b9d6  lea     r8, [rsp+4B0h+pv]; pv
0x18000b9db  mov     rcx, r14; h
0x18000b9de  lea     edx, [rdi-4]; c
0x18000b9e1  call    cs:__imp_GetObjectW
0x18000b9e7  cmp     [rsp+4B0h+pv], r12d
0x18000b9ec  jnz     loc_18000BB96
0x18000b9f2  lea     r9, [rsp+4B0h+pPalEntries]; pPalEntries
0x18000b9f7  mov     r8d, edi; cEntries
0x18000b9fa  xor     edx, edx; iStart
0x18000b9fc  mov     rcx, r14; hpal
0x18000b9ff  call    cs:__imp_GetPaletteEntries
0x18000ba05  lea     r9, [rbp+3B0h+var_420]; pPalEntries
0x18000ba09  mov     r8d, edi; cEntries
0x18000ba0c  lea     edx, [r12-8]; iStart
0x18000ba11  mov     rcx, r14; hpal
0x18000ba14  call    cs:__imp_GetPaletteEntries
0x18000ba1a  xor     eax, eax
0x18000ba1c  mov     [rsp+rax*4+4B0h+pPalEntries.peFlags], 0
0x18000ba21  inc     rax
0x18000ba24  cmp     rax, 10h
0x18000ba28  jnz     short loc_18000BA1C
0x18000ba2a  lea     esi, [rax+30h]
0x18000ba2d  mov     r8d, esi; Size
0x18000ba30  lea     rdx, byte_18001D160; Buf2
0x18000ba37  lea     rcx, [rsp+4B0h+pPalEntries]; Buf1
0x18000ba3c  call    memcmp_0
0x18000ba41  test    eax, eax
0x18000ba43  jz      loc_18000BAEF
0x18000ba49  mov     r8d, esi; Size
0x18000ba4c  lea     rdx, byte_18001D260; Buf2
0x18000ba53  lea     rcx, [rsp+4B0h+pPalEntries]; Buf1
0x18000ba58  call    memcmp_0
0x18000ba5d  test    eax, eax
0x18000ba5f  jz      loc_18000BAEF
0x18000ba65  mov     r8d, esi; Size
0x18000ba68  lea     rdx, qword_18001D2A0; Buf2
0x18000ba6f  lea     rcx, [rsp+4B0h+pPalEntries]; Buf1
0x18000ba74  call    memcmp_0
0x18000ba79  test    eax, eax
0x18000ba7b  jz      short loc_18000BAEF
0x18000ba7d  xor     ecx, ecx; hWnd
0x18000ba7f  call    cs:__imp_GetDC
0x18000ba85  mov     rbx, rax
0x18000ba88  test    rax, rax
0x18000ba8b  jz      loc_18000BB96
0x18000ba91  lea     r9, [rsp+4B0h+Buf2]; pPalEntries
0x18000ba96  mov     r8d, edi; cEntries
0x18000ba99  xor     edx, edx; iStart
0x18000ba9b  mov     rcx, rax; hdc
0x18000ba9e  call    cs:__imp_GetSystemPaletteEntries
0x18000baa4  lea     r9, [rsp+4B0h+var_460]; pPalEntries
0x18000baa9  mov     r8d, edi; cEntries
0x18000baac  mov     edx, 0F8h; iStart
0x18000bab1  mov     rcx, rbx; hdc
0x18000bab4  call    cs:__imp_GetSystemPaletteEntries
0x18000baba  mov     rdx, rbx; hDC
0x18000babd  xor     ecx, ecx; hWnd
0x18000babf  call    cs:__imp_ReleaseDC
0x18000bac5  xor     eax, eax
0x18000bac7  mov     [rsp+rax*4+4B0h+Buf2.peFlags], 0
0x18000bacc  inc     rax
0x18000bacf  cmp     rax, 10h
0x18000bad3  jnz     short loc_18000BAC7
0x18000bad5  mov     r8, rsi; Size
0x18000bad8  lea     rdx, [rsp+4B0h+Buf2]; Buf2
0x18000badd  lea     rcx, [rsp+4B0h+pPalEntries]; Buf1
0x18000bae2  call    memcmp_0
0x18000bae7  test    eax, eax
0x18000bae9  jnz     loc_18000BB96
0x18000baef  lea     r9, [rsp+4B0h+pPalEntries]; pPalEntries
0x18000baf4  mov     r8d, r12d; cEntries
0x18000baf7  xor     edx, edx; iStart
0x18000baf9  mov     rcx, r14; hpal
0x18000bafc  call    cs:__imp_GetPaletteEntries
0x18000bb02  xor     ecx, ecx; hWnd
0x18000bb04  call    cs:__imp_GetDC
0x18000bb0a  mov     esi, 0Ah
0x18000bb0f  lea     r9, [rsp+4B0h+pPalEntries]; pPalEntries
0x18000bb14  mov     r8d, esi; cEntries
0x18000bb17  mov     rcx, rax; hdc
0x18000bb1a  xor     edx, edx; iStart
0x18000bb1c  mov     rbx, rax
0x18000bb1f  call    cs:__imp_GetSystemPaletteEntries
0x18000bb25  mov     edi, 0F6h
0x18000bb2a  lea     r9, [rbp+3B0h+var_68]; pPalEntries
0x18000bb31  mov     edx, edi; iStart
0x18000bb33  mov     r8d, esi; cEntries
0x18000bb36  mov     rcx, rbx; hdc
0x18000bb39  call    cs:__imp_GetSystemPaletteEntries
0x18000bb3f  mov     rdx, rbx; hDC
0x18000bb42  xor     ecx, ecx; hWnd
0x18000bb44  call    cs:__imp_ReleaseDC
0x18000bb4a  xor     eax, eax
0x18000bb4c  mov     [rsp+rax*4+4B0h+pPalEntries.peFlags], 0
0x18000bb51  inc     rax
0x18000bb54  cmp     rax, rsi
0x18000bb57  jnz     short loc_18000BB4C
0x18000bb59  mov     [rsp+rsi*4+4B0h+pPalEntries.peFlags], 4
0x18000bb5e  inc     rsi
0x18000bb61  cmp     rsi, rdi
0x18000bb64  jnz     short loc_18000BB59
0x18000bb66  mov     [rsp+rdi*4+4B0h+pPalEntries.peFlags], 0
0x18000bb6b  inc     rdi
0x18000bb6e  cmp     rdi, r12
0x18000bb71  jnz     short loc_18000BB66
0x18000bb73  lea     r9, [rsp+4B0h+pPalEntries]; pPalEntries
0x18000bb78  mov     r8d, r12d; cEntries
0x18000bb7b  xor     edx, edx; iStart
0x18000bb7d  mov     rcx, r14; hpal
0x18000bb80  call    cs:__imp_SetPaletteEntries
0x18000bb86  mov     rcx, r14; h
0x18000bb89  call    cs:__imp_UnrealizeObject
0x18000bb8f  mov     eax, 1
0x18000bb94  jmp     short loc_18000BB98
0x18000bb96  xor     eax, eax
0x18000bb98  mov     rcx, [rbp+3B0h+var_40]
0x18000bb9f  xor     rcx, rsp; StackCookie
0x18000bba2  call    __security_check_cookie
0x18000bba7  add     rsp, 488h
0x18000bbae  pop     r14
0x18000bbb0  pop     r12
0x18000bbb2  pop     rdi
0x18000bbb3  pop     rsi
0x18000bbb4  pop     rbx
0x18000bbb5  pop     rbp
0x18000bbb6  retn
```
