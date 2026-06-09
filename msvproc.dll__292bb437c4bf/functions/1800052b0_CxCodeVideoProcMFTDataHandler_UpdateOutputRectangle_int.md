# CxCodeVideoProcMFTDataHandler::UpdateOutputRectangle(int)

- ea: `0x1800052b0`
- end: `0x180005c51`
- name: `?UpdateOutputRectangle@CxCodeVideoProcMFTDataHandler@@AEAAJH@Z`
- size: `2465`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180007148`

## callees

- `0x1800052b0`
- `0x180005d44`
- `0x180009470`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180023700`
- `0x1800364d0`
- `0x180054140`
- `0x180054ee4`
- `0x180059ad0`
- `0x180066f48`
- `0x180067058`
- `0x1800d1010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800053af`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800053af`

## string_xrefs

- `0x1800052e5`: `CxCodeVideoProcMFTDataHandler::UpdateOutputRectangle`
- `0x1800058f3`: `CxCodeVideoProcMFTDataHandler::UpdateOutputRectangle`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::UpdateOutputRectangle(CxCodeVideoProcMFTDataHandler *this, int a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  int v7; // edi
  struct tagRECT *v8; // rbx
  CxCodeVideoProcMFTDataHandler *v9; // rcx
  unsigned int ValidArea; // ebx
  unsigned __int64 v11; // rcx
  LONG v12; // r8d
  LONG v13; // r9d
  LONG v14; // r10d
  LONG right; // r15d
  LONG left; // edx
  LONG bottom; // r12d
  LONG top; // r8d
  int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // ecx
  unsigned int v22; // edi
  unsigned __int64 v23; // r13
  unsigned __int64 v24; // r15
  char v25; // r12
  unsigned int v26; // r8d
  unsigned __int64 v27; // kr00_8
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // kr10_8
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // kr40_8
  unsigned __int64 v33; // kr50_8
  unsigned __int64 v34; // rdi
  unsigned int v35; // ebx
  unsigned __int64 v36; // rax
  double v37; // xmm0_8
  double v38; // xmm1_8
  unsigned __int64 v39; // rdx
  unsigned int v40; // r9d
  unsigned int v41; // r9d
  unsigned __int64 v42; // rdi
  unsigned __int64 v43; // r14
  double v44; // xmm0_8
  double v45; // xmm1_8
  int v46; // ecx
  unsigned __int64 v47; // rax
  LONG v48; // eax
  CxCodeVideoProcMFTDataHandler *v49; // rcx
  LONG v50; // ecx
  LONG v51; // edx
  __int64 v52; // rax
  LONG v53; // edi
  LONG v54; // r14d
  int v55; // eax
  LONG v56; // r11d
  LONG v57; // ebx
  LONG v58; // r15d
  LONG v59; // r8d
  int v60; // ebx
  LONG v61; // r8d
  LONG v62; // r10d
  int v63; // edx
  LONG v64; // eax
  CxCodeVideoProcMFTDataHandler *v65; // rcx
  int v67; // [rsp+68h] [rbp-A0h] BYREF
  LONG v68; // [rsp+6Ch] [rbp-9Ch]
  LONG v69; // [rsp+70h] [rbp-98h]
  LONG v70; // [rsp+74h] [rbp-94h]
  LONG v71; // [rsp+78h] [rbp-90h]
  unsigned int v72; // [rsp+7Ch] [rbp-8Ch]
  unsigned int v73; // [rsp+80h] [rbp-88h]
  unsigned __int64 v74; // [rsp+88h] [rbp-80h] BYREF
  struct tagRECT v75; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v76[20]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v77; // [rsp+BCh] [rbp-4Ch]
  unsigned int v78; // [rsp+C0h] [rbp-48h]
  __int64 v79; // [rsp+E0h] [rbp-28h]
  struct tagRECT v80; // [rsp+F8h] [rbp-10h] BYREF

  v75 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v67,
    "CxCodeVideoProcMFTDataHandler::UpdateOutputRectangle",
    3965);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, struct tagRECT *))(**((_QWORD **)this + 388) + 280LL))(
                      *((_QWORD *)this + 388),
                      &v80);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v7 = 0;
  v70 = *((_DWORD *)this + 163);
  v71 = *((_DWORD *)this + 162);
  if ( a2 )
    LOBYTE(v7) = (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21)) < 40960;
  v8 = (struct tagRECT *)((char *)this + 632);
  if ( IsRectEmpty((const RECT *)((char *)this + 632)) )
  {
    v11 = *((_QWORD *)this + 102);
    v68 = 0;
    v69 = 0;
    if ( !v11 )
      v11 = *((_QWORD *)this + 103) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !v11 )
      goto LABEL_19;
    memset_0(v76, 0, 0x50u);
    ValidArea = CtypeSurfaces::Find(*((_DWORD *)this + 154), (struct TypeSurface *)v76);
    if ( ValidArea )
      goto LABEL_89;
    v9 = (CxCodeVideoProcMFTDataHandler *)(unsigned int)*((__int16 *)this + 409);
    v12 = *((__int16 *)this + 411);
    v13 = (_DWORD)v9 + *((_DWORD *)this + 206);
    v14 = v12 + *((_DWORD *)this + 207);
    v80.left = *((__int16 *)this + 409);
    v80.bottom = v14;
    v80.top = v12;
    v80.right = v13;
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qdddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        205,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        (_DWORD)v9,
        v13,
        v12,
        v14);
LABEL_17:
    ValidArea = CxCodeVideoProcMFTDataHandler::GetValidArea(
                  v9,
                  *((_DWORD *)this + 163),
                  *((_DWORD *)this + 162),
                  v77,
                  v78,
                  &v80,
                  v7,
                  1);
    if ( ValidArea )
      goto LABEL_89;
    right = v80.right;
    left = v80.left;
    bottom = v80.bottom;
    top = v80.top;
    *((_DWORD *)this + 173) = v80.right - v80.left;
    v71 = bottom;
    *((_DWORD *)this + 172) = bottom - top;
    v70 = right;
    v69 = top;
    v68 = left;
LABEL_19:
    v19 = *((_DWORD *)this + 388);
    v20 = *((_DWORD *)this + 65);
    v21 = *((_DWORD *)this + 64);
    v72 = v20;
    if ( v19 == 90 || v19 == 270 )
    {
      v22 = v20;
      v73 = v20;
      v20 = v21;
      v72 = v21;
    }
    else
    {
      v22 = v21;
      v73 = v21;
    }
    v23 = *((unsigned int *)this + 173);
    v24 = *((unsigned int *)this + 172);
    v25 = byte_180153DE0;
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    {
      WPP_SF_qdddddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        206,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        v23,
        v24,
        *((_DWORD *)this + 86) - *((_DWORD *)this + 84),
        *((_DWORD *)this + 87) - *((_DWORD *)this + 85),
        v22,
        v20,
        *((_DWORD *)this + 155),
        *((_DWORD *)this + 156));
      v25 = byte_180153DE0;
    }
    v26 = *((_DWORD *)this + 86) - *((_DWORD *)this + 84);
    v27 = (unsigned int)(*((_DWORD *)this + 87) - *((_DWORD *)this + 85));
    *(_QWORD *)&v80.left = 0;
    if ( !is_mul_ok(v20, v27) )
      goto LABEL_88;
    v29 = *((unsigned int *)this + 155);
    v28 = v29 * v20 * v27;
    *(_QWORD *)&v80.left = 0;
    if ( !is_mul_ok(v29, v20 * v27) )
      goto LABEL_88;
    *(_QWORD *)&v80.left = 0;
    v30 = v23 * v28;
    if ( !is_mul_ok(v23, v28)
      || (*(_QWORD *)&v80.left = 0, !is_mul_ok(v22, v26))
      || (v32 = *((unsigned int *)this + 156),
          v33 = v22 * (unsigned __int64)v26,
          v31 = v32 * v33,
          *(_QWORD *)&v80.left = 0,
          v34 = v32 * v33,
          !is_mul_ok(v32, v33)) )
    {
LABEL_88:
      ValidArea = -2147024362;
      goto LABEL_89;
    }
    if ( v31 )
    {
      v36 = v30 / v31;
      if ( v30 % v34 )
      {
        memset_0(v76, 0, 0x50u);
        ValidArea = CtypeSurfaces::Find(*((_DWORD *)this + 154), (struct TypeSurface *)v76);
        if ( ValidArea )
          goto LABEL_89;
        if ( (v30 & 0x8000000000000000uLL) != 0LL )
          v37 = (double)(int)(v30 & 1 | (v30 >> 1)) + (double)(int)(v30 & 1 | (v30 >> 1));
        else
          v37 = (double)(int)v30;
        if ( (v34 & 0x8000000000000000uLL) != 0LL )
          v38 = (double)(int)(v34 & 1 | (v34 >> 1)) + (double)(int)(v34 & 1 | (v34 >> 1));
        else
          v38 = (double)(int)v34;
        v35 = (int)((double)(1 << (v77 - 1)) * 0.5 + v37 / v38);
        if ( !v35 )
          v35 = 1;
      }
      else
      {
        if ( !(_DWORD)v36 )
          LODWORD(v36) = 1;
        v35 = v36;
      }
    }
    else
    {
      v35 = v24 + 1;
    }
    if ( (unsigned __int8)v25 >= 0x20u )
    {
      WPP_SF_qdddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        207,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        0,
        v23,
        ((unsigned int)v24 - v35) >> 1,
        (((unsigned int)v24 - v35) >> 1) + v35);
      v25 = byte_180153DE0;
    }
    if ( v35 > (unsigned int)v24 )
    {
      v39 = (unsigned int)(*((_DWORD *)this + 86) - *((_DWORD *)this + 84));
      v40 = *((_DWORD *)this + 87) - *((_DWORD *)this + 85);
      v74 = v39;
      *(_QWORD *)&v80.left = v40;
      ValidArea = ULongLongMult(v73, v39, &v74);
      if ( ValidArea )
        goto LABEL_89;
      ValidArea = ULongLongMult(*((unsigned int *)this + 156), v74, &v74);
      if ( ValidArea )
        goto LABEL_89;
      ValidArea = ULongLongMult(v24, v74, &v74);
      if ( ValidArea )
        goto LABEL_89;
      ValidArea = ULongLongMult(v72, v41, (unsigned __int64 *)&v80);
      if ( ValidArea )
        goto LABEL_89;
      ValidArea = ULongLongMult(*((unsigned int *)this + 155), *(unsigned __int64 *)&v80.left, (unsigned __int64 *)&v80);
      if ( ValidArea )
        goto LABEL_89;
      v42 = *(_QWORD *)&v80.left;
      if ( !*(_QWORD *)&v80.left )
      {
        if ( (unsigned __int8)v25 >= 0x20u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 208, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
        if ( (unsigned int)XvpOriginateError<20>(
                             "CxCodeVideoProcMFTDataHandler::UpdateOutputRectangle",
                             3222091451LL,
                             L"no valid area found") )
          goto LABEL_89;
        v25 = byte_180153DE0;
      }
      v43 = v74;
      if ( v74 % v42 )
      {
        memset_0(v76, 0, 0x50u);
        ValidArea = CtypeSurfaces::Find(*((_DWORD *)this + 154), (struct TypeSurface *)v76);
        if ( ValidArea )
          goto LABEL_89;
        if ( (v43 & 0x8000000000000000uLL) != 0LL )
          v44 = (double)(int)(v43 & 1 | (v43 >> 1)) + (double)(int)(v43 & 1 | (v43 >> 1));
        else
          v44 = (double)(int)v43;
        if ( (v42 & 0x8000000000000000uLL) != 0LL )
          v45 = (double)(int)(v42 & 1 | (v42 >> 1)) + (double)(int)(v42 & 1 | (v42 >> 1));
        else
          v45 = (double)(int)v42;
        v46 = (int)((double)(1 << (v78 - 1)) * 0.5 + v44 / v45);
        if ( !v46 )
          v46 = 1;
      }
      else
      {
        v47 = v74 / v42;
        if ( !(unsigned int)(v74 / v42) )
          LODWORD(v47) = 1;
        v46 = v47;
      }
      v75.top = 0;
      v75.bottom = v24;
      v48 = (unsigned int)(v23 - v46) >> 1;
      v75.left = v48;
      v75.right = v48 + v46;
      if ( (unsigned __int8)v25 >= 0x20u )
        WPP_SF_qdddd(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          209,
          &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
          this,
          v48,
          v48 + v46,
          0,
          v24);
    }
    else
    {
      v75.right = v23;
      v75.top = ((unsigned int)v24 - v35) >> 1;
      v75.bottom = v35 + v75.top;
    }
    memset_0(v76, 0, 0x50u);
    ValidArea = CtypeSurfaces::Find(*((_DWORD *)this + 154), (struct TypeSurface *)v76);
    if ( !ValidArea )
    {
      ValidArea = CxCodeVideoProcMFTDataHandler::GetValidArea(v49, v23, v24, v77, v78, &v75, 0, 1);
      if ( !ValidArea )
      {
        v50 = v75.right;
        v51 = v75.bottom;
        if ( v75.right == (_DWORD)v23 && v75.bottom == (_DWORD)v24 )
          v52 = 0;
        else
          v52 = v79;
        v53 = v75.left;
        v54 = v75.top;
        *((_QWORD *)this + 343) = v52;
        v55 = *((_DWORD *)this + 388);
        v73 = v53;
        if ( v55 == 90 || v55 == 270 )
        {
          v56 = v70;
          v57 = v71;
          v58 = v68;
          v59 = v69;
          *((_DWORD *)this + 174) = v54;
          *((_DWORD *)this + 175) = v53;
          *((_DWORD *)this + 176) = v51;
          *((_DWORD *)this + 177) = v50;
        }
        else
        {
          v56 = v71;
          v57 = v70;
          v58 = v69;
          v59 = v68;
          *(struct tagRECT *)((char *)this + 696) = v75;
        }
        v72 = v59;
        *(_QWORD *)&v80.left = (char *)this + 712;
        *((_DWORD *)this + 178) = v59;
        *((_DWORD *)this + 179) = v58;
        *((_DWORD *)this + 180) = v57;
        *((_DWORD *)this + 181) = v56;
        v60 = v57 - *((_DWORD *)this + 178);
        *((_DWORD *)this + 181) = v56 - v58;
        v61 = v68;
        *((_DWORD *)this + 180) = v60;
        *((_DWORD *)this + 178) = 0;
        *(_DWORD *)(*(_QWORD *)&v80.left + 4LL) = 0;
        v62 = v69;
        v63 = v69 + v51;
        *((_DWORD *)this + 168) = v61 + v73;
        v64 = v70;
        *((_DWORD *)this + 169) = v62 + v54;
        *((_DWORD *)this + 170) = v61 + v50;
        *((_DWORD *)this + 171) = v63;
        *((_DWORD *)this + 164) = v61;
        *((_DWORD *)this + 166) = v64;
        *((_DWORD *)this + 167) = v71;
        *((_DWORD *)this + 165) = v62;
        memset_0(v76, 0, 0x50u);
        ValidArea = CtypeSurfaces::Find(*((_DWORD *)this + 63), (struct TypeSurface *)v76);
        if ( !ValidArea )
          ValidArea = CxCodeVideoProcMFTDataHandler::GetValidArea(
                        v65,
                        *((_DWORD *)this + 75),
                        *((_DWORD *)this + 74),
                        v77,
                        v78,
                        (struct tagRECT *)this + 20,
                        0,
                        1);
      }
    }
    goto LABEL_89;
  }
  v80 = *v8;
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qdddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      204,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      v8->left,
      *((_DWORD *)this + 160),
      *((_DWORD *)this + 159),
      *((_DWORD *)this + 161));
  memset_0(v76, 0, 0x50u);
  ValidArea = CtypeSurfaces::Find(*((_DWORD *)this + 154), (struct TypeSurface *)v76);
  if ( !ValidArea )
    goto LABEL_17;
LABEL_89:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v67);
  return ValidArea;
}

```

## disassembly

```asm
0x1800052b0  mov     rax, rsp
0x1800052b3  push    rbp
0x1800052b4  push    rbx
0x1800052b5  push    rsi
0x1800052b6  push    rdi
0x1800052b7  push    r12
0x1800052b9  push    r13
0x1800052bb  push    r14
0x1800052bd  push    r15
0x1800052bf  lea     rbp, [rax-68h]
0x1800052c3  sub     rsp, 128h
0x1800052ca  movaps  xmmword ptr [rax-58h], xmm6
0x1800052ce  mov     rax, cs:__security_cookie
0x1800052d5  xor     rax, rsp
0x1800052d8  mov     [rbp+60h+var_60], rax
0x1800052dc  mov     r14d, edx
0x1800052df  mov     rsi, rcx
0x1800052e2  xorps   xmm0, xmm0
0x1800052e5  lea     rdx, aCxcodevideopro_45; "CxCodeVideoProcMFTDataHandler::UpdateOu"...
0x1800052ec  lea     rcx, [rsp+160h+var_100]; this
0x1800052f1  mov     r8d, 0F7Dh; int
0x1800052f7  movups  xmmword ptr [rbp+60h+var_D8.left], xmm0
0x1800052fb  xorps   xmm6, xmm6
0x1800052fe  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180005303  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000530a  xor     r15d, r15d
0x18000530d  cmp     [rcx+8], r15b
0x180005311  jz      short loc_18000536D
0x180005313  cmp     [rsi+0C20h], r15
0x18000531a  jz      short loc_18000536D
0x18000531c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180005321  mov     rdx, [rsi+0C20h]
0x180005328  mov     rdi, rax
0x18000532b  mov     rcx, [rdx]
0x18000532e  mov     rax, [rcx+128h]
0x180005335  mov     rcx, rdx
0x180005338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533d  mov     r8, [rsi+0C20h]
0x180005344  lea     rdx, [rbp+60h+var_70]
0x180005348  mov     ebx, eax
0x18000534a  mov     rcx, [r8]
0x18000534d  mov     rax, [rcx+118h]
0x180005354  mov     rcx, r8
0x180005357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535c  movups  xmm0, xmmword ptr [rax]
0x18000535f  mov     [rdi+7E0h], ebx
0x180005365  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18000536d  mov     eax, [rsi+28Ch]
0x180005373  mov     edi, r15d
0x180005376  mov     [rsp+160h+var_F4], eax
0x18000537a  mov     eax, [rsi+288h]
0x180005380  mov     [rsp+160h+var_F0], eax
0x180005384  test    r14d, r14d
0x180005387  jz      short loc_1800053A5
0x180005389  mov     rcx, [rsi+0A8h]
0x180005390  mov     rax, [rcx]
0x180005393  mov     rax, [rax+30h]
0x180005397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539c  cmp     eax, 0A000h
0x1800053a1  setl    dil
0x1800053a5  lea     rbx, [rsi+278h]
0x1800053ac  mov     rcx, rbx; lprc
0x1800053af  call    cs:__imp_IsRectEmpty
0x1800053b5  mov     r12d, 50h ; 'P'
0x1800053bb  lea     r14d, [r12-4Fh]
0x1800053c0  test    eax, eax
0x1800053c2  jnz     loc_18000544B
0x1800053c8  movups  xmm0, xmmword ptr [rbx]
0x1800053cb  movdqu  xmmword ptr [rbp+60h+var_70.left], xmm0
0x1800053d0  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800053d7  jb      short loc_18000541F
0x1800053d9  mov     eax, [rsi+284h]
0x1800053df  lea     edx, [r12+7Ch]
0x1800053e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053eb  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x1800053f2  mov     [rsp+160h+var_128], eax
0x1800053f6  mov     r9, rsi
0x1800053f9  mov     eax, [rsi+27Ch]
0x1800053ff  mov     [rsp+160h+var_130], eax
0x180005403  mov     eax, [rsi+280h]
0x180005409  mov     rcx, [rcx+150h]
0x180005410  mov     dword ptr [rsp+160h+var_138], eax
0x180005414  mov     eax, [rbx]
0x180005416  mov     [rsp+160h+var_140], eax
0x18000541a  call    WPP_SF_qdddd
0x18000541f  mov     r8, r12; Size
0x180005422  lea     rcx, [rbp+60h+var_C0]; void *
0x180005426  xor     edx, edx; Val
0x180005428  call    memset_0
0x18000542d  mov     ecx, [rsi+268h]; unsigned int
0x180005433  lea     rdx, [rbp+60h+var_C0]; struct TypeSurface *
0x180005437  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x18000543c  mov     ebx, eax
0x18000543e  test    eax, eax
0x180005440  jz      loc_18000551A
0x180005446  jmp     loc_180005C1D
0x18000544b  mov     rcx, [rsi+330h]
0x180005452  movq    rax, xmm6
0x180005457  mov     [rsp+160h+var_FC], r15d
0x18000545c  mov     [rsp+160h+var_F8], r15d
0x180005461  sub     rcx, rax
0x180005464  jnz     short loc_18000547A
0x180005466  mov     rcx, [rsi+338h]
0x18000546d  psrldq  xmm6, 8
0x180005472  movq    rax, xmm6
0x180005477  sub     rcx, rax
0x18000547a  test    rcx, rcx
0x18000547d  jz      loc_18000558C
0x180005483  mov     r8, r12; Size
0x180005486  lea     rcx, [rbp+60h+var_C0]; void *
0x18000548a  xor     edx, edx; Val
0x18000548c  call    memset_0
0x180005491  mov     ecx, [rsi+268h]; unsigned int
0x180005497  lea     rdx, [rbp+60h+var_C0]; struct TypeSurface *
0x18000549b  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x1800054a0  mov     ebx, eax
0x1800054a2  test    eax, eax
0x1800054a4  jnz     loc_180005C1D
0x1800054aa  movsx   ecx, word ptr [rsi+332h]
0x1800054b1  movsx   r8d, word ptr [rsi+336h]
0x1800054b9  mov     r9d, [rsi+338h]
0x1800054c0  mov     r10d, [rsi+33Ch]
0x1800054c7  add     r9d, ecx
0x1800054ca  add     r10d, r8d
0x1800054cd  mov     [rbp+60h+var_70.left], ecx
0x1800054d0  mov     [rbp+60h+var_70.bottom], r10d
0x1800054d4  mov     [rbp+60h+var_70.top], r8d
0x1800054d8  mov     [rbp+60h+var_70.right], r9d
0x1800054dc  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800054e3  jb      short loc_18000551A
0x1800054e5  mov     [rsp+160h+var_128], r10d
0x1800054ea  mov     edx, 0CDh
0x1800054ef  mov     [rsp+160h+var_130], r8d
0x1800054f4  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x1800054fb  mov     dword ptr [rsp+160h+var_138], r9d
0x180005500  mov     r9, rsi
0x180005503  mov     [rsp+160h+var_140], ecx
0x180005507  mov     rcx, cs:WPP_GLOBAL_Control
0x18000550e  mov     rcx, [rcx+150h]
0x180005515  call    WPP_SF_qdddd
0x18000551a  mov     r9d, [rbp+60h+var_AC]; unsigned int
0x18000551e  lea     rax, [rbp+60h+var_70]
0x180005522  mov     r8d, [rsi+288h]; unsigned int
0x180005529  mov     edx, [rsi+28Ch]; unsigned int
0x18000552f  mov     [rsp+160h+var_128], r14d; int
0x180005534  mov     [rsp+160h+var_130], edi; int
0x180005538  mov     [rsp+160h+var_138], rax; struct tagRECT *
0x18000553d  mov     eax, [rbp+60h+var_A8]
0x180005540  mov     [rsp+160h+var_140], eax; unsigned int
0x180005544  call    ?GetValidArea@CxCodeVideoProcMFTDataHandler@@AEAAJKKKKPEAUtagRECT@@HH@Z; CxCodeVideoProcMFTDataHandler::GetValidArea(ulong,ulong,ulong,ulong,tagRECT *,int,int)
0x180005549  mov     ebx, eax
0x18000554b  test    eax, eax
0x18000554d  jnz     loc_180005C1D
0x180005553  mov     r15d, [rbp+60h+var_70.right]
0x180005557  mov     eax, r15d
0x18000555a  mov     edx, [rbp+60h+var_70.left]
0x18000555d  sub     eax, edx
0x18000555f  mov     r12d, [rbp+60h+var_70.bottom]
0x180005563  mov     r8d, [rbp+60h+var_70.top]
0x180005567  mov     [rsi+2B4h], eax
0x18000556d  mov     eax, r12d
0x180005570  sub     eax, r8d
0x180005573  mov     [rsp+160h+var_F0], r12d
0x180005578  mov     [rsi+2B0h], eax
0x18000557e  mov     [rsp+160h+var_F4], r15d
0x180005583  mov     [rsp+160h+var_F8], r8d
0x180005588  mov     [rsp+160h+var_FC], edx
0x18000558c  mov     eax, [rsi+610h]
0x180005592  mov     ebx, [rsi+104h]
0x180005598  mov     ecx, [rsi+100h]
0x18000559e  mov     [rsp+160h+var_EC], ebx
0x1800055a2  cmp     eax, 5Ah ; 'Z'
0x1800055a5  jz      short loc_1800055B6
0x1800055a7  cmp     eax, 10Eh
0x1800055ac  jz      short loc_1800055B6
0x1800055ae  mov     edi, ecx
0x1800055b0  mov     [rsp+160h+var_E8], ecx
0x1800055b4  jmp     short loc_1800055C2
0x1800055b6  mov     edi, ebx
0x1800055b8  mov     [rsp+160h+var_E8], ebx
0x1800055bc  mov     ebx, ecx
0x1800055be  mov     [rsp+160h+var_EC], ecx
0x1800055c2  mov     r13d, [rsi+2B4h]
0x1800055c9  mov     r15d, [rsi+2B0h]
0x1800055d0  mov     r12b, cs:byte_180153DE0
0x1800055d7  cmp     r12b, 20h ; ' '
0x1800055db  jb      short loc_18000564F
0x1800055dd  mov     eax, [rsi+270h]
0x1800055e3  mov     edx, 0CEh
0x1800055e8  mov     r8d, [rsi+15Ch]
0x1800055ef  mov     r9, rsi
0x1800055f2  mov     ecx, [rsi+158h]
0x1800055f8  sub     ecx, [rsi+150h]
0x1800055fe  sub     r8d, [rsi+154h]
0x180005605  mov     dword ptr [rsp+160h+var_108], eax
0x180005609  mov     eax, [rsi+26Ch]
0x18000560f  mov     [rsp+160h+var_110], eax
0x180005613  mov     [rsp+160h+var_118], ebx
0x180005617  mov     [rsp+160h+var_120], edi
0x18000561b  mov     [rsp+160h+var_128], r8d
0x180005620  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180005627  mov     [rsp+160h+var_130], ecx
0x18000562b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005632  mov     dword ptr [rsp+160h+var_138], r15d
0x180005637  mov     [rsp+160h+var_140], r13d
0x18000563c  mov     rcx, [rcx+150h]
0x180005643  call    WPP_SF_qdddddddd
0x180005648  mov     r12b, cs:byte_180153DE0
0x18000564f  mov     eax, [rsi+15Ch]
0x180005655  xor     r9d, r9d
0x180005658  sub     eax, [rsi+154h]
0x18000565e  mov     r8d, [rsi+158h]
0x180005665  sub     r8d, [rsi+150h]
0x18000566c  mov     ecx, ebx
0x18000566e  mul     rcx
0x180005671  mov     qword ptr [rbp+60h+var_70.left], r9
0x180005675  test    rdx, rdx
0x180005678  jnz     loc_180005C18
0x18000567e  mov     ecx, [rsi+26Ch]
0x180005684  mul     rcx
0x180005687  mov     qword ptr [rbp+60h+var_70.left], r9
0x18000568b  test    rdx, rdx
0x18000568e  jnz     loc_180005C18
0x180005694  mul     r13
0x180005697  mov     qword ptr [rbp+60h+var_70.left], r9
0x18000569b  mov     r14, rax
0x18000569e  test    rdx, rdx
0x1800056a1  jnz     loc_180005C18
0x1800056a7  mov     ecx, edi
0x1800056a9  mov     eax, r8d
0x1800056ac  mul     rcx
0x1800056af  mov     qword ptr [rbp+60h+var_70.left], r9
0x1800056b3  test    rdx, rdx
0x1800056b6  jnz     loc_180005C18
0x1800056bc  mov     ecx, [rsi+270h]
0x1800056c2  mul     rcx
0x1800056c5  mov     qword ptr [rbp+60h+var_70.left], r9
0x1800056c9  mov     rdi, rax
0x1800056cc  test    rdx, rdx
0x1800056cf  jnz     loc_180005C18
0x1800056d5  movsd   xmm6, cs:__real@3fe0000000000000
0x1800056dd  test    rax, rax
0x1800056e0  jnz     short loc_1800056EB
0x1800056e2  lea     ebx, [r15+1]
0x1800056e6  jmp     loc_1800057A7
0x1800056eb  xor     edx, edx
0x1800056ed  mov     rax, r14
0x1800056f0  div     rdi
0x1800056f3  test    rdx, rdx
0x1800056f6  jz      loc_18000579B
0x1800056fc  xor     edx, edx; Val
0x1800056fe  lea     rcx, [rbp+60h+var_C0]; void *
0x180005702  lea     r8d, [rdx+50h]; Size
0x180005706  call    memset_0
0x18000570b  mov     ecx, [rsi+268h]; unsigned int
0x180005711  lea     rdx, [rbp+60h+var_C0]; struct TypeSurface *
0x180005715  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x18000571a  xor     r9d, r9d
0x18000571d  mov     ebx, eax
0x18000571f  test    eax, eax
0x180005721  jnz     loc_180005C1D
0x180005727  mov     ecx, [rbp+60h+var_AC]
0x18000572a  lea     edx, [rax+1]
0x18000572d  dec     ecx
0x18000572f  mov     eax, edx
0x180005731  shl     eax, cl
0x180005733  xorps   xmm2, xmm2
0x180005736  xorps   xmm0, xmm0
0x180005739  cvtsi2sd xmm2, rax
0x18000573e  mulsd   xmm2, xmm6
0x180005742  test    r14, r14
0x180005745  js      short loc_18000574E
0x180005747  cvtsi2sd xmm0, r14
0x18000574c  jmp     short loc_180005763
0x18000574e  mov     rax, r14
0x180005751  and     r14, rdx
0x180005754  shr     rax, 1
0x180005757  or      rax, r14
0x18000575a  cvtsi2sd xmm0, rax
0x18000575f  addsd   xmm0, xmm0
0x180005763  xorps   xmm1, xmm1
0x180005766  test    rdi, rdi
0x180005769  js      short loc_180005772
0x18000576b  cvtsi2sd xmm1, rdi
0x180005770  jmp     short loc_180005787
0x180005772  mov     rax, rdi
0x180005775  and     rdi, rdx
0x180005778  shr     rax, 1
0x18000577b  or      rax, rdi
0x18000577e  cvtsi2sd xmm1, rax
0x180005783  addsd   xmm1, xmm1
0x180005787  divsd   xmm0, xmm1
0x18000578b  addsd   xmm2, xmm0
0x18000578f  cvttsd2si rbx, xmm2
0x180005794  cmp     ebx, edx
0x180005796  cmovb   ebx, edx
0x180005799  jmp     short loc_1800057A7
0x18000579b  mov     ecx, 1
0x1800057a0  cmp     eax, ecx
0x1800057a2  cmovb   eax, ecx
  ... truncated ...
```
