# CILRDecorator::_Render(void)

- ea: `0x18000d9c0`
- end: `0x18000ddc3`
- name: `?_Render@CILRDecorator@@MEAAXXZ`
- size: `1027`
- prototype: `void __fastcall(CILRDecorator *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000d9c0`
- `0x18000ddcc`
- `0x180114520`
- `0x180114ebc`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dbad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dbad`
- `GDI32!DeleteObject` at `0x18000dc3d`
- `GDI32!DeleteObject` at `0x18000dc3d`
- `GDI32!GetObjectW` at `0x18000dd4f`
- `GDI32!GetObjectW` at `0x18000dd4f`
- `GDI32!SelectObject` at `0x18000dc20`
- `GDI32!SelectObject` at `0x18000dc20`
- `GDI32!CreateBitmap` at `0x18000db0f`
- `GDI32!CreateBitmap` at `0x18000db0f`
- `GDI32!BitBlt` at `0x18000dc02`
- `GDI32!BitBlt` at `0x18000dc02`
- `SHLWAPI!__imp_CalculateAspectRatio` at `0x18000dcd5`
- `SHLWAPI!__imp_CalculateAspectRatio` at `0x18000dcd5`

## pseudocode

```c
void __fastcall CILRDecorator::_Render(CILRDecorator *this)
{
  __int64 v1; // rax
  __int64 v3; // rcx
  int v4; // eax
  signed int *v5; // rdi
  int *v6; // rsi
  int v7; // ebx
  signed int v8; // r15d
  signed int v9; // r11d
  int v10; // r10d
  int v11; // eax
  HBITMAP Bitmap; // rbx
  HANDLE v13; // rax
  __int64 v14; // r9
  _BYTE *lpBits; // rdi
  int v16; // eax
  __int64 v17; // rax
  __int64 (__fastcall *v18)(CILRDecorator *, char *); // rax
  __int64 v19; // rcx
  void *v20; // rcx
  int v21; // r13d
  signed int v22; // r14d
  unsigned int v23; // r13d
  unsigned int v24; // esi
  unsigned __int64 v25; // rbx
  HANDLE ProcessHeap; // rcx
  int nWidth[4]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v28; // [rsp+60h] [rbp+7h]
  __int64 v29; // [rsp+70h] [rbp+17h] BYREF
  size_t Size; // [rsp+78h] [rbp+1Fh] BYREF

  v1 = *(_QWORD *)this;
  v29 = 0;
  (*(void (__fastcall **)(CILRDecorator *, __int64 *, char *))(v1 + 48))(this, &v29, (char *)&v29 + 4);
  v3 = *((_QWORD *)this + 15);
  *(_QWORD *)nWidth = 0;
  if ( v3 )
  {
    *(_QWORD *)&nWidth[2] = v29;
    if ( (*(int (__fastcall **)(__int64, char *, int *))(*(_QWORD *)v3 + 24LL))(v3, (char *)this + 80, nWidth) < 0
      || (*(int (__fastcall **)(CILRDecorator *, int *))(*(_QWORD *)this + 32LL))(this, nWidth) < 0 )
    {
      goto LABEL_15;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 32LL))(
           *((_QWORD *)this + 15),
           *(_QWORD *)(*((_QWORD *)this + 9) + 192LL));
    v5 = (signed int *)((char *)this + 84);
    v6 = (int *)((char *)this + 92);
  }
  else
  {
    v16 = *((_DWORD *)this + 22) - *((_DWORD *)this + 20);
    *(_QWORD *)&nWidth[2] = v29;
    if ( (int)v29 < v16 )
      LODWORD(Size) = v29;
    else
      LODWORD(Size) = v16;
    v6 = (int *)((char *)this + 92);
    v5 = (signed int *)((char *)this + 84);
    if ( SHIDWORD(v29) < *((_DWORD *)this + 23) - *((_DWORD *)this + 21) )
      HIDWORD(Size) = HIDWORD(v29);
    else
      HIDWORD(Size) = *((_DWORD *)this + 23) - *((_DWORD *)this + 21);
    CalculateAspectRatio((LPWSTR)&Size);
    v17 = *(_QWORD *)this;
    *((_DWORD *)this + 22) = nWidth[2] + *((_DWORD *)this + 20);
    v18 = *(__int64 (__fastcall **)(CILRDecorator *, char *))(v17 + 32);
    *v6 = nWidth[3] + *v5;
    v4 = v18(this, (char *)this + 80);
  }
  if ( v4 >= 0 )
  {
    v19 = *((_QWORD *)this + 9);
    if ( *(_QWORD *)(v19 + 200) )
    {
      v20 = *(void **)(v19 + 160);
      v21 = *v6;
      v22 = *v5;
      *(_OWORD *)nWidth = 0;
      v28 = 0;
      if ( GetObjectW(v20, 32, nWidth) )
      {
        v23 = v21 - v22;
        if ( !v23 )
          v23 = nWidth[2];
        v24 = 2 * ((unsigned __int64)(nWidth[1] + 15LL) >> 4);
        v25 = v23 * (unsigned __int64)v24;
        if ( v25 <= 0xFFFFFFFF )
        {
          ProcessHeap = GetProcessHeap();
          Size = (unsigned int)v25;
          if ( is_mul_ok(1u, (unsigned int)v25) )
          {
            lpBits = HeapAlloc(ProcessHeap, 8u, (unsigned int)v25);
            if ( lpBits )
            {
              v14 = *((_QWORD *)&v28 + 1);
              if ( !*((_QWORD *)&v28 + 1) )
                goto LABEL_23;
              v7 = 0;
              v8 = v22 + v23;
              v9 = v22;
              if ( v22 >= (int)(v22 + v23) )
                goto LABEL_23;
              v10 = nWidth[1];
              do
              {
                v11 = 0;
                if ( v10 > 0 )
                {
                  do
                  {
                    if ( *(_BYTE *)(4 * v11 + v14 + nWidth[3] * (nWidth[2] - v9 - 1) + 3) )
                    {
                      v7 = 1;
                    }
                    else
                    {
                      lpBits[(v11 >> 3) + v24 * (v9 - v22)] |= 1 << (7 - (v11 & 7));
                      v14 = *((_QWORD *)&v28 + 1);
                      v10 = nWidth[1];
                    }
                    ++v11;
                  }
                  while ( v11 < v10 );
                  v8 = v22 + v23;
                }
                ++v9;
              }
              while ( v9 < v8 );
              if ( !v7 )
              {
LABEL_23:
                memset_0(lpBits, 0, Size);
                v10 = nWidth[1];
              }
              Bitmap = CreateBitmap(v10, v23, 1u, 1u, lpBits);
              v13 = GetProcessHeap();
              HeapFree(v13, 0, lpBits);
              if ( Bitmap )
              {
                EnterCriticalSection(&g_csDll);
                CImageList::SelectSrcBitmap(Bitmap);
                BitBlt(
                  *(HDC *)(*((_QWORD *)this + 9) + 200LL),
                  0,
                  *((_DWORD *)this + 21),
                  *((_DWORD *)this + 22) - *((_DWORD *)this + 20),
                  *((_DWORD *)this + 23) - *((_DWORD *)this + 21),
                  g_hdcSrc,
                  0,
                  0,
                  0xCC0020u);
                if ( g_hbmSrc )
                {
                  SelectObject(g_hdcSrc, g_hbmDcDeselect);
                  g_hbmSrc = 0;
                }
                LeaveCriticalSection(&g_csDll);
                DeleteObject(Bitmap);
              }
            }
          }
        }
      }
    }
  }
LABEL_15:
  *((_DWORD *)this + 16) = 1;
}

```

## disassembly

```asm
0x18000d9c0  mov     [rsp-8+arg_18], rbx
0x18000d9c5  push    rbp
0x18000d9c6  push    rsi
0x18000d9c7  push    rdi
0x18000d9c8  push    r12
0x18000d9ca  push    r15
0x18000d9cc  lea     rbp, [rsp-37h]
0x18000d9d1  sub     rsp, 90h
0x18000d9d8  mov     rax, cs:__security_cookie
0x18000d9df  xor     rax, rsp
0x18000d9e2  mov     [rbp+57h+var_30], rax
0x18000d9e6  mov     rax, [rcx]
0x18000d9e9  lea     r8, [rbp+57h+var_40+4]
0x18000d9ed  xor     r15d, r15d
0x18000d9f0  lea     rdx, [rbp+57h+var_40]
0x18000d9f4  mov     r12, rcx
0x18000d9f7  mov     dword ptr [rbp+57h+var_40], r15d
0x18000d9fb  mov     dword ptr [rbp+57h+var_40+4], r15d
0x18000d9ff  mov     rax, [rax+30h]
0x18000da03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da08  mov     rcx, [r12+78h]
0x18000da0d  mov     qword ptr [rbp+57h+nWidth], r15
0x18000da11  test    rcx, rcx
0x18000da14  jz      loc_18000DC8B
0x18000da1a  mov     eax, dword ptr [rbp+57h+var_40]
0x18000da1d  lea     r8, [rbp+57h+nWidth]
0x18000da21  mov     [rbp+57h+nWidth+8], eax
0x18000da24  lea     rdx, [r12+50h]
0x18000da29  mov     eax, dword ptr [rbp+57h+var_40+4]
0x18000da2c  mov     [rbp+57h+nWidth+0Ch], eax
0x18000da2f  mov     rax, [rcx]
0x18000da32  mov     rax, [rax+18h]
0x18000da36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da3b  test    eax, eax
0x18000da3d  js      loc_18000DB41
0x18000da43  mov     rax, [r12]
0x18000da47  lea     rdx, [rbp+57h+nWidth]
0x18000da4b  mov     rcx, r12
0x18000da4e  mov     rax, [rax+20h]
0x18000da52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da57  test    eax, eax
0x18000da59  js      loc_18000DB41
0x18000da5f  mov     rcx, [r12+78h]
0x18000da64  mov     rdx, [r12+48h]
0x18000da69  mov     rax, [rcx]
0x18000da6c  mov     rdx, [rdx+0C0h]
0x18000da73  mov     rax, [rax+20h]
0x18000da77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7c  lea     rdi, [r12+54h]
0x18000da81  lea     rsi, [r12+5Ch]
0x18000da86  jmp     loc_18000DD04
0x18000da8b  xor     ebx, ebx
0x18000da8d  lea     r15d, [r14+r13]
0x18000da91  mov     r11d, r14d
0x18000da94  cmp     r14d, r15d
0x18000da97  jge     loc_18000DC48
0x18000da9d  mov     r10d, [rbp+57h+nWidth+4]
0x18000daa1  xor     eax, eax
0x18000daa3  test    r10d, r10d
0x18000daa6  jle     short loc_18000DAE6
0x18000daa8  mov     r15d, 1
0x18000daae  xchg    ax, ax
0x18000dab0  mov     ecx, [rbp+57h+nWidth+8]
0x18000dab3  sub     ecx, r11d
0x18000dab6  dec     ecx
0x18000dab8  imul    ecx, [rbp+57h+nWidth+0Ch]
0x18000dabc  movsxd  r8, ecx
0x18000dabf  lea     ecx, ds:0[rax*4]
0x18000dac6  movsxd  rdx, ecx
0x18000dac9  lea     rcx, [r9+r8]
0x18000dacd  cmp     byte ptr [rdx+rcx+3], 0
0x18000dad2  jz      loc_18000DB6D
0x18000dad8  mov     ebx, r15d
0x18000dadb  inc     eax
0x18000dadd  cmp     eax, r10d
0x18000dae0  jl      short loc_18000DAB0
0x18000dae2  lea     r15d, [r14+r13]
0x18000dae6  inc     r11d
0x18000dae9  cmp     r11d, r15d
0x18000daec  jl      short loc_18000DAA1
0x18000daee  xor     r15d, r15d
0x18000daf1  test    ebx, ebx
0x18000daf3  jz      loc_18000DC74
0x18000daf9  mov     eax, 1
0x18000dafe  mov     [rsp+0B0h+lpBits], rdi; lpBits
0x18000db03  mov     r9d, eax; nBitCount
0x18000db06  mov     r8d, eax; nPlanes
0x18000db09  mov     edx, r13d; nHeight
0x18000db0c  mov     ecx, r10d; nWidth
0x18000db0f  call    cs:__imp_CreateBitmap
0x18000db15  mov     rbx, rax
0x18000db18  call    cs:__imp_GetProcessHeap
0x18000db1e  mov     r8, rdi; lpMem
0x18000db21  xor     edx, edx; dwFlags
0x18000db23  mov     rcx, rax; hHeap
0x18000db26  call    cs:__imp_HeapFree
0x18000db2c  test    rbx, rbx
0x18000db2f  jnz     short loc_18000DBA6
0x18000db31  mov     r13, [rsp+0B0h+arg_8]
0x18000db39  mov     r14, [rsp+0B0h+arg_10]
0x18000db41  mov     dword ptr [r12+40h], 1
0x18000db4a  mov     rcx, [rbp+57h+var_30]
0x18000db4e  xor     rcx, rsp; StackCookie
0x18000db51  call    __security_check_cookie
0x18000db56  mov     rbx, [rsp+0B0h+arg_18]
0x18000db5e  add     rsp, 90h
0x18000db65  pop     r15
0x18000db67  pop     r12
0x18000db69  pop     rdi
0x18000db6a  pop     rsi
0x18000db6b  pop     rbp
0x18000db6c  retn
0x18000db6d  mov     edx, r11d
0x18000db70  mov     ecx, eax
0x18000db72  sub     edx, r14d
0x18000db75  sar     ecx, 3
0x18000db78  imul    edx, esi
0x18000db7b  add     edx, ecx
0x18000db7d  mov     ecx, 7
0x18000db82  mov     r9d, edx
0x18000db85  movzx   r8d, byte ptr [rdx+rdi]
0x18000db8a  mov     edx, eax
0x18000db8c  and     edx, 7
0x18000db8f  sub     ecx, edx
0x18000db91  bts     r8d, ecx
0x18000db95  mov     [r9+rdi], r8b
0x18000db99  mov     r9, [rbp+57h+var_48]
0x18000db9d  mov     r10d, [rbp+57h+nWidth+4]
0x18000dba1  jmp     loc_18000DADB
0x18000dba6  lea     rcx, g_csDll; lpCriticalSection
0x18000dbad  call    cs:__imp_EnterCriticalSection
0x18000dbb3  mov     rcx, rbx; h
0x18000dbb6  call    ?SelectSrcBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x18000dbbb  mov     edx, [r12+5Ch]
0x18000dbc0  mov     rcx, [r12+48h]
0x18000dbc5  mov     r8d, [r12+54h]; y
0x18000dbca  sub     edx, r8d
0x18000dbcd  mov     rax, cs:?g_hdcSrc@@3PEAUHDC__@@EA; HDC__ * g_hdcSrc
0x18000dbd4  mov     r9d, [r12+58h]
0x18000dbd9  mov     rcx, [rcx+0C8h]; hdc
0x18000dbe0  sub     r9d, [r12+50h]; cx
0x18000dbe5  mov     [rsp+0B0h+rop], 0CC0020h; rop
0x18000dbed  mov     [rsp+0B0h+y1], r15d; y1
0x18000dbf2  mov     [rsp+0B0h+x1], r15d; x1
0x18000dbf7  mov     [rsp+0B0h+hdcSrc], rax; hdcSrc
0x18000dbfc  mov     dword ptr [rsp+0B0h+lpBits], edx; cy
0x18000dc00  xor     edx, edx; x
0x18000dc02  call    cs:__imp_BitBlt
0x18000dc08  cmp     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmSrc
0x18000dc10  jz      short loc_18000DC2D
0x18000dc12  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x18000dc19  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000dc20  call    cs:__imp_SelectObject
0x18000dc26  mov     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, r15; HBITMAP__ * g_hbmSrc
0x18000dc2d  lea     rcx, g_csDll; lpCriticalSection
0x18000dc34  call    cs:__imp_LeaveCriticalSection
0x18000dc3a  mov     rcx, rbx; ho
0x18000dc3d  call    cs:__imp_DeleteObject
0x18000dc43  jmp     loc_18000DB31
0x18000dc48  xor     r15d, r15d
0x18000dc4b  jmp     short loc_18000DC74
0x18000dc4d  mov     r8, rax; dwBytes
0x18000dc50  mov     edx, 8; dwFlags
0x18000dc55  call    cs:__imp_HeapAlloc
0x18000dc5b  mov     rdi, rax
0x18000dc5e  test    rax, rax
0x18000dc61  jz      loc_18000DB31
0x18000dc67  mov     r9, [rbp+57h+var_48]
0x18000dc6b  test    r9, r9
0x18000dc6e  jnz     loc_18000DA8B
0x18000dc74  mov     r8, [rbp+57h+Size]; Size
0x18000dc78  xor     edx, edx; Val
0x18000dc7a  mov     rcx, rdi; void *
0x18000dc7d  call    memset_0
0x18000dc82  mov     r10d, [rbp+57h+nWidth+4]
0x18000dc86  jmp     loc_18000DAF9
0x18000dc8b  mov     ecx, dword ptr [rbp+57h+var_40]
0x18000dc8e  mov     eax, [r12+58h]
0x18000dc93  sub     eax, [r12+50h]
0x18000dc98  mov     edx, dword ptr [rbp+57h+var_40+4]
0x18000dc9b  mov     [rbp+57h+nWidth+8], ecx
0x18000dc9e  mov     [rbp+57h+nWidth+0Ch], edx
0x18000dca1  cmp     ecx, eax
0x18000dca3  jl      loc_18000DDBB
0x18000dca9  mov     dword ptr [rbp+57h+Size], eax
0x18000dcac  mov     eax, [r12+5Ch]
0x18000dcb1  lea     rsi, [r12+5Ch]
0x18000dcb6  sub     eax, [r12+54h]
0x18000dcbb  lea     rdi, [r12+54h]
0x18000dcc0  cmp     edx, eax
0x18000dcc2  jl      loc_18000DDB3
0x18000dcc8  mov     dword ptr [rbp+57h+Size+4], eax
0x18000dccb  lea     r8, [rbp+57h+nWidth]
0x18000dccf  xor     edx, edx
0x18000dcd1  lea     rcx, [rbp+57h+Size]; pszPath
0x18000dcd5  call    cs:__imp_CalculateAspectRatio
0x18000dcdb  mov     ecx, [r12+50h]
0x18000dce0  lea     rdx, [r12+50h]
0x18000dce5  add     ecx, [rbp+57h+nWidth+8]
0x18000dce8  mov     rax, [r12]
0x18000dcec  mov     [r12+58h], ecx
0x18000dcf1  mov     ecx, [rdi]
0x18000dcf3  add     ecx, [rbp+57h+nWidth+0Ch]
0x18000dcf6  mov     rax, [rax+20h]
0x18000dcfa  mov     [rsi], ecx
0x18000dcfc  mov     rcx, r12
0x18000dcff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd04  test    eax, eax
0x18000dd06  js      loc_18000DB41
0x18000dd0c  mov     rcx, [r12+48h]
0x18000dd11  cmp     [rcx+0C8h], r15
0x18000dd18  jz      loc_18000DB41
0x18000dd1e  mov     rcx, [rcx+0A0h]; h
0x18000dd25  lea     r8, [rbp+57h+nWidth]; pv
0x18000dd29  xorps   xmm0, xmm0
0x18000dd2c  mov     [rsp+0B0h+arg_8], r13
0x18000dd34  mov     r13d, [rsi]
0x18000dd37  mov     edx, 20h ; ' '; c
0x18000dd3c  mov     [rsp+0B0h+arg_10], r14
0x18000dd44  mov     r14d, [rdi]
0x18000dd47  movups  xmmword ptr [rbp+57h+nWidth], xmm0
0x18000dd4b  movups  xmmword ptr [rbp+7], xmm0
0x18000dd4f  call    cs:__imp_GetObjectW
0x18000dd55  test    eax, eax
0x18000dd57  jz      loc_18000DB31
0x18000dd5d  movsxd  rsi, [rbp+57h+nWidth+4]
0x18000dd61  sub     r13d, r14d
0x18000dd64  cmovz   r13d, [rbp+57h+nWidth+8]
0x18000dd69  add     rsi, 0Fh
0x18000dd6d  shr     rsi, 4
0x18000dd71  add     esi, esi
0x18000dd73  mov     eax, r13d
0x18000dd76  mov     ebx, esi
0x18000dd78  imul    rbx, rax
0x18000dd7c  mov     eax, 0FFFFFFFFh
0x18000dd81  cmp     rbx, rax
0x18000dd84  ja      loc_18000DB31
0x18000dd8a  call    cs:__imp_GetProcessHeap
0x18000dd90  mov     [rbp+57h+Size], r15
0x18000dd94  mov     edx, 1
0x18000dd99  mov     rcx, rax; hHeap
0x18000dd9c  mov     eax, ebx
0x18000dd9e  mov     [rbp+57h+Size], rax
0x18000dda2  mul     rdx
0x18000dda5  test    rdx, rdx
0x18000dda8  jnz     loc_18000DB31
0x18000ddae  jmp     loc_18000DC4D
0x18000ddb3  mov     dword ptr [rbp+57h+Size+4], edx
0x18000ddb6  jmp     loc_18000DCCB
0x18000ddbb  mov     dword ptr [rbp+57h+Size], ecx
0x18000ddbe  jmp     loc_18000DCAC
```
