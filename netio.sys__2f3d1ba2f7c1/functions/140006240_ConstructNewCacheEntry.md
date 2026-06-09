# ConstructNewCacheEntry

- ea: `0x140006240`
- end: `0x1400068c2`
- name: `ConstructNewCacheEntry`
- size: `1666`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1400016d0`
- `0x140046734`

## callees

- `0x140001464`
- `0x1400022b0`
- `0x140004bf0`
- `0x140006240`
- `0x1400068d0`
- `0x140006c40`
- `0x140007bc0`
- `0x140008000`
- `0x140008130`
- `0x140009520`
- `0x14004efd4`
- `0x140078080`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000629a`
- `ntoskrnl!ExAllocatePool2` at `0x1400062fe`
- `ntoskrnl!ExAllocatePool2` at `0x14000629a`
- `ntoskrnl!ExAllocatePool2` at `0x1400062fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065fc`

## string_xrefs

- `0x14000645f`: `InitializeCacheEntry`
- `0x14000679a`: `InitializeCacheEntry`
- `0x140006716`: `ConstructNewCacheEntry`

## pseudocode

```c
__int64 ConstructNewCacheEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, ...)
{
  char *Pool2; // rax
  char *v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 matched; // r13
  void *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r11d
  unsigned int v19; // r9d
  __int64 v20; // r10
  __int64 v21; // r8
  __int64 v22; // rax
  signed __int64 v23; // rcx
  _QWORD *v24; // rax
  unsigned int i; // ebx
  __int64 v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rdi
  __int64 v30; // r14
  int v31; // esi
  __int64 v32; // rbx
  __int64 v33; // rcx
  BOOL active; // eax
  int v35; // ecx
  __int64 v36; // rdi
  unsigned int v37; // esi
  __int64 j; // rbx
  int v39; // eax
  __int64 v40; // r8
  PVOID v41; // rbx
  PDEVICE_OBJECT v42; // rcx
  bool v43; // zf
  __int128 v44; // [rsp+30h] [rbp-58h] BYREF
  __int128 v45; // [rsp+40h] [rbp-48h]
  PVOID Entry; // [rsp+90h] [rbp+8h] BYREF
  __int64 v47; // [rsp+A8h] [rbp+20h]
  _QWORD *v48; // [rsp+C0h] [rbp+38h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h]
  va_list va1; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v48 = va_arg(va1, _QWORD *);
  v47 = a4;
  v43 = *(_DWORD *)(a1 + 32) == 4;
  v44 = 0;
  Entry = 0;
  v45 = 0;
  *v48 = 0;
  if ( !v43 )
  {
    matched = ConvertTableToEnumTemplate(a2, a3, &v44);
    if ( matched )
      goto LABEL_45;
    for ( i = 0; i < *(_DWORD *)(a2 + 72); ++i )
    {
      v27 = *(_QWORD *)(a2 + 104) + 16LL * i;
      v28 = *(int *)(v27 + 8);
      if ( (_DWORD)v28 != 4 )
      {
        matched = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, PVOID *, _DWORD))&gWfpGlobal[1].L.Future[14 * v28 + 2])(
                    *(_QWORD *)v27,
                    &v44,
                    2,
                    &Entry,
                    0);
        if ( matched )
          goto LABEL_45;
      }
    }
    v29 = Entry;
    if ( !Entry )
      goto LABEL_45;
    v30 = a5;
    v31 = 1;
    do
    {
      v32 = 0;
      if ( *((_WORD *)v29 + 12) )
      {
        while ( 1 )
        {
          v33 = v29[v32 + 4];
          if ( (*(_DWORD *)(*(_QWORD *)(v33 + 24) + 40LL) & 0x4000) == 0 )
            break;
          active = IsActiveCallout(v33, v30, 0);
          v35 = 0;
          if ( !active )
            v35 = v31;
          v31 = v35;
          if ( v35 )
          {
            v32 = (unsigned int)(v32 + 1);
            if ( (unsigned int)v32 < *((unsigned __int16 *)v29 + 12) )
              continue;
          }
          goto LABEL_33;
        }
        v31 = 0;
      }
LABEL_33:
      v29 = (_QWORD *)v29[2];
    }
    while ( v29 );
    if ( v31 )
      goto LABEL_45;
    matched = SortMatchList(Entry);
    if ( matched )
      goto LABEL_45;
    matched = ComputeUnmatchedState(&v44, Entry);
    if ( matched )
      goto LABEL_45;
  }
  Pool2 = (char *)ExAllocatePool2(64, 176, 1215325783);
  v10 = Pool2;
  if ( !Pool2 )
  {
    matched = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"ExAllocatePool2",
        23);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpPoolAllocNonPaged",
        23);
    }
    goto LABEL_45;
  }
  memset(Pool2, 0, 0xB0u);
  *((_DWORD *)v10 + 6) = *(_DWORD *)(a1 + 36);
  if ( *(_DWORD *)(a1 + 32) != 4 )
  {
    v40 = v45;
    v41 = Entry;
    *((_QWORD *)v10 + 9) = v45;
    *((_DWORD *)v10 + 16) = HIDWORD(v44);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_98687f0bf5ea3e300b9458f4256a8986_Traceguids, v10, v40);
    }
    *((_QWORD *)v10 + 10) = v41;
    *((_QWORD *)v10 + 2) = ComputeHash(a3, *(unsigned int *)(a2 + 52));
    *((_QWORD *)v10 + 5) = v10 + 32;
    *((_QWORD *)v10 + 4) = v10 + 32;
    goto LABEL_17;
  }
  v11 = a6;
  if ( a6 )
  {
    *(_QWORD *)(v10 + 76) = *(_QWORD *)(a6 + 12);
    v12 = 0;
    v13 = ExAllocatePool2(64, *(unsigned int *)(v11 + 24), 1097885271);
    *((_QWORD *)v10 + 12) = v13;
    matched = -1073741801;
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"ExAllocatePool2",
          23);
      }
      v12 = -1073741801;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpPoolAllocNonPaged",
          23);
      }
    }
    v15 = (void *)*((_QWORD *)v10 + 12);
    if ( v15 )
    {
      matched = v12;
      memmove(v15, *(const void **)(v11 + 32), *(unsigned int *)(v11 + 24));
      v16 = 0;
      *((_DWORD *)v10 + 22) = *(_DWORD *)(v11 + 24);
      v10[68] = *(_BYTE *)(v11 + 4);
      *((_DWORD *)v10 + 18) = *(_DWORD *)(v11 + 8);
      *((_DWORD *)v10 + 16) = *(_DWORD *)v11;
      v17 = 0;
      v18 = *(_DWORD *)(a1 + 36);
      v19 = *(_DWORD *)(v11 + 24);
      v20 = *(_QWORD *)(v11 + 32);
      LODWORD(v47) = v18;
      if ( v19 )
      {
        do
        {
          v21 = *(unsigned __int8 *)(v16 + v20);
          v16 = (unsigned int)(v16 + 1);
          v17 = v21 + 37 * v17;
        }
        while ( (unsigned int)v16 < v19 );
      }
      v22 = 37
          * (BYTE2(v47)
           + 37
           * (BYTE1(v47)
            + 37
            * ((unsigned __int8)v18
             + 37
             * (*(unsigned __int8 *)(v11 + 19)
              + 37
              * (*(unsigned __int8 *)(v11 + 18)
               + 37
               * (*(unsigned __int8 *)(v11 + 17)
                + 37
                * (*(unsigned __int8 *)(v11 + 16)
                 + 37
                 * (*(unsigned __int8 *)(v11 + 15)
                  + 37
                  * (*(unsigned __int8 *)(v11 + 14)
                   + 37 * (*(unsigned __int8 *)(v11 + 13) + 37 * (*(unsigned __int8 *)(v11 + 12) + 37 * v17)))))))))))
          + BYTE3(v47);
      if ( !v22 )
        v22 = -1;
      *((_QWORD *)v10 + 2) = v22;
      *((_QWORD *)v10 + 5) = v10 + 32;
      *((_QWORD *)v10 + 4) = v10 + 32;
      if ( !v12 )
        goto LABEL_16;
      goto LABEL_12;
    }
    v42 = WPP_GLOBAL_Control;
    v43 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
  }
  else
  {
    v42 = WPP_GLOBAL_Control;
    v43 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    matched = -1073741811;
  }
  if ( !v43 && BYTE1(v42->Timer) >= 2u && (HIDWORD(v42->Timer) & 0x1000) != 0 )
    WPP_SF_sd(
      v42->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"InitializeCacheEntry",
      matched);
LABEL_12:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"InitializeCacheEntry",
      matched);
  }
LABEL_16:
  if ( !matched )
  {
LABEL_17:
    v23 = _InterlockedExchangeAdd64((volatile signed __int64 *)&gWfpGlobal[12].L.Depth, 1u);
    v24 = v48;
    *((_QWORD *)v10 + 7) = v23 + 1;
    *v24 = v10;
    return 0;
  }
  WfpPoolFree(v10 + 96);
  ExFreePoolWithTag(v10, 0);
LABEL_45:
  FreeMatchBufListInternal(Entry);
  v36 = v45;
  v48 = (_QWORD *)v45;
  if ( (_QWORD)v45 )
  {
    v37 = HIDWORD(v44);
    for ( j = 0; (unsigned int)j < v37; j = (unsigned int)(j + 1) )
    {
      v39 = *(_DWORD *)(v36 + 24 * j + 8);
      if ( v39 == 18 || v39 == 4 || v39 == 11 )
        WfpPoolFree(v36 + 8 * (3 * j + 2));
    }
    WfpPoolFree((_QWORD **)va);
  }
  if ( matched )
    WfpReportError(matched, "ConstructNewCacheEntry");
  return matched;
}

```

## disassembly

```asm
0x140006240  mov     rax, rsp
0x140006243  mov     [rax+10h], rbx
0x140006247  mov     [rax+20h], r9
0x14000624b  push    rbp
0x14000624c  push    rsi
0x14000624d  push    rdi
0x14000624e  push    r12
0x140006250  push    r13
0x140006252  push    r14
0x140006254  push    r15
0x140006256  sub     rsp, 50h
0x14000625a  xor     r14d, r14d
0x14000625d  xorps   xmm0, xmm0
0x140006260  cmp     dword ptr [rcx+20h], 4
0x140006264  mov     r12, r8
0x140006267  movups  xmmword ptr [rax-58h], xmm0
0x14000626b  mov     [rax+8], r14
0x14000626f  mov     rbp, rdx
0x140006272  movups  xmmword ptr [rax-48h], xmm0
0x140006276  mov     rax, [rsp+88h+arg_30]
0x14000627e  mov     r15, rcx
0x140006281  mov     [rax], r14
0x140006284  jnz     loc_1400064C7
0x14000628a  mov     edx, 0B0h
0x14000628f  mov     ecx, 40h ; '@'
0x140006294  mov     r8d, 48706657h
0x14000629a  call    cs:__imp_ExAllocatePool2
0x1400062a1  nop     dword ptr [rax+rax+00h]
0x1400062a6  mov     rdi, rax
0x1400062a9  test    rax, rax
0x1400062ac  jz      loc_14000660A
0x1400062b2  xor     edx, edx; Val
0x1400062b4  mov     r8d, 0B0h; Size
0x1400062ba  mov     rcx, rax; void *
0x1400062bd  call    memset
0x1400062c2  mov     eax, [r15+24h]
0x1400062c6  mov     [rdi+18h], eax
0x1400062c9  cmp     dword ptr [r15+20h], 4
0x1400062ce  jnz     loc_1400066BE
0x1400062d4  mov     rsi, [rsp+88h+arg_28]
0x1400062dc  test    rsi, rsi
0x1400062df  jz      loc_140006761
0x1400062e5  mov     rax, [rsi+0Ch]
0x1400062e9  mov     ecx, 40h ; '@'
0x1400062ee  mov     [rdi+4Ch], rax
0x1400062f2  mov     r8d, 41706657h
0x1400062f8  mov     edx, [rsi+18h]
0x1400062fb  mov     rbx, r14
0x1400062fe  call    cs:__imp_ExAllocatePool2
0x140006305  nop     dword ptr [rax+rax+00h]
0x14000630a  mov     [rdi+60h], rax
0x14000630e  lea     r14, WPP_GLOBAL_Control
0x140006315  mov     r13, 0FFFFFFFFC0000017h
0x14000631c  test    rax, rax
0x14000631f  jz      loc_1400067F7
0x140006325  mov     rcx, [rdi+60h]; void *
0x140006329  test    rcx, rcx
0x14000632c  jz      loc_1400067BC
0x140006332  mov     r8d, [rsi+18h]; Size
0x140006336  mov     r13, rbx
0x140006339  mov     rdx, [rsi+20h]; Src
0x14000633d  call    memmove
0x140006342  mov     eax, [rsi+18h]
0x140006345  xor     ecx, ecx
0x140006347  mov     [rdi+58h], eax
0x14000634a  movzx   eax, byte ptr [rsi+4]
0x14000634e  mov     [rdi+44h], al
0x140006351  mov     eax, [rsi+8]
0x140006354  mov     [rdi+48h], eax
0x140006357  mov     eax, [rsi]
0x140006359  mov     [rdi+40h], eax
0x14000635c  xor     eax, eax
0x14000635e  mov     r11d, [r15+24h]
0x140006362  mov     r9d, [rsi+18h]
0x140006366  mov     r10, [rsi+20h]
0x14000636a  mov     dword ptr [rsp+88h+arg_18], r11d
0x140006372  test    r9d, r9d
0x140006375  jz      short loc_140006393
0x140006377  nop     word ptr [rax+rax+00000000h]
0x140006380  movzx   r8d, byte ptr [rcx+r10]
0x140006385  inc     ecx
0x140006387  imul    rax, 25h ; '%'
0x14000638b  add     rax, r8
0x14000638e  cmp     ecx, r9d
0x140006391  jb      short loc_140006380
0x140006393  imul    rcx, rax, 25h ; '%'
0x140006397  movzx   eax, byte ptr [rsi+0Ch]
0x14000639b  add     rcx, rax
0x14000639e  movzx   eax, byte ptr [rsi+0Dh]
0x1400063a2  imul    rdx, rcx, 25h ; '%'
0x1400063a6  add     rdx, rax
0x1400063a9  movzx   eax, byte ptr [rsi+0Eh]
0x1400063ad  imul    rcx, rdx, 25h ; '%'
0x1400063b1  add     rcx, rax
0x1400063b4  movzx   eax, byte ptr [rsi+0Fh]
0x1400063b8  imul    rdx, rcx, 25h ; '%'
0x1400063bc  add     rdx, rax
0x1400063bf  movzx   eax, byte ptr [rsi+10h]
0x1400063c3  imul    rcx, rdx, 25h ; '%'
0x1400063c7  add     rcx, rax
0x1400063ca  movzx   eax, byte ptr [rsi+11h]
0x1400063ce  imul    rdx, rcx, 25h ; '%'
0x1400063d2  add     rdx, rax
0x1400063d5  movzx   eax, byte ptr [rsi+12h]
0x1400063d9  imul    rcx, rdx, 25h ; '%'
0x1400063dd  add     rcx, rax
0x1400063e0  movzx   eax, byte ptr [rsi+13h]
0x1400063e4  imul    rdx, rcx, 25h ; '%'
0x1400063e8  add     rdx, rax
0x1400063eb  movzx   eax, r11b
0x1400063ef  imul    rcx, rdx, 25h ; '%'
0x1400063f3  add     rcx, rax
0x1400063f6  movzx   eax, byte ptr [rsp+88h+arg_18+1]
0x1400063fe  imul    rdx, rcx, 25h ; '%'
0x140006402  add     rdx, rax
0x140006405  movzx   eax, byte ptr [rsp+88h+arg_18+2]
0x14000640d  imul    rcx, rdx, 25h ; '%'
0x140006411  add     rcx, rax
0x140006414  movzx   eax, byte ptr [rsp+88h+arg_18+3]
0x14000641c  imul    rcx, 25h ; '%'
0x140006420  add     rax, rcx
0x140006423  jnz     short loc_14000642C
0x140006425  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000642c  mov     [rdi+10h], rax
0x140006430  lea     rax, [rdi+20h]
0x140006434  mov     [rax+8], rax
0x140006438  mov     [rax], rax
0x14000643b  test    rbx, rbx
0x14000643e  jz      short loc_14000647C
0x140006440  mov     rcx, cs:WPP_GLOBAL_Control
0x140006447  cmp     rcx, r14
0x14000644a  jz      short loc_14000647C
0x14000644c  cmp     byte ptr [rcx+29h], 2
0x140006450  jb      short loc_14000647C
0x140006452  test    dword ptr [rcx+2Ch], 1000h
0x140006459  jz      short loc_14000647C
0x14000645b  mov     rcx, [rcx+18h]
0x14000645f  lea     r9, aInitializecach; "InitializeCacheEntry"
0x140006466  mov     edx, 0Fh
0x14000646b  mov     dword ptr [rsp+88h+var_68], r13d
0x140006470  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140006477  call    WPP_SF_sd
0x14000647c  test    r13, r13
0x14000647f  jnz     loc_1400065EE
0x140006485  mov     rax, cs:gWfpGlobal
0x14000648c  mov     ecx, 1
0x140006491  lock xadd [rax+610h], rcx
0x14000649a  mov     rax, [rsp+88h+arg_30]
0x1400064a2  inc     rcx
0x1400064a5  mov     [rdi+38h], rcx
0x1400064a9  mov     [rax], rdi
0x1400064ac  xor     eax, eax
0x1400064ae  mov     rbx, [rsp+88h+arg_8]
0x1400064b6  add     rsp, 50h
0x1400064ba  pop     r15
0x1400064bc  pop     r14
0x1400064be  pop     r13
0x1400064c0  pop     r12
0x1400064c2  pop     rdi
0x1400064c3  pop     rsi
0x1400064c4  pop     rbp
0x1400064c5  retn
0x1400064c7  lea     r8, [rsp+88h+var_58]
0x1400064cc  mov     rdx, r12
0x1400064cf  mov     rcx, rbp
0x1400064d2  call    ConvertTableToEnumTemplate
0x1400064d7  mov     r13, rax
0x1400064da  test    rax, rax
0x1400064dd  jnz     loc_14000664D
0x1400064e3  mov     ebx, r14d
0x1400064e6  cmp     ebx, [rbp+48h]
0x1400064e9  jnb     short loc_140006542
0x1400064eb  mov     ecx, ebx
0x1400064ed  shl     rcx, 4
0x1400064f1  add     rcx, [rbp+68h]
0x1400064f5  movsxd  rax, dword ptr [rcx+8]
0x1400064f9  cmp     eax, 4
0x1400064fc  jnz     short loc_140006502
0x1400064fe  inc     ebx
0x140006500  jmp     short loc_1400064E6
0x140006502  mov     rcx, [rcx]
0x140006505  lea     r9, [rsp+88h+Entry]
0x14000650d  add     rax, 4
0x140006511  mov     dword ptr [rsp+88h+var_68], r14d
0x140006516  imul    rdx, rax, 38h ; '8'
0x14000651a  mov     rax, cs:gWfpGlobal
0x140006521  mov     r8d, 2
0x140006527  mov     rax, [rdx+rax]
0x14000652b  lea     rdx, [rsp+88h+var_58]
0x140006530  call    _guard_dispatch_icall
0x140006535  mov     r13, rax
0x140006538  test    rax, rax
0x14000653b  jz      short loc_1400064FE
0x14000653d  jmp     loc_14000664D
0x140006542  mov     rdi, [rsp+88h+Entry]
0x14000654a  test    rdi, rdi
0x14000654d  jz      loc_14000664D
0x140006553  mov     r14, [rsp+88h+arg_20]
0x14000655b  mov     esi, 1
0x140006560  xor     ebx, ebx
0x140006562  xor     eax, eax
0x140006564  cmp     ax, [rdi+18h]
0x140006568  jnb     short loc_1400065A2
0x14000656a  mov     rcx, [rdi+rbx*8+20h]
0x14000656f  mov     rax, [rcx+18h]
0x140006573  test    dword ptr [rax+28h], 4000h
0x14000657a  jz      loc_14000675A
0x140006580  xor     r8d, r8d
0x140006583  mov     rdx, r14
0x140006586  call    IsActiveCallout
0x14000658b  xor     ecx, ecx
0x14000658d  test    eax, eax
0x14000658f  cmovz   ecx, esi
0x140006592  mov     esi, ecx
0x140006594  test    ecx, ecx
0x140006596  jz      short loc_1400065A2
0x140006598  movzx   eax, word ptr [rdi+18h]
0x14000659c  inc     ebx
0x14000659e  cmp     ebx, eax
0x1400065a0  jb      short loc_14000656A
0x1400065a2  mov     rdi, [rdi+10h]
0x1400065a6  test    rdi, rdi
0x1400065a9  jnz     short loc_140006560
0x1400065ab  test    esi, esi
0x1400065ad  jnz     loc_14000664D
0x1400065b3  mov     rcx, [rsp+88h+Entry]
0x1400065bb  call    SortMatchList
0x1400065c0  mov     r13, rax
0x1400065c3  test    rax, rax
0x1400065c6  jnz     loc_14000664D
0x1400065cc  mov     rdx, [rsp+88h+Entry]
0x1400065d4  lea     rcx, [rsp+88h+var_58]
0x1400065d9  call    ComputeUnmatchedState
0x1400065de  mov     r13, rax
0x1400065e1  test    rax, rax
0x1400065e4  jnz     short loc_14000664D
0x1400065e6  xor     r14d, r14d
0x1400065e9  jmp     loc_14000628A
0x1400065ee  lea     rcx, [rdi+60h]
0x1400065f2  call    WfpPoolFree
0x1400065f7  xor     edx, edx; Tag
0x1400065f9  mov     rcx, rdi; P
0x1400065fc  call    cs:__imp_ExFreePoolWithTag
0x140006603  nop     dword ptr [rax+rax+00h]
0x140006608  jmp     short loc_14000664D
0x14000660a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006611  lea     r14, WPP_GLOBAL_Control
0x140006618  mov     r13, 0FFFFFFFFC0000017h
0x14000661f  cmp     rcx, r14
0x140006622  jz      short loc_14000662E
0x140006624  cmp     byte ptr [rcx+29h], 2
0x140006628  jnb     loc_140006727
0x14000662e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006635  cmp     rcx, r14
0x140006638  jz      short loc_14000664D
0x14000663a  cmp     byte ptr [rcx+29h], 2
0x14000663e  jb      short loc_14000664D
0x140006640  test    dword ptr [rcx+2Ch], 1000h
0x140006647  jnz     loc_140006885
0x14000664d  mov     rcx, [rsp+88h+Entry]; Entry
0x140006655  call    FreeMatchBufListInternal
0x14000665a  mov     rdi, qword ptr [rsp+88h+var_48]
0x14000665f  mov     [rsp+88h+arg_30], rdi
0x140006667  test    rdi, rdi
0x14000666a  jz      short loc_1400066B1
0x14000666c  mov     esi, [rsp+88h+var_4C]
0x140006670  xor     ebx, ebx
0x140006672  test    esi, esi
0x140006674  jz      short loc_1400066A4
0x140006676  nop     word ptr [rax+rax+00000000h]
0x140006680  lea     rcx, [rbx+rbx*2]
0x140006684  mov     eax, [rdi+rcx*8+8]
0x140006688  cmp     eax, 12h
0x14000668b  jnz     loc_1400068AB
0x140006691  add     rcx, 2
0x140006695  lea     rcx, [rdi+rcx*8]
0x140006699  call    WfpPoolFree
0x14000669e  inc     ebx
0x1400066a0  cmp     ebx, esi
0x1400066a2  jb      short loc_140006680
0x1400066a4  lea     rcx, [rsp+88h+arg_30]
0x1400066ac  call    WfpPoolFree
0x1400066b1  test    r13, r13
0x1400066b4  jnz     short loc_140006716
0x1400066b6  mov     rax, r13
0x1400066b9  jmp     loc_1400064AE
0x1400066be  mov     r8, qword ptr [rsp+88h+var_48]
0x1400066c3  mov     rbx, [rsp+88h+Entry]
0x1400066cb  mov     [rdi+48h], r8
0x1400066cf  mov     eax, [rsp+88h+var_4C]
0x1400066d3  mov     [rdi+40h], eax
0x1400066d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066dd  lea     r14, WPP_GLOBAL_Control
0x1400066e4  cmp     rcx, r14
0x1400066e7  jz      short loc_1400066F3
0x1400066e9  cmp     byte ptr [rcx+29h], 5
0x1400066ed  jnb     loc_1400067C8
0x1400066f3  mov     [rdi+50h], rbx
0x1400066f7  mov     rcx, r12
0x1400066fa  mov     edx, [rbp+34h]
  ... truncated ...
```
