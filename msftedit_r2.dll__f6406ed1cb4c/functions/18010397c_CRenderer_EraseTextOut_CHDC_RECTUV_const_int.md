# CRenderer::EraseTextOut(CHDC &,RECTUV const *,int)

- ea: `0x18010397c`
- end: `0x180103ed4`
- name: `?EraseTextOut@CRenderer@@AEAAXAEAVCHDC@@PEBURECTUV@@H@Z`
- size: `1368`
- prototype: `void __fastcall(CRenderer *__hidden this, struct CHDC *, const struct RECTUV *, int)`
- caller_count: `14`
- callee_count: `7`
- tags: ``

## callers

- `0x18002b134`
- `0x18002c668`
- `0x18002eb2c`
- `0x18004e4a0`
- `0x18004efa4`
- `0x180095890`
- `0x1800a9240`
- `0x1800ff310`
- `0x18012214c`
- `0x180126a4c`
- `0x18014e79c`
- `0x18014ed74`
- `0x18014f31c`
- `0x18014f6a0`

## callees

- `0x18004e140`
- `0x18004ef64`
- `0x18010397c`
- `0x180103edc`
- `0x18013ce80`
- `0x18014e9d8`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103dc5`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103dd7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103e8b`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103dc5`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103dd7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103e8b`
- `ext-ms-win-gdi-draw-l1-1-1!Polyline` at `0x180103e51`
- `ext-ms-win-gdi-draw-l1-1-1!Polyline` at `0x180103e51`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103d7f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103e79`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103d7f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103e79`

## pseudocode

```c
void __fastcall CRenderer::EraseTextOut(CRenderer *this, struct CHDC *a2, const struct RECTUV *a3, int a4)
{
  bool v4; // zf
  struct CHDC *v6; // r12
  CDisplay *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rsi
  _DWORD *v13; // rcx
  int v14; // r15d
  int v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // edi
  signed int v20; // ecx
  int v21; // r8d
  int v22; // r10d
  LONG v23; // r13d
  int v24; // eax
  unsigned int v25; // eax
  int v26; // r8d
  int v27; // edx
  LONG v28; // r8d
  int v29; // edx
  int v30; // r11d
  unsigned int v31; // r12d
  LONG v32; // r15d
  int v33; // edx
  int v34; // r9d
  unsigned int i; // ebx
  __int64 *v36; // rcx
  __int64 v37; // rax
  unsigned int v38; // eax
  unsigned int *v39; // r8
  __int64 *v40; // rcx
  int v41; // r15d
  LONG right; // eax
  int v43; // r13d
  LONG left; // r15d
  void *v45; // r14
  int v46; // esi
  int v47; // ecx
  LONG v48; // edi
  int v49; // eax
  int v50; // r12d
  unsigned int ShadedColor; // eax
  void *v52; // rax
  HDC v53; // r12
  int top; // eax
  HGDIOBJ v55; // rbx
  int v56; // [rsp+70h] [rbp-29h]
  LONG v57; // [rsp+70h] [rbp-29h]
  unsigned int v58; // [rsp+74h] [rbp-25h]
  unsigned int v59; // [rsp+74h] [rbp-25h]
  unsigned int v60; // [rsp+74h] [rbp-25h]
  unsigned int v61; // [rsp+78h] [rbp-21h] BYREF
  POINT apt; // [rsp+80h] [rbp-19h] BYREF
  LONG v63; // [rsp+88h] [rbp-11h]
  LONG bottom; // [rsp+8Ch] [rbp-Dh]
  HGDIOBJ h; // [rsp+90h] [rbp-9h]
  HDC hdc; // [rsp+98h] [rbp-1h]
  struct tagRECT v67; // [rsp+A0h] [rbp+7h] BYREF

  v4 = (*((_DWORD *)this + 125) & 0x4000) == 0;
  v6 = a2;
  apt = (POINT)a2;
  if ( !v4 )
    return;
  v8 = (CDisplay *)*((_QWORD *)this + 19);
  v67 = 0;
  CDisplay::RectFromRectuv(v8, &v67, a3, 1, 0);
  if ( a4 || (unsigned int)CRenderer::IsSimpleBackground(this) )
    goto LABEL_44;
  v9 = *((_QWORD *)this + 2);
  v10 = v9 ? *(_QWORD *)(v9 + 40) : 0LL;
  if ( (*(_DWORD *)(v10 + 184) & 0x40000000) != 0 )
    goto LABEL_44;
  v11 = v9 ? *(_QWORD *)(v9 + 40) : 0LL;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
    goto LABEL_44;
  v13 = (_DWORD *)*((_QWORD *)this + 19);
  v14 = v13[34];
  v15 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 376LL))(v13);
  v16 = CMeasurerNoFC::GetTflow(this) - 1;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 != 2 )
        {
          v19 = v14;
          goto LABEL_23;
        }
        v19 = v15;
        goto LABEL_22;
      }
      v19 = v15;
      v15 = v14;
    }
    else
    {
      v19 = -v14;
    }
    v15 = -v15;
    goto LABEL_23;
  }
  v19 = -v15;
LABEL_22:
  v15 = v14;
LABEL_23:
  if ( (unsigned int)(*(char *)(v12 + 139) - 1) > 2 )
  {
    v40 = *(__int64 **)v6;
    v41 = *(__int16 *)(v12 + 140);
    v61 = *(_DWORD *)(v12 + 128);
    v59 = *(_DWORD *)(v12 + 132);
    hdc = (HDC)(*(__int64 (__fastcall **)(__int64 *))(*v40 + 48))(v40);
    if ( !hdc )
      goto LABEL_44;
    right = v67.right;
    v43 = v41;
    left = v67.left;
    v45 = 0;
    h = 0;
    v57 = v67.right;
    if ( v43 == -135 || v43 == -45 )
    {
      v46 = v67.bottom - v67.top;
      if ( v43 != -45 )
      {
        v15 += v67.top + v19;
        right = v46 + v67.right;
        goto LABEL_55;
      }
      left = v67.left - v46;
      v15 = v19 - v15 - v67.top;
      v46 = v67.top - v67.bottom;
    }
    else
    {
      v46 = 0;
      if ( !v43 )
      {
        left = v67.top;
        right = v67.bottom;
LABEL_55:
        v57 = right;
        goto LABEL_56;
      }
      v15 = v19;
    }
LABEL_56:
    v47 = v59;
    v48 = left;
    if ( !v59 )
      v47 = 6579300;
    v60 = v47;
    if ( left < right )
    {
      do
      {
        v49 = (v48 + v15) % 600 + 600;
        if ( (v48 + v15) % 600 >= 0 )
          v49 = (v48 + v15) % 600;
        v50 = 600 - v49;
        if ( v49 <= 300 )
          v50 = v49;
        if ( v50 <= 30 )
        {
          v50 = 30;
        }
        else if ( v50 >= 270 )
        {
          v50 = 270;
        }
        if ( v45 )
          DeleteObject(v45);
        ShadedColor = GetShadedColor(v60, v61, v50);
        v52 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))pfnCreatePen)(0, 0, ShadedColor);
        v53 = hdc;
        v45 = v52;
        if ( v52 )
        {
          if ( h )
            SelectObject(hdc, v52);
          else
            h = SelectObject(hdc, v52);
        }
        if ( v43 )
        {
          if ( v48 <= v67.right )
          {
            top = v67.top;
            apt.x = v48;
          }
          else
          {
            apt.x = v67.right;
            top = v67.top + v48 - v67.right;
          }
          apt.y = top;
          if ( v48 - v46 >= left )
          {
            v63 = v48 - v46;
            bottom = v67.bottom;
          }
          else
          {
            v63 = left - 1;
            bottom = v67.bottom + 1 + v48 - left - v46;
          }
        }
        else
        {
          apt.x = v67.left;
          v63 = v67.right;
          apt.y = v48;
          bottom = v48;
        }
        Polyline(v53, &apt, 2);
        ++v48;
      }
      while ( v48 < v57 );
      if ( v45 )
      {
        v55 = h;
        if ( h )
        {
          DeleteObject(v45);
          SelectObject(v53, v55);
        }
      }
    }
    return;
  }
  if ( *((__int16 *)this + 248) <= 0
    || (v20 = *((__int16 *)this + 249), *((__int16 *)this + 249) <= 0)
    || !*(_QWORD *)(v12 + 88) )
  {
LABEL_43:
    *(_BYTE *)(v12 + 139) = 0;
LABEL_44:
    v36 = *(__int64 **)v6;
    v37 = **(_QWORD **)v6;
    if ( *((char *)this + 500) >= 0 )
    {
      v39 = 0;
    }
    else
    {
      v38 = (*(__int64 (**)(void))(v37 + 360))();
      v36 = *(__int64 **)v6;
      v39 = &v61;
      v61 = v38;
      v37 = *v36;
    }
    (*(void (__fastcall **)(__int64 *, struct tagRECT *, unsigned int *))(v37 + 256))(v36, &v67, v39);
    return;
  }
  v21 = *(__int16 *)(v12 + 170);
  v22 = *((__int16 *)this + 248);
  v23 = v67.top;
  LODWORD(hdc) = v22;
  v24 = *(__int16 *)(v12 + 164);
  v61 = v20;
  v25 = (int)((unsigned __int64)(1374389535LL * v24 * *(__int16 *)(v12 + 168)) >> 32) >> 5;
  v26 = *(__int16 *)(v12 + 166) * v21;
  LODWORD(h) = (v25 >> 31) + v25;
  v27 = (unsigned __int64)(1374389535LL * v26) >> 32;
  v28 = v67.right;
  v58 = ((unsigned int)v27 >> 31) + (v27 >> 5);
  v29 = (v15 + v67.top) % v20;
  v30 = v29 + v20;
  if ( v29 >= 0 )
    v30 = (v15 + v67.top) % v20;
  v31 = v20 - v30;
LABEL_30:
  v56 = v30;
  if ( v23 < v67.bottom )
  {
    if ( (int)(v31 + v23) > v67.bottom )
      v31 = v67.bottom - v23;
    v32 = v67.left;
    v33 = (v19 + v67.left) % v22;
    v34 = v33 + v22;
    if ( v33 >= 0 )
      v34 = (v19 + v67.left) % v22;
    for ( i = v22 - v34; ; i = (unsigned int)hdc )
    {
      if ( v32 >= v28 )
      {
        v23 += v31;
        v31 = v61;
        v30 = 0;
        goto LABEL_30;
      }
      if ( (int)(v32 + i) > v28 )
        i = v28 - v32;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, int, int, int, _DWORD, unsigned int, _QWORD, __int64, __int64))(***(_QWORD ***)&apt + 240LL))(
              **(_QWORD **)&apt,
              (unsigned int)v32,
              (unsigned int)v23,
              i,
              v31,
              v34,
              v30,
              13369376,
              (_DWORD)h,
              v58,
              *(_QWORD *)(v12 + 88),
              v12 + 96,
              v12 + 104) )
        break;
      v22 = (int)hdc;
      v32 += i;
      v28 = v67.right;
      v34 = 0;
      v30 = v56;
    }
    v6 = (struct CHDC *)apt;
    goto LABEL_43;
  }
}

```

## disassembly

```asm
0x18010397c  mov     [rsp-8+arg_18], rbx
0x180103981  push    rbp
0x180103982  push    rsi
0x180103983  push    rdi
0x180103984  push    r12
0x180103986  push    r13
0x180103988  push    r14
0x18010398a  push    r15
0x18010398c  lea     rbp, [rsp-27h]
0x180103991  sub     rsp, 0C0h
0x180103998  mov     rax, cs:__security_cookie
0x18010399f  xor     rax, rsp
0x1801039a2  mov     [rbp+57h+var_40], rax
0x1801039a6  test    dword ptr [rcx+1F4h], 4000h
0x1801039b0  mov     ebx, r9d
0x1801039b3  mov     r12, rdx
0x1801039b6  mov     qword ptr [rbp+57h+apt.x], rdx
0x1801039ba  mov     r14, rcx
0x1801039bd  jnz     loc_180103EAC
0x1801039c3  mov     rcx, [rcx+98h]; this
0x1801039ca  lea     rdx, [rbp+57h+var_50]; struct tagRECT *
0x1801039ce  xorps   xmm0, xmm0
0x1801039d1  xor     r13d, r13d
0x1801039d4  mov     r9b, 1; bool
0x1801039d7  mov     [rsp+0F0h+var_D0], r13b; bool
0x1801039dc  movups  xmmword ptr [rbp+57h+var_50.left], xmm0
0x1801039e0  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x1801039e5  test    ebx, ebx
0x1801039e7  jnz     loc_180103C45
0x1801039ed  mov     rcx, r14; this
0x1801039f0  call    ?IsSimpleBackground@CRenderer@@QEBAHXZ; CRenderer::IsSimpleBackground(void)
0x1801039f5  test    eax, eax
0x1801039f7  jnz     loc_180103C45
0x1801039fd  mov     rdx, [r14+10h]
0x180103a01  test    rdx, rdx
0x180103a04  jz      short loc_180103A0C
0x180103a06  mov     rax, [rdx+28h]
0x180103a0a  jmp     short loc_180103A0F
0x180103a0c  mov     rax, r13
0x180103a0f  mov     eax, [rax+0B8h]
0x180103a15  shr     eax, 1Eh
0x180103a18  test    al, 1
0x180103a1a  jnz     loc_180103C45
0x180103a20  test    rdx, rdx
0x180103a23  jz      short loc_180103A2B
0x180103a25  mov     rsi, [rdx+28h]
0x180103a29  jmp     short loc_180103A2E
0x180103a2b  mov     rsi, r13
0x180103a2e  mov     rsi, [rsi+100h]
0x180103a35  test    rsi, rsi
0x180103a38  jz      loc_180103C45
0x180103a3e  mov     rcx, [r14+98h]
0x180103a45  mov     rax, [rcx]
0x180103a48  mov     r15d, [rcx+88h]
0x180103a4f  mov     rax, [rax+178h]
0x180103a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a5b  mov     rcx, r14; this
0x180103a5e  mov     ebx, eax
0x180103a60  call    ?GetTflow@CMeasurerNoFC@@QEBAEXZ; CMeasurerNoFC::GetTflow(void)
0x180103a65  movzx   eax, al
0x180103a68  sub     eax, 1
0x180103a6b  jz      short loc_180103A95
0x180103a6d  sub     eax, 1
0x180103a70  jz      short loc_180103A8C
0x180103a72  sub     eax, 1
0x180103a75  jz      short loc_180103A85
0x180103a77  cmp     eax, 2
0x180103a7a  jz      short loc_180103A81
0x180103a7c  mov     edi, r15d
0x180103a7f  jmp     short loc_180103A9C
0x180103a81  mov     edi, ebx
0x180103a83  jmp     short loc_180103A99
0x180103a85  mov     edi, ebx
0x180103a87  mov     ebx, r15d
0x180103a8a  jmp     short loc_180103A91
0x180103a8c  mov     edi, r15d
0x180103a8f  neg     edi
0x180103a91  neg     ebx
0x180103a93  jmp     short loc_180103A9C
0x180103a95  mov     edi, ebx
0x180103a97  neg     edi
0x180103a99  mov     ebx, r15d
0x180103a9c  movsx   eax, byte ptr [rsi+8Bh]
0x180103aa3  dec     eax
0x180103aa5  cmp     eax, 2
0x180103aa8  ja      loc_180103C79
0x180103aae  movsx   eax, word ptr [r14+1F0h]
0x180103ab6  test    ax, ax
0x180103ab9  jle     loc_180103C3E
0x180103abf  movsx   ecx, word ptr [r14+1F2h]
0x180103ac7  test    cx, cx
0x180103aca  jle     loc_180103C3E
0x180103ad0  cmp     [rsi+58h], r13
0x180103ad4  jz      loc_180103C3E
0x180103ada  movsx   r8d, word ptr [rsi+0AAh]
0x180103ae2  mov     r10d, eax
0x180103ae5  mov     r13d, [rbp+57h+var_50.top]
0x180103ae9  mov     r9d, ecx
0x180103aec  mov     dword ptr [rbp+57h+hdc], eax
0x180103aef  mov     r11d, 51EB851Fh
0x180103af5  movsx   eax, word ptr [rsi+0A4h]
0x180103afc  mov     r12d, r9d
0x180103aff  mov     [rbp+57h+var_78], ecx
0x180103b02  movsx   ecx, word ptr [rsi+0A8h]
0x180103b09  imul    ecx, eax
0x180103b0c  mov     eax, r11d
0x180103b0f  imul    ecx
0x180103b11  mov     eax, edx
0x180103b13  sar     eax, 5
0x180103b16  mov     ecx, eax
0x180103b18  shr     ecx, 1Fh
0x180103b1b  add     eax, ecx
0x180103b1d  movsx   ecx, word ptr [rsi+0A6h]
0x180103b24  imul    r8d, ecx
0x180103b28  mov     dword ptr [rbp+57h+h], eax
0x180103b2b  mov     eax, r11d
0x180103b2e  imul    r8d
0x180103b31  mov     r8d, [rbp+57h+var_50.right]
0x180103b35  mov     ecx, edx
0x180103b37  sar     ecx, 5
0x180103b3a  mov     eax, ecx
0x180103b3c  shr     eax, 1Fh
0x180103b3f  add     ecx, eax
0x180103b41  lea     eax, [rbx+r13]
0x180103b45  cdq
0x180103b46  mov     [rbp+57h+var_7C], ecx
0x180103b49  idiv    r9d
0x180103b4c  test    edx, edx
0x180103b4e  lea     r11d, [rdx+r9]
0x180103b52  cmovns  r11d, edx
0x180103b56  sub     r12d, r11d
0x180103b59  mov     ecx, [rbp+57h+var_50.bottom]
0x180103b5c  mov     [rbp+57h+var_80], r11d
0x180103b60  cmp     r13d, ecx
0x180103b63  jge     loc_180103EAC
0x180103b69  lea     eax, [r12+r13]
0x180103b6d  cmp     eax, ecx
0x180103b6f  jle     short loc_180103B77
0x180103b71  mov     r12d, ecx
0x180103b74  sub     r12d, r13d
0x180103b77  mov     r15d, [rbp+57h+var_50.left]
0x180103b7b  mov     ebx, r10d
0x180103b7e  lea     eax, [rdi+r15]
0x180103b82  cdq
0x180103b83  idiv    r10d
0x180103b86  test    edx, edx
0x180103b88  lea     r9d, [rdx+r10]
0x180103b8c  cmovns  r9d, edx
0x180103b90  sub     ebx, r9d
0x180103b93  cmp     r15d, r8d
0x180103b96  jge     loc_180103C28
0x180103b9c  lea     eax, [r15+rbx]
0x180103ba0  cmp     eax, r8d
0x180103ba3  jle     short loc_180103BAB
0x180103ba5  mov     ebx, r8d
0x180103ba8  sub     ebx, r15d
0x180103bab  mov     rax, qword ptr [rbp+57h+apt.x]
0x180103baf  lea     r8, [rsi+60h]
0x180103bb3  lea     rdx, [rsi+68h]
0x180103bb7  mov     [rsp+0F0h+var_90], rdx
0x180103bbc  mov     rdx, [rsi+58h]
0x180103bc0  mov     rcx, [rax]
0x180103bc3  mov     [rsp+0F0h+var_98], r8
0x180103bc8  mov     r8d, r13d
0x180103bcb  mov     [rsp+0F0h+var_A0], rdx
0x180103bd0  mov     edx, [rbp+57h+var_7C]
0x180103bd3  mov     rax, [rcx]
0x180103bd6  mov     [rsp+0F0h+var_A8], edx
0x180103bda  mov     edx, dword ptr [rbp+57h+h]
0x180103bdd  mov     [rsp+0F0h+var_B0], edx
0x180103be1  mov     edx, r15d
0x180103be4  mov     rax, [rax+0F0h]
0x180103beb  mov     [rsp+0F0h+var_B8], 0CC0020h
0x180103bf3  mov     [rsp+0F0h+var_C0], r11d
0x180103bf8  mov     [rsp+0F0h+var_C8], r9d
0x180103bfd  mov     r9d, ebx
0x180103c00  mov     dword ptr [rsp+0F0h+var_D0], r12d
0x180103c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103c0a  test    al, al
0x180103c0c  jz      short loc_180103C37
0x180103c0e  mov     r10d, dword ptr [rbp+57h+hdc]
0x180103c12  add     r15d, ebx
0x180103c15  mov     r8d, [rbp+57h+var_50.right]
0x180103c19  xor     r9d, r9d
0x180103c1c  mov     r11d, [rbp+57h+var_80]
0x180103c20  mov     ebx, r10d
0x180103c23  jmp     loc_180103B93
0x180103c28  add     r13d, r12d
0x180103c2b  mov     r12d, [rbp+57h+var_78]
0x180103c2f  xor     r11d, r11d
0x180103c32  jmp     loc_180103B59
0x180103c37  mov     r12, qword ptr [rbp+57h+apt.x]
0x180103c3b  xor     r13d, r13d
0x180103c3e  mov     [rsi+8Bh], r13b
0x180103c45  test    byte ptr [r14+1F4h], 80h
0x180103c4d  mov     rcx, [r12]
0x180103c51  mov     rax, [rcx]
0x180103c54  jz      loc_180103E99
0x180103c5a  mov     rax, [rax+168h]
0x180103c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103c66  mov     rcx, [r12]
0x180103c6a  lea     r8, [rbp+57h+var_78]
0x180103c6e  mov     [rbp+57h+var_78], eax
0x180103c71  mov     rax, [rcx]
0x180103c74  jmp     loc_180103E9C
0x180103c79  mov     eax, [rsi+80h]
0x180103c7f  mov     rcx, [r12]
0x180103c83  movsx   r15d, word ptr [rsi+8Ch]
0x180103c8b  mov     [rbp+57h+var_78], eax
0x180103c8e  mov     eax, [rsi+84h]
0x180103c94  mov     [rbp+57h+var_7C], eax
0x180103c97  mov     rax, [rcx]
0x180103c9a  mov     rax, [rax+30h]
0x180103c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103ca3  mov     [rbp+57h+hdc], rax
0x180103ca7  test    rax, rax
0x180103caa  jz      short loc_180103C45
0x180103cac  mov     eax, [rbp+57h+var_50.right]
0x180103caf  mov     r13d, r15d
0x180103cb2  mov     r15d, [rbp+57h+var_50.left]
0x180103cb6  xor     r14d, r14d
0x180103cb9  mov     [rbp+57h+h], r14
0x180103cbd  mov     [rbp+57h+var_80], eax
0x180103cc0  cmp     r13d, 0FFFFFF79h
0x180103cc7  jz      short loc_180103CE3
0x180103cc9  cmp     r13d, 0FFFFFFD3h
0x180103ccd  jz      short loc_180103CE3
0x180103ccf  xor     esi, esi
0x180103cd1  test    r13d, r13d
0x180103cd4  jnz     short loc_180103CDF
0x180103cd6  mov     r15d, [rbp+57h+var_50.top]
0x180103cda  mov     eax, [rbp+57h+var_50.bottom]
0x180103cdd  jmp     short loc_180103D04
0x180103cdf  mov     ebx, edi
0x180103ce1  jmp     short loc_180103D07
0x180103ce3  mov     esi, [rbp+57h+var_50.bottom]
0x180103ce6  mov     ecx, [rbp+57h+var_50.top]
0x180103ce9  sub     esi, ecx
0x180103ceb  cmp     r13d, 0FFFFFFD3h
0x180103cef  jnz     short loc_180103CFE
0x180103cf1  sub     edi, ebx
0x180103cf3  sub     r15d, esi
0x180103cf6  mov     ebx, edi
0x180103cf8  sub     ebx, ecx
0x180103cfa  neg     esi
0x180103cfc  jmp     short loc_180103D07
0x180103cfe  add     ebx, edi
0x180103d00  add     ebx, ecx
0x180103d02  add     eax, esi
0x180103d04  mov     [rbp+57h+var_80], eax
0x180103d07  mov     ecx, [rbp+57h+var_7C]
0x180103d0a  mov     edx, 646464h
0x180103d0f  test    ecx, ecx
0x180103d11  mov     edi, r15d
0x180103d14  cmovz   ecx, edx
0x180103d17  mov     [rbp+57h+var_7C], ecx
0x180103d1a  cmp     r15d, eax
0x180103d1d  jge     loc_180103EAC
0x180103d23  lea     ecx, [rdi+rbx]
0x180103d26  mov     eax, 1B4E81B5h
0x180103d2b  imul    ecx
0x180103d2d  mov     r12d, 258h
0x180103d33  sar     edx, 6
0x180103d36  mov     eax, edx
0x180103d38  shr     eax, 1Fh
0x180103d3b  add     edx, eax
0x180103d3d  imul    eax, edx, 258h
0x180103d43  sub     ecx, eax
0x180103d45  lea     eax, [rcx+258h]
0x180103d4b  cmovns  eax, ecx
0x180103d4e  sub     r12d, eax
0x180103d51  cmp     eax, 12Ch
0x180103d56  cmovle  r12d, eax
0x180103d5a  cmp     r12d, 1Eh
0x180103d5e  jle     short loc_180103D71
0x180103d60  cmp     r12d, 10Eh
0x180103d67  jl      short loc_180103D77
0x180103d69  mov     r12d, 10Eh
0x180103d6f  jmp     short loc_180103D77
0x180103d71  mov     r12d, 1Eh
0x180103d77  test    r14, r14
0x180103d7a  jz      short loc_180103D8B
0x180103d7c  mov     rcx, r14; ho
0x180103d7f  call    cs:__imp_DeleteObject
0x180103d86  nop     dword ptr [rax+rax+00h]
0x180103d8b  mov     edx, [rbp+57h+var_78]; unsigned int
0x180103d8e  mov     r8d, r12d; int
0x180103d91  mov     ecx, [rbp+57h+var_7C]; unsigned int
0x180103d94  call    ?GetShadedColor@@YAKKKJ@Z; GetShadedColor(ulong,ulong,long)
0x180103d99  mov     r8d, eax
0x180103d9c  xor     edx, edx
0x180103d9e  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x180103da5  xor     ecx, ecx
0x180103da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103dac  mov     r12, [rbp+57h+hdc]
0x180103db0  mov     r14, rax
0x180103db3  test    rax, rax
0x180103db6  jz      short loc_180103DE3
0x180103db8  cmp     [rbp+57h+h], 0
0x180103dbd  mov     rdx, rax; h
  ... truncated ...
```
