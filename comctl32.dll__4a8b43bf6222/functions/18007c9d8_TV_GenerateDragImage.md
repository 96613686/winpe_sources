# TV_GenerateDragImage

- ea: `0x18007c9d8`
- end: `0x18007cbba`
- name: `TV_GenerateDragImage`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006bbb0`

## callees

- `0x1800115f0`
- `0x180042570`
- `0x180068edc`
- `0x18007b99c`
- `0x18007c9d8`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18007ca1b`
- `GDI32!CreateCompatibleDC` at `0x18007ca1b`
- `GDI32!SelectObject` at `0x18007caf1`
- `GDI32!SelectObject` at `0x18007cb7d`
- `GDI32!SelectObject` at `0x18007caf1`
- `GDI32!SelectObject` at `0x18007cb7d`
- `GDI32!GetDeviceCaps` at `0x18007ca96`
- `GDI32!GetDeviceCaps` at `0x18007caa6`
- `GDI32!GetDeviceCaps` at `0x18007ca96`
- `GDI32!GetDeviceCaps` at `0x18007caa6`
- `GDI32!SetLayout` at `0x18007ca3e`
- `GDI32!SetLayout` at `0x18007ca3e`
- `GDI32!DeleteDC` at `0x18007cb86`
- `GDI32!DeleteDC` at `0x18007cb86`
- `GDI32!CreateBitmap` at `0x18007cabf`
- `GDI32!CreateBitmap` at `0x18007cabf`

## pseudocode

```c
__int64 __fastcall TV_GenerateDragImage(__int64 a1, __int64 a2)
{
  __int64 v2; // r13
  HDC CompatibleDC; // rax
  HDC v6; // r14
  int v7; // r8d
  LONG right; // r15d
  int v9; // esi
  LONG top; // eax
  int v11; // edi
  UINT DeviceCaps; // ebx
  UINT v13; // eax
  HBITMAP Bitmap; // rax
  HGDIOBJ v15; // rdi
  int v16; // ecx
  int v17; // r15d
  int v18; // ebx
  int v20; // [rsp+30h] [rbp-58h]
  LONG v21; // [rsp+34h] [rbp-54h]
  RECT rect; // [rsp+38h] [rbp-50h] BYREF

  v2 = *(_QWORD *)(a1 + 136);
  rect = 0;
  if ( !v2 )
    return 0;
  CompatibleDC = CreateCompatibleDC(0);
  v6 = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  if ( (*(_DWORD *)(a1 + 32) & 0x400000) != 0 )
    SetLayout(CompatibleDC, 1u);
  TV_GetItemRect(a1, v2, &rect, 1);
  v7 = *(__int16 *)(a1 + 296);
  right = rect.right;
  v9 = rect.right - (rect.left - v7);
  v20 = rect.left - v7;
  top = rect.top;
  v11 = rect.bottom - rect.top;
  *(_DWORD *)(a2 + 4) = rect.bottom - rect.top;
  *(_DWORD *)a2 = v9;
  v21 = top;
  DeviceCaps = GetDeviceCaps(v6, 12);
  v13 = GetDeviceCaps(v6, 14);
  Bitmap = CreateBitmap(v9, v11, v13, DeviceCaps, 0);
  *(_QWORD *)(a2 + 16) = Bitmap;
  if ( !Bitmap )
    return 0;
  rect.right = *(_DWORD *)a2;
  rect.bottom = *(_DWORD *)(a2 + 4);
  *(_QWORD *)&rect.left = 0;
  v15 = SelectObject(v6, Bitmap);
  *(_DWORD *)(a2 + 24) = 244;
  FillRectClr(v6, &rect, 0xF4u);
  v16 = *(_DWORD *)(a1 + 272);
  if ( (*(_DWORD *)(a1 + 32) & 0x400000) != 0 )
    v17 = right - v16;
  else
    v17 = v16 - v20;
  *(_DWORD *)(a2 + 8) = v17;
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 276) - v21;
  v18 = *(_DWORD *)(a1 + 284);
  *(_DWORD *)(a1 + 284) = 244;
  TV_DrawItem(a1, v2, v6, 0, 0, 198);
  *(_DWORD *)(a1 + 284) = v18;
  SelectObject(v6, v15);
  DeleteDC(v6);
  return 1;
}

```

## disassembly

```asm
0x18007c9d8  mov     [rsp+arg_10], rbx
0x18007c9dd  push    rbp
0x18007c9de  push    rsi
0x18007c9df  push    rdi
0x18007c9e0  push    r12
0x18007c9e2  push    r13
0x18007c9e4  push    r14
0x18007c9e6  push    r15
0x18007c9e8  sub     rsp, 50h
0x18007c9ec  mov     rax, cs:__security_cookie
0x18007c9f3  xor     rax, rsp
0x18007c9f6  mov     [rsp+88h+var_40], rax
0x18007c9fb  mov     r13, [rcx+88h]
0x18007ca02  xorps   xmm0, xmm0
0x18007ca05  mov     r12, rdx
0x18007ca08  mov     rbp, rcx
0x18007ca0b  movups  xmmword ptr [rsp+88h+rect.left], xmm0
0x18007ca10  test    r13, r13
0x18007ca13  jz      loc_18007CB93
0x18007ca19  xor     ecx, ecx; hdc
0x18007ca1b  call    cs:__imp_CreateCompatibleDC
0x18007ca21  mov     r14, rax
0x18007ca24  test    rax, rax
0x18007ca27  jz      loc_18007CB93
0x18007ca2d  test    dword ptr [rbp+20h], 400000h
0x18007ca34  jz      short loc_18007CA44
0x18007ca36  mov     edx, 1; l
0x18007ca3b  mov     rcx, rax; hdc
0x18007ca3e  call    cs:__imp_SetLayout
0x18007ca44  mov     r9d, 1
0x18007ca4a  lea     r8, [rsp+88h+rect]
0x18007ca4f  mov     rdx, r13
0x18007ca52  mov     rcx, rbp
0x18007ca55  call    TV_GetItemRect
0x18007ca5a  movsx   r8d, word ptr [rbp+128h]
0x18007ca62  mov     edx, 0Ch; index
0x18007ca67  mov     eax, [rsp+88h+rect.left]
0x18007ca6b  mov     rcx, r14; hdc
0x18007ca6e  mov     r15d, [rsp+88h+rect.right]
0x18007ca73  sub     eax, r8d
0x18007ca76  mov     edi, [rsp+88h+rect.bottom]
0x18007ca7a  mov     esi, r15d
0x18007ca7d  sub     esi, eax
0x18007ca7f  mov     [rsp+88h+var_58], eax
0x18007ca83  mov     eax, [rsp+88h+rect.top]
0x18007ca87  sub     edi, eax
0x18007ca89  mov     [r12+4], edi
0x18007ca8e  mov     [r12], esi
0x18007ca92  mov     [rsp+88h+var_54], eax
0x18007ca96  call    cs:__imp_GetDeviceCaps
0x18007ca9c  mov     edx, 0Eh; index
0x18007caa1  mov     rcx, r14; hdc
0x18007caa4  mov     ebx, eax
0x18007caa6  call    cs:__imp_GetDeviceCaps
0x18007caac  mov     r9d, ebx; nBitCount
0x18007caaf  mov     [rsp+88h+lpBits], 0; lpBits
0x18007cab8  mov     r8d, eax; nPlanes
0x18007cabb  mov     edx, edi; nHeight
0x18007cabd  mov     ecx, esi; nWidth
0x18007cabf  call    cs:__imp_CreateBitmap
0x18007cac5  xor     esi, esi
0x18007cac7  mov     [r12+10h], rax
0x18007cacc  test    rax, rax
0x18007cacf  jz      loc_18007CB93
0x18007cad5  mov     ecx, [r12]
0x18007cad9  mov     rdx, rax; h
0x18007cadc  mov     [rsp+88h+rect.right], ecx
0x18007cae0  mov     ecx, [r12+4]
0x18007cae5  mov     [rsp+88h+rect.bottom], ecx
0x18007cae9  mov     rcx, r14; hdc
0x18007caec  mov     qword ptr [rsp+88h+rect.left], rsi
0x18007caf1  call    cs:__imp_SelectObject
0x18007caf7  lea     rdx, [rsp+88h+rect]; lprect
0x18007cafc  mov     rcx, r14; hdc
0x18007caff  mov     rdi, rax
0x18007cb02  mov     eax, 0F4h
0x18007cb07  mov     r8d, eax; color
0x18007cb0a  mov     [r12+18h], eax
0x18007cb0f  call    FillRectClr
0x18007cb14  test    dword ptr [rbp+20h], 400000h
0x18007cb1b  mov     ecx, [rbp+110h]
0x18007cb21  jz      short loc_18007CB28
0x18007cb23  sub     r15d, ecx
0x18007cb26  jmp     short loc_18007CB30
0x18007cb28  mov     r15d, ecx
0x18007cb2b  sub     r15d, [rsp+88h+var_58]
0x18007cb30  mov     [r12+8], r15d
0x18007cb35  xor     r9d, r9d
0x18007cb38  mov     eax, [rbp+114h]
0x18007cb3e  mov     r8, r14
0x18007cb41  sub     eax, [rsp+88h+var_54]
0x18007cb45  mov     rdx, r13
0x18007cb48  mov     [r12+0Ch], eax
0x18007cb4d  mov     rcx, rbp
0x18007cb50  mov     ebx, [rbp+11Ch]
0x18007cb56  mov     [rsp+88h+var_60], 0C6h
0x18007cb5e  mov     dword ptr [rbp+11Ch], 0F4h
0x18007cb68  mov     dword ptr [rsp+88h+lpBits], esi
0x18007cb6c  call    TV_DrawItem
0x18007cb71  mov     rdx, rdi; h
0x18007cb74  mov     [rbp+11Ch], ebx
0x18007cb7a  mov     rcx, r14; hdc
0x18007cb7d  call    cs:__imp_SelectObject
0x18007cb83  mov     rcx, r14; hdc
0x18007cb86  call    cs:__imp_DeleteDC
0x18007cb8c  mov     eax, 1
0x18007cb91  jmp     short loc_18007CB95
0x18007cb93  xor     eax, eax
0x18007cb95  mov     rcx, [rsp+88h+var_40]
0x18007cb9a  xor     rcx, rsp; StackCookie
0x18007cb9d  call    __security_check_cookie
0x18007cba2  mov     rbx, [rsp+88h+arg_10]
0x18007cbaa  add     rsp, 50h
0x18007cbae  pop     r15
0x18007cbb0  pop     r14
0x18007cbb2  pop     r13
0x18007cbb4  pop     r12
0x18007cbb6  pop     rdi
0x18007cbb7  pop     rsi
0x18007cbb8  pop     rbp
0x18007cbb9  retn
```
