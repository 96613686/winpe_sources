# PerflibciQueryV2Provider(ulong,ushort const *,EXT_OBJ_LIST *,ulong,uchar * *,ulong *,ulong *)

- ea: `0x180015250`
- end: `0x1800157ca`
- name: `?PerflibciQueryV2Provider@@YAKKPEBGPEAUEXT_OBJ_LIST@@KPEAPEAEPEAK3@Z`
- size: `1402`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, struct EXT_OBJ_LIST *, unsigned int, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012604`

## callees

- `0x180001520`
- `0x180005da0`
- `0x180005f20`
- `0x180006bc0`
- `0x1800070d0`
- `0x1800072d0`
- `0x180007300`
- `0x180008050`
- `0x18000aac8`
- `0x1800146c8`
- `0x180014b54`
- `0x180015250`
- `0x1800165d0`
- `0x1800166cc`
- `0x18001e431`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015390`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015390`

## pseudocode

```c
__int64 __fastcall PerflibciQueryV2Provider(
        unsigned int a1,
        const unsigned __int16 *a2,
        struct EXT_OBJ_LIST *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned int *a7)
{
  unsigned int Handle; // edi
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  char v14; // r8
  __int64 v15; // r9
  unsigned int i; // ecx
  struct _PERF_QUERY **v17; // rbx
  __int64 v18; // rax
  unsigned int v19; // esi
  __int64 v20; // rax
  char v21; // dl
  _QWORD *v22; // r15
  __int64 v23; // r14
  char v24; // r9
  unsigned int v25; // ecx
  int v26; // edx
  unsigned int j; // r8d
  unsigned int v28; // eax
  struct _PERF_QUERY *v29; // rax
  struct _PERF_QUERY *v30; // rsi
  unsigned int v31; // eax
  unsigned int v32; // edx
  unsigned int v33; // esi
  struct _PERF_QUERY *v34; // rax
  struct _PERF_QUERY *v35; // rbp
  struct _PERF_QUERY *v36; // rdx
  __int64 v37; // rax
  struct _PERF_QUERY *v38; // rcx
  __int128 v39; // xmm0
  struct _PERF_QUERY *v40; // rsi
  unsigned int v41; // edi
  struct _PERF_QUERY *v42; // rax
  struct _PERF_QUERY *v43; // rcx
  unsigned int CounterData; // eax
  struct _PERF_QUERY *v45; // rcx
  __int64 v46; // rax
  unsigned int v48[22]; // [rsp+30h] [rbp-58h] BYREF

  Handle = 87;
  v48[0] = 0;
  v12 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids, a1);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a5 || !a6 || !a7 )
    goto LABEL_87;
  *a6 = 0;
  *a7 = 0;
  *a5 = 0;
  Handle = PerflibciEnsureCounterSetList();
  if ( Handle )
    goto LABEL_86;
  if ( a3 && !a4 )
  {
    Handle = 87;
    goto LABEL_86;
  }
  v13 = g_ObjectList;
  v14 = 0;
  do
  {
    if ( !v13 )
      goto LABEL_86;
    v15 = v13[4];
    if ( v15 )
    {
      if ( a3 )
      {
        for ( i = 0; i < a4; ++i )
        {
          if ( (*((_BYTE *)a3 + 8 * i + 4) & 1) == 0 && *(_DWORD *)(v15 + 92) == *((_DWORD *)a3 + 2 * i) )
            goto LABEL_20;
        }
      }
      else
      {
LABEL_20:
        v14 = 1;
      }
    }
    v13 = (_QWORD *)v13[3];
  }
  while ( !v14 );
  Handle = PerflibciLocalWaitForMutex(g_hGlobalMutex);
  if ( Handle )
    goto LABEL_86;
  v17 = (struct _PERF_QUERY **)g_QueryList;
  if ( !g_QueryList )
    goto LABEL_28;
  do
  {
    if ( *((_DWORD *)v17 + 6) == a1 && CompareStringOrdinal(a2, -1, (LPCWCH)v17[2], -1, 1) == 2 )
      break;
    v17 = (struct _PERF_QUERY **)v17[1];
  }
  while ( v17 );
  if ( !v17 )
  {
LABEL_28:
    v18 = -1;
    do
      ++v18;
    while ( a2[v18] );
    v19 = 2 * v18 + 2;
    if ( (unsigned __int64)(2 * v18 + 2) >> 32 )
      goto LABEL_84;
    if ( (unsigned int)(2 * v18 + 2) < 0xFFFFFF98 && 2 * (_DWORD)v18 != -2 )
      v17 = (struct _PERF_QUERY **)operator new((unsigned int)(2 * v18 + 106));
    if ( !v17 )
    {
LABEL_84:
      Handle = 14;
      goto LABEL_85;
    }
    v20 = operator new(256);
    v17[5] = (struct _PERF_QUERY *)v20;
    if ( !v20 )
    {
      Handle = 14;
LABEL_36:
      operator delete(v17[5]);
      operator delete(v17);
      goto LABEL_85;
    }
    Handle = PerflibciOpenLocalQueryHandle(0, v21, v17);
    if ( Handle )
      goto LABEL_36;
    NtCurrentTeb()->EtwLocalData = (PVOID)1718773072;
    v17[1] = (struct _PERF_QUERY *)g_QueryList;
    *((_DWORD *)v17 + 7) = 64;
    *((_DWORD *)v17 + 6) = a1;
    v17[2] = (struct _PERF_QUERY *)(v17 + 13);
    StringCbCopyW((unsigned __int16 *)v17 + 52, v19, a2);
    g_QueryList = v17;
  }
  v22 = g_ObjectList;
  if ( !g_ObjectList )
  {
LABEL_71:
    if ( !*((_DWORD *)v17 + 12) )
      goto LABEL_81;
    Handle = PerflibciLocalValidateCounters(*v17, (__int64)v17[7], *((_DWORD *)v17 + 17), 1);
    if ( Handle )
    {
      *((_DWORD *)v17 + 17) = 0;
      *((_DWORD *)v17 + 12) = 0;
    }
    else
    {
      Handle = PerflibciLocalQueryCounterInfo((__int64)*v17, v17[7], *((_DWORD *)v17 + 16), v48);
      if ( Handle == 8 )
      {
        while ( 1 )
        {
          v40 = v17[7];
          v41 = (v48[0] + 7) & 0xFFFFFFF8;
          v42 = (struct _PERF_QUERY *)operator new(v41);
          v17[7] = v42;
          if ( !v42 )
            break;
          v43 = *v17;
          *((_DWORD *)v17 + 16) = v41;
          Handle = PerflibciLocalQueryCounterInfo((__int64)v43, v42, v41, v48);
          if ( Handle != 8 )
            goto LABEL_78;
        }
        operator delete(v40);
        v17[8] = 0;
        Handle = 14;
      }
LABEL_78:
      if ( !Handle )
      {
        *((_DWORD *)v17 + 17) = v48[0];
        Handle = PerflibciBuildDefinitionBlock(v17);
        if ( !Handle )
        {
          *((_DWORD *)v17 + 12) = 0;
LABEL_81:
          while ( 1 )
          {
            CounterData = PerflibciLocalQueryCounterData(*v17, v17[11], *((_DWORD *)v17 + 24), v48);
            Handle = CounterData;
            if ( CounterData != 8 )
              break;
            v45 = v17[11];
            *((_DWORD *)v17 + 24) = (v48[0] + 7) & 0xFFFFFFF8;
            operator delete(v45);
            v46 = operator new(*((unsigned int *)v17 + 24));
            v17[11] = (struct _PERF_QUERY *)v46;
            if ( !v46 )
            {
              *((_DWORD *)v17 + 24) = 0;
              goto LABEL_84;
            }
          }
          if ( !CounterData )
            Handle = PerflibciBuildPerfObjectType(v17, a5, a6, a7);
        }
      }
    }
    goto LABEL_85;
  }
  do
  {
    v23 = v22[4];
    if ( v23 )
    {
      if ( !a3 )
        goto LABEL_48;
      v24 = 0;
      v25 = 0;
      if ( a4 )
      {
        do
        {
          v26 = *((_DWORD *)a3 + 2 * v25 + 1);
          if ( (v26 & 1) == 0 && *(_DWORD *)(v23 + 92) == *((_DWORD *)a3 + 2 * v25) )
          {
            v24 = 1;
            *((_DWORD *)a3 + 2 * v25 + 1) = v26 | 1;
          }
          ++v25;
        }
        while ( v25 < a4 );
        if ( v24 )
        {
LABEL_48:
          for ( j = 0; j < *((_DWORD *)v17 + 8); ++j )
          {
            if ( *((_DWORD *)v17[5] + j) == *(_DWORD *)(v23 + 92) )
              goto LABEL_69;
          }
          v28 = *((_DWORD *)v17 + 7);
          if ( *((_DWORD *)v17 + 8) >= v28 && v28 <= 0x3FFFFFBF )
          {
            v29 = (struct _PERF_QUERY *)operator new(saturated_mul(v28 + 64, 4u));
            v30 = v29;
            if ( v29 )
            {
              memcpy_0(v29, v17[5], 4LL * *((unsigned int *)v17 + 8));
              operator delete(v17[5]);
              *((_DWORD *)v17 + 7) += 64;
              v17[5] = v30;
            }
          }
          v31 = *((_DWORD *)v17 + 8);
          if ( v31 < *((_DWORD *)v17 + 7) )
          {
            *((_DWORD *)v17[5] + v31) = *(_DWORD *)(v23 + 92);
            ++*((_DWORD *)v17 + 8);
            if ( !*((_DWORD *)v17 + 12) )
            {
              *((_DWORD *)v17 + 12) = 1;
              *((_DWORD *)v17 + 17) = 0;
            }
            v32 = *((_DWORD *)v17 + 16);
            v33 = (*(_DWORD *)(v23 + 88) & 2) != 0 ? 48 : 40;
            if ( v33 + *((_DWORD *)v17 + 17) >= v32 )
            {
              v34 = (struct _PERF_QUERY *)operator new(v32 + 0x2000);
              v35 = v34;
              if ( !v34 )
              {
                Handle = 14;
                goto LABEL_69;
              }
              v36 = v17[7];
              if ( v36 )
              {
                memcpy_0(v34, v36, *((unsigned int *)v17 + 17));
                operator delete(v17[7]);
              }
              *((_DWORD *)v17 + 16) += 0x2000;
              v17[7] = v35;
            }
            if ( !Handle )
            {
              v37 = *((unsigned int *)v17 + 17);
              v38 = v17[7];
              *(_DWORD *)((char *)v38 + v37 + 16) = 0;
              *(_DWORD *)((char *)v38 + v37 + 20) = v33;
              v39 = *(_OWORD *)(v23 + 24);
              *(_QWORD *)((char *)v38 + v37 + 24) = -1;
              *(_OWORD *)((char *)v38 + v37) = v39;
              if ( (*(_BYTE *)(v23 + 88) & 2) != 0 )
                StringCbCopyW((unsigned __int16 *)((char *)v38 + v37 + 40), v33 - 40LL, L"*");
              *((_DWORD *)v17 + 17) += v33;
            }
          }
        }
      }
    }
LABEL_69:
    v22 = (_QWORD *)v22[3];
  }
  while ( v22 );
  if ( !Handle )
    goto LABEL_71;
LABEL_85:
  PerflibciLocalReleaseMutex(g_hGlobalMutex);
LABEL_86:
  v12 = WPP_GLOBAL_Control;
LABEL_87:
  if ( (*((_BYTE *)v12 + 28) & 8) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_d(v12[2], 13, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids, Handle);
  return Handle;
}

```

## disassembly

```asm
0x180015250  push    rbx
0x180015252  push    rbp
0x180015253  push    rsi
0x180015254  push    rdi
0x180015255  push    r12
0x180015257  push    r13
0x180015259  push    r14
0x18001525b  push    r15
0x18001525d  sub     rsp, 48h
0x180015261  mov     ebx, 57h ; 'W'
0x180015266  xor     esi, esi
0x180015268  mov     edi, ebx
0x18001526a  mov     [rsp+88h+var_58], esi
0x18001526e  mov     r13d, r9d
0x180015271  mov     r12, r8
0x180015274  mov     r14, rdx
0x180015277  mov     ebp, ecx
0x180015279  mov     rcx, cs:WPP_GLOBAL_Control
0x180015280  test    byte ptr [rcx+1Ch], 8
0x180015284  jz      short loc_1800152A9
0x180015286  cmp     byte ptr [rcx+19h], 4
0x18001528a  jb      short loc_1800152A9
0x18001528c  mov     rcx, [rcx+10h]
0x180015290  lea     edx, [rbx-4Bh]
0x180015293  mov     r9d, ebp
0x180015296  lea     r8, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids
0x18001529d  call    WPP_SF_d
0x1800152a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152a9  mov     rax, [rsp+88h+arg_20]
0x1800152b1  test    rax, rax
0x1800152b4  jz      loc_180015763
0x1800152ba  mov     rdx, [rsp+88h+arg_28]
0x1800152c2  test    rdx, rdx
0x1800152c5  jz      loc_180015763
0x1800152cb  mov     r8, [rsp+88h+arg_30]
0x1800152d3  test    r8, r8
0x1800152d6  jz      loc_180015763
0x1800152dc  mov     [rdx], esi
0x1800152de  mov     [r8], esi
0x1800152e1  mov     [rax], rsi
0x1800152e4  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x1800152e9  mov     edi, eax
0x1800152eb  test    eax, eax
0x1800152ed  jnz     loc_18001575C
0x1800152f3  test    r12, r12
0x1800152f6  jz      short loc_180015304
0x1800152f8  test    r13d, r13d
0x1800152fb  jnz     short loc_180015304
0x1800152fd  mov     edi, ebx
0x1800152ff  jmp     loc_18001575C
0x180015304  mov     rdx, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18001530b  mov     r8b, sil
0x18001530e  test    rdx, rdx
0x180015311  jz      loc_18001575C
0x180015317  mov     r9, [rdx+20h]
0x18001531b  test    r9, r9
0x18001531e  jz      short loc_180015347
0x180015320  test    r12, r12
0x180015323  jz      short loc_180015344
0x180015325  mov     ecx, esi
0x180015327  cmp     ecx, r13d
0x18001532a  jnb     short loc_180015347
0x18001532c  mov     eax, ecx
0x18001532e  test    byte ptr [r12+rax*8+4], 1
0x180015334  jnz     short loc_180015340
0x180015336  mov     eax, [r12+rax*8]
0x18001533a  cmp     [r9+5Ch], eax
0x18001533e  jz      short loc_180015344
0x180015340  inc     ecx
0x180015342  jmp     short loc_180015327
0x180015344  mov     r8b, 1
0x180015347  mov     rdx, [rdx+18h]
0x18001534b  test    r8b, r8b
0x18001534e  jz      short loc_18001530E
0x180015350  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180015357  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x18001535c  mov     edi, eax
0x18001535e  test    eax, eax
0x180015360  jnz     loc_18001575C
0x180015366  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x18001536d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180015371  test    rbx, rbx
0x180015374  jz      short loc_1800153AD
0x180015376  cmp     [rbx+18h], ebp
0x180015379  jnz     short loc_18001539B
0x18001537b  mov     r8, [rbx+10h]; lpString2
0x18001537f  mov     r9d, r15d; cchCount2
0x180015382  mov     edx, r15d; cchCount1
0x180015385  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18001538d  mov     rcx, r14; lpString1
0x180015390  call    cs:__imp_CompareStringOrdinal
0x180015396  cmp     eax, 2
0x180015399  jz      short loc_1800153A4
0x18001539b  mov     rbx, [rbx+8]
0x18001539f  test    rbx, rbx
0x1800153a2  jnz     short loc_180015376
0x1800153a4  test    rbx, rbx
0x1800153a7  jnz     loc_18001546C
0x1800153ad  mov     rax, r15
0x1800153b0  inc     rax
0x1800153b3  cmp     [r14+rax*2], si
0x1800153b8  jnz     short loc_1800153B0
0x1800153ba  lea     rsi, ds:2[rax*2]
0x1800153c2  mov     rax, rsi
0x1800153c5  shr     rax, 20h
0x1800153c9  test    eax, eax
0x1800153cb  jnz     loc_18001574B
0x1800153d1  lea     eax, [rsi+68h]
0x1800153d4  cmp     eax, 68h ; 'h'
0x1800153d7  jbe     short loc_1800153E3
0x1800153d9  mov     ecx, eax
0x1800153db  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800153e0  mov     rbx, rax
0x1800153e3  test    rbx, rbx
0x1800153e6  jz      loc_18001574B
0x1800153ec  mov     ecx, 100h
0x1800153f1  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800153f6  mov     [rbx+28h], rax
0x1800153fa  test    rax, rax
0x1800153fd  jnz     short loc_180015418
0x1800153ff  lea     edi, [rax+0Eh]
0x180015402  mov     rcx, [rbx+28h]; Block
0x180015406  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001540b  mov     rcx, rbx; Block
0x18001540e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015413  jmp     loc_180015750
0x180015418  mov     r8, rbx
0x18001541b  xor     ecx, ecx; unsigned __int16 *
0x18001541d  call    PerflibciOpenLocalQueryHandle
0x180015422  mov     edi, eax
0x180015424  test    eax, eax
0x180015426  jnz     short loc_180015402
0x180015428  mov     rax, gs:30h
0x180015431  lea     rcx, [rbx+68h]; unsigned __int16 *
0x180015435  mov     edx, esi; unsigned __int64
0x180015437  mov     r8, r14; unsigned __int16 *
0x18001543a  mov     qword ptr [rax+1728h], 66726550h
0x180015445  mov     rax, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x18001544c  mov     [rbx+8], rax
0x180015450  mov     dword ptr [rbx+1Ch], 40h ; '@'
0x180015457  mov     [rbx+18h], ebp
0x18001545a  mov     [rbx+10h], rcx
0x18001545e  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180015463  xor     esi, esi
0x180015465  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, rbx; PERFI_THREAD_QUERY * g_QueryList
0x18001546c  mov     r15, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180015473  test    r15, r15
0x180015476  jz      loc_18001564B
0x18001547c  mov     r14, [r15+20h]
0x180015480  test    r14, r14
0x180015483  jz      loc_18001562D
0x180015489  test    r12, r12
0x18001548c  jnz     short loc_180015493
0x18001548e  mov     r9b, 1
0x180015491  jmp     short loc_1800154D3
0x180015493  mov     r9b, sil
0x180015496  mov     ecx, esi
0x180015498  test    r13d, r13d
0x18001549b  jz      loc_18001562D
0x1800154a1  mov     r8d, ecx
0x1800154a4  mov     edx, [r12+r8*8+4]
0x1800154a9  test    dl, 1
0x1800154ac  jnz     short loc_1800154C3
0x1800154ae  mov     eax, [r12+r8*8]
0x1800154b2  cmp     [r14+5Ch], eax
0x1800154b6  jnz     short loc_1800154C3
0x1800154b8  or      edx, 1
0x1800154bb  mov     r9b, 1
0x1800154be  mov     [r12+r8*8+4], edx
0x1800154c3  inc     ecx
0x1800154c5  cmp     ecx, r13d
0x1800154c8  jb      short loc_1800154A1
0x1800154ca  test    r9b, r9b
0x1800154cd  jz      loc_18001562D
0x1800154d3  mov     r8d, esi
0x1800154d6  cmp     r8d, [rbx+20h]
0x1800154da  jnb     short loc_1800154F5
0x1800154dc  mov     rcx, [rbx+28h]
0x1800154e0  mov     eax, [r14+5Ch]
0x1800154e4  mov     edx, r8d
0x1800154e7  cmp     [rcx+rdx*4], eax
0x1800154ea  jz      loc_18001562D
0x1800154f0  inc     r8d
0x1800154f3  jmp     short loc_1800154D6
0x1800154f5  test    r9b, r9b
0x1800154f8  jz      loc_18001562D
0x1800154fe  mov     eax, [rbx+1Ch]
0x180015501  cmp     [rbx+20h], eax
0x180015504  jb      short loc_18001555A
0x180015506  cmp     eax, 3FFFFFBFh
0x18001550b  ja      short loc_18001555A
0x18001550d  lea     ecx, [rax+40h]
0x180015510  mov     eax, 4
0x180015515  mul     rcx
0x180015518  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001551f  cmovb   rax, rcx
0x180015523  mov     rcx, rax
0x180015526  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18001552b  mov     rsi, rax
0x18001552e  test    rax, rax
0x180015531  jz      short loc_180015558
0x180015533  mov     r8d, [rbx+20h]
0x180015537  mov     rcx, rax; void *
0x18001553a  mov     rdx, [rbx+28h]; Src
0x18001553e  shl     r8, 2; Size
0x180015542  call    memcpy_0
0x180015547  mov     rcx, [rbx+28h]; Block
0x18001554b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015550  add     dword ptr [rbx+1Ch], 40h ; '@'
0x180015554  mov     [rbx+28h], rsi
0x180015558  xor     esi, esi
0x18001555a  mov     eax, [rbx+20h]
0x18001555d  cmp     eax, [rbx+1Ch]
0x180015560  jnb     loc_18001562D
0x180015566  mov     rcx, [rbx+28h]
0x18001556a  mov     edx, eax
0x18001556c  mov     eax, [r14+5Ch]
0x180015570  mov     [rcx+rdx*4], eax
0x180015573  inc     dword ptr [rbx+20h]
0x180015576  cmp     [rbx+30h], esi
0x180015579  jnz     short loc_180015585
0x18001557b  mov     dword ptr [rbx+30h], 1
0x180015582  mov     [rbx+44h], esi
0x180015585  mov     eax, [r14+58h]
0x180015589  mov     ecx, [rbx+44h]
0x18001558c  and     al, 2
0x18001558e  mov     edx, [rbx+40h]
0x180015591  neg     al
0x180015593  sbb     esi, esi
0x180015595  and     esi, 8
0x180015598  add     esi, 28h ; '('
0x18001559b  add     ecx, esi
0x18001559d  cmp     ecx, edx
0x18001559f  jb      short loc_1800155E2
0x1800155a1  lea     ecx, [rdx+2000h]
0x1800155a7  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800155ac  mov     rbp, rax
0x1800155af  test    rax, rax
0x1800155b2  jnz     short loc_1800155B9
0x1800155b4  lea     edi, [rax+0Eh]
0x1800155b7  jmp     short loc_18001562B
0x1800155b9  mov     rdx, [rbx+38h]; Src
0x1800155bd  test    rdx, rdx
0x1800155c0  jz      short loc_1800155D7
0x1800155c2  mov     r8d, [rbx+44h]; Size
0x1800155c6  mov     rcx, rbp; void *
0x1800155c9  call    memcpy_0
0x1800155ce  mov     rcx, [rbx+38h]; Block
0x1800155d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800155d7  add     dword ptr [rbx+40h], 2000h
0x1800155de  mov     [rbx+38h], rbp
0x1800155e2  test    edi, edi
0x1800155e4  jnz     short loc_18001562B
0x1800155e6  mov     eax, [rbx+44h]
0x1800155e9  mov     rcx, [rbx+38h]
0x1800155ed  mov     [rcx+rax+10h], edi
0x1800155f1  mov     [rcx+rax+14h], esi
0x1800155f5  movups  xmm0, xmmword ptr [r14+18h]
0x1800155fa  mov     qword ptr [rcx+rax+18h], 0FFFFFFFFFFFFFFFFh
0x180015603  movdqu  xmmword ptr [rcx+rax], xmm0
0x180015608  test    byte ptr [r14+58h], 2
0x18001560d  jz      short loc_180015628
0x18001560f  add     rax, 28h ; '('
0x180015613  mov     edx, esi
0x180015615  sub     rdx, 28h ; '('; unsigned __int64
0x180015619  lea     r8, SourceString; "*"
0x180015620  add     rcx, rax; unsigned __int16 *
0x180015623  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180015628  add     [rbx+44h], esi
0x18001562b  xor     esi, esi
0x18001562d  mov     r15, [r15+18h]
0x180015631  test    r15, r15
0x180015634  jnz     loc_18001547C
0x18001563a  test    edi, edi
0x18001563c  jnz     loc_180015750
0x180015642  test    rbx, rbx
0x180015645  jz      loc_180015750
0x18001564b  mov     ebp, 0FFFFFFF8h
0x180015650  cmp     [rbx+30h], esi
0x180015653  jz      loc_180015702
0x180015659  mov     r8d, [rbx+44h]
0x18001565d  mov     r9d, 1
0x180015663  mov     rdx, [rbx+38h]
0x180015667  mov     rcx, [rbx]; struct _PERF_QUERY *
0x18001566a  call    PerflibciLocalValidateCounters
0x18001566f  mov     edi, eax
0x180015671  test    eax, eax
0x180015673  jnz     loc_18001579A
0x180015679  mov     r8d, [rbx+40h]
0x18001567d  lea     r9, [rsp+88h+var_58]
0x180015682  mov     rdx, [rbx+38h]
0x180015686  mov     rcx, [rbx]
0x180015689  call    PerflibciLocalQueryCounterInfo
0x18001568e  mov     edi, eax
0x180015690  cmp     eax, 8
0x180015693  jnz     short loc_1800156E6
0x180015695  mov     eax, [rsp+88h+var_58]
0x180015699  mov     rsi, [rbx+38h]
0x18001569d  add     eax, 7
0x1800156a0  and     eax, ebp
  ... truncated ...
```
