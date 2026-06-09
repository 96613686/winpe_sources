# TV_GenerateDragImage(_TREE *,SHDRAGIMAGE *)

- ea: `0x18001d6e8`
- end: `0x18001d8ef`
- name: `?TV_GenerateDragImage@@YA_JPEAU_TREE@@PEAUSHDRAGIMAGE@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct _TREE *, struct SHDRAGIMAGE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x180007fc4`
- `0x18001aaf0`
- `0x18001d360`
- `0x18001d6e8`
- `0x180114520`

## import_xrefs

- `GDI32!SelectObject` at `0x18001d7fa`
- `GDI32!SelectObject` at `0x18001d8af`
- `GDI32!SelectObject` at `0x18001d7fa`
- `GDI32!SelectObject` at `0x18001d8af`
- `GDI32!DeleteDC` at `0x18001d8b8`
- `GDI32!DeleteDC` at `0x18001d8b8`
- `GDI32!CreateCompatibleDC` at `0x18001d72b`
- `GDI32!CreateCompatibleDC` at `0x18001d72b`
- `GDI32!SetLayout` at `0x18001d74e`
- `GDI32!SetLayout` at `0x18001d74e`
- `GDI32!CreateBitmap` at `0x18001d7cd`
- `GDI32!CreateBitmap` at `0x18001d7cd`
- `GDI32!GetDeviceCaps` at `0x18001d7a5`
- `GDI32!GetDeviceCaps` at `0x18001d7b5`
- `GDI32!GetDeviceCaps` at `0x18001d7a5`
- `GDI32!GetDeviceCaps` at `0x18001d7b5`

## pseudocode

```c
__int64 __fastcall TV_GenerateDragImage(struct _TREE *a1, struct SHDRAGIMAGE *a2)
{
  struct _TREEITEM *v2; // r15
  HDC CompatibleDC; // rax
  HDC v6; // rsi
  __int64 v7; // rbp
  LONG top; // ecx
  int v9; // r12d
  int v10; // r13d
  UINT DeviceCaps; // ebx
  UINT v12; // eax
  HBITMAP Bitmap; // rax
  HGDIOBJ v14; // rbp
  LONG v15; // r12d
  int v16; // ebx
  int v17; // r14d
  LONG v19; // [rsp+30h] [rbp-58h]
  RECT rect; // [rsp+38h] [rbp-50h] BYREF

  v2 = (struct _TREEITEM *)*((_QWORD *)a1 + 20);
  rect = 0;
  if ( !v2 )
    return 0;
  CompatibleDC = CreateCompatibleDC(0);
  v6 = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  v7 = 0;
  if ( (*((_DWORD *)a1 + 8) & 0x400000) != 0 )
    SetLayout(CompatibleDC, 1u);
  TV_GetItemRect(a1, v2, &rect, 2u);
  top = rect.top;
  v9 = rect.right + 4;
  v10 = rect.left - *((__int16 *)a1 + 174);
  v19 = rect.top;
  a2->sizeDragImage.cx = rect.right + 4 - v10;
  a2->sizeDragImage.cy = rect.bottom - top;
  DeviceCaps = GetDeviceCaps(v6, 12);
  v12 = GetDeviceCaps(v6, 14);
  Bitmap = CreateBitmap(a2->sizeDragImage.cx, a2->sizeDragImage.cy, v12, DeviceCaps, 0);
  a2->hbmpDragImage = Bitmap;
  if ( Bitmap )
  {
    rect.right = a2->sizeDragImage.cx;
    rect.bottom = a2->sizeDragImage.cy;
    *(_QWORD *)&rect.left = 0;
    v14 = SelectObject(v6, Bitmap);
    a2->crColorKey = -1;
    FillRectClr(v6, &rect, 0xFFFFFFFF);
    v15 = v9 - *((_DWORD *)a1 + 80);
    if ( (*((_DWORD *)a1 + 8) & 0x400000) == 0 )
      v15 = *((_DWORD *)a1 + 80) - v10;
    a2->ptOffset.x = v15;
    a2->ptOffset.y = *((_DWORD *)a1 + 81) - v19;
    v16 = *((_DWORD *)a1 + 82);
    v17 = *((_DWORD *)a1 + 83);
    *((_DWORD *)a1 + 83) = -1;
    if ( ((v16 + 1) & 0xFFFFFFFE) == 0 )
      *((_DWORD *)a1 + 82) = 65793;
    TV_DrawItem(a1, v2, v6, 0, 0, ((*((_DWORD *)a1 + 125) & 8) << 6) | 0x42);
    *((_DWORD *)a1 + 83) = v17;
    *((_DWORD *)a1 + 82) = v16;
    SelectObject(v6, v14);
    DeleteDC(v6);
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18001d6e8  mov     [rsp+arg_10], rbx
0x18001d6ed  push    rbp
0x18001d6ee  push    rsi
0x18001d6ef  push    rdi
0x18001d6f0  push    r12
0x18001d6f2  push    r13
0x18001d6f4  push    r14
0x18001d6f6  push    r15
0x18001d6f8  sub     rsp, 50h
0x18001d6fc  mov     rax, cs:__security_cookie
0x18001d703  xor     rax, rsp
0x18001d706  mov     [rsp+88h+var_40], rax
0x18001d70b  mov     r15, [rcx+0A0h]
0x18001d712  xorps   xmm0, xmm0
0x18001d715  mov     r14, rdx
0x18001d718  mov     rdi, rcx
0x18001d71b  movups  xmmword ptr [rsp+88h+rect.left], xmm0
0x18001d720  test    r15, r15
0x18001d723  jz      loc_18001D8C8
0x18001d729  xor     ecx, ecx; hdc
0x18001d72b  call    cs:__imp_CreateCompatibleDC
0x18001d731  mov     rsi, rax
0x18001d734  test    rax, rax
0x18001d737  jz      loc_18001D8C8
0x18001d73d  xor     ebp, ebp
0x18001d73f  test    dword ptr [rdi+20h], 400000h
0x18001d746  jz      short loc_18001D754
0x18001d748  lea     edx, [rbp+1]; l
0x18001d74b  mov     rcx, rax; hdc
0x18001d74e  call    cs:__imp_SetLayout
0x18001d754  mov     r9d, 2; unsigned int
0x18001d75a  lea     r8, [rsp+88h+rect]; struct tagRECT *
0x18001d75f  mov     rdx, r15; struct _TREEITEM *
0x18001d762  mov     rcx, rdi; struct _TREE *
0x18001d765  call    ?TV_GetItemRect@@YAHPEAU_TREE@@PEAU_TREEITEM@@PEAUtagRECT@@I@Z; TV_GetItemRect(_TREE *,_TREEITEM *,tagRECT *,uint)
0x18001d76a  movsx   eax, word ptr [rdi+15Ch]
0x18001d771  mov     edx, 0Ch; index
0x18001d776  mov     ecx, [rsp+88h+rect.top]
0x18001d77a  mov     r12d, [rsp+88h+rect.right]
0x18001d77f  mov     r13d, [rsp+88h+rect.left]
0x18001d784  add     r12d, 4
0x18001d788  sub     r13d, eax
0x18001d78b  mov     [rsp+88h+var_58], ecx
0x18001d78f  mov     eax, r12d
0x18001d792  sub     eax, r13d
0x18001d795  mov     [r14], eax
0x18001d798  mov     eax, [rsp+88h+rect.bottom]
0x18001d79c  sub     eax, ecx
0x18001d79e  mov     rcx, rsi; hdc
0x18001d7a1  mov     [r14+4], eax
0x18001d7a5  call    cs:__imp_GetDeviceCaps
0x18001d7ab  mov     edx, 0Eh; index
0x18001d7b0  mov     rcx, rsi; hdc
0x18001d7b3  mov     ebx, eax
0x18001d7b5  call    cs:__imp_GetDeviceCaps
0x18001d7bb  mov     edx, [r14+4]; nHeight
0x18001d7bf  mov     r9d, ebx; nBitCount
0x18001d7c2  mov     ecx, [r14]; nWidth
0x18001d7c5  mov     r8d, eax; nPlanes
0x18001d7c8  mov     [rsp+88h+lpBits], rbp; lpBits
0x18001d7cd  call    cs:__imp_CreateBitmap
0x18001d7d3  mov     [r14+10h], rax
0x18001d7d7  test    rax, rax
0x18001d7da  jz      loc_18001D8C3
0x18001d7e0  mov     ecx, [r14]
0x18001d7e3  mov     rdx, rax; h
0x18001d7e6  mov     [rsp+88h+rect.right], ecx
0x18001d7ea  mov     ecx, [r14+4]
0x18001d7ee  mov     [rsp+88h+rect.bottom], ecx
0x18001d7f2  mov     rcx, rsi; hdc
0x18001d7f5  mov     qword ptr [rsp+88h+rect.left], rbp
0x18001d7fa  call    cs:__imp_SelectObject
0x18001d800  lea     rdx, [rsp+88h+rect]; lprect
0x18001d805  mov     rcx, rsi; hdc
0x18001d808  mov     rbp, rax
0x18001d80b  or      eax, 0FFFFFFFFh
0x18001d80e  mov     r8d, eax; color
0x18001d811  mov     [r14+18h], eax
0x18001d815  call    FillRectClr
0x18001d81a  mov     ecx, [rdi+140h]
0x18001d820  sub     r12d, ecx
0x18001d823  mov     edx, ecx
0x18001d825  sub     edx, r13d
0x18001d828  test    dword ptr [rdi+20h], 400000h
0x18001d82f  cmovz   r12d, edx
0x18001d833  mov     [r14+8], r12d
0x18001d837  mov     eax, [rdi+144h]
0x18001d83d  sub     eax, [rsp+88h+var_58]
0x18001d841  mov     [r14+0Ch], eax
0x18001d845  mov     ebx, [rdi+148h]
0x18001d84b  mov     r14d, [rdi+14Ch]
0x18001d852  mov     dword ptr [rdi+14Ch], 0FFFFFFFFh
0x18001d85c  lea     eax, [rbx+1]
0x18001d85f  test    eax, 0FFFFFFFEh
0x18001d864  jnz     short loc_18001D870
0x18001d866  mov     dword ptr [rdi+148h], 10101h
0x18001d870  mov     eax, [rdi+1F4h]
0x18001d876  xor     r9d, r9d; int
0x18001d879  and     eax, 8
0x18001d87c  mov     r8, rsi; HDC
0x18001d87f  shl     eax, 6
0x18001d882  mov     rdx, r15; struct _TREEITEM *
0x18001d885  or      eax, 42h
0x18001d888  mov     rcx, rdi; struct _TREE *
0x18001d88b  mov     [rsp+88h+var_60], eax; unsigned int
0x18001d88f  mov     dword ptr [rsp+88h+lpBits], 0; int
0x18001d897  call    ?TV_DrawItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@PEAUHDC__@@HHI@Z; TV_DrawItem(_TREE *,_TREEITEM *,HDC__ *,int,int,uint)
0x18001d89c  mov     rdx, rbp; h
0x18001d89f  mov     [rdi+14Ch], r14d
0x18001d8a6  mov     rcx, rsi; hdc
0x18001d8a9  mov     [rdi+148h], ebx
0x18001d8af  call    cs:__imp_SelectObject
0x18001d8b5  mov     rcx, rsi; hdc
0x18001d8b8  call    cs:__imp_DeleteDC
0x18001d8be  mov     ebp, 1
0x18001d8c3  mov     rax, rbp
0x18001d8c6  jmp     short loc_18001D8CA
0x18001d8c8  xor     eax, eax
0x18001d8ca  mov     rcx, [rsp+88h+var_40]
0x18001d8cf  xor     rcx, rsp; StackCookie
0x18001d8d2  call    __security_check_cookie
0x18001d8d7  mov     rbx, [rsp+88h+arg_10]
0x18001d8df  add     rsp, 50h
0x18001d8e3  pop     r15
0x18001d8e5  pop     r14
0x18001d8e7  pop     r13
0x18001d8e9  pop     r12
0x18001d8eb  pop     rdi
0x18001d8ec  pop     rsi
0x18001d8ed  pop     rbp
0x18001d8ee  retn
```
