# CUser::GetXML(uint *,ushort * *)

- ea: `0x180011ff4`
- end: `0x18001251d`
- name: `?GetXML@CUser@@QEAAJPEAIPEAPEAG@Z`
- size: `1321`
- prototype: `__int64 __fastcall(CUser *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180009d3c`
- `0x18000d1a0`

## callees

- `0x180001284`
- `0x180001290`
- `0x180011ff4`
- `0x180015438`
- `0x180017358`
- `0x18003b3b8`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800124c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800124c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012043`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012043`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUser::GetXML(CUser *this, unsigned int *a2, unsigned __int16 **a3)
{
  unsigned int *v3; // r13
  void *v5; // r14
  unsigned __int16 *v6; // r12
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // rsi
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rcx
  int v11; // eax
  unsigned __int16 *v12; // rcx
  int v13; // eax
  unsigned __int16 *v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned int v24; // eax
  unsigned __int64 v25; // r13
  __int64 v26; // rcx
  const wchar_t *v27; // r9
  unsigned __int64 v28; // rdx
  unsigned __int16 *v29; // rcx
  int v30; // eax
  unsigned __int16 *v31; // r8
  unsigned __int16 *v33; // [rsp+20h] [rbp-258h]
  unsigned int v34; // [rsp+30h] [rbp-248h]
  unsigned __int16 *v35; // [rsp+38h] [rbp-240h] BYREF
  unsigned __int16 *v36; // [rsp+40h] [rbp-238h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-230h] BYREF
  unsigned __int16 **v38; // [rsp+50h] [rbp-228h]
  unsigned int *v39; // [rsp+58h] [rbp-220h]
  void *v40; // [rsp+60h] [rbp-218h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-210h]
  __int64 v42; // [rsp+70h] [rbp-208h]
  char *v43; // [rsp+78h] [rbp-200h]
  unsigned __int16 v44[8]; // [rsp+80h] [rbp-1F8h] BYREF
  __int128 v45; // [rsp+90h] [rbp-1E8h]
  __int128 v46; // [rsp+A0h] [rbp-1D8h]
  __int128 v47; // [rsp+B0h] [rbp-1C8h]
  __int128 v48; // [rsp+C0h] [rbp-1B8h]
  __int128 v49; // [rsp+D0h] [rbp-1A8h]
  _OWORD v50[2]; // [rsp+E0h] [rbp-198h]
  unsigned __int16 v51[8]; // [rsp+100h] [rbp-178h] BYREF
  __int128 v52; // [rsp+110h] [rbp-168h]
  __int128 v53; // [rsp+120h] [rbp-158h]
  __int128 v54; // [rsp+130h] [rbp-148h]
  __int128 v55; // [rsp+140h] [rbp-138h]
  __int128 v56; // [rsp+150h] [rbp-128h]
  __int128 v57; // [rsp+160h] [rbp-118h]
  __int128 v58; // [rsp+170h] [rbp-108h]
  _OWORD v59[2]; // [rsp+180h] [rbp-F8h]
  _OWORD v60[9]; // [rsp+1A0h] [rbp-D8h] BYREF
  __int64 v61; // [rsp+230h] [rbp-48h] BYREF

  v42 = -2;
  v38 = a3;
  v3 = a2;
  v39 = a2;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 88);
  v43 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = 0;
  v40 = 0;
  *(_OWORD *)v51 = *(_OWORD *)L"<PRINCIPAL><OBJECT><ID type=\"%s\">%s</ID><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v52 = *(_OWORD *)L"AL><OBJECT><ID type=\"%s\">%s</ID><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v53 = *(_OWORD *)L"CT><ID type=\"%s\">%s</ID><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v54 = *(_OWORD *)L"ype=\"%s\">%s</ID><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v55 = *(_OWORD *)L">%s</ID><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v56 = *(_OWORD *)L"<NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v57 = *(_OWORD *)L"</NAME></OBJECT></PRINCIPAL>";
  v58 = *(_OWORD *)L"/OBJECT></PRINCIPAL>";
  v59[0] = *(_OWORD *)L"</PRINCIPAL>";
  *(_OWORD *)((char *)v59 + 10) = *(_OWORD *)L"NCIPAL>";
  v60[0] = *(_OWORD *)L"<PRINCIPAL><OBJECT><ID type=\"%s\" /><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v60[1] = *(_OWORD *)L"AL><OBJECT><ID type=\"%s\" /><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v60[2] = *(_OWORD *)L"CT><ID type=\"%s\" /><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v60[3] = *(_OWORD *)L"ype=\"%s\" /><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v60[4] = *(_OWORD *)L" /><NAME>%s</NAME></OBJECT></PRINCIPAL>";
  v60[5] = *(_OWORD *)L">%s</NAME></OBJECT></PRINCIPAL>";
  v60[6] = *(_OWORD *)L"E></OBJECT></PRINCIPAL>";
  v60[7] = *(_OWORD *)L"CT></PRINCIPAL>";
  v60[8] = *(_OWORD *)L"NCIPAL>";
  *(_OWORD *)v44 = *(_OWORD *)L"<PRINCIPAL><OBJECT><ID type=\"%s\">%s</ID></OBJECT></PRINCIPAL>";
  v45 = *(_OWORD *)L"AL><OBJECT><ID type=\"%s\">%s</ID></OBJECT></PRINCIPAL>";
  v46 = *(_OWORD *)L"CT><ID type=\"%s\">%s</ID></OBJECT></PRINCIPAL>";
  v47 = *(_OWORD *)L"ype=\"%s\">%s</ID></OBJECT></PRINCIPAL>";
  v48 = *(_OWORD *)L">%s</ID></OBJECT></PRINCIPAL>";
  v49 = *(_OWORD *)L"</OBJECT></PRINCIPAL>";
  v50[0] = *(_OWORD *)L"></PRINCIPAL>";
  *(_OWORD *)((char *)v50 + 12) = *(_OWORD *)L"NCIPAL>";
  v6 = 0;
  v35 = 0;
  v7 = 0;
  v36 = 0;
  v8 = 0;
  v37 = 0;
  if ( !v3 )
  {
    v9 = -2147024809;
    goto LABEL_63;
  }
  v9 = 0;
  *v3 = 0;
  v10 = (unsigned __int16 *)*((_QWORD *)this + 16);
  if ( !v10 || (v11 = EscapeXML(v10, &v35), v9 = v11, v6 = v35, v11 >= 0) )
  {
    v12 = (unsigned __int16 *)*((_QWORD *)this + 17);
    if ( !v12 || (v13 = EscapeXML(v12, &v36), v9 = v13, v7 = v36, v13 >= 0) )
    {
      v14 = (unsigned __int16 *)*((_QWORD *)this + 18);
      if ( !v14 || (v15 = EscapeXML(v14, &v37), v9 = v15, v8 = v37, v15 >= 0) )
      {
        try
        {
          if ( v8 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v8[v16] );
            if ( v16 > 0xFFFFFFFF )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v14);
          }
          else
          {
            LODWORD(v16) = 11;
          }
          if ( v6 )
          {
            if ( v7 )
            {
              v17 = (unsigned int)v16 + 76LL;
              if ( v17 < (unsigned int)v16 || v17 > 0xFFFFFFFF )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
            }
            else
            {
              v17 = (unsigned int)v16 + 71LL;
              if ( v17 < (unsigned int)v16 || v17 > 0xFFFFFFFF )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
            }
          }
          else
          {
            if ( !v7 )
              goto LABEL_24;
            v17 = (unsigned int)v16 + 61LL;
            if ( v17 < (unsigned int)v16 || v17 > 0xFFFFFFFF )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
          }
          LODWORD(v16) = v17;
LABEL_24:
          if ( v6 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v6[v18] );
          }
          else
          {
            v18 = 0;
          }
          v19 = (unsigned int)v16 + v18;
          if ( v19 < (unsigned int)v16 || v19 > 0xFFFFFFFF )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v18);
          if ( v7 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v7[v20] );
          }
          else
          {
            v20 = 0;
          }
          v21 = (unsigned int)v19;
          v22 = (unsigned int)v19 + v20;
          if ( v22 < v21 || v22 > 0xFFFFFFFF )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v20);
          v23 = (unsigned int)v22 + 1LL;
          if ( v23 > 0xFFFFFFFF )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v20);
          if ( (unsigned int)v23 < 4 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v20);
        }
        catch ( SafeIntException v61 )
        {
          v9 = -2147467259;
          v5 = v40;
          v6 = v35;
          v7 = v36;
          v8 = v37;
          goto LABEL_63;
        }
        v24 = v23 - 4;
        v34 = v24;
        if ( !v38 )
          goto LABEL_62;
        v25 = v24;
        v5 = operator new[](saturated_mul(v24, 2u));
        if ( !v5 )
        {
          v9 = -2147024882;
          goto LABEL_63;
        }
        if ( 2 * v25 > 0xFFFFFFFF )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v26);
        memset_0(v5, 0, (unsigned int)(2 * v25));
        if ( v6 )
        {
          v27 = L"Unspecified";
          v28 = v25;
          v29 = (unsigned __int16 *)v5;
          if ( v7 )
          {
            if ( v8 )
              v27 = v8;
            v30 = StringCchPrintfW((unsigned __int16 *)v5, v25, v51, v27, v7, v6);
            goto LABEL_60;
          }
          v33 = v6;
          v31 = (unsigned __int16 *)v60;
        }
        else
        {
          if ( !v7 )
          {
LABEL_61:
            *v38 = (unsigned __int16 *)v5;
            v24 = v34;
            v3 = v39;
LABEL_62:
            *v3 = v24;
            v5 = 0;
            goto LABEL_63;
          }
          v27 = L"Unspecified";
          v33 = v7;
          v31 = v44;
          v28 = v25;
          v29 = (unsigned __int16 *)v5;
        }
        if ( v8 )
          v27 = v8;
        v30 = StringCchPrintfW(v29, v28, v31, v27, v33);
LABEL_60:
        v9 = v30;
        if ( v30 < 0 )
          goto LABEL_63;
        goto LABEL_61;
      }
    }
  }
LABEL_63:
  operator delete(v6);
  operator delete(v7);
  operator delete(v8);
  operator delete(v5);
  LeaveCriticalSection(lpCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x180011ff4  push    rbx
0x180011ff6  push    rsi
0x180011ff7  push    rdi
0x180011ff8  push    r12
0x180011ffa  push    r13
0x180011ffc  push    r14
0x180011ffe  push    r15
0x180012000  sub     rsp, 240h
0x180012007  mov     [rsp+278h+var_208], 0FFFFFFFFFFFFFFFEh
0x180012010  mov     rax, cs:__security_cookie
0x180012017  xor     rax, rsp
0x18001201a  mov     [rsp+278h+var_40], rax
0x180012022  mov     [rsp+278h+var_228], r8
0x180012027  mov     r13, rdx
0x18001202a  mov     [rsp+278h+var_220], rdx
0x18001202f  mov     r15, rcx
0x180012032  lea     rax, [rcx+58h]
0x180012036  mov     [rsp+278h+lpCriticalSection], rax
0x18001203b  mov     [rsp+278h+var_200], rax
0x180012040  mov     rcx, rax; lpCriticalSection
0x180012043  call    cs:__imp_EnterCriticalSection
0x180012049  nop
0x18001204a  xor     r10d, r10d
0x18001204d  mov     r14d, r10d
0x180012050  mov     [rsp+278h+var_218], r10
0x180012055  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_1; "<PRINCIPAL><OBJECT><ID type=\"%s\">%s</"...
0x18001205c  movups  xmmword ptr [rsp+278h+var_178], xmm0
0x180012064  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_1+10h; "AL><OBJECT><ID type=\"%s\">%s</ID><NAME"...
0x18001206b  movups  [rsp+278h+var_168], xmm1
0x180012073  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_1+20h; "CT><ID type=\"%s\">%s</ID><NAME>%s</NAM"...
0x18001207a  movups  [rsp+278h+var_158], xmm0
0x180012082  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_1+30h; "ype=\"%s\">%s</ID><NAME>%s</NAME></OBJE"...
0x180012089  movups  [rsp+278h+var_148], xmm1
0x180012091  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_1+40h; ">%s</ID><NAME>%s</NAME></OBJECT></PRINC"...
0x180012098  movups  [rsp+278h+var_138], xmm0
0x1800120a0  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_1+50h; "<NAME>%s</NAME></OBJECT></PRINCIPAL>"
0x1800120a7  movups  [rsp+278h+var_128], xmm1
0x1800120af  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_1+60h; "</NAME></OBJECT></PRINCIPAL>"
0x1800120b6  movups  [rsp+278h+var_118], xmm0
0x1800120be  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_1+70h; "/OBJECT></PRINCIPAL>"
0x1800120c5  movups  [rsp+278h+var_108], xmm1
0x1800120cd  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_1+80h; "</PRINCIPAL>"
0x1800120d4  movups  xmmword ptr [rsp+278h+var_F8], xmm0
0x1800120dc  movups  xmm1, xmmword ptr cs:aPrincipalObjec_1+8Ah; "NCIPAL>"
0x1800120e3  movups  xmmword ptr [rsp+278h+var_F8+0Ah], xmm1
0x1800120eb  movaps  xmm0, xmmword ptr cs:aPrincipalObjec; "<PRINCIPAL><OBJECT><ID type=\"%s\" /><N"...
0x1800120f2  movups  [rsp+278h+var_D8], xmm0
0x1800120fa  movaps  xmm1, xmmword ptr cs:aPrincipalObjec+10h; "AL><OBJECT><ID type=\"%s\" /><NAME>%s</"...
0x180012101  movups  [rsp+278h+var_C8], xmm1
0x180012109  movaps  xmm0, xmmword ptr cs:aPrincipalObjec+20h; "CT><ID type=\"%s\" /><NAME>%s</NAME></O"...
0x180012110  movups  [rsp+278h+var_B8], xmm0
0x180012118  movaps  xmm1, xmmword ptr cs:aPrincipalObjec+30h; "ype=\"%s\" /><NAME>%s</NAME></OBJECT></"...
0x18001211f  movups  [rsp+278h+var_A8], xmm1
0x180012127  movaps  xmm0, xmmword ptr cs:aPrincipalObjec+40h; " /><NAME>%s</NAME></OBJECT></PRINCIPAL>"
0x18001212e  movups  [rsp+278h+var_98], xmm0
0x180012136  movaps  xmm1, xmmword ptr cs:aPrincipalObjec+50h; ">%s</NAME></OBJECT></PRINCIPAL>"
0x18001213d  movups  [rsp+278h+var_88], xmm1
0x180012145  movaps  xmm0, xmmword ptr cs:aPrincipalObjec+60h; "E></OBJECT></PRINCIPAL>"
0x18001214c  movups  [rsp+278h+var_78], xmm0
0x180012154  movaps  xmm1, xmmword ptr cs:aPrincipalObjec+70h; "CT></PRINCIPAL>"
0x18001215b  movups  [rsp+278h+var_68], xmm1
0x180012163  movaps  xmm0, xmmword ptr cs:aPrincipalObjec+80h; "NCIPAL>"
0x18001216a  movups  [rsp+278h+var_58], xmm0
0x180012172  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_0; "<PRINCIPAL><OBJECT><ID type=\"%s\">%s</"...
0x180012179  movaps  xmmword ptr [rsp+278h+var_1F8], xmm1
0x180012181  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_0+10h; "AL><OBJECT><ID type=\"%s\">%s</ID></OBJ"...
0x180012188  movaps  [rsp+278h+var_1E8], xmm0
0x180012190  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_0+20h; "CT><ID type=\"%s\">%s</ID></OBJECT></PR"...
0x180012197  movaps  [rsp+278h+var_1D8], xmm1
0x18001219f  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_0+30h; "ype=\"%s\">%s</ID></OBJECT></PRINCIPAL>"
0x1800121a6  movaps  [rsp+278h+var_1C8], xmm0
0x1800121ae  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_0+40h; ">%s</ID></OBJECT></PRINCIPAL>"
0x1800121b5  movaps  [rsp+278h+var_1B8], xmm1
0x1800121bd  movaps  xmm0, xmmword ptr cs:aPrincipalObjec_0+50h; "</OBJECT></PRINCIPAL>"
0x1800121c4  movaps  [rsp+278h+var_1A8], xmm0
0x1800121cc  movaps  xmm1, xmmword ptr cs:aPrincipalObjec_0+60h; "></PRINCIPAL>"
0x1800121d3  movaps  xmmword ptr [rsp+278h+var_198], xmm1
0x1800121db  movups  xmm0, xmmword ptr cs:aPrincipalObjec_0+6Ch; "NCIPAL>"
0x1800121e2  movups  xmmword ptr [rsp+278h+var_198+0Ch], xmm0
0x1800121ea  mov     r12d, r10d
0x1800121ed  mov     [rsp+278h+var_240], r10
0x1800121f2  mov     edi, r10d
0x1800121f5  mov     [rsp+278h+var_238], r10
0x1800121fa  mov     esi, r10d
0x1800121fd  mov     [rsp+278h+var_230], r10
0x180012202  test    r13, r13
0x180012205  jnz     short loc_180012211
0x180012207  mov     ebx, 80070057h
0x18001220c  jmp     loc_18001249A
0x180012211  mov     ebx, r10d
0x180012214  mov     [r13+0], r10d
0x180012218  mov     rcx, [r15+80h]; unsigned __int16 *
0x18001221f  test    rcx, rcx
0x180012222  jz      short loc_180012240
0x180012224  lea     rdx, [rsp+278h+var_240]; unsigned __int16 **
0x180012229  call    ?EscapeXML@@YAJPEAGPEAPEAG@Z; EscapeXML(ushort *,ushort * *)
0x18001222e  mov     ebx, eax
0x180012230  xor     r10d, r10d
0x180012233  mov     r12, [rsp+278h+var_240]
0x180012238  test    eax, eax
0x18001223a  js      loc_18001249A
0x180012240  mov     rcx, [r15+88h]; unsigned __int16 *
0x180012247  test    rcx, rcx
0x18001224a  jz      short loc_180012268
0x18001224c  lea     rdx, [rsp+278h+var_238]; unsigned __int16 **
0x180012251  call    ?EscapeXML@@YAJPEAGPEAPEAG@Z; EscapeXML(ushort *,ushort * *)
0x180012256  mov     ebx, eax
0x180012258  xor     r10d, r10d
0x18001225b  mov     rdi, [rsp+278h+var_238]
0x180012260  test    eax, eax
0x180012262  js      loc_18001249A
0x180012268  mov     rcx, [r15+90h]; unsigned __int16 *
0x18001226f  test    rcx, rcx
0x180012272  jz      short loc_180012290
0x180012274  lea     rdx, [rsp+278h+var_230]; unsigned __int16 **
0x180012279  call    ?EscapeXML@@YAJPEAGPEAPEAG@Z; EscapeXML(ushort *,ushort * *)
0x18001227e  mov     ebx, eax
0x180012280  xor     r10d, r10d
0x180012283  mov     rsi, [rsp+278h+var_230]
0x180012288  test    eax, eax
0x18001228a  js      loc_18001249A
0x180012290  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012294  test    rsi, rsi
0x180012297  jz      short loc_1800122B7
0x180012299  mov     rax, r8
0x18001229c  inc     rax
0x18001229f  cmp     [rsi+rax*2], r10w
0x1800122a4  jnz     short loc_18001229C
0x1800122a6  mov     r15d, 0FFFFFFFFh
0x1800122ac  cmp     rax, r15
0x1800122af  ja      loc_1800124EB
0x1800122b5  jmp     short loc_1800122C2
0x1800122b7  mov     eax, 0Bh
0x1800122bc  mov     r15d, 0FFFFFFFFh
0x1800122c2  test    r12, r12
0x1800122c5  jz      short loc_180012312
0x1800122c7  mov     eax, eax
0x1800122c9  test    rdi, rdi
0x1800122cc  jz      short loc_1800122E6
0x1800122ce  lea     rcx, [rax+4Ch]
0x1800122d2  cmp     rcx, rax
0x1800122d5  jb      loc_1800124F1
0x1800122db  cmp     rcx, r15
0x1800122de  ja      loc_1800124F1
0x1800122e4  jmp     short loc_1800122FC
0x1800122e6  lea     rcx, [rax+47h]
0x1800122ea  cmp     rcx, rax
0x1800122ed  jb      loc_1800124F6
0x1800122f3  cmp     rcx, r15
0x1800122f6  ja      loc_1800124F6
0x1800122fc  mov     eax, ecx
0x1800122fe  test    r12, r12
0x180012301  jz      short loc_180012331
0x180012303  mov     rcx, r8
0x180012306  inc     rcx
0x180012309  cmp     [r12+rcx*2], r10w
0x18001230e  jnz     short loc_180012306
0x180012310  jmp     short loc_180012334
0x180012312  test    rdi, rdi
0x180012315  jz      short loc_1800122FE
0x180012317  mov     eax, eax
0x180012319  lea     rcx, [rax+3Dh]
0x18001231d  cmp     rcx, rax
0x180012320  jb      loc_1800124FB
0x180012326  cmp     rcx, r15
0x180012329  ja      loc_1800124FB
0x18001232f  jmp     short loc_1800122FC
0x180012331  mov     rcx, r10
0x180012334  mov     eax, eax
0x180012336  lea     rdx, [rax+rcx]
0x18001233a  cmp     rdx, rax
0x18001233d  jb      loc_180012516
0x180012343  cmp     rdx, r15
0x180012346  ja      loc_180012516
0x18001234c  test    rdi, rdi
0x18001234f  jz      short loc_180012360
0x180012351  mov     rcx, r8
0x180012354  inc     rcx
0x180012357  cmp     [rdi+rcx*2], r10w
0x18001235c  jnz     short loc_180012354
0x18001235e  jmp     short loc_180012363
0x180012360  mov     rcx, r10
0x180012363  mov     eax, edx
0x180012365  lea     rdx, [rax+rcx]
0x180012369  cmp     rdx, rax
0x18001236c  jb      loc_180012511
0x180012372  cmp     rdx, r15
0x180012375  ja      loc_180012511
0x18001237b  mov     eax, edx
0x18001237d  inc     rax
0x180012380  cmp     rax, r15
0x180012383  ja      loc_18001250C
0x180012389  cmp     eax, 4
0x18001238c  jb      loc_180012500
0x180012392  add     eax, 0FFFFFFFCh
0x180012395  mov     [rsp+278h+var_248], eax
0x180012399  cmp     [rsp+278h+var_228], r10
0x18001239e  jz      loc_180012479
0x1800123a4  mov     r13d, eax
0x1800123a7  mov     eax, 2
0x1800123ac  mul     r13
0x1800123af  cmovb   rax, r8
0x1800123b3  mov     rcx, rax; unsigned __int64
0x1800123b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800123bb  mov     r14, rax
0x1800123be  test    rax, rax
0x1800123c1  jnz     short loc_1800123CD
0x1800123c3  mov     ebx, 8007000Eh
0x1800123c8  jmp     loc_18001249A
0x1800123cd  lea     rax, ds:0[r13*2]
0x1800123d5  cmp     rax, r15
0x1800123d8  ja      loc_180012506
0x1800123de  mov     r8d, eax; Size
0x1800123e1  xor     edx, edx; Val
0x1800123e3  mov     rcx, r14; void *
0x1800123e6  call    memset_0
0x1800123eb  xor     r10d, r10d
0x1800123ee  test    r12, r12
0x1800123f1  jz      short loc_180012434
0x1800123f3  lea     r9, aUnspecified; "Unspecified"
0x1800123fa  mov     rdx, r13; unsigned __int64
0x1800123fd  mov     rcx, r14; unsigned __int16 *
0x180012400  test    rdi, rdi
0x180012403  jz      short loc_180012425
0x180012405  test    rsi, rsi
0x180012408  cmovnz  r9, rsi
0x18001240c  mov     [rsp+278h+var_250], r12
0x180012411  mov     [rsp+278h+var_258], rdi
0x180012416  lea     r8, [rsp+278h+var_178]; unsigned __int16 *
0x18001241e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012423  jmp     short loc_18001245F
0x180012425  mov     [rsp+278h+var_258], r12
0x18001242a  lea     r8, [rsp+278h+var_D8]
0x180012432  jmp     short loc_180012453
0x180012434  test    rdi, rdi
0x180012437  jz      short loc_180012468
0x180012439  lea     r9, aUnspecified; "Unspecified"
0x180012440  mov     [rsp+278h+var_258], rdi
0x180012445  lea     r8, [rsp+278h+var_1F8]; unsigned __int16 *
0x18001244d  mov     rdx, r13; unsigned __int64
0x180012450  mov     rcx, r14; unsigned __int16 *
0x180012453  test    rsi, rsi
0x180012456  cmovnz  r9, rsi
0x18001245a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001245f  xor     r10d, r10d
0x180012462  mov     ebx, eax
0x180012464  test    eax, eax
0x180012466  js      short loc_18001249A
0x180012468  mov     rax, [rsp+278h+var_228]
0x18001246d  mov     [rax], r14
0x180012470  mov     eax, [rsp+278h+var_248]
0x180012474  mov     r13, [rsp+278h+var_220]
0x180012479  mov     [r13+0], eax
0x18001247d  mov     r14, r10
0x180012480  jmp     short loc_18001249A
0x180012482  mov     ebx, [rsp+278h+var_248]
0x180012486  mov     r14, [rsp+278h+var_218]
0x18001248b  mov     r12, [rsp+278h+var_240]
0x180012490  mov     rdi, [rsp+278h+var_238]
0x180012495  mov     rsi, [rsp+278h+var_230]
0x18001249a  mov     rcx, r12; Block
0x18001249d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800124a2  mov     rcx, rdi; Block
0x1800124a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800124aa  mov     rcx, rsi; Block
0x1800124ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800124b2  mov     rcx, r14; Block
0x1800124b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800124ba  nop
0x1800124bb  mov     rcx, [rsp+278h+lpCriticalSection]; lpCriticalSection
0x1800124c0  call    cs:__imp_LeaveCriticalSection
0x1800124c6  mov     eax, ebx
0x1800124c8  mov     rcx, [rsp+278h+var_40]
0x1800124d0  xor     rcx, rsp; StackCookie
0x1800124d3  call    __security_check_cookie
0x1800124d8  add     rsp, 240h
0x1800124df  pop     r15
0x1800124e1  pop     r14
0x1800124e3  pop     r13
0x1800124e5  pop     r12
0x1800124e7  pop     rdi
0x1800124e8  pop     rsi
0x1800124e9  pop     rbx
0x1800124ea  retn
0x1800124eb  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800124f1  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800124f6  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800124fb  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180012500  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180012506  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18001250c  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180012511  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180012516  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
