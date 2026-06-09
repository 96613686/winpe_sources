# bDumpDCClipping

- ea: `0x1800c5768`
- end: `0x1800c5a6f`
- name: `bDumpDCClipping`
- size: `775`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c5db4`
- `0x180148700`
- `0x18014a404`
- `0x18014a6c4`
- `0x18014bb40`

## callees

- `0x1800c5768`
- `0x1800c60cc`
- `0x1800c807c`
- `0x180105d40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c5828`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c596b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c5828`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c596b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5a42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5a42`
- `GDI32!GetRgnBox` at `0x1800c588e`
- `GDI32!GetRgnBox` at `0x1800c588e`
- `GDI32!ExtCreateRegion` at `0x1800c586f`
- `GDI32!ExtCreateRegion` at `0x1800c586f`
- `GDI32!CombineRgn` at `0x1800c5933`
- `GDI32!CombineRgn` at `0x1800c5933`
- `GDI32!DeleteObject` at `0x1800c59f2`
- `GDI32!DeleteObject` at `0x1800c5a06`
- `GDI32!DeleteObject` at `0x1800c5a1a`
- `GDI32!DeleteObject` at `0x1800c59f2`
- `GDI32!DeleteObject` at `0x1800c5a06`
- `GDI32!DeleteObject` at `0x1800c5a1a`
- `GDI32!GetRegionData` at `0x1800c580c`
- `GDI32!GetRegionData` at `0x1800c5849`
- `GDI32!GetRegionData` at `0x1800c594f`
- `GDI32!GetRegionData` at `0x1800c5988`
- `GDI32!GetRegionData` at `0x1800c580c`
- `GDI32!GetRegionData` at `0x1800c5849`
- `GDI32!GetRegionData` at `0x1800c594f`
- `GDI32!GetRegionData` at `0x1800c5988`
- `GDI32!GetRandomRgn` at `0x1800c57e7`
- `GDI32!GetRandomRgn` at `0x1800c57e7`
- `GDI32!CreateRectRgn` at `0x1800c57ba`
- `GDI32!CreateRectRgn` at `0x1800c590e`
- `GDI32!CreateRectRgn` at `0x1800c57ba`
- `GDI32!CreateRectRgn` at `0x1800c590e`

## pseudocode

```c
__int64 __fastcall bDumpDCClipping(__int64 a1)
{
  unsigned int v2; // r14d
  HRGN RectRgn; // rax
  HRGN v4; // r13
  HRGN v5; // rdi
  HRGN v6; // r15
  RGNDATA *v7; // rsi
  struct _RGNDATA *v8; // rbx
  int RandomRgn; // eax
  DWORD RegionData; // eax
  DWORD v11; // r12d
  struct _RGNDATA *v12; // rax
  HRGN Region; // rax
  LONG right; // ecx
  LONG left; // r8d
  LONG top; // r9d
  LONG bottom; // eax
  HRGN v18; // rax
  DWORD v19; // eax
  DWORD v20; // r12d
  struct _RGNDATA *v21; // rax
  signed int nCount; // eax
  signed int v23; // r12d
  signed int v25; // [rsp+30h] [rbp-38h]
  struct tagRECT rc; // [rsp+40h] [rbp-28h] BYREF

  rc = 0;
  v2 = 0;
  if ( !(unsigned int)bW16Emit1(a1, 300, 0) )
    return v2;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v4 = RectRgn;
  if ( !RectRgn )
    return v2;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  RandomRgn = GetRandomRgn(*(HDC *)(a1 + 40), RectRgn, 3);
  if ( RandomRgn != -1 )
  {
    if ( RandomRgn )
    {
      RegionData = GetRegionData(v4, 0, 0);
      v11 = RegionData;
      if ( !RegionData )
        goto LABEL_29;
      v12 = (struct _RGNDATA *)LocalAlloc(0, RegionData);
      v7 = v12;
      if ( !v12 )
        goto LABEL_29;
      if ( GetRegionData(v4, v11, v12) != v11 )
        goto LABEL_29;
      Region = ExtCreateRegion((const XFORM *)(a1 + 204), v11, v7);
      v5 = Region;
      if ( !Region || !GetRgnBox(Region, &rc) )
        goto LABEL_29;
      right = rc.right;
      left = rc.left;
      top = rc.top;
      if ( rc.left < -30000 )
        left = -30000;
      rc.left = left;
      if ( rc.top < -30000 )
        top = -30000;
      bottom = rc.bottom;
      rc.top = top;
      if ( rc.right > 30000 )
        right = 30000;
      rc.right = right;
      if ( rc.bottom > 30000 )
        bottom = 30000;
      rc.bottom = bottom;
      if ( !(unsigned int)bW16Emit4(a1, 1046, left, top, right, bottom) )
        goto LABEL_29;
      v18 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
      v6 = v18;
      if ( !v18 )
        goto LABEL_29;
      if ( !CombineRgn(v5, v18, v5, 4) )
        goto LABEL_29;
      v19 = GetRegionData(v5, 0, 0);
      v20 = v19;
      if ( !v19 )
        goto LABEL_29;
      v21 = (struct _RGNDATA *)LocalAlloc(0, v19);
      v8 = v21;
      if ( !v21 || GetRegionData(v5, v20, v21) != v20 )
        goto LABEL_29;
      nCount = v8->rdh.nCount;
      v23 = 0;
      v25 = nCount;
      while ( v23 < nCount )
      {
        if ( !(unsigned int)bW16Emit4(
                              a1,
                              1045,
                              *(unsigned __int16 *)&v8->Buffer[16 * v23],
                              *((unsigned __int16 *)&v8[1].rdh.dwSize + 8 * v23),
                              *((_WORD *)&v8[1].rdh.iType + 8 * v23),
                              *((_WORD *)&v8[1].rdh.nCount + 8 * v23)) )
          goto LABEL_29;
        nCount = v25;
        ++v23;
      }
    }
    v2 = 1;
  }
LABEL_29:
  DeleteObject(v4);
  if ( v5 )
    DeleteObject(v5);
  if ( v6 )
    DeleteObject(v6);
  if ( v7 )
    LocalFree(v7);
  if ( v8 )
    LocalFree(v8);
  return v2;
}

```

## disassembly

```asm
0x1800c5768  push    rbp
0x1800c576a  push    rbx
0x1800c576b  push    rsi
0x1800c576c  push    rdi
0x1800c576d  push    r12
0x1800c576f  push    r13
0x1800c5771  push    r14
0x1800c5773  push    r15
0x1800c5775  mov     rbp, rsp
0x1800c5778  sub     rsp, 68h
0x1800c577c  mov     rax, cs:__security_cookie
0x1800c5783  xor     rax, rsp
0x1800c5786  mov     [rbp+var_18], rax
0x1800c578a  xorps   xmm0, xmm0
0x1800c578d  mov     [rbp+var_30], rcx
0x1800c5791  xor     r8d, r8d
0x1800c5794  mov     edx, 12Ch
0x1800c5799  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800c579d  mov     r12, rcx
0x1800c57a0  xor     r14d, r14d
0x1800c57a3  call    bW16Emit1
0x1800c57a8  test    eax, eax
0x1800c57aa  jz      loc_1800C5A4E
0x1800c57b0  xor     r9d, r9d; y2
0x1800c57b3  xor     r8d, r8d; x2
0x1800c57b6  xor     edx, edx; y1
0x1800c57b8  xor     ecx, ecx; x1
0x1800c57ba  call    cs:__imp_CreateRectRgn
0x1800c57c1  nop     dword ptr [rax+rax+00h]
0x1800c57c6  mov     r13, rax
0x1800c57c9  test    rax, rax
0x1800c57cc  jz      loc_1800C5A4E
0x1800c57d2  mov     rcx, [r12+28h]; hdc
0x1800c57d7  lea     r8d, [r14+3]; i
0x1800c57db  mov     rdx, rax; hrgn
0x1800c57de  xor     edi, edi
0x1800c57e0  xor     r15d, r15d
0x1800c57e3  xor     esi, esi
0x1800c57e5  xor     ebx, ebx
0x1800c57e7  call    cs:__imp_GetRandomRgn
0x1800c57ee  nop     dword ptr [rax+rax+00h]
0x1800c57f3  cmp     eax, 0FFFFFFFFh
0x1800c57f6  jz      loc_1800C59EF
0x1800c57fc  test    eax, eax
0x1800c57fe  jz      loc_1800C59E9
0x1800c5804  xor     r8d, r8d; lpRgnData
0x1800c5807  xor     edx, edx; nCount
0x1800c5809  mov     rcx, r13; hrgn
0x1800c580c  call    cs:__imp_GetRegionData
0x1800c5813  nop     dword ptr [rax+rax+00h]
0x1800c5818  mov     r12d, eax
0x1800c581b  test    eax, eax
0x1800c581d  jz      loc_1800C59EF
0x1800c5823  mov     edx, r12d; uBytes
0x1800c5826  xor     ecx, ecx; uFlags
0x1800c5828  call    cs:__imp_LocalAlloc
0x1800c582f  nop     dword ptr [rax+rax+00h]
0x1800c5834  mov     rsi, rax
0x1800c5837  test    rax, rax
0x1800c583a  jz      loc_1800C59EF
0x1800c5840  mov     r8, rax; lpRgnData
0x1800c5843  mov     edx, r12d; nCount
0x1800c5846  mov     rcx, r13; hrgn
0x1800c5849  call    cs:__imp_GetRegionData
0x1800c5850  nop     dword ptr [rax+rax+00h]
0x1800c5855  cmp     eax, r12d
0x1800c5858  jnz     loc_1800C59EF
0x1800c585e  mov     rcx, [rbp+var_30]
0x1800c5862  mov     r8, rsi; lpData
0x1800c5865  add     rcx, 0CCh; lpx
0x1800c586c  mov     edx, r12d; nCount
0x1800c586f  call    cs:__imp_ExtCreateRegion
0x1800c5876  nop     dword ptr [rax+rax+00h]
0x1800c587b  mov     rdi, rax
0x1800c587e  test    rax, rax
0x1800c5881  jz      loc_1800C59EF
0x1800c5887  lea     rdx, [rbp+rc]; lprc
0x1800c588b  mov     rcx, rax; hrgn
0x1800c588e  call    cs:__imp_GetRgnBox
0x1800c5895  nop     dword ptr [rax+rax+00h]
0x1800c589a  test    eax, eax
0x1800c589c  jz      loc_1800C59EF
0x1800c58a2  mov     ecx, [rbp+rc.right]
0x1800c58a5  mov     eax, 0FFFF8AD0h
0x1800c58aa  mov     r8d, [rbp+rc.left]
0x1800c58ae  mov     edx, 7530h
0x1800c58b3  mov     r9d, [rbp+rc.top]
0x1800c58b7  cmp     r8d, eax
0x1800c58ba  cmovl   r8d, eax
0x1800c58be  cmp     r9d, eax
0x1800c58c1  mov     [rbp+rc.left], r8d
0x1800c58c5  cmovl   r9d, eax
0x1800c58c9  mov     eax, [rbp+rc.bottom]
0x1800c58cc  cmp     ecx, edx
0x1800c58ce  mov     [rbp+rc.top], r9d
0x1800c58d2  cmovg   ecx, edx
0x1800c58d5  cmp     eax, edx
0x1800c58d7  mov     [rbp+rc.right], ecx
0x1800c58da  cmovg   eax, edx
0x1800c58dd  mov     edx, 416h
0x1800c58e2  mov     [rsp+68h+var_40], ax
0x1800c58e7  mov     [rsp+68h+var_48], cx
0x1800c58ec  mov     rcx, [rbp+var_30]
0x1800c58f0  mov     [rbp+rc.bottom], eax
0x1800c58f3  call    bW16Emit4
0x1800c58f8  test    eax, eax
0x1800c58fa  jz      loc_1800C59EF
0x1800c5900  mov     r9d, [rbp+rc.bottom]; y2
0x1800c5904  mov     r8d, [rbp+rc.right]; x2
0x1800c5908  mov     edx, [rbp+rc.top]; y1
0x1800c590b  mov     ecx, [rbp+rc.left]; x1
0x1800c590e  call    cs:__imp_CreateRectRgn
0x1800c5915  nop     dword ptr [rax+rax+00h]
0x1800c591a  mov     r15, rax
0x1800c591d  test    rax, rax
0x1800c5920  jz      loc_1800C59EF
0x1800c5926  lea     r9d, [r14+4]; iMode
0x1800c592a  mov     r8, rdi; hrgnSrc2
0x1800c592d  mov     rdx, rax; hrgnSrc1
0x1800c5930  mov     rcx, rdi; hrgnDst
0x1800c5933  call    cs:__imp_CombineRgn
0x1800c593a  nop     dword ptr [rax+rax+00h]
0x1800c593f  test    eax, eax
0x1800c5941  jz      loc_1800C59EF
0x1800c5947  xor     r8d, r8d; lpRgnData
0x1800c594a  xor     edx, edx; nCount
0x1800c594c  mov     rcx, rdi; hrgn
0x1800c594f  call    cs:__imp_GetRegionData
0x1800c5956  nop     dword ptr [rax+rax+00h]
0x1800c595b  mov     r12d, eax
0x1800c595e  test    eax, eax
0x1800c5960  jz      loc_1800C59EF
0x1800c5966  mov     edx, r12d; uBytes
0x1800c5969  xor     ecx, ecx; uFlags
0x1800c596b  call    cs:__imp_LocalAlloc
0x1800c5972  nop     dword ptr [rax+rax+00h]
0x1800c5977  mov     rbx, rax
0x1800c597a  test    rax, rax
0x1800c597d  jz      short loc_1800C59EF
0x1800c597f  mov     r8, rax; lpRgnData
0x1800c5982  mov     edx, r12d; nCount
0x1800c5985  mov     rcx, rdi; hrgn
0x1800c5988  call    cs:__imp_GetRegionData
0x1800c598f  nop     dword ptr [rax+rax+00h]
0x1800c5994  cmp     eax, r12d
0x1800c5997  jnz     short loc_1800C59EF
0x1800c5999  mov     eax, [rbx+8]
0x1800c599c  xor     r12d, r12d
0x1800c599f  mov     [rbp+var_38], eax
0x1800c59a2  cmp     r12d, eax
0x1800c59a5  jge     short loc_1800C59E9
0x1800c59a7  mov     rcx, [rbp+var_30]
0x1800c59ab  mov     edx, 415h
0x1800c59b0  movsxd  r8, r12d
0x1800c59b3  add     r8, r8
0x1800c59b6  movzx   eax, word ptr [rbx+r8*8+2Ch]
0x1800c59bc  movzx   r9d, word ptr [rbx+r8*8+24h]
0x1800c59c2  mov     [rsp+68h+var_40], ax
0x1800c59c7  movzx   eax, word ptr [rbx+r8*8+28h]
0x1800c59cd  movzx   r8d, word ptr [rbx+r8*8+20h]
0x1800c59d3  mov     [rsp+68h+var_48], ax
0x1800c59d8  call    bW16Emit4
0x1800c59dd  test    eax, eax
0x1800c59df  jz      short loc_1800C59EF
0x1800c59e1  mov     eax, [rbp+var_38]
0x1800c59e4  inc     r12d
0x1800c59e7  jmp     short loc_1800C59A2
0x1800c59e9  mov     r14d, 1
0x1800c59ef  mov     rcx, r13; ho
0x1800c59f2  call    cs:__imp_DeleteObject
0x1800c59f9  nop     dword ptr [rax+rax+00h]
0x1800c59fe  test    rdi, rdi
0x1800c5a01  jz      short loc_1800C5A12
0x1800c5a03  mov     rcx, rdi; ho
0x1800c5a06  call    cs:__imp_DeleteObject
0x1800c5a0d  nop     dword ptr [rax+rax+00h]
0x1800c5a12  test    r15, r15
0x1800c5a15  jz      short loc_1800C5A26
0x1800c5a17  mov     rcx, r15; ho
0x1800c5a1a  call    cs:__imp_DeleteObject
0x1800c5a21  nop     dword ptr [rax+rax+00h]
0x1800c5a26  test    rsi, rsi
0x1800c5a29  jz      short loc_1800C5A3A
0x1800c5a2b  mov     rcx, rsi; hMem
0x1800c5a2e  call    cs:__imp_LocalFree
0x1800c5a35  nop     dword ptr [rax+rax+00h]
0x1800c5a3a  test    rbx, rbx
0x1800c5a3d  jz      short loc_1800C5A4E
0x1800c5a3f  mov     rcx, rbx; hMem
0x1800c5a42  call    cs:__imp_LocalFree
0x1800c5a49  nop     dword ptr [rax+rax+00h]
0x1800c5a4e  mov     eax, r14d
0x1800c5a51  mov     rcx, [rbp+var_18]
0x1800c5a55  xor     rcx, rsp; StackCookie
0x1800c5a58  call    __security_check_cookie
0x1800c5a5d  add     rsp, 68h
0x1800c5a61  pop     r15
0x1800c5a63  pop     r14
0x1800c5a65  pop     r13
0x1800c5a67  pop     r12
0x1800c5a69  pop     rdi
0x1800c5a6a  pop     rsi
0x1800c5a6b  pop     rbx
0x1800c5a6c  pop     rbp
0x1800c5a6d  retn
```
