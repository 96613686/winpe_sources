# CImageList::_GetContentBounds(int,tagRECT *,int *)

- ea: `0x18009e664`
- end: `0x18009e9ca`
- name: `?_GetContentBounds@CImageList@@IEAAJHPEAUtagRECT@@PEAH@Z`
- size: `870`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int, struct tagRECT *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009e57c`

## callees

- `0x18009e664`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e96f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e96f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e7a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e7a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e97d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e97d`
- `GDI32!DeleteObject` at `0x18009e993`
- `GDI32!DeleteObject` at `0x18009e993`
- `GDI32!SelectObject` at `0x18009e7bd`
- `GDI32!SelectObject` at `0x18009e7bd`
- `GDI32!DeleteDC` at `0x18009e989`
- `GDI32!DeleteDC` at `0x18009e989`
- `GDI32!CreateCompatibleDC` at `0x18009e76a`
- `GDI32!CreateCompatibleDC` at `0x18009e76a`
- `GDI32!CreateBitmap` at `0x18009e750`
- `GDI32!CreateBitmap` at `0x18009e750`
- `GDI32!BitBlt` at `0x18009e7f6`
- `GDI32!BitBlt` at `0x18009e7f6`
- `GDI32!GetBitmapBits` at `0x18009e806`
- `GDI32!GetBitmapBits` at `0x18009e806`
- `USER32!SetRect` at `0x18009e6d9`
- `USER32!SetRect` at `0x18009e6f5`
- `USER32!SetRect` at `0x18009e6d9`
- `USER32!SetRect` at `0x18009e6f5`

## pseudocode

```c
__int64 __fastcall CImageList::_GetContentBounds(CImageList *this, int a2, struct tagRECT *a3, int *a4)
{
  int v5; // esi
  int v6; // r12d
  unsigned int v7; // r14d
  unsigned __int64 v8; // r15
  unsigned int v9; // ebx
  LONG v10; // r13d
  HANDLE ProcessHeap; // rcx
  char *v12; // r15
  LONG bottom; // edi
  LONG v14; // r13d
  LONG right; // r10d
  LONG top; // r8d
  LONG left; // r11d
  int v18; // edx
  int v19; // r9d
  __int64 i; // rcx
  int v21; // r14d
  _BYTE *v22; // r12
  int j; // r9d
  HANDLE v24; // rax
  int v26; // [rsp+54h] [rbp-55h]
  HDC hdc; // [rsp+60h] [rbp-49h]
  HBITMAP h; // [rsp+68h] [rbp-41h]
  unsigned int v29; // [rsp+70h] [rbp-39h]
  __int64 v30; // [rsp+78h] [rbp-31h]
  struct tagRECT v33; // [rsp+90h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp-9h]
  struct tagRECT rc; // [rsp+A8h] [rbp-1h] BYREF

  rc = 0;
  v33 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 >= 0 && a2 < *((_DWORD *)this + 29) )
    SetRect(
      &rc,
      0,
      a2 * *((_DWORD *)this + 33),
      *((_DWORD *)this + 32),
      a2 * *((_DWORD *)this + 33) + *((_DWORD *)this + 33));
  SetRect(&v33, 0x7FFF, 0x7FFF, 0, 0);
  v5 = rc.right - rc.left;
  v6 = rc.bottom - rc.top;
  v7 = 2 * ((unsigned __int64)(rc.right - rc.left + 15LL) >> 4);
  v26 = rc.bottom - rc.top;
  v8 = v7 * (unsigned __int64)(unsigned int)(rc.bottom - rc.top);
  v30 = v7;
  v29 = v7;
  if ( v8 > 0xFFFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v9 = 1;
    h = CreateBitmap(v5, v6, 1u, 1u, 0);
    if ( h )
    {
      hdc = CreateCompatibleDC(*((HDC *)this + 25));
      if ( hdc )
      {
        v10 = v8;
        ProcessHeap = GetProcessHeap();
        lpMem = 0;
        if ( is_mul_ok(1u, (unsigned int)v8) )
        {
          v12 = (char *)HeapAlloc(ProcessHeap, (1 * (unsigned __int128)(unsigned int)v8) >> 64, (unsigned int)v8);
          if ( v12 )
          {
            SelectObject(hdc, h);
            BitBlt(hdc, 0, 0, v5, v6, *((HDC *)this + 25), rc.left, rc.top, 0xCC0020u);
            GetBitmapBits(h, v10, v12);
            bottom = v33.bottom;
            v14 = 0;
            right = v33.right;
            top = v33.top;
            left = v33.left;
            if ( v6 <= 0 )
            {
              v22 = v12;
            }
            else
            {
              lpMem = v12;
              v18 = v5 >> 3;
              do
              {
                v19 = 0;
                for ( i = 0; (int)i < v18; i = (unsigned int)(i + 1) )
                {
                  if ( v12[i] != -1 )
                    break;
                  v19 += 8;
                }
                if ( v19 < v5 )
                {
                  v21 = v14 * v7;
                  do
                  {
                    if ( ((unsigned __int8)(1 << (7 - (v19 & 7))) & *((_BYTE *)lpMem + (unsigned int)(v21 + (v19 >> 3)))) == 0 )
                    {
                      if ( left >= v19 )
                        left = v19;
                      v33.left = left;
                      if ( right <= v19 + 1 )
                        right = v19 + 1;
                      v33.right = right;
                      if ( top >= v14 )
                        top = v14;
                      v33.top = top;
                      if ( bottom <= v14 + 1 )
                        bottom = v14 + 1;
                      v33.bottom = bottom;
                      if ( v19 >= left && v19 < right )
                        v19 = right - 1;
                    }
                    ++v19;
                  }
                  while ( v19 < v5 );
                  v7 = v29;
                  v6 = v26;
                  v18 = v5 >> 3;
                }
                v12 += v30;
                ++v14;
              }
              while ( v14 < v6 );
              v22 = lpMem;
            }
            if ( left == 0x7FFF )
              left = 0;
            v33.left = left;
            if ( top == 0x7FFF )
              top = 0;
            v33.top = top;
            *a3 = v33;
            if ( a4 )
            {
              while ( top < bottom )
              {
                for ( j = left; j < right; ++j )
                {
                  if ( ((unsigned __int8)(1 << (7 - (j & 7))) & v22[top * v7 + (j >> 3)]) != 0 )
                    break;
                }
                if ( j != right )
                  break;
                ++top;
              }
              if ( top == bottom )
                *a4 = 1;
            }
            v24 = GetProcessHeap();
            HeapFree(v24, 0, v22);
            v9 = 0;
          }
        }
        DeleteDC(hdc);
      }
      DeleteObject(h);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18009e664  push    rbp
0x18009e666  push    rbx
0x18009e667  push    rsi
0x18009e668  push    rdi
0x18009e669  push    r12
0x18009e66b  push    r13
0x18009e66d  push    r14
0x18009e66f  push    r15
0x18009e671  lea     rbp, [rsp-1Fh]
0x18009e676  sub     rsp, 0C8h
0x18009e67d  mov     rax, cs:__security_cookie
0x18009e684  xor     rax, rsp
0x18009e687  mov     [rbp+57h+var_48], rax
0x18009e68b  xor     r13d, r13d
0x18009e68e  mov     [rbp+57h+var_78], r9
0x18009e692  mov     [rbp+57h+var_80], r8
0x18009e696  xorps   xmm0, xmm0
0x18009e699  xorps   xmm1, xmm1
0x18009e69c  mov     rdi, rcx
0x18009e69f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18009e6a3  movups  xmmword ptr [rbp+57h+var_70.left], xmm1
0x18009e6a7  test    r9, r9
0x18009e6aa  jz      short loc_18009E6AF
0x18009e6ac  mov     [r9], r13d
0x18009e6af  test    edx, edx
0x18009e6b1  js      short loc_18009E6DF
0x18009e6b3  cmp     edx, [rcx+74h]
0x18009e6b6  jge     short loc_18009E6DF
0x18009e6b8  mov     eax, [rcx+84h]
0x18009e6be  mov     r8d, eax
0x18009e6c1  mov     r9d, [rcx+80h]; xRight
0x18009e6c8  lea     rcx, [rbp+57h+rc]; lprc
0x18009e6cc  imul    r8d, edx; yTop
0x18009e6d0  xor     edx, edx; xLeft
0x18009e6d2  add     eax, r8d
0x18009e6d5  mov     [rsp+100h+yBottom], eax; yBottom
0x18009e6d9  call    cs:__imp_SetRect
0x18009e6df  mov     eax, 7FFFh
0x18009e6e4  mov     [rsp+100h+yBottom], r13d; yBottom
0x18009e6e9  mov     r8d, eax; yTop
0x18009e6ec  lea     rcx, [rbp+57h+var_70]; lprc
0x18009e6f0  mov     edx, eax; xLeft
0x18009e6f2  xor     r9d, r9d; xRight
0x18009e6f5  call    cs:__imp_SetRect
0x18009e6fb  mov     esi, [rbp+57h+rc.right]
0x18009e6fe  sub     esi, [rbp+57h+rc.left]
0x18009e701  mov     r12d, [rbp+57h+rc.bottom]
0x18009e705  sub     r12d, [rbp+57h+rc.top]
0x18009e709  movsxd  r14, esi
0x18009e70c  add     r14, 0Fh
0x18009e710  mov     r15d, r12d
0x18009e713  shr     r14, 4
0x18009e717  add     r14d, r14d
0x18009e71a  mov     [rbp+57h+var_AC], r12d
0x18009e71e  mov     eax, r14d
0x18009e721  imul    r15, rax
0x18009e725  mov     [rbp+57h+var_88], rax
0x18009e729  mov     eax, 0FFFFFFFFh
0x18009e72e  mov     [rbp+57h+var_90], r14
0x18009e732  cmp     r15, rax
0x18009e735  ja      loc_18009E9BB
0x18009e73b  mov     ebx, 1
0x18009e740  mov     qword ptr [rsp+100h+yBottom], r13; lpBits
0x18009e745  mov     r9d, ebx; nBitCount
0x18009e748  mov     r8d, ebx; nPlanes
0x18009e74b  mov     edx, r12d; nHeight
0x18009e74e  mov     ecx, esi; nWidth
0x18009e750  call    cs:__imp_CreateBitmap
0x18009e756  mov     [rbp+57h+h], rax
0x18009e75a  test    rax, rax
0x18009e75d  jz      loc_18009E999
0x18009e763  mov     rcx, [rdi+0C8h]; hdc
0x18009e76a  call    cs:__imp_CreateCompatibleDC
0x18009e770  mov     [rbp+57h+hdc], rax
0x18009e774  test    rax, rax
0x18009e777  jz      loc_18009E98F
0x18009e77d  mov     r13d, r15d
0x18009e780  call    cs:__imp_GetProcessHeap
0x18009e786  mov     rcx, rax; hHeap
0x18009e789  mov     [rbp+57h+lpMem], 0
0x18009e791  mov     eax, r15d
0x18009e794  mul     rbx
0x18009e797  test    rdx, rdx
0x18009e79a  jnz     loc_18009E985
0x18009e7a0  mov     r8, rax; dwBytes
0x18009e7a3  call    cs:__imp_HeapAlloc
0x18009e7a9  mov     r15, rax
0x18009e7ac  test    rax, rax
0x18009e7af  jz      loc_18009E985
0x18009e7b5  mov     rdx, [rbp+57h+h]; h
0x18009e7b9  mov     rcx, [rbp+57h+hdc]; hdc
0x18009e7bd  call    cs:__imp_SelectObject
0x18009e7c3  mov     ecx, [rbp+57h+rc.top]
0x18009e7c6  mov     r9d, esi; cx
0x18009e7c9  mov     [rsp+100h+rop], 0CC0020h; rop
0x18009e7d1  xor     r8d, r8d; y
0x18009e7d4  mov     [rsp+100h+y1], ecx; y1
0x18009e7d8  xor     edx, edx; x
0x18009e7da  mov     ecx, [rbp+57h+rc.left]
0x18009e7dd  mov     [rsp+100h+x1], ecx; x1
0x18009e7e1  mov     rcx, [rdi+0C8h]
0x18009e7e8  mov     [rsp+100h+hdcSrc], rcx; hdcSrc
0x18009e7ed  mov     rcx, [rbp+57h+hdc]; hdc
0x18009e7f1  mov     [rsp+100h+yBottom], r12d; cy
0x18009e7f6  call    cs:__imp_BitBlt
0x18009e7fc  mov     rcx, [rbp+57h+h]; hbit
0x18009e800  mov     r8, r15; lpvBits
0x18009e803  mov     edx, r13d; cb
0x18009e806  call    cs:__imp_GetBitmapBits
0x18009e80c  mov     edi, [rbp+57h+var_70.bottom]
0x18009e80f  xor     r13d, r13d
0x18009e812  mov     r10d, [rbp+57h+var_70.right]
0x18009e816  mov     r8d, [rbp+57h+var_70.top]
0x18009e81a  mov     r11d, [rbp+57h+var_70.left]
0x18009e81e  test    r12d, r12d
0x18009e821  jle     loc_18009E9C2
0x18009e827  mov     edx, esi
0x18009e829  mov     [rbp+57h+lpMem], r15
0x18009e82d  sar     edx, 3
0x18009e830  mov     [rbp+57h+var_A8], edx
0x18009e833  xor     r9d, r9d
0x18009e836  xor     ecx, ecx
0x18009e838  test    edx, edx
0x18009e83a  jle     short loc_18009E84D
0x18009e83c  cmp     byte ptr [rcx+r15], 0FFh
0x18009e841  jnz     short loc_18009E84D
0x18009e843  add     r9d, 8
0x18009e847  add     ecx, ebx
0x18009e849  cmp     ecx, edx
0x18009e84b  jl      short loc_18009E83C
0x18009e84d  cmp     r9d, esi
0x18009e850  jge     short loc_18009E88D
0x18009e852  mov     r12, [rbp+57h+lpMem]
0x18009e856  imul    r14d, r13d
0x18009e85a  mov     eax, r9d
0x18009e85d  mov     ecx, 7
0x18009e862  and     eax, 7
0x18009e865  mov     edx, ebx
0x18009e867  sub     ecx, eax
0x18009e869  mov     eax, r9d
0x18009e86c  sar     eax, 3
0x18009e86f  add     eax, r14d
0x18009e872  shl     edx, cl
0x18009e874  test    [rax+r12], dl
0x18009e878  jz      short loc_18009E8D8
0x18009e87a  add     r9d, ebx
0x18009e87d  cmp     r9d, esi
0x18009e880  jl      short loc_18009E85A
0x18009e882  mov     r14, [rbp+57h+var_90]
0x18009e886  mov     r12d, [rbp+57h+var_AC]
0x18009e88a  mov     edx, [rbp+57h+var_A8]
0x18009e88d  add     r15, [rbp+57h+var_88]
0x18009e891  add     r13d, ebx
0x18009e894  cmp     r13d, r12d
0x18009e897  jl      short loc_18009E833
0x18009e899  mov     r12, [rbp+57h+lpMem]
0x18009e89d  mov     r15, [rbp+57h+var_78]
0x18009e8a1  xor     eax, eax
0x18009e8a3  mov     ecx, 7FFFh
0x18009e8a8  cmp     r11d, ecx
0x18009e8ab  cmovz   r11d, eax
0x18009e8af  cmp     r8d, ecx
0x18009e8b2  mov     [rbp+57h+var_70.left], r11d
0x18009e8b6  cmovz   r8d, eax
0x18009e8ba  mov     rax, [rbp+57h+var_80]
0x18009e8be  mov     [rbp+57h+var_70.top], r8d
0x18009e8c2  movups  xmm0, xmmword ptr [rbp+57h+var_70.left]
0x18009e8c6  movdqu  xmmword ptr [rax], xmm0
0x18009e8ca  test    r15, r15
0x18009e8cd  jz      loc_18009E96F
0x18009e8d3  jmp     loc_18009E962
0x18009e8d8  cmp     r11d, r9d
0x18009e8db  lea     eax, [r9+1]
0x18009e8df  cmovge  r11d, r9d
0x18009e8e3  cmp     r10d, eax
0x18009e8e6  mov     [rbp+57h+var_70.left], r11d
0x18009e8ea  cmovle  r10d, eax
0x18009e8ee  cmp     r8d, r13d
0x18009e8f1  lea     eax, [r13+1]
0x18009e8f5  mov     [rbp+57h+var_70.right], r10d
0x18009e8f9  cmovge  r8d, r13d
0x18009e8fd  cmp     edi, eax
0x18009e8ff  mov     [rbp+57h+var_70.top], r8d
0x18009e903  cmovle  edi, eax
0x18009e906  mov     [rbp+57h+var_70.bottom], edi
0x18009e909  cmp     r9d, r11d
0x18009e90c  jl      loc_18009E87A
0x18009e912  cmp     r9d, r10d
0x18009e915  jge     loc_18009E87A
0x18009e91b  lea     r9d, [r10-1]
0x18009e91f  jmp     loc_18009E87A
0x18009e924  mov     r9d, r11d
0x18009e927  cmp     r11d, r10d
0x18009e92a  jge     short loc_18009E95A
0x18009e92c  mov     esi, r14d
0x18009e92f  imul    esi, r8d
0x18009e933  mov     eax, r9d
0x18009e936  mov     ecx, 7
0x18009e93b  and     eax, 7
0x18009e93e  mov     edx, ebx
0x18009e940  sub     ecx, eax
0x18009e942  mov     eax, r9d
0x18009e945  sar     eax, 3
0x18009e948  add     eax, esi
0x18009e94a  shl     edx, cl
0x18009e94c  test    [rax+r12], dl
0x18009e950  jnz     short loc_18009E95A
0x18009e952  add     r9d, ebx
0x18009e955  cmp     r9d, r10d
0x18009e958  jl      short loc_18009E933
0x18009e95a  cmp     r9d, r10d
0x18009e95d  jnz     short loc_18009E967
0x18009e95f  add     r8d, ebx
0x18009e962  cmp     r8d, edi
0x18009e965  jl      short loc_18009E924
0x18009e967  cmp     r8d, edi
0x18009e96a  jnz     short loc_18009E96F
0x18009e96c  mov     [r15], ebx
0x18009e96f  call    cs:__imp_GetProcessHeap
0x18009e975  mov     r8, r12; lpMem
0x18009e978  xor     edx, edx; dwFlags
0x18009e97a  mov     rcx, rax; hHeap
0x18009e97d  call    cs:__imp_HeapFree
0x18009e983  xor     ebx, ebx
0x18009e985  mov     rcx, [rbp+57h+hdc]; hdc
0x18009e989  call    cs:__imp_DeleteDC
0x18009e98f  mov     rcx, [rbp+57h+h]; ho
0x18009e993  call    cs:__imp_DeleteObject
0x18009e999  mov     eax, ebx
0x18009e99b  mov     rcx, [rbp+57h+var_48]
0x18009e99f  xor     rcx, rsp; StackCookie
0x18009e9a2  call    __security_check_cookie
0x18009e9a7  add     rsp, 0C8h
0x18009e9ae  pop     r15
0x18009e9b0  pop     r14
0x18009e9b2  pop     r13
0x18009e9b4  pop     r12
0x18009e9b6  pop     rdi
0x18009e9b7  pop     rsi
0x18009e9b8  pop     rbx
0x18009e9b9  pop     rbp
0x18009e9ba  retn
0x18009e9bb  mov     ebx, 80070216h
0x18009e9c0  jmp     short loc_18009E999
0x18009e9c2  mov     r12, r15
0x18009e9c5  jmp     loc_18009E89D
```
