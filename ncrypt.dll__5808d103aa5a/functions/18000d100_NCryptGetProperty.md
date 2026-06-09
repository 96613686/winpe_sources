# NCryptGetProperty

- ea: `0x18000d100`
- end: `0x18000d92c`
- name: `NCryptGetProperty`
- size: `2092`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, PBYTE pbOutput, DWORD cbOutput, DWORD *pcbResult, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a06c`

## callees

- `0x180007234`
- `0x180007ca0`
- `0x180009cd0`
- `0x18000a670`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000d100`
- `0x18000e120`
- `0x180010684`
- `0x180011cb0`
- `0x180014c1c`
- `0x180020010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000d4bc`
- `ntdll!RtlFreeHeap` at `0x18000d4bc`

## string_xrefs

- `0x18000d1a0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000d37f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000d54b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000d65f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000d88f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000d8ac`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptGetProperty(
        NCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        PBYTE pbOutput,
        DWORD cbOutput,
        DWORD *pcbResult,
        DWORD dwFlags)
{
  PBYTE v6; // r10
  PVOID *v9; // rcx
  NCRYPT_HANDLE v10; // rbx
  NCRYPT_HANDLE v11; // rdx
  NCRYPT_HANDLE v12; // r11
  int v13; // ebp
  PVOID v14; // rsi
  DWORD *v15; // r8
  unsigned __int64 v16; // rax
  DWORD v17; // ebp
  _QWORD *v18; // rsi
  SECURITY_STATUS v19; // r15d
  __int64 i; // rcx
  int v21; // edx
  int v22; // r12d
  __int64 j; // rcx
  int v24; // esi
  __int64 v25; // rcx
  int v26; // ebx
  unsigned int v27; // eax
  int v28; // r9d
  unsigned int v29; // ebp
  DWORD *v30; // rcx
  PBYTE v31; // rbx
  char v32; // r12
  NCRYPT_HANDLE v33; // rdi
  void *v35; // rax
  int v36; // eax
  NCRYPT_HANDLE v37; // r12
  __int64 v38; // rdx
  SECURITY_STATUS v39; // eax
  unsigned int v40; // eax
  __int64 v41; // rcx
  char *v42; // r8
  int v43; // r11d
  __int64 v44; // r9
  char *v45; // rdx
  char *v46; // rax
  unsigned int v47; // eax
  SECURITY_STATUS v48; // eax
  __int64 v49; // r11
  _QWORD *v50; // r10
  __int64 v51; // r9
  __int64 v52; // [rsp+20h] [rbp-88h]
  DWORD v53; // [rsp+40h] [rbp-68h] BYREF
  DWORD v54; // [rsp+44h] [rbp-64h]
  PVOID P; // [rsp+48h] [rbp-60h]
  NCRYPT_HANDLE v56; // [rsp+50h] [rbp-58h]
  _QWORD *v57; // [rsp+58h] [rbp-50h]
  NCRYPT_HANDLE v58; // [rsp+60h] [rbp-48h]
  NCRYPT_HANDLE v59; // [rsp+68h] [rbp-40h]
  int v60; // [rsp+B0h] [rbp+8h]
  DWORD v62; // [rsp+C8h] [rbp+20h]

  v62 = cbOutput;
  v6 = pbOutput;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, (_DWORD)pbOutput, hObject, (__int64)pszProperty, dwFlags);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v6 = pbOutput;
    *(_QWORD *)&cbOutput = v62;
  }
  if ( !hObject )
    goto LABEL_58;
  if ( *(_DWORD *)hObject != 1145307137 )
  {
    if ( *(_DWORD *)hObject == 1145307138 )
    {
      v10 = 0;
      v56 = hObject;
      v11 = 0;
      v12 = hObject;
      goto LABEL_7;
    }
LABEL_58:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v9[2],
        (_DWORD)pszProperty,
        (_DWORD)pbOutput,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        111);
    return -2146893786;
  }
  v12 = 0;
  v56 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(hObject + 4));
  v9 = (PVOID *)WPP_GLOBAL_Control;
  v10 = hObject;
  v11 = hObject;
LABEL_7:
  v13 = 0;
  v14 = v6;
  v59 = v11;
  v58 = v10;
  v60 = 0;
  P = v6;
  if ( !pszProperty || (v15 = pcbResult) == 0 )
  {
    v19 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 1399);
    goto LABEL_36;
  }
  v16 = -1;
  do
    ++v16;
  while ( pszProperty[v16] );
  if ( v16 > 0x40 )
  {
    v19 = -2146893785;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v9[2],
        v11,
        (_DWORD)pcbResult,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        126);
    goto LABEL_36;
  }
  v17 = cbOutput;
  v54 = cbOutput;
  v18 = (_QWORD *)(v11 + 272);
  v19 = -2146893784;
  while ( 1 )
  {
    v57 = v18;
    if ( !v12 )
    {
      v32 = dwFlags;
      v29 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, PBYTE, _QWORD, DWORD *, DWORD))(v10 + 48))(
              *v18,
              pszProperty,
              v6,
              *(_QWORD *)&cbOutput,
              v15,
              dwFlags);
      goto LABEL_32;
    }
    v53 = 0;
    for ( i = 0; i != 16; i += 2 )
    {
      v21 = pszProperty[i] - aProviderHandle[i];
      if ( v21 )
        break;
      v21 = pszProperty[i + 1] - aProviderHandle[i + 1];
      if ( v21 )
        break;
    }
    if ( !v21 )
      break;
    v22 = 0;
    for ( j = 0; j != 10; j += 2 )
    {
      v24 = pszProperty[j] - aUiPolicy[j];
      if ( v24 )
        break;
      v24 = pszProperty[j + 1] - aUiPolicy[j + 1];
      if ( v24 )
        break;
    }
    v25 = -1;
    do
    {
      v26 = pszProperty[v25 + 1] - aEcccurvenameli[v25 + 1];
      if ( v26 )
        break;
      v25 += 2;
      if ( v25 == 17 )
        break;
      v26 = pszProperty[v25] - aEcccurvenameli[v25];
    }
    while ( !v26 );
    if ( P )
    {
      if ( v24 )
      {
        if ( !v26 )
        {
          v35 = (void *)SafeAllocaAllocateFromHeap(v17);
          P = v35;
          if ( !v35 )
            goto LABEL_70;
          v12 = v56;
          v60 = 1;
        }
      }
      else if ( v17 <= 0x20 )
      {
        v17 = 0;
        P = 0;
        v54 = 0;
        v22 = 1;
      }
      else
      {
        v17 -= 32;
        P = (char *)P + 32;
        v54 = v17;
      }
    }
    LODWORD(v52) = v17;
    v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPCWSTR, PVOID, __int64, DWORD *, DWORD))(*(_QWORD *)(v12 + 8)
                                                                                             + 56LL))(
            *(_QWORD *)(*(_QWORD *)(v12 + 8) + 272LL),
            *(_QWORD *)(v12 + 16),
            pszProperty,
            P,
            v52,
            &v53,
            dwFlags);
    v29 = v27;
    if ( v26 || v27 && v27 != -2146893784 )
    {
      v30 = pcbResult;
      v31 = pbOutput;
      *pcbResult = v53;
    }
    else
    {
      if ( !P )
      {
        v35 = (void *)SafeAllocaAllocateFromHeap(v53);
        P = v35;
        if ( !v35 )
        {
LABEL_70:
          v13 = v60;
          v19 = -2146893810;
          v14 = v35;
          goto LABEL_36;
        }
        v13 = 1;
        v60 = 1;
        v47 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPCWSTR, void *, DWORD, DWORD *, DWORD))(*(_QWORD *)(v56 + 8)
                                                                                                + 56LL))(
                *(_QWORD *)(*(_QWORD *)(v56 + 8) + 272LL),
                *(_QWORD *)(v56 + 16),
                pszProperty,
                v35,
                v53,
                &v53,
                dwFlags);
        if ( v47 )
        {
          v48 = NormalizeNteStatus(v47);
          v14 = P;
          v19 = v48;
          goto LABEL_36;
        }
      }
      v31 = pbOutput;
      v40 = DeserializeCurveNameList((_DWORD)P, v53, (_DWORD)pbOutput, v62, (__int64)pcbResult);
      v30 = pcbResult;
      v29 = v40;
    }
    if ( !v24 )
    {
      *v30 += 32;
      if ( v22 )
        goto LABEL_57;
      if ( !v29 )
      {
        v14 = P;
        if ( v31 )
        {
          v41 = *((unsigned int *)P + 2);
          v42 = 0;
          v43 = *((_DWORD *)P + 1);
          v44 = *((unsigned int *)P + 3);
          if ( (_DWORD)v41 )
            v42 = (char *)P + 20;
          v45 = 0;
          if ( (_DWORD)v44 )
            v45 = (char *)P + v41 + 20;
          v46 = 0;
          if ( *((_DWORD *)P + 4) )
            v46 = (char *)P + v44 + v41 + 20;
          *(_DWORD *)v31 = *(_DWORD *)P;
          *((_DWORD *)v31 + 1) = v43;
          *((_QWORD *)v31 + 1) = v42;
          *((_QWORD *)v31 + 2) = v45;
          *((_QWORD *)v31 + 3) = v46;
        }
        goto LABEL_35;
      }
    }
    v10 = v58;
    v18 = v57;
    v32 = dwFlags;
LABEL_32:
    if ( v29 != -2146893778 )
    {
      if ( !v29 )
      {
        v14 = P;
LABEL_35:
        v13 = v60;
        v19 = 0;
        goto LABEL_36;
      }
      v37 = v56;
      goto LABEL_72;
    }
    if ( (v32 & 0x40) != 0 )
    {
      v19 = -2146893790;
      DebugTraceError(
        2148073506LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        1645);
      v13 = v60;
      v14 = P;
      goto LABEL_36;
    }
    v37 = v56;
    if ( !v56 )
    {
      v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(v10 + 192))(
              *v18,
              0,
              L"NCryptGetProperty",
              0);
      if ( !v29 )
        goto LABEL_65;
      v51 = 1670;
LABEL_102:
      DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v51);
LABEL_72:
      if ( v37 )
      {
        v38 = *(_QWORD *)(v37 + 8);
        if ( v38 )
          EtwLogNCryptOperationFailed(16, *(_QWORD *)(v38 + 280), *(_QWORD *)(v37 + 24), v28, v29);
      }
      v39 = NormalizeNteStatus(v29);
      v13 = v60;
      v14 = P;
      v19 = v39;
      goto LABEL_36;
    }
    v29 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_HANDLE, const wchar_t *, _QWORD))(*(_QWORD *)(v56 + 8) + 192LL))(
            *(_QWORD *)(*(_QWORD *)(v56 + 8) + 272LL),
            hObject,
            L"NCryptGetProperty",
            0);
    if ( v29 )
    {
      v51 = 1658;
      goto LABEL_102;
    }
    v18 = (_QWORD *)(v59 + 272);
LABEL_65:
    v15 = pcbResult;
    v12 = v37;
    v6 = pbOutput;
    v17 = v54;
    *(_QWORD *)&cbOutput = v62;
  }
  *v15 = 8;
  if ( !v6 )
  {
    v19 = 0;
LABEL_57:
    v13 = v60;
    v14 = P;
    goto LABEL_36;
  }
  if ( cbOutput >= 8 )
  {
    ValidateAndReferenceProvider(*(_QWORD *)(v12 + 8));
    v19 = 0;
    *v50 = *(_QWORD *)(v49 + 8);
    goto LABEL_57;
  }
  v13 = v60;
  v14 = P;
LABEL_36:
  v33 = v58;
  if ( v58 && _InterlockedExchangeAdd((volatile signed __int32 *)(v58 + 4), 0xFFFFFFFF) == 1 )
  {
    v36 = (*(__int64 (__fastcall **)(_QWORD))(v33 + 96))(*(_QWORD *)(v33 + 272));
    if ( v36 < 0 )
      DebugTraceError(
        (unsigned int)v36,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        128);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids, v33);
    UnloadProvider(*(_QWORD *)(v33 + 8));
    MSCryptFree(v33);
  }
  if ( v13 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
  return v19;
}

```

## disassembly

```asm
0x18000d100  mov     [rsp+arg_18], r9d
0x18000d105  mov     [rsp+arg_10], r8
0x18000d10a  push    rdi
0x18000d10b  push    r14
0x18000d10d  sub     rsp, 98h
0x18000d114  mov     r10, r8
0x18000d117  mov     rdi, rdx
0x18000d11a  mov     r14, rcx
0x18000d11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d124  lea     rax, WPP_GLOBAL_Control
0x18000d12b  cmp     rcx, rax
0x18000d12e  jnz     loc_18000D422
0x18000d134  mov     [rsp+0A8h+arg_8], rbx
0x18000d13c  test    r14, r14
0x18000d13f  jz      loc_18000D53C
0x18000d145  cmp     dword ptr [r14], 44440001h
0x18000d14c  jz      short loc_18000D169
0x18000d14e  cmp     dword ptr [r14], 44440002h
0x18000d155  jnz     loc_18000D53C
0x18000d15b  xor     ebx, ebx
0x18000d15d  mov     [rsp+0A8h+var_58], r14
0x18000d162  xor     edx, edx
0x18000d164  mov     r11, r14
0x18000d167  jmp     short loc_18000D183
0x18000d169  xor     r11d, r11d
0x18000d16c  mov     [rsp+0A8h+var_58], r11
0x18000d171  lock inc dword ptr [r14+4]
0x18000d176  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d17d  mov     rbx, r14
0x18000d180  mov     rdx, r14
0x18000d183  mov     [rsp+0A8h+var_18], rbp
0x18000d18b  xor     ebp, ebp
0x18000d18d  mov     [rsp+0A8h+var_20], rsi
0x18000d195  mov     rsi, r10
0x18000d198  mov     [rsp+0A8h+var_28], r12
0x18000d1a0  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d1a7  mov     [rsp+0A8h+var_30], r13
0x18000d1ac  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000d1b3  mov     [rsp+0A8h+var_38], r15
0x18000d1b8  mov     [rsp+0A8h+var_40], rdx
0x18000d1bd  mov     [rsp+0A8h+var_48], rbx
0x18000d1c2  mov     [rsp+0A8h+arg_0], ebp
0x18000d1c9  mov     [rsp+0A8h+P], r10
0x18000d1ce  test    rdi, rdi
0x18000d1d1  jz      loc_18000D8EB
0x18000d1d7  mov     r8, [rsp+0A8h+pcbResult]
0x18000d1df  test    r8, r8
0x18000d1e2  jz      loc_18000D8EB
0x18000d1e8  mov     rax, r13
0x18000d1eb  nop     dword ptr [rax+rax+00h]
0x18000d1f0  inc     rax
0x18000d1f3  cmp     [rdi+rax*2], bp
0x18000d1f7  jnz     short loc_18000D1F0
0x18000d1f9  cmp     rax, 40h ; '@'
0x18000d1fd  ja      loc_18000D3E0
0x18000d203  mov     ebp, r9d
0x18000d206  mov     [rsp+0A8h+var_64], r9d
0x18000d20b  lea     rsi, [rdx+110h]
0x18000d212  mov     r15d, 80090028h
0x18000d218  lea     r12, aProviderHandle; "Provider Handle"
0x18000d21f  mov     [rsp+0A8h+var_50], rsi
0x18000d224  test    r11, r11
0x18000d227  jz      loc_18000D5EC
0x18000d22d  mov     [rsp+0A8h+var_68], 0
0x18000d235  xor     ecx, ecx
0x18000d237  nop     word ptr [rax+rax+00000000h]
0x18000d240  movzx   edx, word ptr [rdi+rcx*2]
0x18000d244  movzx   eax, word ptr [r12+rcx*2]
0x18000d249  sub     edx, eax
0x18000d24b  jnz     short loc_18000D266
0x18000d24d  movzx   edx, word ptr [rdi+rcx*2+2]
0x18000d252  movzx   eax, word ptr [r12+rcx*2+2]
0x18000d258  sub     edx, eax
0x18000d25a  jnz     short loc_18000D266
0x18000d25c  add     rcx, 2
0x18000d260  cmp     rcx, 10h
0x18000d264  jnz     short loc_18000D240
0x18000d266  test    edx, edx
0x18000d268  jz      loc_18000D6EE
0x18000d26e  xor     r12d, r12d
0x18000d271  lea     rdx, aUiPolicy; "UI Policy"
0x18000d278  xor     ecx, ecx
0x18000d27a  nop     word ptr [rax+rax+00h]
0x18000d280  movzx   esi, word ptr [rdi+rcx*2]
0x18000d284  movzx   eax, word ptr [rdx+rcx*2]
0x18000d288  sub     esi, eax
0x18000d28a  jnz     short loc_18000D2A4
0x18000d28c  movzx   esi, word ptr [rdi+rcx*2+2]
0x18000d291  movzx   eax, word ptr [rdx+rcx*2+2]
0x18000d296  sub     esi, eax
0x18000d298  jnz     short loc_18000D2A4
0x18000d29a  add     rcx, 2
0x18000d29e  cmp     rcx, 0Ah
0x18000d2a2  jnz     short loc_18000D280
0x18000d2a4  mov     rcx, r13
0x18000d2a7  lea     rdx, aEcccurvenameli; "ECCCurveNameList"
0x18000d2ae  xchg    ax, ax
0x18000d2b0  movzx   ebx, word ptr [rdi+rcx*2+2]
0x18000d2b5  movzx   eax, word ptr [rdx+rcx*2+2]
0x18000d2ba  sub     ebx, eax
0x18000d2bc  jnz     short loc_18000D2D4
0x18000d2be  add     rcx, 2
0x18000d2c2  cmp     rcx, 11h
0x18000d2c6  jz      short loc_18000D2D4
0x18000d2c8  movzx   ebx, word ptr [rdi+rcx*2]
0x18000d2cc  movzx   eax, word ptr [rdx+rcx*2]
0x18000d2d0  sub     ebx, eax
0x18000d2d2  jz      short loc_18000D2B0
0x18000d2d4  mov     rax, [rsp+0A8h+P]
0x18000d2d9  test    rax, rax
0x18000d2dc  jnz     loc_18000D470
0x18000d2e2  mov     rax, [r11+8]
0x18000d2e6  mov     r8, rdi
0x18000d2e9  mov     ecx, [rsp+0A8h+dwFlags]
0x18000d2f0  mov     r9, [rsp+0A8h+P]
0x18000d2f5  mov     rdx, [r11+10h]
0x18000d2f9  mov     [rsp+0A8h+var_78], ecx
0x18000d2fd  lea     rcx, [rsp+0A8h+var_68]
0x18000d302  mov     [rsp+0A8h+var_80], rcx
0x18000d307  mov     rcx, [rax+110h]
0x18000d30e  mov     rax, [rax+38h]
0x18000d312  mov     dword ptr [rsp+0A8h+var_88], ebp
0x18000d316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d31b  mov     ebp, eax
0x18000d31d  test    ebx, ebx
0x18000d31f  jz      loc_18000D617
0x18000d325  mov     rcx, [rsp+0A8h+pcbResult]
0x18000d32d  mov     eax, [rsp+0A8h+var_68]
0x18000d331  mov     rbx, [rsp+0A8h+arg_10]
0x18000d339  mov     [rcx], eax
0x18000d33b  test    esi, esi
0x18000d33d  jz      loc_18000D51F
0x18000d343  mov     rbx, [rsp+0A8h+var_48]
0x18000d348  mov     rsi, [rsp+0A8h+var_50]
0x18000d34d  mov     r12d, [rsp+0A8h+dwFlags]
0x18000d355  cmp     ebp, 8009002Eh
0x18000d35b  jz      loc_18000D58B
0x18000d361  test    ebp, ebp
0x18000d363  jnz     loc_18000D65A
0x18000d369  mov     rsi, [rsp+0A8h+P]
0x18000d36e  mov     ebp, [rsp+0A8h+arg_0]
0x18000d375  xor     r15d, r15d
0x18000d378  lea     r14, WPP_GLOBAL_Control
0x18000d37f  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d386  mov     rdi, [rsp+0A8h+var_48]
0x18000d38b  mov     r12, [rsp+0A8h+var_28]
0x18000d393  test    rdi, rdi
0x18000d396  jz      short loc_18000D3A8
0x18000d398  lock xadd [rdi+4], r13d
0x18000d39e  cmp     r13d, 1
0x18000d3a2  jz      loc_18000D4C7
0x18000d3a8  mov     r13, [rsp+0A8h+var_30]
0x18000d3ad  test    ebp, ebp
0x18000d3af  mov     rbp, [rsp+0A8h+var_18]
0x18000d3b7  jnz     loc_18000D4AA
0x18000d3bd  mov     rsi, [rsp+0A8h+var_20]
0x18000d3c5  mov     eax, r15d
0x18000d3c8  mov     r15, [rsp+0A8h+var_38]
0x18000d3cd  mov     rbx, [rsp+0A8h+arg_8]
0x18000d3d5  add     rsp, 98h
0x18000d3dc  pop     r14
0x18000d3de  pop     rdi
0x18000d3df  retn
0x18000d3e0  mov     r15d, 80090027h
0x18000d3e6  lea     r14, WPP_GLOBAL_Control
0x18000d3ed  cmp     rcx, r14
0x18000d3f0  jz      short loc_18000D37F
0x18000d3f2  test    byte ptr [rcx+1Ch], 1
0x18000d3f6  jz      short loc_18000D37F
0x18000d3f8  mov     rcx, [rcx+10h]
0x18000d3fc  lea     r9, aStatus; "Status"
0x18000d403  mov     [rsp+0A8h+var_78], 57Eh
0x18000d40b  mov     [rsp+0A8h+var_80], r12
0x18000d410  mov     dword ptr [rsp+0A8h+var_88], 80090027h
0x18000d418  call    WPP_SF_sDsd
0x18000d41d  jmp     loc_18000D37F
0x18000d422  test    byte ptr [rcx+1Ch], 4
0x18000d426  jz      loc_18000D134
0x18000d42c  mov     eax, [rsp+0A8h+dwFlags]
0x18000d433  mov     edx, 10h
0x18000d438  mov     rcx, [rcx+10h]
0x18000d43c  mov     r9, r14
0x18000d43f  mov     dword ptr [rsp+0A8h+var_80], eax
0x18000d443  mov     [rsp+0A8h+var_88], rdi
0x18000d448  call    WPP_SF_PSD
0x18000d44d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d454  lea     rax, WPP_GLOBAL_Control
0x18000d45b  mov     r10, [rsp+0A8h+arg_10]
0x18000d463  mov     r9d, [rsp+0A8h+arg_18]
0x18000d46b  jmp     loc_18000D134
0x18000d470  test    esi, esi
0x18000d472  jz      loc_18000D7CE
0x18000d478  test    ebx, ebx
0x18000d47a  jnz     loc_18000D2E2
0x18000d480  mov     ecx, ebp
0x18000d482  call    SafeAllocaAllocateFromHeap
0x18000d487  mov     [rsp+0A8h+P], rax
0x18000d48c  test    rax, rax
0x18000d48f  jz      loc_18000D645
0x18000d495  mov     r11, [rsp+0A8h+var_58]
0x18000d49a  mov     [rsp+0A8h+arg_0], 1
0x18000d4a5  jmp     loc_18000D2E2
0x18000d4aa  mov     rcx, gs:60h
0x18000d4b3  mov     r8, rsi; P
0x18000d4b6  xor     edx, edx; Flags
0x18000d4b8  mov     rcx, [rcx+30h]; HeapHandle
0x18000d4bc  call    cs:__imp_RtlFreeHeap
0x18000d4c2  jmp     loc_18000D3BD
0x18000d4c7  mov     rcx, [rdi+110h]
0x18000d4ce  mov     rax, [rdi+60h]
0x18000d4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4d7  test    eax, eax
0x18000d4d9  js      loc_18000D910
0x18000d4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4e6  cmp     rcx, r14
0x18000d4e9  jz      short loc_18000D509
0x18000d4eb  test    byte ptr [rcx+1Ch], 20h
0x18000d4ef  jz      short loc_18000D509
0x18000d4f1  mov     rcx, [rcx+10h]
0x18000d4f5  lea     r8, WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids
0x18000d4fc  mov     edx, 0Ch
0x18000d501  mov     r9, rdi
0x18000d504  call    WPP_SF_q
0x18000d509  mov     rcx, [rdi+8]
0x18000d50d  call    UnloadProvider
0x18000d512  mov     rcx, rdi
0x18000d515  call    MSCryptFree
0x18000d51a  jmp     loc_18000D3A8
0x18000d51f  add     dword ptr [rcx], 20h ; ' '
0x18000d522  test    r12d, r12d
0x18000d525  jz      loc_18000D706
0x18000d52b  mov     ebp, [rsp+0A8h+arg_0]
0x18000d532  mov     rsi, [rsp+0A8h+P]
0x18000d537  jmp     loc_18000D378
0x18000d53c  cmp     rcx, rax
0x18000d53f  jz      short loc_18000D573
0x18000d541  test    byte ptr [rcx+1Ch], 1
0x18000d545  jz      short loc_18000D573
0x18000d547  mov     rcx, [rcx+10h]
0x18000d54b  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d552  mov     [rsp+0A8h+var_78], 56Fh
0x18000d55a  lea     r9, aStatus; "Status"
0x18000d561  mov     [rsp+0A8h+var_80], rbx
0x18000d566  mov     dword ptr [rsp+0A8h+var_88], 80090026h
0x18000d56e  call    WPP_SF_sDsd
0x18000d573  mov     rbx, [rsp+0A8h+arg_8]
0x18000d57b  mov     eax, 80090026h
0x18000d580  add     rsp, 98h
0x18000d587  pop     r14
0x18000d589  pop     rdi
0x18000d58a  retn
0x18000d58b  test    r12b, 40h
0x18000d58f  jnz     loc_18000D8AC
0x18000d595  mov     r12, [rsp+0A8h+var_58]
0x18000d59a  lea     r8, aNcryptgetprope_0; "NCryptGetProperty"
0x18000d5a1  xor     r9d, r9d
0x18000d5a4  test    r12, r12
0x18000d5a7  jnz     loc_18000D82E
0x18000d5ad  mov     rcx, [rsi]
0x18000d5b0  xor     edx, edx
0x18000d5b2  mov     rax, [rbx+0C0h]
0x18000d5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5be  mov     ebp, eax
0x18000d5c0  test    eax, eax
0x18000d5c2  jnz     loc_18000D889
0x18000d5c8  mov     r8, [rsp+0A8h+pcbResult]
0x18000d5d0  mov     r11, r12
0x18000d5d3  mov     r10, [rsp+0A8h+arg_10]
0x18000d5db  mov     ebp, [rsp+0A8h+var_64]
0x18000d5df  mov     r9d, [rsp+0A8h+arg_18]
0x18000d5e7  jmp     loc_18000D218
0x18000d5ec  mov     r12d, [rsp+0A8h+dwFlags]
0x18000d5f4  mov     rdx, rdi
0x18000d5f7  mov     rcx, [rsi]
0x18000d5fa  mov     rax, [rbx+30h]
0x18000d5fe  mov     dword ptr [rsp+0A8h+var_80], r12d
0x18000d603  mov     [rsp+0A8h+var_88], r8
0x18000d608  mov     r8, r10
0x18000d60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d610  mov     ebp, eax
0x18000d612  jmp     loc_18000D355
0x18000d617  test    eax, eax
0x18000d619  jnz     loc_18000D7E8
0x18000d61f  cmp     [rsp+0A8h+P], 0
0x18000d625  jnz     loc_18000D6B1
0x18000d62b  mov     ecx, [rsp+0A8h+var_68]
0x18000d62f  call    SafeAllocaAllocateFromHeap
0x18000d634  mov     [rsp+0A8h+P], rax
0x18000d639  mov     r8, rax
0x18000d63c  test    rax, rax
0x18000d63f  jnz     loc_18000D766
0x18000d645  mov     ebp, [rsp+0A8h+arg_0]
0x18000d64c  mov     r15d, 8009000Eh
0x18000d652  mov     rsi, rax
0x18000d655  jmp     loc_18000D378
0x18000d65a  mov     r12, [rsp+0A8h+var_58]
0x18000d65f  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d666  test    r12, r12
0x18000d669  jz      short loc_18000D68F
0x18000d66b  mov     rdx, [r12+8]
  ... truncated ...
```
