# DrawX(HDC__ *,tagRECT)

- ea: `0x140044bc4`
- end: `0x140044cad`
- name: `?DrawX@@YAXPEAUHDC__@@UtagRECT@@@Z`
- size: `233`
- prototype: `void __fastcall(HDC, struct tagRECT *__struct_ptr)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140044cb0`

## callees

- `0x140001020`

## import_xrefs

- `gdiplus!GdipSetSmoothingMode` at `0x140044bfd`
- `gdiplus!GdipSetSmoothingMode` at `0x140044bfd`
- `gdiplus!GdipDeleteGraphics` at `0x140044c89`
- `gdiplus!GdipDeleteGraphics` at `0x140044c89`
- `gdiplus!GdipCreateFromHDC` at `0x140044bef`
- `gdiplus!GdipCreateFromHDC` at `0x140044bef`
- `gdiplus!GdipDeletePen` at `0x140044c7e`
- `gdiplus!GdipDeletePen` at `0x140044c7e`
- `gdiplus!GdipCreatePen1` at `0x140044c22`
- `gdiplus!GdipCreatePen1` at `0x140044c22`
- `gdiplus!GdipDrawLineI` at `0x140044c54`
- `gdiplus!GdipDrawLineI` at `0x140044c73`
- `gdiplus!GdipDrawLineI` at `0x140044c54`
- `gdiplus!GdipDrawLineI` at `0x140044c73`

## pseudocode

```c
void __fastcall DrawX(HDC a1, struct tagRECT *a2)
{
  __int64 v3; // rdx
  int v4; // eax
  int v5; // edi
  LONG left; // ebx
  unsigned int v7; // esi
  __int64 top; // r9
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h]

  v10 = 0;
  GdipCreateFromHDC(a1, &v10);
  GdipSetSmoothingMode(v10, 4);
  v12 = 0;
  v11 = 0;
  v4 = GdipCreatePen1(4294901502LL, v3, 0, &v11);
  v5 = a2->bottom - 1;
  left = a2->left;
  v7 = a2->right - 1;
  top = (unsigned int)a2->top;
  v9 = (unsigned int)a2->left;
  LODWORD(v12) = v4;
  GdipDrawLineI(v10, v11, v9, top, v7, v5);
  GdipDrawLineI(v10, v11, v7, (unsigned int)a2->top, left, v5);
  GdipDeletePen(v11);
  GdipDeleteGraphics(v10);
}

```

## disassembly

```asm
0x140044bc4  mov     [rsp+arg_10], rbx
0x140044bc9  push    rsi
0x140044bca  push    rdi
0x140044bcb  push    r14
0x140044bcd  sub     rsp, 50h
0x140044bd1  mov     rax, cs:__security_cookie
0x140044bd8  xor     rax, rsp
0x140044bdb  mov     [rsp+68h+var_20], rax
0x140044be0  mov     r14, rdx
0x140044be3  xor     ebx, ebx
0x140044be5  lea     rdx, [rsp+68h+var_38]
0x140044bea  mov     [rsp+68h+var_38], rbx
0x140044bef  call    cs:__imp_GdipCreateFromHDC
0x140044bf5  mov     rcx, [rsp+68h+var_38]
0x140044bfa  lea     edx, [rbx+4]
0x140044bfd  call    cs:__imp_GdipSetSmoothingMode
0x140044c03  movss   xmm1, cs:__real@40000000
0x140044c0b  lea     r9, [rsp+68h+var_30]
0x140044c10  xor     r8d, r8d
0x140044c13  mov     [rsp+68h+var_28], rbx
0x140044c18  mov     ecx, 0FFFEFEFEh
0x140044c1d  mov     [rsp+68h+var_30], rbx
0x140044c22  call    cs:__imp_GdipCreatePen1
0x140044c28  mov     edi, [r14+0Ch]
0x140044c2c  mov     esi, [r14+8]
0x140044c30  dec     edi
0x140044c32  mov     ebx, [r14]
0x140044c35  dec     esi
0x140044c37  mov     r9d, [r14+4]
0x140044c3b  mov     r8d, ebx
0x140044c3e  mov     rdx, [rsp+68h+var_30]
0x140044c43  mov     rcx, [rsp+68h+var_38]
0x140044c48  mov     [rsp+68h+var_40], edi
0x140044c4c  mov     [rsp+68h+var_48], esi
0x140044c50  mov     dword ptr [rsp+68h+var_28], eax
0x140044c54  call    cs:__imp_GdipDrawLineI
0x140044c5a  mov     r9d, [r14+4]
0x140044c5e  mov     r8d, esi
0x140044c61  mov     rdx, [rsp+68h+var_30]
0x140044c66  mov     rcx, [rsp+68h+var_38]
0x140044c6b  mov     [rsp+68h+var_40], edi
0x140044c6f  mov     [rsp+68h+var_48], ebx
0x140044c73  call    cs:__imp_GdipDrawLineI
0x140044c79  mov     rcx, [rsp+68h+var_30]
0x140044c7e  call    cs:__imp_GdipDeletePen
0x140044c84  mov     rcx, [rsp+68h+var_38]
0x140044c89  call    cs:__imp_GdipDeleteGraphics
0x140044c8f  mov     rcx, [rsp+68h+var_20]
0x140044c94  xor     rcx, rsp; StackCookie
0x140044c97  call    __security_check_cookie
0x140044c9c  mov     rbx, [rsp+68h+arg_10]
0x140044ca4  add     rsp, 50h
0x140044ca8  pop     r14
0x140044caa  pop     rdi
0x140044cab  pop     rsi
0x140044cac  retn
```
