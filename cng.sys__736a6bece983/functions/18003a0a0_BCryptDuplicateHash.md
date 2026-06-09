# BCryptDuplicateHash

- ea: `0x18003a0a0`
- end: `0x18003a307`
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
- `0x18003a0a0`
- `0x18003a310`
- `0x18005c3c0`
- `0x18009f6d0`

## string_xrefs

- `0x18003a1cf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003a21e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003a2d3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18003a0a0  push    rbx
0x18003a0a2  push    rbp
0x18003a0a3  push    rsi
0x18003a0a4  push    rdi
0x18003a0a5  push    r12
0x18003a0a7  push    r13
0x18003a0a9  push    r14
0x18003a0ab  push    r15
0x18003a0ad  sub     rsp, 58h
0x18003a0b1  xor     esi, esi
0x18003a0b3  mov     ebx, r9d
0x18003a0b6  mov     [rsp+98h+var_50], rsi
0x18003a0bb  mov     rbp, r8
0x18003a0be  mov     [rsp+98h+var_58], esi
0x18003a0c2  mov     r12, rdx
0x18003a0c5  mov     rdi, rcx
0x18003a0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0cf  lea     r14, WPP_GLOBAL_Control
0x18003a0d6  cmp     rcx, r14
0x18003a0d9  jz      short loc_18003A0E6
0x18003a0db  mov     eax, [rcx+2Ch]
0x18003a0de  test    al, 4
0x18003a0e0  jnz     loc_18003A25C
0x18003a0e6  mov     rcx, rdi
0x18003a0e9  call    ValidateBaseHashHandle
0x18003a0ee  mov     r13, rax
0x18003a0f1  test    rax, rax
0x18003a0f4  jz      loc_18003A1B3
0x18003a0fa  mov     rdi, [rax+8]
0x18003a0fe  test    rbp, rbp
0x18003a101  jz      loc_18003A28B
0x18003a107  test    r12, r12
0x18003a10a  jz      loc_18003A202
0x18003a110  cmp     ebx, 46h ; 'F'
0x18003a113  jb      loc_18003A2BC
0x18003a119  lea     r14, [rbp+0Fh]
0x18003a11d  and     r14, 0FFFFFFFFFFFFFFF0h
0x18003a121  mov     eax, r14d
0x18003a124  sub     eax, ebp
0x18003a126  add     rbp, 28h ; '('
0x18003a12a  sub     ebx, eax
0x18003a12c  mov     ecx, eax
0x18003a12e  add     rbp, rcx
0x18003a131  mov     dword ptr [r14], 28h ; '('
0x18003a138  mov     dword ptr [r14+4], 55555553h
0x18003a140  mov     [r14+8], rdi
0x18003a144  mov     [r14+20h], rsi
0x18003a148  lea     r15d, [rbx-28h]
0x18003a14c  mov     eax, [rdi+8]
0x18003a14f  test    al, 8
0x18003a151  jnz     loc_18003A2E4
0x18003a157  lea     r8, [rbp+0Fh]
0x18003a15b  mov     ecx, [rsp+98h+dwFlags]
0x18003a162  lea     rdx, [r14+10h]
0x18003a166  mov     rax, [rdi+70h]
0x18003a16a  and     r8, 0FFFFFFFFFFFFFFF0h
0x18003a16e  sub     ebp, r8d
0x18003a171  mov     dword ptr [rsp+98h+var_78], ecx
0x18003a175  mov     rcx, [r13+10h]
0x18003a179  add     ebp, r15d
0x18003a17c  mov     r9d, ebp
0x18003a17f  call    _guard_dispatch_icall
0x18003a184  mov     ebx, eax
0x18003a186  test    eax, eax
0x18003a188  jnz     loc_18003A2FD
0x18003a18e  mov     [r12], r14
0x18003a192  test    rdi, rdi
0x18003a195  jz      short loc_18003A19F
0x18003a197  test    ebx, ebx
0x18003a199  js      short loc_18003A19F
0x18003a19b  lock inc dword ptr [rdi+10h]
0x18003a19f  mov     eax, ebx
0x18003a1a1  add     rsp, 58h
0x18003a1a5  pop     r15
0x18003a1a7  pop     r14
0x18003a1a9  pop     r13
0x18003a1ab  pop     r12
0x18003a1ad  pop     rdi
0x18003a1ae  pop     rsi
0x18003a1af  pop     rbp
0x18003a1b0  pop     rbx
0x18003a1b1  retn
0x18003a1b3  mov     ebx, 0C0000008h
0x18003a1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1bf  cmp     rcx, r14
0x18003a1c2  jz      short loc_18003A19F
0x18003a1c4  mov     eax, [rcx+2Ch]
0x18003a1c7  test    al, 1
0x18003a1c9  jz      short loc_18003A19F
0x18003a1cb  mov     rcx, [rcx+18h]
0x18003a1cf  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a1d6  mov     [rsp+98h+var_68], 1947h
0x18003a1de  lea     r9, aStatus; "Status"
0x18003a1e5  mov     [rsp+98h+var_70], rax
0x18003a1ea  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x18003a1f2  call    WPP_SF_sDsd
0x18003a1f7  jmp     short loc_18003A19F
0x18003a1f9  test    rbp, rbp
0x18003a1fc  jnz     loc_18003A107
0x18003a202  mov     ebx, 0C000000Dh
0x18003a207  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a20e  cmp     rcx, r14
0x18003a211  jz      short loc_18003A246
0x18003a213  mov     eax, [rcx+2Ch]
0x18003a216  test    al, 1
0x18003a218  jz      short loc_18003A246
0x18003a21a  mov     rcx, [rcx+18h]
0x18003a21e  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a225  mov     [rsp+98h+var_68], 1966h
0x18003a22d  lea     r9, aStatus; "Status"
0x18003a234  mov     [rsp+98h+var_70], rax
0x18003a239  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x18003a241  call    WPP_SF_sDsd
0x18003a246  test    rsi, rsi
0x18003a249  jz      loc_18003A192
0x18003a24f  mov     rcx, rsi; P
0x18003a252  call    MSCryptFree
0x18003a257  jmp     loc_18003A192
0x18003a25c  mov     eax, [rsp+98h+dwFlags]
0x18003a263  mov     edx, 25h ; '%'
0x18003a268  mov     rcx, [rcx+18h]
0x18003a26c  mov     r9, rdi
0x18003a26f  mov     [rsp+98h+var_60], eax
0x18003a273  mov     [rsp+98h+var_68], ebx
0x18003a277  mov     [rsp+98h+var_70], rbp
0x18003a27c  mov     [rsp+98h+var_78], r12
0x18003a281  call    WPP_SF_qqqdD
0x18003a286  jmp     loc_18003A0E6
0x18003a28b  test    ebx, ebx
0x18003a28d  jnz     loc_18003A1F9
0x18003a293  lea     r8, [rsp+98h+var_58]
0x18003a298  mov     rcx, rdi
0x18003a29b  lea     rdx, [rsp+98h+var_50]
0x18003a2a0  call    AllocateObjectBuffer
0x18003a2a5  mov     rsi, [rsp+98h+var_50]
0x18003a2aa  mov     ebx, eax
0x18003a2ac  test    eax, eax
0x18003a2ae  js      short loc_18003A246
0x18003a2b0  mov     ebx, [rsp+98h+var_58]
0x18003a2b4  mov     rbp, rsi
0x18003a2b7  jmp     loc_18003A1F9
0x18003a2bc  mov     ebx, 0C0000023h
0x18003a2c1  mov     r9d, 196Dh
0x18003a2c7  mov     ecx, 0C0000023h
0x18003a2cc  lea     rdx, aStatus; "Status"
0x18003a2d3  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a2da  call    DebugTraceError
0x18003a2df  jmp     loc_18003A246
0x18003a2e4  mov     edx, [rdi+0Ch]
0x18003a2e7  lea     eax, [rdx+0Fh]
0x18003a2ea  cmp     r15d, eax
0x18003a2ed  jnb     loc_1800A2ED0
0x18003a2f3  mov     ebx, 0C0000023h
0x18003a2f8  jmp     loc_18003A246
0x18003a2fd  mov     r9d, 19B7h
0x18003a303  mov     ecx, eax
0x18003a305  jmp     short loc_18003A2CC
0x1800a2ed0  mov     rax, [rdi+70h]
0x1800a2ed4  lea     rcx, [rdx+rbp]
0x1800a2ed8  lea     rbp, [rcx+0Fh]
0x1800a2edc  sub     r15d, edx
0x1800a2edf  mov     r8d, r15d
0x1800a2ee2  lea     rdx, [r14+18h]
0x1800a2ee6  shr     r8d, 1
0x1800a2ee9  and     rbp, 0FFFFFFFFFFFFFFF0h
0x1800a2eed  sub     r8d, ebp
0x1800a2ef0  add     r8d, ecx
0x1800a2ef3  mov     ecx, [rsp+98h+dwFlags]
0x1800a2efa  mov     [rsp+98h+var_58], r8d
0x1800a2eff  mov     r9d, r8d
0x1800a2f02  mov     dword ptr [rsp+98h+var_78], ecx
0x1800a2f06  mov     r8, rbp
0x1800a2f09  mov     rcx, [r13+18h]
0x1800a2f0d  call    _guard_dispatch_icall
0x1800a2f12  mov     ebx, eax
0x1800a2f14  test    eax, eax
0x1800a2f16  jz      short loc_1800A2F23
0x1800a2f18  mov     r9d, 19A2h
0x1800a2f1e  jmp     loc_18003A303
0x1800a2f23  mov     r8d, [rsp+98h+var_58]
0x1800a2f28  add     r8, 0Fh
0x1800a2f2c  add     r8, rbp
0x1800a2f2f  jmp     loc_18003A15B
```
