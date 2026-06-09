# SerializeProperties

- ea: `0x180012ddc`
- end: `0x18001334a`
- name: `SerializeProperties`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800128ac`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180012ddc`
- `0x1800136f8`
- `0x180013770`
- `0x1800398b0`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x180012ef4`
- `bcrypt!BCryptExportKey` at `0x180012f9e`
- `bcrypt!BCryptExportKey` at `0x180012ef4`
- `bcrypt!BCryptExportKey` at `0x180012f9e`

## string_xrefs

- `0x180012fda`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180013020`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800130dd`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180013160`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800131af`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18001322c`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall SerializeProperties(__int64 a1, __int64 *a2, unsigned int *a3, unsigned int a4)
{
  int v6; // edx
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned int v9; // r14d
  BCRYPT_KEY_HANDLE *v10; // r15
  const void **v11; // rdi
  int v12; // edx
  int v13; // r8d
  __int64 v14; // r12
  unsigned int v15; // eax
  ULONG v16; // ecx
  __int64 v17; // rdx
  ULONG v18; // r8d
  __int64 v19; // r13
  int v20; // edx
  int v21; // r8d
  __int64 v22; // rax
  void *v24; // rcx
  const WCHAR *v25; // r8
  unsigned int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // eax
  __int64 v31; // rcx
  unsigned int v32; // eax
  _QWORD *v33; // rcx
  unsigned int v34; // ecx
  __int64 v35; // r9
  __int64 v36; // rcx
  int v37; // eax
  int v38; // ecx
  __int64 v39; // rbx
  __int64 v40; // rcx
  unsigned int v41; // ecx
  __int64 v42; // rbx
  __int64 v43; // rdi
  char dwFlags; // [rsp+30h] [rbp-40h]
  ULONG cbOutput; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v46; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v47; // [rsp+48h] [rbp-28h] BYREF
  __int128 v48; // [rsp+50h] [rbp-20h]

  v46 = 0;
  cbOutput = 0;
  v47 = 0;
  v7 = ComputeSerializedPropertyListLength(a1, a4, &v46);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v8,
        (unsigned int)"Status",
        v7,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        69);
    return v7;
  }
  if ( !v6 )
  {
    v10 = (BCRYPT_KEY_HANDLE *)(a1 + 104);
    v24 = *(void **)(a1 + 104);
    if ( v24 )
    {
      v25 = *(const WCHAR **)(*(_QWORD *)(a1 + 64) + 48LL);
      if ( !v25 )
      {
        v7 = -2146893783;
        v27 = 2410;
        v28 = 2148073513LL;
        goto LABEL_25;
      }
      v26 = BCryptExportKey(v24, 0, v25, 0, 0, &cbOutput, 0);
      v7 = v26;
      if ( v26 )
      {
        v27 = 2426;
        v28 = v26;
        goto LABEL_25;
      }
      v9 = v46 + cbOutput + 20;
      if ( v9 < v46 )
      {
        v27 = 2437;
LABEL_24:
        v7 = -2147024362;
        v28 = 2147942934LL;
LABEL_25:
        DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v27);
        return v7;
      }
    }
    else
    {
      v9 = v46;
    }
    v11 = (const void **)(a1 + 512);
    if ( *(_QWORD *)(a1 + 512) && (v34 = v9, v9 += *(_DWORD *)(a1 + 520) + 20, v9 < v34) )
    {
      v27 = 2450;
    }
    else
    {
      v29 = *(_QWORD *)(a1 + 544);
      if ( v29 )
      {
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)(v29 + 2 * v31) );
        v32 = v9;
        v9 += 2 * (v31 + 11);
        if ( v9 < v32 )
        {
          v7 = -2147024362;
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v7;
          dwFlags = -97;
          goto LABEL_41;
        }
      }
      if ( !*(_DWORD *)(a1 + 564) )
        goto LABEL_6;
      v30 = v9;
      v9 += 24;
      if ( v9 >= v30 )
        goto LABEL_6;
      v27 = 2476;
    }
    goto LABEL_24;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 64) + 8LL) == 1 )
  {
    v9 = v46 + 24;
    if ( v46 + 24 >= v46 )
      goto LABEL_5;
    v7 = -2147024362;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    dwFlags = 94;
LABEL_41:
    WPP_SF_sDsd(
      v33[2],
      v6,
      v8,
      (unsigned int)"Status",
      22,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      dwFlags);
    return v7;
  }
  v9 = v46;
LABEL_5:
  v10 = (BCRYPT_KEY_HANDLE *)(a1 + 104);
  v11 = (const void **)(a1 + 512);
LABEL_6:
  v14 = SafeAllocaAllocateFromHeap(v9);
  if ( v14 )
  {
    v15 = BuildSerializedPropertyList(a1, a4, v14, v9, (__int64)&v47);
    v7 = v15;
    if ( v15 )
    {
      v35 = 2509;
      v36 = v15;
    }
    else
    {
      v16 = v9 - v47;
      v17 = v14 + v47;
      if ( a4 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 64) + 8LL) != 1 )
        {
LABEL_17:
          v7 = 0;
          *a2 = v14;
          *a3 = v9;
          return v7;
        }
        v48 = 0x700000018uLL;
        if ( v16 >= 0x18 )
        {
          *(_OWORD *)v17 = v48;
          *(_DWORD *)(v17 + 16) = 4;
          v37 = *(_DWORD *)(a1 + 28);
LABEL_69:
          *(_DWORD *)(v17 + 20) = v37;
          goto LABEL_17;
        }
        v35 = 2533;
      }
      else
      {
        if ( !*v10 )
        {
LABEL_13:
          if ( *v11 )
          {
            v38 = *(_DWORD *)(a1 + 520);
            v39 = v17 + 20;
            *((_QWORD *)&v48 + 1) = 0;
            DWORD1(v48) = 24;
            LODWORD(v48) = v38 + 20;
            *(_OWORD *)v17 = (unsigned __int64)v48;
            *(_DWORD *)(v17 + 16) = v38;
            memcpy_0((void *)(v17 + 20), *v11, *(unsigned int *)(a1 + 520));
            v17 = v39 + *(unsigned int *)(a1 + 520);
          }
          v22 = *(_QWORD *)(a1 + 544);
          if ( v22 )
          {
            v40 = -1;
            do
              ++v40;
            while ( *(_WORD *)(v22 + 2 * v40) );
            v41 = 2 * v40 + 2;
            *((_QWORD *)&v48 + 1) = 0;
            v42 = v41;
            v43 = v17 + 20;
            LODWORD(v48) = v41 + 20;
            DWORD1(v48) = 25;
            *(_OWORD *)v17 = (unsigned __int64)v48;
            *(_DWORD *)(v17 + 16) = v41;
            memcpy_0((void *)(v17 + 20), *(const void **)(a1 + 544), v41);
            v17 = v42 + v43;
          }
          if ( !*(_DWORD *)(a1 + 564) )
            goto LABEL_17;
          v48 = 0x1B00000018uLL;
          *(_OWORD *)v17 = 0x1B00000018uLL;
          *(_DWORD *)(v17 + 16) = 4;
          v37 = *(_DWORD *)(a1 + 564);
          goto LABEL_69;
        }
        v18 = cbOutput;
        *((_QWORD *)&v48 + 1) = 0;
        DWORD1(v48) = 10;
        LODWORD(v48) = cbOutput + 20;
        if ( v16 >= cbOutput + 20 )
        {
          v19 = v17 + 20;
          *(_OWORD *)v17 = v48;
          *(_DWORD *)(v17 + 16) = v18;
          v7 = BCryptExportKey(
                 *v10,
                 0,
                 *(LPCWSTR *)(*(_QWORD *)(a1 + 64) + 48LL),
                 (PUCHAR)(v17 + 20),
                 cbOutput,
                 &cbOutput,
                 0);
          if ( !v7 )
          {
            v17 = v19 + cbOutput;
            goto LABEL_13;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v20,
              v21,
              (unsigned int)"Status",
              v7,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
              25);
LABEL_49:
          MSCryptFree(v14);
          return v7;
        }
        v35 = 2566;
      }
      v7 = -2146893792;
      v36 = 2148073504LL;
    }
    DebugTraceError(v36, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v35);
    goto LABEL_49;
  }
  v7 = -2146893810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v13,
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      188);
  return v7;
}

```

## disassembly

```asm
0x180012ddc  mov     [rsp-38h+arg_0], rbx
0x180012de1  mov     [rsp-38h+arg_10], r8
0x180012de6  mov     [rsp-38h+arg_8], rdx
0x180012deb  push    rbp
0x180012dec  push    rsi
0x180012ded  push    rdi
0x180012dee  push    r12
0x180012df0  push    r13
0x180012df2  push    r14
0x180012df4  push    r15
0x180012df6  mov     rbp, rsp
0x180012df9  sub     rsp, 70h
0x180012dfd  xor     r12d, r12d
0x180012e00  lea     r8, [rbp+var_2C]
0x180012e04  mov     edx, r9d
0x180012e07  mov     [rbp+var_2C], r12d
0x180012e0b  mov     [rbp+var_30], r12d
0x180012e0f  mov     r13d, r9d
0x180012e12  mov     [rbp+var_28], r12d
0x180012e16  mov     rsi, rcx
0x180012e19  call    ComputeSerializedPropertyListLength
0x180012e1e  mov     ebx, eax
0x180012e20  test    eax, eax
0x180012e22  jnz     loc_180013186
0x180012e28  test    edx, edx
0x180012e2a  jz      loc_180012F65
0x180012e30  mov     rax, [rsi+40h]
0x180012e34  cmp     dword ptr [rax+8], 1
0x180012e38  jz      loc_1800130F6
0x180012e3e  mov     r14d, [rbp+var_2C]
0x180012e42  lea     r15, [rsi+68h]
0x180012e46  lea     rdi, [rsi+200h]
0x180012e4d  mov     ecx, r14d
0x180012e50  call    SafeAllocaAllocateFromHeap
0x180012e55  mov     r12, rax
0x180012e58  test    rax, rax
0x180012e5b  jz      loc_180012FF2
0x180012e61  lea     rax, [rbp+var_28]
0x180012e65  mov     r9d, r14d
0x180012e68  mov     r8, r12
0x180012e6b  mov     qword ptr [rsp+70h+cbOutput], rax
0x180012e70  mov     edx, r13d
0x180012e73  mov     rcx, rsi
0x180012e76  call    BuildSerializedPropertyList
0x180012e7b  xor     r9d, r9d
0x180012e7e  mov     ebx, eax
0x180012e80  test    eax, eax
0x180012e82  jnz     loc_18001320B
0x180012e88  mov     edx, [rbp+var_28]
0x180012e8b  mov     ecx, r14d
0x180012e8e  sub     ecx, [rbp+var_28]
0x180012e91  add     rdx, r12
0x180012e94  test    r13d, r13d
0x180012e97  jnz     loc_18001323D
0x180012e9d  cmp     [r15], r9
0x180012ea0  jz      short loc_180012F13
0x180012ea2  mov     r8d, [rbp+var_30]
0x180012ea6  mov     qword ptr [rbp+var_20+8], r9
0x180012eaa  mov     dword ptr [rbp+var_20+4], 0Ah
0x180012eb1  lea     eax, [r8+14h]
0x180012eb5  mov     dword ptr [rbp+var_20], eax
0x180012eb8  cmp     ecx, eax
0x180012eba  jb      loc_180013278
0x180012ec0  movups  xmm0, [rbp+var_20]
0x180012ec4  mov     dword ptr [rsp+70h+dwFlags], r9d; dwFlags
0x180012ec9  lea     rax, [rbp+var_30]
0x180012ecd  lea     r13, [rdx+14h]
0x180012ed1  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180012ed6  movups  xmmword ptr [rdx], xmm0
0x180012ed9  mov     [rdx+10h], r8d
0x180012edd  mov     r9, r13; pbOutput
0x180012ee0  mov     r8, [rsi+40h]
0x180012ee4  xor     edx, edx; hExportKey
0x180012ee6  mov     eax, [rbp+var_30]
0x180012ee9  mov     rcx, [r15]; hKey
0x180012eec  mov     [rsp+70h+cbOutput], eax; cbOutput
0x180012ef0  mov     r8, [r8+30h]; pszBlobType
0x180012ef4  call    cs:__imp_BCryptExportKey
0x180012efb  nop     dword ptr [rax+rax+00h]
0x180012f00  xor     r9d, r9d
0x180012f03  mov     ebx, eax
0x180012f05  test    eax, eax
0x180012f07  jnz     loc_180013136
0x180012f0d  mov     edx, [rbp+var_30]
0x180012f10  add     rdx, r13
0x180012f13  cmp     [rdi], r9
0x180012f16  jnz     loc_180013280
0x180012f1c  mov     rax, [rsi+220h]
0x180012f23  test    rax, rax
0x180012f26  jnz     loc_1800132C8
0x180012f2c  cmp     [rsi+234h], r9d
0x180012f33  jnz     loc_18001331C
0x180012f39  mov     rax, [rbp+arg_8]
0x180012f3d  mov     ebx, r9d
0x180012f40  mov     [rax], r12
0x180012f43  mov     rax, [rbp+arg_10]
0x180012f47  mov     [rax], r14d
0x180012f4a  mov     eax, ebx
0x180012f4c  mov     rbx, [rsp+70h+arg_0]
0x180012f54  add     rsp, 70h
0x180012f58  pop     r15
0x180012f5a  pop     r14
0x180012f5c  pop     r13
0x180012f5e  pop     r12
0x180012f60  pop     rdi
0x180012f61  pop     rsi
0x180012f62  pop     rbp
0x180012f63  retn
0x180012f65  lea     r15, [rsi+68h]
0x180012f69  mov     rcx, [r15]; hKey
0x180012f6c  test    rcx, rcx
0x180012f6f  jz      loc_180013049
0x180012f75  mov     rax, [rsi+40h]
0x180012f79  mov     r8, [rax+30h]; pszBlobType
0x180012f7d  test    r8, r8
0x180012f80  jz      loc_1800131E9
0x180012f86  lea     rax, [rbp+var_30]
0x180012f8a  mov     dword ptr [rsp+70h+dwFlags], r12d; dwFlags
0x180012f8f  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180012f94  xor     r9d, r9d; pbOutput
0x180012f97  xor     edx, edx; hExportKey
0x180012f99  mov     [rsp+70h+cbOutput], r12d; cbOutput
0x180012f9e  call    cs:__imp_BCryptExportKey
0x180012fa5  nop     dword ptr [rax+rax+00h]
0x180012faa  mov     ebx, eax
0x180012fac  test    eax, eax
0x180012fae  jnz     loc_1800131FE
0x180012fb4  mov     r14d, [rbp+var_30]
0x180012fb8  add     r14d, 14h
0x180012fbc  add     r14d, [rbp+var_2C]
0x180012fc0  cmp     r14d, [rbp+var_2C]
0x180012fc4  jnb     loc_18001304D
0x180012fca  mov     r9d, 985h
0x180012fd0  mov     ebx, 80070216h
0x180012fd5  mov     ecx, 80070216h
0x180012fda  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012fe1  lea     rdx, aStatus; "Status"
0x180012fe8  call    DebugTraceError
0x180012fed  jmp     loc_180012F4A
0x180012ff2  mov     ebx, 8009000Eh
0x180012ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ffe  lea     rax, WPP_GLOBAL_Control
0x180013005  cmp     rcx, rax
0x180013008  jz      loc_180012F4A
0x18001300e  test    byte ptr [rcx+1Ch], 1
0x180013012  jz      loc_180012F4A
0x180013018  mov     dword ptr [rsp+70h+dwFlags], 9BCh
0x180013020  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013027  mov     [rsp+70h+pcbResult], rax
0x18001302c  mov     [rsp+70h+cbOutput], 8009000Eh
0x180013034  mov     rcx, [rcx+10h]
0x180013038  lea     r9, aStatus; "Status"
0x18001303f  call    WPP_SF_sDsd
0x180013044  jmp     loc_180012F4A
0x180013049  mov     r14d, [rbp+var_2C]
0x18001304d  lea     rdi, [rsi+200h]
0x180013054  cmp     [rdi], r12
0x180013057  jnz     loc_1800131C4
0x18001305d  mov     rax, [rsi+220h]
0x180013064  test    rax, rax
0x180013067  jnz     short loc_180013091
0x180013069  cmp     [rsi+234h], r12d
0x180013070  jz      loc_180012E4D
0x180013076  mov     eax, r14d
0x180013079  add     r14d, 18h
0x18001307d  cmp     r14d, eax
0x180013080  jnb     loc_180012E4D
0x180013086  mov     r9d, 9ACh
0x18001308c  jmp     loc_180012FD0
0x180013091  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013095  inc     rcx
0x180013098  cmp     [rax+rcx*2], r12w
0x18001309d  jnz     short loc_180013095
0x18001309f  mov     eax, r14d
0x1800130a2  lea     r14d, [rcx+0Bh]
0x1800130a6  lea     r14d, [rax+r14*2]
0x1800130aa  cmp     r14d, eax
0x1800130ad  jnb     short loc_180013069
0x1800130af  mov     ebx, 80070216h
0x1800130b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130bb  lea     rax, WPP_GLOBAL_Control
0x1800130c2  cmp     rcx, rax
0x1800130c5  jz      loc_180012F4A
0x1800130cb  test    byte ptr [rcx+1Ch], 1
0x1800130cf  jz      loc_180012F4A
0x1800130d5  mov     dword ptr [rsp+70h+dwFlags], 99Fh
0x1800130dd  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800130e4  mov     [rsp+70h+pcbResult], rax
0x1800130e9  mov     [rsp+70h+cbOutput], 80070216h
0x1800130f1  jmp     loc_180013034
0x1800130f6  mov     eax, [rbp+var_2C]
0x1800130f9  lea     r14d, [rax+18h]
0x1800130fd  cmp     r14d, eax
0x180013100  jnb     loc_180012E42
0x180013106  mov     ebx, 80070216h
0x18001310b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013112  lea     rax, WPP_GLOBAL_Control
0x180013119  cmp     rcx, rax
0x18001311c  jz      loc_180012F4A
0x180013122  test    byte ptr [rcx+1Ch], 1
0x180013126  jz      loc_180012F4A
0x18001312c  mov     dword ptr [rsp+70h+dwFlags], 95Eh
0x180013134  jmp     short loc_1800130DD
0x180013136  mov     rcx, cs:WPP_GLOBAL_Control
0x18001313d  lea     rax, WPP_GLOBAL_Control
0x180013144  cmp     rcx, rax
0x180013147  jz      short loc_18001314F
0x180013149  test    byte ptr [rcx+1Ch], 1
0x18001314d  jnz     short loc_18001315C
0x18001314f  mov     rcx, r12
0x180013152  call    MSCryptFree
0x180013157  jmp     loc_180012F4A
0x18001315c  mov     rcx, [rcx+10h]
0x180013160  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013167  mov     dword ptr [rsp+70h+dwFlags], 0A19h
0x18001316f  lea     r9, aStatus; "Status"
0x180013176  mov     [rsp+70h+pcbResult], rax
0x18001317b  mov     [rsp+70h+cbOutput], ebx
0x18001317f  call    WPP_SF_sDsd
0x180013184  jmp     short loc_18001314F
0x180013186  mov     rcx, cs:WPP_GLOBAL_Control
0x18001318d  lea     rax, WPP_GLOBAL_Control
0x180013194  cmp     rcx, rax
0x180013197  jz      loc_180012F4A
0x18001319d  test    byte ptr [rcx+1Ch], 1
0x1800131a1  jz      loc_180012F4A
0x1800131a7  mov     dword ptr [rsp+70h+dwFlags], 945h
0x1800131af  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800131b6  mov     [rsp+70h+pcbResult], rax
0x1800131bb  mov     [rsp+70h+cbOutput], ebx
0x1800131bf  jmp     loc_180013034
0x1800131c4  mov     ecx, r14d
0x1800131c7  mov     r14d, [rsi+208h]
0x1800131ce  add     r14d, 14h
0x1800131d2  add     r14d, ecx
0x1800131d5  cmp     r14d, ecx
0x1800131d8  jnb     loc_18001305D
0x1800131de  mov     r9d, 992h
0x1800131e4  jmp     loc_180012FD0
0x1800131e9  mov     ebx, 80090029h
0x1800131ee  mov     r9d, 96Ah
0x1800131f4  mov     ecx, 80090029h
0x1800131f9  jmp     loc_180012FDA
0x1800131fe  mov     r9d, 97Ah
0x180013204  mov     ecx, eax
0x180013206  jmp     loc_180012FDA
0x18001320b  mov     r9d, 9CDh
0x180013211  mov     ecx, eax
0x180013213  jmp     short loc_180013225
0x180013215  mov     r9d, 9E5h
0x18001321b  mov     ebx, 80090020h
0x180013220  mov     ecx, 80090020h
0x180013225  lea     rdx, aStatus; "Status"
0x18001322c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013233  call    DebugTraceError
0x180013238  jmp     loc_18001314F
0x18001323d  mov     rax, [rsi+40h]
0x180013241  cmp     dword ptr [rax+8], 1
0x180013245  jnz     loc_180012F39
0x18001324b  mov     qword ptr [rbp+var_20+8], r9
0x18001324f  mov     dword ptr [rbp+var_20], 18h
0x180013256  mov     dword ptr [rbp+var_20+4], 7
0x18001325d  cmp     ecx, 18h
0x180013260  jb      short loc_180013215
0x180013262  movups  xmm0, [rbp+var_20]
0x180013266  movups  xmmword ptr [rdx], xmm0
0x180013269  mov     dword ptr [rdx+10h], 4
0x180013270  mov     eax, [rsi+1Ch]
0x180013273  jmp     loc_180013342
0x180013278  mov     r9d, 0A06h
0x18001327e  jmp     short loc_18001321B
0x180013280  mov     ecx, [rsi+208h]
0x180013286  lea     rbx, [rdx+14h]
0x18001328a  mov     qword ptr [rbp+var_20+8], r9
0x18001328e  mov     dword ptr [rbp+var_20+4], 18h
0x180013295  lea     eax, [rcx+14h]
0x180013298  mov     dword ptr [rbp+var_20], eax
0x18001329b  movups  xmm0, [rbp+var_20]
0x18001329f  movups  xmmword ptr [rdx], xmm0
0x1800132a2  mov     [rdx+10h], ecx
0x1800132a5  mov     rcx, rbx; void *
0x1800132a8  mov     r8d, [rsi+208h]; Size
0x1800132af  mov     rdx, [rdi]; Src
0x1800132b2  call    memcpy_0
0x1800132b7  mov     edx, [rsi+208h]
0x1800132bd  add     rdx, rbx
0x1800132c0  xor     r9d, r9d
0x1800132c3  jmp     loc_180012F1C
0x1800132c8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800132cc  inc     rcx
0x1800132cf  cmp     [rax+rcx*2], r9w
0x1800132d4  jnz     short loc_1800132CC
0x1800132d6  lea     ecx, ds:2[rcx*2]
0x1800132dd  mov     qword ptr [rbp+var_20+8], r9
0x1800132e1  lea     eax, [rcx+14h]
0x1800132e4  mov     ebx, ecx
0x1800132e6  lea     rdi, [rdx+14h]
0x1800132ea  mov     dword ptr [rbp+var_20], eax
0x1800132ed  mov     r8d, ecx; Size
0x1800132f0  mov     dword ptr [rbp+var_20+4], 19h
  ... truncated ...
```
