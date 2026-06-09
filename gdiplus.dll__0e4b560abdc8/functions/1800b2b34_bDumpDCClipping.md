# bDumpDCClipping

- ea: `0x1800b2b34`
- end: `0x1800b2e63`
- name: `bDumpDCClipping`
- size: `815`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b0ff0`
- `0x180140de0`
- `0x1801443b8`
- `0x180144674`
- `0x180145bf8`

## callees

- `0x1800b1574`
- `0x1800b2190`
- `0x1800b2b34`
- `0x1800e9380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2bfe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2d3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2bfe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2d3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2e29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2e29`
- `GDI32!GetRgnBox` at `0x1800b2c60`
- `GDI32!GetRgnBox` at `0x1800b2c60`
- `GDI32!ExtCreateRegion` at `0x1800b2c41`
- `GDI32!ExtCreateRegion` at `0x1800b2c41`
- `GDI32!CombineRgn` at `0x1800b2d04`
- `GDI32!CombineRgn` at `0x1800b2d04`
- `GDI32!DeleteObject` at `0x1800b2dd9`
- `GDI32!DeleteObject` at `0x1800b2ded`
- `GDI32!DeleteObject` at `0x1800b2e01`
- `GDI32!DeleteObject` at `0x1800b2dd9`
- `GDI32!DeleteObject` at `0x1800b2ded`
- `GDI32!DeleteObject` at `0x1800b2e01`
- `GDI32!GetRegionData` at `0x1800b2be2`
- `GDI32!GetRegionData` at `0x1800b2c1f`
- `GDI32!GetRegionData` at `0x1800b2d20`
- `GDI32!GetRegionData` at `0x1800b2d59`
- `GDI32!GetRegionData` at `0x1800b2be2`
- `GDI32!GetRegionData` at `0x1800b2c1f`
- `GDI32!GetRegionData` at `0x1800b2d20`
- `GDI32!GetRegionData` at `0x1800b2d59`
- `GDI32!GetRandomRgn` at `0x1800b2bbd`
- `GDI32!GetRandomRgn` at `0x1800b2bbd`
- `GDI32!CreateRectRgn` at `0x1800b2b9a`
- `GDI32!CreateRectRgn` at `0x1800b2cdf`
- `GDI32!CreateRectRgn` at `0x1800b2b9a`
- `GDI32!CreateRectRgn` at `0x1800b2cdf`

## pseudocode

```c
__int64 __fastcall bDumpDCClipping(__int64 a1)
{
  unsigned int v1; // r14d
  HRGN v3; // rbx
  HRGN v4; // r15
  RGNDATA *v5; // rsi
  int *v6; // rdi
  HRGN RectRgn; // rax
  HRGN v8; // r12
  int RandomRgn; // eax
  DWORD RegionData; // eax
  DWORD v11; // r14d
  struct _RGNDATA *v12; // rax
  HRGN Region; // rax
  LONG right; // ecx
  LONG left; // r8d
  LONG top; // r9d
  LONG bottom; // eax
  HRGN v18; // rax
  DWORD v19; // eax
  DWORD v20; // r14d
  struct _RGNDATA *v21; // rax
  __int64 v22; // rcx
  __int16 *v23; // r14
  __int64 v24; // rax
  __int64 v26; // [rsp+38h] [rbp-28h]
  __int64 v27; // [rsp+40h] [rbp-20h]
  struct tagRECT rc; // [rsp+48h] [rbp-18h] BYREF

  v1 = 0;
  rc = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( !(unsigned int)bW16Emit1(a1, 300, 0) )
    return v1;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v8 = RectRgn;
  if ( !RectRgn )
    return v1;
  RandomRgn = GetRandomRgn(*(HDC *)(a1 + 40), RectRgn, 3);
  if ( RandomRgn != -1 )
  {
    if ( RandomRgn )
    {
      RegionData = GetRegionData(v8, 0, 0);
      v11 = RegionData;
      if ( !RegionData
        || (v12 = (struct _RGNDATA *)LocalAlloc(0, RegionData), (v5 = v12) == 0)
        || GetRegionData(v8, v11, v12) != v11 )
      {
        v1 = 0;
        goto LABEL_32;
      }
      Region = ExtCreateRegion((const XFORM *)(a1 + 204), v11, v5);
      v3 = Region;
      if ( !Region || !GetRgnBox(Region, &rc) )
        goto LABEL_30;
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
      if ( !(unsigned int)bW16Emit4(a1, 1046, left, top, right, bottom)
        || (v18 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom), (v4 = v18) == 0)
        || !CombineRgn(v3, v18, v3, 4)
        || (v19 = GetRegionData(v3, 0, 0), (v20 = v19) == 0) )
      {
LABEL_30:
        v1 = 0;
        goto LABEL_32;
      }
      v21 = (struct _RGNDATA *)LocalAlloc(0, v19);
      v6 = (int *)v21;
      if ( !v21 || GetRegionData(v3, v20, v21) != v20 )
      {
LABEL_29:
        v1 = 0;
        goto LABEL_32;
      }
      v22 = v6[2];
      v23 = (__int16 *)(v6 + 10);
      v27 = v22;
      v24 = 0;
      while ( 1 )
      {
        v26 = v24;
        if ( v24 >= v22 )
          break;
        if ( !(unsigned int)bW16Emit4(
                              a1,
                              1045,
                              (unsigned __int16)*(v23 - 4),
                              (unsigned __int16)*(v23 - 2),
                              *v23,
                              v23[2]) )
          goto LABEL_29;
        v22 = v27;
        v24 = v26 + 1;
        v23 += 8;
      }
    }
    v1 = 1;
  }
LABEL_32:
  DeleteObject(v8);
  if ( v3 )
    DeleteObject(v3);
  if ( v4 )
    DeleteObject(v4);
  if ( v5 )
    LocalFree(v5);
  if ( v6 )
    LocalFree(v6);
  return v1;
}

```

## disassembly

```asm
0x1800b2b34  mov     [rsp-28h+arg_8], rbx
0x1800b2b39  mov     [rsp-28h+arg_10], rsi
0x1800b2b3e  mov     [rsp-28h+arg_18], rdi
0x1800b2b43  push    rbp
0x1800b2b44  push    r12
0x1800b2b46  push    r13
0x1800b2b48  push    r14
0x1800b2b4a  push    r15
0x1800b2b4c  mov     rbp, rsp
0x1800b2b4f  sub     rsp, 60h
0x1800b2b53  mov     rax, cs:__security_cookie
0x1800b2b5a  xor     rax, rsp
0x1800b2b5d  mov     [rbp+var_8], rax
0x1800b2b61  xorps   xmm0, xmm0
0x1800b2b64  xor     r14d, r14d
0x1800b2b67  xor     r8d, r8d
0x1800b2b6a  mov     [rbp+var_30], r14d
0x1800b2b6e  mov     edx, 12Ch
0x1800b2b73  mov     r13, rcx
0x1800b2b76  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800b2b7a  xor     ebx, ebx
0x1800b2b7c  xor     r15d, r15d
0x1800b2b7f  xor     esi, esi
0x1800b2b81  xor     edi, edi
0x1800b2b83  call    bW16Emit1
0x1800b2b88  test    eax, eax
0x1800b2b8a  jz      loc_1800B2E35
0x1800b2b90  xor     r9d, r9d; y2
0x1800b2b93  xor     r8d, r8d; x2
0x1800b2b96  xor     edx, edx; y1
0x1800b2b98  xor     ecx, ecx; x1
0x1800b2b9a  call    cs:__imp_CreateRectRgn
0x1800b2ba1  nop     dword ptr [rax+rax+00h]
0x1800b2ba6  mov     r12, rax
0x1800b2ba9  test    rax, rax
0x1800b2bac  jz      loc_1800B2E35
0x1800b2bb2  mov     rcx, [r13+28h]; hdc
0x1800b2bb6  lea     r8d, [r14+3]; i
0x1800b2bba  mov     rdx, rax; hrgn
0x1800b2bbd  call    cs:__imp_GetRandomRgn
0x1800b2bc4  nop     dword ptr [rax+rax+00h]
0x1800b2bc9  cmp     eax, 0FFFFFFFFh
0x1800b2bcc  jz      loc_1800B2DD6
0x1800b2bd2  test    eax, eax
0x1800b2bd4  jz      loc_1800B2DC0
0x1800b2bda  xor     r8d, r8d; lpRgnData
0x1800b2bdd  xor     edx, edx; nCount
0x1800b2bdf  mov     rcx, r12; hrgn
0x1800b2be2  call    cs:__imp_GetRegionData
0x1800b2be9  nop     dword ptr [rax+rax+00h]
0x1800b2bee  mov     r14d, eax
0x1800b2bf1  test    eax, eax
0x1800b2bf3  jz      loc_1800B2DD3
0x1800b2bf9  mov     edx, r14d; uBytes
0x1800b2bfc  xor     ecx, ecx; uFlags
0x1800b2bfe  call    cs:__imp_LocalAlloc
0x1800b2c05  nop     dword ptr [rax+rax+00h]
0x1800b2c0a  mov     rsi, rax
0x1800b2c0d  test    rax, rax
0x1800b2c10  jz      loc_1800B2DD3
0x1800b2c16  mov     r8, rax; lpRgnData
0x1800b2c19  mov     edx, r14d; nCount
0x1800b2c1c  mov     rcx, r12; hrgn
0x1800b2c1f  call    cs:__imp_GetRegionData
0x1800b2c26  nop     dword ptr [rax+rax+00h]
0x1800b2c2b  cmp     eax, r14d
0x1800b2c2e  jnz     loc_1800B2DD3
0x1800b2c34  lea     rcx, [r13+0CCh]; lpx
0x1800b2c3b  mov     r8, rsi; lpData
0x1800b2c3e  mov     edx, r14d; nCount
0x1800b2c41  call    cs:__imp_ExtCreateRegion
0x1800b2c48  nop     dword ptr [rax+rax+00h]
0x1800b2c4d  mov     rbx, rax
0x1800b2c50  test    rax, rax
0x1800b2c53  jz      loc_1800B2DCE
0x1800b2c59  lea     rdx, [rbp+rc]; lprc
0x1800b2c5d  mov     rcx, rax; hrgn
0x1800b2c60  call    cs:__imp_GetRgnBox
0x1800b2c67  nop     dword ptr [rax+rax+00h]
0x1800b2c6c  test    eax, eax
0x1800b2c6e  jz      loc_1800B2DCE
0x1800b2c74  mov     ecx, [rbp+rc.right]
0x1800b2c77  mov     eax, 0FFFF8AD0h
0x1800b2c7c  mov     r8d, [rbp+rc.left]
0x1800b2c80  mov     edx, 7530h
0x1800b2c85  mov     r9d, [rbp+rc.top]
0x1800b2c89  cmp     r8d, eax
0x1800b2c8c  cmovl   r8d, eax
0x1800b2c90  cmp     r9d, eax
0x1800b2c93  mov     [rbp+rc.left], r8d
0x1800b2c97  cmovl   r9d, eax
0x1800b2c9b  mov     eax, [rbp+rc.bottom]
0x1800b2c9e  cmp     ecx, edx
0x1800b2ca0  mov     [rbp+rc.top], r9d
0x1800b2ca4  cmovg   ecx, edx
0x1800b2ca7  cmp     eax, edx
0x1800b2ca9  mov     [rbp+rc.right], ecx
0x1800b2cac  cmovg   eax, edx
0x1800b2caf  mov     edx, 416h
0x1800b2cb4  mov     [rsp+60h+var_38], ax
0x1800b2cb9  mov     [rsp+60h+var_40], cx
0x1800b2cbe  mov     rcx, r13
0x1800b2cc1  mov     [rbp+rc.bottom], eax
0x1800b2cc4  call    bW16Emit4
0x1800b2cc9  test    eax, eax
0x1800b2ccb  jz      loc_1800B2DCE
0x1800b2cd1  mov     r9d, [rbp+rc.bottom]; y2
0x1800b2cd5  mov     r8d, [rbp+rc.right]; x2
0x1800b2cd9  mov     edx, [rbp+rc.top]; y1
0x1800b2cdc  mov     ecx, [rbp+rc.left]; x1
0x1800b2cdf  call    cs:__imp_CreateRectRgn
0x1800b2ce6  nop     dword ptr [rax+rax+00h]
0x1800b2ceb  mov     r15, rax
0x1800b2cee  test    rax, rax
0x1800b2cf1  jz      loc_1800B2DCE
0x1800b2cf7  lea     r9d, [rdi+4]; iMode
0x1800b2cfb  mov     r8, rbx; hrgnSrc2
0x1800b2cfe  mov     rdx, rax; hrgnSrc1
0x1800b2d01  mov     rcx, rbx; hrgnDst
0x1800b2d04  call    cs:__imp_CombineRgn
0x1800b2d0b  nop     dword ptr [rax+rax+00h]
0x1800b2d10  test    eax, eax
0x1800b2d12  jz      loc_1800B2DCE
0x1800b2d18  xor     r8d, r8d; lpRgnData
0x1800b2d1b  xor     edx, edx; nCount
0x1800b2d1d  mov     rcx, rbx; hrgn
0x1800b2d20  call    cs:__imp_GetRegionData
0x1800b2d27  nop     dword ptr [rax+rax+00h]
0x1800b2d2c  mov     r14d, eax
0x1800b2d2f  test    eax, eax
0x1800b2d31  jz      loc_1800B2DCE
0x1800b2d37  mov     edx, r14d; uBytes
0x1800b2d3a  xor     ecx, ecx; uFlags
0x1800b2d3c  call    cs:__imp_LocalAlloc
0x1800b2d43  nop     dword ptr [rax+rax+00h]
0x1800b2d48  mov     rdi, rax
0x1800b2d4b  test    rax, rax
0x1800b2d4e  jz      short loc_1800B2DC8
0x1800b2d50  mov     r8, rax; lpRgnData
0x1800b2d53  mov     edx, r14d; nCount
0x1800b2d56  mov     rcx, rbx; hrgn
0x1800b2d59  call    cs:__imp_GetRegionData
0x1800b2d60  nop     dword ptr [rax+rax+00h]
0x1800b2d65  cmp     eax, r14d
0x1800b2d68  jnz     short loc_1800B2DC8
0x1800b2d6a  movsxd  rcx, dword ptr [rdi+8]
0x1800b2d6e  lea     r14, [rdi+28h]
0x1800b2d72  mov     [rbp+var_20], rcx
0x1800b2d76  xor     eax, eax
0x1800b2d78  mov     [rbp+var_28], rax
0x1800b2d7c  cmp     rax, rcx
0x1800b2d7f  jge     short loc_1800B2DC0
0x1800b2d81  movzx   eax, word ptr [r14+4]
0x1800b2d86  mov     edx, 415h
0x1800b2d8b  movzx   r9d, word ptr [r14-4]
0x1800b2d90  mov     rcx, r13
0x1800b2d93  movzx   r8d, word ptr [r14-8]
0x1800b2d98  mov     [rsp+60h+var_38], ax
0x1800b2d9d  movzx   eax, word ptr [r14]
0x1800b2da1  mov     [rsp+60h+var_40], ax
0x1800b2da6  call    bW16Emit4
0x1800b2dab  test    eax, eax
0x1800b2dad  jz      short loc_1800B2DC8
0x1800b2daf  mov     rax, [rbp+var_28]
0x1800b2db3  mov     rcx, [rbp+var_20]
0x1800b2db7  inc     rax
0x1800b2dba  add     r14, 10h
0x1800b2dbe  jmp     short loc_1800B2D78
0x1800b2dc0  mov     r14d, 1
0x1800b2dc6  jmp     short loc_1800B2DD6
0x1800b2dc8  mov     r14d, [rbp+var_30]
0x1800b2dcc  jmp     short loc_1800B2DD6
0x1800b2dce  mov     r14d, edi
0x1800b2dd1  jmp     short loc_1800B2DD6
0x1800b2dd3  mov     r14d, ebx
0x1800b2dd6  mov     rcx, r12; ho
0x1800b2dd9  call    cs:__imp_DeleteObject
0x1800b2de0  nop     dword ptr [rax+rax+00h]
0x1800b2de5  test    rbx, rbx
0x1800b2de8  jz      short loc_1800B2DF9
0x1800b2dea  mov     rcx, rbx; ho
0x1800b2ded  call    cs:__imp_DeleteObject
0x1800b2df4  nop     dword ptr [rax+rax+00h]
0x1800b2df9  test    r15, r15
0x1800b2dfc  jz      short loc_1800B2E0D
0x1800b2dfe  mov     rcx, r15; ho
0x1800b2e01  call    cs:__imp_DeleteObject
0x1800b2e08  nop     dword ptr [rax+rax+00h]
0x1800b2e0d  test    rsi, rsi
0x1800b2e10  jz      short loc_1800B2E21
0x1800b2e12  mov     rcx, rsi; hMem
0x1800b2e15  call    cs:__imp_LocalFree
0x1800b2e1c  nop     dword ptr [rax+rax+00h]
0x1800b2e21  test    rdi, rdi
0x1800b2e24  jz      short loc_1800B2E35
0x1800b2e26  mov     rcx, rdi; hMem
0x1800b2e29  call    cs:__imp_LocalFree
0x1800b2e30  nop     dword ptr [rax+rax+00h]
0x1800b2e35  mov     eax, r14d
0x1800b2e38  mov     rcx, [rbp+var_8]
0x1800b2e3c  xor     rcx, rsp; StackCookie
0x1800b2e3f  call    __security_check_cookie
0x1800b2e44  lea     r11, [rsp+60h+var_s0]
0x1800b2e49  mov     rbx, [r11+38h]
0x1800b2e4d  mov     rsi, [r11+40h]
0x1800b2e51  mov     rdi, [r11+48h]
0x1800b2e55  mov     rsp, r11
0x1800b2e58  pop     r15
0x1800b2e5a  pop     r14
0x1800b2e5c  pop     r13
0x1800b2e5e  pop     r12
0x1800b2e60  pop     rbp
0x1800b2e61  retn
```
