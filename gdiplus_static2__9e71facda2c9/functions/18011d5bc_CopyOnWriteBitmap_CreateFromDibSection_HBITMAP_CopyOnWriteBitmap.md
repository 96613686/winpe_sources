# CopyOnWriteBitmap::CreateFromDibSection(HBITMAP__ *,CopyOnWriteBitmap * *)

- ea: `0x18011d5bc`
- end: `0x18011d818`
- name: `?CreateFromDibSection@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAPEAV1@@Z`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18011d820`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x1800653e4`
- `0x1800f7db0`
- `0x180105d40`
- `0x18010673c`
- `0x18011d5bc`
- `0x180171428`
- `0x180172010`

## import_xrefs

- `GDI32!GetDIBColorTable` at `0x18011d6e7`
- `GDI32!GetDIBColorTable` at `0x18011d6e7`
- `GDI32!DeleteDC` at `0x18011d70a`
- `GDI32!DeleteDC` at `0x18011d70a`
- `GDI32!SelectObject` at `0x18011d6c9`
- `GDI32!SelectObject` at `0x18011d6fb`
- `GDI32!SelectObject` at `0x18011d6c9`
- `GDI32!SelectObject` at `0x18011d6fb`
- `GDI32!CreateCompatibleDC` at `0x18011d6ab`
- `GDI32!CreateCompatibleDC` at `0x18011d6ab`
- `GDI32!GetObjectA` at `0x18011d627`
- `GDI32!GetObjectA` at `0x18011d627`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromDibSection(void *a1, CopyOnWriteBitmap **a2)
{
  unsigned int v4; // r14d
  unsigned int v5; // esi
  HDC CompatibleDC; // rax
  HDC v7; // r12
  HGDIOBJ v8; // rdi
  UINT DIBColorTable; // ebx
  void *v11; // rax
  void *v12; // rbx
  CopyOnWriteBitmap *v13; // rax
  CopyOnWriteBitmap *v14; // rax
  _BYTE pv[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh]
  int v17; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v18; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v19; // [rsp+32h] [rbp-CEh]
  void *Src; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  LONG v22; // [rsp+48h] [rbp-B8h]
  WORD v23; // [rsp+4Ch] [rbp-B4h]
  WORD v24; // [rsp+4Eh] [rbp-B2h]
  DWORD v25; // [rsp+50h] [rbp-B0h]
  _DWORD Size[15]; // [rsp+54h] [rbp-ACh]
  struct tagBITMAPINFO v27; // [rsp+90h] [rbp-70h] BYREF
  int v28; // [rsp+BCh] [rbp-44h]
  int v29; // [rsp+C0h] [rbp-40h]

  v4 = 7;
  memset_0(pv, 0, 0x68u);
  memset_0(&v27, 0, 0x428u);
  if ( GetObjectA(a1, 104, pv) != 104 )
    return v4;
  v5 = Size[0];
  if ( !Size[0] )
    v5 = v17 * v18 * (((v16 * v19 + 31) >> 3) & 0xFFFFFFFC);
  v27.bmiHeader.biHeight = v22;
  *(_QWORD *)&v27.bmiHeader.biSize = v21;
  v27.bmiHeader.biPlanes = v23;
  v27.bmiHeader.biBitCount = v24;
  v27.bmiHeader.biCompression = v25;
  v27.bmiHeader.biSizeImage = Size[0];
  *(_OWORD *)&v27.bmiHeader.biXPelsPerMeter = *(_OWORD *)&Size[1];
  if ( v24 > 8u )
  {
    if ( v24 == 16 && v25 == 3 )
    {
      v27.bmiColors[0] = (RGBQUAD)Size[5];
      v28 = Size[6];
      v29 = Size[7];
    }
  }
  else
  {
    CompatibleDC = CreateCompatibleDC(0);
    v7 = CompatibleDC;
    if ( CompatibleDC )
    {
      v8 = SelectObject(CompatibleDC, a1);
      DIBColorTable = GetDIBColorTable(v7, 0, 0x100u, v27.bmiColors);
      SelectObject(v7, v8);
      DeleteDC(v7);
      if ( !DIBColorTable )
        return v4;
    }
  }
  v11 = (void *)GpMallocEx(v5, 0);
  v12 = v11;
  if ( v11 )
  {
    memcpy_0(v11, Src, v5);
    v13 = (CopyOnWriteBitmap *)GpMallocEx(264, 0);
    if ( v13 )
    {
      v14 = CopyOnWriteBitmap::CopyOnWriteBitmap(v13, &v27, v12, 1);
      *a2 = v14;
      if ( v14 )
      {
        if ( (*(unsigned int (__fastcall **)(CopyOnWriteBitmap *))(*(_QWORD *)v14 + 16LL))(v14) )
        {
          return 0;
        }
        else
        {
          CopyOnWriteBitmap::Dispose(*a2);
          *a2 = 0;
          return 2;
        }
      }
    }
    else
    {
      *a2 = 0;
    }
    GpFree(v12);
    return 3;
  }
  return 3;
}

```

## disassembly

```asm
0x18011d5bc  mov     [rsp-8+arg_10], rbx
0x18011d5c1  mov     [rsp-8+arg_18], rsi
0x18011d5c6  push    rbp
0x18011d5c7  push    rdi
0x18011d5c8  push    r12
0x18011d5ca  push    r14
0x18011d5cc  push    r15
0x18011d5ce  lea     rbp, [rsp-3D0h]
0x18011d5d6  sub     rsp, 4D0h
0x18011d5dd  mov     rax, cs:__security_cookie
0x18011d5e4  xor     rax, rsp
0x18011d5e7  mov     [rbp+3F0h+var_30], rax
0x18011d5ee  mov     edi, 68h ; 'h'
0x18011d5f3  mov     r15, rdx
0x18011d5f6  mov     rbx, rcx
0x18011d5f9  mov     r8d, edi; Size
0x18011d5fc  xor     edx, edx; Val
0x18011d5fe  lea     rcx, [rsp+4F0h+pv]; void *
0x18011d603  lea     r14d, [rdi-61h]
0x18011d607  call    memset_0
0x18011d60c  xor     edx, edx; Val
0x18011d60e  lea     rcx, [rbp+3F0h+var_460]; void *
0x18011d612  mov     r8d, 428h; Size
0x18011d618  call    memset_0
0x18011d61d  lea     r8, [rsp+4F0h+pv]; pv
0x18011d622  mov     edx, edi; c
0x18011d624  mov     rcx, rbx; h
0x18011d627  call    cs:__imp_GetObjectA
0x18011d62e  nop     dword ptr [rax+rax+00h]
0x18011d633  cmp     eax, edi
0x18011d635  jnz     loc_18011D71A
0x18011d63b  mov     ecx, dword ptr [rsp+4F0h+Size]
0x18011d63f  mov     esi, ecx
0x18011d641  test    ecx, ecx
0x18011d643  jnz     short loc_18011D665
0x18011d645  movzx   esi, [rsp+4F0h+var_4BE]
0x18011d64a  imul    esi, [rsp+4F0h+var_4CC]
0x18011d64f  movzx   eax, [rsp+4F0h+var_4C0]
0x18011d654  add     esi, 1Fh
0x18011d657  sar     esi, 3
0x18011d65a  and     esi, 0FFFFFFFCh
0x18011d65d  imul    esi, eax
0x18011d660  imul    esi, [rsp+4F0h+var_4C8]
0x18011d665  mov     eax, [rsp+4F0h+var_4A8]
0x18011d669  movsd   xmm0, [rsp+4F0h+var_4B0]
0x18011d66f  mov     r8d, [rsp+4F0h+var_4A0]
0x18011d674  mov     [rbp+3F0h+var_460.bmiHeader.biHeight], eax
0x18011d677  movzx   eax, [rsp+4F0h+var_4A4]
0x18011d67c  movsd   qword ptr [rbp+3F0h+var_460.bmiHeader.biSize], xmm0
0x18011d681  movups  xmm0, xmmword ptr [rsp+4F0h+Size+4]
0x18011d686  mov     [rbp+3F0h+var_460.bmiHeader.biPlanes], ax
0x18011d68a  movzx   eax, [rsp+4F0h+var_4A2]
0x18011d68f  mov     [rbp+3F0h+var_460.bmiHeader.biBitCount], ax
0x18011d693  mov     [rbp+3F0h+var_460.bmiHeader.biCompression], r8d
0x18011d697  mov     [rbp+3F0h+var_460.bmiHeader.biSizeImage], ecx
0x18011d69a  movdqu  xmmword ptr [rbp+3F0h+var_460.bmiHeader.biXPelsPerMeter], xmm0
0x18011d69f  cmp     ax, 8
0x18011d6a3  ja      loc_18011D749
0x18011d6a9  xor     ecx, ecx; hdc
0x18011d6ab  call    cs:__imp_CreateCompatibleDC
0x18011d6b2  nop     dword ptr [rax+rax+00h]
0x18011d6b7  mov     r12, rax
0x18011d6ba  test    rax, rax
0x18011d6bd  jz      loc_18011D76A
0x18011d6c3  mov     rdx, rbx; h
0x18011d6c6  mov     rcx, rax; hdc
0x18011d6c9  call    cs:__imp_SelectObject
0x18011d6d0  nop     dword ptr [rax+rax+00h]
0x18011d6d5  lea     r9, [rbp+3F0h+var_460.bmiColors]; prgbq
0x18011d6d9  xor     edx, edx; iStart
0x18011d6db  mov     r8d, 100h; cEntries
0x18011d6e1  mov     rcx, r12; hdc
0x18011d6e4  mov     rdi, rax
0x18011d6e7  call    cs:__imp_GetDIBColorTable
0x18011d6ee  nop     dword ptr [rax+rax+00h]
0x18011d6f3  mov     rdx, rdi; h
0x18011d6f6  mov     rcx, r12; hdc
0x18011d6f9  mov     ebx, eax
0x18011d6fb  call    cs:__imp_SelectObject
0x18011d702  nop     dword ptr [rax+rax+00h]
0x18011d707  mov     rcx, r12; hdc
0x18011d70a  call    cs:__imp_DeleteDC
0x18011d711  nop     dword ptr [rax+rax+00h]
0x18011d716  test    ebx, ebx
0x18011d718  jnz     short loc_18011D76A
0x18011d71a  mov     eax, r14d
0x18011d71d  mov     rcx, [rbp+3F0h+var_30]
0x18011d724  xor     rcx, rsp; StackCookie
0x18011d727  call    __security_check_cookie
0x18011d72c  lea     r11, [rsp+4F0h+var_20]
0x18011d734  mov     rbx, [r11+40h]
0x18011d738  mov     rsi, [r11+48h]
0x18011d73c  mov     rsp, r11
0x18011d73f  pop     r15
0x18011d741  pop     r14
0x18011d743  pop     r12
0x18011d745  pop     rdi
0x18011d746  pop     rbp
0x18011d747  retn
0x18011d749  cmp     ax, 10h
0x18011d74d  jnz     short loc_18011D76A
0x18011d74f  cmp     r8d, 3
0x18011d753  jnz     short loc_18011D76A
0x18011d755  mov     eax, [rsp+4F0h+var_488]
0x18011d759  mov     dword ptr [rbp+3F0h+var_460.bmiColors.rgbBlue], eax
0x18011d75c  mov     eax, [rsp+4F0h+var_484]
0x18011d760  mov     [rbp+3F0h+var_434], eax
0x18011d763  mov     eax, [rsp+4F0h+var_480]
0x18011d767  mov     [rbp+3F0h+var_430], eax
0x18011d76a  xor     edx, edx
0x18011d76c  mov     ecx, esi
0x18011d76e  mov     edi, esi
0x18011d770  call    GpMallocEx
0x18011d775  mov     rbx, rax
0x18011d778  test    rax, rax
0x18011d77b  jz      loc_18011D80E
0x18011d781  mov     rdx, [rsp+4F0h+Src]; Src
0x18011d786  mov     r8d, edi; Size
0x18011d789  mov     rcx, rax; void *
0x18011d78c  call    memcpy_0
0x18011d791  xor     edx, edx
0x18011d793  mov     ecx, 108h
0x18011d798  call    GpMallocEx
0x18011d79d  test    rax, rax
0x18011d7a0  jz      short loc_18011D7F4
0x18011d7a2  mov     r9d, 1; int
0x18011d7a8  lea     rdx, [rbp+3F0h+var_460]; struct tagBITMAPINFO *
0x18011d7ac  mov     r8, rbx; void *
0x18011d7af  mov     rcx, rax; this
0x18011d7b2  call    ??0CopyOnWriteBitmap@@AEAA@PEAUtagBITMAPINFO@@PEAXH@Z; CopyOnWriteBitmap::CopyOnWriteBitmap(tagBITMAPINFO *,void *,int)
0x18011d7b7  mov     [r15], rax
0x18011d7ba  mov     rcx, rax
0x18011d7bd  test    rax, rax
0x18011d7c0  jz      short loc_18011D7FB
0x18011d7c2  mov     rax, [rax]
0x18011d7c5  mov     rax, [rax+10h]
0x18011d7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d7ce  test    eax, eax
0x18011d7d0  jz      short loc_18011D7DA
0x18011d7d2  xor     r14d, r14d
0x18011d7d5  jmp     loc_18011D71A
0x18011d7da  mov     rcx, [r15]; this
0x18011d7dd  call    ?Dispose@CopyOnWriteBitmap@@AEAAXXZ; CopyOnWriteBitmap::Dispose(void)
0x18011d7e2  mov     qword ptr [r15], 0
0x18011d7e9  mov     r14d, 2
0x18011d7ef  jmp     loc_18011D71A
0x18011d7f4  mov     qword ptr [r15], 0
0x18011d7fb  mov     rcx, rbx
0x18011d7fe  call    GpFree
0x18011d803  mov     r14d, 3
0x18011d809  jmp     loc_18011D71A
0x18011d80e  mov     eax, 3
0x18011d813  jmp     loc_18011D71D
```
