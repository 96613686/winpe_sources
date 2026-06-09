# IndexListEnum

- ea: `0x140004fb0`
- end: `0x140005952`
- name: `IndexListEnum`
- size: `2466`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation`

## callees

- `0x140003480`
- `0x140004970`
- `0x140004fb0`
- `0x140006c40`
- `0x140009520`
- `0x140009e00`
- `0x14000c210`
- `0x14001e330`
- `0x14001efd0`
- `0x14001f950`
- `0x14001f9b0`
- `0x14001fd70`
- `0x14001fdac`
- `0x1400201a8`
- `0x140020350`
- `0x140038dc8`
- `0x14004efd4`
- `0x140050c38`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000535e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000535e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400058e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400058e6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400057b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400057b9`

## string_xrefs

- `0x1400058fd`: `ExAllocateFromNPagedLookasideList`
- `0x14000591b`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall IndexListEnum(__int64 **a1, __int64 a2, __int64 a3, _QWORD *a4, int a5)
{
  __int64 **v6; // rax
  __int64 v7; // r9
  __int64 v8; // rsi
  __int64 v9; // rcx
  _DWORD *v10; // r13
  __int64 *v11; // rdi
  __int64 *v12; // r14
  int v13; // eax
  int v14; // edx
  __int64 v15; // r13
  int v16; // eax
  unsigned int v17; // r10d
  unsigned int v18; // r8d
  int v19; // edi
  unsigned int v20; // ebx
  __int64 v21; // r15
  __int64 v22; // r14
  __int64 v23; // rdi
  int v24; // ecx
  int v25; // r8d
  int v26; // ecx
  _DWORD *v27; // rax
  int *v28; // r12
  int v29; // edx
  _DWORD *v30; // rsi
  int v31; // r10d
  _DWORD *v32; // r15
  __int64 v34; // rcx
  _DWORD *v35; // rbx
  _QWORD *v36; // r12
  _DWORD *v37; // r14
  __int64 v38; // rdi
  __int64 v39; // rbx
  bool v40; // dl
  signed __int64 v41; // rcx
  unsigned int v42; // edx
  int v43; // eax
  int v44; // eax
  bool v45; // zf
  __int64 v46; // rax
  __int64 matched; // rax
  __int64 v48; // rax
  BOOL v49; // [rsp+30h] [rbp-D0h]
  int v50; // [rsp+34h] [rbp-CCh] BYREF
  int v51; // [rsp+38h] [rbp-C8h] BYREF
  int v52; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v53; // [rsp+40h] [rbp-C0h]
  __int64 v54; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  int v56; // [rsp+58h] [rbp-A8h] BYREF
  int v57; // [rsp+5Ch] [rbp-A4h] BYREF
  int v58; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v59; // [rsp+68h] [rbp-98h]
  _DWORD *v60; // [rsp+70h] [rbp-90h]
  _QWORD *v61; // [rsp+78h] [rbp-88h]
  __int64 *v62; // [rsp+80h] [rbp-80h]
  __int64 v63; // [rsp+88h] [rbp-78h] BYREF
  __int128 *v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  __int128 *v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h] BYREF
  __int128 *v68; // [rsp+B0h] [rbp-50h]
  __int64 v69; // [rsp+B8h] [rbp-48h] BYREF
  __int128 *v70; // [rsp+C0h] [rbp-40h]
  __int64 *v71; // [rsp+C8h] [rbp-38h]
  __int64 **v72; // [rsp+D0h] [rbp-30h]
  __int128 v73; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v74; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v75; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v76; // [rsp+108h] [rbp+8h] BYREF

  v72 = a1;
  v61 = a4;
  v6 = a1;
  v55 = a2;
  v7 = a2;
  v60 = 0;
  v8 = 0;
  v50 = 0;
  v9 = *a4;
  v10 = 0;
  v59 = (_DWORD *)v9;
  if ( v9 )
  {
    if ( *(_QWORD *)(v9 + 16) )
    {
      do
        v9 = *(_QWORD *)(v9 + 16);
      while ( *(_QWORD *)(v9 + 16) );
      v59 = (_DWORD *)v9;
    }
  }
  else
  {
    v59 = 0;
  }
  v11 = *v6;
  while ( 1 )
  {
    v62 = v11;
    if ( v11 == (__int64 *)v6 )
      break;
    v12 = (__int64 *)*v11;
    v13 = *(_DWORD *)(v7 + 8) & 0x20;
    v71 = (__int64 *)*v11;
    if ( !isFeature_Firewall_042024Enabled )
    {
      if ( v13 )
        matched = FilterMatchEnumAll(v11[3], v7, &v50);
      else
        matched = FilterMatchEnumVisible(v11, v7, &v50);
      goto LABEL_136;
    }
    if ( !v13 && (v14 = *((_DWORD *)v11 + 13)) != 0 && ((v14 & 1) != 0 || (v14 & gWfpGlobal[11].L.Future[6]) == 0) )
    {
      v6 = v72;
      v8 = 0;
      v50 = 0;
      v11 = v12;
    }
    else
    {
      v15 = v11[3];
      if ( a5 )
      {
        matched = FilterMatchPreciseEnumAll(v11[3], v7, &v50);
        v10 = v60;
LABEL_136:
        v8 = matched;
        goto LABEL_37;
      }
      v16 = *(_DWORD *)(v7 + 24);
      v8 = 0;
      v50 = 0;
      if ( (v16 & *(_DWORD *)(v15 + 40)) != 0 )
      {
        v50 = 1;
        v17 = 0;
LABEL_11:
        v53 = v17;
        if ( v17 < *(_DWORD *)(v7 + 12) )
        {
          v18 = 0;
          v49 = 0;
          v19 = 0;
          v52 = 0;
          while ( 1 )
          {
            while ( 1 )
            {
              if ( v19 )
              {
LABEL_29:
                ++v17;
                goto LABEL_11;
              }
              v20 = v18;
              v21 = *(_QWORD *)(v7 + 16) + 24LL * v17;
              while ( 1 )
              {
                if ( v20 >= *(_DWORD *)(v15 + 28) )
                  goto LABEL_28;
                v22 = 24LL * v20;
                v23 = v22 + *(_QWORD *)(v15 + 32);
                if ( *(_WORD *)v21 == *(_WORD *)v23 )
                  break;
                ++v20;
              }
              v18 = v20;
              if ( !v23 )
              {
LABEL_28:
                if ( !v18 )
                  goto LABEL_29;
                v50 = 0;
                goto LABEL_36;
              }
              v24 = *(_DWORD *)(v7 + 4);
              if ( !v24 )
                break;
              if ( v24 == 1 )
              {
                v8 = MatchConditionOverlap(v22 + *(_QWORD *)(v15 + 32), v21, &v52, 0);
                if ( v8 )
                  goto LABEL_32;
                v19 = v52;
                v49 = v52;
                if ( !v52 && !(unsigned int)IsContinueMatchOnOrFilter(v15, v20) )
                {
LABEL_85:
                  v50 = 0;
                  goto LABEL_36;
                }
                goto LABEL_86;
              }
              v19 = v49;
              v18 = v20 + 1;
            }
            v25 = *(_DWORD *)(v23 + 8);
            v64 = &v73;
            v66 = &v74;
            v68 = &v75;
            v70 = &v76;
            v26 = 0;
            v54 = 0;
            v49 = 0;
            v56 = 0;
            v27 = (_DWORD *)(v23 + 8);
            v63 = 11;
            v28 = (int *)(v21 + 8);
            v65 = 11;
            v57 = 0;
            v67 = 11;
            v69 = 11;
            v58 = 0;
            v73 = 0;
            v74 = 0;
            v75 = 0;
            v76 = 0;
            if ( !v25 )
            {
              LOBYTE(v26) = *(_DWORD *)(v23 + 4) == 0;
LABEL_93:
              v43 = 0;
              v49 = 0;
              if ( !*v28 )
                v43 = *(_DWORD *)(v21 + 4) == 0;
              if ( v26 == v43 )
              {
                v19 = 1;
                v49 = 1;
              }
              else
              {
                v19 = 0;
              }
              goto LABEL_80;
            }
            v29 = *v28;
            if ( !*v28 )
              goto LABEL_93;
            v30 = (_DWORD *)(v23 + 4);
            v31 = *(_DWORD *)(v23 + 4);
            v51 = 0;
            v52 = 0;
            if ( isFeature_Firewall_042024Enabled )
            {
              if ( !v31 )
              {
                if ( *(_DWORD *)(v21 + 4) )
                  goto LABEL_26;
                goto LABEL_25;
              }
            }
            else if ( !v31 )
            {
              if ( *(_DWORD *)(v21 + 4) )
                goto LABEL_26;
              goto LABEL_25;
            }
            if ( v31 != 10
              || *(_DWORD *)(v21 + 4) != 10
              || !(unsigned int)IsSDType((unsigned int)v25)
              || !(unsigned int)IsSDType(v42) )
            {
              goto LABEL_26;
            }
            v27 = (_DWORD *)(v23 + 8);
LABEL_25:
            if ( v29 < 255 && v25 < 255 )
            {
              v19 = MatchValues(v31, v27, (_DWORD *)(v21 + 8));
              v49 = v19;
              goto LABEL_80;
            }
LABEL_26:
            CheckFlagsConditionEnumMatch(v23, v21, (unsigned int)&v51, (unsigned int)&v52, (__int64)&v54);
            if ( v51 )
            {
              v19 = v52;
              v49 = v52;
              goto LABEL_80;
            }
            v44 = *v30;
            v51 = 0;
            if ( v44 == 10 )
            {
              v45 = *(_DWORD *)(v21 + 4) == 10;
LABEL_120:
              if ( v45 )
                goto LABEL_103;
              goto LABEL_101;
            }
            if ( !v44 )
            {
              v45 = *(_DWORD *)(v21 + 4) == 0;
              goto LABEL_120;
            }
LABEL_101:
            if ( *(_DWORD *)(v23 + 8) != 13 || *v28 != 13 )
            {
LABEL_103:
              v54 = ConvertConditionToRange(v23, &v63, &v51, &v57);
              if ( v54 || !v51 || (v54 = ConvertConditionToRange(v21, &v67, &v51, &v58)) != 0 || !v51 )
              {
LABEL_111:
                v19 = v49;
              }
              else
              {
                if ( *v30 != 10 && *(_DWORD *)(v21 + 4) != 10 )
                {
                  v49 = MatchValues(3, &v63, &v67) && MatchValues(4, &v65, &v69);
                  goto LABEL_111;
                }
                v46 = MatchRangeConditionsContainsNotEqual(
                        (unsigned int)&v63,
                        *v30,
                        (unsigned int)&v67,
                        *(_DWORD *)(v21 + 4),
                        (__int64)&v56);
                v19 = v56;
                v54 = v46;
                v49 = v56;
              }
              if ( v57 )
              {
                WfpPoolFree((char *)v64 + 8);
                WfpPoolFree((char *)v66 + 8);
              }
              if ( v58 )
              {
                WfpPoolFree((char *)v68 + 8);
                WfpPoolFree((char *)v70 + 8);
              }
              goto LABEL_80;
            }
            v19 = !MatchValues(0, (_DWORD *)(v23 + 8), (_DWORD *)(v21 + 8));
            v49 = v19;
LABEL_80:
            v8 = v54;
            v52 = v19;
            if ( v54 )
            {
              WfpReportError(v54, "MatchConditionContains");
LABEL_32:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"FilterMatchEnumAll",
                  v8);
              }
              break;
            }
            if ( !v19
              && ((*(_BYTE *)(v15 + 26) & 4) == 0
               || v20 == *(_DWORD *)(v15 + 28) - 1
               || *(_WORD *)(*(_QWORD *)(v15 + 32) + 24LL * v20) != *(_WORD *)(*(_QWORD *)(v15 + 32) + 24LL * (v20 + 1))) )
            {
              goto LABEL_85;
            }
LABEL_86:
            v17 = v53;
            v18 = v20 + 1;
            v7 = v55;
          }
        }
      }
LABEL_36:
      v11 = v62;
      v12 = v71;
      v10 = v60;
LABEL_37:
      if ( v8 )
        goto LABEL_58;
      if ( v50 )
      {
        v32 = v59;
        if ( v59 && *((_WORD *)v59 + 12) < 7u )
        {
          _InterlockedIncrement64(v11 + 2);
          *(_QWORD *)&v32[2 * (unsigned __int16)(*((_WORD *)v32 + 12))++ + 8] = v11;
          v8 = 0;
LABEL_43:
          if ( !v10 )
            v10 = v32;
          v60 = v10;
          goto LABEL_39;
        }
        v8 = 0;
        v35 = ExAllocateFromNPagedLookasideList(gWfpGlobal);
        if ( v35
          || (v48 = WfpReportSysErrorAsNtStatus(v34, "ExAllocateFromNPagedLookasideList", 3221225495LL, 1),
              (v8 = v48) == 0) )
        {
          v35[7] = 0;
          *((_QWORD *)v35 + 1) = v35;
          *(_QWORD *)v35 = v35;
          *((_QWORD *)v35 + 2) = 0;
          v35[6] = -65536;
          *((_QWORD *)v35 + 11) = 0;
          _InterlockedIncrement64(v11 + 2);
          ++*((_WORD *)v35 + 12);
          *((_QWORD *)v35 + 4) = v11;
          if ( v32 )
            *((_QWORD *)v32 + 2) = v35;
          v32 = v35;
          v59 = v35;
          if ( !v8 )
            goto LABEL_43;
        }
        else
        {
          WfpReportError(v48, "WfpAllocFromNPagedLookasideList");
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"InsertFilterToMatchBuf",
            v8);
        }
        if ( v8 )
        {
LABEL_58:
          v36 = v61;
          if ( *v61 )
          {
            v10 = (_DWORD *)*v61;
            goto LABEL_60;
          }
          *v61 = v10;
          if ( !v10 )
          {
LABEL_71:
            *v36 = 0;
            WfpReportError(v8, "IndexListEnum");
            return v8;
          }
LABEL_60:
          while ( 1 )
          {
            v37 = (_DWORD *)*((_QWORD *)v10 + 2);
            v38 = 0;
            if ( *((_WORD *)v10 + 12) )
              break;
LABEL_68:
            if ( (v10[7] & 1) == 0 )
            {
              if ( *((_QWORD *)v10 + 11) )
                WfpPoolFree(v10 + 22);
              ExFreeToNPagedLookasideList(gWfpGlobal, v10);
            }
            v10 = v37;
            if ( !v37 )
            {
              v36 = v61;
              goto LABEL_71;
            }
          }
          while ( 2 )
          {
            v39 = *(_QWORD *)&v10[2 * v38 + 8];
            v40 = 0;
            _InterlockedIncrement64((volatile signed __int64 *)(v39 + 16));
            v41 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v39 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
            if ( (_DWORD)v41 == HIDWORD(v41) )
            {
              _m_prefetchw((const void *)(v39 + 52));
              v40 = (_InterlockedOr((volatile signed __int32 *)(v39 + 52), 0x10u) & 0x10) == 0;
            }
            if ( (*(_DWORD *)(*(_QWORD *)(v39 + 24) + 40LL) & 0x4000) != 0 && v40 )
            {
              if ( !KeGetCurrentIrql() )
              {
                FeNotifyIntFilterDelete(v39);
                goto LABEL_65;
              }
              NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
            }
            else
            {
LABEL_65:
              if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v39 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
                FreeWFPFilter((PVOID)v39);
            }
            v38 = (unsigned int)(v38 + 1);
            if ( (unsigned int)v38 >= *((unsigned __int16 *)v10 + 12) )
              goto LABEL_68;
            continue;
          }
        }
        goto LABEL_43;
      }
LABEL_39:
      v7 = v55;
      v6 = v72;
      v11 = v12;
    }
  }
  if ( !*v61 )
    *v61 = v10;
  return v8;
}

```

## disassembly

```asm
0x140004fb0  mov     [rsp-8+arg_10], rbx
0x140004fb5  push    rbp
0x140004fb6  push    rsi
0x140004fb7  push    rdi
0x140004fb8  push    r12
0x140004fba  push    r13
0x140004fbc  push    r14
0x140004fbe  push    r15
0x140004fc0  lea     rbp, [rsp-20h]
0x140004fc5  sub     rsp, 120h
0x140004fcc  mov     rax, cs:__security_cookie
0x140004fd3  xor     rax, rsp
0x140004fd6  mov     [rbp+50h+var_38], rax
0x140004fda  xor     r11d, r11d
0x140004fdd  mov     [rbp+50h+var_80], rcx
0x140004fe1  mov     r12, r9
0x140004fe4  mov     [rsp+150h+var_D8], r9
0x140004fe9  mov     rax, rcx
0x140004fec  mov     [rsp+150h+var_100], rdx
0x140004ff1  mov     r9, rdx
0x140004ff4  mov     [rsp+150h+var_E0], r11
0x140004ff9  mov     esi, r11d
0x140004ffc  mov     [rsp+150h+var_11C], r11d
0x140005001  mov     rcx, [r12]
0x140005005  mov     r13d, r11d
0x140005008  mov     [rsp+150h+var_E8], rcx
0x14000500d  test    rcx, rcx
0x140005010  jnz     loc_14000576A
0x140005016  mov     [rsp+150h+var_E8], r11
0x14000501b  mov     rdi, [rax]
0x14000501e  mov     [rbp+50h+var_D0], rdi
0x140005022  mov     ecx, 1
0x140005027  cmp     rdi, rax
0x14000502a  jz      loc_1400052CF
0x140005030  mov     eax, [r9+8]
0x140005034  mov     r14, [rdi]
0x140005037  and     eax, 20h
0x14000503a  cmp     cs:isFeature_Firewall_042024Enabled, 0
0x140005041  mov     [rbp+50h+var_88], r14
0x140005045  jz      loc_1400058A5
0x14000504b  test    eax, eax
0x14000504d  jnz     short loc_14000505A
0x14000504f  mov     edx, [rdi+34h]
0x140005052  test    edx, edx
0x140005054  jnz     loc_1400054D4
0x14000505a  cmp     [rbp+50h+arg_20], 0
0x140005061  mov     r13, [rdi+18h]
0x140005065  jnz     loc_140005888
0x14000506b  mov     eax, [r9+18h]
0x14000506f  mov     rsi, r11
0x140005072  mov     [rsp+150h+var_11C], r11d
0x140005077  test    [r13+28h], eax
0x14000507b  jz      loc_140005261
0x140005081  mov     [rsp+150h+var_11C], ecx
0x140005085  mov     r10d, r11d
0x140005088  mov     [rsp+150h+var_110], r10d
0x14000508d  cmp     r10d, [r9+0Ch]
0x140005091  jnb     loc_14000521A
0x140005097  mov     r8d, r11d
0x14000509a  mov     [rsp+150h+var_120], r11d
0x14000509f  mov     edi, r11d
0x1400050a2  mov     [rsp+150h+var_114], r11d
0x1400050a7  test    edi, edi
0x1400050a9  jnz     loc_14000520D
0x1400050af  mov     edx, [r13+1Ch]
0x1400050b3  mov     ebx, r8d
0x1400050b6  mov     eax, r10d
0x1400050b9  lea     rcx, [rax+rax*2]
0x1400050bd  mov     rax, [r9+10h]
0x1400050c1  lea     r15, [rax+rcx*8]
0x1400050c5  cmp     ebx, edx
0x1400050c7  jnb     loc_140005208
0x1400050cd  mov     rdi, [r13+20h]
0x1400050d1  mov     eax, ebx
0x1400050d3  lea     rcx, [rax+rax*2]
0x1400050d7  lea     r14, ds:0[rcx*8]
0x1400050df  add     rdi, r14
0x1400050e2  movzx   eax, word ptr [rdi]
0x1400050e5  cmp     [r15], ax
0x1400050e9  jz      short loc_1400050EF
0x1400050eb  inc     ebx
0x1400050ed  jmp     short loc_1400050C5
0x1400050ef  mov     r8d, ebx
0x1400050f2  test    rdi, rdi
0x1400050f5  jz      loc_140005208
0x1400050fb  mov     ecx, [r9+4]
0x1400050ff  test    ecx, ecx
0x140005101  jnz     loc_1400055AF
0x140005107  mov     r8d, [rdi+8]
0x14000510b  lea     rax, [rbp+50h+var_78]
0x14000510f  mov     [rbp+50h+var_C0], rax
0x140005113  lea     rax, [rbp+50h+var_68]
0x140005117  mov     [rbp+50h+var_B0], rax
0x14000511b  lea     rax, [rbp+50h+var_58]
0x14000511f  mov     [rbp+50h+var_A0], rax
0x140005123  lea     rax, [rbp+50h+var_48]
0x140005127  mov     [rbp+50h+var_90], rax
0x14000512b  mov     ecx, r11d
0x14000512e  mov     [rsp+150h+var_108], r11
0x140005133  xorps   xmm0, xmm0
0x140005136  mov     [rsp+150h+var_120], ecx
0x14000513a  xorps   xmm1, xmm1
0x14000513d  mov     [rsp+150h+var_F8], ecx
0x140005141  lea     rax, [rdi+8]
0x140005145  mov     [rbp+50h+var_C8], 0Bh
0x14000514d  lea     r12, [r15+8]
0x140005151  mov     [rbp+50h+var_B8], 0Bh
0x140005159  mov     [rsp+150h+var_F4], r11d
0x14000515e  mov     [rbp+50h+var_A8], 0Bh
0x140005166  mov     [rbp+50h+var_98], 0Bh
0x14000516e  mov     [rsp+150h+var_F0], r11d
0x140005173  movups  [rbp+50h+var_78], xmm0
0x140005177  movups  [rbp+50h+var_68], xmm1
0x14000517b  movups  [rbp+50h+var_58], xmm0
0x14000517f  movups  [rbp+50h+var_48], xmm1
0x140005183  test    r8d, r8d
0x140005186  jz      loc_1400055F3
0x14000518c  mov     edx, [r12]
0x140005190  test    edx, edx
0x140005192  jz      loc_1400055FA
0x140005198  cmp     cs:isFeature_Firewall_042024Enabled, 0
0x14000519f  lea     rsi, [rdi+4]
0x1400051a3  mov     r10d, [rsi]
0x1400051a6  mov     [rsp+150h+var_118], r11d
0x1400051ab  mov     [rsp+150h+var_114], r11d
0x1400051b0  jnz     loc_140005827
0x1400051b6  test    r10d, r10d
0x1400051b9  jnz     loc_1400054FA
0x1400051bf  cmp     [r15+4], r10d
0x1400051c3  jnz     short loc_1400051D1
0x1400051c5  cmp     edx, 0FFh
0x1400051cb  jl      loc_1400057D6
0x1400051d1  lea     rax, [rsp+150h+var_108]
0x1400051d6  mov     rdx, r15
0x1400051d9  lea     r9, [rsp+150h+var_114]
0x1400051de  mov     [rsp+150h+var_130], rax
0x1400051e3  lea     r8, [rsp+150h+var_118]
0x1400051e8  mov     rcx, rdi
0x1400051eb  call    CheckFlagsConditionEnumMatch
0x1400051f0  cmp     [rsp+150h+var_118], 0
0x1400051f5  jz      loc_14000564F
0x1400051fb  mov     edi, [rsp+150h+var_114]
0x1400051ff  mov     [rsp+150h+var_120], edi
0x140005203  jmp     loc_14000554F
0x140005208  test    r8d, r8d
0x14000520b  jnz     short loc_140005215
0x14000520d  inc     r10d
0x140005210  jmp     loc_140005088
0x140005215  mov     [rsp+150h+var_11C], r11d
0x14000521a  test    rsi, rsi
0x14000521d  jz      short loc_140005261
0x14000521f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005226  lea     rax, WPP_GLOBAL_Control
0x14000522d  cmp     rcx, rax
0x140005230  jz      short loc_140005261
0x140005232  cmp     byte ptr [rcx+29h], 2
0x140005236  jb      short loc_140005261
0x140005238  test    dword ptr [rcx+2Ch], 1000h
0x14000523f  jz      short loc_140005261
0x140005241  mov     rcx, [rcx+18h]
0x140005245  lea     r9, aFiltermatchenu_0
0x14000524c  mov     edx, 0Fh
0x140005251  mov     dword ptr [rsp+150h+var_130], esi
0x140005255  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000525c  call    WPP_SF_sd
0x140005261  mov     rdi, [rbp+50h+var_D0]
0x140005265  mov     r14, [rbp+50h+var_88]
0x140005269  mov     r13, [rsp+150h+var_E0]
0x14000526e  test    rsi, rsi
0x140005271  jnz     loc_140005402
0x140005277  cmp     [rsp+150h+var_11C], esi
0x14000527b  jnz     short loc_140005291
0x14000527d  mov     r9, [rsp+150h+var_100]
0x140005282  xor     r11d, r11d
0x140005285  mov     rax, [rbp+50h+var_80]
0x140005289  mov     rdi, r14
0x14000528c  jmp     loc_14000501E
0x140005291  mov     r15, [rsp+150h+var_E8]
0x140005296  test    r15, r15
0x140005299  jz      loc_140005351
0x14000529f  cmp     word ptr [r15+18h], 7
0x1400052a5  jnb     loc_140005351
0x1400052ab  lock inc qword ptr [rdi+10h]
0x1400052b0  movzx   eax, word ptr [r15+18h]
0x1400052b5  mov     [r15+rax*8+20h], rdi
0x1400052ba  inc     word ptr [r15+18h]
0x1400052bf  xor     esi, esi
0x1400052c1  test    r13, r13
0x1400052c4  cmovz   r13, r15
0x1400052c8  mov     [rsp+150h+var_E0], r13
0x1400052cd  jmp     short loc_14000527D
0x1400052cf  mov     r12, [rsp+150h+var_D8]
0x1400052d4  cmp     qword ptr [r12], 0
0x1400052d9  jnz     short loc_1400052DF
0x1400052db  mov     [r12], r13
0x1400052df  test    rsi, rsi
0x1400052e2  jz      short loc_140005326
0x1400052e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052eb  lea     rax, WPP_GLOBAL_Control
0x1400052f2  cmp     rcx, rax
0x1400052f5  jz      short loc_140005326
0x1400052f7  cmp     byte ptr [rcx+29h], 2
0x1400052fb  jb      short loc_140005326
0x1400052fd  test    dword ptr [rcx+2Ch], 1000h
0x140005304  jz      short loc_140005326
0x140005306  mov     rcx, [rcx+18h]
0x14000530a  lea     r9, aIndexlistenum
0x140005311  mov     edx, 0Fh
0x140005316  mov     dword ptr [rsp+150h+var_130], esi
0x14000531a  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140005321  call    WPP_SF_sd
0x140005326  mov     rax, rsi
0x140005329  mov     rcx, [rbp+50h+var_38]
0x14000532d  xor     rcx, rsp; StackCookie
0x140005330  call    __security_check_cookie
0x140005335  mov     rbx, [rsp+150h+arg_10]
0x14000533d  add     rsp, 120h
0x140005344  pop     r15
0x140005346  pop     r14
0x140005348  pop     r13
0x14000534a  pop     r12
0x14000534c  pop     rdi
0x14000534d  pop     rsi
0x14000534e  pop     rbp
0x14000534f  retn
0x140005351  mov     rcx, cs:gWfpGlobal; Lookaside
0x140005358  xor     r12d, r12d
0x14000535b  mov     esi, r12d
0x14000535e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140005365  nop     dword ptr [rax+rax+00h]
0x14000536a  mov     rbx, rax
0x14000536d  test    rax, rax
0x140005370  jz      loc_1400058F7
0x140005376  mov     [rbx+1Ch], r12d
0x14000537a  mov     [rbx+8], rbx
0x14000537e  mov     [rbx], rbx
0x140005381  mov     [rbx+10h], r12
0x140005385  mov     dword ptr [rbx+18h], 0FFFF0000h
0x14000538c  mov     [rbx+58h], r12
0x140005390  lock inc qword ptr [rdi+10h]
0x140005395  inc     word ptr [rbx+18h]
0x140005399  mov     [rbx+20h], rdi
0x14000539d  test    r15, r15
0x1400053a0  jz      short loc_1400053A6
0x1400053a2  mov     [r15+10h], rbx
0x1400053a6  mov     r15, rbx
0x1400053a9  mov     [rsp+150h+var_E8], rbx
0x1400053ae  test    rsi, rsi
0x1400053b1  jz      loc_1400052C1
0x1400053b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053be  lea     rax, WPP_GLOBAL_Control
0x1400053c5  cmp     rcx, rax
0x1400053c8  jz      short loc_1400053F9
0x1400053ca  cmp     byte ptr [rcx+29h], 2
0x1400053ce  jb      short loc_1400053F9
0x1400053d0  test    dword ptr [rcx+2Ch], 1000h
0x1400053d7  jz      short loc_1400053F9
0x1400053d9  mov     rcx, [rcx+18h]
0x1400053dd  lea     r9, aInsertfilterto
0x1400053e4  mov     edx, 0Fh
0x1400053e9  mov     dword ptr [rsp+150h+var_130], esi
0x1400053ed  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400053f4  call    WPP_SF_sd
0x1400053f9  test    rsi, rsi
0x1400053fc  jz      loc_1400052C1
0x140005402  mov     r12, [rsp+150h+var_D8]
0x140005407  mov     rax, [r12]
0x14000540b  test    rax, rax
0x14000540e  jz      loc_1400058BF
0x140005414  mov     r13, rax
0x140005417  mov     r12d, 1
0x14000541d  mov     r14, [r13+10h]
0x140005421  xor     edi, edi
0x140005423  xor     eax, eax
0x140005425  cmp     ax, [r13+18h]
0x14000542a  jnb     short loc_140005491
0x14000542c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x140005433  mov     rbx, [r13+rdi*8+20h]
0x140005438  xor     dl, dl
0x14000543a  lock inc qword ptr [rbx+10h]
0x14000543f  mov     rcx, r15
0x140005442  lock xadd [rbx+10h], rcx
0x140005448  sub     rcx, 2
0x14000544c  mov     rax, rcx
0x14000544f  shr     rax, 20h
0x140005453  cmp     ecx, eax
0x140005455  jz      loc_140005788
0x14000545b  mov     rax, [rbx+18h]
0x14000545f  test    dword ptr [rax+28h], 4000h
0x140005466  jz      short loc_140005470
0x140005468  test    dl, dl
0x14000546a  jnz     loc_1400057B9
0x140005470  mov     rax, r15
0x140005473  lock xadd [rbx+10h], rax
0x140005479  cmp     rax, r12
0x14000547c  jnz     short loc_140005486
0x14000547e  mov     rcx, rbx; P
0x140005481  call    FreeWFPFilter
0x140005486  movzx   eax, word ptr [r13+18h]
0x14000548b  inc     edi
  ... truncated ...
```
