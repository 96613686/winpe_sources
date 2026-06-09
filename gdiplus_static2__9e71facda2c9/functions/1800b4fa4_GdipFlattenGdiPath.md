# GdipFlattenGdiPath

- ea: `0x1800b4fa4`
- end: `0x1800b5381`
- name: `GdipFlattenGdiPath`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18014b6c0`

## callees

- `0x180018c90`
- `0x1800b4fa4`
- `0x1800b5390`
- `0x1800b54c0`
- `0x1800b5664`
- `0x1800b56f0`
- `0x1800b5880`
- `0x1800b5a10`
- `0x1800b5b90`
- `0x1800c790c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5016`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b51eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5224`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5016`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b51eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5338`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b534c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5360`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5338`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b534c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5360`
- `GDI32!GetPath` at `0x1800b4fd0`
- `GDI32!GetPath` at `0x1800b5057`
- `GDI32!GetPath` at `0x1800b4fd0`
- `GDI32!GetPath` at `0x1800b5057`

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
0x1800b4fa4  mov     [rsp+arg_10], r8
0x1800b4fa9  mov     [rsp+arg_8], rdx
0x1800b4fae  push    rbx
0x1800b4faf  push    rbp
0x1800b4fb0  push    rsi
0x1800b4fb1  push    rdi
0x1800b4fb2  push    r12
0x1800b4fb4  push    r13
0x1800b4fb6  push    r14
0x1800b4fb8  push    r15
0x1800b4fba  sub     rsp, 68h
0x1800b4fbe  mov     r15, rcx
0x1800b4fc1  xor     r9d, r9d; cpt
0x1800b4fc4  mov     rcx, [rcx+28h]; hdc
0x1800b4fc8  xor     r8d, r8d; aj
0x1800b4fcb  xor     edx, edx; apt
0x1800b4fcd  xor     r12d, r12d
0x1800b4fd0  call    cs:__imp_GetPath
0x1800b4fd7  nop     dword ptr [rax+rax+00h]
0x1800b4fdc  movsxd  rbx, eax
0x1800b4fdf  cmp     ebx, 0FFFFFFFFh
0x1800b4fe2  jz      loc_1800B536C
0x1800b4fe8  test    eax, eax
0x1800b4fea  jnz     short loc_1800B4FF5
0x1800b4fec  lea     r12d, [rax+1]
0x1800b4ff0  jmp     loc_1800B536C
0x1800b4ff5  mov     ecx, 11h
0x1800b4ffa  mov     [rsp+0A8h+arg_18], r12
0x1800b5002  mov     rax, rbx
0x1800b5005  mul     rcx
0x1800b5008  test    rdx, rdx
0x1800b500b  jnz     loc_1800B536C
0x1800b5011  mov     rdx, rax; uBytes
0x1800b5014  xor     ecx, ecx; uFlags
0x1800b5016  call    cs:__imp_LocalAlloc
0x1800b501d  nop     dword ptr [rax+rax+00h]
0x1800b5022  mov     r13, rax
0x1800b5025  test    rax, rax
0x1800b5028  jz      loc_1800B536C
0x1800b502e  mov     rcx, [r15+28h]; hdc
0x1800b5032  lea     rdi, ds:0[rbx*8]
0x1800b503a  add     rdi, rax
0x1800b503d  mov     r9d, ebx; cpt
0x1800b5040  mov     rdx, rdi; apt
0x1800b5043  xor     r14d, r14d
0x1800b5046  xor     esi, esi
0x1800b5048  lea     rax, [rdi+rbx*8]
0x1800b504c  mov     r8, rax; aj
0x1800b504f  mov     [rsp+0A8h+arg_18], rax
0x1800b5057  call    cs:__imp_GetPath
0x1800b505e  nop     dword ptr [rax+rax+00h]
0x1800b5063  cmp     eax, ebx
0x1800b5065  jnz     loc_1800B5335
0x1800b506b  cmp     cs:pfnSetVirtualResolution, rsi
0x1800b5072  jnz     short loc_1800B508A
0x1800b5074  lea     r8, [r15+6Ch]
0x1800b5078  mov     edx, ebx
0x1800b507a  mov     rcx, rdi
0x1800b507d  call    bXformWorkhorse
0x1800b5082  test    eax, eax
0x1800b5084  jz      loc_1800B5335
0x1800b508a  xor     bpl, bpl
0x1800b508d  xor     r8d, r8d
0x1800b5090  test    ebx, ebx
0x1800b5092  jle     short loc_1800B50FD
0x1800b5094  mov     r10, [rsp+0A8h+arg_18]
0x1800b509c  movd    xmm1, dword ptr [rdi+r8*8+4]
0x1800b50a3  movd    xmm0, dword ptr [rdi+r8*8]
0x1800b50a9  cvtdq2ps xmm1, xmm1
0x1800b50ac  cvtdq2ps xmm0, xmm0
0x1800b50af  movss   dword ptr [r13+r8*8+4], xmm1
0x1800b50b6  movss   dword ptr [r13+r8*8+0], xmm0
0x1800b50bd  movzx   r9d, byte ptr [r8+r10]
0x1800b50c2  mov     eax, r9d
0x1800b50c5  and     eax, 0FFFFFFFEh
0x1800b50c8  cmp     eax, 2
0x1800b50cb  jz      short loc_1800B50DE
0x1800b50cd  cmp     eax, 4
0x1800b50d0  jz      short loc_1800B50DA
0x1800b50d2  cmp     eax, 6
0x1800b50d5  setnz   cl
0x1800b50d8  jmp     short loc_1800B50E0
0x1800b50da  mov     cl, 3
0x1800b50dc  jmp     short loc_1800B50E0
0x1800b50de  mov     cl, 1
0x1800b50e0  mov     al, cl
0x1800b50e2  or      al, 80h
0x1800b50e4  movzx   ebp, al
0x1800b50e7  test    r9b, 1
0x1800b50eb  movzx   eax, cl
0x1800b50ee  cmovz   ebp, eax
0x1800b50f1  mov     [r8+r10], bpl
0x1800b50f5  inc     r8d
0x1800b50f8  cmp     r8d, ebx
0x1800b50fb  jl      short loc_1800B509C
0x1800b50fd  movss   xmm0, dword ptr [r15+0F8h]
0x1800b5106  lea     rcx, [rsp+0A8h+var_58]; this
0x1800b510b  movss   xmm1, dword ptr [r15+0F4h]
0x1800b5114  movss   xmm3, dword ptr [r15+0ECh]; float
0x1800b511d  movss   xmm2, dword ptr [r15+0E8h]; float
0x1800b5126  movss   [rsp+0A8h+var_78], xmm0; float
0x1800b512c  movss   xmm0, dword ptr [r15+0F0h]
0x1800b5135  movss   [rsp+0A8h+var_80], xmm1; float
0x1800b513b  movss   xmm1, dword ptr [r15+0E4h]; float
0x1800b5144  movss   [rsp+0A8h+var_88], xmm0; float
0x1800b514a  call    ??0Matrix@Gdiplus@@QEAA@MMMMMM@Z; Gdiplus::Matrix::Matrix(float,float,float,float,float,float)
0x1800b514f  mov     rdx, [rsp+0A8h+arg_18]
0x1800b5157  lea     rax, [rsp+0A8h+var_68]
0x1800b515c  xor     r9d, r9d
0x1800b515f  mov     qword ptr [rsp+0A8h+var_88], rax
0x1800b5164  mov     r8d, ebx
0x1800b5167  mov     [rsp+0A8h+var_68], rsi
0x1800b516c  mov     rcx, r13
0x1800b516f  call    GdipCreatePath2
0x1800b5174  mov     rdi, [rsp+0A8h+var_58]
0x1800b5179  mov     rbx, [rsp+0A8h+var_68]
0x1800b517e  mov     rdx, rdi
0x1800b5181  movss   xmm2, cs:__real@3e2aaaab
0x1800b5189  mov     rcx, rbx
0x1800b518c  call    GdipFlattenPath
0x1800b5191  lea     rdx, [rsp+0A8h+arg_18]
0x1800b5199  mov     dword ptr [rsp+0A8h+arg_18], esi
0x1800b51a0  mov     rcx, rbx
0x1800b51a3  call    GdipGetPointCount
0x1800b51a8  movsxd  r15, dword ptr [rsp+0A8h+arg_18]
0x1800b51b0  test    r15d, r15d
0x1800b51b3  jns     short loc_1800B51CA
0x1800b51b5  mov     rcx, rbx
0x1800b51b8  call    GdipDeletePath
0x1800b51bd  mov     rcx, rdi
0x1800b51c0  call    GdipDeleteMatrix
0x1800b51c5  jmp     loc_1800B5335
0x1800b51ca  mov     ecx, 9
0x1800b51cf  mov     [rsp+0A8h+arg_18], rsi
0x1800b51d7  mov     rax, r15
0x1800b51da  mul     rcx
0x1800b51dd  test    rdx, rdx
0x1800b51e0  jnz     loc_1800B5322
0x1800b51e6  mov     rdx, rax; uBytes
0x1800b51e9  xor     ecx, ecx; uFlags
0x1800b51eb  call    cs:__imp_LocalAlloc
0x1800b51f2  nop     dword ptr [rax+rax+00h]
0x1800b51f7  mov     r14, rax
0x1800b51fa  test    rax, rax
0x1800b51fd  jz      loc_1800B5322
0x1800b5203  mov     rax, r15
0x1800b5206  mov     [rsp+0A8h+arg_18], rsi
0x1800b520e  mov     ecx, 9
0x1800b5213  mul     rcx
0x1800b5216  test    rdx, rdx
0x1800b5219  jnz     loc_1800B5322
0x1800b521f  mov     rdx, rax; uBytes
0x1800b5222  xor     ecx, ecx; uFlags
0x1800b5224  call    cs:__imp_LocalAlloc
0x1800b522b  nop     dword ptr [rax+rax+00h]
0x1800b5230  mov     rsi, rax
0x1800b5233  mov     rcx, rbx
0x1800b5236  test    rax, rax
0x1800b5239  jz      loc_1800B51B8
0x1800b523f  lea     rax, [r14+r15*8]
0x1800b5243  mov     r8d, r15d
0x1800b5246  mov     rdx, rax
0x1800b5249  mov     [rsp+0A8h+arg_18], rax
0x1800b5251  call    GdipGetPathTypes
0x1800b5256  mov     rcx, rbx
0x1800b5259  test    eax, eax
0x1800b525b  jnz     loc_1800B51B8
0x1800b5261  mov     r8d, r15d
0x1800b5264  mov     rdx, r14
0x1800b5267  call    GdipGetPathPoints
0x1800b526c  test    eax, eax
0x1800b526e  jnz     loc_1800B51B5
0x1800b5274  xor     r8d, r8d
0x1800b5277  lea     r11, [rsi+r15*8]
0x1800b527b  test    r15d, r15d
0x1800b527e  jle     short loc_1800B52F4
0x1800b5280  movss   xmm2, cs:__real@3f000000
0x1800b5288  mov     r9, [rsp+0A8h+arg_18]
0x1800b5290  movss   xmm0, dword ptr [r14+r8*8]
0x1800b5296  addss   xmm0, xmm2
0x1800b529a  cvttss2si eax, xmm0
0x1800b529e  mov     [rsi+r8*8], eax
0x1800b52a2  movss   xmm1, dword ptr [r14+r8*8+4]
0x1800b52a9  addss   xmm1, xmm2
0x1800b52ad  cvttss2si eax, xmm1
0x1800b52b1  mov     [rsi+r8*8+4], eax
0x1800b52b6  movzx   r10d, byte ptr [r8+r9]
0x1800b52bb  mov     ecx, r10d
0x1800b52be  and     ecx, 0FFFFFF7Fh
0x1800b52c4  jz      short loc_1800B52D0
0x1800b52c6  cmp     ecx, 1
0x1800b52c9  jnz     short loc_1800B52D3
0x1800b52cb  mov     bpl, 2
0x1800b52ce  jmp     short loc_1800B52D3
0x1800b52d0  mov     bpl, 6
0x1800b52d3  mov     al, bpl
0x1800b52d6  or      al, 1
0x1800b52d8  movzx   ecx, al
0x1800b52db  test    r10b, r10b
0x1800b52de  movzx   eax, bpl
0x1800b52e2  cmovns  ecx, eax
0x1800b52e5  mov     [r8+r11], cl
0x1800b52e9  mov     bpl, cl
0x1800b52ec  inc     r8d
0x1800b52ef  cmp     r8d, r15d
0x1800b52f2  jl      short loc_1800B5290
0x1800b52f4  mov     rcx, rbx
0x1800b52f7  call    GdipDeletePath
0x1800b52fc  mov     rcx, rdi
0x1800b52ff  call    GdipDeleteMatrix
0x1800b5304  mov     rax, [rsp+0A8h+arg_8]
0x1800b530c  mov     [rax], rsi
0x1800b530f  xor     esi, esi
0x1800b5311  mov     rax, [rsp+0A8h+arg_10]
0x1800b5319  lea     r12d, [rsi+1]
0x1800b531d  mov     [rax], r15d
0x1800b5320  jmp     short loc_1800B5335
0x1800b5322  mov     rcx, rbx
0x1800b5325  call    GdipDeletePath
0x1800b532a  mov     rcx, rdi
0x1800b532d  call    GdipDeleteMatrix
0x1800b5332  mov     r12d, esi
0x1800b5335  mov     rcx, r13; hMem
0x1800b5338  call    cs:__imp_LocalFree
0x1800b533f  nop     dword ptr [rax+rax+00h]
0x1800b5344  test    r14, r14
0x1800b5347  jz      short loc_1800B5358
0x1800b5349  mov     rcx, r14; hMem
0x1800b534c  call    cs:__imp_LocalFree
0x1800b5353  nop     dword ptr [rax+rax+00h]
0x1800b5358  test    rsi, rsi
0x1800b535b  jz      short loc_1800B536C
0x1800b535d  mov     rcx, rsi; hMem
0x1800b5360  call    cs:__imp_LocalFree
0x1800b5367  nop     dword ptr [rax+rax+00h]
0x1800b536c  mov     eax, r12d
0x1800b536f  add     rsp, 68h
0x1800b5373  pop     r15
0x1800b5375  pop     r14
0x1800b5377  pop     r13
0x1800b5379  pop     r12
0x1800b537b  pop     rdi
0x1800b537c  pop     rsi
0x1800b537d  pop     rbp
0x1800b537e  pop     rbx
0x1800b537f  retn
```
