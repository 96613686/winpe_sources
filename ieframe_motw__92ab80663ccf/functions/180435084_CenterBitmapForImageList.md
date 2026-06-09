# CenterBitmapForImageList

- ea: `0x180435084`
- end: `0x18043531c`
- name: `CenterBitmapForImageList`
- size: `664`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801fad50`
- `0x18022fd90`
- `0x1802eb780`

## callees

- `0x180435084`
- `0x180591f80`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x180435203`
- `GDI32!CreateSolidBrush` at `0x180435203`
- `GDI32!CreateDIBSection` at `0x180435177`
- `GDI32!CreateDIBSection` at `0x180435177`
- `GDI32!GetPixel` at `0x1804351f5`
- `GDI32!GetPixel` at `0x1804351f5`
- `GDI32!DeleteObject` at `0x180435230`
- `GDI32!DeleteObject` at `0x180435230`
- `GDI32!SelectObject` at `0x180435196`
- `GDI32!SelectObject` at `0x1804351ad`
- `GDI32!SelectObject` at `0x1804352b8`
- `GDI32!SelectObject` at `0x1804352cb`
- `GDI32!SelectObject` at `0x180435196`
- `GDI32!SelectObject` at `0x1804351ad`
- `GDI32!SelectObject` at `0x1804352b8`
- `GDI32!SelectObject` at `0x1804352cb`
- `GDI32!GetObjectW` at `0x1804350d4`
- `GDI32!GetObjectW` at `0x1804350d4`
- `GDI32!DeleteDC` at `0x1804352dd`
- `GDI32!DeleteDC` at `0x1804352ec`
- `GDI32!DeleteDC` at `0x1804352dd`
- `GDI32!DeleteDC` at `0x1804352ec`
- `GDI32!CreateCompatibleDC` at `0x180435101`
- `GDI32!CreateCompatibleDC` at `0x18043511c`
- `GDI32!CreateCompatibleDC` at `0x180435101`
- `GDI32!CreateCompatibleDC` at `0x18043511c`
- `GDI32!BitBlt` at `0x18043529a`
- `GDI32!BitBlt` at `0x18043529a`
- `USER32!FillRect` at `0x180435221`
- `USER32!FillRect` at `0x180435221`

## pseudocode

```c
__int64 __fastcall CenterBitmapForImageList(LONG *a1, void *a2, int a3, HGDIOBJ *a4)
{
  unsigned int v8; // r14d
  HDC CompatibleDC; // rax
  HDC v10; // rbx
  HDC v11; // rdi
  LONG v12; // eax
  HBITMAP v13; // rax
  HGDIOBJ v14; // rax
  LONG right; // r13d
  LONG v16; // r12d
  int v17; // r14d
  COLORREF Pixel; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v20; // rsi
  int v21; // esi
  int v22; // r8d
  int v23; // r12d
  int v25; // [rsp+50h] [rbp-69h]
  LONG cy; // [rsp+54h] [rbp-65h]
  HGDIOBJ h; // [rsp+58h] [rbp-61h]
  HGDIOBJ v28; // [rsp+60h] [rbp-59h]
  RECT pv[2]; // [rsp+68h] [rbp-51h] BYREF
  RECT rc; // [rsp+88h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+98h] [rbp-21h] BYREF

  v8 = -2147467259;
  memset(pv, 0, sizeof(pv));
  if ( GetObjectW(a2, 32, pv) )
  {
    if ( pv[0].top <= *a1 && pv[0].right <= a1[1] )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v10 = CompatibleDC;
      if ( CompatibleDC )
      {
        v11 = CreateCompatibleDC(CompatibleDC);
        if ( v11 )
        {
          v12 = *a1;
          memset(&pbmi.bmiHeader.biWidth, 0, 40);
          pbmi.bmiHeader.biWidth = v12;
          pbmi.bmiHeader.biHeight = a1[1];
          pbmi.bmiHeader.biSize = 40;
          *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
          v13 = CreateDIBSection(v10, &pbmi, 0, 0, 0, 0);
          *a4 = v13;
          if ( v13 )
          {
            h = SelectObject(v11, a2);
            v14 = SelectObject(v10, *a4);
            right = pv[0].right;
            v16 = a1[1];
            v28 = v14;
            rc.right = *a1;
            cy = pv[0].right;
            v17 = pv[0].top / a3;
            *(_QWORD *)&rc.left = 0;
            rc.bottom = v16;
            v25 = rc.right / a3;
            Pixel = GetPixel(v11, 0, 0);
            SolidBrush = CreateSolidBrush(Pixel);
            v20 = SolidBrush;
            if ( SolidBrush )
            {
              FillRect(v10, &rc, SolidBrush);
              DeleteObject(v20);
            }
            v21 = 0;
            if ( a3 > 0 )
            {
              v22 = v25;
              v23 = (v16 - right) / 2;
              do
              {
                BitBlt(v10, (v25 - v17) / 2 + v22 * v21, v23, v17, cy, v11, v17 * v21, 0, 0xCC0020u);
                v22 = v25;
                ++v21;
              }
              while ( v21 < a3 );
            }
            SelectObject(v11, h);
            SelectObject(v10, v28);
            v8 = 0;
          }
          DeleteDC(v11);
        }
        DeleteDC(v10);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180435084  push    rbp
0x180435086  push    rbx
0x180435087  push    rsi
0x180435088  push    rdi
0x180435089  push    r12
0x18043508b  push    r13
0x18043508d  push    r14
0x18043508f  push    r15
0x180435091  lea     rbp, [rsp-1Fh]
0x180435096  sub     rsp, 0D8h
0x18043509d  mov     rax, cs:__security_cookie
0x1804350a4  xor     rax, rsp
0x1804350a7  mov     [rbp+57h+var_48], rax
0x1804350ab  mov     r13, rdx
0x1804350ae  xorps   xmm0, xmm0
0x1804350b1  mov     r15d, r8d
0x1804350b4  mov     rsi, rcx
0x1804350b7  mov     rcx, r13; h
0x1804350ba  lea     r8, [rbp+57h+pv]; pv
0x1804350be  mov     edx, 20h ; ' '; c
0x1804350c3  mov     r12, r9
0x1804350c6  mov     r14d, 80004005h
0x1804350cc  movups  [rbp+57h+pv], xmm0
0x1804350d0  movups  [rbp+57h+var_98], xmm0
0x1804350d4  call    cs:__imp_GetObjectW
0x1804350db  nop     dword ptr [rax+rax+00h]
0x1804350e0  test    eax, eax
0x1804350e2  jz      loc_1804352F8
0x1804350e8  mov     eax, [rsi]
0x1804350ea  cmp     dword ptr [rbp+57h+pv+4], eax
0x1804350ed  jg      loc_1804352F8
0x1804350f3  mov     eax, [rsi+4]
0x1804350f6  cmp     dword ptr [rbp+57h+pv+8], eax
0x1804350f9  jg      loc_1804352F8
0x1804350ff  xor     ecx, ecx; hdc
0x180435101  call    cs:__imp_CreateCompatibleDC
0x180435108  nop     dword ptr [rax+rax+00h]
0x18043510d  mov     rbx, rax
0x180435110  test    rax, rax
0x180435113  jz      loc_1804352F8
0x180435119  mov     rcx, rax; hdc
0x18043511c  call    cs:__imp_CreateCompatibleDC
0x180435123  nop     dword ptr [rax+rax+00h]
0x180435128  xor     ecx, ecx
0x18043512a  mov     rdi, rax
0x18043512d  test    rax, rax
0x180435130  jz      loc_1804352E9
0x180435136  xor     eax, eax
0x180435138  mov     [rsp+110h+offset], ecx; offset
0x18043513c  xorps   xmm0, xmm0
0x18043513f  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x180435143  mov     eax, [rsi]
0x180435145  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180435149  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18043514d  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180435150  xor     r9d, r9d; ppvBits
0x180435153  mov     eax, [rsi+4]
0x180435156  xor     r8d, r8d; usage
0x180435159  mov     [rsp+110h+hSection], rcx; hSection
0x18043515e  mov     rcx, rbx; hdc
0x180435161  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x180435164  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180435168  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18043516f  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180435177  call    cs:__imp_CreateDIBSection
0x18043517e  nop     dword ptr [rax+rax+00h]
0x180435183  mov     [r12], rax
0x180435187  test    rax, rax
0x18043518a  jz      loc_1804352DA
0x180435190  mov     rdx, r13; h
0x180435193  mov     rcx, rdi; hdc
0x180435196  call    cs:__imp_SelectObject
0x18043519d  nop     dword ptr [rax+rax+00h]
0x1804351a2  mov     rdx, [r12]; h
0x1804351a6  mov     rcx, rbx; hdc
0x1804351a9  mov     [rbp+57h+h], rax
0x1804351ad  call    cs:__imp_SelectObject
0x1804351b4  nop     dword ptr [rax+rax+00h]
0x1804351b9  mov     ecx, [rsi]
0x1804351bb  xor     r8d, r8d; y
0x1804351be  mov     r13d, dword ptr [rbp+57h+pv+8]
0x1804351c2  mov     r12d, [rsi+4]
0x1804351c6  mov     [rbp+57h+var_B0], rax
0x1804351ca  mov     eax, dword ptr [rbp+57h+pv+4]
0x1804351cd  cdq
0x1804351ce  mov     [rbp+57h+rc.right], ecx
0x1804351d1  idiv    r15d
0x1804351d4  mov     [rbp+57h+cy], r13d
0x1804351d8  mov     r14d, eax
0x1804351db  mov     qword ptr [rbp+57h+rc.left], 0
0x1804351e3  mov     eax, ecx
0x1804351e5  mov     [rbp+57h+rc.bottom], r12d
0x1804351e9  cdq
0x1804351ea  mov     rcx, rdi; hdc
0x1804351ed  idiv    r15d
0x1804351f0  xor     edx, edx; x
0x1804351f2  mov     [rbp+57h+var_C0], eax
0x1804351f5  call    cs:__imp_GetPixel
0x1804351fc  nop     dword ptr [rax+rax+00h]
0x180435201  mov     ecx, eax; color
0x180435203  call    cs:__imp_CreateSolidBrush
0x18043520a  nop     dword ptr [rax+rax+00h]
0x18043520f  mov     rsi, rax
0x180435212  test    rax, rax
0x180435215  jz      short loc_18043523C
0x180435217  mov     r8, rax; hbr
0x18043521a  lea     rdx, [rbp+57h+rc]; lprc
0x18043521e  mov     rcx, rbx; hDC
0x180435221  call    cs:__imp_FillRect
0x180435228  nop     dword ptr [rax+rax+00h]
0x18043522d  mov     rcx, rsi; ho
0x180435230  call    cs:__imp_DeleteObject
0x180435237  nop     dword ptr [rax+rax+00h]
0x18043523c  xor     esi, esi
0x18043523e  test    r15d, r15d
0x180435241  jle     short loc_1804352B1
0x180435243  mov     r8d, [rbp+57h+var_C0]
0x180435247  lea     ecx, [rsi+2]
0x18043524a  sub     r12d, r13d
0x18043524d  mov     eax, r12d
0x180435250  cdq
0x180435251  idiv    ecx
0x180435253  mov     r12d, eax
0x180435256  mov     eax, r8d
0x180435259  sub     eax, r14d
0x18043525c  cdq
0x18043525d  idiv    ecx
0x18043525f  mov     r13d, eax
0x180435262  mov     eax, [rbp+57h+cy]
0x180435265  mov     ecx, esi
0x180435267  mov     [rsp+110h+rop], 0CC0020h; rop
0x18043526f  mov     edx, esi
0x180435271  imul    ecx, r14d
0x180435275  mov     r9d, r14d; cx
0x180435278  imul    edx, r8d
0x18043527c  mov     r8d, r12d; y
0x18043527f  mov     [rsp+110h+y1], 0; y1
0x180435287  mov     [rsp+110h+x1], ecx; x1
0x18043528b  mov     rcx, rbx; hdc
0x18043528e  mov     qword ptr [rsp+110h+offset], rdi; hdcSrc
0x180435293  add     edx, r13d; x
0x180435296  mov     dword ptr [rsp+110h+hSection], eax; cy
0x18043529a  call    cs:__imp_BitBlt
0x1804352a1  nop     dword ptr [rax+rax+00h]
0x1804352a6  mov     r8d, [rbp+57h+var_C0]
0x1804352aa  inc     esi
0x1804352ac  cmp     esi, r15d
0x1804352af  jl      short loc_180435262
0x1804352b1  mov     rdx, [rbp+57h+h]; h
0x1804352b5  mov     rcx, rdi; hdc
0x1804352b8  call    cs:__imp_SelectObject
0x1804352bf  nop     dword ptr [rax+rax+00h]
0x1804352c4  mov     rdx, [rbp+57h+var_B0]; h
0x1804352c8  mov     rcx, rbx; hdc
0x1804352cb  call    cs:__imp_SelectObject
0x1804352d2  nop     dword ptr [rax+rax+00h]
0x1804352d7  xor     r14d, r14d
0x1804352da  mov     rcx, rdi; hdc
0x1804352dd  call    cs:__imp_DeleteDC
0x1804352e4  nop     dword ptr [rax+rax+00h]
0x1804352e9  mov     rcx, rbx; hdc
0x1804352ec  call    cs:__imp_DeleteDC
0x1804352f3  nop     dword ptr [rax+rax+00h]
0x1804352f8  mov     eax, r14d
0x1804352fb  mov     rcx, [rbp+57h+var_48]
0x1804352ff  xor     rcx, rsp; StackCookie
0x180435302  call    __security_check_cookie
0x180435307  add     rsp, 0D8h
0x18043530e  pop     r15
0x180435310  pop     r14
0x180435312  pop     r13
0x180435314  pop     r12
0x180435316  pop     rdi
0x180435317  pop     rsi
0x180435318  pop     rbx
0x180435319  pop     rbp
0x18043531a  retn
```
