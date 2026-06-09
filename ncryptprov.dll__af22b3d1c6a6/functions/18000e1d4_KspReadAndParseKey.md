# KspReadAndParseKey

- ea: `0x18000e1d4`
- end: `0x18000e602`
- name: `KspReadAndParseKey`
- size: `1070`
- prototype: `__int64 __fastcall(__int64, _WORD *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c7b0`
- `0x1800351c8`

## callees

- `0x180005290`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000e1d4`
- `0x18000ed10`
- `0x18000f8e8`
- `0x180011548`
- `0x180011678`
- `0x180047124`
- `0x180051e8c`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x18000e471`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000e471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5f1`

## string_xrefs

- `0x18000e1f9`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e2fa`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e331`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e3cc`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e4aa`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e50a`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e577`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000e5ad`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall KspReadAndParseKey(__int64 a1, _WORD *a2, unsigned int a3, __int64 a4)
{
  void *v4; // r14
  __int64 v7; // rsi
  __int64 v8; // r10
  _WORD *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // r13d
  void *v14; // rdi
  int v15; // ebx
  int KeyFromStore; // eax
  int v17; // edx
  int v18; // r8d
  BOOL v19; // r12d
  unsigned int v20; // eax
  int v21; // edx
  int v22; // r8d
  PVOID *v23; // rcx
  unsigned int v24; // eax
  bool v26; // zf
  unsigned int KeyFromMemoryStore; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // r12d
  unsigned int v31; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-24h] BYREF
  __int64 v33; // [rsp+58h] [rbp-20h] BYREF
  void *v34; // [rsp+60h] [rbp-18h] BYREF
  void *v35; // [rsp+68h] [rbp-10h] BYREF
  BOOL v39; // [rsp+D8h] [rbp+60h]

  v4 = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v7 = 0;
  if ( a4 && (v8 = *(_QWORD *)(a4 + 8)) != 0 )
  {
    v9 = *(_WORD **)(a4 + 8);
    v10 = 0x7FFFFFFF;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v10;
    }
    while ( v10 );
    v11 = v10 == 0 ? 0x80070057 : 0;
    if ( !v10 )
      goto LABEL_30;
    if ( ((0x7FFFFFFF - v10) & (unsigned __int64)-(__int64)(v10 != 0)) <= 0xE
      || (v26 = (unsigned int)RtlCompareUnicodeStrings(v8, 14, L"\\\\~\\EPHEMERAL\\") == 0, v12 = 1, !v26) )
    {
      v12 = 0;
    }
    v13 = 0;
    if ( v12 == 1 )
    {
      KeyFromMemoryStore = ReadKeyFromMemoryStore(a4);
      v11 = KeyFromMemoryStore;
      if ( KeyFromMemoryStore )
      {
        DebugTraceError(
          KeyFromMemoryStore,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          1882);
        return v11;
      }
      goto LABEL_20;
    }
  }
  else
  {
    v13 = 0;
  }
  v39 = 0;
  v14 = 0;
  v34 = 0;
  v35 = 0;
  if ( !a3 )
  {
LABEL_11:
    v15 = 0;
    KeyFromStore = ReadKeyFromStore(a4, a3, a2);
    v19 = KeyFromStore == 0;
    if ( KeyFromStore )
    {
      v11 = ReadLegacyKeyFile(a1, a4, a3, a2, &v32, &v33, &v31);
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            v18,
            (unsigned int)"Status",
            v11,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
            242);
        v7 = v33;
LABEL_13:
        if ( !a3 )
          goto LABEL_14;
        goto LABEL_52;
      }
      v7 = v33;
      v15 = 1;
    }
    v13 = v15;
    v39 = v19;
    v11 = 0;
    goto LABEL_13;
  }
  v28 = ChangeThreadILToMedium(&v34, &v35);
  v11 = v28;
  if ( !v28 )
  {
    v14 = v34;
    v4 = v35;
    goto LABEL_11;
  }
  DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 1738);
  v14 = v34;
  v4 = v35;
LABEL_52:
  v29 = RevertBackToCallerToken(v14);
  v30 = v29;
  if ( v29 )
  {
    DebugTraceError(v29, "RevertStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 1799);
    if ( !v11 )
      v11 = v30;
  }
LABEL_14:
  if ( v4 )
    CloseHandle(v4);
  if ( v14 )
    CloseHandle(v14);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v18,
        (unsigned int)"Status",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        115);
    goto LABEL_30;
  }
  if ( !v39 )
  {
    if ( v13 )
    {
      v24 = ParseLegacyKeyFile(a4, v32, v7, v31, 1);
      v11 = v24;
      if ( v24 )
      {
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            v22,
            (unsigned int)"Status",
            v24,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
            152);
          v23 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_24;
      }
    }
    goto LABEL_29;
  }
LABEL_20:
  v20 = ParseKeyFile(a4);
  v11 = v20;
  if ( v20 )
  {
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        v22,
        (unsigned int)"Status",
        v20,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        132);
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_24:
    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v23[2],
        v21,
        v22,
        (unsigned int)"Status",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        131);
    goto LABEL_30;
  }
LABEL_29:
  v11 = 0;
LABEL_30:
  if ( v7 )
    MSCryptFree(v7);
  return v11;
}

```

## disassembly

```asm
0x18000e1d4  mov     [rsp-40h+arg_10], r8d
0x18000e1d9  mov     [rsp-40h+arg_8], rdx
0x18000e1de  mov     [rsp-40h+arg_0], rcx
0x18000e1e3  push    rbp
0x18000e1e4  push    rbx
0x18000e1e5  push    rsi
0x18000e1e6  push    rdi
0x18000e1e7  push    r12
0x18000e1e9  push    r13
0x18000e1eb  push    r14
0x18000e1ed  push    r15
0x18000e1ef  mov     rbp, rsp
0x18000e1f2  sub     rsp, 78h
0x18000e1f6  xor     r14d, r14d
0x18000e1f9  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e200  mov     [rbp+var_20], r14
0x18000e204  mov     r15, r9
0x18000e207  mov     [rbp+var_28], r14d
0x18000e20b  mov     r12d, r8d
0x18000e20e  mov     [rbp+var_24], r14d
0x18000e212  mov     esi, r14d
0x18000e215  test    r9, r9
0x18000e218  jz      loc_18000E457
0x18000e21e  mov     r10, [r9+8]
0x18000e222  test    r10, r10
0x18000e225  jz      loc_18000E457
0x18000e22b  mov     edx, 7FFFFFFFh
0x18000e230  mov     rax, r10
0x18000e233  mov     ecx, edx
0x18000e235  cmp     [rax], r14w
0x18000e239  jz      short loc_18000E245
0x18000e23b  add     rax, 2
0x18000e23f  sub     rcx, 1
0x18000e243  jnz     short loc_18000E235
0x18000e245  mov     rax, rcx
0x18000e248  neg     rax
0x18000e24b  mov     rax, rcx
0x18000e24e  sbb     ebx, ebx
0x18000e250  sub     rdx, rcx
0x18000e253  not     ebx
0x18000e255  and     ebx, 80070057h
0x18000e25b  neg     rax
0x18000e25e  sbb     r8, r8
0x18000e261  and     r8, rdx
0x18000e264  test    rcx, rcx
0x18000e267  jz      loc_18000E392
0x18000e26d  mov     edx, 0Eh
0x18000e272  cmp     r8, rdx
0x18000e275  ja      loc_18000E45F
0x18000e27b  mov     eax, r14d
0x18000e27e  mov     r13d, r14d
0x18000e281  cmp     eax, 1
0x18000e284  jz      loc_18000E530
0x18000e28a  mov     [rbp+arg_18], r14d
0x18000e28e  mov     rdi, r14
0x18000e291  mov     [rbp+var_18], r14
0x18000e295  mov     [rbp+var_10], r14
0x18000e299  test    r12d, r12d
0x18000e29c  jnz     loc_18000E55E
0x18000e2a2  mov     r8, [rbp+arg_8]
0x18000e2a6  mov     edx, r12d
0x18000e2a9  mov     rcx, r15
0x18000e2ac  xor     ebx, ebx
0x18000e2ae  call    ReadKeyFromStore
0x18000e2b3  xor     r12d, r12d
0x18000e2b6  test    eax, eax
0x18000e2b8  setz    r12b
0x18000e2bc  test    eax, eax
0x18000e2be  jnz     loc_18000E3E5
0x18000e2c4  mov     r13d, ebx
0x18000e2c7  mov     [rbp+arg_18], r12d
0x18000e2cb  xor     ebx, ebx
0x18000e2cd  cmp     [rbp+arg_10], 0
0x18000e2d1  jnz     loc_18000E594
0x18000e2d7  test    r14, r14
0x18000e2da  jnz     loc_18000E5DA
0x18000e2e0  xor     r14d, r14d
0x18000e2e3  test    rdi, rdi
0x18000e2e6  jnz     loc_18000E5EE
0x18000e2ec  test    ebx, ebx
0x18000e2ee  jnz     loc_18000E3B3
0x18000e2f4  cmp     [rbp+arg_18], r14d
0x18000e2f8  jz      short loc_18000E366
0x18000e2fa  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e301  mov     edx, 1
0x18000e306  mov     rcx, r15
0x18000e309  call    ParseKeyFile
0x18000e30e  mov     ebx, eax
0x18000e310  test    eax, eax
0x18000e312  jz      short loc_18000E38F
0x18000e314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e31b  lea     r15, WPP_GLOBAL_Control
0x18000e322  cmp     rcx, r15
0x18000e325  jz      short loc_18000E331
0x18000e327  test    byte ptr [rcx+1Ch], 1
0x18000e32b  jnz     loc_18000E42A
0x18000e331  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e338  cmp     rcx, r15
0x18000e33b  jz      short loc_18000E392
0x18000e33d  test    byte ptr [rcx+1Ch], 1
0x18000e341  jz      short loc_18000E392
0x18000e343  mov     dword ptr [rsp+78h+var_48], 783h
0x18000e34b  mov     [rsp+78h+var_50], rdi
0x18000e350  mov     rcx, [rcx+10h]
0x18000e354  lea     r9, aStatus; "Status"
0x18000e35b  mov     dword ptr [rsp+78h+var_58], ebx
0x18000e35f  call    WPP_SF_sDsd
0x18000e364  jmp     short loc_18000E392
0x18000e366  test    r13d, r13d
0x18000e369  jz      short loc_18000E38F
0x18000e36b  mov     r9d, [rbp+var_28]
0x18000e36f  mov     r8, rsi
0x18000e372  mov     edx, [rbp+var_24]
0x18000e375  mov     rcx, r15
0x18000e378  mov     dword ptr [rsp+78h+var_58], 1
0x18000e380  call    ParseLegacyKeyFile
0x18000e385  mov     ebx, eax
0x18000e387  test    eax, eax
0x18000e389  jnz     loc_18000E48F
0x18000e38f  mov     ebx, r14d
0x18000e392  test    rsi, rsi
0x18000e395  jz      short loc_18000E39F
0x18000e397  mov     rcx, rsi
0x18000e39a  call    MSCryptFree
0x18000e39f  mov     eax, ebx
0x18000e3a1  add     rsp, 78h
0x18000e3a5  pop     r15
0x18000e3a7  pop     r14
0x18000e3a9  pop     r13
0x18000e3ab  pop     r12
0x18000e3ad  pop     rdi
0x18000e3ae  pop     rsi
0x18000e3af  pop     rbx
0x18000e3b0  pop     rbp
0x18000e3b1  retn
0x18000e3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3ba  lea     rax, WPP_GLOBAL_Control
0x18000e3c1  cmp     rcx, rax
0x18000e3c4  jz      short loc_18000E392
0x18000e3c6  test    byte ptr [rcx+1Ch], 1
0x18000e3ca  jz      short loc_18000E392
0x18000e3cc  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e3d3  mov     dword ptr [rsp+78h+var_48], 773h
0x18000e3db  mov     [rsp+78h+var_50], rax
0x18000e3e0  jmp     loc_18000E350
0x18000e3e5  mov     r9, [rbp+arg_8]
0x18000e3e9  lea     rax, [rbp+var_28]
0x18000e3ed  mov     r8d, [rbp+arg_10]
0x18000e3f1  mov     rdx, r15
0x18000e3f4  mov     rcx, [rbp+arg_0]
0x18000e3f8  mov     [rsp+78h+var_48], rax
0x18000e3fd  lea     rax, [rbp+var_20]
0x18000e401  mov     [rsp+78h+var_50], rax
0x18000e406  lea     rax, [rbp+var_24]
0x18000e40a  mov     [rsp+78h+var_58], rax
0x18000e40f  call    ReadLegacyKeyFile
0x18000e414  mov     ebx, eax
0x18000e416  test    eax, eax
0x18000e418  jnz     loc_18000E4E4
0x18000e41e  mov     rsi, [rbp+var_20]
0x18000e422  lea     ebx, [rax+1]
0x18000e425  jmp     loc_18000E2C4
0x18000e42a  mov     rcx, [rcx+10h]
0x18000e42e  lea     r9, aStatus; "Status"
0x18000e435  mov     dword ptr [rsp+78h+var_48], 684h
0x18000e43d  mov     [rsp+78h+var_50], rdi
0x18000e442  mov     dword ptr [rsp+78h+var_58], eax
0x18000e446  call    WPP_SF_sDsd
0x18000e44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e452  jmp     loc_18000E331
0x18000e457  mov     r13d, r14d
0x18000e45a  jmp     loc_18000E28A
0x18000e45f  mov     r9, rdx
0x18000e462  mov     byte ptr [rsp+78h+var_58], r14b
0x18000e467  lea     r8, aEphemeral; "\\\\~\\EPHEMERAL\\"
0x18000e46e  mov     rcx, r10
0x18000e471  call    cs:__imp_RtlCompareUnicodeStrings
0x18000e478  nop     dword ptr [rax+rax+00h]
0x18000e47d  test    eax, eax
0x18000e47f  mov     eax, 1
0x18000e484  jz      loc_18000E27E
0x18000e48a  jmp     loc_18000E27B
0x18000e48f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e496  lea     r15, WPP_GLOBAL_Control
0x18000e49d  cmp     rcx, r15
0x18000e4a0  jz      loc_18000E331
0x18000e4a6  test    byte ptr [rcx+1Ch], 1
0x18000e4aa  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e4b1  jz      loc_18000E338
0x18000e4b7  mov     rcx, [rcx+10h]
0x18000e4bb  lea     r9, aStatus; "Status"
0x18000e4c2  mov     dword ptr [rsp+78h+var_48], 698h
0x18000e4ca  mov     [rsp+78h+var_50], rdi
0x18000e4cf  mov     dword ptr [rsp+78h+var_58], eax
0x18000e4d3  call    WPP_SF_sDsd
0x18000e4d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4df  jmp     loc_18000E338
0x18000e4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4eb  lea     rax, WPP_GLOBAL_Control
0x18000e4f2  cmp     rcx, rax
0x18000e4f5  jz      short loc_18000E4FD
0x18000e4f7  test    byte ptr [rcx+1Ch], 1
0x18000e4fb  jnz     short loc_18000E506
0x18000e4fd  mov     rsi, [rbp+var_20]
0x18000e501  jmp     loc_18000E2CD
0x18000e506  mov     rcx, [rcx+10h]
0x18000e50a  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e511  mov     dword ptr [rsp+78h+var_48], 6F2h
0x18000e519  lea     r9, aStatus; "Status"
0x18000e520  mov     [rsp+78h+var_50], rax
0x18000e525  mov     dword ptr [rsp+78h+var_58], ebx
0x18000e529  call    WPP_SF_sDsd
0x18000e52e  jmp     short loc_18000E4FD
0x18000e530  mov     rcx, r15
0x18000e533  call    ReadKeyFromMemoryStore
0x18000e538  mov     ebx, eax
0x18000e53a  test    eax, eax
0x18000e53c  jz      loc_18000E301
0x18000e542  mov     r9d, 75Ah
0x18000e548  lea     rdx, aStatus; "Status"
0x18000e54f  mov     r8, rdi
0x18000e552  mov     ecx, eax
0x18000e554  call    DebugTraceError
0x18000e559  jmp     loc_18000E39F
0x18000e55e  lea     rdx, [rbp+var_10]
0x18000e562  lea     rcx, [rbp+var_18]
0x18000e566  call    ChangeThreadILToMedium
0x18000e56b  mov     ebx, eax
0x18000e56d  test    eax, eax
0x18000e56f  jz      short loc_18000E5CD
0x18000e571  mov     r9d, 6CAh
0x18000e577  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e57e  lea     rdx, aStatus; "Status"
0x18000e585  mov     ecx, eax
0x18000e587  call    DebugTraceError
0x18000e58c  mov     rdi, [rbp+var_18]
0x18000e590  mov     r14, [rbp+var_10]
0x18000e594  mov     rcx, rdi
0x18000e597  call    RevertBackToCallerToken
0x18000e59c  mov     r12d, eax
0x18000e59f  test    eax, eax
0x18000e5a1  jz      loc_18000E2D7
0x18000e5a7  mov     r9d, 707h
0x18000e5ad  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e5b4  lea     rdx, aRevertstatus; "RevertStatus"
0x18000e5bb  mov     ecx, eax
0x18000e5bd  call    DebugTraceError
0x18000e5c2  test    ebx, ebx
0x18000e5c4  cmovz   ebx, r12d
0x18000e5c8  jmp     loc_18000E2D7
0x18000e5cd  mov     rdi, [rbp+var_18]
0x18000e5d1  mov     r14, [rbp+var_10]
0x18000e5d5  jmp     loc_18000E2A2
0x18000e5da  mov     rcx, r14; hObject
0x18000e5dd  call    cs:__imp_CloseHandle
0x18000e5e4  nop     dword ptr [rax+rax+00h]
0x18000e5e9  jmp     loc_18000E2E0
0x18000e5ee  mov     rcx, rdi; hObject
0x18000e5f1  call    cs:__imp_CloseHandle
0x18000e5f8  nop     dword ptr [rax+rax+00h]
0x18000e5fd  jmp     loc_18000E2EC
```
