# DoStretchBlt

- ea: `0x1800b1afc`
- end: `0x1800b1ee1`
- name: `DoStretchBlt`
- size: `997`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int hDest, int, __int16, __int16, int, int, __int64, UINT, BITMAPINFO *, SIZE_T, __int64, int)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800b1950`
- `0x180141150`
- `0x180141ed8`
- `0x1801438a4`
- `0x180143a78`
- `0x180143d54`

## callees

- `0x1800b1afc`
- `0x1800b1ee8`
- `0x1800b1fa8`
- `0x1800e9380`
- `0x18013ead4`
- `0x18013ee58`
- `0x180141d90`
- `0x1801432b0`
- `0x180143e78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b1ed0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b1ed0`
- `GDI32!CreateDIBitmap` at `0x1800b1e4e`
- `GDI32!CreateDIBitmap` at `0x1800b1e4e`
- `GDI32!DeleteObject` at `0x1800b1eb8`
- `GDI32!DeleteObject` at `0x1800b1eb8`

## pseudocode

```c
__int64 __fastcall DoStretchBlt(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int hDest,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        XFORM *a11,
        UINT iUsage,
        BITMAPINFO *Src,
        SIZE_T a14,
        void *a15,
        int a16)
{
  unsigned int v16; // r14d
  int v18; // eax
  DWORD v19; // esi
  unsigned int v20; // ebx
  int v22; // ecx
  __int64 v23; // rdx
  DWORD v24; // esi
  void *v25; // r12
  HBITMAP DIBitmap; // rax
  HBITMAP v27; // rsi
  size_t Size; // [rsp+58h] [rbp-69h]
  SIZE_T uBytes; // [rsp+68h] [rbp-59h]
  unsigned __int16 v30; // [rsp+80h] [rbp-41h] BYREF
  void *pjBits; // [rsp+88h] [rbp-39h]
  int v32; // [rsp+90h] [rbp-31h] BYREF
  int v33; // [rsp+94h] [rbp-2Dh]
  int v34; // [rsp+98h] [rbp-29h]
  int v35; // [rsp+9Ch] [rbp-25h]
  __int16 v36[2]; // [rsp+A0h] [rbp-21h] BYREF
  __int16 v37[2]; // [rsp+A4h] [rbp-1Dh]
  int v38; // [rsp+A8h] [rbp-19h]
  int v39; // [rsp+ACh] [rbp-15h]

  v16 = a6;
  pjBits = a15;
  if ( a6 == 11141161 )
    return 1;
  v18 = *(_DWORD *)(a1 + 4);
  v19 = 4;
  if ( (v18 & 4) != 0 )
  {
    LODWORD(uBytes) = a14;
    return DoRotatedStretchBlt(a1, a2, a3, a4, hDest, a6, a7, a8, a9, a10, a11, iUsage, Src, uBytes, a15);
  }
  v20 = 0;
  if ( *(_DWORD *)(a1 + 484) )
  {
    if ( a6 == 13369376 )
    {
      v16 = 6684742;
    }
    else
    {
      if ( a6 != 15728673 )
      {
        *(_DWORD *)(a1 + 4) = v18 | 0x40000000;
        return 0;
      }
      v16 = 5898313;
    }
  }
  v32 = a2;
  v35 = a3 + hDest;
  v33 = a3;
  v34 = a4 + a2;
  if ( !(unsigned int)bXformWorkhorse(&v32, 2, a1 + 228) )
    return 0;
  if ( ((v16 ^ (4 * v16)) & 0xCCCC0000) == 0 )
    return bW16Emit9(
             a1,
             HIWORD(v16),
             (unsigned __int16)v32,
             (unsigned __int16)v33,
             (unsigned __int16)v34 - (unsigned __int16)v32,
             (unsigned __int16)v35 - (unsigned __int16)v33);
  if ( a11->eM12 != 0.0 || a11->eM21 != 0.0 )
  {
    SetLastError(0xDu);
    return 0;
  }
  *(_DWORD *)v36 = a7;
  v38 = a9 + a7;
  *(_DWORD *)v37 = a8;
  v39 = a8 + a10;
  if ( !(unsigned int)bXformWorkhorse(v36, 2, a11) )
    return 0;
  if ( iUsage
    || Src->bmiHeader.biPlanes != 1
    || Src->bmiHeader.biBitCount > 0x18u
    || (v22 = 16777490, !_bittest(&v22, Src->bmiHeader.biBitCount)) )
  {
    if ( !Src->bmiHeader.biCompression )
    {
LABEL_30:
      v19 = 6;
LABEL_31:
      DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &Src->bmiHeader, v19, pjBits, Src, iUsage);
      v27 = DIBitmap;
      if ( DIBitmap )
      {
        v20 = bEmitBitmap(
                a1,
                DIBitmap,
                v32,
                v33,
                (unsigned __int16)v34 - (unsigned __int16)v32,
                (unsigned __int16)v35 - (unsigned __int16)v33,
                v36[0],
                v37[0],
                (unsigned __int16)v38 - v36[0],
                (unsigned __int16)v39 - v37[0],
                v16);
        DeleteObject(v27);
      }
      return v20;
    }
LABEL_29:
    if ( Src->bmiHeader.biCompression != 3 )
      goto LABEL_31;
    goto LABEL_30;
  }
  if ( Src->bmiHeader.biCompression )
    goto LABEL_29;
  v30 = 0;
  if ( (int)GetSizeOfColorTable(Src, &v30) < 0 )
    return 0;
  v23 = Src->bmiHeader.biSize + v30;
  if ( (unsigned int)v23 < Src->bmiHeader.biSize )
    return 0;
  v24 = a14;
  v25 = pjBits;
  if ( (unsigned int)v23 < (unsigned int)a14 )
    v24 = Src->bmiHeader.biSize + v30;
  DoMakeBitmapBottomUp((__int64)Src, v23, (char *)pjBits, a16);
  LODWORD(Size) = v24;
  return (unsigned int)bEmitWin16StretchBlt(
                         a1,
                         (unsigned __int16)v32,
                         (unsigned __int16)v33,
                         (unsigned __int16)(v34 - v32),
                         (unsigned __int16)v35 - (unsigned __int16)v33,
                         v36[0],
                         v37[0],
                         (unsigned __int16)v38 - v36[0],
                         (unsigned __int16)v39 - v37[0],
                         v16,
                         Src,
                         Size,
                         (__int64)v25,
                         a16);
}

```

## disassembly

```asm
0x1800b1afc  push    rbp
0x1800b1afe  push    rbx
0x1800b1aff  push    rsi
0x1800b1b00  push    rdi
0x1800b1b01  push    r12
0x1800b1b03  push    r13
0x1800b1b05  push    r14
0x1800b1b07  push    r15
0x1800b1b09  lea     rbp, [rsp-7]
0x1800b1b0e  sub     rsp, 0C8h
0x1800b1b15  mov     rax, cs:__security_cookie
0x1800b1b1c  xor     rax, rsp
0x1800b1b1f  mov     [rbp+3Fh+var_50], rax
0x1800b1b23  mov     r14d, [rbp+3Fh+arg_28]
0x1800b1b27  mov     r13, rcx
0x1800b1b2a  mov     rcx, [rbp+3Fh+arg_70]
0x1800b1b31  mov     rdi, [rbp+3Fh+arg_50]
0x1800b1b38  mov     r12d, [rbp+3Fh+arg_58]
0x1800b1b3f  mov     r15, [rbp+3Fh+arg_60]
0x1800b1b46  mov     [rbp+3Fh+pjBits], rcx
0x1800b1b4a  cmp     r14d, 0AA0029h
0x1800b1b51  jz      loc_1800B1C20
0x1800b1b57  mov     eax, [r13+4]
0x1800b1b5b  mov     esi, 4
0x1800b1b60  test    sil, al
0x1800b1b63  jnz     loc_1800B1C27
0x1800b1b69  xor     ebx, ebx
0x1800b1b6b  cmp     [r13+1E4h], ebx
0x1800b1b72  jnz     loc_1800B1C83
0x1800b1b78  mov     ecx, [rbp+3Fh+hDest]
0x1800b1b7b  lea     eax, [r9+rdx]
0x1800b1b7f  add     ecx, r8d
0x1800b1b82  mov     [rbp+3Fh+var_70], edx
0x1800b1b85  mov     [rbp+3Fh+var_64], ecx
0x1800b1b88  mov     edx, 2
0x1800b1b8d  mov     [rbp+3Fh+var_6C], r8d
0x1800b1b91  lea     rcx, [rbp+3Fh+var_70]
0x1800b1b95  lea     r8, [r13+0E4h]
0x1800b1b9c  mov     [rbp+3Fh+var_68], eax
0x1800b1b9f  call    bXformWorkhorse
0x1800b1ba4  test    eax, eax
0x1800b1ba6  jz      short loc_1800B1C1C
0x1800b1ba8  lea     eax, ds:0[r14*4]
0x1800b1bb0  xor     eax, r14d
0x1800b1bb3  test    eax, 0CCCC0000h
0x1800b1bb8  jnz     loc_1800B1CB8
0x1800b1bbe  movzx   ecx, word ptr [rbp+3Fh+var_64]
0x1800b1bc2  mov     edx, r14d
0x1800b1bc5  movzx   r9d, word ptr [rbp+3Fh+var_6C]
0x1800b1bca  movzx   eax, word ptr [rbp+3Fh+var_68]
0x1800b1bce  sub     cx, r9w
0x1800b1bd2  movzx   r8d, word ptr [rbp+3Fh+var_70]
0x1800b1bd7  mov     word ptr [rsp+100h+Src], r14w
0x1800b1bdd  sub     ax, r8w
0x1800b1be1  shr     edx, 10h
0x1800b1be4  mov     [rsp+100h+var_B8], dx
0x1800b1be9  mov     word ptr [rsp+100h+iUsage], cx
0x1800b1bee  mov     rcx, r13
0x1800b1bf1  mov     word ptr [rsp+100h+pbmi], ax
0x1800b1bf6  call    bW16Emit9
0x1800b1bfb  mov     rcx, [rbp+3Fh+var_50]
0x1800b1bff  xor     rcx, rsp; StackCookie
0x1800b1c02  call    __security_check_cookie
0x1800b1c07  add     rsp, 0C8h
0x1800b1c0e  pop     r15
0x1800b1c10  pop     r14
0x1800b1c12  pop     r13
0x1800b1c14  pop     r12
0x1800b1c16  pop     rdi
0x1800b1c17  pop     rsi
0x1800b1c18  pop     rbx
0x1800b1c19  pop     rbp
0x1800b1c1a  retn
0x1800b1c1c  xor     eax, eax
0x1800b1c1e  jmp     short loc_1800B1BFB
0x1800b1c20  mov     eax, 1
0x1800b1c25  jmp     short loc_1800B1BFB
0x1800b1c27  mov     eax, dword ptr [rbp+3Fh+arg_68]
0x1800b1c2d  mov     [rsp+100h+var_90], rcx; __int64
0x1800b1c32  mov     rcx, r13; int
0x1800b1c35  mov     dword ptr [rsp+100h+uBytes], eax; uBytes
0x1800b1c39  mov     eax, [rbp+3Fh+arg_48]
0x1800b1c3f  mov     [rsp+100h+var_A0], r15; __int64
0x1800b1c44  mov     dword ptr [rsp+100h+Size], r12d; int
0x1800b1c49  mov     [rsp+100h+Src], rdi; __int64
0x1800b1c4e  mov     dword ptr [rsp+100h+var_B8], eax; int
0x1800b1c52  mov     eax, [rbp+3Fh+arg_40]
0x1800b1c58  mov     dword ptr [rsp+100h+var_C0], eax; int
0x1800b1c5c  mov     eax, dword ptr [rbp+3Fh+arg_38]
0x1800b1c62  mov     dword ptr [rsp+100h+var_C8], eax; __int16
0x1800b1c66  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1800b1c69  mov     dword ptr [rsp+100h+var_D0], eax; __int16
0x1800b1c6d  mov     eax, [rbp+3Fh+hDest]
0x1800b1c70  mov     [rsp+100h+iUsage], r14d; int
0x1800b1c75  mov     dword ptr [rsp+100h+pbmi], eax; hDest
0x1800b1c79  call    DoRotatedStretchBlt
0x1800b1c7e  jmp     loc_1800B1BFB
0x1800b1c83  cmp     r14d, 0CC0020h
0x1800b1c8a  jnz     short loc_1800B1C97
0x1800b1c8c  mov     r14d, 660046h
0x1800b1c92  jmp     loc_1800B1B78
0x1800b1c97  cmp     r14d, 0F00021h
0x1800b1c9e  jnz     short loc_1800B1CAB
0x1800b1ca0  mov     r14d, 5A0049h
0x1800b1ca6  jmp     loc_1800B1B78
0x1800b1cab  bts     eax, 1Eh
0x1800b1caf  mov     [r13+4], eax
0x1800b1cb3  jmp     loc_1800B1C1C
0x1800b1cb8  movss   xmm0, dword ptr [rdi+4]
0x1800b1cbd  xorps   xmm1, xmm1
0x1800b1cc0  ucomiss xmm0, xmm1
0x1800b1cc3  jp      loc_1800B1ECB
0x1800b1cc9  jnz     loc_1800B1ECB
0x1800b1ccf  movss   xmm0, dword ptr [rdi+8]
0x1800b1cd4  ucomiss xmm0, xmm1
0x1800b1cd7  jp      loc_1800B1ECB
0x1800b1cdd  jnz     loc_1800B1ECB
0x1800b1ce3  mov     ecx, dword ptr [rbp+3Fh+arg_30]
0x1800b1ce6  mov     r8, rdi
0x1800b1ce9  mov     r9d, dword ptr [rbp+3Fh+arg_38]
0x1800b1cf0  mov     edx, 2
0x1800b1cf5  mov     dword ptr [rbp+3Fh+var_60], ecx
0x1800b1cf8  add     ecx, [rbp+3Fh+arg_40]
0x1800b1cfe  mov     [rbp+3Fh+var_58], ecx
0x1800b1d01  mov     ecx, [rbp+3Fh+arg_48]
0x1800b1d07  add     ecx, r9d
0x1800b1d0a  mov     dword ptr [rbp+3Fh+var_5C], r9d
0x1800b1d0e  mov     [rbp+3Fh+var_54], ecx
0x1800b1d11  lea     rcx, [rbp+3Fh+var_60]
0x1800b1d15  call    bXformWorkhorse
0x1800b1d1a  test    eax, eax
0x1800b1d1c  jz      loc_1800B1C1C
0x1800b1d22  test    r12d, r12d
0x1800b1d25  jnz     loc_1800B1E24
0x1800b1d2b  lea     eax, [r12+1]
0x1800b1d30  cmp     [r15+0Ch], ax
0x1800b1d35  jnz     loc_1800B1E24
0x1800b1d3b  cmp     word ptr [r15+0Eh], 18h
0x1800b1d41  ja      loc_1800B1E24
0x1800b1d47  movzx   eax, word ptr [r15+0Eh]
0x1800b1d4c  mov     ecx, 1000112h
0x1800b1d51  bt      ecx, eax
0x1800b1d54  jnb     loc_1800B1E24
0x1800b1d5a  cmp     [r15+10h], ebx
0x1800b1d5e  jnz     loc_1800B1E2A
0x1800b1d64  lea     rdx, [rbp+3Fh+var_80]
0x1800b1d68  mov     [rbp+3Fh+var_80], bx
0x1800b1d6c  mov     rcx, r15
0x1800b1d6f  call    GetSizeOfColorTable
0x1800b1d74  test    eax, eax
0x1800b1d76  js      loc_1800B1C1C
0x1800b1d7c  movzx   edx, [rbp+3Fh+var_80]
0x1800b1d80  add     edx, [r15]
0x1800b1d83  cmp     edx, [r15]
0x1800b1d86  jb      loc_1800B1C1C
0x1800b1d8c  mov     esi, dword ptr [rbp+3Fh+arg_68]
0x1800b1d92  mov     rcx, r15
0x1800b1d95  mov     r12, [rbp+3Fh+pjBits]
0x1800b1d99  cmp     edx, esi
0x1800b1d9b  mov     ebx, [rbp+3Fh+arg_78]
0x1800b1da1  mov     r8, r12
0x1800b1da4  mov     r9d, ebx
0x1800b1da7  cmovb   esi, edx
0x1800b1daa  call    DoMakeBitmapBottomUp
0x1800b1daf  movzx   r10d, [rbp+3Fh+var_60]
0x1800b1db4  movzx   r11d, word ptr [rbp+3Fh+var_54]
0x1800b1db9  movzx   edi, [rbp+3Fh+var_5C]
0x1800b1dbd  movzx   eax, word ptr [rbp+3Fh+var_58]
0x1800b1dc1  sub     r11w, di
0x1800b1dc5  movzx   ecx, word ptr [rbp+3Fh+var_64]
0x1800b1dc9  sub     ax, r10w
0x1800b1dcd  movzx   r8d, word ptr [rbp+3Fh+var_6C]; int
0x1800b1dd2  movzx   r9d, word ptr [rbp+3Fh+var_68]
0x1800b1dd7  sub     cx, r8w
0x1800b1ddb  movzx   edx, word ptr [rbp+3Fh+var_70]; int
0x1800b1ddf  mov     dword ptr [rsp+100h+uBytes], ebx; int
0x1800b1de3  sub     r9w, dx; int
0x1800b1de7  mov     [rsp+100h+var_A0], r12; __int64
0x1800b1dec  mov     dword ptr [rsp+100h+Size], esi; Size
0x1800b1df0  mov     [rsp+100h+Src], r15; Src
0x1800b1df5  mov     dword ptr [rsp+100h+var_B8], r14d; int
0x1800b1dfa  mov     [rsp+100h+var_C0], r11w; __int16
0x1800b1e00  mov     [rsp+100h+var_C8], ax; __int16
0x1800b1e05  mov     [rsp+100h+var_D0], di; __int16
0x1800b1e0a  mov     word ptr [rsp+100h+iUsage], r10w; __int16
0x1800b1e10  mov     word ptr [rsp+100h+pbmi], cx; __int16
0x1800b1e15  mov     rcx, r13; int
0x1800b1e18  call    bEmitWin16StretchBlt
0x1800b1e1d  mov     ebx, eax
0x1800b1e1f  jmp     loc_1800B1EC4
0x1800b1e24  cmp     [r15+10h], ebx
0x1800b1e28  jz      short loc_1800B1E31
0x1800b1e2a  cmp     dword ptr [r15+10h], 3
0x1800b1e2f  jnz     short loc_1800B1E36
0x1800b1e31  mov     esi, 6
0x1800b1e36  mov     r9, [rbp+3Fh+pjBits]; pjBits
0x1800b1e3a  mov     r8d, esi; flInit
0x1800b1e3d  mov     rcx, [r13+28h]; hdc
0x1800b1e41  mov     rdx, r15; pbmih
0x1800b1e44  mov     [rsp+100h+iUsage], r12d; iUsage
0x1800b1e49  mov     [rsp+100h+pbmi], r15; pbmi
0x1800b1e4e  call    cs:__imp_CreateDIBitmap
0x1800b1e55  nop     dword ptr [rax+rax+00h]
0x1800b1e5a  mov     rsi, rax
0x1800b1e5d  test    rax, rax
0x1800b1e60  jz      short loc_1800B1EC4
0x1800b1e62  mov     r11d, dword ptr [rbp+3Fh+var_60]
0x1800b1e66  mov     edi, dword ptr [rbp+3Fh+var_5C]
0x1800b1e69  mov     edx, [rbp+3Fh+var_58]
0x1800b1e6c  mov     r10d, [rbp+3Fh+var_64]
0x1800b1e70  sub     edx, r11d
0x1800b1e73  mov     r9d, [rbp+3Fh+var_6C]
0x1800b1e77  sub     r10d, r9d
0x1800b1e7a  mov     ecx, [rbp+3Fh+var_68]
0x1800b1e7d  mov     r8d, [rbp+3Fh+var_70]
0x1800b1e81  sub     ecx, r8d
0x1800b1e84  mov     ebx, [rbp+3Fh+var_54]
0x1800b1e87  mov     dword ptr [rsp+100h+Src], r14d; int
0x1800b1e8c  sub     ebx, edi
0x1800b1e8e  mov     dword ptr [rsp+100h+var_B8], ebx; __int16
0x1800b1e92  mov     dword ptr [rsp+100h+var_C0], edx; __int16
0x1800b1e96  mov     rdx, rax; hbm
0x1800b1e99  mov     dword ptr [rsp+100h+var_C8], edi; __int16
0x1800b1e9d  mov     dword ptr [rsp+100h+var_D0], r11d; __int16
0x1800b1ea2  mov     [rsp+100h+iUsage], r10d; __int16
0x1800b1ea7  mov     dword ptr [rsp+100h+pbmi], ecx; __int16
0x1800b1eab  mov     rcx, r13; int
0x1800b1eae  call    bEmitBitmap
0x1800b1eb3  mov     ebx, eax
0x1800b1eb5  mov     rcx, rsi; ho
0x1800b1eb8  call    cs:__imp_DeleteObject
0x1800b1ebf  nop     dword ptr [rax+rax+00h]
0x1800b1ec4  mov     eax, ebx
0x1800b1ec6  jmp     loc_1800B1BFB
0x1800b1ecb  mov     ecx, 0Dh; dwErrCode
0x1800b1ed0  call    cs:__imp_SetLastError
0x1800b1ed7  nop     dword ptr [rax+rax+00h]
0x1800b1edc  jmp     loc_1800B1C1C
```
