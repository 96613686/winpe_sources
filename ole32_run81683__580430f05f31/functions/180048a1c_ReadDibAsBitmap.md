# ReadDibAsBitmap

- ea: `0x180048a1c`
- end: `0x180048bb0`
- name: `ReadDibAsBitmap`
- size: `404`
- prototype: `__int64 __fastcall(IStream *pstm, CData *pdata)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a3218`

## callees

- `0x18000b2d4`
- `0x180048a1c`
- `0x180048bb8`
- `0x1800a22a4`
- `0x1800a63ac`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180048b01`
- `KERNELBASE!GlobalAlloc` at `0x180048b01`
- `KERNELBASE!GlobalFree` at `0x180048b30`
- `KERNELBASE!GlobalFree` at `0x180048b56`
- `KERNELBASE!GlobalFree` at `0x180048b30`
- `KERNELBASE!GlobalFree` at `0x180048b56`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180048b16`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180048b16`
- `GDI32!DeleteObject` at `0x180048b27`
- `GDI32!DeleteObject` at `0x180048b4d`
- `GDI32!DeleteObject` at `0x180048ba3`
- `GDI32!DeleteObject` at `0x180048b27`
- `GDI32!DeleteObject` at `0x180048b4d`
- `GDI32!DeleteObject` at `0x180048ba3`
- `GDI32!GetObjectW` at `0x180048a94`
- `GDI32!GetObjectW` at `0x180048a94`
- `GDI32!GetBitmapBits` at `0x180048b3f`
- `GDI32!GetBitmapBits` at `0x180048b3f`

## pseudocode

```c
__int64 __fastcall ReadDibAsBitmap(IStream *pstm, CData *pdata)
{
  int v3; // ebx
  HBITMAP v4; // rax
  HBITMAP v5; // rbx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  LONG v8; // r15d
  unsigned __int64 v9; // rcx
  int v10; // r14d
  SIZE_T v11; // rdi
  HGLOBAL v12; // rax
  void *v13; // rdi
  tagBITMAP *v14; // rax
  tagBITMAP *v15; // rsi
  tagBITMAP bm; // [rsp+20h] [rbp-40h] BYREF
  CData dataDib; // [rsp+40h] [rbp-20h] BYREF

  dataDib.m_cbSize = 0;
  memset(&dataDib.m_pv, 0, 20);
  memset(&bm, 0, sizeof(bm));
  v3 = OLE2StmToSizedData(pstm, &dataDib, 0, 0);
  if ( v3 >= 0 )
  {
    v4 = UtConvertDibToBitmap(dataDib.m_h);
    v5 = v4;
    if ( v4 )
    {
      if ( GetObjectW(v4, 32, &bm) )
      {
        v6 = (unsigned int)bm.bmWidthBytes * (unsigned __int64)(unsigned int)bm.bmHeight;
        if ( v6 <= 0xFFFFFFFF )
        {
          v7 = bm.bmPlanes * (unsigned __int64)(unsigned int)v6;
          if ( v7 <= 0xFFFFFFFF )
          {
            v8 = bm.bmPlanes * (_DWORD)v6;
            v9 = bm.bmBitsPixel * (unsigned __int64)(unsigned int)v7;
            if ( v9 <= 0xFFFFFFFF )
            {
              v10 = v9;
              v11 = (unsigned int)v9 + 32LL;
              if ( v11 >= (unsigned int)v9 )
              {
                if ( v11 >= GetSafeAllocSize() || (v12 = GlobalAlloc(2u, v11), (v13 = v12) == 0) )
                {
                  DeleteObject(v5);
                  goto LABEL_18;
                }
                v14 = (tagBITMAP *)GlobalLock(v12);
                v15 = v14;
                if ( !v14 )
                {
                  DeleteObject(v5);
                  GlobalFree(v13);
LABEL_18:
                  v3 = -2147024882;
                  goto LABEL_15;
                }
                if ( GetBitmapBits(v5, v8, &v14[1]) == v8 )
                {
                  v3 = 0;
                  *v15 = bm;
                  pdata->m_h = v13;
                  pdata->m_pv = v15;
                  pdata->m_cbSize = v10 + 32;
                  goto LABEL_15;
                }
                DeleteObject(v5);
                GlobalFree(v13);
              }
            }
          }
        }
      }
    }
    v3 = -2147221050;
  }
LABEL_15:
  CData::~CData(&dataDib);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180048a1c  push    rbp
0x180048a1e  push    rbx
0x180048a1f  push    rsi
0x180048a20  push    rdi
0x180048a21  push    r12
0x180048a23  push    r14
0x180048a25  push    r15
0x180048a27  mov     rbp, rsp
0x180048a2a  sub     rsp, 60h
0x180048a2e  xorps   xmm0, xmm0
0x180048a31  mov     [rbp+dataDib.m_cbSize], 0
0x180048a38  mov     r12, pdata
0x180048a3b  mov     [rbp+dataDib.m_h], 0
0x180048a43  lea     pdata, [rbp+dataDib]; pdata
0x180048a47  mov     [rbp+dataDib.m_pv], 0
0x180048a4f  xor     r9d, r9d; cbSizeKnown
0x180048a52  mov     [rbp+dataDib.m_fNoFree], 0
0x180048a59  xor     r8d, r8d; cbSizeDelta
0x180048a5c  movups  xmmword ptr [rbp+bm.bmType], xmm0
0x180048a60  movups  xmmword ptr [rbp+bm.bmPlanes], xmm0
0x180048a64  call    OLE2StmToSizedData
0x180048a69  mov     ebx, eax
0x180048a6b  test    eax, eax
0x180048a6d  js      loc_180048B61
0x180048a73  mov     pstm, [rbp+dataDib.m_h]; hDib
0x180048a77  call    ?UtConvertDibToBitmap@@YAPEAUHBITMAP__@@PEAX@Z; UtConvertDibToBitmap(void *)
0x180048a7c  mov     rbx, rax
0x180048a7f  test    rax, rax
0x180048a82  jz      loc_180048B5C
0x180048a88  lea     r8, [rbp+bm]; pv
0x180048a8c  mov     edx, 20h ; ' '; c
0x180048a91  mov     pstm, rax; h
0x180048a94  call    cs:__imp_GetObjectW
0x180048a9a  test    eax, eax
0x180048a9c  jz      loc_180048B5C
0x180048aa2  mov     eax, [rbp+bm.bmHeight]
0x180048aa5  mov     edx, 0FFFFFFFFh
0x180048aaa  mov     ecx, [rbp+bm.bmWidthBytes]
0x180048aad  imul    rax, pstm
0x180048ab1  cmp     rax, pdata
0x180048ab4  ja      loc_180048B5C
0x180048aba  mov     ecx, eax
0x180048abc  movzx   eax, [rbp+bm.bmPlanes]
0x180048ac0  imul    pstm, rax
0x180048ac4  cmp     pstm, pdata
0x180048ac7  ja      loc_180048B5C
0x180048acd  movzx   eax, [rbp+bm.bmBitsPixel]
0x180048ad1  mov     r15d, ecx
0x180048ad4  mov     ecx, ecx
0x180048ad6  imul    pstm, rax
0x180048ada  cmp     pstm, pdata
0x180048add  ja      short loc_180048B5C
0x180048adf  mov     r14d, ecx
0x180048ae2  lea     rdi, [r14+20h]
0x180048ae6  cmp     rdi, r14
0x180048ae9  jb      short loc_180048B5C
0x180048aeb  call    GetSafeAllocSize
0x180048af0  cmp     rdi, rax
0x180048af3  jnb     loc_180048BA0
0x180048af9  mov     pdata, rdi; dwBytes
0x180048afc  mov     ecx, 2; uFlags
0x180048b01  call    cs:__imp_GlobalAlloc
0x180048b07  mov     rdi, rax
0x180048b0a  test    rax, rax
0x180048b0d  jz      loc_180048BA0
0x180048b13  mov     pstm, rax; hMem
0x180048b16  call    cs:__imp_GlobalLock
0x180048b1c  mov     rsi, rax
0x180048b1f  mov     pstm, rbx; hbit
0x180048b22  test    rax, rax
0x180048b25  jnz     short loc_180048B38
0x180048b27  call    cs:__imp_DeleteObject
0x180048b2d  mov     pstm, rdi; hMem
0x180048b30  call    cs:__imp_GlobalFree
0x180048b36  jmp     short loc_180048BA9
0x180048b38  lea     r8, [rax+20h]; lpvBits
0x180048b3c  mov     edx, r15d; cb
0x180048b3f  call    cs:__imp_GetBitmapBits
0x180048b45  cmp     eax, r15d
0x180048b48  jz      short loc_180048B7B
0x180048b4a  mov     pstm, rbx; ho
0x180048b4d  call    cs:__imp_DeleteObject
0x180048b53  mov     pstm, rdi; hMem
0x180048b56  call    cs:__imp_GlobalFree
0x180048b5c  mov     ebx, 800401C6h
0x180048b61  lea     pstm, [rbp+dataDib]; this
0x180048b65  call    ??1CData@@QEAA@XZ; CData::~CData(void)
0x180048b6a  mov     eax, ebx
0x180048b6c  add     rsp, 60h
0x180048b70  pop     r15
0x180048b72  pop     r14
0x180048b74  pop     r12
0x180048b76  pop     rdi
0x180048b77  pop     rsi
0x180048b78  pop     rbx
0x180048b79  pop     rbp
0x180048b7a  retn
0x180048b7b  movups  xmm0, xmmword ptr [rbp+bm.bmType]
0x180048b7f  lea     eax, [r14+20h]
0x180048b83  xor     ebx, ebx
0x180048b85  movups  xmmword ptr [rsi], xmm0
0x180048b88  movups  xmm1, xmmword ptr [rbp+bm.bmPlanes]
0x180048b8c  movups  xmmword ptr [rsi+10h], xmm1
0x180048b90  mov     [r12+10h], rdi
0x180048b95  mov     [r12+8], rsi
0x180048b9a  mov     [r12], eax
0x180048b9e  jmp     short loc_180048B61
0x180048ba0  mov     pstm, rbx; ho
0x180048ba3  call    cs:__imp_DeleteObject
0x180048ba9  mov     ebx, 8007000Eh
0x180048bae  jmp     short loc_180048B61
```
