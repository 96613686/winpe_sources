# CImageList::_SetOverlayImage(int,int)

- ea: `0x180084ef8`
- end: `0x180085298`
- name: `?_SetOverlayImage@CImageList@@QEAAJHH@Z`
- size: `928`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180082e60`
- `0x18008462c`

## callees

- `0x1800115f0`
- `0x180084ef8`
- `0x180090020`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180085026`
- `GDI32!CreateCompatibleDC` at `0x180085026`
- `GDI32!SelectObject` at `0x180085059`
- `GDI32!SelectObject` at `0x180085059`
- `GDI32!BitBlt` at `0x180085092`
- `GDI32!BitBlt` at `0x180085092`
- `GDI32!DeleteObject` at `0x18008525b`
- `GDI32!DeleteObject` at `0x18008525b`
- `GDI32!DeleteDC` at `0x180085251`
- `GDI32!DeleteDC` at `0x180085251`
- `GDI32!CreateBitmap` at `0x18008500c`
- `GDI32!CreateBitmap` at `0x18008500c`
- `GDI32!GetBitmapBits` at `0x1800850a1`
- `GDI32!GetBitmapBits` at `0x1800850a1`
- `KERNEL32!LocalFree` at `0x180085245`
- `KERNEL32!LocalFree` at `0x180085245`
- `KERNEL32!LocalAlloc` at `0x18008503f`
- `KERNEL32!LocalAlloc` at `0x18008503f`
- `USER32!SetRect` at `0x180084fb2`
- `USER32!SetRect` at `0x180084fb2`

## pseudocode

```c
__int64 __fastcall CImageList::_SetOverlayImage(CImageList *this, __int64 a2, int a3)
{
  CImageList *v3; // rdi
  __int64 v4; // r13
  int v6; // r14d
  int v7; // r15d
  unsigned __int64 v8; // rsi
  unsigned int v9; // ebx
  HLOCAL v10; // r12
  LONG bottom; // esi
  LONG v12; // r11d
  LONG right; // r10d
  _BYTE *v14; // rdx
  LONG top; // r9d
  bool v16; // cc
  LONG left; // r15d
  int v18; // r13d
  int v19; // r8d
  __int64 i; // rcx
  bool v21; // zf
  int j; // r8d
  int v23; // [rsp+54h] [rbp-45h]
  HDC hdc; // [rsp+58h] [rbp-41h]
  HBITMAP h; // [rsp+60h] [rbp-39h]
  _BYTE *v26; // [rsp+68h] [rbp-31h]
  unsigned int v27; // [rsp+70h] [rbp-29h]
  __int64 v29; // [rsp+88h] [rbp-11h]
  struct tagRECT rc; // [rsp+90h] [rbp-9h] BYREF
  int x1[4]; // [rsp+A0h] [rbp+7h] BYREF

  v3 = this;
  *(_OWORD *)x1 = 0;
  rc = 0;
  if ( !*((_QWORD *)this + 16) || (int)a2 < 0 || (int)a2 >= *((_DWORD *)this + 14) || (unsigned int)(a3 - 1) > 0xE )
    return 2147942487LL;
  v4 = a3;
  v29 = a3;
  if ( *((_DWORD *)this + a3 + 33) == (__int16)a2 )
    return 0;
  *((_DWORD *)this + a3 + 33) = (__int16)a2;
  (*(void (__fastcall **)(char *, __int64, int *))(*((_QWORD *)this + 2) + 120LL))((char *)this + 16, a2, x1);
  SetRect(&rc, 0x7FFF, 0x7FFF, 0, 0);
  v6 = x1[2] - x1[0];
  v7 = x1[3] - x1[1];
  v23 = x1[3] - x1[1];
  v8 = 2
     * (unsigned int)((unsigned __int64)(x1[2] - x1[0] + 15LL) >> 4)
     * (unsigned __int64)(unsigned int)(x1[3] - x1[1]);
  v27 = 2 * ((unsigned __int64)(x1[2] - x1[0] + 15LL) >> 4);
  if ( v8 > 0xFFFFFFFF )
    return 2147500037LL;
  v9 = 1;
  h = CreateBitmap(v6, v7, 1u, 1u, 0);
  if ( h )
  {
    hdc = CreateCompatibleDC(*((HDC *)v3 + 16));
    if ( hdc )
    {
      v10 = LocalAlloc(0, (unsigned int)v8);
      if ( v10 )
      {
        SelectObject(hdc, h);
        BitBlt(hdc, 0, 0, v6, v7, *((HDC *)v3 + 16), x1[0], x1[1], 0xCC0020u);
        GetBitmapBits(h, v8, v10);
        bottom = rc.bottom;
        v12 = 0;
        right = rc.right;
        v14 = v10;
        top = rc.top;
        v16 = v7 <= 0;
        left = rc.left;
        v26 = v10;
        if ( !v16 )
        {
          v18 = v6 >> 3;
          do
          {
            v19 = 0;
            for ( i = 0; (int)i < v18; i = (unsigned int)(i + 1) )
            {
              if ( v14[i] != 0xFF )
                break;
              v19 += 8;
            }
            if ( v19 < v6 )
            {
              do
              {
                if ( ((unsigned __int8)(1 << (7 - (v19 & 7))) & *((_BYTE *)v10 + v12 * v27 + (v19 >> 3))) == 0 )
                {
                  if ( left >= v19 )
                    left = v19;
                  rc.left = left;
                  if ( right <= v19 + 1 )
                    right = v19 + 1;
                  rc.right = right;
                  if ( top >= v12 )
                    top = v12;
                  rc.top = top;
                  if ( bottom <= v12 + 1 )
                    bottom = v12 + 1;
                  rc.bottom = bottom;
                  if ( v19 >= left && v19 < right )
                    v19 = right - 1;
                }
                ++v19;
              }
              while ( v19 < v6 );
              v14 = v26;
            }
            v14 += v27;
            ++v12;
            v26 = v14;
          }
          while ( v12 < v23 );
          v3 = this;
          v4 = v29;
        }
        *((_DWORD *)v3 + v4 + 108) = 0;
        if ( left == 0x7FFF )
          left = 0;
        rc.left = left;
        if ( top == 0x7FFF )
          top = 0;
        rc.top = top;
        *((_DWORD *)v3 + v4 + 78) = (__int16)(right - left);
        *((_DWORD *)v3 + v4 + 93) = (__int16)(bottom - top);
        *((_DWORD *)v3 + v4 + 48) = (__int16)left;
        *((_DWORD *)v3 + v4 + 63) = (__int16)top;
        v21 = top == bottom;
        if ( top < bottom )
        {
          do
          {
            for ( j = left; j < right; ++j )
            {
              if ( ((unsigned __int8)(1 << (7 - (j & 7))) & *((_BYTE *)v10 + top * v27 + (j >> 3))) != 0 )
                break;
            }
            if ( j != right )
              break;
            ++top;
          }
          while ( top < bottom );
          v3 = this;
          v21 = top == bottom;
        }
        if ( v21 )
          *((_DWORD *)v3 + v4 + 108) = 32;
        LocalFree(v10);
        v9 = 0;
      }
      DeleteDC(hdc);
    }
    DeleteObject(h);
  }
  return v9;
}

```

## disassembly

```asm
0x180084ef8  mov     [rsp-8+arg_18], rbx
0x180084efd  push    rbp
0x180084efe  push    rsi
0x180084eff  push    rdi
0x180084f00  push    r12
0x180084f02  push    r13
0x180084f04  push    r14
0x180084f06  push    r15
0x180084f08  lea     rbp, [rsp-27h]
0x180084f0d  sub     rsp, 0C0h
0x180084f14  mov     rax, cs:__security_cookie
0x180084f1b  xor     rax, rsp
0x180084f1e  mov     [rbp+57h+var_40], rax
0x180084f22  xor     r12d, r12d
0x180084f25  mov     [rbp+57h+var_78], rcx
0x180084f29  xorps   xmm0, xmm0
0x180084f2c  xorps   xmm1, xmm1
0x180084f2f  mov     rdi, rcx
0x180084f32  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180084f36  movups  xmmword ptr [rbp+57h+rc.left], xmm1
0x180084f3a  cmp     [rcx+80h], r12
0x180084f41  jz      loc_18008526C
0x180084f47  test    edx, edx
0x180084f49  js      loc_18008526C
0x180084f4f  cmp     edx, [rcx+38h]
0x180084f52  jge     loc_18008526C
0x180084f58  lea     eax, [r8-1]
0x180084f5c  cmp     eax, 0Eh
0x180084f5f  ja      loc_18008526C
0x180084f65  movsxd  r13, r8d
0x180084f68  movsx   eax, dx
0x180084f6b  mov     [rbp+57h+var_68], r13
0x180084f6f  cmp     [rcx+r13*4+84h], eax
0x180084f77  jnz     short loc_180084F80
0x180084f79  xor     eax, eax
0x180084f7b  jmp     loc_180085271
0x180084f80  mov     [rcx+r13*4+84h], eax
0x180084f88  lea     r8, [rbp+57h+var_50]
0x180084f8c  add     rcx, 10h
0x180084f90  mov     rax, [rcx]
0x180084f93  mov     rax, [rax+78h]
0x180084f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084f9c  mov     eax, 7FFFh
0x180084fa1  mov     [rsp+0F0h+yBottom], r12d; yBottom
0x180084fa6  mov     r8d, eax; yTop
0x180084fa9  lea     rcx, [rbp+57h+rc]; lprc
0x180084fad  mov     edx, eax; xLeft
0x180084faf  xor     r9d, r9d; xRight
0x180084fb2  call    cs:__imp_SetRect
0x180084fb8  mov     r14d, [rbp+57h+var_50+8]
0x180084fbc  sub     r14d, [rbp+57h+var_50]
0x180084fc0  mov     r15d, [rbp+57h+var_50+0Ch]
0x180084fc4  sub     r15d, [rbp+57h+var_50+4]
0x180084fc8  movsxd  rax, r14d
0x180084fcb  add     rax, 0Fh
0x180084fcf  mov     esi, r15d
0x180084fd2  shr     rax, 4
0x180084fd6  add     eax, eax
0x180084fd8  mov     [rbp+57h+var_9C], r15d
0x180084fdc  imul    rsi, rax
0x180084fe0  mov     [rbp+57h+var_80], rax
0x180084fe4  mov     [rbp+57h+var_70], rax
0x180084fe8  mov     eax, 0FFFFFFFFh
0x180084fed  cmp     rsi, rax
0x180084ff0  ja      loc_180085265
0x180084ff6  mov     ebx, 1
0x180084ffb  mov     qword ptr [rsp+0F0h+yBottom], r12; lpBits
0x180085000  mov     r9d, ebx; nBitCount
0x180085003  mov     r8d, ebx; nPlanes
0x180085006  mov     edx, r15d; nHeight
0x180085009  mov     ecx, r14d; nWidth
0x18008500c  call    cs:__imp_CreateBitmap
0x180085012  mov     [rbp+57h+h], rax
0x180085016  test    rax, rax
0x180085019  jz      loc_180085261
0x18008501f  mov     rcx, [rdi+80h]; hdc
0x180085026  call    cs:__imp_CreateCompatibleDC
0x18008502c  mov     [rbp+57h+hdc], rax
0x180085030  test    rax, rax
0x180085033  jz      loc_180085257
0x180085039  mov     esi, esi
0x18008503b  xor     ecx, ecx; uFlags
0x18008503d  mov     edx, esi; uBytes
0x18008503f  call    cs:__imp_LocalAlloc
0x180085045  mov     r12, rax
0x180085048  test    rax, rax
0x18008504b  jz      loc_18008524D
0x180085051  mov     rdx, [rbp+57h+h]; h
0x180085055  mov     rcx, [rbp+57h+hdc]; hdc
0x180085059  call    cs:__imp_SelectObject
0x18008505f  mov     ecx, [rbp+57h+var_50+4]
0x180085062  mov     r9d, r14d; cx
0x180085065  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18008506d  xor     r8d, r8d; y
0x180085070  mov     [rsp+0F0h+y1], ecx; y1
0x180085074  xor     edx, edx; x
0x180085076  mov     ecx, [rbp+57h+var_50]
0x180085079  mov     [rsp+0F0h+x1], ecx; x1
0x18008507d  mov     rcx, [rdi+80h]
0x180085084  mov     [rsp+0F0h+hdcSrc], rcx; hdcSrc
0x180085089  mov     rcx, [rbp+57h+hdc]; hdc
0x18008508d  mov     [rsp+0F0h+yBottom], r15d; cy
0x180085092  call    cs:__imp_BitBlt
0x180085098  mov     rcx, [rbp+57h+h]; hbit
0x18008509c  mov     r8, r12; lpvBits
0x18008509f  mov     edx, esi; cb
0x1800850a1  call    cs:__imp_GetBitmapBits
0x1800850a7  mov     esi, [rbp+57h+rc.bottom]
0x1800850aa  xor     r11d, r11d
0x1800850ad  mov     r10d, [rbp+57h+rc.right]
0x1800850b1  mov     rdx, r12
0x1800850b4  mov     r9d, [rbp+57h+rc.top]
0x1800850b8  test    r15d, r15d
0x1800850bb  mov     r15d, [rbp+57h+rc.left]
0x1800850bf  mov     [rbp+57h+var_88], rdx
0x1800850c3  jle     loc_18008517E
0x1800850c9  mov     r13d, r14d
0x1800850cc  sar     r13d, 3
0x1800850d0  xor     r8d, r8d
0x1800850d3  xor     ecx, ecx
0x1800850d5  test    r13d, r13d
0x1800850d8  jle     short loc_1800850EB
0x1800850da  cmp     byte ptr [rcx+rdx], 0FFh
0x1800850de  jnz     short loc_1800850EB
0x1800850e0  add     r8d, 8
0x1800850e4  add     ecx, ebx
0x1800850e6  cmp     ecx, r13d
0x1800850e9  jl      short loc_1800850DA
0x1800850eb  cmp     r8d, r14d
0x1800850ee  jge     short loc_180085161
0x1800850f0  mov     edi, dword ptr [rbp+57h+var_80]
0x1800850f3  imul    edi, r11d
0x1800850f7  mov     eax, r8d
0x1800850fa  mov     ecx, 7
0x1800850ff  and     eax, 7
0x180085102  mov     edx, ebx
0x180085104  sub     ecx, eax
0x180085106  mov     eax, r8d
0x180085109  sar     eax, 3
0x18008510c  add     eax, edi
0x18008510e  shl     edx, cl
0x180085110  test    [rax+r12], dl
0x180085114  jnz     short loc_180085155
0x180085116  cmp     r15d, r8d
0x180085119  lea     eax, [r8+1]
0x18008511d  cmovge  r15d, r8d
0x180085121  cmp     r10d, eax
0x180085124  mov     [rbp+57h+rc.left], r15d
0x180085128  cmovle  r10d, eax
0x18008512c  cmp     r9d, r11d
0x18008512f  lea     eax, [r11+1]
0x180085133  mov     [rbp+57h+rc.right], r10d
0x180085137  cmovge  r9d, r11d
0x18008513b  cmp     esi, eax
0x18008513d  mov     [rbp+57h+rc.top], r9d
0x180085141  cmovle  esi, eax
0x180085144  mov     [rbp+57h+rc.bottom], esi
0x180085147  cmp     r8d, r15d
0x18008514a  jl      short loc_180085155
0x18008514c  cmp     r8d, r10d
0x18008514f  jge     short loc_180085155
0x180085151  lea     r8d, [r10-1]
0x180085155  add     r8d, ebx
0x180085158  cmp     r8d, r14d
0x18008515b  jl      short loc_1800850F7
0x18008515d  mov     rdx, [rbp+57h+var_88]
0x180085161  add     rdx, [rbp+57h+var_70]
0x180085165  add     r11d, ebx
0x180085168  mov     [rbp+57h+var_88], rdx
0x18008516c  cmp     r11d, [rbp+57h+var_9C]
0x180085170  jl      loc_1800850D0
0x180085176  mov     rdi, [rbp+57h+var_78]
0x18008517a  mov     r13, [rbp+57h+var_68]
0x18008517e  xor     eax, eax
0x180085180  mov     dword ptr [rdi+r13*4+1B0h], 0
0x18008518c  mov     ecx, 7FFFh
0x180085191  cmp     r15d, ecx
0x180085194  cmovz   r15d, eax
0x180085198  cmp     r9d, ecx
0x18008519b  mov     [rbp+57h+rc.left], r15d
0x18008519f  cmovz   r9d, eax
0x1800851a3  movzx   eax, r10w
0x1800851a7  sub     ax, r15w
0x1800851ab  mov     [rbp+57h+rc.top], r9d
0x1800851af  cwde
0x1800851b0  mov     [rdi+r13*4+138h], eax
0x1800851b8  movzx   eax, si
0x1800851bb  sub     ax, r9w
0x1800851bf  cwde
0x1800851c0  mov     [rdi+r13*4+174h], eax
0x1800851c8  movsx   eax, r15w
0x1800851cc  mov     [rdi+r13*4+0C0h], eax
0x1800851d4  movsx   eax, r9w
0x1800851d8  mov     [rdi+r13*4+0FCh], eax
0x1800851e0  cmp     r9d, esi
0x1800851e3  jge     short loc_180085234
0x1800851e5  mov     rdi, [rbp+57h+var_80]
0x1800851e9  mov     r8d, r15d
0x1800851ec  cmp     r15d, r10d
0x1800851ef  jge     short loc_180085220
0x1800851f1  mov     r11d, edi
0x1800851f4  imul    r11d, r9d
0x1800851f8  mov     eax, r8d
0x1800851fb  mov     ecx, 7
0x180085200  and     eax, 7
0x180085203  mov     edx, ebx
0x180085205  sub     ecx, eax
0x180085207  mov     eax, r8d
0x18008520a  sar     eax, 3
0x18008520d  add     eax, r11d
0x180085210  shl     edx, cl
0x180085212  test    [rax+r12], dl
0x180085216  jnz     short loc_180085220
0x180085218  add     r8d, ebx
0x18008521b  cmp     r8d, r10d
0x18008521e  jl      short loc_1800851F8
0x180085220  cmp     r8d, r10d
0x180085223  jnz     short loc_18008522D
0x180085225  add     r9d, ebx
0x180085228  cmp     r9d, esi
0x18008522b  jl      short loc_1800851E9
0x18008522d  mov     rdi, [rbp+57h+var_78]
0x180085231  cmp     r9d, esi
0x180085234  jnz     short loc_180085242
0x180085236  mov     dword ptr [rdi+r13*4+1B0h], 20h ; ' '
0x180085242  mov     rcx, r12; hMem
0x180085245  call    cs:__imp_LocalFree
0x18008524b  xor     ebx, ebx
0x18008524d  mov     rcx, [rbp+57h+hdc]; hdc
0x180085251  call    cs:__imp_DeleteDC
0x180085257  mov     rcx, [rbp+57h+h]; ho
0x18008525b  call    cs:__imp_DeleteObject
0x180085261  mov     eax, ebx
0x180085263  jmp     short loc_180085271
0x180085265  mov     eax, 80004005h
0x18008526a  jmp     short loc_180085271
0x18008526c  mov     eax, 80070057h
0x180085271  mov     rcx, [rbp+57h+var_40]
0x180085275  xor     rcx, rsp; StackCookie
0x180085278  call    __security_check_cookie
0x18008527d  mov     rbx, [rsp+0F0h+arg_18]
0x180085285  add     rsp, 0C0h
0x18008528c  pop     r15
0x18008528e  pop     r14
0x180085290  pop     r13
0x180085292  pop     r12
0x180085294  pop     rdi
0x180085295  pop     rsi
0x180085296  pop     rbp
0x180085297  retn
```
