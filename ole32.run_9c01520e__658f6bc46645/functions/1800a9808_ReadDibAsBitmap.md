# ReadDibAsBitmap

- ea: `0x1800a9808`
- end: `0x1800a99ee`
- name: `ReadDibAsBitmap`
- size: `486`
- prototype: `HRESULT __fastcall(IStream *pstm, CData *pdata)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a9630`

## callees

- `0x18000a574`
- `0x1800a6d64`
- `0x1800a8594`
- `0x1800a9808`
- `0x1800ad4bc`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a98fc`
- `KERNELBASE!GlobalAlloc` at `0x1800a98fc`
- `KERNELBASE!GlobalFree` at `0x1800a993d`
- `KERNELBASE!GlobalFree` at `0x1800a9978`
- `KERNELBASE!GlobalFree` at `0x1800a993d`
- `KERNELBASE!GlobalFree` at `0x1800a9978`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a9917`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a9917`
- `GDI32!DeleteObject` at `0x1800a992e`
- `GDI32!DeleteObject` at `0x1800a9969`
- `GDI32!DeleteObject` at `0x1800a99db`
- `GDI32!DeleteObject` at `0x1800a992e`
- `GDI32!DeleteObject` at `0x1800a9969`
- `GDI32!DeleteObject` at `0x1800a99db`
- `GDI32!GetObjectW` at `0x1800a9881`
- `GDI32!GetObjectW` at `0x1800a9881`
- `GDI32!GetBitmapBits` at `0x1800a9955`
- `GDI32!GetBitmapBits` at `0x1800a9955`

## pseudocode

```c
__int64 __fastcall ReadDibAsBitmap(IStream *pstm, CData *pdata)
{
  int v3; // ebx
  HBITMAP__ *v4; // rax
  HBITMAP v5; // rbx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rdi
  HGLOBAL v10; // rax
  void *v11; // rdi
  tagBITMAP *v12; // rax
  tagBITMAP *v13; // rsi
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
          v7 = (unsigned int)v6 * (unsigned __int64)bm.bmPlanes;
          if ( v7 <= 0xFFFFFFFF )
          {
            v8 = (unsigned int)v7 * (unsigned __int64)bm.bmBitsPixel;
            if ( v8 <= 0xFFFFFFFF )
            {
              v9 = (unsigned int)v8 + 32LL;
              if ( v9 >= (unsigned int)v8 )
              {
                if ( v9 >= GetSafeAllocSize() || (v10 = GlobalAlloc(2u, (unsigned int)v8 + 32LL), (v11 = v10) == 0) )
                {
                  DeleteObject(v5);
                  goto LABEL_18;
                }
                v12 = (tagBITMAP *)GlobalLock(v10);
                v13 = v12;
                if ( !v12 )
                {
                  DeleteObject(v5);
                  GlobalFree(v11);
LABEL_18:
                  v3 = -2147024882;
                  goto LABEL_15;
                }
                if ( GetBitmapBits(v5, v7, &v12[1]) == (_DWORD)v7 )
                {
                  v3 = 0;
                  *v13 = bm;
                  pdata->m_h = v11;
                  pdata->m_pv = v13;
                  pdata->m_cbSize = v8 + 32;
                  goto LABEL_15;
                }
                DeleteObject(v5);
                GlobalFree(v11);
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
0x1800a9808  mov     rax, rsp
0x1800a980b  mov     [rax+8], rbx
0x1800a980f  mov     [rax+10h], rsi
0x1800a9813  mov     [rax+18h], rdi
0x1800a9817  mov     [rax+20h], r12
0x1800a981b  push    rbp
0x1800a981c  push    r14
0x1800a981e  push    r15
0x1800a9820  mov     rbp, rsp
0x1800a9823  sub     rsp, 60h
0x1800a9827  and     [rbp+dataDib.m_cbSize], 0
0x1800a982b  xorps   xmm0, xmm0
0x1800a982e  and     [rbp+dataDib.m_h], 0
0x1800a9833  mov     r12, pdata
0x1800a9836  and     [rbp+dataDib.m_pv], 0
0x1800a983b  lea     pdata, [rbp+dataDib]; pdata
0x1800a983f  and     [rbp+dataDib.m_fNoFree], 0
0x1800a9843  xor     r9d, r9d; cbSizeKnown
0x1800a9846  xor     r8d, r8d; cbSizeDelta
0x1800a9849  movups  xmmword ptr [rbp+bm.bmType], xmm0
0x1800a984d  movups  xmmword ptr [rbp+bm.bmPlanes], xmm0
0x1800a9851  call    OLE2StmToSizedData
0x1800a9856  mov     ebx, eax
0x1800a9858  test    eax, eax
0x1800a985a  js      loc_1800A9989
0x1800a9860  mov     pstm, [rbp+dataDib.m_h]; hDib
0x1800a9864  call    ?UtConvertDibToBitmap@@YAPEAUHBITMAP__@@PEAX@Z; UtConvertDibToBitmap(void *)
0x1800a9869  mov     rbx, rax
0x1800a986c  test    rax, rax
0x1800a986f  jz      loc_1800A9984
0x1800a9875  lea     r8, [rbp+bm]; pv
0x1800a9879  mov     edx, 20h ; ' '; c
0x1800a987e  mov     pstm, rax; h
0x1800a9881  call    cs:__imp_GetObjectW
0x1800a9888  nop     dword ptr [rax+rax+00h]
0x1800a988d  test    eax, eax
0x1800a988f  jz      loc_1800A9984
0x1800a9895  mov     ecx, [rbp+bm.bmWidthBytes]
0x1800a9898  mov     eax, [rbp+bm.bmHeight]
0x1800a989b  imul    rax, pstm
0x1800a989f  mov     ecx, 0FFFFFFFFh
0x1800a98a4  cmp     rax, pstm
0x1800a98a7  ja      loc_1800A9984
0x1800a98ad  movzx   r14d, [rbp+bm.bmPlanes]
0x1800a98b2  mov     eax, eax
0x1800a98b4  imul    r14, rax
0x1800a98b8  cmp     r14, pstm
0x1800a98bb  ja      loc_1800A9984
0x1800a98c1  movzx   r15d, [rbp+bm.bmBitsPixel]
0x1800a98c6  mov     eax, r14d
0x1800a98c9  imul    r15, rax
0x1800a98cd  cmp     r15, pstm
0x1800a98d0  ja      loc_1800A9984
0x1800a98d6  mov     eax, r15d
0x1800a98d9  lea     rdi, [rax+20h]
0x1800a98dd  cmp     rdi, rax
0x1800a98e0  jb      loc_1800A9984
0x1800a98e6  call    GetSafeAllocSize
0x1800a98eb  cmp     rdi, rax
0x1800a98ee  jnb     loc_1800A99D8
0x1800a98f4  mov     pdata, rdi; dwBytes
0x1800a98f7  mov     ecx, 2; uFlags
0x1800a98fc  call    cs:__imp_GlobalAlloc
0x1800a9903  nop     dword ptr [rax+rax+00h]
0x1800a9908  mov     rdi, rax
0x1800a990b  test    rax, rax
0x1800a990e  jz      loc_1800A99D8
0x1800a9914  mov     pstm, rax; hMem
0x1800a9917  call    cs:__imp_GlobalLock
0x1800a991e  nop     dword ptr [rax+rax+00h]
0x1800a9923  mov     rsi, rax
0x1800a9926  mov     pstm, rbx; hbit
0x1800a9929  test    rax, rax
0x1800a992c  jnz     short loc_1800A994E
0x1800a992e  call    cs:__imp_DeleteObject
0x1800a9935  nop     dword ptr [rax+rax+00h]
0x1800a993a  mov     pstm, rdi; hMem
0x1800a993d  call    cs:__imp_GlobalFree
0x1800a9944  nop     dword ptr [rax+rax+00h]
0x1800a9949  jmp     loc_1800A99E7
0x1800a994e  lea     r8, [rax+20h]; lpvBits
0x1800a9952  mov     edx, r14d; cb
0x1800a9955  call    cs:__imp_GetBitmapBits
0x1800a995c  nop     dword ptr [rax+rax+00h]
0x1800a9961  cmp     eax, r14d
0x1800a9964  jz      short loc_1800A99B3
0x1800a9966  mov     pstm, rbx; ho
0x1800a9969  call    cs:__imp_DeleteObject
0x1800a9970  nop     dword ptr [rax+rax+00h]
0x1800a9975  mov     pstm, rdi; hMem
0x1800a9978  call    cs:__imp_GlobalFree
0x1800a997f  nop     dword ptr [rax+rax+00h]
0x1800a9984  mov     ebx, 800401C6h
0x1800a9989  lea     pstm, [rbp+dataDib]; this
0x1800a998d  call    ??1CData@@QEAA@XZ; CData::~CData(void)
0x1800a9992  lea     r11, [rsp+60h+var_s0]
0x1800a9997  mov     eax, ebx
0x1800a9999  mov     rbx, [r11+20h]
0x1800a999d  mov     rsi, [r11+28h]
0x1800a99a1  mov     rdi, [r11+30h]
0x1800a99a5  mov     r12, [r11+38h]
0x1800a99a9  mov     rsp, r11
0x1800a99ac  pop     r15
0x1800a99ae  pop     r14
0x1800a99b0  pop     rbp
0x1800a99b1  retn
0x1800a99b3  movups  xmm0, xmmword ptr [rbp+bm.bmType]
0x1800a99b7  lea     eax, [r15+20h]
0x1800a99bb  xor     ebx, ebx
0x1800a99bd  movups  xmmword ptr [rsi], xmm0
0x1800a99c0  movups  xmm1, xmmword ptr [rbp+bm.bmPlanes]
0x1800a99c4  movups  xmmword ptr [rsi+10h], xmm1
0x1800a99c8  mov     [r12+10h], rdi
0x1800a99cd  mov     [r12+8], rsi
0x1800a99d2  mov     [r12], eax
0x1800a99d6  jmp     short loc_1800A9989
0x1800a99d8  mov     pstm, rbx; ho
0x1800a99db  call    cs:__imp_DeleteObject
0x1800a99e2  nop     dword ptr [rax+rax+00h]
0x1800a99e7  mov     ebx, 8007000Eh
0x1800a99ec  jmp     short loc_1800A9989
```
