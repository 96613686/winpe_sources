# LoadProviderEx

- ea: `0x18003af6c`
- end: `0x18003b2ef`
- name: `LoadProviderEx`
- size: `899`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180045440`
- `0x18005d420`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003af6c`
- `0x18003b2f8`
- `0x18003b348`
- `0x18003bafc`
- `0x18003bc74`
- `0x18006a2b4`
- `0x18006a378`
- `0x18009f780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18003afbc`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003afbc`
- `ntoskrnl!KeSetEvent` at `0x18003b0ec`
- `ntoskrnl!KeSetEvent` at `0x18003b0ec`

## string_xrefs

- `0x18003b0aa`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b1b1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b1d3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b2ab`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b2d1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18003af6c  push    rbp
0x18003af6e  push    rbx
0x18003af6f  push    rsi
0x18003af70  push    rdi
0x18003af71  push    r12
0x18003af73  push    r14
0x18003af75  push    r15
0x18003af77  mov     rbp, rsp
0x18003af7a  sub     rsp, 70h
0x18003af7e  cmp     cs:g_fLoaderInitialized, 0
0x18003af85  xorps   xmm0, xmm0
0x18003af88  movdqa  [rbp+var_20], xmm0
0x18003af8d  mov     r12, r9
0x18003af90  mov     ebx, r8d
0x18003af93  mov     [rbp+Src], 0
0x18003af9b  mov     r14, rcx
0x18003af9e  jz      loc_18003B1D0
0x18003afa4  xor     r9d, r9d; Alertable
0x18003afa7  mov     [rsp+70h+Timeout], 0; Timeout
0x18003afb0  xor     r8d, r8d; WaitMode
0x18003afb3  lea     rcx, g_evtLoaderLock; Object
0x18003afba  xor     edx, edx; WaitReason
0x18003afbc  call    cs:__imp_KeWaitForSingleObject
0x18003afc3  nop     dword ptr [rax+rax+00h]
0x18003afc8  mov     rcx, r14
0x18003afcb  call    _FindInLoadedProviderList
0x18003afd0  mov     [rbp+var_30], rax
0x18003afd4  mov     rdi, rax
0x18003afd7  mov     r15d, 1
0x18003afdd  test    rax, rax
0x18003afe0  jz      loc_18003B174
0x18003afe6  movups  xmm0, xmmword ptr [rax+8]
0x18003afea  movdqa  [rbp+var_20], xmm0
0x18003afef  lea     r9, [rbp+Src]
0x18003aff3  movdqa  [rbp+var_10], xmm0
0x18003aff8  mov     rdx, r14
0x18003affb  lea     rcx, [rbp+var_10]
0x18003afff  call    _LoadInterface
0x18003b004  mov     esi, eax
0x18003b006  test    eax, eax
0x18003b008  jnz     short loc_18003B087
0x18003b00a  test    ebx, ebx
0x18003b00c  jnz     short loc_18003B036
0x18003b00e  mov     eax, [r14]
0x18003b011  cmp     eax, 6
0x18003b014  ja      loc_18003B24B
0x18003b01a  jz      loc_18003B241
0x18003b020  sub     eax, r15d
0x18003b023  jnz     loc_18003B218
0x18003b029  mov     ebx, 60h ; '`'
0x18003b02e  test    ebx, ebx
0x18003b030  jz      loc_18003B282
0x18003b036  mov     rdx, [rbp+Src]; Src
0x18003b03a  mov     rcx, [rbp+arg_20]; void *
0x18003b03e  mov     r8d, ebx; Size
0x18003b041  call    memmove
0x18003b046  test    rdi, rdi
0x18003b049  jz      loc_18003B10A
0x18003b04f  mov     eax, [rdi+18h]
0x18003b052  lea     r8d, [rax+1]
0x18003b056  cmp     r8d, eax
0x18003b059  jb      loc_18003B294
0x18003b05f  mov     [rdi+18h], r8d
0x18003b063  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b06a  lea     rdx, WPP_GLOBAL_Control
0x18003b071  cmp     rcx, rdx
0x18003b074  jz      short loc_18003B081
0x18003b076  mov     eax, [rcx+2Ch]
0x18003b079  test    al, 20h
0x18003b07b  jnz     loc_18003B2BC
0x18003b081  mov     [r12], rdi
0x18003b085  jmp     short loc_18003B0E0
0x18003b087  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b08e  lea     rdx, WPP_GLOBAL_Control
0x18003b095  cmp     rcx, rdx
0x18003b098  jz      short loc_18003B0CA
0x18003b09a  mov     eax, [rcx+2Ch]
0x18003b09d  test    r15b, al
0x18003b0a0  jz      short loc_18003B0CA
0x18003b0a2  mov     [rsp+70h+var_40], 9BAh
0x18003b0aa  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b0b1  mov     [rsp+70h+var_48], r8
0x18003b0b6  mov     dword ptr [rsp+70h+Timeout], esi
0x18003b0ba  mov     rcx, [rcx+18h]
0x18003b0be  lea     r9, aSresult; "sResult"
0x18003b0c5  call    WPP_SF_sDsd
0x18003b0ca  test    rdi, rdi
0x18003b0cd  jz      loc_18003B1F6
0x18003b0d3  mov     qword ptr [r12], 0
0x18003b0db  test    r15d, r15d
0x18003b0de  jz      short loc_18003B0F8
0x18003b0e0  xor     r8d, r8d; Wait
0x18003b0e3  lea     rcx, g_evtLoaderLock; Event
0x18003b0ea  xor     edx, edx; Increment
0x18003b0ec  call    cs:__imp_KeSetEvent
0x18003b0f3  nop     dword ptr [rax+rax+00h]
0x18003b0f8  mov     eax, esi
0x18003b0fa  add     rsp, 70h
0x18003b0fe  pop     r15
0x18003b100  pop     r14
0x18003b102  pop     r12
0x18003b104  pop     rdi
0x18003b105  pop     rsi
0x18003b106  pop     rbx
0x18003b107  pop     rbp
0x18003b108  retn
0x18003b10a  movaps  xmm0, [rbp+var_20]
0x18003b10e  lea     r8, [rbp+var_30]
0x18003b112  lea     rdx, [rbp+var_10]
0x18003b116  movdqa  [rbp+var_10], xmm0
0x18003b11b  mov     rcx, r14
0x18003b11e  call    _NewLoadedProviderHandle
0x18003b123  mov     esi, eax
0x18003b125  test    eax, eax
0x18003b127  jnz     loc_18003B2CB
0x18003b12d  mov     rdi, [rbp+var_30]
0x18003b131  mov     rax, cs:g_pLoadedProviderList
0x18003b138  mov     cs:g_pLoadedProviderList, rdi
0x18003b13f  mov     [rdi+20h], rax
0x18003b143  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b14a  lea     rdx, WPP_GLOBAL_Control
0x18003b151  cmp     rcx, rdx
0x18003b154  jz      loc_18003B081
0x18003b15a  mov     eax, [rcx+2Ch]
0x18003b15d  test    al, 20h
0x18003b15f  jz      loc_18003B081
0x18003b165  mov     eax, [rdi+18h]
0x18003b168  lea     edx, [rsi+1Ch]
0x18003b16b  mov     [rsp+70h+var_40], eax
0x18003b16f  jmp     loc_1800A32BB
0x18003b174  lea     rdx, [rbp+var_20]
0x18003b178  mov     rcx, r14
0x18003b17b  call    _LoadImage
0x18003b180  mov     esi, eax
0x18003b182  test    eax, eax
0x18003b184  jz      short loc_18003B1C6
0x18003b186  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b18d  lea     rdx, WPP_GLOBAL_Control
0x18003b194  cmp     rcx, rdx
0x18003b197  jz      loc_18003B0CA
0x18003b19d  mov     edx, [rcx+2Ch]
0x18003b1a0  test    r15b, dl
0x18003b1a3  jz      loc_18003B0CA
0x18003b1a9  mov     [rsp+70h+var_40], 9A9h
0x18003b1b1  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b1b8  mov     [rsp+70h+var_48], r8
0x18003b1bd  mov     dword ptr [rsp+70h+Timeout], eax
0x18003b1c1  jmp     loc_18003B0BA
0x18003b1c6  movdqa  xmm0, [rbp+var_20]
0x18003b1cb  jmp     loc_18003AFEF
0x18003b1d0  xor     r15d, r15d
0x18003b1d3  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b1da  mov     r9d, 98Fh
0x18003b1e0  lea     rdx, aSresult; "sResult"
0x18003b1e7  mov     ecx, 0C00000E5h
0x18003b1ec  mov     esi, 0C00000E5h
0x18003b1f1  call    DebugTraceError
0x18003b1f6  cmp     qword ptr [rbp+var_20], 0
0x18003b1fb  jz      loc_18003B0D3
0x18003b201  movaps  xmm0, [rbp+var_20]
0x18003b205  lea     rcx, [rbp+var_10]
0x18003b209  movdqa  [rbp+var_10], xmm0
0x18003b20e  call    _FreeImage
0x18003b213  jmp     loc_18003B0D3
0x18003b218  sub     eax, r15d
0x18003b21b  jz      loc_18003B029
0x18003b221  sub     eax, r15d
0x18003b224  jz      loc_1800A328C
0x18003b22a  sub     eax, r15d
0x18003b22d  jz      loc_1800A3282
0x18003b233  cmp     eax, r15d
0x18003b236  jnz     loc_1800A3296
0x18003b23c  jmp     loc_18003B029
0x18003b241  mov     ebx, 30h ; '0'
0x18003b246  jmp     loc_18003B02E
0x18003b24b  sub     eax, 7
0x18003b24e  jz      loc_1800A32B1
0x18003b254  sub     eax, r15d
0x18003b257  jz      loc_18003B029
0x18003b25d  sub     eax, 0FFF9h
0x18003b262  jz      loc_1800A32A7
0x18003b268  sub     eax, r15d
0x18003b26b  jz      loc_1800A329D
0x18003b271  cmp     eax, 2
0x18003b274  jnz     loc_1800A3296
0x18003b27a  lea     ebx, [rax+26h]
0x18003b27d  jmp     loc_18003B02E
0x18003b282  mov     esi, 0C000000Dh
0x18003b287  mov     r9d, 9C4h
0x18003b28d  mov     ecx, 0C000000Dh
0x18003b292  jmp     short loc_18003B2A4
0x18003b294  mov     esi, 0C000009Ah
0x18003b299  mov     r9d, 9D5h
0x18003b29f  mov     ecx, 0C000009Ah
0x18003b2a4  lea     rdx, aSresult; "sResult"
0x18003b2ab  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b2b2  call    DebugTraceError
0x18003b2b7  jmp     loc_18003B0CA
0x18003b2bc  mov     edx, 1Bh
0x18003b2c1  mov     [rsp+70h+var_40], r8d
0x18003b2c6  jmp     loc_1800A32BB
0x18003b2cb  mov     r9d, 9EBh
0x18003b2d1  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b2d8  lea     rdx, aSresult; "sResult"
0x18003b2df  mov     ecx, eax
0x18003b2e1  call    DebugTraceError
0x18003b2e6  mov     rdi, [rbp+var_30]
0x18003b2ea  jmp     loc_18003B0CA
0x1800a3282  mov     ebx, 68h ; 'h'
0x1800a3287  jmp     loc_18003B02E
0x1800a328c  mov     ebx, 70h ; 'p'
0x1800a3291  jmp     loc_18003B02E
0x1800a3296  xor     ebx, ebx
0x1800a3298  jmp     loc_18003B02E
0x1800a329d  mov     ebx, 188h
0x1800a32a2  jmp     loc_18003B02E
0x1800a32a7  mov     ebx, 100h
0x1800a32ac  jmp     loc_18003B02E
0x1800a32b1  mov     ebx, 58h ; 'X'
0x1800a32b6  jmp     loc_18003B02E
0x1800a32bb  mov     rax, [rdi]
0x1800a32be  mov     r9, r14
0x1800a32c1  mov     rcx, [rcx+18h]
0x1800a32c5  mov     [rsp+70h+var_48], rax
0x1800a32ca  mov     [rsp+70h+Timeout], rdi
0x1800a32cf  call    WPP_SF_qqSD
0x1800a32d4  nop
0x1800a32d5  jmp     loc_18003B081
```
