# TV_CreateDragImage

- ea: `0x18007b070`
- end: `0x18007b35e`
- name: `TV_CreateDragImage`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006bbb0`

## callees

- `0x18001968c`
- `0x18007b070`
- `0x18007b99c`
- `0x18007cc7c`
- `0x1800852a0`
- `0x180085390`
- `0x180085704`
- `0x1800857d0`
- `0x180086550`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18007b0ed`
- `GDI32!CreateCompatibleDC` at `0x18007b0ed`
- `GDI32!SelectObject` at `0x18007b170`
- `GDI32!SelectObject` at `0x18007b18a`
- `GDI32!SelectObject` at `0x18007b1f6`
- `GDI32!SelectObject` at `0x18007b256`
- `GDI32!SelectObject` at `0x18007b266`
- `GDI32!SelectObject` at `0x18007b170`
- `GDI32!SelectObject` at `0x18007b18a`
- `GDI32!SelectObject` at `0x18007b1f6`
- `GDI32!SelectObject` at `0x18007b256`
- `GDI32!SelectObject` at `0x18007b266`
- `GDI32!DeleteObject` at `0x18007b31e`
- `GDI32!DeleteObject` at `0x18007b32c`
- `GDI32!DeleteObject` at `0x18007b33a`
- `GDI32!DeleteObject` at `0x18007b31e`
- `GDI32!DeleteObject` at `0x18007b32c`
- `GDI32!DeleteObject` at `0x18007b33a`
- `GDI32!SetLayout` at `0x18007b15b`
- `GDI32!SetLayout` at `0x18007b15b`
- `GDI32!SetBkMode` at `0x18007b17e`
- `GDI32!SetBkMode` at `0x18007b17e`
- `GDI32!PatBlt` at `0x18007b1b9`
- `GDI32!PatBlt` at `0x18007b214`
- `GDI32!PatBlt` at `0x18007b1b9`
- `GDI32!PatBlt` at `0x18007b214`
- `GDI32!CreateBitmap` at `0x18007b139`
- `GDI32!CreateBitmap` at `0x18007b139`

## pseudocode

```c
struct _IMAGELIST *__fastcall TV_CreateDragImage(__int64 a1, __int64 a2)
{
  struct _IMAGELIST *result; // rax
  __int64 v3; // rsi
  struct _IMAGELIST *v5; // r15
  int v6; // r12d
  int v7; // r14d
  int v8; // r13d
  HDC CompatibleDC; // rbx
  int v10; // r13d
  HBITMAP Bitmap; // rbp
  HBITMAP ColorBitmap; // r14
  int v13; // r12d
  void *v14; // rdx
  struct _IMAGELIST *v15; // rax
  _OWORD v16[7]; // [rsp+40h] [rbp-78h] BYREF
  __int16 v17; // [rsp+C0h] [rbp+8h]
  HGDIOBJ h; // [rsp+D0h] [rbp+18h]

  result = 0;
  v3 = a2;
  memset(v16, 0, 60);
  if ( *(_QWORD *)(a1 + 152) )
  {
    if ( a2 || (v3 = *(_QWORD *)(a1 + 136)) != 0 )
    {
      v5 = 0;
      v6 = *(_DWORD *)(a1 + 32);
      v7 = *(__int16 *)(a1 + 296);
      v8 = *(unsigned __int16 *)(v3 + 46);
      v17 = *(_WORD *)(a1 + 302);
      CompatibleDC = CreateCompatibleDC(0);
      if ( CompatibleDC )
      {
        v10 = v7 + v8;
        Bitmap = 0;
        ColorBitmap = (HBITMAP)CreateColorBitmap(v10, v17);
        if ( ColorBitmap )
        {
          Bitmap = CreateBitmap(v10, v17, 1u, 1u, 0);
          if ( Bitmap )
          {
            v13 = v6 & 0x400000;
            if ( v13 )
              SetLayout(CompatibleDC, 1u);
            v14 = *(void **)(a1 + 200);
            if ( v14 )
              SelectObject(CompatibleDC, v14);
            SetBkMode(CompatibleDC, 1);
            h = SelectObject(CompatibleDC, ColorBitmap);
            PatBlt(CompatibleDC, 0, 0, v10, v17, 0x42u);
            TV_DrawItem(a1, v3, CompatibleDC, 0, 0, 7);
            if ( v13 )
              MirrorBitmapInDC(CompatibleDC, ColorBitmap);
            SelectObject(CompatibleDC, Bitmap);
            PatBlt(CompatibleDC, 0, 0, v10, v17, 0xFF0062u);
            TV_DrawItem(a1, v3, CompatibleDC, 0, 0, 7);
            if ( v13 )
              MirrorBitmapInDC(CompatibleDC, Bitmap);
            SelectObject(CompatibleDC, h);
            SelectObject(CompatibleDC, g_hfontSystem);
            v15 = ImageList_Create(v10, v17, 1u, 1, 0);
            v5 = v15;
            if ( v15 )
            {
              ImageList_SetBkColor(v15, 0xFFFFFFFF);
              ImageList_Add(v5, ColorBitmap, Bitmap);
              TV_GetItem(a1, v3, 2, v16);
              ImageList_CopyDitherImage(
                (int)v5,
                (*(__int16 *)(a1 + 302) - *(__int16 *)(a1 + 298)) >> 31,
                0,
                (*(__int16 *)(a1 + 302) - *(__int16 *)(a1 + 298)) / 2,
                *(struct _IMAGELIST **)(a1 + 152),
                SDWORD1(v16[2]),
                (*(_DWORD *)(a1 + 32) >> 15) & 0x80 | *(_WORD *)(v3 + 40) & 0xF00);
            }
          }
        }
        DeleteObject(CompatibleDC);
        if ( ColorBitmap )
          DeleteObject(ColorBitmap);
        if ( Bitmap )
          DeleteObject(Bitmap);
      }
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007b070  mov     [rsp+arg_8], rbx
0x18007b075  push    rbp
0x18007b076  push    rsi
0x18007b077  push    rdi
0x18007b078  push    r12
0x18007b07a  push    r13
0x18007b07c  push    r14
0x18007b07e  push    r15
0x18007b080  sub     rsp, 80h
0x18007b087  xorps   xmm0, xmm0
0x18007b08a  xor     eax, eax
0x18007b08c  mov     rsi, rdx
0x18007b08f  mov     rdi, rcx
0x18007b092  movups  xmmword ptr [rsp+0B8h+var_58], xmm0
0x18007b097  movups  xmmword ptr [rsp+0B8h+var_58+0Ch], xmm0
0x18007b09c  movups  [rsp+0B8h+var_78], xmm0
0x18007b0a1  movups  [rsp+0B8h+var_68], xmm0
0x18007b0a6  cmp     [rcx+98h], rax
0x18007b0ad  jz      loc_18007B343
0x18007b0b3  test    rdx, rdx
0x18007b0b6  jnz     short loc_18007B0C8
0x18007b0b8  mov     rsi, [rcx+88h]
0x18007b0bf  test    rsi, rsi
0x18007b0c2  jz      loc_18007B343
0x18007b0c8  movzx   eax, word ptr [rcx+12Eh]
0x18007b0cf  xor     r15d, r15d
0x18007b0d2  mov     r12d, [rcx+20h]
0x18007b0d6  movsx   r14d, word ptr [rcx+128h]
0x18007b0de  xor     ecx, ecx; hdc
0x18007b0e0  movzx   r13d, word ptr [rsi+2Eh]
0x18007b0e5  mov     [rsp+0B8h+arg_0], ax
0x18007b0ed  call    cs:__imp_CreateCompatibleDC
0x18007b0f3  mov     rbx, rax
0x18007b0f6  test    rax, rax
0x18007b0f9  jz      loc_18007B340
0x18007b0ff  movsx   edx, [rsp+0B8h+arg_0]; cy
0x18007b107  add     r13d, r14d
0x18007b10a  mov     ecx, r13d; cx
0x18007b10d  xor     ebp, ebp
0x18007b10f  call    CreateColorBitmap
0x18007b114  mov     r14, rax
0x18007b117  test    rax, rax
0x18007b11a  jz      loc_18007B31B
0x18007b120  movsx   edx, [rsp+0B8h+arg_0]; nHeight
0x18007b128  lea     eax, [rbp+1]
0x18007b12b  mov     r9d, eax; nBitCount
0x18007b12e  mov     [rsp+0B8h+lpBits], rbp; lpBits
0x18007b133  mov     r8d, eax; nPlanes
0x18007b136  mov     ecx, r13d; nWidth
0x18007b139  call    cs:__imp_CreateBitmap
0x18007b13f  mov     rbp, rax
0x18007b142  test    rax, rax
0x18007b145  jz      loc_18007B31B
0x18007b14b  and     r12d, 400000h
0x18007b152  jz      short loc_18007B161
0x18007b154  lea     edx, [r15+1]; l
0x18007b158  mov     rcx, rbx; hdc
0x18007b15b  call    cs:__imp_SetLayout
0x18007b161  mov     rdx, [rdi+0C8h]; h
0x18007b168  test    rdx, rdx
0x18007b16b  jz      short loc_18007B176
0x18007b16d  mov     rcx, rbx; hdc
0x18007b170  call    cs:__imp_SelectObject
0x18007b176  mov     edx, 1; mode
0x18007b17b  mov     rcx, rbx; hdc
0x18007b17e  call    cs:__imp_SetBkMode
0x18007b184  mov     rdx, r14; h
0x18007b187  mov     rcx, rbx; hdc
0x18007b18a  call    cs:__imp_SelectObject
0x18007b190  movsx   r15d, [rsp+0B8h+arg_0]
0x18007b199  mov     r9d, r13d; w
0x18007b19c  xor     r8d, r8d; y
0x18007b19f  mov     [rsp+0B8h+rop], 42h ; 'B'; rop
0x18007b1a7  xor     edx, edx; x
0x18007b1a9  mov     [rsp+0B8h+h], rax
0x18007b1b1  mov     rcx, rbx; hdc
0x18007b1b4  mov     dword ptr [rsp+0B8h+lpBits], r15d; h
0x18007b1b9  call    cs:__imp_PatBlt
0x18007b1bf  xor     r9d, r9d
0x18007b1c2  mov     [rsp+0B8h+rop], 7
0x18007b1ca  mov     r8, rbx
0x18007b1cd  mov     dword ptr [rsp+0B8h+lpBits], 0
0x18007b1d5  mov     rdx, rsi
0x18007b1d8  mov     rcx, rdi
0x18007b1db  call    TV_DrawItem
0x18007b1e0  test    r12d, r12d
0x18007b1e3  jz      short loc_18007B1F0
0x18007b1e5  mov     rdx, r14; h
0x18007b1e8  mov     rcx, rbx; hdc
0x18007b1eb  call    MirrorBitmapInDC
0x18007b1f0  mov     rdx, rbp; h
0x18007b1f3  mov     rcx, rbx; hdc
0x18007b1f6  call    cs:__imp_SelectObject
0x18007b1fc  mov     r9d, r13d; w
0x18007b1ff  mov     [rsp+0B8h+rop], 0FF0062h; rop
0x18007b207  xor     r8d, r8d; y
0x18007b20a  mov     dword ptr [rsp+0B8h+lpBits], r15d; h
0x18007b20f  xor     edx, edx; x
0x18007b211  mov     rcx, rbx; hdc
0x18007b214  call    cs:__imp_PatBlt
0x18007b21a  xor     r9d, r9d
0x18007b21d  mov     [rsp+0B8h+rop], 7
0x18007b225  mov     r8, rbx
0x18007b228  mov     dword ptr [rsp+0B8h+lpBits], 0
0x18007b230  mov     rdx, rsi
0x18007b233  mov     rcx, rdi
0x18007b236  call    TV_DrawItem
0x18007b23b  test    r12d, r12d
0x18007b23e  jz      short loc_18007B24B
0x18007b240  mov     rdx, rbp; h
0x18007b243  mov     rcx, rbx; hdc
0x18007b246  call    MirrorBitmapInDC
0x18007b24b  mov     rdx, [rsp+0B8h+h]; h
0x18007b253  mov     rcx, rbx; hdc
0x18007b256  call    cs:__imp_SelectObject
0x18007b25c  mov     rdx, cs:g_hfontSystem; h
0x18007b263  mov     rcx, rbx; hdc
0x18007b266  call    cs:__imp_SelectObject
0x18007b26c  mov     eax, 1
0x18007b271  mov     dword ptr [rsp+0B8h+lpBits], 0; cGrow
0x18007b279  mov     r9d, eax; cInitial
0x18007b27c  mov     r8d, eax; flags
0x18007b27f  mov     edx, r15d; cy
0x18007b282  mov     ecx, r13d; cx
0x18007b285  call    ImageList_Create
0x18007b28a  mov     r15, rax
0x18007b28d  test    rax, rax
0x18007b290  jz      loc_18007B31B
0x18007b296  or      edx, 0FFFFFFFFh; clrBk
0x18007b299  mov     rcx, rax; himl
0x18007b29c  call    ImageList_SetBkColor
0x18007b2a1  mov     r8, rbp; hbmMask
0x18007b2a4  mov     rdx, r14; hbmImage
0x18007b2a7  mov     rcx, r15; himl
0x18007b2aa  call    ImageList_Add
0x18007b2af  lea     r9, [rsp+0B8h+var_78]
0x18007b2b4  mov     r8d, 2
0x18007b2ba  mov     rdx, rsi
0x18007b2bd  mov     rcx, rdi
0x18007b2c0  call    TV_GetItem
0x18007b2c5  mov     eax, [rdi+20h]
0x18007b2c8  movsx   ecx, word ptr [rdi+12Ah]
0x18007b2cf  movzx   r8d, word ptr [rsi+28h]
0x18007b2d4  shr     eax, 0Fh
0x18007b2d7  and     r8d, 0F00h
0x18007b2de  and     eax, 80h
0x18007b2e3  or      r8d, eax
0x18007b2e6  movsx   eax, word ptr [rdi+12Eh]
0x18007b2ed  sub     eax, ecx
0x18007b2ef  mov     [rsp+0B8h+var_88], r8d; int
0x18007b2f4  cdq; int
0x18007b2f5  xor     r8d, r8d; int
0x18007b2f8  sub     eax, edx
0x18007b2fa  mov     rcx, r15; int
0x18007b2fd  sar     eax, 1
0x18007b2ff  mov     r9d, eax; int
0x18007b302  mov     eax, dword ptr [rsp+0B8h+var_58+4]
0x18007b306  mov     [rsp+0B8h+rop], eax; int
0x18007b30a  mov     rax, [rdi+98h]
0x18007b311  mov     [rsp+0B8h+lpBits], rax; struct _IMAGELIST *
0x18007b316  call    ImageList_CopyDitherImage
0x18007b31b  mov     rcx, rbx; ho
0x18007b31e  call    cs:__imp_DeleteObject
0x18007b324  test    r14, r14
0x18007b327  jz      short loc_18007B332
0x18007b329  mov     rcx, r14; ho
0x18007b32c  call    cs:__imp_DeleteObject
0x18007b332  test    rbp, rbp
0x18007b335  jz      short loc_18007B340
0x18007b337  mov     rcx, rbp; ho
0x18007b33a  call    cs:__imp_DeleteObject
0x18007b340  mov     rax, r15
0x18007b343  mov     rbx, [rsp+0B8h+arg_8]
0x18007b34b  add     rsp, 80h
0x18007b352  pop     r15
0x18007b354  pop     r14
0x18007b356  pop     r13
0x18007b358  pop     r12
0x18007b35a  pop     rdi
0x18007b35b  pop     rsi
0x18007b35c  pop     rbp
0x18007b35d  retn
```
