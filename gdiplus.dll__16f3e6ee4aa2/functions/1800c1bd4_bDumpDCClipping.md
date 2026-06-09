# bDumpDCClipping

- ea: `0x1800c1bd4`
- end: `0x1800c1e70`
- name: `bDumpDCClipping`
- size: `668`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c2194`
- `0x18013fee0`
- `0x180141aa0`
- `0x180141d38`
- `0x1801430ac`

## callees

- `0x1800c1bd4`
- `0x1800c2474`
- `0x1800c42f4`
- `0x1800fe680`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1c82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1d97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1c82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1e3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1e4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1e3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1e4a`
- `GDI32!GetRgnBox` at `0x1800c1cd6`
- `GDI32!GetRgnBox` at `0x1800c1cd6`
- `GDI32!ExtCreateRegion` at `0x1800c1cbd`
- `GDI32!ExtCreateRegion` at `0x1800c1cbd`
- `GDI32!CombineRgn` at `0x1800c1d6f`
- `GDI32!CombineRgn` at `0x1800c1d6f`
- `GDI32!DeleteObject` at `0x1800c1e12`
- `GDI32!DeleteObject` at `0x1800c1e20`
- `GDI32!DeleteObject` at `0x1800c1e2e`
- `GDI32!DeleteObject` at `0x1800c1e12`
- `GDI32!DeleteObject` at `0x1800c1e20`
- `GDI32!DeleteObject` at `0x1800c1e2e`
- `GDI32!GetRegionData` at `0x1800c1c6c`
- `GDI32!GetRegionData` at `0x1800c1c9d`
- `GDI32!GetRegionData` at `0x1800c1d85`
- `GDI32!GetRegionData` at `0x1800c1dae`
- `GDI32!GetRegionData` at `0x1800c1c6c`
- `GDI32!GetRegionData` at `0x1800c1c9d`
- `GDI32!GetRegionData` at `0x1800c1d85`
- `GDI32!GetRegionData` at `0x1800c1dae`
- `GDI32!GetRandomRgn` at `0x1800c1c4d`
- `GDI32!GetRandomRgn` at `0x1800c1c4d`
- `GDI32!CreateRectRgn` at `0x1800c1c26`
- `GDI32!CreateRectRgn` at `0x1800c1d50`
- `GDI32!CreateRectRgn` at `0x1800c1c26`
- `GDI32!CreateRectRgn` at `0x1800c1d50`

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
0x1800c1bd4  push    rbp
0x1800c1bd6  push    rbx
0x1800c1bd7  push    rsi
0x1800c1bd8  push    rdi
0x1800c1bd9  push    r12
0x1800c1bdb  push    r13
0x1800c1bdd  push    r14
0x1800c1bdf  push    r15
0x1800c1be1  mov     rbp, rsp
0x1800c1be4  sub     rsp, 68h
0x1800c1be8  mov     rax, cs:__security_cookie
0x1800c1bef  xor     rax, rsp
0x1800c1bf2  mov     [rbp+var_18], rax
0x1800c1bf6  xorps   xmm0, xmm0
0x1800c1bf9  mov     [rbp+var_30], rcx
0x1800c1bfd  xor     r8d, r8d
0x1800c1c00  mov     edx, 12Ch
0x1800c1c05  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800c1c09  mov     r12, rcx
0x1800c1c0c  xor     r14d, r14d
0x1800c1c0f  call    bW16Emit1
0x1800c1c14  test    eax, eax
0x1800c1c16  jz      loc_1800C1E50
0x1800c1c1c  xor     r9d, r9d; y2
0x1800c1c1f  xor     r8d, r8d; x2
0x1800c1c22  xor     edx, edx; y1
0x1800c1c24  xor     ecx, ecx; x1
0x1800c1c26  call    cs:__imp_CreateRectRgn
0x1800c1c2c  mov     r13, rax
0x1800c1c2f  test    rax, rax
0x1800c1c32  jz      loc_1800C1E50
0x1800c1c38  mov     rcx, [r12+28h]; hdc
0x1800c1c3d  lea     r8d, [r14+3]; i
0x1800c1c41  mov     rdx, rax; hrgn
0x1800c1c44  xor     edi, edi
0x1800c1c46  xor     r15d, r15d
0x1800c1c49  xor     esi, esi
0x1800c1c4b  xor     ebx, ebx
0x1800c1c4d  call    cs:__imp_GetRandomRgn
0x1800c1c53  cmp     eax, 0FFFFFFFFh
0x1800c1c56  jz      loc_1800C1E0F
0x1800c1c5c  test    eax, eax
0x1800c1c5e  jz      loc_1800C1E09
0x1800c1c64  xor     r8d, r8d; lpRgnData
0x1800c1c67  xor     edx, edx; nCount
0x1800c1c69  mov     rcx, r13; hrgn
0x1800c1c6c  call    cs:__imp_GetRegionData
0x1800c1c72  mov     r12d, eax
0x1800c1c75  test    eax, eax
0x1800c1c77  jz      loc_1800C1E0F
0x1800c1c7d  mov     edx, r12d; uBytes
0x1800c1c80  xor     ecx, ecx; uFlags
0x1800c1c82  call    cs:__imp_LocalAlloc
0x1800c1c88  mov     rsi, rax
0x1800c1c8b  test    rax, rax
0x1800c1c8e  jz      loc_1800C1E0F
0x1800c1c94  mov     r8, rax; lpRgnData
0x1800c1c97  mov     edx, r12d; nCount
0x1800c1c9a  mov     rcx, r13; hrgn
0x1800c1c9d  call    cs:__imp_GetRegionData
0x1800c1ca3  cmp     eax, r12d
0x1800c1ca6  jnz     loc_1800C1E0F
0x1800c1cac  mov     rcx, [rbp+var_30]
0x1800c1cb0  mov     r8, rsi; lpData
0x1800c1cb3  add     rcx, 0CCh; lpx
0x1800c1cba  mov     edx, r12d; nCount
0x1800c1cbd  call    cs:__imp_ExtCreateRegion
0x1800c1cc3  mov     rdi, rax
0x1800c1cc6  test    rax, rax
0x1800c1cc9  jz      loc_1800C1E0F
0x1800c1ccf  lea     rdx, [rbp+rc]; lprc
0x1800c1cd3  mov     rcx, rax; hrgn
0x1800c1cd6  call    cs:__imp_GetRgnBox
0x1800c1cdc  test    eax, eax
0x1800c1cde  jz      loc_1800C1E0F
0x1800c1ce4  mov     ecx, [rbp+rc.right]
0x1800c1ce7  mov     eax, 0FFFF8AD0h
0x1800c1cec  mov     r8d, [rbp+rc.left]
0x1800c1cf0  mov     edx, 7530h
0x1800c1cf5  mov     r9d, [rbp+rc.top]
0x1800c1cf9  cmp     r8d, eax
0x1800c1cfc  cmovl   r8d, eax
0x1800c1d00  cmp     r9d, eax
0x1800c1d03  mov     [rbp+rc.left], r8d
0x1800c1d07  cmovl   r9d, eax
0x1800c1d0b  mov     eax, [rbp+rc.bottom]
0x1800c1d0e  cmp     ecx, edx
0x1800c1d10  mov     [rbp+rc.top], r9d
0x1800c1d14  cmovg   ecx, edx
0x1800c1d17  cmp     eax, edx
0x1800c1d19  mov     [rbp+rc.right], ecx
0x1800c1d1c  cmovg   eax, edx
0x1800c1d1f  mov     edx, 416h
0x1800c1d24  mov     [rsp+68h+var_40], ax
0x1800c1d29  mov     [rsp+68h+var_48], cx
0x1800c1d2e  mov     rcx, [rbp+var_30]
0x1800c1d32  mov     [rbp+rc.bottom], eax
0x1800c1d35  call    bW16Emit4
0x1800c1d3a  test    eax, eax
0x1800c1d3c  jz      loc_1800C1E0F
0x1800c1d42  mov     r9d, [rbp+rc.bottom]; y2
0x1800c1d46  mov     r8d, [rbp+rc.right]; x2
0x1800c1d4a  mov     edx, [rbp+rc.top]; y1
0x1800c1d4d  mov     ecx, [rbp+rc.left]; x1
0x1800c1d50  call    cs:__imp_CreateRectRgn
0x1800c1d56  mov     r15, rax
0x1800c1d59  test    rax, rax
0x1800c1d5c  jz      loc_1800C1E0F
0x1800c1d62  lea     r9d, [r14+4]; iMode
0x1800c1d66  mov     r8, rdi; hrgnSrc2
0x1800c1d69  mov     rdx, rax; hrgnSrc1
0x1800c1d6c  mov     rcx, rdi; hrgnDst
0x1800c1d6f  call    cs:__imp_CombineRgn
0x1800c1d75  test    eax, eax
0x1800c1d77  jz      loc_1800C1E0F
0x1800c1d7d  xor     r8d, r8d; lpRgnData
0x1800c1d80  xor     edx, edx; nCount
0x1800c1d82  mov     rcx, rdi; hrgn
0x1800c1d85  call    cs:__imp_GetRegionData
0x1800c1d8b  mov     r12d, eax
0x1800c1d8e  test    eax, eax
0x1800c1d90  jz      short loc_1800C1E0F
0x1800c1d92  mov     edx, r12d; uBytes
0x1800c1d95  xor     ecx, ecx; uFlags
0x1800c1d97  call    cs:__imp_LocalAlloc
0x1800c1d9d  mov     rbx, rax
0x1800c1da0  test    rax, rax
0x1800c1da3  jz      short loc_1800C1E0F
0x1800c1da5  mov     r8, rax; lpRgnData
0x1800c1da8  mov     edx, r12d; nCount
0x1800c1dab  mov     rcx, rdi; hrgn
0x1800c1dae  call    cs:__imp_GetRegionData
0x1800c1db4  cmp     eax, r12d
0x1800c1db7  jnz     short loc_1800C1E0F
0x1800c1db9  mov     eax, [rbx+8]
0x1800c1dbc  xor     r12d, r12d
0x1800c1dbf  mov     [rbp+var_38], eax
0x1800c1dc2  cmp     r12d, eax
0x1800c1dc5  jge     short loc_1800C1E09
0x1800c1dc7  mov     rcx, [rbp+var_30]
0x1800c1dcb  mov     edx, 415h
0x1800c1dd0  movsxd  r8, r12d
0x1800c1dd3  add     r8, r8
0x1800c1dd6  movzx   eax, word ptr [rbx+r8*8+2Ch]
0x1800c1ddc  movzx   r9d, word ptr [rbx+r8*8+24h]
0x1800c1de2  mov     [rsp+68h+var_40], ax
0x1800c1de7  movzx   eax, word ptr [rbx+r8*8+28h]
0x1800c1ded  movzx   r8d, word ptr [rbx+r8*8+20h]
0x1800c1df3  mov     [rsp+68h+var_48], ax
0x1800c1df8  call    bW16Emit4
0x1800c1dfd  test    eax, eax
0x1800c1dff  jz      short loc_1800C1E0F
0x1800c1e01  mov     eax, [rbp+var_38]
0x1800c1e04  inc     r12d
0x1800c1e07  jmp     short loc_1800C1DC2
0x1800c1e09  mov     r14d, 1
0x1800c1e0f  mov     rcx, r13; ho
0x1800c1e12  call    cs:__imp_DeleteObject
0x1800c1e18  test    rdi, rdi
0x1800c1e1b  jz      short loc_1800C1E26
0x1800c1e1d  mov     rcx, rdi; ho
0x1800c1e20  call    cs:__imp_DeleteObject
0x1800c1e26  test    r15, r15
0x1800c1e29  jz      short loc_1800C1E34
0x1800c1e2b  mov     rcx, r15; ho
0x1800c1e2e  call    cs:__imp_DeleteObject
0x1800c1e34  test    rsi, rsi
0x1800c1e37  jz      short loc_1800C1E42
0x1800c1e39  mov     rcx, rsi; hMem
0x1800c1e3c  call    cs:__imp_LocalFree
0x1800c1e42  test    rbx, rbx
0x1800c1e45  jz      short loc_1800C1E50
0x1800c1e47  mov     rcx, rbx; hMem
0x1800c1e4a  call    cs:__imp_LocalFree
0x1800c1e50  mov     eax, r14d
0x1800c1e53  mov     rcx, [rbp+var_18]
0x1800c1e57  xor     rcx, rsp; StackCookie
0x1800c1e5a  call    __security_check_cookie
0x1800c1e5f  add     rsp, 68h
0x1800c1e63  pop     r15
0x1800c1e65  pop     r14
0x1800c1e67  pop     r13
0x1800c1e69  pop     r12
0x1800c1e6b  pop     rdi
0x1800c1e6c  pop     rsi
0x1800c1e6d  pop     rbx
0x1800c1e6e  pop     rbp
0x1800c1e6f  retn
```
