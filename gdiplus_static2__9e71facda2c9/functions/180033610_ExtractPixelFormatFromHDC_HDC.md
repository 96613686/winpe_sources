# ExtractPixelFormatFromHDC(HDC__ *)

- ea: `0x180033610`
- end: `0x180033823`
- name: `?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800319f0`
- `0x180033cd0`
- `0x180034410`
- `0x1800865b8`

## callees

- `0x180033610`
- `0x180105d40`
- `0x18010673c`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x180033655`
- `GDI32!CreateCompatibleBitmap` at `0x180033655`
- `GDI32!GetDIBits` at `0x180033694`
- `GDI32!GetDIBits` at `0x1800336dc`
- `GDI32!GetDIBits` at `0x180033694`
- `GDI32!GetDIBits` at `0x1800336dc`
- `GDI32!DeleteObject` at `0x18003372b`
- `GDI32!DeleteObject` at `0x18003372b`

## pseudocode

```c
__int64 __fastcall ExtractPixelFormatFromHDC(HDC hdc)
{
  unsigned int v2; // ebx
  HBITMAP CompatibleBitmap; // rdi
  WORD biBitCount; // ax
  struct tagBITMAPINFO bmi; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+6Ch] [rbp-94h]
  int v8; // [rsp+70h] [rbp-90h]

  v2 = 0;
  memset_0(&bmi, 0, 0x428u);
  CompatibleBitmap = CreateCompatibleBitmap(hdc, 1, 1);
  if ( CompatibleBitmap )
  {
    bmi.bmiHeader.biSize = 40;
    GetDIBits(hdc, CompatibleBitmap, 0, 0, 0, &bmi, 0);
    biBitCount = bmi.bmiHeader.biBitCount;
    if ( bmi.bmiHeader.biBitCount <= 8u )
    {
      switch ( bmi.bmiHeader.biBitCount )
      {
        case 1u:
          v2 = 196865;
          break;
        case 4u:
          v2 = 197634;
          break;
        case 8u:
          v2 = 198659;
          break;
      }
      goto LABEL_11;
    }
    if ( bmi.bmiHeader.biCompression == 3 )
    {
      GetDIBits(hdc, CompatibleBitmap, 0, bmi.bmiHeader.biHeight, 0, &bmi, 0);
      if ( *(_DWORD *)bmi.bmiColors != 16711680 )
      {
        if ( *(_DWORD *)bmi.bmiColors == 255 )
        {
          if ( v7 == 65280 && v8 == 16711680 && bmi.bmiHeader.biBitCount == 24 )
            v2 = 137232;
        }
        else if ( *(_DWORD *)bmi.bmiColors == 31744 )
        {
          if ( v7 == 992 && v8 == 31 && bmi.bmiHeader.biBitCount == 16 )
            v2 = 135173;
        }
        else if ( *(_DWORD *)bmi.bmiColors == 63488 && v7 == 2016 && v8 == 31 && bmi.bmiHeader.biBitCount == 16 )
        {
          v2 = 135174;
        }
        goto LABEL_11;
      }
      if ( v7 == 65280 && v8 == 255 )
      {
        biBitCount = bmi.bmiHeader.biBitCount;
        goto LABEL_8;
      }
    }
    else if ( !bmi.bmiHeader.biCompression )
    {
LABEL_8:
      if ( biBitCount == 24 )
      {
        v2 = 137224;
      }
      else if ( biBitCount == 32 )
      {
        v2 = 139273;
      }
    }
LABEL_11:
    DeleteObject(CompatibleBitmap);
  }
  return v2;
}

```

## disassembly

```asm
0x180033610  push    rbp
0x180033612  push    rbx
0x180033613  push    rsi
0x180033614  push    rdi
0x180033615  lea     rbp, [rsp-388h]
0x18003361d  sub     rsp, 488h
0x180033624  mov     rax, cs:__security_cookie
0x18003362b  xor     rax, rsp
0x18003362e  mov     [rbp+3A0h+var_30], rax
0x180033635  mov     rsi, rcx
0x180033638  xor     edx, edx; Val
0x18003363a  lea     rcx, [rsp+4A0h+bmi]; void *
0x18003363f  mov     r8d, 428h; Size
0x180033645  xor     ebx, ebx
0x180033647  call    memset_0
0x18003364c  lea     edx, [rbx+1]; cx
0x18003364f  mov     rcx, rsi; hdc
0x180033652  mov     r8d, edx; cy
0x180033655  call    cs:__imp_CreateCompatibleBitmap
0x18003365c  nop     dword ptr [rax+rax+00h]
0x180033661  mov     rdi, rax
0x180033664  test    rax, rax
0x180033667  jz      loc_180033737
0x18003366d  lea     rax, [rsp+4A0h+bmi]
0x180033672  mov     [rsp+4A0h+usage], ebx; usage
0x180033676  mov     [rsp+4A0h+lpbmi], rax; lpbmi
0x18003367b  xor     r9d, r9d; cLines
0x18003367e  xor     r8d, r8d; start
0x180033681  mov     [rsp+4A0h+lpvBits], rbx; lpvBits
0x180033686  mov     rdx, rdi; hbm
0x180033689  mov     [rsp+4A0h+bmi.bmiHeader.biSize], 28h ; '('
0x180033691  mov     rcx, rsi; hdc
0x180033694  call    cs:__imp_GetDIBits
0x18003369b  nop     dword ptr [rax+rax+00h]
0x1800336a0  movzx   eax, [rsp+4A0h+bmi.bmiHeader.biBitCount]
0x1800336a5  cmp     eax, 8
0x1800336a8  jbe     loc_18003378A
0x1800336ae  mov     edx, [rsp+4A0h+bmi.bmiHeader.biCompression]
0x1800336b2  cmp     edx, 3
0x1800336b5  jnz     loc_18003380C
0x1800336bb  mov     r9d, [rsp+4A0h+bmi.bmiHeader.biHeight]; cLines
0x1800336c0  lea     rax, [rsp+4A0h+bmi]
0x1800336c5  mov     [rsp+4A0h+usage], ebx; usage
0x1800336c9  xor     r8d, r8d; start
0x1800336cc  mov     [rsp+4A0h+lpbmi], rax; lpbmi
0x1800336d1  mov     rdx, rdi; hbm
0x1800336d4  mov     rcx, rsi; hdc
0x1800336d7  mov     [rsp+4A0h+lpvBits], rbx; lpvBits
0x1800336dc  call    cs:__imp_GetDIBits
0x1800336e3  nop     dword ptr [rax+rax+00h]
0x1800336e8  mov     edx, dword ptr [rsp+4A0h+bmi.bmiColors.rgbBlue]
0x1800336ec  mov     r8d, 0FF0000h
0x1800336f2  mov     ecx, [rsp+4A0h+var_434]
0x1800336f6  mov     eax, [rsp+4A0h+var_430]
0x1800336fa  cmp     edx, r8d
0x1800336fd  jnz     short loc_180033755
0x1800336ff  cmp     ecx, 0FF00h
0x180033705  jnz     short loc_180033728
0x180033707  cmp     eax, 0FFh
0x18003370c  jnz     short loc_180033728
0x18003370e  movzx   eax, [rsp+4A0h+bmi.bmiHeader.biBitCount]
0x180033713  cmp     ax, 18h
0x180033717  jz      loc_180033819
0x18003371d  cmp     ax, 20h ; ' '
0x180033721  jnz     short loc_180033728
0x180033723  mov     ebx, 22009h
0x180033728  mov     rcx, rdi; ho
0x18003372b  call    cs:__imp_DeleteObject
0x180033732  nop     dword ptr [rax+rax+00h]
0x180033737  mov     eax, ebx
0x180033739  mov     rcx, [rbp+3A0h+var_30]
0x180033740  xor     rcx, rsp; StackCookie
0x180033743  call    __security_check_cookie
0x180033748  add     rsp, 488h
0x18003374f  pop     rdi
0x180033750  pop     rsi
0x180033751  pop     rbx
0x180033752  pop     rbp
0x180033753  retn
0x180033755  cmp     edx, 0FFh
0x18003375b  jz      short loc_1800337B6
0x18003375d  cmp     edx, 7C00h
0x180033763  jz      short loc_1800337E1
0x180033765  cmp     edx, 0F800h
0x18003376b  jnz     short loc_180033728
0x18003376d  cmp     ecx, 7E0h
0x180033773  jnz     short loc_180033728
0x180033775  cmp     eax, 1Fh
0x180033778  jnz     short loc_180033728
0x18003377a  cmp     [rsp+4A0h+bmi.bmiHeader.biBitCount], 10h
0x180033780  mov     eax, 21006h
0x180033785  cmovz   ebx, eax
0x180033788  jmp     short loc_180033728
0x18003378a  mov     ecx, eax
0x18003378c  sub     ecx, 1
0x18003378f  jz      short loc_1800337AC
0x180033791  sub     ecx, 3
0x180033794  jz      short loc_1800337A2
0x180033796  cmp     ecx, 4
0x180033799  jnz     short loc_180033728
0x18003379b  mov     ebx, 30803h
0x1800337a0  jmp     short loc_180033728
0x1800337a2  mov     ebx, 30402h
0x1800337a7  jmp     loc_180033728
0x1800337ac  mov     ebx, 30101h
0x1800337b1  jmp     loc_180033728
0x1800337b6  cmp     ecx, 0FF00h
0x1800337bc  jnz     loc_180033728
0x1800337c2  cmp     eax, r8d
0x1800337c5  jnz     loc_180033728
0x1800337cb  cmp     [rsp+4A0h+bmi.bmiHeader.biBitCount], 18h
0x1800337d1  jnz     loc_180033728
0x1800337d7  mov     ebx, 21810h
0x1800337dc  jmp     loc_180033728
0x1800337e1  cmp     ecx, 3E0h
0x1800337e7  jnz     loc_180033728
0x1800337ed  cmp     eax, 1Fh
0x1800337f0  jnz     loc_180033728
0x1800337f6  cmp     [rsp+4A0h+bmi.bmiHeader.biBitCount], 10h
0x1800337fc  jnz     loc_180033728
0x180033802  mov     ebx, 21005h
0x180033807  jmp     loc_180033728
0x18003380c  test    edx, edx
0x18003380e  jnz     loc_180033728
0x180033814  jmp     loc_180033713
0x180033819  mov     ebx, 21808h
0x18003381e  jmp     loc_180033728
```
