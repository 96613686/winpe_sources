# CRenderer::RenderUnderline(long,long,long,long)

- ea: `0x1800b32b4`
- end: `0x1800b3786`
- name: `?RenderUnderline@CRenderer@@QEAAXJJJJ@Z`
- size: `1234`
- prototype: `void __fastcall(CRenderer *__hidden this, int, int, int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x1800b43c8`
- `0x18014e41c`

## callees

- `0x18000f260`
- `0x18002cccc`
- `0x18004e140`
- `0x1800566a8`
- `0x1800b32b4`
- `0x1800e9918`
- `0x1800f26b4`
- `0x18010a1e0`
- `0x18010d478`
- `0x18010e600`
- `0x18013ce80`
- `0x18014e718`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b3584`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b36d8`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b3584`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b36d8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b36e7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b36e7`

## pseudocode

```c
void __fastcall CRenderer::RenderUnderline(CRenderer *this, int a2, int a3, int a4, int a5)
{
  CMeasurerNoFC *v9; // rcx
  int v10; // ecx
  int *v11; // rdi
  int v12; // r15d
  int v13; // eax
  int v14; // ebx
  int v15; // edi
  COLORREF v16; // r13d
  int v17; // edi
  CDisplay *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // r12d
  int v22; // eax
  char v23; // al
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // edi
  void *v27; // r15
  unsigned int v28; // ebx
  __int64 v29; // rcx
  HDC v30; // rax
  int v31; // eax
  char v32; // al
  int v33; // eax
  int v34; // r12d
  int v35; // ebx
  int v36; // eax
  int v37; // eax
  HGDIOBJ v38; // rbx
  HDC v39; // rax
  __int16 *v40; // rcx
  int v41; // edi
  int v42; // ebx
  int Ascent; // eax
  CDisplay *v44; // rcx
  int v45; // [rsp+30h] [rbp-51h] BYREF
  int v46[2]; // [rsp+38h] [rbp-49h] BYREF
  HGDIOBJ h; // [rsp+40h] [rbp-41h] BYREF
  int v48; // [rsp+48h] [rbp-39h]
  int v49; // [rsp+4Ch] [rbp-35h]
  unsigned __int64 v50; // [rsp+50h] [rbp-31h] BYREF
  int v51; // [rsp+58h] [rbp-29h]
  int v52; // [rsp+5Ch] [rbp-25h]
  void *v53; // [rsp+60h] [rbp-21h]
  unsigned int v54; // [rsp+68h] [rbp-19h]
  struct tagRECT v55; // [rsp+70h] [rbp-11h] BYREF

  v52 = a2;
  v45 = CMeasurerNoFC::fUseLineServices(this);
  if ( v45 )
    a4 -= CMeasurerNoFC::GetAlignSpacing(v9, *((_DWORD *)v9 + 8) + *((_DWORD *)v9 + 24), 1);
  v10 = *((unsigned __int8 *)this + 524);
  v54 = a2 + a4;
  if ( (unsigned int)(v10 - 4) <= 4
    || (unsigned int)(v10 - 19) <= 3
    || (LODWORD(v53) = 0, (unsigned int)(v10 - 11) <= 7) )
  {
    LODWORD(v53) = 1;
  }
  v11 = (int *)((char *)this + 376);
  v49 = a3 + a5;
  h = (HGDIOBJ)__PAIR64__(a3, a2);
  v48 = a2 + a4;
  if ( this != (CRenderer *)-376LL )
  {
    v12 = a2;
    v13 = *((_DWORD *)this + 96);
    if ( *v11 > a2 )
      v12 = *v11;
    if ( v13 >= a2 + a4 )
      v13 = a2 + a4;
    LODWORD(v50) = v13;
    if ( v12 < v13 )
    {
      v14 = a3;
      if ( *((_DWORD *)this + 95) > a3 )
        v14 = *((_DWORD *)this + 95);
      v15 = *((_DWORD *)this + 97);
      if ( v15 >= a3 + a5 )
        v15 = a3 + a5;
      if ( v14 < v15 )
      {
        v16 = *((_DWORD *)this + 130);
        v17 = v15 - v14;
        v51 = v13 - v12;
        v46[0] = v13 - v12;
        a5 = v17;
        if ( v16 == -9999997 || v16 == -9999999 )
          v16 = *((_DWORD *)this + 113);
        v18 = (CDisplay *)*((_QWORD *)this + 19);
        v55 = 0;
        CDisplay::RectFromRectuv(v18, &v55, (const struct RECTUV *)&h, 1, 0);
        LOBYTE(v19) = *((_BYTE *)this + 524);
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD, struct tagRECT *))(**((_QWORD **)this + 42)
                                                                                           + 432LL))(
                *((_QWORD *)this + 42),
                v19,
                v16,
                &v55) )
        {
          v20 = *((unsigned __int8 *)this + 524);
          if ( (_BYTE)v20 == 0xFE )
          {
            v40 = (__int16 *)*((_QWORD *)this + 41);
            HIDWORD(h) = *((_DWORD *)this + 129);
            v41 = HIDWORD(h);
            LODWORD(h) = v12;
            v42 = CCcs::ScaleMetric((CCcs *)v40, v40[10]);
            Ascent = CLine::GetAscent((CRenderer *)((char *)this + 96), 0, 0);
            v44 = (CDisplay *)*((_QWORD *)this + 19);
            v49 = v42 + v41 + Ascent;
            v48 = v50;
            CDisplay::RectFromRectuv(v44, &v55, (const struct RECTUV *)&h, 1, 0);
            (*(void (__fastcall **)(_QWORD, struct tagRECT *))(**((_QWORD **)this + 42) + 280LL))(
              *((_QWORD *)this + 42),
              &v55);
            return;
          }
          if ( !(_DWORD)v53 )
          {
            HIDWORD(h) = v14;
            if ( (_BYTE)v20 == 9 && v14 > v17 + *((_DWORD *)this + 95) )
            {
              v14 -= v17;
              HIDWORD(h) = v14;
              a5 = 2 * v17;
            }
            CRenderer::CorrectLineWidth(this, v46, &a5);
            v21 = a5;
            if ( v45 )
              goto LABEL_39;
            if ( (*((_BYTE *)this + 109) & 0x10) != 0 )
              goto LABEL_29;
            v23 = *((_BYTE *)this + 111) & 3;
            if ( v23 == 1 )
            {
              v25 = *((_QWORD *)this + 15);
              if ( !v25 )
                goto LABEL_29;
              SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
                *(int *)(v25 + 8),
                &v45);
              v22 = v45;
            }
            else
            {
              if ( v23 == 2 )
              {
                v24 = *((_QWORD *)this + 15);
                if ( v24 )
                {
                  v22 = *(_DWORD *)(v24 + 16);
                  goto LABEL_37;
                }
LABEL_29:
                v22 = 0;
                goto LABEL_37;
              }
              v22 = *((_DWORD *)this + 31);
            }
LABEL_37:
            v26 = *((_DWORD *)this + 129);
            if ( v14 >= v26 + v22 )
            {
              v14 = v26 - v21 + CLine::GetHeight((CRenderer *)((char *)this + 96), 0, 0);
              HIDWORD(h) = v14;
            }
LABEL_39:
            v49 = v14 + v21;
            v48 = v12 + v46[0];
            LODWORD(h) = v12;
            CRenderer::FillRectWithColor(this, (const struct RECTUV *)&h, v16);
            return;
          }
          v27 = 0;
          v28 = *((char *)qword_1802AFDA8 + v20 - 4);
          v29 = *((_QWORD *)this + 42);
          v45 = v28;
          v53 = 0;
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 48LL))(v29) )
          {
            v27 = (void *)((__int64 (__fastcall *)(_QWORD, bool, _QWORD))pfnCreatePen)(v28, v28 == 0, v16);
            v53 = v27;
          }
          if ( !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42)) || v27 )
          {
            if ( v27 )
            {
              v30 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
              h = SelectObject(v30, v27);
            }
            else
            {
              h = 0;
            }
            v31 = 1;
            v46[0] = a2;
            if ( v51 < v17 )
              v17 = v51;
            v46[1] = a3;
            if ( v17 > 1 )
              v31 = v17;
            v51 = v31;
            v32 = *((_BYTE *)this + 524);
            if ( v32 != 8 && (unsigned __int8)(v32 - 11) > 1u )
              goto LABEL_55;
            if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 80LL))(*((_QWORD *)this + 42)) )
            {
              v28 = 7;
LABEL_55:
              v50 = __PAIR64__(a3, v54);
              CRenderer::DrawLine(
                this,
                (const struct Ptls6::tagLSPOINTUV *)v46,
                (const struct Ptls6::tagLSPOINTUV *)&v50,
                v51,
                v28,
                v16);
LABEL_68:
              if ( v27 )
              {
                v38 = h;
                if ( h )
                {
                  v39 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
                  SelectObject(v39, v38);
                }
                DeleteObject(v27);
              }
              return;
            }
            v33 = v52;
            v34 = 2;
            v52 = v54 + 1;
            v35 = v33 + 1;
            switch ( v33 % 4 )
            {
              case 1:
                v36 = a3 + 2;
                v34 = -1;
                ++v35;
                break;
              case 2:
                v34 = -1;
                goto LABEL_63;
              case 3:
                v36 = a3 - 1;
                ++v35;
                break;
              default:
                goto LABEL_63;
            }
            v46[1] = v36;
LABEL_63:
            if ( v35 < (int)(v54 + 1) )
            {
              do
              {
                HIDWORD(v50) = v34 + a3;
                LODWORD(v50) = v35;
                CRenderer::DrawLine(
                  this,
                  (const struct Ptls6::tagLSPOINTUV *)v46,
                  (const struct Ptls6::tagLSPOINTUV *)&v50,
                  1,
                  v45,
                  v16);
                v35 += 2;
                *(_QWORD *)v46 = v50;
                v37 = -1;
                if ( v34 != 2 )
                  v37 = 2;
                v34 = v37;
              }
              while ( v35 < v52 );
              v27 = v53;
            }
            goto LABEL_68;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800b32b4  push    rbp
0x1800b32b6  push    rbx
0x1800b32b7  push    rsi
0x1800b32b8  push    rdi
0x1800b32b9  push    r12
0x1800b32bb  push    r13
0x1800b32bd  push    r14
0x1800b32bf  push    r15
0x1800b32c1  lea     rbp, [rsp-17h]
0x1800b32c6  sub     rsp, 98h
0x1800b32cd  mov     rax, cs:__security_cookie
0x1800b32d4  xor     rax, rsp
0x1800b32d7  mov     [rbp+4Fh+var_50], rax
0x1800b32db  mov     ebx, r9d
0x1800b32de  mov     [rbp+4Fh+var_74], edx
0x1800b32e1  mov     r14d, r8d
0x1800b32e4  mov     r12d, edx
0x1800b32e7  mov     rsi, rcx
0x1800b32ea  call    ?fUseLineServices@CMeasurerNoFC@@QEBAHXZ; CMeasurerNoFC::fUseLineServices(void)
0x1800b32ef  mov     [rbp+4Fh+var_A0], eax
0x1800b32f2  test    eax, eax
0x1800b32f4  jz      short loc_1800B3306
0x1800b32f6  mov     edx, [rcx+60h]
0x1800b32f9  mov     r8b, 1; bool
0x1800b32fc  add     edx, [rcx+20h]; int
0x1800b32ff  call    ?GetAlignSpacing@CMeasurerNoFC@@QEAAJJ_N@Z; CMeasurerNoFC::GetAlignSpacing(long,bool)
0x1800b3304  sub     ebx, eax
0x1800b3306  movzx   ecx, byte ptr [rsi+20Ch]
0x1800b330d  lea     edx, [r12+rbx]
0x1800b3311  mov     [rbp+4Fh+var_68], edx
0x1800b3314  lea     eax, [rcx-4]
0x1800b3317  cmp     eax, 4
0x1800b331a  jbe     short loc_1800B3333
0x1800b331c  lea     eax, [rcx-13h]
0x1800b331f  cmp     eax, 3
0x1800b3322  jbe     short loc_1800B3333
0x1800b3324  lea     eax, [rcx-0Bh]
0x1800b3327  mov     dword ptr [rbp+4Fh+var_70], 0
0x1800b332e  cmp     eax, 7
0x1800b3331  ja      short loc_1800B333A
0x1800b3333  mov     dword ptr [rbp+4Fh+var_70], 1
0x1800b333a  mov     ecx, [rbp+4Fh+arg_20]
0x1800b333d  lea     rdi, [rsi+178h]
0x1800b3344  add     ecx, r14d
0x1800b3347  mov     dword ptr [rbp+4Fh+h+4], r14d
0x1800b334b  mov     [rbp+4Fh+var_84], ecx
0x1800b334e  mov     dword ptr [rbp+4Fh+h], r12d
0x1800b3352  mov     [rbp+4Fh+var_88], edx
0x1800b3355  test    rdi, rdi
0x1800b3358  jz      loc_1800B3765
0x1800b335e  cmp     [rdi], r12d
0x1800b3361  mov     r15d, r12d
0x1800b3364  mov     eax, [rdi+8]
0x1800b3367  cmovg   r15d, [rdi]
0x1800b336b  cmp     eax, edx
0x1800b336d  cmovge  eax, edx
0x1800b3370  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800b3373  cmp     r15d, eax
0x1800b3376  jge     loc_1800B3765
0x1800b337c  cmp     [rdi+4], r14d
0x1800b3380  mov     ebx, r14d
0x1800b3383  cmovg   ebx, [rdi+4]
0x1800b3387  mov     edi, [rdi+0Ch]
0x1800b338a  cmp     edi, ecx
0x1800b338c  cmovge  edi, ecx
0x1800b338f  cmp     ebx, edi
0x1800b3391  jge     loc_1800B3765
0x1800b3397  mov     r13d, [rsi+208h]
0x1800b339e  sub     eax, r15d
0x1800b33a1  sub     edi, ebx
0x1800b33a3  mov     [rbp+4Fh+var_78], eax
0x1800b33a6  mov     [rbp+4Fh+var_98], eax
0x1800b33a9  mov     [rbp+4Fh+arg_20], edi
0x1800b33ac  cmp     r13d, 0FF676983h
0x1800b33b3  jz      short loc_1800B33BE
0x1800b33b5  cmp     r13d, 0FF676981h
0x1800b33bc  jnz     short loc_1800B33C5
0x1800b33be  mov     r13d, [rsi+1C4h]
0x1800b33c5  mov     rcx, [rsi+98h]; this
0x1800b33cc  lea     r8, [rbp+4Fh+h]; struct RECTUV *
0x1800b33d0  xorps   xmm0, xmm0
0x1800b33d3  mov     [rsp+0D0h+var_B0], 0; bool
0x1800b33d8  mov     r9b, 1; bool
0x1800b33db  lea     rdx, [rbp+4Fh+var_60]; struct tagRECT *
0x1800b33df  movups  xmmword ptr [rbp+4Fh+var_60.left], xmm0
0x1800b33e3  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x1800b33e8  mov     rcx, [rsi+150h]
0x1800b33ef  lea     r9, [rbp+4Fh+var_60]
0x1800b33f3  mov     dl, [rsi+20Ch]
0x1800b33f9  mov     r8d, r13d
0x1800b33fc  mov     rax, [rcx]
0x1800b33ff  mov     rax, [rax+1B0h]
0x1800b3406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b340b  test    al, al
0x1800b340d  jnz     loc_1800B3765
0x1800b3413  movzx   eax, byte ptr [rsi+20Ch]
0x1800b341a  cmp     al, 0FEh
0x1800b341c  jz      loc_1800B36F5
0x1800b3422  cmp     dword ptr [rbp+4Fh+var_70], 0
0x1800b3426  jnz     loc_1800B34F8
0x1800b342c  mov     dword ptr [rbp+4Fh+h+4], ebx
0x1800b342f  cmp     al, 9
0x1800b3431  jnz     short loc_1800B344A
0x1800b3433  mov     ecx, [rsi+17Ch]
0x1800b3439  add     ecx, edi
0x1800b343b  cmp     ebx, ecx
0x1800b343d  jle     short loc_1800B344A
0x1800b343f  sub     ebx, edi
0x1800b3441  lea     eax, [rdi+rdi]
0x1800b3444  mov     dword ptr [rbp+4Fh+h+4], ebx
0x1800b3447  mov     [rbp+4Fh+arg_20], eax
0x1800b344a  lea     r8, [rbp+4Fh+arg_20]; int *
0x1800b344e  mov     rcx, rsi; this
0x1800b3451  lea     rdx, [rbp+4Fh+var_98]; int *
0x1800b3455  call    ?CorrectLineWidth@CRenderer@@QEBAXAEAJ0@Z; CRenderer::CorrectLineWidth(long &,long &)
0x1800b345a  cmp     [rbp+4Fh+var_A0], 0
0x1800b345e  mov     r12d, [rbp+4Fh+arg_20]
0x1800b3462  jnz     short loc_1800B34D0
0x1800b3464  test    byte ptr [rsi+6Dh], 10h
0x1800b3468  jz      short loc_1800B346E
0x1800b346a  xor     eax, eax
0x1800b346c  jmp     short loc_1800B34AD
0x1800b346e  mov     al, [rsi+6Fh]
0x1800b3471  and     al, 3
0x1800b3473  cmp     al, 1
0x1800b3475  jz      short loc_1800B3494
0x1800b3477  mov     edi, 2
0x1800b347c  cmp     al, dil
0x1800b347f  jnz     short loc_1800B348F
0x1800b3481  mov     rax, [rsi+78h]
0x1800b3485  test    rax, rax
0x1800b3488  jz      short loc_1800B346A
0x1800b348a  mov     eax, [rax+10h]
0x1800b348d  jmp     short loc_1800B34AD
0x1800b348f  mov     eax, [rsi+7Ch]
0x1800b3492  jmp     short loc_1800B34AD
0x1800b3494  mov     rax, [rsi+78h]
0x1800b3498  test    rax, rax
0x1800b349b  jz      short loc_1800B346A
0x1800b349d  movsxd  rcx, dword ptr [rax+8]
0x1800b34a1  lea     rdx, [rbp+4Fh+var_A0]
0x1800b34a5  call    ??$CastThrow@V?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@?$SafeCastHelper@J_J$03@@SAX_JAEAJ@Z; SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(__int64,long &)
0x1800b34aa  mov     eax, [rbp+4Fh+var_A0]
0x1800b34ad  mov     edi, [rsi+204h]
0x1800b34b3  add     eax, edi
0x1800b34b5  cmp     ebx, eax
0x1800b34b7  jl      short loc_1800B34D0
0x1800b34b9  xor     r8d, r8d; struct CDisplay *
0x1800b34bc  lea     rcx, [rsi+60h]; this
0x1800b34c0  xor     edx, edx; bool
0x1800b34c2  call    ?GetHeight@CLine@@QEBAJ_NPEBVCDisplay@@@Z; CLine::GetHeight(bool,CDisplay const *)
0x1800b34c7  sub     edi, r12d
0x1800b34ca  lea     ebx, [rdi+rax]
0x1800b34cd  mov     dword ptr [rbp+4Fh+h+4], ebx
0x1800b34d0  mov     edx, [rbp+4Fh+var_98]
0x1800b34d3  lea     eax, [rbx+r12]
0x1800b34d7  add     edx, r15d
0x1800b34da  mov     [rbp+4Fh+var_84], eax
0x1800b34dd  mov     [rbp+4Fh+var_88], edx
0x1800b34e0  mov     r8d, r13d; unsigned int
0x1800b34e3  lea     rdx, [rbp+4Fh+h]; struct RECTUV *
0x1800b34e7  mov     dword ptr [rbp+4Fh+h], r15d
0x1800b34eb  mov     rcx, rsi; this
0x1800b34ee  call    ?FillRectWithColor@CRenderer@@QEAAXPEBURECTUV@@K@Z; CRenderer::FillRectWithColor(RECTUV const *,ulong)
0x1800b34f3  jmp     loc_1800B3765
0x1800b34f8  lea     rcx, qword_1802AFDA8
0x1800b34ff  xor     r15d, r15d
0x1800b3502  movsx   ebx, byte ptr [rax+rcx-4]
0x1800b3507  mov     rcx, [rsi+150h]
0x1800b350e  mov     [rbp+4Fh+var_A0], ebx
0x1800b3511  mov     [rbp+4Fh+var_70], r15
0x1800b3515  mov     rax, [rcx]
0x1800b3518  mov     rax, [rax+30h]
0x1800b351c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3521  test    rax, rax
0x1800b3524  jz      short loc_1800B3545
0x1800b3526  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x1800b352d  xor     edx, edx
0x1800b352f  test    ebx, ebx
0x1800b3531  mov     r8d, r13d
0x1800b3534  mov     ecx, ebx
0x1800b3536  setz    dl
0x1800b3539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b353e  mov     r15, rax
0x1800b3541  mov     [rbp+4Fh+var_70], rax
0x1800b3545  mov     rcx, [rsi+150h]
0x1800b354c  mov     rax, [rcx]
0x1800b354f  mov     rax, [rax+30h]
0x1800b3553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3558  test    rax, rax
0x1800b355b  jz      short loc_1800B3566
0x1800b355d  test    r15, r15
0x1800b3560  jz      loc_1800B3765
0x1800b3566  test    r15, r15
0x1800b3569  jz      short loc_1800B3596
0x1800b356b  mov     rcx, [rsi+150h]
0x1800b3572  mov     rax, [rcx]
0x1800b3575  mov     rax, [rax+30h]
0x1800b3579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b357e  mov     rdx, r15; h
0x1800b3581  mov     rcx, rax; hdc
0x1800b3584  call    cs:__imp_SelectObject
0x1800b358b  nop     dword ptr [rax+rax+00h]
0x1800b3590  mov     [rbp+4Fh+h], rax
0x1800b3594  jmp     short loc_1800B359E
0x1800b3596  mov     [rbp+4Fh+h], 0
0x1800b359e  cmp     [rbp+4Fh+var_78], edi
0x1800b35a1  mov     eax, 1
0x1800b35a6  mov     [rbp+4Fh+var_98], r12d
0x1800b35aa  cmovl   edi, [rbp+4Fh+var_78]
0x1800b35ae  cmp     edi, eax
0x1800b35b0  mov     [rbp+4Fh+var_98+4], r14d
0x1800b35b4  cmovg   eax, edi
0x1800b35b7  mov     [rbp+4Fh+var_78], eax
0x1800b35ba  mov     al, [rsi+20Ch]
0x1800b35c0  cmp     al, 8
0x1800b35c2  jz      short loc_1800B35CA
0x1800b35c4  sub     al, 0Bh
0x1800b35c6  cmp     al, 1
0x1800b35c8  ja      short loc_1800B35E6
0x1800b35ca  mov     rcx, [rsi+150h]
0x1800b35d1  mov     rax, [rcx]
0x1800b35d4  mov     rax, [rax+50h]
0x1800b35d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b35dd  test    al, al
0x1800b35df  jz      short loc_1800B3612
0x1800b35e1  mov     ebx, 7
0x1800b35e6  mov     ecx, [rbp+4Fh+var_68]
0x1800b35e9  lea     r8, [rbp+4Fh+var_80]; struct Ptls6::tagLSPOINTUV *
0x1800b35ed  mov     r9d, [rbp+4Fh+var_78]; int
0x1800b35f1  lea     rdx, [rbp+4Fh+var_98]; struct Ptls6::tagLSPOINTUV *
0x1800b35f5  mov     dword ptr [rbp+4Fh+var_80], ecx
0x1800b35f8  mov     rcx, rsi; this
0x1800b35fb  mov     [rsp+0D0h+var_A8], r13d; unsigned int
0x1800b3600  mov     dword ptr [rbp+4Fh+var_80+4], r14d
0x1800b3604  mov     dword ptr [rsp+0D0h+var_B0], ebx; int
0x1800b3608  call    ?DrawLine@CRenderer@@QEAAXAEBUtagLSPOINTUV@Ptls6@@0JHK@Z; CRenderer::DrawLine(Ptls6::tagLSPOINTUV const &,Ptls6::tagLSPOINTUV const &,long,int,ulong)
0x1800b360d  jmp     loc_1800B36AD
0x1800b3612  mov     eax, [rbp+4Fh+var_74]
0x1800b3615  mov     edi, 2
0x1800b361a  mov     ecx, [rbp+4Fh+var_68]
0x1800b361d  mov     r12d, edi
0x1800b3620  inc     ecx
0x1800b3622  mov     [rbp+4Fh+var_74], ecx
0x1800b3625  lea     ebx, [rax+1]
0x1800b3628  cdq
0x1800b3629  lea     r8d, [rdi+2]
0x1800b362d  idiv    r8d
0x1800b3630  or      r8d, 0FFFFFFFFh
0x1800b3634  sub     edx, 1
0x1800b3637  jz      short loc_1800B3650
0x1800b3639  sub     edx, 1
0x1800b363c  jz      short loc_1800B364B
0x1800b363e  cmp     edx, 1
0x1800b3641  jnz     short loc_1800B365C
0x1800b3643  lea     eax, [r14-1]
0x1800b3647  inc     ebx
0x1800b3649  jmp     short loc_1800B3659
0x1800b364b  mov     r12d, r8d
0x1800b364e  jmp     short loc_1800B365C
0x1800b3650  lea     eax, [r14+2]
0x1800b3654  mov     r12d, r8d
0x1800b3657  inc     ebx
0x1800b3659  mov     [rbp+4Fh+var_98+4], eax
0x1800b365c  cmp     ebx, ecx
0x1800b365e  jge     short loc_1800B36AD
0x1800b3660  mov     r15d, [rbp+4Fh+var_A0]
0x1800b3664  lea     eax, [r12+r14]
0x1800b3668  mov     [rsp+0D0h+var_A8], r13d; unsigned int
0x1800b366d  mov     r9d, 1; int
0x1800b3673  mov     dword ptr [rbp+4Fh+var_80+4], eax
0x1800b3676  lea     r8, [rbp+4Fh+var_80]; struct Ptls6::tagLSPOINTUV *
0x1800b367a  mov     dword ptr [rbp+4Fh+var_80], ebx
0x1800b367d  lea     rdx, [rbp+4Fh+var_98]; struct Ptls6::tagLSPOINTUV *
0x1800b3681  mov     dword ptr [rsp+0D0h+var_B0], r15d; int
0x1800b3686  mov     rcx, rsi; this
0x1800b3689  call    ?DrawLine@CRenderer@@QEAAXAEBUtagLSPOINTUV@Ptls6@@0JHK@Z; CRenderer::DrawLine(Ptls6::tagLSPOINTUV const &,Ptls6::tagLSPOINTUV const &,long,int,ulong)
0x1800b368e  mov     rax, [rbp+4Fh+var_80]
0x1800b3692  add     ebx, edi
0x1800b3694  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800b3698  or      eax, 0FFFFFFFFh
0x1800b369b  cmp     r12d, edi
0x1800b369e  cmovnz  eax, edi
0x1800b36a1  mov     r12d, eax
0x1800b36a4  cmp     ebx, [rbp+4Fh+var_74]
0x1800b36a7  jl      short loc_1800B3664
0x1800b36a9  mov     r15, [rbp+4Fh+var_70]
0x1800b36ad  test    r15, r15
0x1800b36b0  jz      loc_1800B3765
0x1800b36b6  mov     rbx, [rbp+4Fh+h]
0x1800b36ba  test    rbx, rbx
0x1800b36bd  jz      short loc_1800B36E4
0x1800b36bf  mov     rcx, [rsi+150h]
0x1800b36c6  mov     rax, [rcx]
0x1800b36c9  mov     rax, [rax+30h]
0x1800b36cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b36d2  mov     rdx, rbx; h
0x1800b36d5  mov     rcx, rax; hdc
0x1800b36d8  call    cs:__imp_SelectObject
0x1800b36df  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
