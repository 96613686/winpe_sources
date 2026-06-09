# CImageList::_ReAllocBitmaps(int)

- ea: `0x1800118a4`
- end: `0x180011bb0`
- name: `?_ReAllocBitmaps@CImageList@@IEAAJH@Z`
- size: `780`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e35c`
- `0x180010370`
- `0x180010578`
- `0x180010c30`
- `0x1800123c0`
- `0x18008dcf0`

## callees

- `0x1800107ec`
- `0x1800118a4`
- `0x180011bb8`
- `0x180011c10`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001194f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001194f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011961`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011961`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011987`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011987`
- `GDI32!DeleteObject` at `0x180011aa4`
- `GDI32!DeleteObject` at `0x180011ba5`
- `GDI32!DeleteObject` at `0x180011aa4`
- `GDI32!DeleteObject` at `0x180011ba5`
- `GDI32!SelectObject` at `0x1800119b7`
- `GDI32!SelectObject` at `0x1800119d2`
- `GDI32!SelectObject` at `0x1800119e7`
- `GDI32!SelectObject` at `0x1800119b7`
- `GDI32!SelectObject` at `0x1800119d2`
- `GDI32!SelectObject` at `0x1800119e7`
- `GDI32!CreateBitmap` at `0x180011a84`
- `GDI32!CreateBitmap` at `0x180011a84`
- `GDI32!BitBlt` at `0x180011b16`
- `GDI32!BitBlt` at `0x180011b60`
- `GDI32!BitBlt` at `0x180011b16`
- `GDI32!BitBlt` at `0x180011b60`

## pseudocode

```c
__int64 __fastcall CImageList::_ReAllocBitmaps(CImageList *this, int a2)
{
  int v3; // ebp
  int v4; // r12d
  _BYTE *v5; // r15
  HBITMAP Bitmap; // rdi
  HBITMAP v7; // r14
  int v8; // esi
  int v9; // esi
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  int v12; // esi
  HDC v13; // rcx
  HBITMAP v14; // rcx
  HBITMAP v15; // rcx
  HBITMAP v17; // rcx
  int v18; // esi
  int v19; // ecx
  struct tagRGBQUAD *v20; // [rsp+50h] [rbp-38h] BYREF

  v20 = 0;
  if ( a2 > 0 )
  {
    if ( *((_DWORD *)this + 30) >= a2 )
      return 0;
  }
  else
  {
    a2 = -a2;
  }
  v3 = a2 + *((_DWORD *)this + 31) - 1 - (a2 + *((_DWORD *)this + 31) - 1) % *((_DWORD *)this + 31);
  if ( v3 == *((_DWORD *)this + 30) )
    return 0;
  v4 = *((_DWORD *)this + 32);
  v5 = (char *)this + 136;
  Bitmap = 0;
  v7 = 0;
  if ( v3 <= 0 )
  {
LABEL_10:
    EnterCriticalSection(&g_csDll);
    v12 = *((_DWORD *)this + 29);
    if ( v12 > 0 )
    {
      if ( v3 < v12 )
        v12 = v3;
      v18 = *((_DWORD *)this + 33) * v12;
      if ( (*v5 & 1) != 0 )
      {
        CImageList::SelectDstBitmap(Bitmap);
        BitBlt(g_hdcDst, 0, 0, v4, v18, *((HDC *)this + 25), 0, 0, 0xCC0020u);
      }
      CImageList::SelectDstBitmap(v7);
      BitBlt(g_hdcDst, 0, 0, v4, v18, *((HDC *)this + 24), 0, 0, 0xCC0020u);
    }
    CImageList::SelectDstBitmap(0);
    if ( g_hbmSrc )
    {
      SelectObject(g_hdcSrc, g_hbmDcDeselect);
      g_hbmSrc = 0;
    }
    SelectObject(*((HDC *)this + 24), v7);
    v13 = (HDC)*((_QWORD *)this + 25);
    if ( v13 )
      SelectObject(v13, Bitmap);
    v14 = (HBITMAP)*((_QWORD *)this + 21);
    if ( v14 )
      CImageList::_DeleteBitmap(v14);
    v15 = (HBITMAP)*((_QWORD *)this + 20);
    if ( v15 )
      CImageList::_DeleteBitmap(v15);
    LeaveCriticalSection(&g_csDll);
    *((_QWORD *)this + 23) = v20;
    *((_QWORD *)this + 21) = Bitmap;
    *((_QWORD *)this + 20) = v7;
    *((_DWORD *)this + 35) = -1;
    *((_DWORD *)this + 30) = v3;
    return 0;
  }
  v8 = *((_DWORD *)this + 33) * v3;
  if ( (*v5 & 1) != 0 )
  {
    Bitmap = CreateBitmap(v4, v8, 1u, 1u, 0);
    if ( !Bitmap )
      return 2147942414LL;
  }
  v7 = CImageList::_CreateBitmap(this, v4, v8, &v20);
  if ( v7 )
  {
    if ( *((_QWORD *)this + 22) )
      goto LABEL_10;
    v9 = *((_DWORD *)this + 31);
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 8u, 0x20u);
    if ( v11 )
    {
      v19 = 0xFFFFFFF;
      v11[5] = 8;
      if ( v9 <= 0xFFFFFFF )
      {
        v19 = v9;
        if ( v9 <= 1 )
          v19 = 1;
      }
      v11[6] = v19;
    }
    *((_QWORD *)this + 22) = v11;
    if ( v11 )
      goto LABEL_10;
    if ( Bitmap )
      DeleteObject(Bitmap);
    v17 = v7;
  }
  else
  {
    if ( !Bitmap )
      return 2147942414LL;
    v17 = Bitmap;
  }
  DeleteObject(v17);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800118a4  mov     [rsp+arg_10], rbx
0x1800118a9  mov     [rsp+arg_18], rbp
0x1800118ae  push    rsi
0x1800118af  push    rdi
0x1800118b0  push    r12
0x1800118b2  push    r14
0x1800118b4  push    r15
0x1800118b6  sub     rsp, 60h
0x1800118ba  mov     rax, cs:__security_cookie
0x1800118c1  xor     rax, rsp
0x1800118c4  mov     [rsp+88h+var_30], rax
0x1800118c9  mov     [rsp+88h+var_38], 0
0x1800118d2  mov     rbx, rcx
0x1800118d5  test    edx, edx
0x1800118d7  jg      loc_180011A69
0x1800118dd  neg     edx
0x1800118df  mov     ecx, [rcx+7Ch]
0x1800118e2  lea     ebp, [rcx-1]
0x1800118e5  add     ebp, edx
0x1800118e7  mov     eax, ebp
0x1800118e9  cdq
0x1800118ea  idiv    ecx
0x1800118ec  sub     ebp, edx
0x1800118ee  cmp     ebp, [rbx+78h]
0x1800118f1  jz      loc_180011A41
0x1800118f7  mov     r12d, [rbx+80h]
0x1800118fe  lea     r15, [rbx+88h]
0x180011905  xor     edi, edi
0x180011907  xor     r14d, r14d
0x18001190a  lea     eax, [rdi+1]
0x18001190d  test    ebp, ebp
0x18001190f  jle     short loc_180011980
0x180011911  mov     esi, ebp
0x180011913  imul    esi, [rbx+84h]
0x18001191a  test    [r15], al
0x18001191d  jnz     loc_180011A74
0x180011923  lea     r9, [rsp+88h+var_38]; struct tagRGBQUAD **
0x180011928  mov     r8d, esi; int
0x18001192b  mov     edx, r12d; int
0x18001192e  mov     rcx, rbx; this
0x180011931  call    ?_CreateBitmap@CImageList@@IEAAPEAUHBITMAP__@@HHPEAPEAUtagRGBQUAD@@@Z; CImageList::_CreateBitmap(int,int,tagRGBQUAD * *)
0x180011936  mov     r14, rax
0x180011939  test    rax, rax
0x18001193c  jz      loc_180011B6B
0x180011942  cmp     qword ptr [rbx+0B0h], 0
0x18001194a  jnz     short loc_180011980
0x18001194c  mov     esi, [rbx+7Ch]
0x18001194f  call    cs:__imp_GetProcessHeap
0x180011955  mov     edx, 8; dwFlags
0x18001195a  mov     rcx, rax; hHeap
0x18001195d  lea     r8d, [rdx+18h]; dwBytes
0x180011961  call    cs:__imp_HeapAlloc
0x180011967  test    rax, rax
0x18001196a  jnz     loc_180011B90
0x180011970  mov     [rbx+0B0h], rax
0x180011977  test    rax, rax
0x18001197a  jz      loc_180011A98
0x180011980  lea     rcx, g_csDll; lpCriticalSection
0x180011987  call    cs:__imp_EnterCriticalSection
0x18001198d  mov     esi, [rbx+74h]
0x180011990  test    esi, esi
0x180011992  jg      loc_180011AC5
0x180011998  xor     ecx, ecx; HBITMAP
0x18001199a  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x18001199f  cmp     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmSrc
0x1800119a7  jz      short loc_1800119C8
0x1800119a9  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x1800119b0  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x1800119b7  call    cs:__imp_SelectObject
0x1800119bd  mov     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmSrc
0x1800119c8  mov     rcx, [rbx+0C0h]; hdc
0x1800119cf  mov     rdx, r14; h
0x1800119d2  call    cs:__imp_SelectObject
0x1800119d8  mov     rcx, [rbx+0C8h]; hdc
0x1800119df  test    rcx, rcx
0x1800119e2  jz      short loc_1800119ED
0x1800119e4  mov     rdx, rdi; h
0x1800119e7  call    cs:__imp_SelectObject
0x1800119ed  mov     rcx, [rbx+0A8h]; ho
0x1800119f4  test    rcx, rcx
0x1800119f7  jnz     loc_180011ABB
0x1800119fd  mov     rcx, [rbx+0A0h]; ho
0x180011a04  test    rcx, rcx
0x180011a07  jnz     loc_180011AB1
0x180011a0d  lea     rcx, g_csDll; lpCriticalSection
0x180011a14  call    cs:__imp_LeaveCriticalSection
0x180011a1a  mov     rax, [rsp+88h+var_38]
0x180011a1f  mov     [rbx+0B8h], rax
0x180011a26  mov     [rbx+0A8h], rdi
0x180011a2d  mov     [rbx+0A0h], r14
0x180011a34  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x180011a3e  mov     [rbx+78h], ebp
0x180011a41  xor     eax, eax
0x180011a43  mov     rcx, [rsp+88h+var_30]
0x180011a48  xor     rcx, rsp; StackCookie
0x180011a4b  call    __security_check_cookie
0x180011a50  lea     r11, [rsp+88h+var_28]
0x180011a55  mov     rbx, [r11+40h]
0x180011a59  mov     rbp, [r11+48h]
0x180011a5d  mov     rsp, r11
0x180011a60  pop     r15
0x180011a62  pop     r14
0x180011a64  pop     r12
0x180011a66  pop     rdi
0x180011a67  pop     rsi
0x180011a68  retn
0x180011a69  cmp     [rcx+78h], edx
0x180011a6c  jl      loc_1800118DF
0x180011a72  jmp     short loc_180011A41
0x180011a74  mov     r9d, eax; nBitCount
0x180011a77  mov     [rsp+88h+lpBits], rdi; lpBits
0x180011a7c  mov     r8d, eax; nPlanes
0x180011a7f  mov     edx, esi; nHeight
0x180011a81  mov     ecx, r12d; nWidth
0x180011a84  call    cs:__imp_CreateBitmap
0x180011a8a  mov     rdi, rax
0x180011a8d  test    rax, rax
0x180011a90  jnz     loc_180011923
0x180011a96  jmp     short loc_180011AAA
0x180011a98  test    rdi, rdi
0x180011a9b  jnz     loc_180011BA2
0x180011aa1  mov     rcx, r14; ho
0x180011aa4  call    cs:__imp_DeleteObject
0x180011aaa  mov     eax, 8007000Eh
0x180011aaf  jmp     short loc_180011A43
0x180011ab1  call    ?_DeleteBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x180011ab6  jmp     loc_180011A0D
0x180011abb  call    ?_DeleteBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x180011ac0  jmp     loc_1800119FD
0x180011ac5  cmp     ebp, esi
0x180011ac7  cmovl   esi, ebp
0x180011aca  imul    esi, [rbx+84h]
0x180011ad1  test    byte ptr [r15], 1
0x180011ad5  jnz     short loc_180011B21
0x180011ad7  mov     rcx, r14; HBITMAP
0x180011ada  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180011adf  mov     rax, [rbx+0C0h]
0x180011ae6  mov     r9d, r12d; cx
0x180011ae9  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180011af0  xor     r8d, r8d; y
0x180011af3  mov     [rsp+88h+rop], 0CC0020h; rop
0x180011afb  xor     edx, edx; x
0x180011afd  mov     [rsp+88h+y1], 0; y1
0x180011b05  mov     [rsp+88h+x1], 0; x1
0x180011b0d  mov     [rsp+88h+hdcSrc], rax; hdcSrc
0x180011b12  mov     dword ptr [rsp+88h+lpBits], esi; cy
0x180011b16  call    cs:__imp_BitBlt
0x180011b1c  jmp     loc_180011998
0x180011b21  mov     rcx, rdi; HBITMAP
0x180011b24  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180011b29  mov     rax, [rbx+0C8h]
0x180011b30  mov     r9d, r12d; cx
0x180011b33  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180011b3a  xor     r8d, r8d; y
0x180011b3d  mov     [rsp+88h+rop], 0CC0020h; rop
0x180011b45  xor     edx, edx; x
0x180011b47  mov     [rsp+88h+y1], 0; y1
0x180011b4f  mov     [rsp+88h+x1], 0; x1
0x180011b57  mov     [rsp+88h+hdcSrc], rax; hdcSrc
0x180011b5c  mov     dword ptr [rsp+88h+lpBits], esi; cy
0x180011b60  call    cs:__imp_BitBlt
0x180011b66  jmp     loc_180011AD7
0x180011b6b  test    rdi, rdi
0x180011b6e  jz      loc_180011AAA
0x180011b74  mov     rcx, rdi
0x180011b77  jmp     loc_180011AA4
0x180011b7c  mov     ecx, esi
0x180011b7e  cmp     esi, 1
0x180011b81  jg      short loc_180011B88
0x180011b83  mov     ecx, 1
0x180011b88  mov     [rax+18h], ecx
0x180011b8b  jmp     loc_180011970
0x180011b90  mov     ecx, 0FFFFFFFh
0x180011b95  mov     dword ptr [rax+14h], 8
0x180011b9c  cmp     esi, ecx
0x180011b9e  jg      short loc_180011B88
0x180011ba0  jmp     short loc_180011B7C
0x180011ba2  mov     rcx, rdi; ho
0x180011ba5  call    cs:__imp_DeleteObject
0x180011bab  jmp     loc_180011AA1
```
