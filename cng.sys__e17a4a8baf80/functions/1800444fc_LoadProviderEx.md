# LoadProviderEx

- ea: `0x1800444fc`
- end: `0x18004487f`
- name: `LoadProviderEx`
- size: `899`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004eaa0`
- `0x180066d00`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x1800444fc`
- `0x180044888`
- `0x1800448d8`
- `0x18004508c`
- `0x180045204`
- `0x180073a54`
- `0x180073b18`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18004454c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004454c`
- `ntoskrnl!KeSetEvent` at `0x18004467c`
- `ntoskrnl!KeSetEvent` at `0x18004467c`

## string_xrefs

- `0x18004463a`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044741`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044763`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18004483b`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044861`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadProviderEx(int *a1, __int64 a2, unsigned int a3, __int64 *a4, void *a5)
{
  __int64 v8; // rax
  int v9; // r8d
  __int64 v10; // rdi
  int v11; // r15d
  __m128i v12; // xmm0
  unsigned int Interface; // esi
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // r8d
  unsigned int v19; // eax
  int v20; // r8d
  __int64 v21; // rax
  unsigned int Image; // eax
  int v23; // edx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // [rsp+40h] [rbp-30h] BYREF
  void *Src; // [rsp+48h] [rbp-28h] BYREF
  __m128i v35; // [rsp+50h] [rbp-20h] BYREF
  __m128i v36; // [rsp+60h] [rbp-10h] BYREF

  v35 = 0;
  Src = 0;
  if ( g_fLoaderInitialized )
  {
    KeWaitForSingleObject(&g_evtLoaderLock, Executive, 0, 0, 0);
    v8 = FindInLoadedProviderList(a1);
    v33 = v8;
    v10 = v8;
    v11 = 1;
    if ( v8 )
    {
      v12 = *(__m128i *)(v8 + 8);
      v35 = v12;
    }
    else
    {
      Image = LoadImage((__int64)a1, (__int64)&v35);
      Interface = Image;
      if ( Image )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v23 = *((_DWORD *)WPP_GLOBAL_Control + 11);
          if ( (v23 & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v23,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              (unsigned int)"sResult",
              Image,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              169);
        }
        goto LABEL_20;
      }
      v12 = _mm_load_si128(&v35);
    }
    v36 = v12;
    Interface = LoadInterface((__int64)&v36, a1, v9, (_WORD **)&Src);
    if ( Interface )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          (unsigned int)"sResult",
          Interface,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          186);
      goto LABEL_20;
    }
    if ( a3 )
    {
LABEL_11:
      memmove(a5, Src, a3);
      if ( v10 )
      {
        v16 = *(_DWORD *)(v10 + 24);
        v17 = v16 + 1;
        if ( v16 + 1 >= v16 )
        {
          *(_DWORD *)(v10 + 24) = v17;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0 )
          {
            WPP_SF_qqSD(*((_QWORD *)WPP_GLOBAL_Control + 3), 27, v17, (_DWORD)a1, v10, *(_QWORD *)v10, v17);
          }
LABEL_16:
          *a4 = v10;
LABEL_22:
          KeSetEvent(&g_evtLoaderLock, 0, 0);
          return Interface;
        }
        Interface = -1073741670;
        v31 = 2517;
        v32 = 3221225626LL;
        goto LABEL_50;
      }
      v36 = v35;
      v19 = NewLoadedProviderHandle(a1, &v36, &v33);
      Interface = v19;
      if ( !v19 )
      {
        v10 = v33;
        v21 = g_pLoadedProviderList;
        g_pLoadedProviderList = v33;
        *(_QWORD *)(v33 + 32) = v21;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0 )
          WPP_SF_qqSD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            Interface + 28,
            v20,
            (_DWORD)a1,
            v10,
            *(_QWORD *)v10,
            *(_DWORD *)(v10 + 24));
        goto LABEL_16;
      }
      DebugTraceError(v19, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 2539);
      v10 = v33;
LABEL_20:
      if ( v10 )
        goto LABEL_21;
      goto LABEL_34;
    }
    v14 = *a1;
    if ( (unsigned int)*a1 <= 6 )
    {
      if ( v14 == 6 )
      {
        a3 = 48;
        goto LABEL_10;
      }
      v15 = v14 - 1;
      if ( !v15 )
        goto LABEL_9;
      v24 = v15 - 1;
      if ( !v24 )
        goto LABEL_9;
      v25 = v24 - 1;
      if ( !v25 )
      {
        a3 = 112;
        goto LABEL_10;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        a3 = 104;
        goto LABEL_10;
      }
      if ( v26 == 1 )
        goto LABEL_9;
      goto LABEL_54;
    }
    v27 = v14 - 7;
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( !v28 )
      {
LABEL_9:
        a3 = 96;
        goto LABEL_10;
      }
      v29 = v28 - 65529;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( v30 )
        {
          if ( v30 == 2 )
          {
            a3 = 40;
            goto LABEL_10;
          }
LABEL_54:
          a3 = 0;
          goto LABEL_10;
        }
        a3 = 392;
      }
      else
      {
        a3 = 256;
      }
    }
    else
    {
      a3 = 88;
    }
LABEL_10:
    if ( !a3 )
    {
      Interface = -1073741811;
      v31 = 2500;
      v32 = 3221225485LL;
LABEL_50:
      DebugTraceError(v32, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v31);
      goto LABEL_20;
    }
    goto LABEL_11;
  }
  v11 = 0;
  Interface = -1073741595;
  DebugTraceError(3221225701LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 2447);
LABEL_34:
  if ( v35.m128i_i64[0] )
  {
    v36 = v35;
    FreeImage(&v36);
  }
LABEL_21:
  *a4 = 0;
  if ( v11 )
    goto LABEL_22;
  return Interface;
}

```

## disassembly

```asm
0x1800444fc  push    rbp
0x1800444fe  push    rbx
0x1800444ff  push    rsi
0x180044500  push    rdi
0x180044501  push    r12
0x180044503  push    r14
0x180044505  push    r15
0x180044507  mov     rbp, rsp
0x18004450a  sub     rsp, 70h
0x18004450e  cmp     cs:g_fLoaderInitialized, 0
0x180044515  xorps   xmm0, xmm0
0x180044518  movdqa  [rbp+var_20], xmm0
0x18004451d  mov     r12, r9
0x180044520  mov     ebx, r8d
0x180044523  mov     [rbp+Src], 0
0x18004452b  mov     r14, rcx
0x18004452e  jz      loc_180044760
0x180044534  xor     r9d, r9d; Alertable
0x180044537  mov     [rsp+70h+Timeout], 0; Timeout
0x180044540  xor     r8d, r8d; WaitMode
0x180044543  lea     rcx, g_evtLoaderLock; Object
0x18004454a  xor     edx, edx; WaitReason
0x18004454c  call    cs:__imp_KeWaitForSingleObject
0x180044553  nop     dword ptr [rax+rax+00h]
0x180044558  mov     rcx, r14
0x18004455b  call    _FindInLoadedProviderList
0x180044560  mov     [rbp+var_30], rax
0x180044564  mov     rdi, rax
0x180044567  mov     r15d, 1
0x18004456d  test    rax, rax
0x180044570  jz      loc_180044704
0x180044576  movups  xmm0, xmmword ptr [rax+8]
0x18004457a  movdqa  [rbp+var_20], xmm0
0x18004457f  lea     r9, [rbp+Src]
0x180044583  movdqa  [rbp+var_10], xmm0
0x180044588  mov     rdx, r14
0x18004458b  lea     rcx, [rbp+var_10]
0x18004458f  call    _LoadInterface
0x180044594  mov     esi, eax
0x180044596  test    eax, eax
0x180044598  jnz     short loc_180044617
0x18004459a  test    ebx, ebx
0x18004459c  jnz     short loc_1800445C6
0x18004459e  mov     eax, [r14]
0x1800445a1  cmp     eax, 6
0x1800445a4  ja      loc_1800447DB
0x1800445aa  jz      loc_1800447D1
0x1800445b0  sub     eax, r15d
0x1800445b3  jnz     loc_1800447A8
0x1800445b9  mov     ebx, 60h ; '`'
0x1800445be  test    ebx, ebx
0x1800445c0  jz      loc_180044812
0x1800445c6  mov     rdx, [rbp+Src]; Src
0x1800445ca  mov     rcx, [rbp+arg_20]; void *
0x1800445ce  mov     r8d, ebx; Size
0x1800445d1  call    memmove
0x1800445d6  test    rdi, rdi
0x1800445d9  jz      loc_18004469A
0x1800445df  mov     eax, [rdi+18h]
0x1800445e2  lea     r8d, [rax+1]
0x1800445e6  cmp     r8d, eax
0x1800445e9  jb      loc_180044824
0x1800445ef  mov     [rdi+18h], r8d
0x1800445f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800445fa  lea     rdx, WPP_GLOBAL_Control
0x180044601  cmp     rcx, rdx
0x180044604  jz      short loc_180044611
0x180044606  mov     eax, [rcx+2Ch]
0x180044609  test    al, 20h
0x18004460b  jnz     loc_18004484C
0x180044611  mov     [r12], rdi
0x180044615  jmp     short loc_180044670
0x180044617  mov     rcx, cs:WPP_GLOBAL_Control
0x18004461e  lea     rdx, WPP_GLOBAL_Control
0x180044625  cmp     rcx, rdx
0x180044628  jz      short loc_18004465A
0x18004462a  mov     eax, [rcx+2Ch]
0x18004462d  test    r15b, al
0x180044630  jz      short loc_18004465A
0x180044632  mov     [rsp+70h+var_40], 9BAh
0x18004463a  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044641  mov     [rsp+70h+var_48], r8
0x180044646  mov     dword ptr [rsp+70h+Timeout], esi
0x18004464a  mov     rcx, [rcx+18h]
0x18004464e  lea     r9, aSresult; "sResult"
0x180044655  call    WPP_SF_sDsd
0x18004465a  test    rdi, rdi
0x18004465d  jz      loc_180044786
0x180044663  mov     qword ptr [r12], 0
0x18004466b  test    r15d, r15d
0x18004466e  jz      short loc_180044688
0x180044670  xor     r8d, r8d; Wait
0x180044673  lea     rcx, g_evtLoaderLock; Event
0x18004467a  xor     edx, edx; Increment
0x18004467c  call    cs:__imp_KeSetEvent
0x180044683  nop     dword ptr [rax+rax+00h]
0x180044688  mov     eax, esi
0x18004468a  add     rsp, 70h
0x18004468e  pop     r15
0x180044690  pop     r14
0x180044692  pop     r12
0x180044694  pop     rdi
0x180044695  pop     rsi
0x180044696  pop     rbx
0x180044697  pop     rbp
0x180044698  retn
0x18004469a  movaps  xmm0, [rbp+var_20]
0x18004469e  lea     r8, [rbp+var_30]
0x1800446a2  lea     rdx, [rbp+var_10]
0x1800446a6  movdqa  [rbp+var_10], xmm0
0x1800446ab  mov     rcx, r14
0x1800446ae  call    _NewLoadedProviderHandle
0x1800446b3  mov     esi, eax
0x1800446b5  test    eax, eax
0x1800446b7  jnz     loc_18004485B
0x1800446bd  mov     rdi, [rbp+var_30]
0x1800446c1  mov     rax, cs:g_pLoadedProviderList
0x1800446c8  mov     cs:g_pLoadedProviderList, rdi
0x1800446cf  mov     [rdi+20h], rax
0x1800446d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446da  lea     rdx, WPP_GLOBAL_Control
0x1800446e1  cmp     rcx, rdx
0x1800446e4  jz      loc_180044611
0x1800446ea  mov     eax, [rcx+2Ch]
0x1800446ed  test    al, 20h
0x1800446ef  jz      loc_180044611
0x1800446f5  mov     eax, [rdi+18h]
0x1800446f8  lea     edx, [rsi+1Ch]
0x1800446fb  mov     [rsp+70h+var_40], eax
0x1800446ff  jmp     loc_1800A8229
0x180044704  lea     rdx, [rbp+var_20]
0x180044708  mov     rcx, r14
0x18004470b  call    _LoadImage
0x180044710  mov     esi, eax
0x180044712  test    eax, eax
0x180044714  jz      short loc_180044756
0x180044716  mov     rcx, cs:WPP_GLOBAL_Control
0x18004471d  lea     rdx, WPP_GLOBAL_Control
0x180044724  cmp     rcx, rdx
0x180044727  jz      loc_18004465A
0x18004472d  mov     edx, [rcx+2Ch]
0x180044730  test    r15b, dl
0x180044733  jz      loc_18004465A
0x180044739  mov     [rsp+70h+var_40], 9A9h
0x180044741  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044748  mov     [rsp+70h+var_48], r8
0x18004474d  mov     dword ptr [rsp+70h+Timeout], eax
0x180044751  jmp     loc_18004464A
0x180044756  movdqa  xmm0, [rbp+var_20]
0x18004475b  jmp     loc_18004457F
0x180044760  xor     r15d, r15d
0x180044763  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004476a  mov     r9d, 98Fh
0x180044770  lea     rdx, aSresult; "sResult"
0x180044777  mov     ecx, 0C00000E5h
0x18004477c  mov     esi, 0C00000E5h
0x180044781  call    DebugTraceError
0x180044786  cmp     qword ptr [rbp+var_20], 0
0x18004478b  jz      loc_180044663
0x180044791  movaps  xmm0, [rbp+var_20]
0x180044795  lea     rcx, [rbp+var_10]
0x180044799  movdqa  [rbp+var_10], xmm0
0x18004479e  call    _FreeImage
0x1800447a3  jmp     loc_180044663
0x1800447a8  sub     eax, r15d
0x1800447ab  jz      loc_1800445B9
0x1800447b1  sub     eax, r15d
0x1800447b4  jz      loc_1800A81FA
0x1800447ba  sub     eax, r15d
0x1800447bd  jz      loc_1800A81F0
0x1800447c3  cmp     eax, r15d
0x1800447c6  jnz     loc_1800A8204
0x1800447cc  jmp     loc_1800445B9
0x1800447d1  mov     ebx, 30h ; '0'
0x1800447d6  jmp     loc_1800445BE
0x1800447db  sub     eax, 7
0x1800447de  jz      loc_1800A821F
0x1800447e4  sub     eax, r15d
0x1800447e7  jz      loc_1800445B9
0x1800447ed  sub     eax, 0FFF9h
0x1800447f2  jz      loc_1800A8215
0x1800447f8  sub     eax, r15d
0x1800447fb  jz      loc_1800A820B
0x180044801  cmp     eax, 2
0x180044804  jnz     loc_1800A8204
0x18004480a  lea     ebx, [rax+26h]
0x18004480d  jmp     loc_1800445BE
0x180044812  mov     esi, 0C000000Dh
0x180044817  mov     r9d, 9C4h
0x18004481d  mov     ecx, 0C000000Dh
0x180044822  jmp     short loc_180044834
0x180044824  mov     esi, 0C000009Ah
0x180044829  mov     r9d, 9D5h
0x18004482f  mov     ecx, 0C000009Ah
0x180044834  lea     rdx, aSresult; "sResult"
0x18004483b  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044842  call    DebugTraceError
0x180044847  jmp     loc_18004465A
0x18004484c  mov     edx, 1Bh
0x180044851  mov     [rsp+70h+var_40], r8d
0x180044856  jmp     loc_1800A8229
0x18004485b  mov     r9d, 9EBh
0x180044861  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044868  lea     rdx, aSresult; "sResult"
0x18004486f  mov     ecx, eax
0x180044871  call    DebugTraceError
0x180044876  mov     rdi, [rbp+var_30]
0x18004487a  jmp     loc_18004465A
0x1800a81f0  mov     ebx, 68h ; 'h'
0x1800a81f5  jmp     loc_1800445BE
0x1800a81fa  mov     ebx, 70h ; 'p'
0x1800a81ff  jmp     loc_1800445BE
0x1800a8204  xor     ebx, ebx
0x1800a8206  jmp     loc_1800445BE
0x1800a820b  mov     ebx, 188h
0x1800a8210  jmp     loc_1800445BE
0x1800a8215  mov     ebx, 100h
0x1800a821a  jmp     loc_1800445BE
0x1800a821f  mov     ebx, 58h ; 'X'
0x1800a8224  jmp     loc_1800445BE
0x1800a8229  mov     rax, [rdi]
0x1800a822c  mov     r9, r14
0x1800a822f  mov     rcx, [rcx+18h]
0x1800a8233  mov     [rsp+70h+var_48], rax
0x1800a8238  mov     [rsp+70h+Timeout], rdi
0x1800a823d  call    WPP_SF_qqSD
0x1800a8242  nop
0x1800a8243  jmp     loc_180044611
```
