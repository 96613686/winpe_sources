# LoadProviderEx

- ea: `0x18003a46c`
- end: `0x18003a7ef`
- name: `LoadProviderEx`
- size: `899`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800449b0`
- `0x18005cb30`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003a46c`
- `0x18003a7f8`
- `0x18003a848`
- `0x18003affc`
- `0x18003b174`
- `0x1800698b4`
- `0x180069978`
- `0x18009da40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18003a4bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003a4bc`
- `ntoskrnl!KeSetEvent` at `0x18003a5ec`
- `ntoskrnl!KeSetEvent` at `0x18003a5ec`

## string_xrefs

- `0x18003a5aa`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003a6b1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003a6d3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003a7ab`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003a7d1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
      v19 = NewLoadedProviderHandle((__int64)a1, &v36, &v33);
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
0x18003a46c  push    rbp
0x18003a46e  push    rbx
0x18003a46f  push    rsi
0x18003a470  push    rdi
0x18003a471  push    r12
0x18003a473  push    r14
0x18003a475  push    r15
0x18003a477  mov     rbp, rsp
0x18003a47a  sub     rsp, 70h
0x18003a47e  cmp     cs:g_fLoaderInitialized, 0
0x18003a485  xorps   xmm0, xmm0
0x18003a488  movdqa  [rbp+var_20], xmm0
0x18003a48d  mov     r12, r9
0x18003a490  mov     ebx, r8d
0x18003a493  mov     [rbp+Src], 0
0x18003a49b  mov     r14, rcx
0x18003a49e  jz      loc_18003A6D0
0x18003a4a4  xor     r9d, r9d; Alertable
0x18003a4a7  mov     [rsp+70h+Timeout], 0; Timeout
0x18003a4b0  xor     r8d, r8d; WaitMode
0x18003a4b3  lea     rcx, g_evtLoaderLock; Object
0x18003a4ba  xor     edx, edx; WaitReason
0x18003a4bc  call    cs:__imp_KeWaitForSingleObject
0x18003a4c3  nop     dword ptr [rax+rax+00h]
0x18003a4c8  mov     rcx, r14
0x18003a4cb  call    _FindInLoadedProviderList
0x18003a4d0  mov     [rbp+var_30], rax
0x18003a4d4  mov     rdi, rax
0x18003a4d7  mov     r15d, 1
0x18003a4dd  test    rax, rax
0x18003a4e0  jz      loc_18003A674
0x18003a4e6  movups  xmm0, xmmword ptr [rax+8]
0x18003a4ea  movdqa  [rbp+var_20], xmm0
0x18003a4ef  lea     r9, [rbp+Src]
0x18003a4f3  movdqa  [rbp+var_10], xmm0
0x18003a4f8  mov     rdx, r14
0x18003a4fb  lea     rcx, [rbp+var_10]
0x18003a4ff  call    _LoadInterface
0x18003a504  mov     esi, eax
0x18003a506  test    eax, eax
0x18003a508  jnz     short loc_18003A587
0x18003a50a  test    ebx, ebx
0x18003a50c  jnz     short loc_18003A536
0x18003a50e  mov     eax, [r14]
0x18003a511  cmp     eax, 6
0x18003a514  ja      loc_18003A74B
0x18003a51a  jz      loc_18003A741
0x18003a520  sub     eax, r15d
0x18003a523  jnz     loc_18003A718
0x18003a529  mov     ebx, 60h ; '`'
0x18003a52e  test    ebx, ebx
0x18003a530  jz      loc_18003A782
0x18003a536  mov     rdx, [rbp+Src]; Src
0x18003a53a  mov     rcx, [rbp+arg_20]; void *
0x18003a53e  mov     r8d, ebx; Size
0x18003a541  call    memmove
0x18003a546  test    rdi, rdi
0x18003a549  jz      loc_18003A60A
0x18003a54f  mov     eax, [rdi+18h]
0x18003a552  lea     r8d, [rax+1]
0x18003a556  cmp     r8d, eax
0x18003a559  jb      loc_18003A794
0x18003a55f  mov     [rdi+18h], r8d
0x18003a563  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a56a  lea     rdx, WPP_GLOBAL_Control
0x18003a571  cmp     rcx, rdx
0x18003a574  jz      short loc_18003A581
0x18003a576  mov     eax, [rcx+2Ch]
0x18003a579  test    al, 20h
0x18003a57b  jnz     loc_18003A7BC
0x18003a581  mov     [r12], rdi
0x18003a585  jmp     short loc_18003A5E0
0x18003a587  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a58e  lea     rdx, WPP_GLOBAL_Control
0x18003a595  cmp     rcx, rdx
0x18003a598  jz      short loc_18003A5CA
0x18003a59a  mov     eax, [rcx+2Ch]
0x18003a59d  test    r15b, al
0x18003a5a0  jz      short loc_18003A5CA
0x18003a5a2  mov     [rsp+70h+var_40], 9BAh
0x18003a5aa  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a5b1  mov     [rsp+70h+var_48], r8
0x18003a5b6  mov     dword ptr [rsp+70h+Timeout], esi
0x18003a5ba  mov     rcx, [rcx+18h]
0x18003a5be  lea     r9, aSresult; "sResult"
0x18003a5c5  call    WPP_SF_sDsd
0x18003a5ca  test    rdi, rdi
0x18003a5cd  jz      loc_18003A6F6
0x18003a5d3  mov     qword ptr [r12], 0
0x18003a5db  test    r15d, r15d
0x18003a5de  jz      short loc_18003A5F8
0x18003a5e0  xor     r8d, r8d; Wait
0x18003a5e3  lea     rcx, g_evtLoaderLock; Event
0x18003a5ea  xor     edx, edx; Increment
0x18003a5ec  call    cs:__imp_KeSetEvent
0x18003a5f3  nop     dword ptr [rax+rax+00h]
0x18003a5f8  mov     eax, esi
0x18003a5fa  add     rsp, 70h
0x18003a5fe  pop     r15
0x18003a600  pop     r14
0x18003a602  pop     r12
0x18003a604  pop     rdi
0x18003a605  pop     rsi
0x18003a606  pop     rbx
0x18003a607  pop     rbp
0x18003a608  retn
0x18003a60a  movaps  xmm0, [rbp+var_20]
0x18003a60e  lea     r8, [rbp+var_30]
0x18003a612  lea     rdx, [rbp+var_10]
0x18003a616  movdqa  [rbp+var_10], xmm0
0x18003a61b  mov     rcx, r14
0x18003a61e  call    _NewLoadedProviderHandle
0x18003a623  mov     esi, eax
0x18003a625  test    eax, eax
0x18003a627  jnz     loc_18003A7CB
0x18003a62d  mov     rdi, [rbp+var_30]
0x18003a631  mov     rax, cs:g_pLoadedProviderList
0x18003a638  mov     cs:g_pLoadedProviderList, rdi
0x18003a63f  mov     [rdi+20h], rax
0x18003a643  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a64a  lea     rdx, WPP_GLOBAL_Control
0x18003a651  cmp     rcx, rdx
0x18003a654  jz      loc_18003A581
0x18003a65a  mov     eax, [rcx+2Ch]
0x18003a65d  test    al, 20h
0x18003a65f  jz      loc_18003A581
0x18003a665  mov     eax, [rdi+18h]
0x18003a668  lea     edx, [rsi+1Ch]
0x18003a66b  mov     [rsp+70h+var_40], eax
0x18003a66f  jmp     loc_1800A148B
0x18003a674  lea     rdx, [rbp+var_20]
0x18003a678  mov     rcx, r14
0x18003a67b  call    _LoadImage
0x18003a680  mov     esi, eax
0x18003a682  test    eax, eax
0x18003a684  jz      short loc_18003A6C6
0x18003a686  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a68d  lea     rdx, WPP_GLOBAL_Control
0x18003a694  cmp     rcx, rdx
0x18003a697  jz      loc_18003A5CA
0x18003a69d  mov     edx, [rcx+2Ch]
0x18003a6a0  test    r15b, dl
0x18003a6a3  jz      loc_18003A5CA
0x18003a6a9  mov     [rsp+70h+var_40], 9A9h
0x18003a6b1  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a6b8  mov     [rsp+70h+var_48], r8
0x18003a6bd  mov     dword ptr [rsp+70h+Timeout], eax
0x18003a6c1  jmp     loc_18003A5BA
0x18003a6c6  movdqa  xmm0, [rbp+var_20]
0x18003a6cb  jmp     loc_18003A4EF
0x18003a6d0  xor     r15d, r15d
0x18003a6d3  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a6da  mov     r9d, 98Fh
0x18003a6e0  lea     rdx, aSresult; "sResult"
0x18003a6e7  mov     ecx, 0C00000E5h
0x18003a6ec  mov     esi, 0C00000E5h
0x18003a6f1  call    DebugTraceError
0x18003a6f6  cmp     qword ptr [rbp+var_20], 0
0x18003a6fb  jz      loc_18003A5D3
0x18003a701  movaps  xmm0, [rbp+var_20]
0x18003a705  lea     rcx, [rbp+var_10]
0x18003a709  movdqa  [rbp+var_10], xmm0
0x18003a70e  call    _FreeImage
0x18003a713  jmp     loc_18003A5D3
0x18003a718  sub     eax, r15d
0x18003a71b  jz      loc_18003A529
0x18003a721  sub     eax, r15d
0x18003a724  jz      loc_1800A145C
0x18003a72a  sub     eax, r15d
0x18003a72d  jz      loc_1800A1452
0x18003a733  cmp     eax, r15d
0x18003a736  jnz     loc_1800A1466
0x18003a73c  jmp     loc_18003A529
0x18003a741  mov     ebx, 30h ; '0'
0x18003a746  jmp     loc_18003A52E
0x18003a74b  sub     eax, 7
0x18003a74e  jz      loc_1800A1481
0x18003a754  sub     eax, r15d
0x18003a757  jz      loc_18003A529
0x18003a75d  sub     eax, 0FFF9h
0x18003a762  jz      loc_1800A1477
0x18003a768  sub     eax, r15d
0x18003a76b  jz      loc_1800A146D
0x18003a771  cmp     eax, 2
0x18003a774  jnz     loc_1800A1466
0x18003a77a  lea     ebx, [rax+26h]
0x18003a77d  jmp     loc_18003A52E
0x18003a782  mov     esi, 0C000000Dh
0x18003a787  mov     r9d, 9C4h
0x18003a78d  mov     ecx, 0C000000Dh
0x18003a792  jmp     short loc_18003A7A4
0x18003a794  mov     esi, 0C000009Ah
0x18003a799  mov     r9d, 9D5h
0x18003a79f  mov     ecx, 0C000009Ah
0x18003a7a4  lea     rdx, aSresult; "sResult"
0x18003a7ab  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a7b2  call    DebugTraceError
0x18003a7b7  jmp     loc_18003A5CA
0x18003a7bc  mov     edx, 1Bh
0x18003a7c1  mov     [rsp+70h+var_40], r8d
0x18003a7c6  jmp     loc_1800A148B
0x18003a7cb  mov     r9d, 9EBh
0x18003a7d1  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a7d8  lea     rdx, aSresult; "sResult"
0x18003a7df  mov     ecx, eax
0x18003a7e1  call    DebugTraceError
0x18003a7e6  mov     rdi, [rbp+var_30]
0x18003a7ea  jmp     loc_18003A5CA
0x1800a1452  mov     ebx, 68h ; 'h'
0x1800a1457  jmp     loc_18003A52E
0x1800a145c  mov     ebx, 70h ; 'p'
0x1800a1461  jmp     loc_18003A52E
0x1800a1466  xor     ebx, ebx
0x1800a1468  jmp     loc_18003A52E
0x1800a146d  mov     ebx, 188h
0x1800a1472  jmp     loc_18003A52E
0x1800a1477  mov     ebx, 100h
0x1800a147c  jmp     loc_18003A52E
0x1800a1481  mov     ebx, 58h ; 'X'
0x1800a1486  jmp     loc_18003A52E
0x1800a148b  mov     rax, [rdi]
0x1800a148e  mov     r9, r14
0x1800a1491  mov     rcx, [rcx+18h]
0x1800a1495  mov     [rsp+70h+var_48], rax
0x1800a149a  mov     [rsp+70h+Timeout], rdi
0x1800a149f  call    WPP_SF_qqSD
0x1800a14a4  nop
0x1800a14a5  jmp     loc_18003A581
```
