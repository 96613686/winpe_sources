# GdipFlattenGdiPath

- ea: `0x1800af12c`
- end: `0x1800af4d4`
- name: `GdipFlattenGdiPath`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180142c70`

## callees

- `0x180026b10`
- `0x1800af12c`
- `0x1800af4e0`
- `0x1800af5e0`
- `0x1800af744`
- `0x1800af7d0`
- `0x1800af900`
- `0x1800afa70`
- `0x1800afbc0`
- `0x1800c3bb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af361`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af394`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af361`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af394`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af49e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af4ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af4ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af49e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af4ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af4ba`
- `GDI32!GetPath` at `0x1800af158`
- `GDI32!GetPath` at `0x1800af1d3`
- `GDI32!GetPath` at `0x1800af158`
- `GDI32!GetPath` at `0x1800af1d3`

## pseudocode

```c
__int64 __fastcall GdipFlattenGdiPath(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned int v4; // r12d
  int Path; // eax
  unsigned __int64 v6; // rbx
  SIZE_T v7; // rax
  float *v8; // rax
  float *v9; // r13
  HDC v10; // rcx
  struct tagPOINT *v11; // rdi
  char *v12; // r14
  HLOCAL v13; // rsi
  char v14; // bp
  __int64 v15; // r8
  LPBYTE v16; // r10
  float x; // xmm0_4
  int v18; // eax
  char v19; // cl
  __int64 v20; // rdi
  __int64 v21; // rbx
  unsigned __int64 v22; // r15
  __int64 v23; // rcx
  int PathTypes; // eax
  __int64 v25; // r8
  LPBYTE v26; // r9
  char v27; // cl
  __int64 v29; // [rsp+40h] [rbp-68h] BYREF
  __int64 v30[11]; // [rsp+50h] [rbp-58h] BYREF
  LPBYTE v33; // [rsp+C8h] [rbp+20h] BYREF

  v4 = 0;
  Path = GetPath(*(HDC *)(a1 + 40), 0, 0, 0);
  v6 = Path;
  if ( Path != -1 )
  {
    if ( !Path )
      return 1;
    v33 = 0;
    v7 = 17LL * Path;
    if ( is_mul_ok(0x11u, v6) )
    {
      v8 = (float *)LocalAlloc(0, v7);
      v9 = v8;
      if ( v8 )
      {
        v10 = *(HDC *)(a1 + 40);
        v11 = (struct tagPOINT *)&v8[2 * v6];
        v12 = 0;
        v13 = 0;
        v33 = (LPBYTE)&v11[v6];
        if ( GetPath(v10, v11, v33, v6) != (_DWORD)v6
          || !pfnSetVirtualResolution && !(unsigned int)bXformWorkhorse(v11, (unsigned int)v6, a1 + 108) )
        {
          goto LABEL_39;
        }
        v14 = 0;
        v15 = 0;
        if ( (int)v6 > 0 )
        {
          v16 = v33;
          do
          {
            x = (float)v11[v15].x;
            v9[2 * v15 + 1] = (float)v11[v15].y;
            v9[2 * v15] = x;
            v18 = v16[v15] & 0xFE;
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
            if ( (v16[v15] & 1) == 0 )
              v14 = v19;
            v16[v15] = v14;
            v15 = (unsigned int)(v15 + 1);
          }
          while ( (int)v15 < (int)v6 );
        }
        Gdiplus::Matrix::Matrix(
          (Gdiplus::Matrix *)v30,
          *(float *)(a1 + 228),
          *(float *)(a1 + 232),
          *(float *)(a1 + 236),
          *(float *)(a1 + 240),
          *(float *)(a1 + 244),
          *(float *)(a1 + 248));
        v29 = 0;
        GdipCreatePath2((_DWORD)v9, (_DWORD)v33, v6, 0, (__int64)&v29);
        v20 = v30[0];
        v21 = v29;
        GdipFlattenPath(v29, v30[0]);
        LODWORD(v33) = 0;
        GdipGetPointCount(v21, &v33);
        v22 = (int)v33;
        if ( (int)v33 >= 0 )
        {
          v33 = 0;
          if ( !is_mul_ok(9u, v22) || (v12 = (char *)LocalAlloc(0, 9 * v22)) == 0 || (v33 = 0, !is_mul_ok(9u, v22)) )
          {
            GdipDeletePath(v21);
            GdipDeleteMatrix(v20);
            v4 = 0;
            goto LABEL_39;
          }
          v13 = LocalAlloc(0, 9 * v22);
          v23 = v21;
          if ( !v13
            || (v33 = (LPBYTE)&v12[8 * v22],
                PathTypes = GdipGetPathTypes(v21, v33, (unsigned int)v22),
                v23 = v21,
                PathTypes) )
          {
LABEL_21:
            GdipDeletePath(v23);
            GdipDeleteMatrix(v20);
LABEL_39:
            LocalFree(v9);
            if ( v12 )
              LocalFree(v12);
            if ( v13 )
              LocalFree(v13);
            return v4;
          }
          if ( !(unsigned int)GdipGetPathPoints(v21, v12, (unsigned int)v22) )
          {
            v25 = 0;
            if ( (int)v22 > 0 )
            {
              v26 = v33;
              do
              {
                *((_DWORD *)v13 + 2 * v25) = (int)(float)(*(float *)&v12[8 * v25] + 0.5);
                *((_DWORD *)v13 + 2 * v25 + 1) = (int)(float)(*(float *)&v12[8 * v25 + 4] + 0.5);
                if ( (v26[v25] & 0x7F) != 0 )
                {
                  if ( (v26[v25] & 0x7F) == 1 )
                    v14 = 2;
                }
                else
                {
                  v14 = 6;
                }
                v27 = v14 | 1;
                if ( (v26[v25] & 0x80u) == 0 )
                  v27 = v14;
                *((_BYTE *)v13 + 8 * v22 + v25) = v27;
                v14 = v27;
                v25 = (unsigned int)(v25 + 1);
              }
              while ( (int)v25 < (int)v22 );
            }
            GdipDeletePath(v21);
            GdipDeleteMatrix(v20);
            *a2 = v13;
            v13 = 0;
            v4 = 1;
            *a3 = v22;
            goto LABEL_39;
          }
        }
        v23 = v21;
        goto LABEL_21;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800af12c  mov     [rsp+arg_10], r8
0x1800af131  mov     [rsp+arg_8], rdx
0x1800af136  push    rbx
0x1800af137  push    rbp
0x1800af138  push    rsi
0x1800af139  push    rdi
0x1800af13a  push    r12
0x1800af13c  push    r13
0x1800af13e  push    r14
0x1800af140  push    r15
0x1800af142  sub     rsp, 68h
0x1800af146  mov     r15, rcx
0x1800af149  xor     r9d, r9d; cpt
0x1800af14c  mov     rcx, [rcx+28h]; hdc
0x1800af150  xor     r8d, r8d; aj
0x1800af153  xor     edx, edx; apt
0x1800af155  xor     r12d, r12d
0x1800af158  call    cs:__imp_GetPath
0x1800af15e  movsxd  rbx, eax
0x1800af161  cmp     ebx, 0FFFFFFFFh
0x1800af164  jz      loc_1800AF4C0
0x1800af16a  test    eax, eax
0x1800af16c  jnz     short loc_1800AF177
0x1800af16e  lea     r12d, [rax+1]
0x1800af172  jmp     loc_1800AF4C0
0x1800af177  mov     ecx, 11h
0x1800af17c  mov     [rsp+0A8h+arg_18], r12
0x1800af184  mov     rax, rbx
0x1800af187  mul     rcx
0x1800af18a  test    rdx, rdx
0x1800af18d  jnz     loc_1800AF4C0
0x1800af193  mov     rdx, rax; uBytes
0x1800af196  xor     ecx, ecx; uFlags
0x1800af198  call    cs:__imp_LocalAlloc
0x1800af19e  mov     r13, rax
0x1800af1a1  test    rax, rax
0x1800af1a4  jz      loc_1800AF4C0
0x1800af1aa  mov     rcx, [r15+28h]; hdc
0x1800af1ae  lea     rdi, ds:0[rbx*8]
0x1800af1b6  add     rdi, rax
0x1800af1b9  mov     r9d, ebx; cpt
0x1800af1bc  mov     rdx, rdi; apt
0x1800af1bf  xor     r14d, r14d
0x1800af1c2  xor     esi, esi
0x1800af1c4  lea     rax, [rdi+rbx*8]
0x1800af1c8  mov     r8, rax; aj
0x1800af1cb  mov     [rsp+0A8h+arg_18], rax
0x1800af1d3  call    cs:__imp_GetPath
0x1800af1d9  cmp     eax, ebx
0x1800af1db  jnz     loc_1800AF49B
0x1800af1e1  cmp     cs:pfnSetVirtualResolution, rsi
0x1800af1e8  jnz     short loc_1800AF200
0x1800af1ea  lea     r8, [r15+6Ch]
0x1800af1ee  mov     edx, ebx
0x1800af1f0  mov     rcx, rdi
0x1800af1f3  call    bXformWorkhorse
0x1800af1f8  test    eax, eax
0x1800af1fa  jz      loc_1800AF49B
0x1800af200  xor     bpl, bpl
0x1800af203  xor     r8d, r8d
0x1800af206  test    ebx, ebx
0x1800af208  jle     short loc_1800AF273
0x1800af20a  mov     r10, [rsp+0A8h+arg_18]
0x1800af212  movd    xmm1, dword ptr [rdi+r8*8+4]
0x1800af219  movd    xmm0, dword ptr [rdi+r8*8]
0x1800af21f  cvtdq2ps xmm1, xmm1
0x1800af222  cvtdq2ps xmm0, xmm0
0x1800af225  movss   dword ptr [r13+r8*8+4], xmm1
0x1800af22c  movss   dword ptr [r13+r8*8+0], xmm0
0x1800af233  movzx   r9d, byte ptr [r8+r10]
0x1800af238  mov     eax, r9d
0x1800af23b  and     eax, 0FFFFFFFEh
0x1800af23e  cmp     eax, 2
0x1800af241  jz      short loc_1800AF254
0x1800af243  cmp     eax, 4
0x1800af246  jz      short loc_1800AF250
0x1800af248  cmp     eax, 6
0x1800af24b  setnz   cl
0x1800af24e  jmp     short loc_1800AF256
0x1800af250  mov     cl, 3
0x1800af252  jmp     short loc_1800AF256
0x1800af254  mov     cl, 1
0x1800af256  mov     al, cl
0x1800af258  or      al, 80h
0x1800af25a  movzx   ebp, al
0x1800af25d  test    r9b, 1
0x1800af261  movzx   eax, cl
0x1800af264  cmovz   ebp, eax
0x1800af267  mov     [r8+r10], bpl
0x1800af26b  inc     r8d
0x1800af26e  cmp     r8d, ebx
0x1800af271  jl      short loc_1800AF212
0x1800af273  movss   xmm0, dword ptr [r15+0F8h]
0x1800af27c  lea     rcx, [rsp+0A8h+var_58]; this
0x1800af281  movss   xmm1, dword ptr [r15+0F4h]
0x1800af28a  movss   xmm3, dword ptr [r15+0ECh]; float
0x1800af293  movss   xmm2, dword ptr [r15+0E8h]; float
0x1800af29c  movss   [rsp+0A8h+var_78], xmm0; float
0x1800af2a2  movss   xmm0, dword ptr [r15+0F0h]
0x1800af2ab  movss   [rsp+0A8h+var_80], xmm1; float
0x1800af2b1  movss   xmm1, dword ptr [r15+0E4h]; float
0x1800af2ba  movss   [rsp+0A8h+var_88], xmm0; float
0x1800af2c0  call    ??0Matrix@Gdiplus@@QEAA@MMMMMM@Z; Gdiplus::Matrix::Matrix(float,float,float,float,float,float)
0x1800af2c5  mov     rdx, [rsp+0A8h+arg_18]
0x1800af2cd  lea     rax, [rsp+0A8h+var_68]
0x1800af2d2  xor     r9d, r9d
0x1800af2d5  mov     qword ptr [rsp+0A8h+var_88], rax
0x1800af2da  mov     r8d, ebx
0x1800af2dd  mov     [rsp+0A8h+var_68], rsi
0x1800af2e2  mov     rcx, r13
0x1800af2e5  call    GdipCreatePath2
0x1800af2ea  mov     rdi, [rsp+0A8h+var_58]
0x1800af2ef  mov     rbx, [rsp+0A8h+var_68]
0x1800af2f4  mov     rdx, rdi
0x1800af2f7  movss   xmm2, cs:__real@3e2aaaab
0x1800af2ff  mov     rcx, rbx
0x1800af302  call    GdipFlattenPath
0x1800af307  lea     rdx, [rsp+0A8h+arg_18]
0x1800af30f  mov     dword ptr [rsp+0A8h+arg_18], esi
0x1800af316  mov     rcx, rbx
0x1800af319  call    GdipGetPointCount
0x1800af31e  movsxd  r15, dword ptr [rsp+0A8h+arg_18]
0x1800af326  test    r15d, r15d
0x1800af329  jns     short loc_1800AF340
0x1800af32b  mov     rcx, rbx
0x1800af32e  call    GdipDeletePath
0x1800af333  mov     rcx, rdi
0x1800af336  call    GdipDeleteMatrix
0x1800af33b  jmp     loc_1800AF49B
0x1800af340  mov     ecx, 9
0x1800af345  mov     [rsp+0A8h+arg_18], rsi
0x1800af34d  mov     rax, r15
0x1800af350  mul     rcx
0x1800af353  test    rdx, rdx
0x1800af356  jnz     loc_1800AF488
0x1800af35c  mov     rdx, rax; uBytes
0x1800af35f  xor     ecx, ecx; uFlags
0x1800af361  call    cs:__imp_LocalAlloc
0x1800af367  mov     r14, rax
0x1800af36a  test    rax, rax
0x1800af36d  jz      loc_1800AF488
0x1800af373  mov     rax, r15
0x1800af376  mov     [rsp+0A8h+arg_18], rsi
0x1800af37e  mov     ecx, 9
0x1800af383  mul     rcx
0x1800af386  test    rdx, rdx
0x1800af389  jnz     loc_1800AF488
0x1800af38f  mov     rdx, rax; uBytes
0x1800af392  xor     ecx, ecx; uFlags
0x1800af394  call    cs:__imp_LocalAlloc
0x1800af39a  mov     rsi, rax
0x1800af39d  mov     rcx, rbx
0x1800af3a0  test    rax, rax
0x1800af3a3  jz      short loc_1800AF32E
0x1800af3a5  lea     rax, [r14+r15*8]
0x1800af3a9  mov     r8d, r15d
0x1800af3ac  mov     rdx, rax
0x1800af3af  mov     [rsp+0A8h+arg_18], rax
0x1800af3b7  call    GdipGetPathTypes
0x1800af3bc  mov     rcx, rbx
0x1800af3bf  test    eax, eax
0x1800af3c1  jnz     loc_1800AF32E
0x1800af3c7  mov     r8d, r15d
0x1800af3ca  mov     rdx, r14
0x1800af3cd  call    GdipGetPathPoints
0x1800af3d2  test    eax, eax
0x1800af3d4  jnz     loc_1800AF32B
0x1800af3da  xor     r8d, r8d
0x1800af3dd  lea     r11, [rsi+r15*8]
0x1800af3e1  test    r15d, r15d
0x1800af3e4  jle     short loc_1800AF45A
0x1800af3e6  movss   xmm2, cs:__real@3f000000
0x1800af3ee  mov     r9, [rsp+0A8h+arg_18]
0x1800af3f6  movss   xmm0, dword ptr [r14+r8*8]
0x1800af3fc  addss   xmm0, xmm2
0x1800af400  cvttss2si eax, xmm0
0x1800af404  mov     [rsi+r8*8], eax
0x1800af408  movss   xmm1, dword ptr [r14+r8*8+4]
0x1800af40f  addss   xmm1, xmm2
0x1800af413  cvttss2si eax, xmm1
0x1800af417  mov     [rsi+r8*8+4], eax
0x1800af41c  movzx   r10d, byte ptr [r8+r9]
0x1800af421  mov     ecx, r10d
0x1800af424  and     ecx, 0FFFFFF7Fh
0x1800af42a  jz      short loc_1800AF436
0x1800af42c  cmp     ecx, 1
0x1800af42f  jnz     short loc_1800AF439
0x1800af431  mov     bpl, 2
0x1800af434  jmp     short loc_1800AF439
0x1800af436  mov     bpl, 6
0x1800af439  mov     al, bpl
0x1800af43c  or      al, 1
0x1800af43e  movzx   ecx, al
0x1800af441  test    r10b, r10b
0x1800af444  movzx   eax, bpl
0x1800af448  cmovns  ecx, eax
0x1800af44b  mov     [r8+r11], cl
0x1800af44f  mov     bpl, cl
0x1800af452  inc     r8d
0x1800af455  cmp     r8d, r15d
0x1800af458  jl      short loc_1800AF3F6
0x1800af45a  mov     rcx, rbx
0x1800af45d  call    GdipDeletePath
0x1800af462  mov     rcx, rdi
0x1800af465  call    GdipDeleteMatrix
0x1800af46a  mov     rax, [rsp+0A8h+arg_8]
0x1800af472  mov     [rax], rsi
0x1800af475  xor     esi, esi
0x1800af477  mov     rax, [rsp+0A8h+arg_10]
0x1800af47f  lea     r12d, [rsi+1]
0x1800af483  mov     [rax], r15d
0x1800af486  jmp     short loc_1800AF49B
0x1800af488  mov     rcx, rbx
0x1800af48b  call    GdipDeletePath
0x1800af490  mov     rcx, rdi
0x1800af493  call    GdipDeleteMatrix
0x1800af498  mov     r12d, esi
0x1800af49b  mov     rcx, r13; hMem
0x1800af49e  call    cs:__imp_LocalFree
0x1800af4a4  test    r14, r14
0x1800af4a7  jz      short loc_1800AF4B2
0x1800af4a9  mov     rcx, r14; hMem
0x1800af4ac  call    cs:__imp_LocalFree
0x1800af4b2  test    rsi, rsi
0x1800af4b5  jz      short loc_1800AF4C0
0x1800af4b7  mov     rcx, rsi; hMem
0x1800af4ba  call    cs:__imp_LocalFree
0x1800af4c0  mov     eax, r12d
0x1800af4c3  add     rsp, 68h
0x1800af4c7  pop     r15
0x1800af4c9  pop     r14
0x1800af4cb  pop     r13
0x1800af4cd  pop     r12
0x1800af4cf  pop     rdi
0x1800af4d0  pop     rsi
0x1800af4d1  pop     rbp
0x1800af4d2  pop     rbx
0x1800af4d3  retn
```
