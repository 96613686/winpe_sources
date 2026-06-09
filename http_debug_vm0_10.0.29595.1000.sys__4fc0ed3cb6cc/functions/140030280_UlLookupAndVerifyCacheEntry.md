# UlLookupAndVerifyCacheEntry

- ea: `0x140030280`
- end: `0x140030b35`
- name: `UlLookupAndVerifyCacheEntry`
- size: `2229`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14002ebb0`
- `0x14011f7e4`

## callees

- `0x14000a350`
- `0x140013430`
- `0x140030280`
- `0x140030e6c`
- `0x140038e80`
- `0x1400811f0`
- `0x140087760`
- `0x1400d45e8`
- `0x1400d6844`
- `0x1400e6f78`
- `0x1401516c4`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c45cc`
- `0x1401c80b0`
- `0x1401ccf58`
- `0x1401cd174`
- `0x1401da2b4`
- `0x1401da550`
- `0x1401da5a4`
- `0x1401da69c`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140030754`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140030754`
- `ntoskrnl!_strnicmp` at `0x1401749d2`
- `ntoskrnl!_strnicmp` at `0x1401749d2`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x140174a4c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x140174a4c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140174a9f`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140174a9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030414`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140174aab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030414`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140174aab`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400303ce`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400303ce`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140030408`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140030408`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400303bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140174a37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400303bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140174a37`

## pseudocode

```c
__int64 __fastcall UlLookupAndVerifyCacheEntry(__int64 a1, __int64 *a2, _DWORD *a3)
{
  __int64 v3; // rax
  _DWORD *v4; // r12
  __int64 *v5; // r13
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  __int64 v9; // rdx
  int v10; // eax
  int v11; // r8d
  __int64 v12; // rbx
  int v13; // edi
  unsigned __int64 v14; // rsi
  __int64 v15; // rbx
  int v16; // edx
  __int64 v17; // rdi
  int RoutingToken; // esi
  _QWORD *v20; // r15
  _QWORD *v21; // rbx
  unsigned __int16 v22; // si
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // r8
  int v30; // ecx
  __int64 v31; // rbx
  bool v32; // zf
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  _QWORD *v36; // rax
  _QWORD *v37; // r12
  int v38; // eax
  unsigned int v39; // ecx
  unsigned __int16 v40; // ax
  __int64 v41; // r15
  UNICODE_STRING String2; // [rsp+40h] [rbp-39h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-29h] BYREF
  __int128 v44; // [rsp+60h] [rbp-19h] BYREF
  __int128 v45; // [rsp+70h] [rbp-9h]
  __int128 v46; // [rsp+80h] [rbp+7h]
  __int64 v47; // [rsp+90h] [rbp+17h]
  unsigned __int64 v48; // [rsp+E0h] [rbp+67h]

  v3 = 0;
  v44 = 0;
  v47 = 0;
  v4 = a3;
  v45 = 0;
  v5 = a2;
  v46 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( a1 )
      v3 = *(_QWORD *)(a1 + 64);
    WPP_SF_qqqi(1033, 228, WPP_173ede4a325638307373c19033e5a27a_Traceguids, a1, v3, a2, a3);
  }
  *v5 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL);
  if ( !*(_DWORD *)(v7 + 1168) && !*(_DWORD *)(v7 + 1172) )
    goto LABEL_4;
  RoutingToken = UlGenerateRoutingToken(a1, 2);
  if ( RoutingToken < 0 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qiLq(1032, 235, v29, a1, *(_QWORD *)(a1 + 64), 18, 0);
    *(_DWORD *)(a1 + 500) = *(_DWORD *)(a1 + 496);
    *(_DWORD *)(a1 + 496) = 11;
    *(_DWORD *)(a1 + 1868) = 18;
    if ( (BYTE9(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_qidsH(v28, v27, v29, a1, *(_QWORD *)(a1 + 64), 18, (__int64)"UlErrorInternalServer", 244);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 237, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
    *v4 = 5;
    goto LABEL_20;
  }
  LOBYTE(v27) = 1;
  UlInitSearchKeyFromRequest(a1, v27, &v44);
  v17 = UlCheckoutUriCacheEntry(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL), &v44, a1);
  if ( !v17 )
  {
LABEL_4:
    v8 = (_QWORD *)(a1 + 64);
    if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_qilq(1044, 113, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, a1, *v8, 0, &v44);
    v9 = *(_QWORD *)(a1 + 2032);
    v10 = *(_DWORD *)(a1 + 2068);
    v11 = *(_DWORD *)(a1 + 2064);
    *((_QWORD *)&v45 + 1) = *(_QWORD *)(a1 + 2048);
    HIDWORD(v44) = v10;
    *(_QWORD *)&v45 = *(_QWORD *)(a1 + 2040);
    LOWORD(v10) = *(_WORD *)(a1 + 2074);
    DWORD2(v44) = v11;
    WORD2(v46) = v10;
    LOWORD(v10) = *(_WORD *)(a1 + 2072);
    WORD1(v46) = v11 - 2 * ((*((_QWORD *)&v45 + 1) - v9) >> 1);
    *(_QWORD *)&v44 = v9;
    LOWORD(v46) = v10;
    *((_QWORD *)&v46 + 1) = 0;
    LODWORD(v47) = 0;
    if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_(1044, 114, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids);
    v12 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL);
    if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_qqqi(1044, 21, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, v12, &v44, a1, *v8);
    v13 = HIDWORD(v44);
    v14 = *(_QWORD *)(v12 + 1080) + ((unsigned __int64)(HIDWORD(v44) & (unsigned int)UlHashTableMask) << 6);
    v48 = v14;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(v14, 0);
    v15 = *(_QWORD *)(v14 + 8);
    if ( v15 )
    {
      v16 = v47;
      do
      {
        if ( *(_DWORD *)(v15 + 52) == v13 )
        {
          if ( *((_QWORD *)&v46 + 1) && v16 )
          {
            if ( v16 + WORD1(v46) != *(_DWORD *)(v15 + 48) )
              goto LABEL_13;
            if ( (unsigned __int8)UlEqualUnicodeStringEx(
                                    DWORD2(v46),
                                    v16,
                                    DWORD2(v45),
                                    WORD1(v46),
                                    *(_QWORD *)(v15 + 40)) )
              break;
            goto LABEL_74;
          }
          if ( DWORD2(v44) == *(_DWORD *)(v15 + 48) )
          {
            *(&String1.MaximumLength + 2) = 0;
            *(&String2.MaximumLength + 2) = 0;
            String1.Length = WORD4(v44);
            String2.Length = WORD4(v44);
            *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(WORD4(v44) + 2);
            *(_DWORD *)&String2.MaximumLength = *(_DWORD *)&String1.MaximumLength;
            String1.Buffer = (PWSTR)v44;
            String2.Buffer = *(PWSTR *)(v15 + 40);
            if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
              break;
LABEL_74:
            v16 = v47;
          }
        }
LABEL_13:
        v15 = *(_QWORD *)(v15 + 8);
      }
      while ( v15 );
    }
    v17 = 0;
    if ( v15 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_qq(1044, 158, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, v15, a1);
      v20 = (_QWORD *)(v15 + 24);
      if ( *(_BYTE *)(v15 + 101) )
      {
        if ( (_QWORD *)*v20 != v20 )
          v17 = *v20 - 16LL;
      }
      else
      {
        v21 = (_QWORD *)*v20;
        v22 = 0;
        while ( v21 != v20 )
        {
          v23 = *((int *)v21 + 42);
          if ( *(_WORD *)(a1 + 2 * v23 + 2444) > v22 )
          {
            if ( (_DWORD)v23 == 5 )
            {
              v36 = (_QWORD *)(a1 + 2464);
              v37 = *(_QWORD **)(a1 + 2464);
              while ( v37 != v36 )
              {
                v39 = *((_DWORD *)v21 + 43);
                if ( *((unsigned __int16 *)v37 - 4) == v39
                  && !_strnicmp((const char *)*(v37 - 2), (const char *)v21[22], v39) )
                {
                  v40 = *((_WORD *)v37 - 3);
                  if ( v40 <= v22 )
                    goto LABEL_32;
                  goto LABEL_115;
                }
                v37 = (_QWORD *)*v37;
                v36 = (_QWORD *)(a1 + 2464);
              }
              v40 = *(_WORD *)(a1 + 2456);
              if ( v40 <= v22 )
                goto LABEL_32;
LABEL_115:
              v22 = v40;
            }
            else
            {
              v22 = *(_WORD *)(a1 + 2 * v23 + 2444);
            }
            v17 = (__int64)(v21 - 2);
LABEL_32:
            if ( v22 == 1000 )
              goto LABEL_37;
          }
          v21 = (_QWORD *)*v21;
        }
        if ( !v17 || *(_DWORD *)(v17 + 184) != 4 || !*(_BYTE *)(v17 + 555) )
        {
LABEL_37:
          v5 = a2;
          v4 = a3;
          v14 = v48;
          goto LABEL_38;
        }
        v14 = v48;
        v4 = a3;
        v5 = a2;
        if ( !*(_BYTE *)(a1 + 2443) )
          v17 = 0;
      }
LABEL_38:
      if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_q(1044, 159, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, v17);
      if ( v17 )
      {
        v24 = _InterlockedIncrement((volatile signed __int32 *)(v17 + 4));
        if ( UxDebugCheckRefcount )
        {
          if ( v24 <= -1 )
            UlBugCheckEx(3u, v17 + 4, 0xAu, v24);
        }
      }
    }
    ExReleasePushLockSharedEx(v14, 0);
    KeLeaveCriticalRegion();
    if ( !v17 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 0x10) == 0 )
        goto LABEL_17;
      WPP_SF_SS(1044, 22, (unsigned int)WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, DWORD2(v46), v44);
      goto LABEL_87;
    }
    v25 = *(_QWORD *)(v17 + 8);
    if ( *(_DWORD *)(v17 + 124) == 2 && MEMORY[0xFFFFF78000000014] > *(_QWORD *)(v17 + 136) )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_q(1044, 23, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, v17);
    }
    else
    {
      v26 = *(_QWORD *)(v17 + 208);
      if ( !v26 || !*(_DWORD *)(v26 + 248) )
      {
        ++*(_DWORD *)(v17 + 32);
        *(_DWORD *)(v17 + 120) = 0;
        if ( (BYTE2(xmmword_1401A2CA0) & 0x10) == 0 )
          goto LABEL_17;
        WPP_SF_qSd(
          1044,
          25,
          (unsigned int)WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids,
          v17,
          *(_QWORD *)(v25 + 40),
          *(_DWORD *)(v17 + 4));
LABEL_87:
        if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1044, 26, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, v17);
LABEL_17:
        if ( !v17 )
        {
          *v4 = 2;
LABEL_19:
          RoutingToken = 0;
          goto LABEL_20;
        }
        goto LABEL_58;
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_q(1044, 24, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, v17);
    }
    UlCheckinUriCacheEntry((PVOID)v17);
    v17 = 0;
    goto LABEL_87;
  }
LABEL_58:
  if ( !*(_DWORD *)(v17 + 512) )
    goto LABEL_75;
  v30 = *(_DWORD *)(v17 + 352);
  if ( v30 != 4 )
  {
    if ( v30 )
    {
      v33 = v30 - 1;
      if ( !v33 )
      {
        v38 = UlLookupHostPlusIPSite(a1);
        RoutingToken = v38;
        if ( v38 >= 0 )
          goto LABEL_75;
        v32 = v38 == -1073741772;
        goto LABEL_68;
      }
      v34 = v33 - 1;
      if ( !v34 || (v35 = v34 - 1) == 0 || v35 == 2 )
      {
LABEL_69:
        if ( (*(_DWORD *)(a1 + 2200) & 0x20) != 0 || (unsigned __int8)UlParseAcceptHeaderMatch(a1, v17) )
        {
          *v4 = 1;
          *v5 = v17;
          goto LABEL_19;
        }
LABEL_75:
        UlCheckinUriCacheEntry((PVOID)v17);
        *v4 = 2;
        goto LABEL_19;
      }
    }
    UlCheckinUriCacheEntry((PVOID)v17);
    UlSetErrorCode(a1, 18, 0);
    *v4 = 5;
    RoutingToken = -1073741436;
    goto LABEL_20;
  }
  RoutingToken = -1073741772;
  v31 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 151, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, a1, *(_QWORD *)(a1 + 64));
  if ( *(int *)(v31 + 1332) > 0 || *(int *)(v31 + 1328) > 0 )
  {
    KeEnterCriticalRegion();
    v41 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v31 + 1368), 0);
    if ( *(int *)(*(_QWORD *)(v31 + 1320) + 28LL) <= 0
      || (RoutingToken = UlpTreeFindIpOnlyNode(a1, 3), RoutingToken == -1073741772) )
    {
      if ( *(int *)(*(_QWORD *)(v31 + 1320) + 16LL) > 0 )
        RoutingToken = UlpTreeFindIpOnlyNode(a1, 2);
    }
    ExReleaseCacheAwarePushLockSharedEx(v41, 0);
    KeLeaveCriticalRegion();
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 152, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)RoutingToken);
  if ( RoutingToken >= 0 )
    goto LABEL_75;
  v32 = RoutingToken == -1073741772;
LABEL_68:
  if ( v32 )
    goto LABEL_69;
  UlCheckinUriCacheEntry((PVOID)v17);
  UlSetErrorCode(a1, 18, 0);
  *v4 = 5;
LABEL_20:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqD(1033, 229, WPP_173ede4a325638307373c19033e5a27a_Traceguids, *v5, v4, RoutingToken);
  return (unsigned int)RoutingToken;
}

```

## disassembly

```asm
0x140030280  mov     [rsp-8+arg_10], r8
0x140030285  mov     [rsp-8+arg_8], rdx
0x14003028a  push    rbp
0x14003028b  push    rbx
0x14003028c  push    rsi
0x14003028d  push    r12
0x14003028f  push    r13
0x140030291  push    r14
0x140030293  push    r15
0x140030295  lea     rbp, [rsp-27h]
0x14003029a  sub     rsp, 0A0h
0x1400302a1  xorps   xmm0, xmm0
0x1400302a4  xor     eax, eax
0x1400302a6  movups  [rbp+57h+var_70], xmm0
0x1400302aa  mov     [rbp+57h+var_40], rax
0x1400302ae  mov     r12, r8
0x1400302b1  movups  [rbp+57h+var_60], xmm0
0x1400302b5  mov     r13, rdx
0x1400302b8  mov     r14, rcx
0x1400302bb  movups  [rbp+57h+var_50], xmm0
0x1400302bf  xor     esi, esi
0x1400302c1  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400302c8  jnz     loc_140030785
0x1400302ce  mov     [r13+0], rsi
0x1400302d2  mov     ebx, 40h ; '@'
0x1400302d7  mov     rax, [r14+18h]
0x1400302db  mov     r15, r14
0x1400302de  mov     [rsp+0D0h+arg_18], rdi
0x1400302e6  mov     rcx, [rax+448h]
0x1400302ed  cmp     [rcx+490h], esi
0x1400302f3  jnz     loc_1400305D0
0x1400302f9  cmp     [rcx+494h], esi
0x1400302ff  jnz     loc_1400305D0
0x140030305  lea     rdi, [rbx+r15]
0x140030309  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x140030310  jnz     loc_14003093C
0x140030316  mov     rcx, [r14+800h]
0x14003031d  mov     rdx, [r14+7F0h]
0x140030324  mov     eax, [r14+814h]
0x14003032b  mov     r8d, [r14+810h]
0x140030332  mov     qword ptr [rbp+57h+var_60+8], rcx
0x140030336  sub     rcx, rdx
0x140030339  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x14003033c  mov     rax, [r14+7F8h]
0x140030343  sar     rcx, 1
0x140030346  mov     qword ptr [rbp+57h+var_60], rax
0x14003034a  add     cx, cx
0x14003034d  movzx   eax, word ptr [r14+81Ah]
0x140030355  mov     dword ptr [rbp+57h+var_70+8], r8d
0x140030359  sub     r8w, cx
0x14003035d  mov     word ptr [rbp+57h+var_50+4], ax
0x140030361  movzx   eax, word ptr [r14+818h]
0x140030369  mov     word ptr [rbp+57h+var_50+2], r8w
0x14003036e  mov     qword ptr [rbp+57h+var_70], rdx
0x140030372  mov     word ptr [rbp+57h+var_50], ax
0x140030376  mov     qword ptr [rbp+57h+var_50+8], rsi
0x14003037a  mov     dword ptr [rbp+57h+var_40], esi
0x14003037d  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x140030384  jnz     loc_14003096F
0x14003038a  mov     rax, [r14+18h]
0x14003038e  mov     rbx, [rax+448h]
0x140030395  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x14003039c  jnz     loc_14003098A
0x1400303a2  mov     edi, dword ptr [rbp+57h+var_70+0Ch]
0x1400303a5  mov     esi, cs:UlHashTableMask
0x1400303ab  and     rsi, rdi
0x1400303ae  shl     rsi, 6
0x1400303b2  add     rsi, [rbx+438h]
0x1400303b9  mov     [rbp+57h+arg_0], rsi
0x1400303bd  call    cs:__imp_KeEnterCriticalRegion
0x1400303c4  nop     dword ptr [rax+rax+00h]
0x1400303c9  xor     edx, edx
0x1400303cb  mov     rcx, rsi
0x1400303ce  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400303d5  nop     dword ptr [rax+rax+00h]
0x1400303da  mov     rbx, [rsi+8]
0x1400303de  test    rbx, rbx
0x1400303e1  jz      short loc_1400303F8
0x1400303e3  mov     edx, dword ptr [rbp+57h+var_40]
0x1400303e6  cmp     [rbx+34h], edi
0x1400303e9  jz      loc_140030700
0x1400303ef  mov     rbx, [rbx+8]
0x1400303f3  test    rbx, rbx
0x1400303f6  jnz     short loc_1400303E6
0x1400303f8  xor     edi, edi
0x1400303fa  test    rbx, rbx
0x1400303fd  jnz     loc_140030495
0x140030403  xor     edx, edx
0x140030405  mov     rcx, rsi
0x140030408  call    cs:__imp_ExReleasePushLockSharedEx
0x14003040f  nop     dword ptr [rax+rax+00h]
0x140030414  call    cs:__imp_KeLeaveCriticalRegion
0x14003041b  nop     dword ptr [rax+rax+00h]
0x140030420  test    rdi, rdi
0x140030423  jnz     loc_140030564
0x140030429  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x140030430  jnz     loc_140030837
0x140030436  test    rdi, rdi
0x140030439  jnz     loc_14003066C
0x14003043f  mov     dword ptr [r12], 2
0x140030447  xor     esi, esi
0x140030449  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140030450  jnz     short loc_140030470
0x140030452  mov     rdi, [rsp+0D0h+arg_18]
0x14003045a  mov     eax, esi
0x14003045c  add     rsp, 0A0h
0x140030463  pop     r15
0x140030465  pop     r14
0x140030467  pop     r13
0x140030469  pop     r12
0x14003046b  pop     rsi
0x14003046c  pop     rbx
0x14003046d  pop     rbp
0x14003046e  retn
0x140030470  mov     r9, [r13+0]
0x140030474  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x14003047b  mov     edx, 0E5h
0x140030480  mov     dword ptr [rsp+0D0h+var_A8], esi
0x140030484  mov     ecx, 409h
0x140030489  mov     [rsp+0D0h+var_B0], r12
0x14003048e  call    WPP_SF_qqD
0x140030493  jmp     short loc_140030452
0x140030495  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x14003049c  jnz     loc_1400309F7
0x1400304a2  lea     r15, [rbx+18h]
0x1400304a6  cmp     [rbx+65h], dil
0x1400304aa  jnz     loc_1400308A3
0x1400304b0  mov     rbx, [r15]
0x1400304b3  xor     esi, esi
0x1400304b5  cmp     rbx, r15
0x1400304b8  jz      short loc_1400304EE
0x1400304ba  movsxd  rcx, dword ptr [rbx+0A8h]
0x1400304c1  movzx   edx, word ptr [r14+rcx*2+98Ch]
0x1400304ca  cmp     dx, si
0x1400304cd  jbe     short loc_1400304E9
0x1400304cf  cmp     ecx, 5
0x1400304d2  jz      loc_140030A1A
0x1400304d8  movzx   esi, dx
0x1400304db  lea     rdi, [rbx-10h]
0x1400304df  mov     eax, 3E8h
0x1400304e4  cmp     si, ax
0x1400304e7  jz      short loc_140030509
0x1400304e9  mov     rbx, [rbx]
0x1400304ec  jmp     short loc_1400304B5
0x1400304ee  test    rdi, rdi
0x1400304f1  jz      short loc_140030509
0x1400304f3  cmp     dword ptr [rdi+0B8h], 4
0x1400304fa  jnz     short loc_140030509
0x1400304fc  cmp     byte ptr [rdi+22Bh], 0
0x140030503  jnz     loc_140030A29
0x140030509  mov     r13, [rbp+57h+arg_8]
0x14003050d  mov     r12, [rbp+57h+arg_10]
0x140030511  mov     rsi, [rbp+57h+arg_0]
0x140030515  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x14003051c  jnz     loc_140030885
0x140030522  test    rdi, rdi
0x140030525  jz      loc_140030403
0x14003052b  lea     rdx, [rdi+4]; BugCheckParameter2
0x14003052f  mov     eax, 1
0x140030534  lock xadd [rdx], eax
0x140030538  inc     eax
0x14003053a  cmp     cs:UxDebugCheckRefcount, 0
0x140030541  jz      loc_140030403
0x140030547  cmp     eax, 0FFFFFFFFh
0x14003054a  jg      loc_140030403
0x140030550  movsxd  r9, eax; BugCheckParameter4
0x140030553  mov     ecx, 3; BugCheckParameter1
0x140030558  mov     r8d, 0Ah; BugCheckParameter3
0x14003055e  call    UlBugCheckEx
0x140030564  cmp     dword ptr [rdi+7Ch], 2
0x140030568  mov     r8, [rdi+8]
0x14003056c  jz      loc_140030A4A
0x140030572  mov     rax, [rdi+0D0h]
0x140030579  test    rax, rax
0x14003057c  jz      short loc_14003058B
0x14003057e  cmp     dword ptr [rax+0F8h], 0
0x140030585  jnz     loc_140030A90
0x14003058b  inc     dword ptr [rdi+20h]
0x14003058e  mov     dword ptr [rdi+78h], 0
0x140030595  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x14003059c  jz      loc_140030436
0x1400305a2  mov     eax, [rdi+4]
0x1400305a5  mov     edx, 19h
0x1400305aa  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1400305ae  mov     ecx, 414h
0x1400305b3  mov     rax, [r8+28h]
0x1400305b7  mov     r9, rdi
0x1400305ba  lea     r8, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids
0x1400305c1  mov     [rsp+0D0h+var_B0], rax
0x1400305c6  call    WPP_SF_qSd
0x1400305cb  jmp     loc_14003085A
0x1400305d0  mov     edx, 2
0x1400305d5  mov     rcx, r14
0x1400305d8  call    UlGenerateRoutingToken
0x1400305dd  mov     esi, eax
0x1400305df  test    eax, eax
0x1400305e1  jns     short loc_14003063B
0x1400305e3  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400305ea  jnz     loc_1400308B8
0x1400305f0  mov     eax, [r14+1F0h]
0x1400305f7  mov     [r14+1F4h], eax
0x1400305fe  mov     dword ptr [r14+1F0h], 0Bh
0x140030609  mov     dword ptr [r14+74Ch], 12h
0x140030614  test    byte ptr cs:xmmword_1401A2C90+9, 40h
0x14003061b  jnz     loc_1400308E9
0x140030621  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140030628  jnz     loc_14003091A
0x14003062e  mov     dword ptr [r12], 5
0x140030636  jmp     loc_140030449
0x14003063b  lea     r8, [rbp+57h+var_70]
0x14003063f  mov     dl, 1
0x140030641  mov     rcx, r14
0x140030644  call    UlInitSearchKeyFromRequest
0x140030649  mov     rcx, [r14+18h]
0x14003064d  lea     rdx, [rbp+57h+var_70]
0x140030651  mov     r8, r14
0x140030654  mov     rcx, [rcx+448h]
0x14003065b  call    UlCheckoutUriCacheEntry
0x140030660  mov     rdi, rax
0x140030663  test    rax, rax
0x140030666  jz      loc_140030935
0x14003066c  cmp     dword ptr [rdi+200h], 0
0x140030673  jz      loc_140030770
0x140030679  mov     ecx, [rdi+160h]
0x14003067f  cmp     ecx, 4
0x140030682  jnz     loc_1400307B7
0x140030688  mov     rax, [r14+18h]
0x14003068c  mov     esi, 0C0000034h
0x140030691  mov     rbx, [rax+448h]
0x140030698  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14003069f  jnz     loc_140030AD8
0x1400306a5  cmp     dword ptr [rbx+534h], 0
0x1400306ac  jg      loc_140174A37
0x1400306b2  cmp     dword ptr [rbx+530h], 0
0x1400306b9  jg      loc_140174A37
0x1400306bf  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400306c6  jnz     loc_140030AFF
0x1400306cc  test    esi, esi
0x1400306ce  jns     loc_140030770
0x1400306d4  cmp     esi, 0C0000034h
0x1400306da  jnz     loc_140030812
0x1400306e0  mov     eax, [r14+898h]
0x1400306e7  test    al, 20h
0x1400306e9  jz      loc_140030B1D
0x1400306ef  mov     dword ptr [r12], 1
0x1400306f7  mov     [r13+0], rdi
0x1400306fb  jmp     loc_140030447
0x140030700  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x140030704  test    rcx, rcx
0x140030707  jnz     loc_1400309BE
0x14003070d  mov     eax, [rbx+30h]
0x140030710  cmp     dword ptr [rbp+57h+var_70+8], eax
0x140030713  jnz     loc_1400303EF
0x140030719  xor     eax, eax
0x14003071b  lea     rdx, [rbp+57h+String2]; String2
0x14003071f  mov     dword ptr [rbp+57h+String1+4], eax
0x140030722  lea     rcx, [rbp+57h+String1]; String1
0x140030726  mov     dword ptr [rbp+57h+String2+4], eax
0x140030729  mov     r8b, 1; CaseInSensitive
0x14003072c  movzx   eax, word ptr [rbp+57h+var_70+8]
0x140030730  mov     [rbp+57h+String1.Length], ax
0x140030734  mov     [rbp+57h+String2.Length], ax
0x140030738  add     ax, 2
0x14003073c  mov     [rbp+57h+String1.MaximumLength], ax
0x140030740  mov     [rbp+57h+String2.MaximumLength], ax
0x140030744  mov     rax, qword ptr [rbp+57h+var_70]
0x140030748  mov     [rbp+57h+String1.Buffer], rax
0x14003074c  mov     rax, [rbx+28h]
0x140030750  mov     [rbp+57h+String2.Buffer], rax
0x140030754  call    cs:__imp_RtlEqualUnicodeString
0x14003075b  nop     dword ptr [rax+rax+00h]
0x140030760  test    al, al
0x140030762  jnz     loc_1400303F8
0x140030768  mov     edx, dword ptr [rbp+57h+var_40]
0x14003076b  jmp     loc_1400303EF
0x140030770  mov     rcx, rdi; P
0x140030773  call    UlCheckinUriCacheEntry
0x140030778  mov     dword ptr [r12], 2
0x140030780  jmp     loc_140030447
0x140030785  test    r14, r14
0x140030788  jnz     short loc_140030809
0x14003078a  mov     [rsp+0D0h+var_A0], r12
0x14003078f  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140030796  mov     [rsp+0D0h+var_A8], r13
0x14003079b  mov     edx, 0E4h
0x1400307a0  mov     ecx, 409h
0x1400307a5  mov     [rsp+0D0h+var_B0], rax
0x1400307aa  mov     r9, r14
0x1400307ad  call    WPP_SF_qqqi
0x1400307b2  jmp     loc_1400302CE
0x1400307b7  test    ecx, ecx
0x1400307b9  jz      short loc_1400307DF
0x1400307bb  sub     ecx, 1
0x1400307be  jz      loc_140030ABC
0x1400307c4  sub     ecx, 1
0x1400307c7  jz      loc_1400306E0
0x1400307cd  sub     ecx, 1
0x1400307d0  jz      loc_1400306E0
0x1400307d6  cmp     ecx, 2
0x1400307d9  jz      loc_1400306E0
  ... truncated ...
```
