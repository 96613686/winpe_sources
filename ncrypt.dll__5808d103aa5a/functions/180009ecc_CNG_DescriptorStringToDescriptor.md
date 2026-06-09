# CNG_DescriptorStringToDescriptor

- ea: `0x180009ecc`
- end: `0x18000a3c5`
- name: `CNG_DescriptorStringToDescriptor`
- size: `1273`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000962c`

## callees

- `0x1800090e0`
- `0x180009cd0`
- `0x180009ecc`
- `0x18000a770`
- `0x18000d02c`
- `0x18000e120`
- `0x18000f9d8`
- `0x180014d6c`
- `0x1800152c8`
- `0x180015c4c`
- `0x180015fc4`
- `0x18001f145`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a073`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a073`

## string_xrefs

- `0x18000a152`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000a1d3`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000a251`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000a298`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000a331`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000a351`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000a3ad`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall CNG_DescriptorStringToDescriptor(STRSAFE_LPCWSTR pszSrc, _QWORD *a2)
{
  __int64 v4; // rax
  size_t v5; // r14
  wchar_t *v6; // rdi
  unsigned __int64 v7; // rbx
  wchar_t *v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  HRESULT v13; // eax
  int ProviderNameAndMoveCursToProviderValue; // ebx
  char *v15; // rax
  int v16; // edx
  char *v17; // rsi
  unsigned int v18; // r14d
  PCNZWCH *v19; // r15
  PCNZWCH v20; // r13
  __int64 v21; // rax
  unsigned int v22; // eax
  _QWORD *v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // [rsp+0h] [rbp-40h] BYREF
  PCNZWCH lpString2; // [rsp+20h] [rbp-20h]
  int cchCount2[2]; // [rsp+28h] [rbp-18h]
  int v31; // [rsp+30h] [rbp-10h]
  int v32; // [rsp+40h] [rbp+0h] BYREF
  int v33; // [rsp+44h] [rbp+4h] BYREF
  wchar_t *v34; // [rsp+48h] [rbp+8h] BYREF
  __int128 v35; // [rsp+50h] [rbp+10h] BYREF
  const size_t *v36; // [rsp+60h] [rbp+20h] BYREF
  PCNZWCH lpString1; // [rsp+68h] [rbp+28h] BYREF

  *a2 = 0;
  v35 = 0;
  if ( !pszSrc )
  {
    v25 = CNG_DuplicateDescriptor(&v35, a2, 1);
    ProviderNameAndMoveCursToProviderValue = v25;
    if ( v25 )
      DebugTraceError(v25, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c", 779);
    goto LABEL_33;
  }
  v4 = -1;
  do
    ++v4;
  while ( pszSrc[v4] );
  v5 = v4 + 1;
  v6 = 0;
  v7 = 2 * (v4 + 1);
  if ( !v7
    || v7 > g_ulMaxStackAllocSize
    || v7 + g_ulAdditionalProbeSize + 8 < v7
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_71;
  }
  v9 = v7 + 23;
  if ( v7 + 23 <= v7 + 8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  v6 = (wchar_t *)&v32;
  if ( &v28 == (__int64 *)-64LL || (v32 = 1801679955, (v6 = (wchar_t *)&v34) == 0) )
  {
LABEL_71:
    if ( v7 + 8 >= v7 )
    {
      v8 = (wchar_t *)((__int64 (*)(void))g_pfnAllocate)();
      v6 = v8;
      if ( v8 )
      {
        *(_DWORD *)v8 = 1885431112;
        v6 = v8 + 4;
      }
    }
  }
  if ( !v6 )
  {
    ProviderNameAndMoveCursToProviderValue = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        (unsigned int)"hr",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        28);
LABEL_33:
    v17 = (char *)*((_QWORD *)&v35 + 1);
    goto LABEL_34;
  }
  v13 = StringCchCopyW(v6, v5, pszSrc);
  ProviderNameAndMoveCursToProviderValue = v13;
  if ( v13 < 0 )
  {
    DebugTraceError(
      (unsigned int)v13,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      803);
    v17 = (char *)*((_QWORD *)&v35 + 1);
    goto LABEL_28;
  }
  v15 = (char *)SafeAllocaAllocateFromHeap(2304);
  *((_QWORD *)&v35 + 1) = v15;
  v17 = v15;
  if ( !v15 )
  {
    ProviderNameAndMoveCursToProviderValue = -2146893810;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v31 = 819;
    *(_QWORD *)cchCount2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c";
    LODWORD(lpString2) = -2146893810;
    goto LABEL_41;
  }
  v32 = 0;
  v18 = 0;
  memset_0(v15, 0, 0x900u);
  v19 = (PCNZWCH *)(v17 + 256);
  v34 = v6;
  *((_QWORD *)v17 + 1) = v17 + 256;
  while ( 1 )
  {
    if ( !*v34 )
    {
LABEL_27:
      LODWORD(v35) = v18 + 1;
      v22 = CNG_DuplicateDescriptor(&v35, a2, 1);
      ProviderNameAndMoveCursToProviderValue = v22;
      if ( !v22 )
        goto LABEL_28;
      v26 = 940;
      v27 = v22;
      goto LABEL_68;
    }
    lpString1 = (PCNZWCH)&LocaleName;
    v36 = &LocaleName;
    v33 = 0;
    ProviderNameAndMoveCursToProviderValue = GetProviderNameAndMoveCursToProviderValue(&v34, &lpString1);
    if ( ProviderNameAndMoveCursToProviderValue < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v31 = 859;
      goto LABEL_40;
    }
    v20 = lpString1;
    if ( CompareStringW(0, 1u, lpString1, -1, L"CERTIFICATE", -1) == 2 )
    {
      if ( v32 )
      {
        ProviderNameAndMoveCursToProviderValue = -2146893783;
        goto LABEL_28;
      }
      v32 = 1;
    }
    ProviderNameAndMoveCursToProviderValue = GetProviderValueAndMoveCursToUnparsed(&v34, &v36);
    if ( ProviderNameAndMoveCursToProviderValue < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v31 = 880;
      goto LABEL_40;
    }
    v21 = 32LL * v18;
    if ( ++*(_DWORD *)&v17[v21] > 8u )
      break;
    v19[1] = (PCNZWCH)v36;
    *v19 = v20;
    ProviderNameAndMoveCursToProviderValue = GetTokenAndMoveCursToUnparsed(&v34, &v33);
    if ( ProviderNameAndMoveCursToProviderValue < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v31 = 901;
LABEL_40:
      *(_QWORD *)cchCount2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c";
      LODWORD(lpString2) = ProviderNameAndMoveCursToProviderValue;
      goto LABEL_41;
    }
    v19 += 4;
    switch ( v33 )
    {
      case 2:
        if ( ++v18 + 1 > 8 )
        {
          v26 = 910;
LABEL_66:
          ProviderNameAndMoveCursToProviderValue = -2146893819;
          v27 = 2148073477LL;
LABEL_68:
          DebugTraceError(
            v27,
            "hr",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
            v26);
          goto LABEL_28;
        }
        *(_QWORD *)&v17[32 * v18 + 8] = v19;
        break;
      case 0:
        v26 = 918;
        goto LABEL_66;
      case 3:
        goto LABEL_27;
    }
  }
  ProviderNameAndMoveCursToProviderValue = -2146893819;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_28;
  v31 = 888;
  *(_QWORD *)cchCount2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c";
  LODWORD(lpString2) = -2146893819;
LABEL_41:
  WPP_SF_sDsd(
    v24[2],
    v16,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
    (unsigned int)"hr",
    (char)lpString2,
    *(__int64 *)cchCount2,
    v31);
LABEL_28:
  if ( *((_DWORD *)v6 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_34:
  if ( v17 )
    MSCryptFree(v17);
  return (unsigned int)ProviderNameAndMoveCursToProviderValue;
}

```

## disassembly

```asm
0x180009ecc  push    rbp
0x180009ece  push    rbx
0x180009ecf  push    rsi
0x180009ed0  push    rdi
0x180009ed1  push    r12
0x180009ed3  push    r13
0x180009ed5  push    r14
0x180009ed7  push    r15
0x180009ed9  sub     rsp, 88h
0x180009ee0  lea     rbp, [rsp+40h]
0x180009ee5  mov     rax, cs:__security_cookie
0x180009eec  xor     rax, rbp
0x180009eef  mov     [rbp+80h+var_50], rax
0x180009ef3  xor     r13d, r13d
0x180009ef6  xorps   xmm0, xmm0
0x180009ef9  mov     [rdx], r13
0x180009efc  mov     r12, rdx
0x180009eff  mov     rsi, rcx
0x180009f02  movups  [rbp+80h+var_70], xmm0
0x180009f06  test    rcx, rcx
0x180009f09  jz      loc_18000A312
0x180009f0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009f13  inc     rax
0x180009f16  cmp     [rcx+rax*2], r13w
0x180009f1b  jnz     short loc_180009F13
0x180009f1d  lea     r14, [rax+1]
0x180009f21  mov     rdi, r13
0x180009f24  lea     rbx, [r14+r14]
0x180009f28  test    rbx, rbx
0x180009f2b  jnz     loc_18000A300
0x180009f31  lea     rcx, [rbx+8]
0x180009f35  cmp     rcx, rbx
0x180009f38  jb      short loc_180009FB6
0x180009f3a  mov     rax, cs:g_pfnAllocate
0x180009f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f46  mov     rdi, rax
0x180009f49  test    rax, rax
0x180009f4c  jz      short loc_180009FB6
0x180009f4e  mov     dword ptr [rax], 70616548h
0x180009f54  add     rdi, 8
0x180009f58  jmp     short loc_180009FB6
0x180009f5a  mov     rcx, cs:g_ulAdditionalProbeSize
0x180009f61  add     rcx, 8
0x180009f65  add     rcx, rbx
0x180009f68  cmp     rcx, rbx
0x180009f6b  jb      short loc_180009F31
0x180009f6d  call    VerifyStackAvailable
0x180009f72  test    eax, eax
0x180009f74  jz      short loc_180009F31
0x180009f76  lea     rax, [rbx+8]
0x180009f7a  lea     rcx, [rax+0Fh]
0x180009f7e  cmp     rcx, rax
0x180009f81  ja      short loc_180009F8D
0x180009f83  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180009f8d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180009f91  mov     rax, rcx
0x180009f94  call    __chkstk_0
0x180009f99  sub     rsp, rcx
0x180009f9c  lea     rdi, [rsp+0C0h+var_80]
0x180009fa1  test    rdi, rdi
0x180009fa4  jz      short loc_180009F31
0x180009fa6  mov     dword ptr [rdi], 6B637453h
0x180009fac  add     rdi, 8
0x180009fb0  jz      loc_180009F31
0x180009fb6  test    rdi, rdi
0x180009fb9  jz      loc_18000A130
0x180009fbf  mov     r8, rsi; pszSrc
0x180009fc2  mov     rdx, r14; cchDest
0x180009fc5  mov     rcx, rdi; pszDest
0x180009fc8  call    StringCchCopyW
0x180009fcd  mov     ebx, eax
0x180009fcf  test    eax, eax
0x180009fd1  js      loc_18000A34B
0x180009fd7  mov     ebx, 900h
0x180009fdc  mov     ecx, ebx
0x180009fde  call    SafeAllocaAllocateFromHeap
0x180009fe3  mov     qword ptr [rbp+80h+var_70+8], rax
0x180009fe7  mov     rsi, rax
0x180009fea  test    rax, rax
0x180009fed  jz      loc_18000A223
0x180009ff3  mov     r8d, ebx; Size
0x180009ff6  mov     [rbp+80h+var_80], r13d
0x180009ffa  xor     edx, edx; Val
0x180009ffc  mov     rcx, rax; void *
0x180009fff  mov     r14d, r13d
0x18000a002  call    memset_0
0x18000a007  lea     r15, [rsi+100h]
0x18000a00e  mov     [rbp+80h+var_78], rdi
0x18000a012  mov     [rsi+8], r15
0x18000a016  mov     rax, [rbp+80h+var_78]
0x18000a01a  lea     rcx, LocaleName
0x18000a021  cmp     [rax], r13w
0x18000a025  jz      loc_18000A0F3
0x18000a02b  mov     [rbp+80h+lpString1], rcx
0x18000a02f  lea     rdx, [rbp+80h+lpString1]
0x18000a033  mov     [rbp+80h+var_60], rcx
0x18000a037  lea     rcx, [rbp+80h+var_78]
0x18000a03b  mov     [rbp+80h+var_7C], r13d
0x18000a03f  call    _GetProviderNameAndMoveCursToProviderValue
0x18000a044  mov     ebx, eax
0x18000a046  test    eax, eax
0x18000a048  js      loc_18000A1AA
0x18000a04e  mov     r13, [rbp+80h+lpString1]
0x18000a052  lea     rax, aCertificate; "CERTIFICATE"
0x18000a059  or      r9d, 0FFFFFFFFh; cchCount1
0x18000a05d  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000a065  mov     r8, r13; lpString1
0x18000a068  mov     [rsp+0C0h+lpString2], rax; lpString2
0x18000a06d  xor     ecx, ecx; Locale
0x18000a06f  lea     edx, [r9+2]; dwCmpFlags
0x18000a073  call    cs:__imp_CompareStringW
0x18000a079  cmp     eax, 2
0x18000a07c  jz      loc_18000A36F
0x18000a082  lea     rdx, [rbp+80h+var_60]
0x18000a086  lea     rcx, [rbp+80h+var_78]
0x18000a08a  call    _GetProviderValueAndMoveCursToUnparsed
0x18000a08f  mov     ebx, eax
0x18000a091  test    eax, eax
0x18000a093  js      loc_18000A1F8
0x18000a099  mov     eax, r14d
0x18000a09c  shl     rax, 5
0x18000a0a0  inc     dword ptr [rax+rsi]
0x18000a0a3  cmp     dword ptr [rax+rsi], 8
0x18000a0a7  ja      loc_18000A26A
0x18000a0ad  mov     rax, [rbp+80h+var_60]
0x18000a0b1  lea     rdx, [rbp+80h+var_7C]
0x18000a0b5  lea     rcx, [rbp+80h+var_78]
0x18000a0b9  mov     [r15+8], rax
0x18000a0bd  mov     [r15], r13
0x18000a0c0  call    _GetTokenAndMoveCursToUnparsed
0x18000a0c5  xor     r13d, r13d
0x18000a0c8  mov     ebx, eax
0x18000a0ca  test    eax, eax
0x18000a0cc  js      loc_18000A2B1
0x18000a0d2  mov     eax, [rbp+80h+var_7C]
0x18000a0d5  add     r15, 20h ; ' '
0x18000a0d9  cmp     eax, 2
0x18000a0dc  jz      loc_18000A2DF
0x18000a0e2  test    eax, eax
0x18000a0e4  jz      loc_18000A393
0x18000a0ea  cmp     eax, 3
0x18000a0ed  jnz     loc_18000A016
0x18000a0f3  lea     eax, [r14+1]
0x18000a0f7  mov     r8d, 1
0x18000a0fd  mov     rdx, r12
0x18000a100  mov     dword ptr [rbp+80h+var_70], eax
0x18000a103  lea     rcx, [rbp+80h+var_70]
0x18000a107  call    CNG_DuplicateDescriptor
0x18000a10c  mov     ebx, eax
0x18000a10e  test    eax, eax
0x18000a110  jnz     loc_18000A3A5
0x18000a116  lea     rcx, [rdi-8]
0x18000a11a  cmp     dword ptr [rcx], 70616548h
0x18000a120  jnz     short loc_18000A17E
0x18000a122  mov     rax, cs:g_pfnFree
0x18000a129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12e  jmp     short loc_18000A17E
0x18000a130  mov     ebx, 8009000Eh
0x18000a135  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a13c  lea     rax, WPP_GLOBAL_Control
0x18000a143  cmp     rcx, rax
0x18000a146  jz      short loc_18000A17A
0x18000a148  test    byte ptr [rcx+1Ch], 1
0x18000a14c  jz      short loc_18000A17A
0x18000a14e  mov     rcx, [rcx+10h]
0x18000a152  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a159  mov     [rsp+0C0h+var_90], 31Ch
0x18000a161  lea     r9, aHr; "hr"
0x18000a168  mov     qword ptr [rsp+0C0h+cchCount2], r8
0x18000a16d  mov     dword ptr [rsp+0C0h+lpString2], 8009000Eh
0x18000a175  call    WPP_SF_sDsd
0x18000a17a  mov     rsi, qword ptr [rbp+80h+var_70+8]
0x18000a17e  test    rsi, rsi
0x18000a181  jz      short loc_18000A18B
0x18000a183  mov     rcx, rsi
0x18000a186  call    MSCryptFree
0x18000a18b  mov     eax, ebx
0x18000a18d  mov     rcx, [rbp+80h+var_50]
0x18000a191  xor     rcx, rbp; StackCookie
0x18000a194  call    __security_check_cookie
0x18000a199  lea     rsp, [rbp+48h]
0x18000a19d  pop     r15
0x18000a19f  pop     r14
0x18000a1a1  pop     r13
0x18000a1a3  pop     r12
0x18000a1a5  pop     rdi
0x18000a1a6  pop     rsi
0x18000a1a7  pop     rbx
0x18000a1a8  pop     rbp
0x18000a1a9  retn
0x18000a1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1b1  lea     rax, WPP_GLOBAL_Control
0x18000a1b8  cmp     rcx, rax
0x18000a1bb  jz      loc_18000A116
0x18000a1c1  test    byte ptr [rcx+1Ch], 1
0x18000a1c5  jz      loc_18000A116
0x18000a1cb  mov     [rsp+0C0h+var_90], 35Bh
0x18000a1d3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a1da  mov     qword ptr [rsp+0C0h+cchCount2], r8
0x18000a1df  mov     dword ptr [rsp+0C0h+lpString2], ebx
0x18000a1e3  mov     rcx, [rcx+10h]
0x18000a1e7  lea     r9, aHr; "hr"
0x18000a1ee  call    WPP_SF_sDsd
0x18000a1f3  jmp     loc_18000A116
0x18000a1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1ff  lea     rax, WPP_GLOBAL_Control
0x18000a206  cmp     rcx, rax
0x18000a209  jz      loc_18000A116
0x18000a20f  test    byte ptr [rcx+1Ch], 1
0x18000a213  jz      loc_18000A116
0x18000a219  mov     [rsp+0C0h+var_90], 370h
0x18000a221  jmp     short loc_18000A1D3
0x18000a223  mov     ebx, 8009000Eh
0x18000a228  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a22f  lea     rax, WPP_GLOBAL_Control
0x18000a236  cmp     rcx, rax
0x18000a239  jz      loc_18000A116
0x18000a23f  test    byte ptr [rcx+1Ch], 1
0x18000a243  jz      loc_18000A116
0x18000a249  mov     [rsp+0C0h+var_90], 333h
0x18000a251  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a258  mov     qword ptr [rsp+0C0h+cchCount2], r8
0x18000a25d  mov     dword ptr [rsp+0C0h+lpString2], 8009000Eh
0x18000a265  jmp     loc_18000A1E3
0x18000a26a  mov     ebx, 80090005h
0x18000a26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a276  lea     rax, WPP_GLOBAL_Control
0x18000a27d  cmp     rcx, rax
0x18000a280  jz      loc_18000A116
0x18000a286  test    byte ptr [rcx+1Ch], 1
0x18000a28a  jz      loc_18000A116
0x18000a290  mov     [rsp+0C0h+var_90], 378h
0x18000a298  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a29f  mov     qword ptr [rsp+0C0h+cchCount2], r8
0x18000a2a4  mov     dword ptr [rsp+0C0h+lpString2], 80090005h
0x18000a2ac  jmp     loc_18000A1E3
0x18000a2b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2b8  lea     rax, WPP_GLOBAL_Control
0x18000a2bf  cmp     rcx, rax
0x18000a2c2  jz      loc_18000A116
0x18000a2c8  test    byte ptr [rcx+1Ch], 1
0x18000a2cc  jz      loc_18000A116
0x18000a2d2  mov     [rsp+0C0h+var_90], 385h
0x18000a2da  jmp     loc_18000A1D3
0x18000a2df  inc     r14d
0x18000a2e2  lea     eax, [r14+1]
0x18000a2e6  cmp     eax, 8
0x18000a2e9  ja      loc_18000A38B
0x18000a2ef  mov     eax, r14d
0x18000a2f2  shl     rax, 5
0x18000a2f6  mov     [rax+rsi+8], r15
0x18000a2fb  jmp     loc_18000A016
0x18000a300  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000a307  ja      loc_180009F31
0x18000a30d  jmp     loc_180009F5A
0x18000a312  mov     r8d, 1
0x18000a318  lea     rcx, [rbp+80h+var_70]
0x18000a31c  call    CNG_DuplicateDescriptor
0x18000a321  mov     ebx, eax
0x18000a323  test    eax, eax
0x18000a325  jz      loc_18000A17A
0x18000a32b  mov     r9d, 30Bh
0x18000a331  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a338  lea     rdx, aHr; "hr"
0x18000a33f  mov     ecx, eax
0x18000a341  call    DebugTraceError
0x18000a346  jmp     loc_18000A17A
0x18000a34b  mov     r9d, 323h
0x18000a351  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a358  lea     rdx, aHr; "hr"
0x18000a35f  mov     ecx, eax
0x18000a361  call    DebugTraceError
0x18000a366  mov     rsi, qword ptr [rbp+80h+var_70+8]
0x18000a36a  jmp     loc_18000A116
0x18000a36f  cmp     [rbp+80h+var_80], 0
0x18000a373  jnz     short loc_18000A381
0x18000a375  mov     [rbp+80h+var_80], 1
0x18000a37c  jmp     loc_18000A082
0x18000a381  mov     ebx, 80090029h
0x18000a386  jmp     loc_18000A116
0x18000a38b  mov     r9d, 38Eh
0x18000a391  jmp     short loc_18000A399
0x18000a393  mov     r9d, 396h
0x18000a399  mov     ebx, 80090005h
0x18000a39e  mov     ecx, 80090005h
0x18000a3a3  jmp     short loc_18000A3AD
0x18000a3a5  mov     r9d, 3ACh
0x18000a3ab  mov     ecx, eax
0x18000a3ad  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a3b4  lea     rdx, aHr; "hr"
0x18000a3bb  call    DebugTraceError
0x18000a3c0  jmp     loc_18000A116
```
