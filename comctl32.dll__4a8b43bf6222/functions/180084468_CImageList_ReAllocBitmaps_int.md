# CImageList::_ReAllocBitmaps(int)

- ea: `0x180084468`
- end: `0x180084624`
- name: `?_ReAllocBitmaps@CImageList@@QEAAJH@Z`
- size: `444`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18008212c`
- `0x180082e00`
- `0x1800835e8`
- `0x18008471c`

## callees

- `0x180082a7c`
- `0x180082ad0`
- `0x180083c6c`
- `0x180084018`
- `0x180084468`

## import_xrefs

- `GDI32!SelectObject` at `0x1800845c7`
- `GDI32!SelectObject` at `0x1800845e1`
- `GDI32!SelectObject` at `0x1800845c7`
- `GDI32!SelectObject` at `0x1800845e1`
- `GDI32!BitBlt` at `0x180084564`
- `GDI32!BitBlt` at `0x1800845a7`
- `GDI32!BitBlt` at `0x180084564`
- `GDI32!BitBlt` at `0x1800845a7`
- `GDI32!CreateBitmap` at `0x1800844c2`
- `GDI32!CreateBitmap` at `0x1800844c2`

## pseudocode

```c
__int64 __fastcall CImageList::_ReAllocBitmaps(CImageList *this, int a2)
{
  int v2; // edi
  int v4; // ecx
  HBITMAP Bitmap; // rsi
  HBITMAP v6; // rbp
  int v7; // r14d
  int v8; // ebp
  int v10; // eax
  int v11; // r15d
  HDC v12; // rcx
  HBITMAP v13; // rcx
  HBITMAP v14; // rcx

  v2 = a2;
  if ( a2 <= 0 )
  {
    v2 = -a2;
LABEL_5:
    v4 = *((_DWORD *)this + 19);
    Bitmap = 0;
    v6 = 0;
    v7 = *((_DWORD *)this + 17) * v4;
    if ( v2 > 0 )
    {
      v8 = *((_DWORD *)this + 18) * ((v2 + v4 - 1) / v4);
      if ( (*((_BYTE *)this + 80) & 1) != 0 )
      {
        Bitmap = CreateBitmap(v7, v8, 1u, 1u, 0);
        if ( !Bitmap )
          return 2147942414LL;
      }
      v6 = CImageList::_CreateBitmap(this, v7, v8);
      if ( !v6 )
      {
        if ( Bitmap )
          CImageList::_DeleteBitmap(Bitmap);
        return 2147942414LL;
      }
    }
    v10 = *((_DWORD *)this + 14);
    if ( v10 > 0 )
    {
      if ( v2 < v10 )
        v10 = v2;
      v11 = *((_DWORD *)this + 18) * ((*((_DWORD *)this + 19) + v10 - 1) / *((_DWORD *)this + 19));
      if ( (*((_BYTE *)this + 80) & 1) != 0 )
      {
        CImageList::SelectDstBitmap(Bitmap);
        BitBlt(g_hdcDst, 0, 0, v7, v11, *((HDC *)this + 16), 0, 0, 0xCC0020u);
      }
      CImageList::SelectDstBitmap(v6);
      BitBlt(g_hdcDst, 0, 0, v7, v11, *((HDC *)this + 15), 0, 0, 0xCC0020u);
    }
    CImageList::SelectDstBitmap(0);
    CImageList::SelectSrcBitmap(0);
    if ( v6 )
      SelectObject(*((HDC *)this + 15), v6);
    v12 = (HDC)*((_QWORD *)this + 16);
    if ( v12 && Bitmap )
      SelectObject(v12, Bitmap);
    v13 = (HBITMAP)*((_QWORD *)this + 14);
    if ( v13 )
      CImageList::_DeleteBitmap(v13);
    v14 = (HBITMAP)*((_QWORD *)this + 13);
    if ( v14 )
      CImageList::_DeleteBitmap(v14);
    *((_QWORD *)this + 14) = Bitmap;
    *((_QWORD *)this + 13) = v6;
    *((_DWORD *)this + 21) = -1;
    *((_DWORD *)this + 15) = v2;
    return 0;
  }
  if ( *((_DWORD *)this + 15) < a2 )
    goto LABEL_5;
  return 0;
}

```

## disassembly

```asm
0x180084468  push    rbx
0x18008446a  push    rbp
0x18008446b  push    rsi
0x18008446c  push    rdi
0x18008446d  push    r14
0x18008446f  push    r15
0x180084471  sub     rsp, 58h
0x180084475  mov     edi, edx
0x180084477  mov     rbx, rcx
0x18008447a  test    edx, edx
0x18008447c  jle     short loc_180084488
0x18008447e  cmp     [rcx+3Ch], edx
0x180084481  jl      short loc_18008448A
0x180084483  jmp     loc_180084615
0x180084488  neg     edi
0x18008448a  mov     ecx, [rcx+4Ch]
0x18008448d  xor     esi, esi
0x18008448f  mov     r14d, ecx
0x180084492  xor     ebp, ebp
0x180084494  imul    r14d, [rbx+44h]
0x180084499  test    edi, edi
0x18008449b  jle     short loc_1800844FD
0x18008449d  lea     eax, [rcx-1]
0x1800844a0  add     eax, edi
0x1800844a2  cdq
0x1800844a3  idiv    ecx
0x1800844a5  mov     ebp, eax
0x1800844a7  imul    ebp, [rbx+48h]
0x1800844ab  test    byte ptr [rbx+50h], 1
0x1800844af  jz      short loc_1800844D0
0x1800844b1  lea     r9d, [rsi+1]; nBitCount
0x1800844b5  mov     [rsp+88h+lpBits], rsi; lpBits
0x1800844ba  mov     r8d, r9d; nPlanes
0x1800844bd  mov     edx, ebp; nHeight
0x1800844bf  mov     ecx, r14d; nWidth
0x1800844c2  call    cs:__imp_CreateBitmap
0x1800844c8  mov     rsi, rax
0x1800844cb  test    rax, rax
0x1800844ce  jz      short loc_1800844F3
0x1800844d0  mov     r8d, ebp; int
0x1800844d3  mov     edx, r14d; int
0x1800844d6  mov     rcx, rbx; this
0x1800844d9  call    ?_CreateBitmap@CImageList@@QEAAPEAUHBITMAP__@@HH@Z; CImageList::_CreateBitmap(int,int)
0x1800844de  mov     rbp, rax
0x1800844e1  test    rax, rax
0x1800844e4  jnz     short loc_1800844FD
0x1800844e6  test    rsi, rsi
0x1800844e9  jz      short loc_1800844F3
0x1800844eb  mov     rcx, rsi; ho
0x1800844ee  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x1800844f3  mov     eax, 8007000Eh
0x1800844f8  jmp     loc_180084617
0x1800844fd  mov     eax, [rbx+38h]
0x180084500  test    eax, eax
0x180084502  jle     loc_1800845AD
0x180084508  cmp     edi, eax
0x18008450a  cmovl   eax, edi
0x18008450d  dec     eax
0x18008450f  add     eax, [rbx+4Ch]
0x180084512  cdq
0x180084513  idiv    dword ptr [rbx+4Ch]
0x180084516  mov     r15d, eax
0x180084519  imul    r15d, [rbx+48h]
0x18008451e  test    byte ptr [rbx+50h], 1
0x180084522  jz      short loc_18008456A
0x180084524  mov     rcx, rsi; HBITMAP
0x180084527  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x18008452c  mov     rcx, [rbx+80h]
0x180084533  mov     r9d, r14d; cx
0x180084536  mov     [rsp+88h+rop], 0CC0020h; rop
0x18008453e  xor     r8d, r8d; y
0x180084541  mov     [rsp+88h+y1], 0; y1
0x180084549  xor     edx, edx; x
0x18008454b  mov     [rsp+88h+x1], 0; x1
0x180084553  mov     [rsp+88h+hdcSrc], rcx; hdcSrc
0x180084558  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x18008455f  mov     dword ptr [rsp+88h+lpBits], r15d; cy
0x180084564  call    cs:__imp_BitBlt
0x18008456a  mov     rcx, rbp; HBITMAP
0x18008456d  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180084572  mov     rax, [rbx+78h]
0x180084576  mov     r9d, r14d; cx
0x180084579  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180084580  xor     r8d, r8d; y
0x180084583  mov     [rsp+88h+rop], 0CC0020h; rop
0x18008458b  xor     edx, edx; x
0x18008458d  mov     [rsp+88h+y1], 0; y1
0x180084595  mov     [rsp+88h+x1], 0; x1
0x18008459d  mov     [rsp+88h+hdcSrc], rax; hdcSrc
0x1800845a2  mov     dword ptr [rsp+88h+lpBits], r15d; cy
0x1800845a7  call    cs:__imp_BitBlt
0x1800845ad  xor     ecx, ecx; HBITMAP
0x1800845af  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800845b4  xor     ecx, ecx; HBITMAP
0x1800845b6  call    ?SelectSrcBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x1800845bb  test    rbp, rbp
0x1800845be  jz      short loc_1800845CD
0x1800845c0  mov     rcx, [rbx+78h]; hdc
0x1800845c4  mov     rdx, rbp; h
0x1800845c7  call    cs:__imp_SelectObject
0x1800845cd  mov     rcx, [rbx+80h]; hdc
0x1800845d4  test    rcx, rcx
0x1800845d7  jz      short loc_1800845E7
0x1800845d9  test    rsi, rsi
0x1800845dc  jz      short loc_1800845E7
0x1800845de  mov     rdx, rsi; h
0x1800845e1  call    cs:__imp_SelectObject
0x1800845e7  mov     rcx, [rbx+70h]; ho
0x1800845eb  test    rcx, rcx
0x1800845ee  jz      short loc_1800845F5
0x1800845f0  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x1800845f5  mov     rcx, [rbx+68h]; ho
0x1800845f9  test    rcx, rcx
0x1800845fc  jz      short loc_180084603
0x1800845fe  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x180084603  mov     [rbx+70h], rsi
0x180084607  mov     [rbx+68h], rbp
0x18008460b  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x180084612  mov     [rbx+3Ch], edi
0x180084615  xor     eax, eax
0x180084617  add     rsp, 58h
0x18008461b  pop     r15
0x18008461d  pop     r14
0x18008461f  pop     rdi
0x180084620  pop     rsi
0x180084621  pop     rbp
0x180084622  pop     rbx
0x180084623  retn
```
