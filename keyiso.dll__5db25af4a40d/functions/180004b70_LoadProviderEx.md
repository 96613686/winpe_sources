# LoadProviderEx

- ea: `0x180004b70`
- end: `0x180004e2c`
- name: `LoadProviderEx`
- size: `700`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004550`

## callees

- `0x180001824`
- `0x180003cf0`
- `0x180004470`
- `0x180004b70`
- `0x180004e34`
- `0x180005440`
- `0x180005634`
- `0x18000d094`
- `0x180017240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004cd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ba4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ba4`

## string_xrefs

- `0x180004d76`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180004db1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadProviderEx(__int64 a1, int a2, __int64 a3, __int64 *a4, __int64 a5)
{
  __int64 v7; // r8
  __int64 i; // rbx
  HMODULE v9; // rbp
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v13; // rdx
  __int128 *v14; // rcx
  __int128 v15; // xmm0
  unsigned int v16; // eax
  unsigned int v17; // r8d
  int v19; // edi
  int v20; // r8d
  __int64 v21; // r9
  __int64 v22; // rcx
  HMODULE v23; // [rsp+40h] [rbp-58h] BYREF
  __int64 v24; // [rsp+48h] [rbp-50h] BYREF
  __int128 *v25; // [rsp+50h] [rbp-48h] BYREF

  v25 = 0;
  v23 = 0;
  if ( !g_fLoaderInitialized )
  {
    v19 = 0;
    v11 = -1073741595;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        (unsigned int)"sResult",
        229,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        143);
LABEL_21:
    *a4 = 0;
    if ( !v19 )
      return v11;
    goto LABEL_16;
  }
  EnterCriticalSection(&g_csLoaderLock);
  for ( i = g_pLoadedProviderList; i; i = *(_QWORD *)(i + 24) )
  {
    if ( !wcsicmp(**(const wchar_t ***)(a1 + 40), *(const wchar_t **)i) )
      break;
  }
  v24 = i;
  if ( i )
  {
    v9 = *(HMODULE *)(i + 8);
  }
  else
  {
    v10 = LoadImage(a1, &v23);
    v9 = v23;
    v11 = v10;
    if ( v10 )
    {
      v21 = 2473;
LABEL_35:
      v22 = v10;
      goto LABEL_27;
    }
  }
  v10 = LoadInterface(v9, a1, v7, &v25);
  v11 = v10;
  if ( v10 )
  {
    v21 = 2490;
    goto LABEL_35;
  }
  v13 = 2;
  v14 = v25;
  do
  {
    a5 += 128;
    v15 = *v14;
    v14 += 8;
    *(_OWORD *)(a5 - 128) = v15;
    *(_OWORD *)(a5 - 112) = *(v14 - 7);
    *(_OWORD *)(a5 - 96) = *(v14 - 6);
    *(_OWORD *)(a5 - 80) = *(v14 - 5);
    *(_OWORD *)(a5 - 64) = *(v14 - 4);
    *(_OWORD *)(a5 - 48) = *(v14 - 3);
    *(_OWORD *)(a5 - 32) = *(v14 - 2);
    *(_OWORD *)(a5 - 16) = *(v14 - 1);
    --v13;
  }
  while ( v13 );
  if ( !i )
  {
    v10 = NewLoadedProviderHandle(a1, v9, &v24);
    i = v24;
    v11 = v10;
    if ( !v10 )
    {
      *(_QWORD *)(v24 + 24) = g_pLoadedProviderList;
      g_pLoadedProviderList = i;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qqSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v20, a1, i, *(_QWORD *)i, *(_DWORD *)(i + 16));
      goto LABEL_15;
    }
    v21 = 2539;
    goto LABEL_35;
  }
  v16 = *(_DWORD *)(i + 16);
  v17 = v16 + 1;
  if ( v16 + 1 < v16 )
  {
    v11 = -1073741670;
    v22 = 3221225626LL;
    v21 = 2517;
LABEL_27:
    v19 = 1;
    DebugTraceError(v22, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v21);
    if ( !i && v9 )
      FreeImage(v9);
    goto LABEL_21;
  }
  *(_DWORD *)(i + 16) = v17;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qqSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v17, a1, i, *(_QWORD *)i, v17);
LABEL_15:
  *a4 = i;
LABEL_16:
  LeaveCriticalSection(&g_csLoaderLock);
  return v11;
}

```

## disassembly

```asm
0x180004b70  push    rbx
0x180004b72  push    rbp
0x180004b73  push    rsi
0x180004b74  push    rdi
0x180004b75  push    r14
0x180004b77  push    r15
0x180004b79  sub     rsp, 68h
0x180004b7d  xor     r15d, r15d
0x180004b80  mov     r14, r9
0x180004b83  cmp     cs:g_fLoaderInitialized, r15d
0x180004b8a  mov     rdi, rcx
0x180004b8d  mov     [rsp+98h+var_48], r15
0x180004b92  mov     [rsp+98h+var_58], r15
0x180004b97  jz      loc_180004CE5
0x180004b9d  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180004ba4  call    cs:__imp_EnterCriticalSection
0x180004baa  mov     rbx, cs:g_pLoadedProviderList
0x180004bb1  test    rbx, rbx
0x180004bb4  jz      short loc_180004BDC
0x180004bb6  nop     word ptr [rax+rax+00000000h]
0x180004bc0  mov     rcx, [rdi+28h]
0x180004bc4  mov     rdx, [rbx]; String2
0x180004bc7  mov     rcx, [rcx]; String1
0x180004bca  call    _wcsicmp
0x180004bcf  test    eax, eax
0x180004bd1  jz      short loc_180004BDC
0x180004bd3  mov     rbx, [rbx+18h]
0x180004bd7  test    rbx, rbx
0x180004bda  jnz     short loc_180004BC0
0x180004bdc  mov     [rsp+98h+var_50], rbx
0x180004be1  test    rbx, rbx
0x180004be4  jz      loc_180004DDE
0x180004bea  mov     rbp, [rbx+8]
0x180004bee  lea     r9, [rsp+98h+var_48]
0x180004bf3  mov     rdx, rdi
0x180004bf6  mov     rcx, rbp
0x180004bf9  call    _LoadInterface
0x180004bfe  mov     esi, eax
0x180004c00  test    eax, eax
0x180004c02  jnz     loc_180004E02
0x180004c08  mov     rax, [rsp+98h+arg_20]
0x180004c10  mov     edx, 2
0x180004c15  mov     rcx, [rsp+98h+var_48]
0x180004c1a  lea     rax, [rax+80h]
0x180004c21  movups  xmm0, xmmword ptr [rcx]
0x180004c24  lea     rcx, [rcx+80h]
0x180004c2b  movups  xmmword ptr [rax-80h], xmm0
0x180004c2f  movups  xmm1, xmmword ptr [rcx-70h]
0x180004c33  movups  xmmword ptr [rax-70h], xmm1
0x180004c37  movups  xmm0, xmmword ptr [rcx-60h]
0x180004c3b  movups  xmmword ptr [rax-60h], xmm0
0x180004c3f  movups  xmm1, xmmword ptr [rcx-50h]
0x180004c43  movups  xmmword ptr [rax-50h], xmm1
0x180004c47  movups  xmm0, xmmword ptr [rcx-40h]
0x180004c4b  movups  xmmword ptr [rax-40h], xmm0
0x180004c4f  movups  xmm1, xmmword ptr [rcx-30h]
0x180004c53  movups  xmmword ptr [rax-30h], xmm1
0x180004c57  movups  xmm0, xmmword ptr [rcx-20h]
0x180004c5b  movups  xmmword ptr [rax-20h], xmm0
0x180004c5f  movups  xmm1, xmmword ptr [rcx-10h]
0x180004c63  movups  xmmword ptr [rax-10h], xmm1
0x180004c67  sub     rdx, 1
0x180004c6b  jnz     short loc_180004C1A
0x180004c6d  test    rbx, rbx
0x180004c70  jz      loc_180004D13
0x180004c76  mov     eax, [rbx+10h]
0x180004c79  lea     r8d, [rax+1]
0x180004c7d  cmp     r8d, eax
0x180004c80  jb      loc_180004E0A
0x180004c86  mov     [rbx+10h], r8d
0x180004c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c91  lea     rax, WPP_GLOBAL_Control
0x180004c98  cmp     rcx, rax
0x180004c9b  jz      short loc_180004CC6
0x180004c9d  test    byte ptr [rcx+1Ch], 20h
0x180004ca1  jz      short loc_180004CC6
0x180004ca3  mov     edx, 1Bh
0x180004ca8  mov     [rsp+98h+var_68], r8d
0x180004cad  mov     rax, [rbx]
0x180004cb0  mov     r9, rdi
0x180004cb3  mov     rcx, [rcx+10h]
0x180004cb7  mov     [rsp+98h+var_70], rax
0x180004cbc  mov     [rsp+98h+var_78], rbx
0x180004cc1  call    WPP_SF_qqSD
0x180004cc6  mov     [r14], rbx
0x180004cc9  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180004cd0  call    cs:__imp_LeaveCriticalSection
0x180004cd6  mov     eax, esi
0x180004cd8  add     rsp, 68h
0x180004cdc  pop     r15
0x180004cde  pop     r14
0x180004ce0  pop     rdi
0x180004ce1  pop     rsi
0x180004ce2  pop     rbp
0x180004ce3  pop     rbx
0x180004ce4  retn
0x180004ce5  mov     edi, r15d
0x180004ce8  mov     esi, 0C00000E5h
0x180004ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cf4  lea     rax, WPP_GLOBAL_Control
0x180004cfb  cmp     rcx, rax
0x180004cfe  jz      short loc_180004D0A
0x180004d00  test    byte ptr [rcx+1Ch], 1
0x180004d04  jnz     loc_180004DAD
0x180004d0a  mov     [r14], r15
0x180004d0d  test    edi, edi
0x180004d0f  jnz     short loc_180004CC9
0x180004d11  jmp     short loc_180004CD6
0x180004d13  lea     r8, [rsp+98h+var_50]
0x180004d18  mov     rdx, rbp
0x180004d1b  mov     rcx, rdi
0x180004d1e  call    _NewLoadedProviderHandle
0x180004d23  mov     rbx, [rsp+98h+var_50]
0x180004d28  mov     esi, eax
0x180004d2a  test    eax, eax
0x180004d2c  jnz     loc_180004E1F
0x180004d32  mov     rax, cs:g_pLoadedProviderList
0x180004d39  mov     [rbx+18h], rax
0x180004d3d  mov     cs:g_pLoadedProviderList, rbx
0x180004d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d4b  lea     rax, WPP_GLOBAL_Control
0x180004d52  cmp     rcx, rax
0x180004d55  jz      loc_180004CC6
0x180004d5b  test    byte ptr [rcx+1Ch], 20h
0x180004d5f  jz      loc_180004CC6
0x180004d65  mov     eax, [rbx+10h]
0x180004d68  mov     edx, 1Ch
0x180004d6d  mov     [rsp+98h+var_68], eax
0x180004d71  jmp     loc_180004CAD
0x180004d76  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004d7d  lea     rdx, aSresult; "sResult"
0x180004d84  mov     edi, 1
0x180004d89  call    DebugTraceError
0x180004d8e  test    rbx, rbx
0x180004d91  jnz     loc_180004D0A
0x180004d97  test    rbp, rbp
0x180004d9a  jz      loc_180004D0A
0x180004da0  mov     rcx, rbp
0x180004da3  call    _FreeImage
0x180004da8  jmp     loc_180004D0A
0x180004dad  mov     rcx, [rcx+10h]
0x180004db1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004db8  mov     [rsp+98h+var_68], 98Fh
0x180004dc0  lea     r9, aSresult; "sResult"
0x180004dc7  mov     [rsp+98h+var_70], r8
0x180004dcc  mov     dword ptr [rsp+98h+var_78], 0C00000E5h
0x180004dd4  call    WPP_SF_sDsd
0x180004dd9  jmp     loc_180004D0A
0x180004dde  lea     rdx, [rsp+98h+var_58]
0x180004de3  mov     rcx, rdi
0x180004de6  call    _LoadImage
0x180004deb  mov     rbp, [rsp+98h+var_58]
0x180004df0  mov     esi, eax
0x180004df2  test    eax, eax
0x180004df4  jz      loc_180004BEE
0x180004dfa  mov     r9d, 9A9h
0x180004e00  jmp     short loc_180004E25
0x180004e02  mov     r9d, 9BAh
0x180004e08  jmp     short loc_180004E25
0x180004e0a  mov     esi, 0C000009Ah
0x180004e0f  mov     ecx, 0C000009Ah
0x180004e14  mov     r9d, 9D5h
0x180004e1a  jmp     loc_180004D76
0x180004e1f  mov     r9d, 9EBh
0x180004e25  mov     ecx, eax
0x180004e27  jmp     loc_180004D76
```
