# CImageList::GetIcon(int,uint,HICON__ * *)

- ea: `0x180081170`
- end: `0x18008132f`
- name: `?GetIcon@CImageList@@UEAAJHIPEAPEAUHICON__@@@Z`
- size: `447`
- prototype: `int(CImageList *__hidden this, int, unsigned int, HICON *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180081170`
- `0x180082a7c`
- `0x1800834d0`
- `0x1800852a0`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800812f3`
- `GDI32!DeleteObject` at `0x1800812fc`
- `GDI32!DeleteObject` at `0x1800812f3`
- `GDI32!DeleteObject` at `0x1800812fc`
- `GDI32!PatBlt` at `0x18008122d`
- `GDI32!PatBlt` at `0x180081290`
- `GDI32!PatBlt` at `0x18008122d`
- `GDI32!PatBlt` at `0x180081290`
- `GDI32!CreateBitmap` at `0x1800811ea`
- `GDI32!CreateBitmap` at `0x1800811ea`
- `KERNEL32!EnterCriticalSection` at `0x180081203`
- `KERNEL32!EnterCriticalSection` at `0x180081203`
- `KERNEL32!LeaveCriticalSection` at `0x1800812c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800812c4`
- `USER32!CreateIconIndirect` at `0x1800812e7`
- `USER32!CreateIconIndirect` at `0x1800812e7`

## pseudocode

```c
__int64 __fastcall CImageList::GetIcon(unsigned __int64 this, int a2, int a3, HICON *a4)
{
  int v6; // r15d
  HICON v7; // rbx
  int v8; // r14d
  unsigned int v9; // r12d
  HBITMAP ColorBitmap; // rbp
  HBITMAP Bitmap; // r13
  struct IImageList *v12; // rbx
  ICONINFO piconinfo; // [rsp+30h] [rbp-58h] BYREF

  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( a2 < 0 || a2 >= *(_DWORD *)(this + 40) )
    return 2147942487LL;
  v6 = *(_DWORD *)(this + 56);
  v7 = 0;
  v8 = *(_DWORD *)(this + 52);
  v9 = -2147024882;
  ColorBitmap = (HBITMAP)CreateColorBitmap(v8, v6);
  if ( ColorBitmap )
  {
    Bitmap = CreateBitmap(v8, v6, 1u, 1u, 0);
    if ( Bitmap )
    {
      EnterCriticalSection(&g_csDll);
      CImageList::SelectDstBitmap(Bitmap);
      PatBlt(g_hdcDst, 0, 0, v8, v6, 0xFF0062u);
      v9 = 0;
      v12 = (struct IImageList *)(this & -(__int64)(this != 16));
      WimpyDraw(v12, a2, g_hdcDst, 0, 0, a3 | 0x10);
      CImageList::SelectDstBitmap(ColorBitmap);
      PatBlt(g_hdcDst, 0, 0, v8, v6, 0x42u);
      WimpyDraw(v12, a2, g_hdcDst, 0, 0, a3 | 1);
      CImageList::SelectDstBitmap(0);
      LeaveCriticalSection(&g_csDll);
      *(_QWORD *)&piconinfo.fIcon = 1;
      piconinfo.yHotspot = 0;
      piconinfo.hbmColor = ColorBitmap;
      piconinfo.hbmMask = Bitmap;
      v7 = CreateIconIndirect(&piconinfo);
      DeleteObject(Bitmap);
    }
    DeleteObject(ColorBitmap);
  }
  *a4 = v7;
  return v9;
}

```

## disassembly

```asm
0x180081170  mov     rax, rsp
0x180081173  mov     [rax+8], rbx
0x180081177  mov     [rax+20h], r9
0x18008117b  mov     [rax+18h], r8d
0x18008117f  push    rbp
0x180081180  push    rsi
0x180081181  push    rdi
0x180081182  push    r12
0x180081184  push    r13
0x180081186  push    r14
0x180081188  push    r15
0x18008118a  sub     rsp, 50h
0x18008118e  xorps   xmm0, xmm0
0x180081191  mov     esi, edx
0x180081193  mov     rdi, rcx
0x180081196  movups  xmmword ptr [rax-58h], xmm0
0x18008119a  movups  xmmword ptr [rax-48h], xmm0
0x18008119e  test    edx, edx
0x1800811a0  js      loc_180081312
0x1800811a6  cmp     edx, [rcx+28h]
0x1800811a9  jge     loc_180081312
0x1800811af  mov     r15d, [rcx+38h]
0x1800811b3  xor     ebx, ebx
0x1800811b5  mov     r14d, [rcx+34h]
0x1800811b9  mov     edx, r15d; cy
0x1800811bc  mov     ecx, r14d; cx
0x1800811bf  mov     r12d, 8007000Eh
0x1800811c5  call    CreateColorBitmap
0x1800811ca  mov     rbp, rax
0x1800811cd  test    rax, rax
0x1800811d0  jz      loc_180081302
0x1800811d6  lea     eax, [rbx+1]
0x1800811d9  mov     [rsp+88h+lpBits], rbx; lpBits
0x1800811de  mov     r9d, eax; nBitCount
0x1800811e1  mov     r8d, eax; nPlanes
0x1800811e4  mov     edx, r15d; nHeight
0x1800811e7  mov     ecx, r14d; nWidth
0x1800811ea  call    cs:__imp_CreateBitmap
0x1800811f0  mov     r13, rax
0x1800811f3  test    rax, rax
0x1800811f6  jz      loc_1800812F9
0x1800811fc  lea     rcx, g_csDll; lpCriticalSection
0x180081203  call    cs:__imp_EnterCriticalSection
0x180081209  mov     rcx, r13; HBITMAP
0x18008120c  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180081211  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180081218  mov     r9d, r14d; w
0x18008121b  xor     r8d, r8d; y
0x18008121e  mov     [rsp+88h+rop], 0FF0062h; rop
0x180081226  xor     edx, edx; x
0x180081228  mov     dword ptr [rsp+88h+lpBits], r15d; h
0x18008122d  call    cs:__imp_PatBlt
0x180081233  mov     r8, cs:?g_hdcDst@@3PEAUHDC__@@EA; HDC
0x18008123a  lea     rax, [rdi-10h]
0x18008123e  neg     rax
0x180081241  mov     edx, esi; int
0x180081243  sbb     rbx, rbx
0x180081246  xor     r12d, r12d
0x180081249  and     rbx, rdi
0x18008124c  xor     r9d, r9d; int
0x18008124f  mov     edi, [rsp+88h+arg_10]
0x180081256  mov     rcx, rbx; struct IImageList *
0x180081259  mov     eax, edi
0x18008125b  or      eax, 10h
0x18008125e  mov     [rsp+88h+rop], eax; unsigned int
0x180081262  mov     dword ptr [rsp+88h+lpBits], r12d; int
0x180081267  call    ?WimpyDraw@@YAJPEAUIImageList@@HPEAUHDC__@@HHI@Z; WimpyDraw(IImageList *,int,HDC__ *,int,int,uint)
0x18008126c  mov     rcx, rbp; HBITMAP
0x18008126f  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180081274  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x18008127b  mov     r9d, r14d; w
0x18008127e  xor     r8d, r8d; y
0x180081281  mov     [rsp+88h+rop], 42h ; 'B'; rop
0x180081289  xor     edx, edx; x
0x18008128b  mov     dword ptr [rsp+88h+lpBits], r15d; h
0x180081290  call    cs:__imp_PatBlt
0x180081296  mov     r8, cs:?g_hdcDst@@3PEAUHDC__@@EA; HDC
0x18008129d  or      edi, 1
0x1800812a0  mov     [rsp+88h+rop], edi; unsigned int
0x1800812a4  xor     r9d, r9d; int
0x1800812a7  mov     edx, esi; int
0x1800812a9  mov     dword ptr [rsp+88h+lpBits], r12d; int
0x1800812ae  mov     rcx, rbx; struct IImageList *
0x1800812b1  call    ?WimpyDraw@@YAJPEAUIImageList@@HPEAUHDC__@@HHI@Z; WimpyDraw(IImageList *,int,HDC__ *,int,int,uint)
0x1800812b6  xor     ecx, ecx; HBITMAP
0x1800812b8  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800812bd  lea     rcx, g_csDll; lpCriticalSection
0x1800812c4  call    cs:__imp_LeaveCriticalSection
0x1800812ca  lea     rcx, [rsp+88h+piconinfo]; piconinfo
0x1800812cf  mov     qword ptr [rsp+88h+piconinfo.fIcon], 1
0x1800812d8  mov     [rsp+88h+piconinfo.yHotspot], r12d
0x1800812dd  mov     [rsp+88h+piconinfo.hbmColor], rbp
0x1800812e2  mov     [rsp+88h+piconinfo.hbmMask], r13
0x1800812e7  call    cs:__imp_CreateIconIndirect
0x1800812ed  mov     rcx, r13; ho
0x1800812f0  mov     rbx, rax
0x1800812f3  call    cs:__imp_DeleteObject
0x1800812f9  mov     rcx, rbp; ho
0x1800812fc  call    cs:__imp_DeleteObject
0x180081302  mov     rax, [rsp+88h+arg_18]
0x18008130a  mov     [rax], rbx
0x18008130d  mov     eax, r12d
0x180081310  jmp     short loc_180081317
0x180081312  mov     eax, 80070057h
0x180081317  mov     rbx, [rsp+88h+arg_0]
0x18008131f  add     rsp, 50h
0x180081323  pop     r15
0x180081325  pop     r14
0x180081327  pop     r13
0x180081329  pop     r12
0x18008132b  pop     rdi
0x18008132c  pop     rsi
0x18008132d  pop     rbp
0x18008132e  retn
```
