# CopyOnWriteBitmap::CreateFromDibSection(HBITMAP__ *,CopyOnWriteBitmap * *)

- ea: `0x1801045a4`
- end: `0x1801047e3`
- name: `?CreateFromDibSection@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAPEAV1@@Z`
- size: `575`
- prototype: `__int64 __fastcall(void *, CopyOnWriteBitmap **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18010487c`

## callees

- `0x180004698`
- `0x18001f950`
- `0x1800e5044`
- `0x1800e728c`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x1801045a4`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `GDI32!GetDIBColorTable` at `0x1801046b5`
- `GDI32!GetDIBColorTable` at `0x1801046b5`
- `GDI32!DeleteDC` at `0x1801046d8`
- `GDI32!DeleteDC` at `0x1801046d8`
- `GDI32!SelectObject` at `0x180104697`
- `GDI32!SelectObject` at `0x1801046c9`
- `GDI32!SelectObject` at `0x180104697`
- `GDI32!SelectObject` at `0x1801046c9`
- `GDI32!CreateCompatibleDC` at `0x180104679`
- `GDI32!CreateCompatibleDC` at `0x180104679`
- `GDI32!GetObjectA` at `0x18010460f`
- `GDI32!GetObjectA` at `0x18010460f`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromDibSection(void *a1, CopyOnWriteBitmap **a2)
{
  unsigned int v4; // r14d
  unsigned int v5; // esi
  unsigned __int16 epi16; // ax
  HDC CompatibleDC; // rax
  HDC v8; // r12
  HGDIOBJ v9; // rdi
  UINT DIBColorTable; // ebx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rbx
  CopyOnWriteBitmap *v14; // rax
  CopyOnWriteBitmap *v15; // rax
  _BYTE pv[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v19; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v20; // [rsp+32h] [rbp-CEh]
  void *Src; // [rsp+38h] [rbp-C8h]
  __m128i v22; // [rsp+40h] [rbp-C0h]
  __m128i v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  RGBQUAD v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+6Ch] [rbp-94h]
  int v27; // [rsp+70h] [rbp-90h]
  struct tagBITMAPINFO v28; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+BCh] [rbp-44h]
  int v30; // [rsp+C0h] [rbp-40h]

  v4 = 7;
  memset_0(pv, 0, 0x68u);
  memset_0(v28.bmiColors, 0, 0x400u);
  if ( GetObjectA(a1, 104, pv) != 104 )
    return v4;
  v5 = v23.m128i_u32[1];
  if ( !v23.m128i_i32[1] )
    v5 = v18 * v19 * (((v17 * v20 + 31) >> 3) & 0xFFFFFFFC);
  epi16 = _mm_extract_epi16(v22, 7);
  *(__m128i *)&v28.bmiHeader.biSize = v22;
  *(__m128i *)&v28.bmiHeader.biCompression = v23;
  *(_QWORD *)&v28.bmiHeader.biClrUsed = v24;
  if ( epi16 > 8u )
  {
    if ( epi16 == 16 && _mm_cvtsi128_si32(v23) == 3 )
    {
      v28.bmiColors[0] = v25;
      v29 = v26;
      v30 = v27;
    }
  }
  else
  {
    CompatibleDC = CreateCompatibleDC(0);
    v8 = CompatibleDC;
    if ( CompatibleDC )
    {
      v9 = SelectObject(CompatibleDC, a1);
      DIBColorTable = GetDIBColorTable(v8, 0, 0x100u, v28.bmiColors);
      SelectObject(v8, v9);
      DeleteDC(v8);
      if ( !DIBColorTable )
        return v4;
    }
  }
  v12 = (unsigned __int8 *)GpMallocEx(v5, 0);
  v13 = v12;
  if ( v12 )
  {
    memcpy_0(v12, Src, v5);
    v14 = (CopyOnWriteBitmap *)GpMallocEx(264, 0);
    if ( v14 )
    {
      v15 = CopyOnWriteBitmap::CopyOnWriteBitmap(v14, &v28, v13, 1);
      *a2 = v15;
      if ( v15 )
      {
        if ( (*(unsigned int (__fastcall **)(CopyOnWriteBitmap *))(*(_QWORD *)v15 + 16LL))(v15) )
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
    GpFree(v13);
    return 3;
  }
  return 3;
}

```

## disassembly

```asm
0x1801045a4  mov     [rsp-8+arg_10], rbx
0x1801045a9  mov     [rsp-8+arg_18], rsi
0x1801045ae  push    rbp
0x1801045af  push    rdi
0x1801045b0  push    r12
0x1801045b2  push    r14
0x1801045b4  push    r15
0x1801045b6  lea     rbp, [rsp-3D0h]
0x1801045be  sub     rsp, 4D0h
0x1801045c5  mov     rax, cs:__security_cookie
0x1801045cc  xor     rax, rsp
0x1801045cf  mov     [rbp+3F0h+var_30], rax
0x1801045d6  mov     edi, 68h ; 'h'
0x1801045db  mov     r15, rdx
0x1801045de  mov     rbx, rcx
0x1801045e1  mov     r8d, edi; Size
0x1801045e4  xor     edx, edx; Val
0x1801045e6  lea     rcx, [rsp+4F0h+pv]; void *
0x1801045eb  lea     r14d, [rdi-61h]
0x1801045ef  call    memset_0
0x1801045f4  xor     edx, edx; Val
0x1801045f6  lea     rcx, [rbp+3F0h+var_460.bmiColors]; void *
0x1801045fa  mov     r8d, 400h; Size
0x180104600  call    memset_0
0x180104605  lea     r8, [rsp+4F0h+pv]; pv
0x18010460a  mov     edx, edi; c
0x18010460c  mov     rcx, rbx; h
0x18010460f  call    cs:__imp_GetObjectA
0x180104616  nop     dword ptr [rax+rax+00h]
0x18010461b  cmp     eax, edi
0x18010461d  jnz     loc_1801046E8
0x180104623  mov     esi, dword ptr [rsp+4F0h+Size]
0x180104627  test    esi, esi
0x180104629  jnz     short loc_18010464B
0x18010462b  movzx   esi, [rsp+4F0h+var_4BE]
0x180104630  imul    esi, [rsp+4F0h+var_4CC]
0x180104635  movzx   eax, [rsp+4F0h+var_4C0]
0x18010463a  add     esi, 1Fh
0x18010463d  sar     esi, 3
0x180104640  and     esi, 0FFFFFFFCh
0x180104643  imul    esi, eax
0x180104646  imul    esi, [rsp+4F0h+var_4C8]
0x18010464b  movaps  xmm1, [rsp+4F0h+var_4B0]
0x180104650  movaps  xmm2, xmmword ptr [rsp+50h]
0x180104655  movsd   xmm0, [rsp+4F0h+var_490]
0x18010465b  pextrw  eax, xmm1, 7
0x180104660  movaps  xmmword ptr [rbp+3F0h+var_460.bmiHeader.biSize], xmm1
0x180104664  movaps  xmmword ptr [rbp+3F0h+var_460.bmiHeader.biCompression], xmm2
0x180104668  movsd   qword ptr [rbp+3F0h+var_460.bmiHeader.biClrUsed], xmm0
0x18010466d  cmp     ax, 8
0x180104671  ja      loc_180104717
0x180104677  xor     ecx, ecx; hdc
0x180104679  call    cs:__imp_CreateCompatibleDC
0x180104680  nop     dword ptr [rax+rax+00h]
0x180104685  mov     r12, rax
0x180104688  test    rax, rax
0x18010468b  jz      loc_18010473B
0x180104691  mov     rdx, rbx; h
0x180104694  mov     rcx, rax; hdc
0x180104697  call    cs:__imp_SelectObject
0x18010469e  nop     dword ptr [rax+rax+00h]
0x1801046a3  lea     r9, [rbp+3F0h+var_460.bmiColors]; prgbq
0x1801046a7  xor     edx, edx; iStart
0x1801046a9  mov     r8d, 100h; cEntries
0x1801046af  mov     rcx, r12; hdc
0x1801046b2  mov     rdi, rax
0x1801046b5  call    cs:__imp_GetDIBColorTable
0x1801046bc  nop     dword ptr [rax+rax+00h]
0x1801046c1  mov     rdx, rdi; h
0x1801046c4  mov     rcx, r12; hdc
0x1801046c7  mov     ebx, eax
0x1801046c9  call    cs:__imp_SelectObject
0x1801046d0  nop     dword ptr [rax+rax+00h]
0x1801046d5  mov     rcx, r12; hdc
0x1801046d8  call    cs:__imp_DeleteDC
0x1801046df  nop     dword ptr [rax+rax+00h]
0x1801046e4  test    ebx, ebx
0x1801046e6  jnz     short loc_18010473B
0x1801046e8  mov     eax, r14d
0x1801046eb  mov     rcx, [rbp+3F0h+var_30]
0x1801046f2  xor     rcx, rsp; StackCookie
0x1801046f5  call    __security_check_cookie
0x1801046fa  lea     r11, [rsp+4F0h+var_20]
0x180104702  mov     rbx, [r11+40h]
0x180104706  mov     rsi, [r11+48h]
0x18010470a  mov     rsp, r11
0x18010470d  pop     r15
0x18010470f  pop     r14
0x180104711  pop     r12
0x180104713  pop     rdi
0x180104714  pop     rbp
0x180104715  retn
0x180104717  cmp     ax, 10h
0x18010471b  jnz     short loc_18010473B
0x18010471d  movd    eax, xmm2
0x180104721  cmp     eax, 3
0x180104724  jnz     short loc_18010473B
0x180104726  mov     eax, [rsp+4F0h+var_488]
0x18010472a  mov     dword ptr [rbp+3F0h+var_460.bmiColors.rgbBlue], eax
0x18010472d  mov     eax, [rsp+4F0h+var_484]
0x180104731  mov     [rbp+3F0h+var_434], eax
0x180104734  mov     eax, [rsp+4F0h+var_480]
0x180104738  mov     [rbp+3F0h+var_430], eax
0x18010473b  xor     edx, edx
0x18010473d  mov     ecx, esi
0x18010473f  mov     edi, esi
0x180104741  call    GpMallocEx
0x180104746  mov     rbx, rax
0x180104749  test    rax, rax
0x18010474c  jz      loc_1801047D9
0x180104752  mov     rdx, [rsp+4F0h+Src]; Src
0x180104757  mov     r8d, edi; Size
0x18010475a  mov     rcx, rax; void *
0x18010475d  call    memcpy_0
0x180104762  xor     edx, edx
0x180104764  mov     ecx, 108h
0x180104769  call    GpMallocEx
0x18010476e  test    rax, rax
0x180104771  jz      short loc_1801047C2
0x180104773  mov     r9d, 1; int
0x180104779  lea     rdx, [rbp+3F0h+var_460]; struct tagBITMAPINFO *
0x18010477d  mov     r8, rbx; void *
0x180104780  mov     rcx, rax; this
0x180104783  call    ??0CopyOnWriteBitmap@@AEAA@PEAUtagBITMAPINFO@@PEAXH@Z; CopyOnWriteBitmap::CopyOnWriteBitmap(tagBITMAPINFO *,void *,int)
0x180104788  mov     [r15], rax
0x18010478b  mov     rcx, rax
0x18010478e  test    rax, rax
0x180104791  jz      short loc_1801047C6
0x180104793  mov     rax, [rax]
0x180104796  mov     rax, [rax+10h]
0x18010479a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010479f  test    eax, eax
0x1801047a1  jz      short loc_1801047AB
0x1801047a3  xor     r14d, r14d
0x1801047a6  jmp     loc_1801046E8
0x1801047ab  mov     rcx, [r15]; this
0x1801047ae  call    ?Dispose@CopyOnWriteBitmap@@AEAAXXZ; CopyOnWriteBitmap::Dispose(void)
0x1801047b3  and     qword ptr [r15], 0
0x1801047b7  mov     r14d, 2
0x1801047bd  jmp     loc_1801046E8
0x1801047c2  and     qword ptr [r15], 0
0x1801047c6  mov     rcx, rbx
0x1801047c9  call    GpFree
0x1801047ce  mov     r14d, 3
0x1801047d4  jmp     loc_1801046E8
0x1801047d9  mov     eax, 3
0x1801047de  jmp     loc_1801046EB
```
