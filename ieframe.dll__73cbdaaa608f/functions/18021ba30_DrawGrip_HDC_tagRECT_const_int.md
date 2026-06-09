# DrawGrip(HDC__ *,tagRECT const *,int)

- ea: `0x18021ba30`
- end: `0x18021bc8f`
- name: `?DrawGrip@@YAHPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `607`
- prototype: `__int64 __fastcall(HDC hdc, const struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180220680`

## callees

- `0x18021ba30`

## import_xrefs

- `GDI32!PatBlt` at `0x18021bad6`
- `GDI32!PatBlt` at `0x18021bad6`
- `GDI32!CreatePen` at `0x18021bafd`
- `GDI32!CreatePen` at `0x18021bb78`
- `GDI32!CreatePen` at `0x18021bbed`
- `GDI32!CreatePen` at `0x18021bafd`
- `GDI32!CreatePen` at `0x18021bb78`
- `GDI32!CreatePen` at `0x18021bbed`
- `GDI32!DeleteObject` at `0x18021bb63`
- `GDI32!DeleteObject` at `0x18021bbd7`
- `GDI32!DeleteObject` at `0x18021bc6d`
- `GDI32!DeleteObject` at `0x18021bb63`
- `GDI32!DeleteObject` at `0x18021bbd7`
- `GDI32!DeleteObject` at `0x18021bc6d`
- `GDI32!SelectObject` at `0x18021baab`
- `GDI32!SelectObject` at `0x18021bae2`
- `GDI32!SelectObject` at `0x18021bb15`
- `GDI32!SelectObject` at `0x18021bb5a`
- `GDI32!SelectObject` at `0x18021bb90`
- `GDI32!SelectObject` at `0x18021bbce`
- `GDI32!SelectObject` at `0x18021bc01`
- `GDI32!SelectObject` at `0x18021bc64`
- `GDI32!SelectObject` at `0x18021baab`
- `GDI32!SelectObject` at `0x18021bae2`
- `GDI32!SelectObject` at `0x18021bb15`
- `GDI32!SelectObject` at `0x18021bb5a`
- `GDI32!SelectObject` at `0x18021bb90`
- `GDI32!SelectObject` at `0x18021bbce`
- `GDI32!SelectObject` at `0x18021bc01`
- `GDI32!SelectObject` at `0x18021bc64`
- `GDI32!MoveToEx` at `0x18021bb35`
- `GDI32!MoveToEx` at `0x18021bba9`
- `GDI32!MoveToEx` at `0x18021bc1f`
- `GDI32!MoveToEx` at `0x18021bc3f`
- `GDI32!MoveToEx` at `0x18021bb35`
- `GDI32!MoveToEx` at `0x18021bba9`
- `GDI32!MoveToEx` at `0x18021bc1f`
- `GDI32!MoveToEx` at `0x18021bc3f`
- `GDI32!LineTo` at `0x18021bb43`
- `GDI32!LineTo` at `0x18021bbb7`
- `GDI32!LineTo` at `0x18021bc2d`
- `GDI32!LineTo` at `0x18021bc4e`
- `GDI32!LineTo` at `0x18021bb43`
- `GDI32!LineTo` at `0x18021bbb7`
- `GDI32!LineTo` at `0x18021bc2d`
- `GDI32!LineTo` at `0x18021bc4e`
- `USER32!GetSysColor` at `0x18021ba86`
- `USER32!GetSysColor` at `0x18021ba97`
- `USER32!GetSysColor` at `0x18021baed`
- `USER32!GetSysColor` at `0x18021ba86`
- `USER32!GetSysColor` at `0x18021ba97`
- `USER32!GetSysColor` at `0x18021baed`
- `USER32!GetSysColorBrush` at `0x18021ba79`
- `USER32!GetSysColorBrush` at `0x18021ba79`

## pseudocode

```c
__int64 __fastcall DrawGrip(HDC hdc, const struct tagRECT *a2, int a3)
{
  LONG top; // r11d
  int v5; // eax
  int v8; // ebp
  int v9; // r12d
  HBRUSH SysColorBrush; // r14
  HGDIOBJ v11; // rbx
  COLORREF v12; // eax
  HPEN Pen; // rax
  HPEN v14; // r15
  HGDIOBJ v15; // r13
  int v16; // r14d
  int i; // ebx
  HPEN v18; // rax
  HPEN v19; // r14
  HGDIOBJ v20; // rax
  LONG v21; // r15d
  void *v22; // r13
  LONG j; // ebx
  HPEN v24; // rax
  HPEN v25; // r14
  HGDIOBJ v26; // r15
  int v27; // ebx
  int v28; // edi
  DWORD SysColor; // [rsp+78h] [rbp+10h]
  DWORD color; // [rsp+80h] [rbp+18h]

  top = a2->top;
  v5 = a2->right - a2->left;
  if ( v5 >= a2->bottom - top )
    v5 = a2->bottom - top;
  v8 = v5 + a2->left;
  v9 = v5 + top;
  SysColorBrush = GetSysColorBrush(15);
  color = GetSysColor(20);
  SysColor = GetSysColor(16);
  if ( a3 )
  {
    v11 = SelectObject(hdc, SysColorBrush);
    PatBlt(hdc, a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 0xF00021u);
    SelectObject(hdc, v11);
  }
  else
  {
    v12 = GetSysColor(15);
    Pen = CreatePen(0, 1, v12);
    v14 = Pen;
    if ( !Pen )
      return 0;
    v15 = SelectObject(hdc, Pen);
    v16 = a2->top + 3;
    for ( i = a2->left + 3; i < v8; i += 4 )
    {
      MoveToEx(hdc, i, v9, 0);
      LineTo(hdc, v8, v16);
      v16 += 4;
    }
    SelectObject(hdc, v15);
    DeleteObject(v14);
  }
  v18 = CreatePen(0, 1, color);
  v19 = v18;
  if ( !v18 )
    return 0;
  v20 = SelectObject(hdc, v18);
  v21 = a2->top;
  v22 = v20;
  for ( j = a2->left; j < v8; j += 4 )
  {
    MoveToEx(hdc, j, v9, 0);
    LineTo(hdc, v8, v21);
    v21 += 4;
  }
  SelectObject(hdc, v22);
  DeleteObject(v19);
  v24 = CreatePen(0, 1, SysColor);
  v25 = v24;
  if ( !v24 )
    return 0;
  v26 = SelectObject(hdc, v24);
  v27 = a2->left + 1;
  v28 = a2->top + 1;
  while ( v27 < v8 )
  {
    MoveToEx(hdc, v27, v9, 0);
    LineTo(hdc, v8, v28);
    MoveToEx(hdc, v27 + 1, v9, 0);
    LineTo(hdc, v8, v28 + 1);
    v27 += 4;
    v28 += 4;
  }
  SelectObject(hdc, v26);
  DeleteObject(v25);
  return 1;
}

```

## disassembly

```asm
0x18021ba30  mov     [rsp+arg_0], rbx
0x18021ba35  push    rbp
0x18021ba36  push    rsi
0x18021ba37  push    rdi
0x18021ba38  push    r12
0x18021ba3a  push    r13
0x18021ba3c  push    r14
0x18021ba3e  push    r15
0x18021ba40  sub     rsp, 30h
0x18021ba44  mov     r11d, [rdx+4]
0x18021ba48  mov     rsi, rcx
0x18021ba4b  mov     r9d, [rdx]
0x18021ba4e  mov     r15d, 0Fh
0x18021ba54  mov     r10d, [rdx+0Ch]
0x18021ba58  mov     ecx, r15d; nIndex
0x18021ba5b  mov     eax, [rdx+8]
0x18021ba5e  sub     r10d, r11d
0x18021ba61  sub     eax, r9d
0x18021ba64  mov     ebx, r8d
0x18021ba67  cmp     eax, r10d
0x18021ba6a  mov     rdi, rdx
0x18021ba6d  cmovge  eax, r10d
0x18021ba71  lea     ebp, [rax+r9]
0x18021ba75  lea     r12d, [rax+r11]
0x18021ba79  call    cs:__imp_GetSysColorBrush
0x18021ba7f  lea     ecx, [r15+5]; nIndex
0x18021ba83  mov     r14, rax
0x18021ba86  call    cs:__imp_GetSysColor
0x18021ba8c  lea     ecx, [r15+1]; nIndex
0x18021ba90  mov     [rsp+68h+color], eax
0x18021ba97  call    cs:__imp_GetSysColor
0x18021ba9d  mov     [rsp+68h+arg_8], eax
0x18021baa1  test    ebx, ebx
0x18021baa3  jz      short loc_18021BAEA
0x18021baa5  mov     rdx, r14; h
0x18021baa8  mov     rcx, rsi; hdc
0x18021baab  call    cs:__imp_SelectObject
0x18021bab1  mov     ecx, [rdi+0Ch]
0x18021bab4  mov     rbx, rax
0x18021bab7  mov     r8d, [rdi+4]; y
0x18021babb  sub     ecx, r8d
0x18021babe  mov     r9d, [rdi+8]
0x18021bac2  sub     r9d, [rdi]; w
0x18021bac5  mov     edx, [rdi]; x
0x18021bac7  mov     [rsp+68h+rop], 0F00021h; rop
0x18021bacf  mov     [rsp+68h+h], ecx; h
0x18021bad3  mov     rcx, rsi; hdc
0x18021bad6  call    cs:__imp_PatBlt
0x18021badc  mov     rdx, rbx; h
0x18021badf  mov     rcx, rsi; hdc
0x18021bae2  call    cs:__imp_SelectObject
0x18021bae8  jmp     short loc_18021BB69
0x18021baea  mov     ecx, r15d; nIndex
0x18021baed  call    cs:__imp_GetSysColor
0x18021baf3  mov     edx, 1; cWidth
0x18021baf8  xor     ecx, ecx; iStyle
0x18021bafa  mov     r8d, eax; color
0x18021bafd  call    cs:__imp_CreatePen
0x18021bb03  mov     r15, rax
0x18021bb06  test    rax, rax
0x18021bb09  jz      loc_18021BC78
0x18021bb0f  mov     rdx, rax; h
0x18021bb12  mov     rcx, rsi; hdc
0x18021bb15  call    cs:__imp_SelectObject
0x18021bb1b  mov     r14d, [rdi+4]
0x18021bb1f  mov     r13, rax
0x18021bb22  mov     ebx, [rdi]
0x18021bb24  add     r14d, 3
0x18021bb28  add     ebx, 3
0x18021bb2b  jmp     short loc_18021BB50
0x18021bb2d  xor     r9d, r9d; lppt
0x18021bb30  mov     r8d, r12d; y
0x18021bb33  mov     edx, ebx; x
0x18021bb35  call    cs:__imp_MoveToEx
0x18021bb3b  mov     r8d, r14d; y
0x18021bb3e  mov     edx, ebp; x
0x18021bb40  mov     rcx, rsi; hdc
0x18021bb43  call    cs:__imp_LineTo
0x18021bb49  add     ebx, 4
0x18021bb4c  add     r14d, 4
0x18021bb50  mov     rcx, rsi; hdc
0x18021bb53  cmp     ebx, ebp
0x18021bb55  jl      short loc_18021BB2D
0x18021bb57  mov     rdx, r13; h
0x18021bb5a  call    cs:__imp_SelectObject
0x18021bb60  mov     rcx, r15; ho
0x18021bb63  call    cs:__imp_DeleteObject
0x18021bb69  mov     r8d, [rsp+68h+color]; color
0x18021bb71  mov     edx, 1; cWidth
0x18021bb76  xor     ecx, ecx; iStyle
0x18021bb78  call    cs:__imp_CreatePen
0x18021bb7e  mov     r14, rax
0x18021bb81  test    rax, rax
0x18021bb84  jz      loc_18021BC78
0x18021bb8a  mov     rdx, rax; h
0x18021bb8d  mov     rcx, rsi; hdc
0x18021bb90  call    cs:__imp_SelectObject
0x18021bb96  mov     r15d, [rdi+4]
0x18021bb9a  mov     r13, rax
0x18021bb9d  mov     ebx, [rdi]
0x18021bb9f  jmp     short loc_18021BBC4
0x18021bba1  xor     r9d, r9d; lppt
0x18021bba4  mov     r8d, r12d; y
0x18021bba7  mov     edx, ebx; x
0x18021bba9  call    cs:__imp_MoveToEx
0x18021bbaf  mov     r8d, r15d; y
0x18021bbb2  mov     edx, ebp; x
0x18021bbb4  mov     rcx, rsi; hdc
0x18021bbb7  call    cs:__imp_LineTo
0x18021bbbd  add     ebx, 4
0x18021bbc0  add     r15d, 4
0x18021bbc4  mov     rcx, rsi; hdc
0x18021bbc7  cmp     ebx, ebp
0x18021bbc9  jl      short loc_18021BBA1
0x18021bbcb  mov     rdx, r13; h
0x18021bbce  call    cs:__imp_SelectObject
0x18021bbd4  mov     rcx, r14; ho
0x18021bbd7  call    cs:__imp_DeleteObject
0x18021bbdd  mov     r8d, [rsp+68h+arg_8]; color
0x18021bbe2  mov     r13d, 1
0x18021bbe8  mov     edx, r13d; cWidth
0x18021bbeb  xor     ecx, ecx; iStyle
0x18021bbed  call    cs:__imp_CreatePen
0x18021bbf3  mov     r14, rax
0x18021bbf6  test    rax, rax
0x18021bbf9  jz      short loc_18021BC78
0x18021bbfb  mov     rdx, rax; h
0x18021bbfe  mov     rcx, rsi; hdc
0x18021bc01  call    cs:__imp_SelectObject
0x18021bc07  mov     ebx, [rdi]
0x18021bc09  mov     r15, rax
0x18021bc0c  mov     edi, [rdi+4]
0x18021bc0f  add     ebx, r13d
0x18021bc12  add     edi, r13d
0x18021bc15  jmp     short loc_18021BC5A
0x18021bc17  xor     r9d, r9d; lppt
0x18021bc1a  mov     r8d, r12d; y
0x18021bc1d  mov     edx, ebx; x
0x18021bc1f  call    cs:__imp_MoveToEx
0x18021bc25  mov     r8d, edi; y
0x18021bc28  mov     edx, ebp; x
0x18021bc2a  mov     rcx, rsi; hdc
0x18021bc2d  call    cs:__imp_LineTo
0x18021bc33  xor     r9d, r9d; lppt
0x18021bc36  lea     edx, [rbx+1]; x
0x18021bc39  mov     r8d, r12d; y
0x18021bc3c  mov     rcx, rsi; hdc
0x18021bc3f  call    cs:__imp_MoveToEx
0x18021bc45  lea     r8d, [rdi+1]; y
0x18021bc49  mov     edx, ebp; x
0x18021bc4b  mov     rcx, rsi; hdc
0x18021bc4e  call    cs:__imp_LineTo
0x18021bc54  add     ebx, 4
0x18021bc57  add     edi, 4
0x18021bc5a  mov     rcx, rsi; hdc
0x18021bc5d  cmp     ebx, ebp
0x18021bc5f  jl      short loc_18021BC17
0x18021bc61  mov     rdx, r15; h
0x18021bc64  call    cs:__imp_SelectObject
0x18021bc6a  mov     rcx, r14; ho
0x18021bc6d  call    cs:__imp_DeleteObject
0x18021bc73  mov     eax, r13d
0x18021bc76  jmp     short loc_18021BC7A
0x18021bc78  xor     eax, eax
0x18021bc7a  mov     rbx, [rsp+68h+arg_0]
0x18021bc7f  add     rsp, 30h
0x18021bc83  pop     r15
0x18021bc85  pop     r14
0x18021bc87  pop     r13
0x18021bc89  pop     r12
0x18021bc8b  pop     rdi
0x18021bc8c  pop     rsi
0x18021bc8d  pop     rbp
0x18021bc8e  retn
```
