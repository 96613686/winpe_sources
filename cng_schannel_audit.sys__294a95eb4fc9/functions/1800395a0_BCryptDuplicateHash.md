# BCryptDuplicateHash

- ea: `0x1800395a0`
- end: `0x180039807`
- name: `BCryptDuplicateHash`
- size: `615`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_HASH_HANDLE *phNewHash, PUCHAR pbHashObject, ULONG cbHashObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003b10`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x1800395a0`
- `0x180039810`
- `0x18005bad0`
- `0x18009d860`

## string_xrefs

- `0x1800396cf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003971e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800397d3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x1800395a0  push    rbx
0x1800395a2  push    rbp
0x1800395a3  push    rsi
0x1800395a4  push    rdi
0x1800395a5  push    r12
0x1800395a7  push    r13
0x1800395a9  push    r14
0x1800395ab  push    r15
0x1800395ad  sub     rsp, 58h
0x1800395b1  xor     esi, esi
0x1800395b3  mov     ebx, r9d
0x1800395b6  mov     [rsp+98h+var_50], rsi
0x1800395bb  mov     rbp, r8
0x1800395be  mov     [rsp+98h+var_58], esi
0x1800395c2  mov     r12, rdx
0x1800395c5  mov     rdi, rcx
0x1800395c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800395cf  lea     r14, WPP_GLOBAL_Control
0x1800395d6  cmp     rcx, r14
0x1800395d9  jz      short loc_1800395E6
0x1800395db  mov     eax, [rcx+2Ch]
0x1800395de  test    al, 4
0x1800395e0  jnz     loc_18003975C
0x1800395e6  mov     rcx, rdi
0x1800395e9  call    ValidateBaseHashHandle
0x1800395ee  mov     r13, rax
0x1800395f1  test    rax, rax
0x1800395f4  jz      loc_1800396B3
0x1800395fa  mov     rdi, [rax+8]
0x1800395fe  test    rbp, rbp
0x180039601  jz      loc_18003978B
0x180039607  test    r12, r12
0x18003960a  jz      loc_180039702
0x180039610  cmp     ebx, 46h ; 'F'
0x180039613  jb      loc_1800397BC
0x180039619  lea     r14, [rbp+0Fh]
0x18003961d  and     r14, 0FFFFFFFFFFFFFFF0h
0x180039621  mov     eax, r14d
0x180039624  sub     eax, ebp
0x180039626  add     rbp, 28h ; '('
0x18003962a  sub     ebx, eax
0x18003962c  mov     ecx, eax
0x18003962e  add     rbp, rcx
0x180039631  mov     dword ptr [r14], 28h ; '('
0x180039638  mov     dword ptr [r14+4], 55555553h
0x180039640  mov     [r14+8], rdi
0x180039644  mov     [r14+20h], rsi
0x180039648  lea     r15d, [rbx-28h]
0x18003964c  mov     eax, [rdi+8]
0x18003964f  test    al, 8
0x180039651  jnz     loc_1800397E4
0x180039657  lea     r8, [rbp+0Fh]
0x18003965b  mov     ecx, [rsp+98h+dwFlags]
0x180039662  lea     rdx, [r14+10h]
0x180039666  mov     rax, [rdi+70h]
0x18003966a  and     r8, 0FFFFFFFFFFFFFFF0h
0x18003966e  sub     ebp, r8d
0x180039671  mov     dword ptr [rsp+98h+var_78], ecx
0x180039675  mov     rcx, [r13+10h]
0x180039679  add     ebp, r15d
0x18003967c  mov     r9d, ebp
0x18003967f  call    _guard_dispatch_icall
0x180039684  mov     ebx, eax
0x180039686  test    eax, eax
0x180039688  jnz     loc_1800397FD
0x18003968e  mov     [r12], r14
0x180039692  test    rdi, rdi
0x180039695  jz      short loc_18003969F
0x180039697  test    ebx, ebx
0x180039699  js      short loc_18003969F
0x18003969b  lock inc dword ptr [rdi+10h]
0x18003969f  mov     eax, ebx
0x1800396a1  add     rsp, 58h
0x1800396a5  pop     r15
0x1800396a7  pop     r14
0x1800396a9  pop     r13
0x1800396ab  pop     r12
0x1800396ad  pop     rdi
0x1800396ae  pop     rsi
0x1800396af  pop     rbp
0x1800396b0  pop     rbx
0x1800396b1  retn
0x1800396b3  mov     ebx, 0C0000008h
0x1800396b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396bf  cmp     rcx, r14
0x1800396c2  jz      short loc_18003969F
0x1800396c4  mov     eax, [rcx+2Ch]
0x1800396c7  test    al, 1
0x1800396c9  jz      short loc_18003969F
0x1800396cb  mov     rcx, [rcx+18h]
0x1800396cf  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800396d6  mov     [rsp+98h+var_68], 1947h
0x1800396de  lea     r9, aStatus; "Status"
0x1800396e5  mov     [rsp+98h+var_70], rax
0x1800396ea  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x1800396f2  call    WPP_SF_sDsd
0x1800396f7  jmp     short loc_18003969F
0x1800396f9  test    rbp, rbp
0x1800396fc  jnz     loc_180039607
0x180039702  mov     ebx, 0C000000Dh
0x180039707  mov     rcx, cs:WPP_GLOBAL_Control
0x18003970e  cmp     rcx, r14
0x180039711  jz      short loc_180039746
0x180039713  mov     eax, [rcx+2Ch]
0x180039716  test    al, 1
0x180039718  jz      short loc_180039746
0x18003971a  mov     rcx, [rcx+18h]
0x18003971e  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039725  mov     [rsp+98h+var_68], 1966h
0x18003972d  lea     r9, aStatus; "Status"
0x180039734  mov     [rsp+98h+var_70], rax
0x180039739  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x180039741  call    WPP_SF_sDsd
0x180039746  test    rsi, rsi
0x180039749  jz      loc_180039692
0x18003974f  mov     rcx, rsi; P
0x180039752  call    MSCryptFree
0x180039757  jmp     loc_180039692
0x18003975c  mov     eax, [rsp+98h+dwFlags]
0x180039763  mov     edx, 25h ; '%'
0x180039768  mov     rcx, [rcx+18h]
0x18003976c  mov     r9, rdi
0x18003976f  mov     [rsp+98h+var_60], eax
0x180039773  mov     [rsp+98h+var_68], ebx
0x180039777  mov     [rsp+98h+var_70], rbp
0x18003977c  mov     [rsp+98h+var_78], r12
0x180039781  call    WPP_SF_qqqdD
0x180039786  jmp     loc_1800395E6
0x18003978b  test    ebx, ebx
0x18003978d  jnz     loc_1800396F9
0x180039793  lea     r8, [rsp+98h+var_58]
0x180039798  mov     rcx, rdi
0x18003979b  lea     rdx, [rsp+98h+var_50]
0x1800397a0  call    AllocateObjectBuffer
0x1800397a5  mov     rsi, [rsp+98h+var_50]
0x1800397aa  mov     ebx, eax
0x1800397ac  test    eax, eax
0x1800397ae  js      short loc_180039746
0x1800397b0  mov     ebx, [rsp+98h+var_58]
0x1800397b4  mov     rbp, rsi
0x1800397b7  jmp     loc_1800396F9
0x1800397bc  mov     ebx, 0C0000023h
0x1800397c1  mov     r9d, 196Dh
0x1800397c7  mov     ecx, 0C0000023h
0x1800397cc  lea     rdx, aStatus; "Status"
0x1800397d3  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800397da  call    DebugTraceError
0x1800397df  jmp     loc_180039746
0x1800397e4  mov     edx, [rdi+0Ch]
0x1800397e7  lea     eax, [rdx+0Fh]
0x1800397ea  cmp     r15d, eax
0x1800397ed  jnb     loc_1800A10A0
0x1800397f3  mov     ebx, 0C0000023h
0x1800397f8  jmp     loc_180039746
0x1800397fd  mov     r9d, 19B7h
0x180039803  mov     ecx, eax
0x180039805  jmp     short loc_1800397CC
0x1800a10a0  mov     rax, [rdi+70h]
0x1800a10a4  lea     rcx, [rdx+rbp]
0x1800a10a8  lea     rbp, [rcx+0Fh]
0x1800a10ac  sub     r15d, edx
0x1800a10af  mov     r8d, r15d
0x1800a10b2  lea     rdx, [r14+18h]
0x1800a10b6  shr     r8d, 1
0x1800a10b9  and     rbp, 0FFFFFFFFFFFFFFF0h
0x1800a10bd  sub     r8d, ebp
0x1800a10c0  add     r8d, ecx
0x1800a10c3  mov     ecx, [rsp+98h+dwFlags]
0x1800a10ca  mov     [rsp+98h+var_58], r8d
0x1800a10cf  mov     r9d, r8d
0x1800a10d2  mov     dword ptr [rsp+98h+var_78], ecx
0x1800a10d6  mov     r8, rbp
0x1800a10d9  mov     rcx, [r13+18h]
0x1800a10dd  call    _guard_dispatch_icall
0x1800a10e2  mov     ebx, eax
0x1800a10e4  test    eax, eax
0x1800a10e6  jz      short loc_1800A10F3
0x1800a10e8  mov     r9d, 19A2h
0x1800a10ee  jmp     loc_180039803
0x1800a10f3  mov     r8d, [rsp+98h+var_58]
0x1800a10f8  add     r8, 0Fh
0x1800a10fc  add     r8, rbp
0x1800a10ff  jmp     loc_18003965B
```
