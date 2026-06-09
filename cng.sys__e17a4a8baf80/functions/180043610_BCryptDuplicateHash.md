# BCryptDuplicateHash

- ea: `0x180043610`
- end: `0x180043877`
- name: `BCryptDuplicateHash`
- size: `615`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_HASH_HANDLE *phNewHash, PUCHAR pbHashObject, ULONG cbHashObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000dc30`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x180043610`
- `0x180043880`
- `0x180065ca0`
- `0x1800a4300`

## string_xrefs

- `0x18004373f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18004378e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180043843`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDuplicateHash(
        BCRYPT_HASH_HANDLE hHash,
        BCRYPT_HASH_HANDLE *phNewHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        ULONG dwFlags)
{
  void *v5; // rsi
  ULONG v6; // ebx
  PUCHAR v7; // rbp
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // r13
  __int64 v14; // rdi
  _DWORD *v15; // r14
  unsigned int v16; // eax
  unsigned __int64 v17; // rbp
  unsigned int v18; // r15d
  unsigned __int64 v19; // r8
  unsigned int v20; // eax
  NTSTATUS v21; // ebx
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 (__fastcall *v27)(_QWORD, _DWORD *, unsigned __int64, _QWORD, ULONG); // rax
  int v28; // ecx
  ULONG v29; // [rsp+40h] [rbp-58h] BYREF
  void *v30; // [rsp+48h] [rbp-50h] BYREF

  v5 = 0;
  v6 = cbHashObject;
  v30 = 0;
  v7 = pbHashObject;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      37,
      pbHashObject,
      hHash,
      phNewHash,
      pbHashObject,
      cbHashObject,
      dwFlags);
  v10 = ValidateBaseHashHandle(hHash);
  v13 = v10;
  if ( v10 )
  {
    v14 = *(_QWORD *)(v10 + 8);
    if ( !v7 )
    {
      if ( !v6 )
      {
        v23 = AllocateObjectBuffer(*(_QWORD *)(v10 + 8), &v30, &v29);
        v5 = v30;
        v21 = v23;
        if ( v23 < 0 )
          goto LABEL_23;
        v6 = v29;
        v7 = (PUCHAR)v30;
      }
      if ( !v7 )
        goto LABEL_20;
    }
    if ( !phNewHash )
    {
LABEL_20:
      v21 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v11,
          v12,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          102);
      goto LABEL_23;
    }
    if ( v6 < 0x46 )
    {
      v21 = -1073741789;
      v24 = 6509;
      v25 = 3221225507LL;
LABEL_29:
      DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v24);
      goto LABEL_23;
    }
    v15 = (_DWORD *)((unsigned __int64)(v7 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
    v16 = (((_DWORD)v7 + 15) & 0xFFFFFFF0) - (_DWORD)v7;
    v17 = (unsigned __int64)&v7[v16 + 40];
    *v15 = 40;
    v15[1] = 1431655763;
    *((_QWORD *)v15 + 1) = v14;
    *((_QWORD *)v15 + 4) = v5;
    v18 = v6 - v16 - 40;
    if ( (*(_DWORD *)(v14 + 8) & 8) != 0 )
    {
      v26 = *(unsigned int *)(v14 + 12);
      if ( v18 < (int)v26 + 15 )
      {
        v21 = -1073741789;
LABEL_23:
        if ( v5 )
          MSCryptFree(v5);
        goto LABEL_12;
      }
      v27 = *(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, _QWORD, ULONG))(v14 + 112);
      v28 = v26 + v17;
      v18 -= v26;
      v17 = (v26 + v17 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
      v29 = v28 + (v18 >> 1) - v17;
      v20 = v27(*(_QWORD *)(v13 + 24), v15 + 6, v17, v29, dwFlags);
      v21 = v20;
      if ( v20 )
      {
        v24 = 6562;
LABEL_33:
        v25 = v20;
        goto LABEL_29;
      }
      v19 = v17 + v29 + 15LL;
    }
    else
    {
      v19 = v17 + 15;
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, unsigned __int64, ULONG))(v14 + 112))(
            *(_QWORD *)(v13 + 16),
            v15 + 4,
            v19 & 0xFFFFFFFFFFFFFFF0uLL,
            v18 + (_DWORD)v17 - (v19 & 0xFFFFFFF0),
            dwFlags);
    v21 = v20;
    if ( !v20 )
    {
      *phNewHash = v15;
LABEL_12:
      if ( v14 && v21 >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(v14 + 16));
      return v21;
    }
    v24 = 6583;
    goto LABEL_33;
  }
  v21 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v11,
      v12,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      71);
  return v21;
}

```

## disassembly

```asm
0x180043610  push    rbx
0x180043612  push    rbp
0x180043613  push    rsi
0x180043614  push    rdi
0x180043615  push    r12
0x180043617  push    r13
0x180043619  push    r14
0x18004361b  push    r15
0x18004361d  sub     rsp, 58h
0x180043621  xor     esi, esi
0x180043623  mov     ebx, r9d
0x180043626  mov     [rsp+98h+var_50], rsi
0x18004362b  mov     rbp, r8
0x18004362e  mov     [rsp+98h+var_58], esi
0x180043632  mov     r12, rdx
0x180043635  mov     rdi, rcx
0x180043638  mov     rcx, cs:WPP_GLOBAL_Control
0x18004363f  lea     r14, WPP_GLOBAL_Control
0x180043646  cmp     rcx, r14
0x180043649  jz      short loc_180043656
0x18004364b  mov     eax, [rcx+2Ch]
0x18004364e  test    al, 4
0x180043650  jnz     loc_1800437CC
0x180043656  mov     rcx, rdi
0x180043659  call    ValidateBaseHashHandle
0x18004365e  mov     r13, rax
0x180043661  test    rax, rax
0x180043664  jz      loc_180043723
0x18004366a  mov     rdi, [rax+8]
0x18004366e  test    rbp, rbp
0x180043671  jz      loc_1800437FB
0x180043677  test    r12, r12
0x18004367a  jz      loc_180043772
0x180043680  cmp     ebx, 46h ; 'F'
0x180043683  jb      loc_18004382C
0x180043689  lea     r14, [rbp+0Fh]
0x18004368d  and     r14, 0FFFFFFFFFFFFFFF0h
0x180043691  mov     eax, r14d
0x180043694  sub     eax, ebp
0x180043696  add     rbp, 28h ; '('
0x18004369a  sub     ebx, eax
0x18004369c  mov     ecx, eax
0x18004369e  add     rbp, rcx
0x1800436a1  mov     dword ptr [r14], 28h ; '('
0x1800436a8  mov     dword ptr [r14+4], 55555553h
0x1800436b0  mov     [r14+8], rdi
0x1800436b4  mov     [r14+20h], rsi
0x1800436b8  lea     r15d, [rbx-28h]
0x1800436bc  mov     eax, [rdi+8]
0x1800436bf  test    al, 8
0x1800436c1  jnz     loc_180043854
0x1800436c7  lea     r8, [rbp+0Fh]
0x1800436cb  mov     ecx, [rsp+98h+dwFlags]
0x1800436d2  lea     rdx, [r14+10h]
0x1800436d6  mov     rax, [rdi+70h]
0x1800436da  and     r8, 0FFFFFFFFFFFFFFF0h
0x1800436de  sub     ebp, r8d
0x1800436e1  mov     dword ptr [rsp+98h+var_78], ecx
0x1800436e5  mov     rcx, [r13+10h]
0x1800436e9  add     ebp, r15d
0x1800436ec  mov     r9d, ebp
0x1800436ef  call    _guard_dispatch_icall
0x1800436f4  mov     ebx, eax
0x1800436f6  test    eax, eax
0x1800436f8  jnz     loc_18004386D
0x1800436fe  mov     [r12], r14
0x180043702  test    rdi, rdi
0x180043705  jz      short loc_18004370F
0x180043707  test    ebx, ebx
0x180043709  js      short loc_18004370F
0x18004370b  lock inc dword ptr [rdi+10h]
0x18004370f  mov     eax, ebx
0x180043711  add     rsp, 58h
0x180043715  pop     r15
0x180043717  pop     r14
0x180043719  pop     r13
0x18004371b  pop     r12
0x18004371d  pop     rdi
0x18004371e  pop     rsi
0x18004371f  pop     rbp
0x180043720  pop     rbx
0x180043721  retn
0x180043723  mov     ebx, 0C0000008h
0x180043728  mov     rcx, cs:WPP_GLOBAL_Control
0x18004372f  cmp     rcx, r14
0x180043732  jz      short loc_18004370F
0x180043734  mov     eax, [rcx+2Ch]
0x180043737  test    al, 1
0x180043739  jz      short loc_18004370F
0x18004373b  mov     rcx, [rcx+18h]
0x18004373f  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043746  mov     [rsp+98h+var_68], 1947h
0x18004374e  lea     r9, aStatus; "Status"
0x180043755  mov     [rsp+98h+var_70], rax
0x18004375a  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x180043762  call    WPP_SF_sDsd
0x180043767  jmp     short loc_18004370F
0x180043769  test    rbp, rbp
0x18004376c  jnz     loc_180043677
0x180043772  mov     ebx, 0C000000Dh
0x180043777  mov     rcx, cs:WPP_GLOBAL_Control
0x18004377e  cmp     rcx, r14
0x180043781  jz      short loc_1800437B6
0x180043783  mov     eax, [rcx+2Ch]
0x180043786  test    al, 1
0x180043788  jz      short loc_1800437B6
0x18004378a  mov     rcx, [rcx+18h]
0x18004378e  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043795  mov     [rsp+98h+var_68], 1966h
0x18004379d  lea     r9, aStatus; "Status"
0x1800437a4  mov     [rsp+98h+var_70], rax
0x1800437a9  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x1800437b1  call    WPP_SF_sDsd
0x1800437b6  test    rsi, rsi
0x1800437b9  jz      loc_180043702
0x1800437bf  mov     rcx, rsi; P
0x1800437c2  call    MSCryptFree
0x1800437c7  jmp     loc_180043702
0x1800437cc  mov     eax, [rsp+98h+dwFlags]
0x1800437d3  mov     edx, 25h ; '%'
0x1800437d8  mov     rcx, [rcx+18h]
0x1800437dc  mov     r9, rdi
0x1800437df  mov     [rsp+98h+var_60], eax
0x1800437e3  mov     [rsp+98h+var_68], ebx
0x1800437e7  mov     [rsp+98h+var_70], rbp
0x1800437ec  mov     [rsp+98h+var_78], r12
0x1800437f1  call    WPP_SF_qqqdD
0x1800437f6  jmp     loc_180043656
0x1800437fb  test    ebx, ebx
0x1800437fd  jnz     loc_180043769
0x180043803  lea     r8, [rsp+98h+var_58]
0x180043808  mov     rcx, rdi
0x18004380b  lea     rdx, [rsp+98h+var_50]
0x180043810  call    AllocateObjectBuffer
0x180043815  mov     rsi, [rsp+98h+var_50]
0x18004381a  mov     ebx, eax
0x18004381c  test    eax, eax
0x18004381e  js      short loc_1800437B6
0x180043820  mov     ebx, [rsp+98h+var_58]
0x180043824  mov     rbp, rsi
0x180043827  jmp     loc_180043769
0x18004382c  mov     ebx, 0C0000023h
0x180043831  mov     r9d, 196Dh
0x180043837  mov     ecx, 0C0000023h
0x18004383c  lea     rdx, aStatus; "Status"
0x180043843  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004384a  call    DebugTraceError
0x18004384f  jmp     loc_1800437B6
0x180043854  mov     edx, [rdi+0Ch]
0x180043857  lea     eax, [rdx+0Fh]
0x18004385a  cmp     r15d, eax
0x18004385d  jnb     loc_1800A7E3E
0x180043863  mov     ebx, 0C0000023h
0x180043868  jmp     loc_1800437B6
0x18004386d  mov     r9d, 19B7h
0x180043873  mov     ecx, eax
0x180043875  jmp     short loc_18004383C
0x1800a7e3e  mov     rax, [rdi+70h]
0x1800a7e42  lea     rcx, [rdx+rbp]
0x1800a7e46  lea     rbp, [rcx+0Fh]
0x1800a7e4a  sub     r15d, edx
0x1800a7e4d  mov     r8d, r15d
0x1800a7e50  lea     rdx, [r14+18h]
0x1800a7e54  shr     r8d, 1
0x1800a7e57  and     rbp, 0FFFFFFFFFFFFFFF0h
0x1800a7e5b  sub     r8d, ebp
0x1800a7e5e  add     r8d, ecx
0x1800a7e61  mov     ecx, [rsp+98h+dwFlags]
0x1800a7e68  mov     [rsp+98h+var_58], r8d
0x1800a7e6d  mov     r9d, r8d
0x1800a7e70  mov     dword ptr [rsp+98h+var_78], ecx
0x1800a7e74  mov     r8, rbp
0x1800a7e77  mov     rcx, [r13+18h]
0x1800a7e7b  call    _guard_dispatch_icall
0x1800a7e80  mov     ebx, eax
0x1800a7e82  test    eax, eax
0x1800a7e84  jz      short loc_1800A7E91
0x1800a7e86  mov     r9d, 19A2h
0x1800a7e8c  jmp     loc_180043873
0x1800a7e91  mov     r8d, [rsp+98h+var_58]
0x1800a7e96  add     r8, 0Fh
0x1800a7e9a  add     r8, rbp
0x1800a7e9d  jmp     loc_1800436CB
```
