# CTouchHandleAnimationController::_GetPVLTransformInfo(int,int,int *,CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO * *)

- ea: `0x1802047e4`
- end: `0x180204a39`
- name: `?_GetPVLTransformInfo@CTouchHandleAnimationController@@AEAAJHHPEAHPEAPEAUOPACITY_TRANSFORM_INFO@1@@Z`
- size: `597`
- prototype: `int(CTouchHandleAnimationController *__hidden this, int, int, int *, struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180204c4c`

## callees

- `0x18013d250`
- `0x18013d5bc`
- `0x1802047e4`
- `0x180204a40`
- `0x180204b6c`

## import_xrefs

- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationProperty` at `0x180204891`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationProperty` at `0x180204891`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x180204827`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18020484a`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x180204827`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18020484a`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x1802049df`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x1802049fc`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x1802049df`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x1802049fc`

## pseudocode

```c
__int64 __fastcall CTouchHandleAnimationController::_GetPVLTransformInfo(
        CTouchHandleAnimationController *this,
        unsigned int a2,
        int a3,
        int *a4,
        struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **a5)
{
  struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **v5; // rsi
  unsigned int v6; // r14d
  HTHEME v7; // r12
  char *v8; // rdi
  HTHEME v9; // r13
  int ThemeAnimationProperty; // ebx
  unsigned __int64 v11; // rax
  CTouchHandleAnimationController *v12; // rcx
  int v13; // r9d
  int v14; // r15d
  struct TA_TRANSFORM *v15; // rsi
  struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO *v16; // r14
  int *v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  struct TA_TRANSFORM *v22; // [rsp+40h] [rbp-18h] BYREF
  struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO *v23; // [rsp+48h] [rbp-10h] BYREF
  CTouchHandleAnimationController *v24; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+50h]
  int v26; // [rsp+B0h] [rbp+58h] BYREF
  int *v27; // [rsp+B8h] [rbp+60h]

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v24 = this;
  v5 = a5;
  v6 = a2;
  *a4 = 0;
  *v5 = 0;
  v7 = OpenThemeData(0, L"Animations");
  if ( v7 )
  {
    v8 = 0;
    v9 = OpenThemeData(0, L"timingfunction");
    if ( v9 )
    {
      v26 = 0;
      LODWORD(v24) = 0;
      ThemeAnimationProperty = GetThemeAnimationProperty(v7, v6, 1, 1, &v26, 4, &v24);
      if ( ThemeAnimationProperty >= 0 )
      {
        v11 = 32LL * (unsigned int)v26;
        if ( !is_mul_ok((unsigned int)v26, 0x20u) )
          v11 = -1;
        v8 = (char *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
        if ( v8 )
        {
          ThemeAnimationProperty = 0;
          v14 = 0;
          if ( v26 > 0 )
          {
            do
            {
              if ( ThemeAnimationProperty < 0 )
                break;
              v22 = 0;
              ThemeAnimationProperty = CTouchHandleAnimationController::_RetrieveTransform(v12, v7, v6, v13, v14, &v22);
              if ( ThemeAnimationProperty >= 0 )
              {
                v15 = v22;
                v23 = 0;
                ThemeAnimationProperty = CTouchHandleAnimationController::_RetrieveTimingCurve(
                                           v12,
                                           v9,
                                           *((_DWORD *)v22 + 1),
                                           &v23);
                if ( ThemeAnimationProperty >= 0 )
                {
                  v16 = v23;
                  *(_DWORD *)v23 = *(_DWORD *)v15;
                  *((float *)v16 + 2) = (float)*((int *)v15 + 3);
                  *((float *)v16 + 1) = (float)*((int *)v15 + 2) * 0.001;
                  *((float *)v16 + 2) = *((float *)v16 + 2) * 0.001;
                  if ( *(_DWORD *)v15 == 2 )
                    *((_DWORD *)v16 + 3) = *((_DWORD *)v15 + 5);
                  v17 = v27;
                  v18 = *v27;
                  v19 = 32 * v18;
                  *(_OWORD *)&v8[v19] = *(_OWORD *)v16;
                  *(_OWORD *)&v8[v19 + 16] = *((_OWORD *)v16 + 1);
                  *v17 = v18 + 1;
                  operator delete(v15, v18);
                  operator delete(v16, 0x20u);
                  v6 = v25;
                }
              }
              ++v14;
            }
            while ( v14 < v26 );
            v5 = a5;
          }
        }
        else
        {
          ThemeAnimationProperty = -2147024882;
        }
      }
      CloseThemeData(v9);
    }
    else
    {
      ThemeAnimationProperty = -2147467259;
    }
    CloseThemeData(v7);
    if ( ThemeAnimationProperty < 0 )
    {
      if ( v8 )
        operator delete(v8, v20);
    }
    else
    {
      *v5 = (struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO *)v8;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)ThemeAnimationProperty;
}

```

## disassembly

```asm
0x1802047e4  mov     rax, rsp
0x1802047e7  mov     [rax+20h], r9
0x1802047eb  mov     [rax+18h], r8d
0x1802047ef  mov     [rax+10h], edx
0x1802047f2  mov     [rax+8], rcx
0x1802047f6  push    rbp
0x1802047f7  push    rbx
0x1802047f8  push    rsi
0x1802047f9  push    rdi
0x1802047fa  push    r12
0x1802047fc  push    r13
0x1802047fe  push    r14
0x180204800  push    r15
0x180204802  mov     rbp, rsp
0x180204805  sub     rsp, 58h
0x180204809  mov     rsi, [rbp+arg_20]
0x18020480d  mov     r14d, edx
0x180204810  lea     rdx, aAnimations; "Animations"
0x180204817  mov     dword ptr [r9], 0
0x18020481e  xor     ecx, ecx; hwnd
0x180204820  mov     qword ptr [rsi], 0
0x180204827  call    cs:__imp_OpenThemeData
0x18020482e  nop     dword ptr [rax+rax+00h]
0x180204833  mov     r12, rax
0x180204836  test    rax, rax
0x180204839  jz      loc_180204A20
0x18020483f  lea     rdx, aTimingfunction; "timingfunction"
0x180204846  xor     ecx, ecx; hwnd
0x180204848  xor     edi, edi
0x18020484a  call    cs:__imp_OpenThemeData
0x180204851  nop     dword ptr [rax+rax+00h]
0x180204856  mov     r13, rax
0x180204859  test    rax, rax
0x18020485c  jz      loc_1802049F4
0x180204862  lea     rax, [rbp+arg_0]
0x180204866  mov     [rbp+arg_10], edi
0x180204869  mov     [rsp+58h+var_28], rax
0x18020486e  mov     edx, r14d
0x180204871  lea     rax, [rbp+arg_10]
0x180204875  mov     dword ptr [rsp+58h+var_30], 4
0x18020487d  mov     qword ptr [rsp+58h+var_38], rax
0x180204882  mov     rcx, r12
0x180204885  lea     eax, [rdi+1]
0x180204888  mov     dword ptr [rbp+arg_0], edi
0x18020488b  mov     r9d, eax
0x18020488e  mov     r8d, eax
0x180204891  call    cs:__imp_GetThemeAnimationProperty
0x180204898  nop     dword ptr [rax+rax+00h]
0x18020489d  mov     ebx, eax
0x18020489f  test    eax, eax
0x1802048a1  js      loc_1802049DC
0x1802048a7  mov     ecx, [rbp+arg_10]
0x1802048aa  lea     eax, [rdi+20h]
0x1802048ad  mul     rcx
0x1802048b0  lea     rcx, [rdi-1]
0x1802048b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802048bb  cmovb   rax, rcx
0x1802048bf  mov     rcx, rax; unsigned __int64
0x1802048c2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1802048c7  mov     rdi, rax
0x1802048ca  test    rax, rax
0x1802048cd  jz      loc_1802049ED
0x1802048d3  xor     ebx, ebx
0x1802048d5  xor     r15d, r15d
0x1802048d8  cmp     [rbp+arg_10], ebx
0x1802048db  jle     loc_1802049DC
0x1802048e1  test    ebx, ebx
0x1802048e3  js      loc_1802049D8
0x1802048e9  lea     rax, [rbp+var_18]
0x1802048ed  mov     [rbp+var_18], 0
0x1802048f5  mov     [rsp+58h+var_30], rax; struct TA_TRANSFORM **
0x1802048fa  mov     r8d, r14d; int
0x1802048fd  mov     rdx, r12; void *
0x180204900  mov     [rsp+58h+var_38], r15d; int
0x180204905  call    ?_RetrieveTransform@CTouchHandleAnimationController@@AEAAJPEAXHHHPEAPEAUTA_TRANSFORM@@@Z; CTouchHandleAnimationController::_RetrieveTransform(void *,int,int,int,TA_TRANSFORM * *)
0x18020490a  mov     ebx, eax
0x18020490c  test    eax, eax
0x18020490e  js      loc_1802049CB
0x180204914  mov     rsi, [rbp+var_18]
0x180204918  lea     r9, [rbp+var_10]; struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **
0x18020491c  mov     rdx, r13; void *
0x18020491f  mov     [rbp+var_10], 0
0x180204927  mov     r8d, [rsi+4]; unsigned int
0x18020492b  call    ?_RetrieveTimingCurve@CTouchHandleAnimationController@@AEAAJPEAXKPEAPEAUOPACITY_TRANSFORM_INFO@1@@Z; CTouchHandleAnimationController::_RetrieveTimingCurve(void *,ulong,CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO * *)
0x180204930  mov     ebx, eax
0x180204932  test    eax, eax
0x180204934  js      loc_1802049CB
0x18020493a  mov     r14, [rbp+var_10]
0x18020493e  xorps   xmm0, xmm0
0x180204941  mov     eax, [rsi]
0x180204943  xorps   xmm1, xmm1
0x180204946  mov     [r14], eax
0x180204949  mov     eax, [rsi+0Ch]
0x18020494c  cvtsi2ss xmm0, rax
0x180204951  movss   dword ptr [r14+8], xmm0
0x180204957  mov     eax, [rsi+8]
0x18020495a  cvtsi2ss xmm1, rax
0x18020495f  mulss   xmm1, cs:__real@3a83126f
0x180204967  movss   dword ptr [r14+4], xmm1
0x18020496d  movss   xmm0, dword ptr [r14+8]
0x180204973  mulss   xmm0, cs:__real@3a83126f
0x18020497b  movss   dword ptr [r14+8], xmm0
0x180204981  cmp     dword ptr [rsi], 2
0x180204984  jnz     short loc_18020498D
0x180204986  mov     eax, [rsi+14h]
0x180204989  mov     [r14+0Ch], eax
0x18020498d  mov     rcx, [rbp+arg_18]
0x180204991  movups  xmm0, xmmword ptr [r14]
0x180204995  movsxd  rdx, dword ptr [rcx]; unsigned __int64
0x180204998  mov     rax, rdx
0x18020499b  shl     rax, 5
0x18020499f  movups  xmmword ptr [rax+rdi], xmm0
0x1802049a3  movups  xmm1, xmmword ptr [r14+10h]
0x1802049a8  movups  xmmword ptr [rax+rdi+10h], xmm1
0x1802049ad  lea     eax, [rdx+1]
0x1802049b0  mov     [rcx], eax
0x1802049b2  mov     rcx, rsi; void *
0x1802049b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802049ba  mov     edx, 20h ; ' '; unsigned __int64
0x1802049bf  mov     rcx, r14; void *
0x1802049c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802049c7  mov     r14d, [rbp+arg_8]
0x1802049cb  inc     r15d
0x1802049ce  cmp     r15d, [rbp+arg_10]
0x1802049d2  jl      loc_1802048E1
0x1802049d8  mov     rsi, [rbp+arg_20]
0x1802049dc  mov     rcx, r13; hTheme
0x1802049df  call    cs:__imp_CloseThemeData
0x1802049e6  nop     dword ptr [rax+rax+00h]
0x1802049eb  jmp     short loc_1802049F9
0x1802049ed  mov     ebx, 8007000Eh
0x1802049f2  jmp     short loc_1802049DC
0x1802049f4  mov     ebx, 80004005h
0x1802049f9  mov     rcx, r12; hTheme
0x1802049fc  call    cs:__imp_CloseThemeData
0x180204a03  nop     dword ptr [rax+rax+00h]
0x180204a08  test    ebx, ebx
0x180204a0a  js      short loc_180204A11
0x180204a0c  mov     [rsi], rdi
0x180204a0f  jmp     short loc_180204A25
0x180204a11  test    rdi, rdi
0x180204a14  jz      short loc_180204A25
0x180204a16  mov     rcx, rdi; void *
0x180204a19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180204a1e  jmp     short loc_180204A25
0x180204a20  mov     ebx, 80004005h
0x180204a25  mov     eax, ebx
0x180204a27  add     rsp, 58h
0x180204a2b  pop     r15
0x180204a2d  pop     r14
0x180204a2f  pop     r13
0x180204a31  pop     r12
0x180204a33  pop     rdi
0x180204a34  pop     rsi
0x180204a35  pop     rbx
0x180204a36  pop     rbp
0x180204a37  retn
```
