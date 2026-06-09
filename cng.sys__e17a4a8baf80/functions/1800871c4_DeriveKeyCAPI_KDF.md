# DeriveKeyCAPI_KDF

- ea: `0x1800871c4`
- end: `0x1800874ab`
- name: `DeriveKeyCAPI_KDF`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180043e70`

## callees

- `0x18000c650`
- `0x18000e090`
- `0x18000e440`
- `0x18000f2f4`
- `0x18000f6b0`
- `0x180010590`
- `0x18001155c`
- `0x18003b290`
- `0x1800441e0`
- `0x180045a00`
- `0x1800871c4`
- `0x180087c38`
- `0x1800a45c0`

## string_xrefs

- `0x1800872a7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180087311`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180087436`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyCAPI_KDF(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6)
{
  __int64 v8; // rdi
  _BYTE *v9; // rsi
  wchar_t *v10; // r14
  __int64 v11; // r9
  int ParameterList; // eax
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // r15
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  unsigned __int64 v18; // r12
  size_t v19; // r13
  wchar_t *v20; // rax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  unsigned int HashProperty; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned int v26; // r15d
  __int64 v27; // rax
  _BYTE *v28; // rdx
  size_t Size; // [rsp+30h] [rbp-38h]
  int v31; // [rsp+40h] [rbp-28h]
  unsigned int v32; // [rsp+44h] [rbp-24h] BYREF
  int v33[2]; // [rsp+48h] [rbp-20h] BYREF
  int v34[2]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v37; // [rsp+C0h] [rbp+58h]
  unsigned int v38; // [rsp+C8h] [rbp+60h]

  v38 = a4;
  v37 = a3;
  *(_QWORD *)v33 = 0;
  *(_QWORD *)v34 = 0;
  v8 = 0;
  LODWORD(v36) = 0;
  v9 = 0;
  v32 = 0;
  v10 = 0;
  if ( !a2 )
  {
    v11 = 1434;
LABEL_28:
    v21 = -1073741811;
    v25 = 3221225485LL;
    goto LABEL_29;
  }
  if ( (a6 & 0xFFFFFFEF) != 0 )
  {
    v11 = 1441;
    goto LABEL_28;
  }
  *a5 = 0;
  ParameterList = QueryParameterList(a2, 0, 0);
  if ( ParameterList < 0 )
  {
    v11 = 1467;
    goto LABEL_28;
  }
  v13 = *(_DWORD *)(a1 + 32);
  v31 = v13;
  _mm_lfence();
  v14 = *(_QWORD *)(a2 + 8);
  v15 = 2LL * ParameterList;
  v16 = *(_DWORD *)(v14 + 16LL * ParameterList);
  if ( (v16 & 1) != 0 || v16 < 2 )
  {
    v11 = 1478;
    goto LABEL_28;
  }
  v17 = *(const wchar_t **)(v14 + 8 * v15 + 8);
  v18 = (unsigned __int64)v16 >> 1;
  v19 = v16;
  if ( v17[v18 - 1] )
  {
    v20 = (wchar_t *)MSCryptAlloc(v16 + 2LL, v17);
    v10 = v20;
    if ( !v20 )
    {
      v21 = -1073741801;
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        1493);
      goto LABEL_30;
    }
    memmove(v20, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v15 + 8), v19);
    v13 = v31;
    v10[v18] = 0;
    v17 = v10;
  }
  v22 = MSCryptOpenHashProvider((__int64 *)v34, v17, (unsigned int)(v13 != 0) + 32);
  v21 = v22;
  if ( v22 )
  {
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1517);
    v8 = *(_QWORD *)v34;
    goto LABEL_30;
  }
  v8 = *(_QWORD *)v34;
  HashProperty = MSCryptGetHashProperty(*(_DWORD **)v34, L"ObjectLength", &v36, 4u, &v32, 0);
  v21 = HashProperty;
  if ( HashProperty )
  {
    v11 = 1531;
  }
  else
  {
    v9 = (_BYTE *)MSCryptAlloc((unsigned int)v36, v24);
    if ( !v9 )
    {
      v21 = -1073741801;
      v11 = 1539;
      v25 = 3221225495LL;
      goto LABEL_29;
    }
    LODWORD(Size) = 0;
    HashProperty = MSCryptCreateMultiHash(v8, (int)v33, 0, (int)v9, v36, 0, Size, 0);
    v21 = HashProperty;
    if ( HashProperty )
    {
      v11 = 1555;
    }
    else
    {
      HashProperty = MSCryptHashData(*(__int64 *)v33, *(_QWORD *)(a1 + 24), *(_DWORD *)(a1 + 16), 0);
      v21 = HashProperty;
      if ( HashProperty )
      {
        v11 = 1566;
      }
      else
      {
        v26 = v38;
        HashProperty = CapiKDF(*(_QWORD *)v33, v37, v38, a6);
        v21 = HashProperty;
        if ( !HashProperty )
        {
          v21 = 0;
          *a5 = v26;
          goto LABEL_30;
        }
        v11 = 1578;
      }
    }
  }
  v25 = HashProperty;
LABEL_29:
  DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v11);
LABEL_30:
  if ( *(_QWORD *)v33 )
    MSCryptDestroyHash();
  if ( v9 )
  {
    v27 = (unsigned int)v36;
    v28 = v9;
    if ( (_DWORD)v36 )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
    }
    MSCryptFree(v9);
  }
  if ( v8 )
    MSCryptCloseHashProvider(v8, 0);
  if ( v10 )
    MSCryptFree(v10);
  return v21;
}

```

## disassembly

```asm
0x1800871c4  mov     [rsp-40h+arg_18], r9d
0x1800871c9  mov     [rsp-40h+arg_10], r8
0x1800871ce  mov     [rsp-40h+arg_0], rcx
0x1800871d3  push    rbp
0x1800871d4  push    rbx
0x1800871d5  push    rsi
0x1800871d6  push    rdi
0x1800871d7  push    r12
0x1800871d9  push    r13
0x1800871db  push    r14
0x1800871dd  push    r15
0x1800871df  mov     rbp, rsp
0x1800871e2  sub     rsp, 68h
0x1800871e6  xor     r12d, r12d
0x1800871e9  mov     rbx, rdx
0x1800871ec  mov     qword ptr [rbp+var_20], r12
0x1800871f0  mov     r15, rcx
0x1800871f3  mov     qword ptr [rbp+var_18], r12
0x1800871f7  mov     edi, r12d
0x1800871fa  mov     dword ptr [rbp+arg_8], r12d
0x1800871fe  mov     esi, r12d
0x180087201  mov     [rbp+var_24], r12d
0x180087205  mov     r14d, r12d
0x180087208  test    rdx, rdx
0x18008720b  jnz     short loc_180087218
0x18008720d  mov     r9d, 59Ah
0x180087213  jmp     loc_18008742C
0x180087218  test    [rbp+arg_28], 0FFFFFFEFh
0x18008721f  jz      short loc_18008722C
0x180087221  mov     r9d, 5A1h
0x180087227  jmp     loc_18008742C
0x18008722c  mov     rax, [rbp+arg_20]
0x180087230  xor     r8d, r8d
0x180087233  xor     edx, edx
0x180087235  mov     rcx, rbx
0x180087238  mov     [rax], r12d
0x18008723b  call    QueryParameterList
0x180087240  test    eax, eax
0x180087242  jns     short loc_18008724F
0x180087244  mov     r9d, 5BBh
0x18008724a  jmp     loc_18008742C
0x18008724f  mov     ecx, [r15+20h]
0x180087253  mov     [rbp+var_28], ecx
0x180087256  lfence
0x180087259  mov     rdx, [rbx+8]
0x18008725d  movsxd  r15, eax
0x180087260  add     r15, r15
0x180087263  mov     eax, [rdx+r15*8]
0x180087267  test    al, 1
0x180087269  jnz     loc_180087426
0x18008726f  cmp     eax, 2
0x180087272  jb      loc_180087426
0x180087278  mov     rdx, [rdx+r15*8+8]
0x18008727d  mov     r12d, eax
0x180087280  shr     r12, 1
0x180087283  mov     r13d, eax
0x180087286  xor     eax, eax
0x180087288  cmp     ax, [rdx+r12*2-2]
0x18008728e  jz      short loc_1800872ED
0x180087290  lea     rcx, [r13+2]
0x180087294  call    MSCryptAlloc
0x180087299  mov     r14, rax
0x18008729c  test    rax, rax
0x18008729f  jnz     short loc_1800872CC
0x1800872a1  mov     r9d, 5D5h
0x1800872a7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800872ae  lea     rdx, aStatus; "Status"
0x1800872b5  mov     ecx, 0C0000017h
0x1800872ba  mov     ebx, 0C0000017h
0x1800872bf  call    DebugTraceError
0x1800872c4  xor     r12d, r12d
0x1800872c7  jmp     loc_180087449
0x1800872cc  mov     rdx, [rbx+8]
0x1800872d0  mov     r8, r13; Size
0x1800872d3  mov     rcx, r14; void *
0x1800872d6  mov     rdx, [rdx+r15*8+8]; Src
0x1800872db  call    memmove
0x1800872e0  mov     ecx, [rbp+var_28]
0x1800872e3  xor     eax, eax
0x1800872e5  mov     [r14+r12*2], ax
0x1800872ea  mov     rdx, r14
0x1800872ed  neg     ecx
0x1800872ef  lea     rcx, [rbp+var_18]
0x1800872f3  sbb     r8d, r8d
0x1800872f6  neg     r8d
0x1800872f9  add     r8d, 20h ; ' '
0x1800872fd  call    MSCryptOpenHashProvider
0x180087302  xor     r12d, r12d
0x180087305  mov     ebx, eax
0x180087307  test    eax, eax
0x180087309  jz      short loc_18008732F
0x18008730b  mov     r9d, 5EDh
0x180087311  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180087318  lea     rdx, aStatus; "Status"
0x18008731f  mov     ecx, eax
0x180087321  call    DebugTraceError
0x180087326  mov     rdi, qword ptr [rbp+var_18]
0x18008732a  jmp     loc_180087449
0x18008732f  mov     rdi, qword ptr [rbp+var_18]
0x180087333  lea     rax, [rbp+var_24]
0x180087337  mov     rcx, rdi
0x18008733a  mov     dword ptr [rsp+68h+Src], r12d
0x18008733f  mov     r9d, 4
0x180087345  mov     qword ptr [rsp+68h+var_48], rax
0x18008734a  lea     r8, [rbp+arg_8]
0x18008734e  lea     rdx, aObjectlength; "ObjectLength"
0x180087355  call    MSCryptGetHashProperty
0x18008735a  mov     ebx, eax
0x18008735c  test    eax, eax
0x18008735e  jz      short loc_18008736D
0x180087360  mov     r9d, 5FBh
0x180087366  mov     ecx, eax
0x180087368  jmp     loc_180087436
0x18008736d  mov     ecx, dword ptr [rbp+arg_8]
0x180087370  call    MSCryptAlloc
0x180087375  mov     rsi, rax
0x180087378  test    rax, rax
0x18008737b  jnz     short loc_180087392
0x18008737d  mov     ebx, 0C0000017h
0x180087382  mov     r9d, 603h
0x180087388  mov     ecx, 0C0000017h
0x18008738d  jmp     loc_180087436
0x180087392  mov     eax, dword ptr [rbp+arg_8]
0x180087395  lea     rdx, [rbp+var_20]; int
0x180087399  mov     [rsp+68h+var_30], r12d; int
0x18008739e  mov     r9, rsi; int
0x1800873a1  mov     dword ptr [rsp+68h+Size], r12d; Size
0x1800873a6  xor     r8d, r8d; int
0x1800873a9  mov     [rsp+68h+Src], r12; Src
0x1800873ae  mov     rcx, rdi; int
0x1800873b1  mov     [rsp+68h+var_48], eax; int
0x1800873b5  call    MSCryptCreateMultiHash
0x1800873ba  mov     ebx, eax
0x1800873bc  test    eax, eax
0x1800873be  jz      short loc_1800873C8
0x1800873c0  mov     r9d, 613h
0x1800873c6  jmp     short loc_180087366
0x1800873c8  mov     rdx, [rbp+arg_0]
0x1800873cc  xor     r9d, r9d
0x1800873cf  mov     rcx, qword ptr [rbp+var_20]
0x1800873d3  mov     r8d, [rdx+10h]
0x1800873d7  mov     rdx, [rdx+18h]
0x1800873db  call    MSCryptHashData
0x1800873e0  mov     ebx, eax
0x1800873e2  test    eax, eax
0x1800873e4  jz      short loc_1800873F1
0x1800873e6  mov     r9d, 61Eh
0x1800873ec  jmp     loc_180087366
0x1800873f1  mov     r15d, [rbp+arg_18]
0x1800873f5  mov     r8d, r15d
0x1800873f8  mov     r9d, [rbp+arg_28]
0x1800873fc  mov     rdx, [rbp+arg_10]
0x180087400  mov     rcx, qword ptr [rbp+var_20]
0x180087404  call    _CapiKDF
0x180087409  mov     ebx, eax
0x18008740b  test    eax, eax
0x18008740d  jz      short loc_18008741A
0x18008740f  mov     r9d, 62Ah
0x180087415  jmp     loc_180087366
0x18008741a  mov     rax, [rbp+arg_20]
0x18008741e  mov     ebx, r12d
0x180087421  mov     [rax], r15d
0x180087424  jmp     short loc_180087449
0x180087426  mov     r9d, 5C6h
0x18008742c  mov     ebx, 0C000000Dh
0x180087431  mov     ecx, 0C000000Dh
0x180087436  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008743d  lea     rdx, aStatus; "Status"
0x180087444  call    DebugTraceError
0x180087449  mov     rcx, qword ptr [rbp+var_20]
0x18008744d  test    rcx, rcx
0x180087450  jz      short loc_180087457
0x180087452  call    MSCryptDestroyHash
0x180087457  test    rsi, rsi
0x18008745a  jz      short loc_18008747B
0x18008745c  mov     eax, dword ptr [rbp+arg_8]
0x18008745f  mov     rdx, rsi
0x180087462  test    rax, rax
0x180087465  jz      short loc_180087473
0x180087467  mov     [rdx], r12b
0x18008746a  inc     rdx
0x18008746d  sub     rax, 1
0x180087471  jnz     short loc_180087467
0x180087473  mov     rcx, rsi; P
0x180087476  call    MSCryptFree
0x18008747b  test    rdi, rdi
0x18008747e  jz      short loc_18008748A
0x180087480  xor     edx, edx
0x180087482  mov     rcx, rdi
0x180087485  call    MSCryptCloseHashProvider
0x18008748a  test    r14, r14
0x18008748d  jz      short loc_180087497
0x18008748f  mov     rcx, r14; P
0x180087492  call    MSCryptFree
0x180087497  mov     eax, ebx
0x180087499  add     rsp, 68h
0x18008749d  pop     r15
0x18008749f  pop     r14
0x1800874a1  pop     r13
0x1800874a3  pop     r12
0x1800874a5  pop     rdi
0x1800874a6  pop     rsi
0x1800874a7  pop     rbx
0x1800874a8  pop     rbp
0x1800874a9  retn
```
