# pcfLocateCFONT(HDC__ *,_DC_ATTR *,uint,void *,uint,int)

- ea: `0x180071120`
- end: `0x180071544`
- name: `?pcfLocateCFONT@@YA?AV?$ReturnValueTracer@PEAU_CFONT@@@@PEAUHDC__@@PEAU_DC_ATTR@@IPEAXIH@Z`
- size: `1060`
- prototype: ``
- caller_count: `8`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000d500`
- `0x180015c70`
- `0x180037eec`
- `0x1800528a0`
- `0x1800588fc`
- `0x18005caf0`
- `0x180071550`
- `0x180071750`

## callees

- `0x18000ed60`
- `0x180036584`
- `0x180036b10`
- `0x180036be4`
- `0x180036e38`
- `0x180038290`
- `0x18004b0ec`
- `0x1800710c4`
- `0x180071120`
- `0x180085010`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18007123c`
- `GDI32!GdiGetEntry` at `0x18007123c`
- `GDI32!gW32PID` at `0x180071275`
- `GDI32!gCookie` at `0x180071299`
- `GDI32!gMaxGdiHandleCount` at `0x180071217`
- `win32u!NtGdiComputeXformCoefficients` at `0x1800711a3`
- `win32u!NtGdiComputeXformCoefficients` at `0x1800711a3`

## pseudocode

```c
__int64 __fastcall pcfLocateCFONT(
        __int64 a1,
        HDC a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        int a7)
{
  __int64 v11; // r15
  int CodePage; // eax
  unsigned int v13; // eax
  int v14; // ecx
  struct _CFONT *v15; // rdx
  struct _CFONT *i; // rbx
  unsigned int v18; // eax
  __int64 v19; // rsi
  struct _CFONT **v20; // rax
  struct _CFONT *CFONT; // rax
  unsigned __int8 *v22; // r8
  int v23; // eax
  int j; // ecx
  __int64 v25; // rax
  unsigned __int8 *v26; // rax
  int v27; // eax
  unsigned int v28; // r9d
  int v29; // eax
  unsigned int v30; // r9d
  __int128 v31; // [rsp+30h] [rbp-58h] BYREF
  __int64 v32; // [rsp+40h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  }
  if ( (int)GetDCDpiScaleValue(a2) > 1 )
    goto LABEL_18;
  if ( (unsigned int)QueryFontAssocStatus() )
    goto LABEL_18;
  v11 = *(_QWORD *)(a3 + 296);
  if ( (*(_BYTE *)(a3 + 152) & 0x20) != 0 )
    goto LABEL_18;
  if ( (*(_DWORD *)(a3 + 340) & 0xE000) != 0 || (*(_BYTE *)(a3 + 64) & 1) == 0 )
  {
    if ( !(unsigned int)NtGdiComputeXformCoefficients(a2) )
      *(_DWORD *)(a3 + 152) |= 0x20u;
    if ( (*(_BYTE *)(a3 + 152) & 0x20) != 0 )
      goto LABEL_18;
  }
  if ( guintDBCScp != -1 )
  {
    CodePage = GetCodePage(a2);
    if ( guintDBCScp != CodePage )
    {
      v13 = CodePage - 932;
      if ( v13 <= 0x12 )
      {
        v14 = 393233;
        if ( _bittest(&v14, v13) )
        {
          *(_DWORD *)(a3 + 152) |= 0x20u;
LABEL_18:
          v15 = 0;
          goto LABEL_19;
        }
      }
    }
  }
  i = 0;
  v18 = HANDLE_TO_INDEX(v11);
  if ( v18 < gMaxGdiHandleCount
    && (v32 = 0, v31 = 0, (int)GdiGetEntry(v18, &v31) >= 0)
    && BYTE14(v31) == 10
    && WORD6(v31) == WORD1(v11)
    && (DWORD2(v31) & 0xFFFFFFFE) == gW32PID
    && v32
    && (v19 = gCookie ^ __ROR8__(v32, 64 - (gCookie & 0x3Fu))) != 0
    && (v20 = *(struct _CFONT ***)(v19 + 8)) != 0
    && (*(_BYTE *)v19 & 1) == 0 )
  {
    for ( i = *v20; ; i = *(struct _CFONT **)i )
    {
      if ( !i )
      {
        CFONT = pcfCreateCFONT(a2, (struct _DC_ATTR *)a3, a4, a5, a6, a7);
        i = CFONT;
        if ( CFONT )
        {
          *((_QWORD *)CFONT + 2) = v11;
          if ( (*(_BYTE *)a3 & 2) != 0 )
          {
            *((_QWORD *)CFONT + 5) = 0;
            *((_QWORD *)CFONT + 1) = 0;
          }
          else
          {
            *((_QWORD *)CFONT + 5) = a2;
            *((_QWORD *)CFONT + 1) = *(_QWORD *)(a3 + 352);
            *(_QWORD *)(a3 + 352) = CFONT;
          }
          *(_QWORD *)CFONT = **(_QWORD **)(v19 + 8);
          **(_QWORD **)(v19 + 8) = CFONT;
        }
        goto LABEL_81;
      }
      if ( (!*((_QWORD *)i + 5) && (*(_BYTE *)a3 & 2) != 0 || *((HDC *)i + 5) == a2)
        && *((float *)i + 12) == *(float *)(a3 + 32)
        && *((float *)i + 13) == *(float *)(a3 + 44) )
      {
        break;
      }
    }
    ++*((_DWORD *)i + 6);
    if ( (*((_BYTE *)i + 28) & 1) != 0 )
      goto LABEL_41;
    v22 = a5;
    v23 = *((_DWORD *)i + 7) & 0x20;
    if ( a5 )
    {
      if ( v23 )
      {
        if ( a7 )
        {
          if ( (*((_BYTE *)i + 28) & 4) != 0 )
          {
            for ( j = a6; j > 0; ++v22 )
            {
              v25 = *v22;
              if ( *((_WORD *)gpwcDBCSCharSet + v25) == 0xFFFF )
              {
                v26 = v22 + 1;
                if ( !j )
                  v26 = v22;
                v22 = v26;
                v27 = j - 1;
                if ( !j )
                  v27 = 0;
                j = v27;
              }
              else if ( *((_WORD *)i + v25 + 42) == 0xFFFF )
              {
                break;
              }
              --j;
            }
            v28 = 0;
            if ( j >= 0 )
              v28 = j;
          }
          else
          {
            v28 = a6;
            if ( !a6 )
              goto LABEL_81;
            do
            {
              if ( *((_WORD *)i + *v22 + 42) == 0xFFFF )
                break;
              ++v22;
              --v28;
            }
            while ( v28 );
          }
        }
        else
        {
          v28 = a6;
          if ( !a6 )
            goto LABEL_81;
          do
          {
            if ( *((_WORD *)i + *(unsigned __int16 *)v22 + 42) == 0xFFFF )
              break;
            v22 += 2;
            --v28;
          }
          while ( v28 );
        }
      }
      else
      {
        v28 = a6;
      }
      if ( !v28 )
        goto LABEL_81;
      v29 = bFillWidthTableForGTE(a2, i, v22, v28, a7);
    }
    else
    {
      v30 = a6;
      if ( !v23 || ((a4 | (a4 + a6)) & 0xFFFFFF00) != 0 )
      {
LABEL_74:
        if ( !v30 )
          goto LABEL_81;
      }
      else
      {
        if ( !a6 )
          goto LABEL_81;
        while ( *((_WORD *)i + a4 + 42) != 0xFFFF )
        {
          ++a4;
          if ( !--v30 )
            goto LABEL_74;
        }
      }
      v29 = bFillWidthTableForGCW(a2, i, a4, v30);
    }
    if ( v29 == -1 )
    {
      --*((_DWORD *)i + 6);
      *(_DWORD *)(a3 + 152) |= 0x20u;
      i = 0;
    }
  }
  else
  {
    *(_DWORD *)(a3 + 152) |= 0x20u;
  }
LABEL_81:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  }
LABEL_41:
  v15 = i;
LABEL_19:
  ReturnValueTracer<_CFONT *>::ReturnValueTracer<_CFONT *>(a1, v15);
  return a1;
}

```

## disassembly

```asm
0x180071120  push    rbx
0x180071122  push    rbp
0x180071123  push    rsi
0x180071124  push    rdi
0x180071125  push    r12
0x180071127  push    r14
0x180071129  push    r15
0x18007112b  sub     rsp, 50h
0x18007112f  mov     r14d, r9d
0x180071132  mov     rdi, r8
0x180071135  mov     r12, rdx
0x180071138  mov     rbp, rcx
0x18007113b  mov     rcx, cs:WPP_GLOBAL_Control
0x180071142  lea     rax, WPP_GLOBAL_Control
0x180071149  cmp     rcx, rax
0x18007114c  jz      short loc_180071168
0x18007114e  test    byte ptr [rcx+1Ch], 1
0x180071152  jz      short loc_180071168
0x180071154  cmp     byte ptr [rcx+19h], 5
0x180071158  jb      short loc_180071168
0x18007115a  mov     rcx, [rcx+10h]
0x18007115e  mov     edx, 0Ah
0x180071163  call    WPP_SF_
0x180071168  mov     rcx, r12
0x18007116b  call    GetDCDpiScaleValue
0x180071170  cmp     eax, 1
0x180071173  jg      short loc_1800711F1
0x180071175  call    QueryFontAssocStatus
0x18007117a  test    eax, eax
0x18007117c  jnz     short loc_1800711F1
0x18007117e  test    byte ptr [rdi+98h], 20h
0x180071185  mov     r15, [rdi+128h]
0x18007118c  jnz     short loc_1800711F1
0x18007118e  test    dword ptr [rdi+154h], 0E000h
0x180071198  jnz     short loc_1800711A0
0x18007119a  test    byte ptr [rdi+40h], 1
0x18007119e  jnz     short loc_1800711BD
0x1800711a0  mov     rcx, r12
0x1800711a3  call    cs:__imp_NtGdiComputeXformCoefficients
0x1800711a9  test    eax, eax
0x1800711ab  jnz     short loc_1800711B4
0x1800711ad  or      dword ptr [rdi+98h], 20h
0x1800711b4  test    byte ptr [rdi+98h], 20h
0x1800711bb  jnz     short loc_1800711F1
0x1800711bd  cmp     cs:guintDBCScp, 0FFFFFFFFh
0x1800711c4  jz      short loc_18007120D
0x1800711c6  mov     rcx, r12
0x1800711c9  call    GetCodePage
0x1800711ce  cmp     cs:guintDBCScp, eax
0x1800711d4  jz      short loc_18007120D
0x1800711d6  add     eax, 0FFFFFC5Ch
0x1800711db  cmp     eax, 12h
0x1800711de  ja      short loc_18007120D
0x1800711e0  mov     ecx, 60011h
0x1800711e5  bt      ecx, eax
0x1800711e8  jnb     short loc_18007120D
0x1800711ea  or      dword ptr [rdi+98h], 20h
0x1800711f1  xor     edx, edx
0x1800711f3  mov     rcx, rbp
0x1800711f6  call    ??0?$ReturnValueTracer@PEAU_CFONT@@@@QEAA@QEAU_CFONT@@@Z; ReturnValueTracer<_CFONT *>::ReturnValueTracer<_CFONT *>(_CFONT * const)
0x1800711fb  mov     rax, rbp
0x1800711fe  add     rsp, 50h
0x180071202  pop     r15
0x180071204  pop     r14
0x180071206  pop     r12
0x180071208  pop     rdi
0x180071209  pop     rsi
0x18007120a  pop     rbp
0x18007120b  pop     rbx
0x18007120c  retn
0x18007120d  mov     rcx, r15
0x180071210  xor     ebx, ebx
0x180071212  call    HANDLE_TO_INDEX
0x180071217  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18007121e  cmp     eax, [rcx]
0x180071220  jnb     loc_1800714FF
0x180071226  xor     ecx, ecx
0x180071228  lea     rdx, [rsp+88h+var_58]
0x18007122d  mov     [rsp+88h+var_48], rcx
0x180071232  xorps   xmm0, xmm0
0x180071235  mov     ecx, eax
0x180071237  movups  [rsp+88h+var_58], xmm0
0x18007123c  call    cs:__imp_GdiGetEntry
0x180071242  test    eax, eax
0x180071244  js      loc_1800714FF
0x18007124a  cmp     byte ptr [rsp+88h+var_58+0Eh], 0Ah
0x18007124f  jnz     loc_1800714FF
0x180071255  movzx   eax, byte ptr [rsp+88h+var_58+0Ch]
0x18007125a  movzx   ecx, byte ptr [rsp+88h+var_58+0Dh]
0x18007125f  shl     cx, 8
0x180071263  or      cx, ax
0x180071266  mov     eax, r15d
0x180071269  shr     eax, 10h
0x18007126c  cmp     cx, ax
0x18007126f  jnz     loc_1800714FF
0x180071275  mov     rax, cs:__imp_gW32PID
0x18007127c  mov     ecx, dword ptr [rsp+88h+var_58+8]
0x180071280  and     ecx, 0FFFFFFFEh
0x180071283  cmp     ecx, [rax]
0x180071285  jnz     loc_1800714FF
0x18007128b  mov     rsi, [rsp+88h+var_48]
0x180071290  test    rsi, rsi
0x180071293  jz      loc_1800714FF
0x180071299  mov     rax, cs:__imp_gCookie
0x1800712a0  lea     ecx, [rbx+40h]
0x1800712a3  mov     rdx, [rax]
0x1800712a6  mov     eax, edx
0x1800712a8  and     eax, 3Fh
0x1800712ab  sub     ecx, eax
0x1800712ad  ror     rsi, cl
0x1800712b0  xor     rsi, rdx
0x1800712b3  jz      loc_1800714FF
0x1800712b9  mov     rax, [rsi+8]
0x1800712bd  test    rax, rax
0x1800712c0  jz      loc_1800714FF
0x1800712c6  test    byte ptr [rsi], 1
0x1800712c9  jnz     loc_1800714FF
0x1800712cf  mov     rbx, [rax]
0x1800712d2  jmp     short loc_180071303
0x1800712d4  cmp     qword ptr [rbx+28h], 0
0x1800712d9  jnz     short loc_1800712E0
0x1800712db  test    byte ptr [rdi], 2
0x1800712de  jnz     short loc_1800712E6
0x1800712e0  cmp     [rbx+28h], r12
0x1800712e4  jnz     short loc_180071300
0x1800712e6  movss   xmm0, dword ptr [rbx+30h]
0x1800712eb  ucomiss xmm0, dword ptr [rdi+20h]
0x1800712ef  jp      short loc_180071300
0x1800712f1  jnz     short loc_180071300
0x1800712f3  movss   xmm0, dword ptr [rbx+34h]
0x1800712f8  ucomiss xmm0, dword ptr [rdi+2Ch]
0x1800712fc  jp      short loc_180071300
0x1800712fe  jz      short loc_180071362
0x180071300  mov     rbx, [rbx]
0x180071303  test    rbx, rbx
0x180071306  jnz     short loc_1800712D4
0x180071308  mov     eax, [rsp+88h+arg_30]
0x18007130f  mov     r8d, r14d; unsigned int
0x180071312  mov     r9, [rsp+88h+arg_20]; void *
0x18007131a  mov     rdx, rdi; struct _DC_ATTR *
0x18007131d  mov     [rsp+88h+var_60], eax; int
0x180071321  mov     rcx, r12; HDC
0x180071324  mov     eax, [rsp+88h+arg_28]
0x18007132b  mov     [rsp+88h+var_68], eax; unsigned int
0x18007132f  call    ?pcfCreateCFONT@@YAPEAU_CFONT@@PEAUHDC__@@PEAU_DC_ATTR@@IPEAXIH@Z; pcfCreateCFONT(HDC__ *,_DC_ATTR *,uint,void *,uint,int)
0x180071334  mov     rbx, rax
0x180071337  test    rax, rax
0x18007133a  jz      loc_180071506
0x180071340  mov     [rax+10h], r15
0x180071344  test    byte ptr [rdi], 2
0x180071347  jz      loc_1800714D6
0x18007134d  mov     qword ptr [rax+28h], 0
0x180071355  mov     qword ptr [rax+8], 0
0x18007135d  jmp     loc_1800714EC
0x180071362  inc     dword ptr [rbx+18h]
0x180071365  test    byte ptr [rbx+1Ch], 1
0x180071369  jz      short loc_180071373
0x18007136b  mov     rdx, rbx
0x18007136e  jmp     loc_1800711F3
0x180071373  mov     eax, [rbx+1Ch]
0x180071376  mov     r8, [rsp+88h+arg_20]; void *
0x18007137e  and     eax, 20h
0x180071381  test    r8, r8
0x180071384  jz      loc_180071479
0x18007138a  mov     r10d, [rsp+88h+arg_30]
0x180071392  test    eax, eax
0x180071394  jz      loc_180071456
0x18007139a  test    r10d, r10d
0x18007139d  jz      loc_180071429
0x1800713a3  test    byte ptr [rbx+1Ch], 4
0x1800713a7  jz      short loc_1800713FD
0x1800713a9  mov     ecx, [rsp+88h+arg_28]
0x1800713b0  test    ecx, ecx
0x1800713b2  jle     short loc_1800713F2
0x1800713b4  mov     r9, cs:gpwcDBCSCharSet
0x1800713bb  mov     edx, 0FFFFh
0x1800713c0  movzx   eax, byte ptr [r8]
0x1800713c4  cmp     [r9+rax*2], dx
0x1800713c9  jnz     short loc_1800713E2
0x1800713cb  test    ecx, ecx
0x1800713cd  lea     rax, [r8+1]
0x1800713d1  cmovz   rax, r8
0x1800713d5  mov     r8, rax
0x1800713d8  lea     eax, [rcx-1]
0x1800713db  cmovz   eax, ecx
0x1800713de  mov     ecx, eax
0x1800713e0  jmp     short loc_1800713E9
0x1800713e2  cmp     [rbx+rax*2+54h], dx
0x1800713e7  jz      short loc_1800713F2
0x1800713e9  dec     ecx
0x1800713eb  inc     r8
0x1800713ee  test    ecx, ecx
0x1800713f0  jg      short loc_1800713C0
0x1800713f2  xor     r9d, r9d
0x1800713f5  test    ecx, ecx
0x1800713f7  cmovns  r9d, ecx
0x1800713fb  jmp     short loc_18007145E
0x1800713fd  mov     r9d, [rsp+88h+arg_28]
0x180071405  test    r9d, r9d
0x180071408  jz      loc_180071506
0x18007140e  mov     edx, 0FFFFh
0x180071413  movzx   eax, byte ptr [r8]
0x180071417  cmp     [rbx+rax*2+54h], dx
0x18007141c  jz      short loc_18007145E
0x18007141e  inc     r8
0x180071421  add     r9d, 0FFFFFFFFh
0x180071425  jnz     short loc_180071413
0x180071427  jmp     short loc_18007145E
0x180071429  mov     r9d, [rsp+88h+arg_28]
0x180071431  test    r9d, r9d
0x180071434  jz      loc_180071506
0x18007143a  mov     edx, 0FFFFh
0x18007143f  movzx   eax, word ptr [r8]
0x180071443  cmp     [rbx+rax*2+54h], dx
0x180071448  jz      short loc_18007145E
0x18007144a  add     r8, 2
0x18007144e  add     r9d, 0FFFFFFFFh
0x180071452  jnz     short loc_18007143F
0x180071454  jmp     short loc_18007145E
0x180071456  mov     r9d, [rsp+88h+arg_28]; unsigned int
0x18007145e  test    r9d, r9d
0x180071461  jz      loc_180071506
0x180071467  mov     rdx, rbx; struct _CFONT *
0x18007146a  mov     [rsp+88h+var_68], r10d; int
0x18007146f  mov     rcx, r12; HDC
0x180071472  call    ?bFillWidthTableForGTE@@YAHPEAUHDC__@@PEAU_CFONT@@PEAXIH@Z; bFillWidthTableForGTE(HDC__ *,_CFONT *,void *,uint,int)
0x180071477  jmp     short loc_1800714C3
0x180071479  mov     r9d, [rsp+88h+arg_28]
0x180071481  test    eax, eax
0x180071483  jz      short loc_1800714B0
0x180071485  lea     eax, [r14+r9]
0x180071489  or      eax, r14d
0x18007148c  test    eax, 0FFFFFF00h
0x180071491  jnz     short loc_1800714B0
0x180071493  test    r9d, r9d
0x180071496  jz      short loc_180071506
0x180071498  mov     edx, 0FFFFh
0x18007149d  mov     eax, r14d
0x1800714a0  cmp     [rbx+rax*2+54h], dx
0x1800714a5  jz      short loc_1800714B5
0x1800714a7  inc     r14d
0x1800714aa  add     r9d, 0FFFFFFFFh; unsigned int
0x1800714ae  jnz     short loc_18007149D
0x1800714b0  test    r9d, r9d
0x1800714b3  jz      short loc_180071506
0x1800714b5  mov     r8d, r14d; unsigned int
0x1800714b8  mov     rdx, rbx; struct _CFONT *
0x1800714bb  mov     rcx, r12; HDC
0x1800714be  call    ?bFillWidthTableForGCW@@YAHPEAUHDC__@@PEAU_CFONT@@II@Z; bFillWidthTableForGCW(HDC__ *,_CFONT *,uint,uint)
0x1800714c3  cmp     eax, 0FFFFFFFFh
0x1800714c6  jnz     short loc_180071506
0x1800714c8  dec     dword ptr [rbx+18h]
0x1800714cb  or      dword ptr [rdi+98h], 20h
0x1800714d2  xor     ebx, ebx
0x1800714d4  jmp     short loc_180071506
0x1800714d6  mov     [rax+28h], r12
0x1800714da  mov     rax, [rdi+160h]
0x1800714e1  mov     [rbx+8], rax
0x1800714e5  mov     [rdi+160h], rbx
0x1800714ec  mov     rax, [rsi+8]
0x1800714f0  mov     rcx, [rax]
0x1800714f3  mov     [rbx], rcx
0x1800714f6  mov     rax, [rsi+8]
0x1800714fa  mov     [rax], rbx
0x1800714fd  jmp     short loc_180071506
0x1800714ff  or      dword ptr [rdi+98h], 20h
0x180071506  mov     rcx, cs:WPP_GLOBAL_Control
0x18007150d  lea     rax, WPP_GLOBAL_Control
0x180071514  cmp     rcx, rax
0x180071517  jz      loc_18007136B
0x18007151d  test    byte ptr [rcx+1Ch], 1
0x180071521  jz      loc_18007136B
0x180071527  cmp     byte ptr [rcx+19h], 5
0x18007152b  jb      loc_18007136B
0x180071531  mov     rcx, [rcx+10h]
0x180071535  mov     edx, 0Bh
0x18007153a  call    WPP_SF_
0x18007153f  jmp     loc_18007136B
```
