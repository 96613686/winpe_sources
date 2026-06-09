# CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)

- ea: `0x180017040`
- end: `0x1800175bb`
- name: `?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z`
- size: `1403`
- prototype: `__int64 __fastcall(CDetectURL *__hidden this, const struct CTxtPtr *, int, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016b44`
- `0x18001f408`

## callees

- `0x180017040`
- `0x18001d8b0`
- `0x180027f70`
- `0x18008cc28`
- `0x18008dbbc`
- `0x180091140`

## import_xrefs

- `KERNEL32!GetStringTypeExW` at `0x180017306`
- `KERNEL32!GetStringTypeExW` at `0x180017306`
- `KERNEL32!GetStringTypeExA` at `0x180017599`
- `KERNEL32!GetStringTypeExA` at `0x180017599`

## pseudocode

```c
__int64 __fastcall CDetectURL::MoveByDelimiters(
        CDetectURL *this,
        const struct CTxtPtr *a2,
        int a3,
        char a4,
        unsigned __int16 *a5)
{
  __int128 v5; // xmm0
  unsigned int v6; // r13d
  __int128 v7; // xmm1
  int v8; // r15d
  int v9; // r10d
  int v10; // r11d
  unsigned __int16 v11; // r14
  int v12; // ebp
  int v13; // ebx
  int v14; // eax
  void *v15; // rdx
  int v16; // esi
  int v17; // r9d
  __int64 v18; // rdi
  int v19; // ecx
  int v20; // eax
  int *v21; // r8
  int v22; // esi
  int v23; // r9d
  int v24; // r13d
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  unsigned int v30; // r9d
  unsigned int v31; // eax
  bool v32; // zf
  int v33; // ecx
  __int64 result; // rax
  int *v35; // rax
  WCHAR SrcStr; // [rsp+30h] [rbp-2B8h] BYREF
  WORD CharType[2]; // [rsp+38h] [rbp-2B0h] BYREF
  int v38; // [rsp+3Ch] [rbp-2ACh]
  int v39; // [rsp+40h] [rbp-2A8h]
  int v40; // [rsp+44h] [rbp-2A4h]
  int v41; // [rsp+48h] [rbp-2A0h]
  int v42; // [rsp+4Ch] [rbp-29Ch]
  int v43; // [rsp+50h] [rbp-298h]
  int v44; // [rsp+54h] [rbp-294h]
  CArrayBase *v45[2]; // [rsp+58h] [rbp-290h] BYREF
  __int128 v46; // [rsp+68h] [rbp-280h]
  LPCSTR lpSrcStr[66]; // [rsp+80h] [rbp-268h] BYREF
  int cchSrc; // [rsp+290h] [rbp-58h]

  v5 = *(_OWORD *)a2;
  v6 = 0;
  v7 = *((_OWORD *)a2 + 1);
  v38 = a3;
  v40 = 0;
  v8 = 0x3FFFFFFF;
  if ( (a4 & 0x20) == 0 )
    v8 = 512;
  v9 = a3;
  v10 = a4 & 0x10;
  v39 = v10;
  v42 = a4 & 1;
  v11 = 32;
  v41 = a4 & 2;
  v44 = a4 & 4;
  v43 = a4 & 8;
  v12 = 0;
  *(_OWORD *)v45 = v5;
  v46 = v7;
  while ( 2 )
  {
    if ( v9 != 1 )
    {
      v13 = -1;
      if ( v45[0] && *((_DWORD *)v45[0] + 2) )
      {
        v20 = *((_DWORD *)v45[0] + 2);
        if ( v20 > 0 && SLODWORD(v45[1]) < v20 && *(_QWORD *)v45[0] && SLODWORD(v45[1]) >= 0 )
          v21 = (int *)(*(_QWORD *)v45[0] + *((_DWORD *)v45[0] + 4) * LODWORD(v45[1]));
        else
          v21 = 0;
        v22 = 0;
        if ( v21 )
        {
          v23 = HIDWORD(v45[1]);
          if ( HIDWORD(v45[1]) )
            goto LABEL_27;
          if ( LODWORD(v45[1]) )
          {
            v35 = (int *)CArrayBase::Elem(v45[0], LODWORD(v45[1]) - 1);
            v21 = v35;
            if ( v35 )
            {
              v23 = *v35;
LABEL_27:
              v18 = *((_QWORD *)v21 + 1) + 2LL * v23;
              v22 = v23 - v21[4] / 2;
              if ( v22 > 0 )
                v18 += 2LL * (v21[5] / 2 - *v21);
              else
                v22 = v23;
              goto LABEL_29;
            }
          }
        }
      }
      else
      {
        v22 = 0;
      }
      v18 = 0;
LABEL_29:
      v16 = v22 + 1;
      goto LABEL_30;
    }
    v13 = 0;
    if ( !v45[0] || !*((_DWORD *)v45[0] + 2) )
    {
      v16 = 0;
LABEL_69:
      v18 = 0;
      goto LABEL_30;
    }
    v14 = *((_DWORD *)v45[0] + 2);
    if ( v14 > 0 && SLODWORD(v45[1]) < v14 && *(_QWORD *)v45[0] && SLODWORD(v45[1]) >= 0 )
      v15 = (void *)(*(_QWORD *)v45[0] + *((_DWORD *)v45[0] + 4) * LODWORD(v45[1]));
    else
      v15 = 0;
    v16 = 0;
    if ( !v15 )
      goto LABEL_69;
    v17 = HIDWORD(v45[1]);
    if ( HIDWORD(v45[1]) != *(_DWORD *)v15 )
      goto LABEL_14;
    if ( SLODWORD(v45[1]) >= *((_DWORD *)v45[0] + 2) - 1 )
      goto LABEL_69;
    v15 = CArrayBase::Elem(v45[0], LODWORD(v45[1]) + 1);
    if ( v15 )
    {
      v17 = 0;
LABEL_14:
      v18 = *((_QWORD *)v15 + 1) + 2LL * v17;
      v19 = *((_DWORD *)v15 + 4);
      if ( 2 * v17 >= v19 )
      {
        v16 = *(_DWORD *)v15 - v17;
        v18 += 2LL * (*((_DWORD *)v15 + 5) / 2 - *(_DWORD *)v15);
        if ( !v16 )
          v18 = 0;
      }
      else
      {
        v16 = v19 / 2 - v17;
        if ( v19 / 2 == v17 )
          v18 = 0;
      }
      goto LABEL_30;
    }
    v18 = 0;
LABEL_30:
    if ( !v18 )
      break;
    v24 = v41;
    while ( 1 )
    {
      v25 = -v13;
      if ( v13 > 0 )
        v25 = v13;
      if ( v25 >= v16 || v12 >= v8 )
        break;
      v26 = *(unsigned __int16 *)(v18 + 2LL * v13);
      if ( v26 == 32 || v26 - 9 <= 4 || (v26 | 1) == 0x2029 )
      {
LABEL_67:
        v29 = v42 == 0;
        goto LABEL_47;
      }
      v27 = v26 - 44032;
      if ( (unsigned __int16)v26 >= 0x3000u )
      {
        if ( v27 > 0x2BFF )
          goto LABEL_67;
        SrcStr = *(_WORD *)(v18 + 2LL * v13);
      }
      else
      {
        SrcStr = *(_WORD *)(v18 + 2LL * v13);
        if ( v27 > 0x2BFF )
        {
          if ( v26 - 55296 <= 0x7FF )
          {
            v28 = (v26 - 56320 <= 0x3FF) + 1;
          }
          else
          {
            v28 = *((char *)qword_1800A3ED0
                  + 64 * (unsigned __int64)*((unsigned __int8 *)qword_1800A3ED8 + ((unsigned __int64)v26 >> 6))
                  + (v26 & 0x3F));
            if ( v28 < 0 )
            {
              CharType[0] = 0;
              if ( CW32System::_dwPlatformId == 1 )
              {
                CStrIn::CStrIn((CStrIn *)lpSrcStr, &SrcStr, 1, 0);
                GetStringTypeExA(0, 4u, lpSrcStr[0], cchSrc, CharType);
                CConvertStr::Free((CConvertStr *)lpSrcStr);
              }
              else
              {
                GetStringTypeExW(0, 4u, &SrcStr, 1, CharType);
              }
              v10 = v39;
              v9 = v38;
              goto LABEL_46;
            }
          }
          if ( ((v28 - 10) & 0xFFFFFFFB) == 0 )
            goto LABEL_67;
        }
      }
LABEL_46:
      v29 = v24 == 0;
LABEL_47:
      if ( !v29 )
        break;
      if ( (v30 = *(unsigned __int16 *)(v18 + 2LL * v13), v30 - 44032 > 0x2BFF)
        && (v31 = *((char *)qword_1800A3ED0
                  + 64 * (unsigned __int64)*((unsigned __int8 *)qword_1800A3ED8 + ((unsigned __int64)v30 >> 6))
                  + (v30 & 0x3F)),
            v31 > 2)
        && (v31 - 4 > 2 || v30 == 47)
        && (((_WORD)v30 - 60) & 0xFFFD) != 0 )
      {
        v32 = v43 == 0;
      }
      else
      {
        v32 = v44 == 0;
      }
      if ( !v32 || v10 && v11 != 32 && *a5 == v11 || (v11 == 13 || v11 == 10) && !v24 )
        break;
      v13 += v9;
      v11 = v30;
      ++v12;
    }
    if ( v9 == -1 )
    {
      ++v13;
      --v16;
    }
    v6 = v13 + v40;
    v33 = -v13;
    v40 += v13;
    if ( v13 > 0 )
      v33 = v13;
    if ( v33 >= v16 )
    {
      CTxtPtr::AdvanceCp((CTxtPtr *)v45, v13);
      v9 = v38;
      v10 = v39;
      if ( v12 < v8 )
        continue;
    }
    break;
  }
  result = v6;
  if ( a5 )
    *a5 = v11;
  return result;
}

```

## disassembly

```asm
0x180017040  mov     [rsp+arg_0], rbx
0x180017045  push    rbp
0x180017046  push    rsi
0x180017047  push    rdi
0x180017048  push    r12
0x18001704a  push    r13
0x18001704c  push    r14
0x18001704e  push    r15
0x180017050  sub     rsp, 2B0h
0x180017057  mov     rax, cs:__security_cookie
0x18001705e  xor     rax, rsp
0x180017061  mov     [rsp+2E8h+var_48], rax
0x180017069  movups  xmm0, xmmword ptr [rdx]
0x18001706c  mov     r12, [rsp+2E8h+arg_20]
0x180017074  xor     r13d, r13d
0x180017077  movups  xmm1, xmmword ptr [rdx+10h]
0x18001707b  test    r9b, 20h
0x18001707f  mov     [rsp+2E8h+var_2AC], r8d
0x180017084  mov     eax, 200h
0x180017089  mov     [rsp+2E8h+var_2A4], r13d
0x18001708e  mov     r15d, 3FFFFFFFh
0x180017094  mov     r11d, r9d
0x180017097  cmovz   r15d, eax
0x18001709b  mov     r10d, r8d
0x18001709e  and     r11d, 10h
0x1800170a2  mov     eax, r9d
0x1800170a5  and     eax, 1
0x1800170a8  mov     [rsp+2E8h+var_2A8], r11d
0x1800170ad  mov     [rsp+2E8h+var_29C], eax
0x1800170b1  mov     r14d, 20h ; ' '
0x1800170b7  mov     eax, r9d
0x1800170ba  and     eax, 2
0x1800170bd  mov     [rsp+2E8h+var_2A0], eax
0x1800170c1  mov     eax, r9d
0x1800170c4  and     eax, 4
0x1800170c7  mov     [rsp+2E8h+var_294], eax
0x1800170cb  mov     eax, r9d
0x1800170ce  and     eax, 8
0x1800170d1  mov     [rsp+2E8h+var_298], eax
0x1800170d5  xor     ebp, ebp
0x1800170d7  movups  xmmword ptr [rsp+2E8h+var_290], xmm0
0x1800170dc  movups  [rsp+2E8h+var_280], xmm1
0x1800170e1  mov     rcx, [rsp+2E8h+var_290]; this
0x1800170e6  cmp     r10d, 1
0x1800170ea  jnz     loc_18001718B
0x1800170f0  xor     ebx, ebx
0x1800170f2  test    rcx, rcx
0x1800170f5  jz      loc_18001742E
0x1800170fb  cmp     [rcx+8], ebx
0x1800170fe  jz      loc_18001742E
0x180017104  mov     eax, [rcx+8]
0x180017107  mov     r8d, dword ptr [rsp+2E8h+var_290+8]
0x18001710c  test    eax, eax
0x18001710e  jle     loc_180017530
0x180017114  cmp     r8d, eax
0x180017117  jge     loc_180017530
0x18001711d  mov     r9, [rcx]
0x180017120  test    r9, r9
0x180017123  jz      loc_180017530
0x180017129  test    r8d, r8d
0x18001712c  js      loc_180017530
0x180017132  mov     eax, r8d
0x180017135  imul    eax, [rcx+10h]
0x180017139  movsxd  rdx, eax
0x18001713c  add     rdx, r9
0x18001713f  xor     esi, esi
0x180017141  test    rdx, rdx
0x180017144  jz      loc_180017430
0x18001714a  mov     r9d, dword ptr [rsp+2E8h+var_290+0Ch]
0x18001714f  cmp     r9d, [rdx]
0x180017152  jz      loc_1800174AC
0x180017158  mov     rax, [rdx+8]
0x18001715c  movsxd  rcx, r9d
0x18001715f  lea     rdi, [rax+rcx*2]
0x180017163  mov     ecx, [rdx+10h]
0x180017166  lea     eax, [r9+r9]
0x18001716a  cmp     eax, ecx
0x18001716c  jge     loc_180017461
0x180017172  mov     eax, ecx
0x180017174  cdq
0x180017175  sub     eax, edx
0x180017177  sar     eax, 1
0x180017179  mov     esi, eax
0x18001717b  xor     eax, eax
0x18001717d  sub     esi, r9d
0x180017180  test    esi, esi
0x180017182  cmovz   rdi, rax
0x180017186  jmp     loc_180017219
0x18001718b  mov     ebx, 0FFFFFFFFh
0x180017190  test    rcx, rcx
0x180017193  jz      loc_180017437
0x180017199  cmp     dword ptr [rcx+8], 0
0x18001719d  jz      loc_180017437
0x1800171a3  mov     eax, [rcx+8]
0x1800171a6  mov     edx, dword ptr [rsp+2E8h+var_290+8]
0x1800171aa  test    eax, eax
0x1800171ac  jle     loc_180017537
0x1800171b2  cmp     edx, eax
0x1800171b4  jge     loc_180017537
0x1800171ba  mov     r9, [rcx]
0x1800171bd  test    r9, r9
0x1800171c0  jz      loc_180017537
0x1800171c6  test    edx, edx
0x1800171c8  js      loc_180017537
0x1800171ce  mov     eax, edx
0x1800171d0  imul    eax, [rcx+10h]
0x1800171d4  movsxd  r8, eax
0x1800171d7  add     r8, r9
0x1800171da  xor     esi, esi
0x1800171dc  test    r8, r8
0x1800171df  jz      loc_180017439
0x1800171e5  mov     r9d, dword ptr [rsp+2E8h+var_290+0Ch]
0x1800171ea  test    r9d, r9d
0x1800171ed  jz      loc_18001750D
0x1800171f3  mov     rax, [r8+8]
0x1800171f7  mov     esi, r9d
0x1800171fa  movsxd  rcx, r9d
0x1800171fd  lea     rdi, [rax+rcx*2]
0x180017201  mov     eax, [r8+10h]
0x180017205  cdq
0x180017206  sub     eax, edx
0x180017208  sar     eax, 1
0x18001720a  sub     esi, eax
0x18001720c  test    esi, esi
0x18001720e  jg      loc_1800174F6
0x180017214  mov     esi, r9d
0x180017217  inc     esi
0x180017219  test    rdi, rdi
0x18001721c  jz      loc_1800173DE
0x180017222  mov     r13d, [rsp+2E8h+var_2A0]
0x180017227  mov     eax, ebx
0x180017229  neg     eax
0x18001722b  cmovs   eax, ebx
0x18001722e  cmp     eax, esi
0x180017230  jge     loc_1800173B8
0x180017236  cmp     ebp, r15d
0x180017239  jge     loc_1800173B8
0x18001723f  movsxd  rax, ebx
0x180017242  movzx   eax, word ptr [rdi+rax*2]
0x180017246  cmp     eax, 20h ; ' '
0x180017249  jz      loc_180017424
0x18001724f  lea     ecx, [rax-9]
0x180017252  cmp     ecx, 4
0x180017255  jbe     loc_180017424
0x18001725b  mov     ecx, eax
0x18001725d  or      ecx, 1
0x180017260  cmp     ecx, 2029h
0x180017266  jz      loc_180017424
0x18001726c  mov     ecx, 3000h
0x180017271  cmp     ax, cx
0x180017274  lea     ecx, [rax-0AC00h]
0x18001727a  jnb     loc_180017440
0x180017280  mov     [rsp+2E8h+SrcStr], ax
0x180017285  cmp     ecx, 2BFFh
0x18001728b  jbe     loc_180017316
0x180017291  lea     ecx, [rax-0D800h]
0x180017297  cmp     ecx, 7FFh
0x18001729d  jbe     loc_180017547
0x1800172a3  mov     r8d, eax
0x1800172a6  mov     ecx, eax
0x1800172a8  mov     rax, cs:qword_1800A3ED8
0x1800172af  and     r8d, 3Fh
0x1800172b3  shr     rcx, 6
0x1800172b7  movzx   edx, byte ptr [rcx+rax]
0x1800172bb  mov     rcx, cs:qword_1800A3ED0
0x1800172c2  shl     rdx, 6
0x1800172c6  add     rcx, rdx
0x1800172c9  movsx   ecx, byte ptr [r8+rcx]
0x1800172ce  test    ecx, ecx
0x1800172d0  jns     loc_180017416
0x1800172d6  xor     eax, eax
0x1800172d8  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x1800172df  mov     [rsp+2E8h+CharType], ax
0x1800172e4  jz      loc_18001755D
0x1800172ea  lea     rax, [rsp+2E8h+CharType]
0x1800172ef  mov     r9d, 1; cchSrc
0x1800172f5  lea     r8, [rsp+2E8h+SrcStr]; lpSrcStr
0x1800172fa  mov     [rsp+2E8h+lpCharType], rax; lpCharType
0x1800172ff  mov     edx, 4; dwInfoType
0x180017304  xor     ecx, ecx; Locale
0x180017306  call    cs:__imp_GetStringTypeExW
0x18001730c  mov     r11d, [rsp+2E8h+var_2A8]
0x180017311  mov     r10d, [rsp+2E8h+var_2AC]
0x180017316  test    r13d, r13d
0x180017319  jnz     loc_1800173B8
0x18001731f  movsxd  rax, ebx
0x180017322  movzx   r9d, word ptr [rdi+rax*2]
0x180017327  lea     eax, [r9-0AC00h]
0x18001732e  cmp     eax, 2BFFh
0x180017333  jbe     short loc_180017384
0x180017335  mov     rax, cs:qword_1800A3ED8
0x18001733c  mov     r8d, r9d
0x18001733f  and     r8d, 3Fh
0x180017343  mov     ecx, r9d
0x180017346  shr     rcx, 6
0x18001734a  movzx   edx, byte ptr [rcx+rax]
0x18001734e  mov     rcx, cs:qword_1800A3ED0
0x180017355  shl     rdx, 6
0x180017359  add     rcx, rdx
0x18001735c  movsx   eax, byte ptr [r8+rcx]
0x180017361  cmp     eax, 2
0x180017364  jbe     short loc_180017384
0x180017366  add     eax, 0FFFFFFFCh
0x180017369  cmp     eax, 2
0x18001736c  jbe     loc_180017452
0x180017372  lea     eax, [r9-3Ch]
0x180017376  mov     ecx, 0FFFDh
0x18001737b  test    cx, ax
0x18001737e  jnz     loc_1800175B1
0x180017384  cmp     [rsp+2E8h+var_294], 0
0x180017389  jnz     short loc_1800173B8
0x18001738b  test    r11d, r11d
0x18001738e  jnz     loc_180017491
0x180017394  cmp     r14w, 0Dh
0x180017399  jz      loc_180017483
0x18001739f  cmp     r14w, 0Ah
0x1800173a4  jz      loc_180017483
0x1800173aa  add     ebx, r10d
0x1800173ad  movzx   r14d, r9w
0x1800173b1  inc     ebp
0x1800173b3  jmp     loc_180017227
0x1800173b8  mov     r13d, [rsp+2E8h+var_2A4]
0x1800173bd  cmp     r10d, 0FFFFFFFFh
0x1800173c1  jnz     short loc_1800173C7
0x1800173c3  inc     ebx
0x1800173c5  dec     esi
0x1800173c7  add     r13d, ebx
0x1800173ca  mov     ecx, ebx
0x1800173cc  neg     ecx
0x1800173ce  mov     [rsp+2E8h+var_2A4], r13d
0x1800173d3  cmovs   ecx, ebx
0x1800173d6  cmp     ecx, esi
0x1800173d8  jge     loc_1800174D2
0x1800173de  mov     eax, r13d
0x1800173e1  test    r12, r12
0x1800173e4  jz      short loc_1800173EB
0x1800173e6  mov     [r12], r14w
0x1800173eb  mov     rcx, [rsp+2E8h+var_48]
0x1800173f3  xor     rcx, rsp; StackCookie
0x1800173f6  call    __security_check_cookie
0x1800173fb  mov     rbx, [rsp+2E8h+arg_0]
0x180017403  add     rsp, 2B0h
0x18001740a  pop     r15
0x18001740c  pop     r14
0x18001740e  pop     r13
0x180017410  pop     r12
0x180017412  pop     rdi
0x180017413  pop     rsi
0x180017414  pop     rbp
0x180017415  retn
0x180017416  lea     eax, [rcx-0Ah]
0x180017419  test    eax, 0FFFFFFFBh
0x18001741e  jnz     loc_180017316
0x180017424  cmp     [rsp+2E8h+var_29C], 0
0x180017429  jmp     loc_180017319
0x18001742e  xor     esi, esi
0x180017430  xor     edi, edi
0x180017432  jmp     loc_180017219
0x180017437  xor     esi, esi
0x180017439  xor     edi, edi
0x18001743b  jmp     loc_180017217
0x180017440  cmp     ecx, 2BFFh
0x180017446  ja      short loc_180017424
0x180017448  mov     [rsp+2E8h+SrcStr], ax
0x18001744d  jmp     loc_180017316
0x180017452  cmp     r9d, 2Fh ; '/'
0x180017456  jnz     loc_180017384
0x18001745c  jmp     loc_180017372
0x180017461  mov     esi, [rdx]
0x180017463  mov     eax, [rdx+14h]
0x180017466  cdq
0x180017467  sub     eax, edx
0x180017469  sar     eax, 1
0x18001746b  sub     eax, esi
0x18001746d  sub     esi, r9d
0x180017470  cdqe
0x180017472  lea     rdi, [rdi+rax*2]
0x180017476  xor     eax, eax
0x180017478  test    esi, esi
0x18001747a  cmovz   rdi, rax
0x18001747e  jmp     loc_180017219
0x180017483  test    r13d, r13d
0x180017486  jnz     loc_1800173AA
0x18001748c  jmp     loc_1800173B8
0x180017491  cmp     r14w, 20h ; ' '
0x180017496  jz      loc_180017394
0x18001749c  cmp     [r12], r14w
0x1800174a1  jnz     loc_180017394
0x1800174a7  jmp     loc_1800173B8
0x1800174ac  mov     eax, [rcx+8]
0x1800174af  dec     eax
0x1800174b1  cmp     r8d, eax
0x1800174b4  jge     loc_180017430
0x1800174ba  lea     edx, [r8+1]; int
0x1800174be  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x1800174c3  mov     rdx, rax
0x1800174c6  test    rax, rax
0x1800174c9  jnz     short loc_18001753F
0x1800174cb  xor     edi, edi
0x1800174cd  jmp     loc_180017219
  ... truncated ...
```
