# GdipFlattenGdiPath

- ea: `0x18008ef00`
- end: `0x18008f2f3`
- name: `GdipFlattenGdiPath`
- size: `1011`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1801456fc`

## callees

- `0x18008ef00`
- `0x18008f300`
- `0x18008f47c`
- `0x18008f730`
- `0x18008f8c0`
- `0x18008fa70`
- `0x18008fbe0`
- `0x180090040`
- `0x1800901c0`
- `0x1800b1ee8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ef7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f148`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f17d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ef7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f148`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f17d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f2aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f2be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f2d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f2aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f2be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f2d2`
- `GDI32!GetPath` at `0x18008ef31`
- `GDI32!GetPath` at `0x18008efbc`
- `GDI32!GetPath` at `0x18008ef31`
- `GDI32!GetPath` at `0x18008efbc`

## pseudocode

```c
__int64 __fastcall GdipFlattenGdiPath(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned int v4; // r13d
  _BYTE *v5; // r15
  char *v6; // rsi
  int Path; // eax
  unsigned __int64 v8; // rbx
  __int64 v9; // rdi
  SIZE_T v10; // rax
  char *v11; // rax
  HDC v12; // rcx
  struct tagPOINT *v13; // rbp
  char v14; // bp
  LPBYTE v15; // r8
  float *v16; // rcx
  float v17; // xmm1_4
  int v18; // eax
  char v19; // dl
  __int64 v20; // rdi
  __int64 v21; // rbx
  signed __int64 v22; // r14
  char *v23; // rax
  char *v24; // rax
  __int64 v25; // rcx
  char *v26; // r12
  int PathTypes; // eax
  _DWORD *v28; // rdx
  signed __int64 v29; // r8
  signed __int64 v30; // rdi
  char v31; // cl
  _DWORD *v32; // rcx
  char *v34; // [rsp+40h] [rbp-78h]
  __int64 v35; // [rsp+48h] [rbp-70h] BYREF
  __int64 v36[12]; // [rsp+58h] [rbp-60h] BYREF
  LPBYTE v37; // [rsp+C0h] [rbp+8h] BYREF
  _QWORD *v38; // [rsp+C8h] [rbp+10h]
  _DWORD *v39; // [rsp+D0h] [rbp+18h]
  HLOCAL hMem; // [rsp+D8h] [rbp+20h]

  v39 = a3;
  v38 = a2;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  Path = GetPath(*(HDC *)(a1 + 40), 0, 0, 0);
  v8 = Path;
  if ( Path != -1 )
  {
    if ( !Path )
      return 1;
    v37 = 0;
    v9 = Path;
    v10 = 17LL * Path;
    if ( is_mul_ok(0x11u, v8) )
    {
      v11 = (char *)LocalAlloc(0, v10);
      hMem = v11;
      if ( v11 )
      {
        v12 = *(HDC *)(a1 + 40);
        v13 = (struct tagPOINT *)&v11[8 * v8];
        v37 = (LPBYTE)&v13[v8];
        if ( GetPath(v12, v13, v37, v8) != (_DWORD)v8
          || !pfnSetVirtualResolution && !(unsigned int)bXformWorkhorse(v13, (unsigned int)v8, a1 + 108) )
        {
          goto LABEL_39;
        }
        v14 = 0;
        if ( (int)v8 > 0 )
        {
          v15 = v37;
          v16 = (float *)((char *)hMem + 4);
          do
          {
            v17 = (float)SLODWORD(v16[2 * v8]);
            *(v16 - 1) = (float)SLODWORD(v16[2 * v8 - 1]);
            *v16 = v17;
            v18 = *v15 & 0xFE;
            if ( v18 == 2 )
            {
              v19 = 1;
            }
            else if ( v18 == 4 )
            {
              v19 = 3;
            }
            else
            {
              v19 = v18 != 6;
            }
            v14 = v19 | 0x80;
            if ( (*v15 & 1) == 0 )
              v14 = v19;
            v16 += 2;
            *v15++ = v14;
            --v9;
          }
          while ( v9 );
        }
        Gdiplus::Matrix::Matrix(
          (Gdiplus::Matrix *)v36,
          *(float *)(a1 + 228),
          *(float *)(a1 + 232),
          *(float *)(a1 + 236),
          *(float *)(a1 + 240),
          *(float *)(a1 + 244),
          *(float *)(a1 + 248));
        v35 = 0;
        GdipCreatePath2((_DWORD)hMem, (_DWORD)v37, v8, 0, (__int64)&v35);
        v20 = v36[0];
        v21 = v35;
        GdipFlattenPath(v35, v36[0]);
        LODWORD(v37) = 0;
        GdipGetPointCount(v21, &v37);
        if ( (int)v37 >= 0 )
        {
          v22 = (int)v37;
          if ( is_mul_ok(9u, (int)v37) )
          {
            v23 = (char *)LocalAlloc(0, 9LL * (int)v37);
            v5 = v23;
            if ( v23 )
            {
              v34 = &v23[8 * v22];
              if ( is_mul_ok(9u, v22) )
              {
                v24 = (char *)LocalAlloc(0, 9 * v22);
                v6 = v24;
                v25 = v21;
                if ( !v24 )
                  goto LABEL_38;
                v26 = &v24[8 * v22];
                PathTypes = GdipGetPathTypes(v21, v34, (unsigned int)v37);
                v25 = v21;
                if ( PathTypes )
                  goto LABEL_38;
                if ( !(unsigned int)GdipGetPathPoints(v21, v5, (unsigned int)v37) )
                {
                  if ( v22 > 0 )
                  {
                    v28 = v6 + 4;
                    v29 = v5 - v6;
                    v30 = v34 - v26;
                    do
                    {
                      *(v28 - 1) = (int)(float)(*(float *)((char *)v28 + v29 - 4) + 0.5);
                      *v28 = (int)(float)(*(float *)((char *)v28 + v29) + 0.5);
                      if ( (v26[v30] & 0x7F) != 0 )
                      {
                        if ( (v26[v30] & 0x7F) == 1 )
                          v14 = 2;
                      }
                      else
                      {
                        v14 = 6;
                      }
                      v31 = v14 | 1;
                      if ( v26[v30] >= 0 )
                        v31 = v14;
                      v28 += 2;
                      *v26 = v31;
                      v14 = v31;
                      ++v26;
                      --v22;
                    }
                    while ( v22 );
                    v20 = v36[0];
                  }
                  GdipDeletePath(v21);
                  GdipDeleteMatrix(v20);
                  v32 = v39;
                  *v38 = v6;
                  v6 = 0;
                  *v32 = (_DWORD)v37;
                  v4 = 1;
                  goto LABEL_39;
                }
              }
            }
          }
        }
        v25 = v21;
LABEL_38:
        GdipDeletePath(v25);
        GdipDeleteMatrix(v20);
LABEL_39:
        LocalFree(hMem);
        if ( v5 )
          LocalFree(v5);
        if ( v6 )
          LocalFree(v6);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18008ef00  mov     [rsp+arg_10], r8
0x18008ef05  mov     [rsp+arg_8], rdx
0x18008ef0a  push    rbx
0x18008ef0b  push    rbp
0x18008ef0c  push    rsi
0x18008ef0d  push    rdi
0x18008ef0e  push    r12
0x18008ef10  push    r13
0x18008ef12  push    r14
0x18008ef14  push    r15
0x18008ef16  sub     rsp, 78h
0x18008ef1a  mov     r14, rcx
0x18008ef1d  xor     r9d, r9d; cpt
0x18008ef20  mov     rcx, [rcx+28h]; hdc
0x18008ef24  xor     r8d, r8d; aj
0x18008ef27  xor     edx, edx; apt
0x18008ef29  xor     r13d, r13d
0x18008ef2c  xor     r15d, r15d
0x18008ef2f  xor     esi, esi
0x18008ef31  call    cs:__imp_GetPath
0x18008ef38  nop     dword ptr [rax+rax+00h]
0x18008ef3d  movsxd  rbx, eax
0x18008ef40  cmp     ebx, 0FFFFFFFFh
0x18008ef43  jz      loc_18008F2DE
0x18008ef49  test    eax, eax
0x18008ef4b  jnz     short loc_18008EF56
0x18008ef4d  lea     r13d, [r15+1]
0x18008ef51  jmp     loc_18008F2DE
0x18008ef56  and     [rsp+0B8h+arg_0], rsi
0x18008ef5e  mov     ecx, 11h
0x18008ef63  mov     rax, rbx
0x18008ef66  mov     rdi, rbx
0x18008ef69  mul     rcx
0x18008ef6c  test    rdx, rdx
0x18008ef6f  jnz     loc_18008F2DE
0x18008ef75  mov     rdx, rax; uBytes
0x18008ef78  xor     ecx, ecx; uFlags
0x18008ef7a  call    cs:__imp_LocalAlloc
0x18008ef81  nop     dword ptr [rax+rax+00h]
0x18008ef86  mov     [rsp+0B8h+hMem], rax
0x18008ef8e  test    rax, rax
0x18008ef91  jz      loc_18008F2DE
0x18008ef97  mov     rcx, [r14+28h]; hdc
0x18008ef9b  lea     r12, ds:0[rbx*8]
0x18008efa3  lea     rbp, [r12+rax]
0x18008efa7  mov     r9d, ebx; cpt
0x18008efaa  lea     rax, [r12+rbp]
0x18008efae  mov     rdx, rbp; apt
0x18008efb1  mov     r8, rax; aj
0x18008efb4  mov     [rsp+0B8h+arg_0], rax
0x18008efbc  call    cs:__imp_GetPath
0x18008efc3  nop     dword ptr [rax+rax+00h]
0x18008efc8  cmp     eax, ebx
0x18008efca  jnz     loc_18008F2A2
0x18008efd0  cmp     cs:pfnSetVirtualResolution, rsi
0x18008efd7  jnz     short loc_18008EFEF
0x18008efd9  lea     r8, [r14+6Ch]
0x18008efdd  mov     edx, ebx
0x18008efdf  mov     rcx, rbp
0x18008efe2  call    bXformWorkhorse
0x18008efe7  test    eax, eax
0x18008efe9  jz      loc_18008F2A2
0x18008efef  xor     bpl, bpl
0x18008eff2  test    ebx, ebx
0x18008eff4  jle     short loc_18008F069
0x18008eff6  mov     rcx, [rsp+0B8h+hMem]
0x18008effe  mov     r8, [rsp+0B8h+arg_0]
0x18008f006  add     rcx, 4
0x18008f00a  movd    xmm0, dword ptr [r12+rcx-4]
0x18008f011  movd    xmm1, dword ptr [rcx+r12]
0x18008f017  cvtdq2ps xmm0, xmm0
0x18008f01a  cvtdq2ps xmm1, xmm1
0x18008f01d  movss   dword ptr [rcx-4], xmm0
0x18008f022  movss   dword ptr [rcx], xmm1
0x18008f026  movzx   r9d, byte ptr [r8]
0x18008f02a  mov     eax, r9d
0x18008f02d  and     eax, 0FFFFFFFEh
0x18008f030  cmp     eax, 2
0x18008f033  jz      short loc_18008F046
0x18008f035  cmp     eax, 4
0x18008f038  jz      short loc_18008F042
0x18008f03a  cmp     eax, 6
0x18008f03d  setnz   dl
0x18008f040  jmp     short loc_18008F048
0x18008f042  mov     dl, 3
0x18008f044  jmp     short loc_18008F048
0x18008f046  mov     dl, 1
0x18008f048  mov     al, dl
0x18008f04a  or      al, 80h
0x18008f04c  movzx   ebp, al
0x18008f04f  test    r9b, 1
0x18008f053  movzx   eax, dl
0x18008f056  cmovz   ebp, eax
0x18008f059  add     rcx, 8
0x18008f05d  mov     [r8], bpl
0x18008f060  inc     r8
0x18008f063  sub     rdi, 1
0x18008f067  jnz     short loc_18008F00A
0x18008f069  movss   xmm0, dword ptr [r14+0F8h]
0x18008f072  lea     rcx, [rsp+0B8h+var_60]; this
0x18008f077  movss   xmm1, dword ptr [r14+0F4h]
0x18008f080  movss   xmm3, dword ptr [r14+0ECh]; float
0x18008f089  movss   xmm2, dword ptr [r14+0E8h]; float
0x18008f092  movss   [rsp+0B8h+var_88], xmm0; float
0x18008f098  movss   xmm0, dword ptr [r14+0F0h]
0x18008f0a1  movss   [rsp+0B8h+var_90], xmm1; float
0x18008f0a7  movss   xmm1, dword ptr [r14+0E4h]; float
0x18008f0b0  movss   [rsp+0B8h+var_98], xmm0; float
0x18008f0b6  call    ??0Matrix@Gdiplus@@QEAA@MMMMMM@Z; Gdiplus::Matrix::Matrix(float,float,float,float,float,float)
0x18008f0bb  mov     rdx, [rsp+0B8h+arg_0]
0x18008f0c3  lea     rax, [rsp+0B8h+var_70]
0x18008f0c8  mov     rcx, [rsp+0B8h+hMem]
0x18008f0d0  xor     r9d, r9d
0x18008f0d3  and     [rsp+0B8h+var_70], rsi
0x18008f0d8  mov     r8d, ebx
0x18008f0db  mov     qword ptr [rsp+0B8h+var_98], rax
0x18008f0e0  call    GdipCreatePath2
0x18008f0e5  mov     rdi, [rsp+0B8h+var_60]
0x18008f0ea  mov     rbx, [rsp+0B8h+var_70]
0x18008f0ef  mov     rdx, rdi
0x18008f0f2  movss   xmm2, cs:__real@3e2aaaab
0x18008f0fa  mov     rcx, rbx
0x18008f0fd  call    GdipFlattenPath
0x18008f102  and     dword ptr [rsp+0B8h+arg_0], esi
0x18008f109  lea     rdx, [rsp+0B8h+arg_0]
0x18008f111  mov     rcx, rbx
0x18008f114  call    GdipGetPointCount
0x18008f119  movsxd  rax, dword ptr [rsp+0B8h+arg_0]
0x18008f121  test    eax, eax
0x18008f123  js      loc_18008F292
0x18008f129  and     [rsp+0B8h+var_78], rsi
0x18008f12e  mov     r12d, 9
0x18008f134  mov     r14, rax
0x18008f137  mul     r12
0x18008f13a  test    rdx, rdx
0x18008f13d  jnz     loc_18008F292
0x18008f143  mov     rdx, rax; uBytes
0x18008f146  xor     ecx, ecx; uFlags
0x18008f148  call    cs:__imp_LocalAlloc
0x18008f14f  nop     dword ptr [rax+rax+00h]
0x18008f154  mov     r15, rax
0x18008f157  test    rax, rax
0x18008f15a  jz      loc_18008F292
0x18008f160  lea     rax, [rax+r14*8]
0x18008f164  mov     [rsp+0B8h+var_78], rax
0x18008f169  mov     rax, r14
0x18008f16c  mul     r12
0x18008f16f  test    rdx, rdx
0x18008f172  jnz     loc_18008F292
0x18008f178  mov     rdx, rax; uBytes
0x18008f17b  xor     ecx, ecx; uFlags
0x18008f17d  call    cs:__imp_LocalAlloc
0x18008f184  nop     dword ptr [rax+rax+00h]
0x18008f189  mov     rsi, rax
0x18008f18c  mov     rcx, rbx
0x18008f18f  test    rax, rax
0x18008f192  jz      loc_18008F295
0x18008f198  mov     r8d, dword ptr [rsp+0B8h+arg_0]
0x18008f1a0  lea     r12, [rax+r14*8]
0x18008f1a4  mov     rdx, [rsp+0B8h+var_78]
0x18008f1a9  call    GdipGetPathTypes
0x18008f1ae  mov     rcx, rbx
0x18008f1b1  test    eax, eax
0x18008f1b3  jnz     loc_18008F295
0x18008f1b9  mov     r8d, dword ptr [rsp+0B8h+arg_0]
0x18008f1c1  mov     rdx, r15
0x18008f1c4  call    GdipGetPathPoints
0x18008f1c9  test    eax, eax
0x18008f1cb  jnz     loc_18008F292
0x18008f1d1  test    r14, r14
0x18008f1d4  jle     loc_18008F25E
0x18008f1da  mov     rdi, [rsp+0B8h+var_78]
0x18008f1df  lea     rdx, [rsi+4]
0x18008f1e3  movss   xmm2, cs:__real@3f000000
0x18008f1eb  mov     r8, r15
0x18008f1ee  sub     r8, rsi
0x18008f1f1  sub     rdi, r12
0x18008f1f4  movss   xmm0, dword ptr [r8+rdx-4]
0x18008f1fb  addss   xmm0, xmm2
0x18008f1ff  cvttss2si eax, xmm0
0x18008f203  mov     [rdx-4], eax
0x18008f206  movss   xmm1, dword ptr [r8+rdx]
0x18008f20c  addss   xmm1, xmm2
0x18008f210  cvttss2si eax, xmm1
0x18008f214  mov     [rdx], eax
0x18008f216  movzx   r9d, byte ptr [rdi+r12]
0x18008f21b  mov     ecx, r9d
0x18008f21e  and     ecx, 0FFFFFF7Fh
0x18008f224  jz      short loc_18008F230
0x18008f226  cmp     ecx, 1
0x18008f229  jnz     short loc_18008F233
0x18008f22b  mov     bpl, 2
0x18008f22e  jmp     short loc_18008F233
0x18008f230  mov     bpl, 6
0x18008f233  mov     al, bpl
0x18008f236  or      al, 1
0x18008f238  movzx   ecx, al
0x18008f23b  test    r9b, r9b
0x18008f23e  movzx   eax, bpl
0x18008f242  cmovns  ecx, eax
0x18008f245  add     rdx, 8
0x18008f249  mov     [r12], cl
0x18008f24d  mov     bpl, cl
0x18008f250  inc     r12
0x18008f253  sub     r14, 1
0x18008f257  jnz     short loc_18008F1F4
0x18008f259  mov     rdi, [rsp+0B8h+var_60]
0x18008f25e  mov     rcx, rbx
0x18008f261  call    GdipDeletePath
0x18008f266  mov     rcx, rdi
0x18008f269  call    GdipDeleteMatrix
0x18008f26e  mov     rax, [rsp+0B8h+arg_8]
0x18008f276  mov     rcx, [rsp+0B8h+arg_10]
0x18008f27e  mov     [rax], rsi
0x18008f281  xor     esi, esi
0x18008f283  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x18008f28a  mov     [rcx], eax
0x18008f28c  lea     r13d, [rsi+1]
0x18008f290  jmp     short loc_18008F2A2
0x18008f292  mov     rcx, rbx
0x18008f295  call    GdipDeletePath
0x18008f29a  mov     rcx, rdi
0x18008f29d  call    GdipDeleteMatrix
0x18008f2a2  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18008f2aa  call    cs:__imp_LocalFree
0x18008f2b1  nop     dword ptr [rax+rax+00h]
0x18008f2b6  test    r15, r15
0x18008f2b9  jz      short loc_18008F2CA
0x18008f2bb  mov     rcx, r15; hMem
0x18008f2be  call    cs:__imp_LocalFree
0x18008f2c5  nop     dword ptr [rax+rax+00h]
0x18008f2ca  test    rsi, rsi
0x18008f2cd  jz      short loc_18008F2DE
0x18008f2cf  mov     rcx, rsi; hMem
0x18008f2d2  call    cs:__imp_LocalFree
0x18008f2d9  nop     dword ptr [rax+rax+00h]
0x18008f2de  mov     eax, r13d
0x18008f2e1  add     rsp, 78h
0x18008f2e5  pop     r15
0x18008f2e7  pop     r14
0x18008f2e9  pop     r13
0x18008f2eb  pop     r12
0x18008f2ed  pop     rdi
0x18008f2ee  pop     rsi
0x18008f2ef  pop     rbp
0x18008f2f0  pop     rbx
0x18008f2f1  retn
```
