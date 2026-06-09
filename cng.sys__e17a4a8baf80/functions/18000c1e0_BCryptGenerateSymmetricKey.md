# BCryptGenerateSymmetricKey

- ea: `0x18000c1e0`
- end: `0x18000c4ef`
- name: `BCryptGenerateSymmetricKey`
- size: `783`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbKeyObject, ULONG cbKeyObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18008ce48`
- `0x18008d2cc`
- `0x18008d5c0`

## callees

- `0x18000c1e0`
- `0x18000daf0`
- `0x18000dc30`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x180065d2c`
- `0x1800a4300`

## string_xrefs

- `0x18000c35a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c3ae`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c3fa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c45b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c4c0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptGenerateSymmetricKey(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  void *v7; // rdi
  ULONG v8; // r14d
  PUCHAR v9; // rbx
  int v12; // edx
  __int64 v13; // rbp
  int v14; // r8d
  _DWORD *v15; // rsi
  int v16; // edx
  int v17; // ebx
  int v18; // r8d
  int v20; // edx
  ULONG v21; // [rsp+50h] [rbp-58h] BYREF
  void *v22; // [rsp+58h] [rbp-50h] BYREF

  v7 = 0;
  v8 = cbKeyObject;
  v22 = 0;
  v9 = pbKeyObject;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      20,
      pbKeyObject,
      hAlgorithm,
      phKey,
      pbKeyObject,
      cbKeyObject,
      pbSecret,
      cbSecret,
      dwFlags);
  v13 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v13 )
  {
    if ( v9 )
      goto LABEL_7;
    if ( !v8 )
    {
      v17 = AllocateObjectBuffer(hAlgorithm, &v22, &v21);
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v20 = *((_DWORD *)WPP_GLOBAL_Control + 11);
          if ( (v20 & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v20,
              v14,
              (unsigned int)"Status",
              v17,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              22);
        }
        v7 = v22;
        goto LABEL_27;
      }
      v7 = v22;
      v8 = v21;
      v9 = (PUCHAR)v22;
    }
    if ( v9 )
    {
LABEL_7:
      if ( phKey && pbSecret )
      {
        if ( v8 < 0x3E )
        {
          v17 = -1073741789;
        }
        else
        {
          v15 = (_DWORD *)((unsigned __int64)(v9 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
          *v15 = 32;
          v15[1] = 1431655762;
          *((_QWORD *)v15 + 1) = v13;
          *((_QWORD *)v15 + 3) = v7;
          if ( *(_DWORD *)(v13 + 36) == 1 || *(_DWORD *)(v13 + 36) == 7 )
          {
            v17 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, _QWORD, PUCHAR, ULONG, ULONG))(v13 + 88))(
                    *(_QWORD *)(v13 + 24),
                    v15 + 4,
                    ((unsigned __int64)v15 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
                    v8 + (_DWORD)v9 - (((_DWORD)v15 + 47) & 0xFFFFFFF0),
                    pbSecret,
                    cbSecret,
                    dwFlags);
            if ( v17 >= 0 )
            {
              *phKey = v15;
              v17 = 0;
              _InterlockedIncrement((volatile signed __int32 *)(v13 + 16));
              return v17;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v16,
                v18,
                (unsigned int)"Status",
                v17,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                91);
            }
          }
          else
          {
            v17 = -1073741637;
            DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 3404);
          }
        }
        goto LABEL_27;
      }
    }
    v17 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v14,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        39);
LABEL_27:
    if ( v7 )
      MSCryptFree(v7);
    return v17;
  }
  v17 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v12,
      v14,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      8);
  return v17;
}

```

## disassembly

```asm
0x18000c1e0  push    rbx
0x18000c1e2  push    rbp
0x18000c1e3  push    rsi
0x18000c1e4  push    rdi
0x18000c1e5  push    r12
0x18000c1e7  push    r13
0x18000c1e9  push    r14
0x18000c1eb  push    r15
0x18000c1ed  sub     rsp, 68h
0x18000c1f1  xor     edi, edi
0x18000c1f3  mov     r14d, r9d
0x18000c1f6  mov     [rsp+0A8h+var_50], rdi
0x18000c1fb  mov     rbx, r8
0x18000c1fe  mov     [rsp+0A8h+var_58], edi
0x18000c202  mov     r15, rdx
0x18000c205  mov     rsi, rcx
0x18000c208  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c20f  lea     rax, WPP_GLOBAL_Control
0x18000c216  mov     r13d, [rsp+0A8h+dwFlags]
0x18000c21e  mov     r12, [rsp+0A8h+pbSecret]
0x18000c226  cmp     rcx, rax
0x18000c229  jz      short loc_18000C236
0x18000c22b  mov     eax, [rcx+2Ch]
0x18000c22e  test    al, 4
0x18000c230  jnz     loc_18000C477
0x18000c236  mov     rcx, rsi
0x18000c239  call    ValidateBaseAlgHandle
0x18000c23e  mov     rbp, rax
0x18000c241  test    rax, rax
0x18000c244  jz      loc_18000C383
0x18000c24a  test    rbx, rbx
0x18000c24d  jz      loc_18000C2F4
0x18000c253  test    r15, r15
0x18000c256  jz      loc_18000C32B
0x18000c25c  test    r12, r12
0x18000c25f  jz      loc_18000C32B
0x18000c265  cmp     r14d, 3Eh ; '>'
0x18000c269  jb      loc_18000C470
0x18000c26f  lea     rsi, [rbx+0Fh]
0x18000c273  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18000c277  mov     dword ptr [rsi], 20h ; ' '
0x18000c27d  mov     dword ptr [rsi+4], 55555552h
0x18000c284  mov     [rsi+8], rbp
0x18000c288  mov     [rsi+18h], rdi
0x18000c28c  mov     ecx, [rbp+24h]
0x18000c28f  sub     ecx, 1
0x18000c292  jnz     loc_18000C4B1
0x18000c298  mov     ecx, [rsp+0A8h+cbSecret]
0x18000c29f  lea     r8, [rsi+2Fh]
0x18000c2a3  mov     rax, [rbp+58h]
0x18000c2a7  lea     rdx, [rsi+10h]
0x18000c2ab  and     r8, 0FFFFFFFFFFFFFFF0h
0x18000c2af  mov     [rsp+0A8h+var_78], r13d
0x18000c2b4  mov     dword ptr [rsp+0A8h+var_80], ecx
0x18000c2b8  sub     ebx, r8d
0x18000c2bb  mov     rcx, [rbp+18h]
0x18000c2bf  mov     [rsp+0A8h+var_88], r12
0x18000c2c4  lea     r9d, [r14+rbx]
0x18000c2c8  call    _guard_dispatch_icall
0x18000c2cd  mov     ebx, eax
0x18000c2cf  test    eax, eax
0x18000c2d1  js      loc_18000C439
0x18000c2d7  mov     [r15], rsi
0x18000c2da  xor     ebx, ebx
0x18000c2dc  lock inc dword ptr [rbp+10h]
0x18000c2e0  mov     eax, ebx
0x18000c2e2  add     rsp, 68h
0x18000c2e6  pop     r15
0x18000c2e8  pop     r14
0x18000c2ea  pop     r13
0x18000c2ec  pop     r12
0x18000c2ee  pop     rdi
0x18000c2ef  pop     rsi
0x18000c2f0  pop     rbp
0x18000c2f1  pop     rbx
0x18000c2f2  retn
0x18000c2f4  test    r14d, r14d
0x18000c2f7  jnz     short loc_18000C322
0x18000c2f9  lea     r8, [rsp+0A8h+var_58]
0x18000c2fe  mov     rcx, rsi
0x18000c301  lea     rdx, [rsp+0A8h+var_50]
0x18000c306  call    AllocateObjectBuffer
0x18000c30b  mov     ebx, eax
0x18000c30d  test    eax, eax
0x18000c30f  js      loc_18000C3DB
0x18000c315  mov     rdi, [rsp+0A8h+var_50]
0x18000c31a  mov     r14d, [rsp+0A8h+var_58]
0x18000c31f  mov     rbx, rdi
0x18000c322  test    rbx, rbx
0x18000c325  jnz     loc_18000C253
0x18000c32b  mov     ebx, 0C000000Dh
0x18000c330  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c337  lea     rax, WPP_GLOBAL_Control
0x18000c33e  cmp     rcx, rax
0x18000c341  jz      loc_18000C423
0x18000c347  mov     eax, [rcx+2Ch]
0x18000c34a  test    al, 1
0x18000c34c  jz      loc_18000C423
0x18000c352  mov     [rsp+0A8h+var_78], 0D27h
0x18000c35a  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c361  mov     [rsp+0A8h+var_80], rax
0x18000c366  mov     dword ptr [rsp+0A8h+var_88], 0C000000Dh
0x18000c36e  mov     rcx, [rcx+18h]
0x18000c372  lea     r9, aStatus; "Status"
0x18000c379  call    WPP_SF_sDsd
0x18000c37e  jmp     loc_18000C423
0x18000c383  mov     ebx, 0C0000008h
0x18000c388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c38f  lea     rax, WPP_GLOBAL_Control
0x18000c396  cmp     rcx, rax
0x18000c399  jz      loc_18000C2E0
0x18000c39f  mov     eax, [rcx+2Ch]
0x18000c3a2  test    al, 1
0x18000c3a4  jz      loc_18000C2E0
0x18000c3aa  mov     rcx, [rcx+18h]
0x18000c3ae  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c3b5  mov     [rsp+0A8h+var_78], 0D08h
0x18000c3bd  lea     r9, aStatus; "Status"
0x18000c3c4  mov     [rsp+0A8h+var_80], rax
0x18000c3c9  mov     dword ptr [rsp+0A8h+var_88], 0C0000008h
0x18000c3d1  call    WPP_SF_sDsd
0x18000c3d6  jmp     loc_18000C2E0
0x18000c3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3e2  lea     rax, WPP_GLOBAL_Control
0x18000c3e9  cmp     rcx, rax
0x18000c3ec  jz      short loc_18000C41E
0x18000c3ee  mov     edx, [rcx+2Ch]
0x18000c3f1  test    dl, 1
0x18000c3f4  jz      short loc_18000C41E
0x18000c3f6  mov     rcx, [rcx+18h]
0x18000c3fa  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c401  mov     [rsp+0A8h+var_78], 0D16h
0x18000c409  lea     r9, aStatus; "Status"
0x18000c410  mov     [rsp+0A8h+var_80], rax
0x18000c415  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000c419  call    WPP_SF_sDsd
0x18000c41e  mov     rdi, [rsp+0A8h+var_50]
0x18000c423  test    rdi, rdi
0x18000c426  jnz     loc_18000C4E2
0x18000c42c  test    ebx, ebx
0x18000c42e  jns     loc_18000C2DC
0x18000c434  jmp     loc_18000C2E0
0x18000c439  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c440  lea     rax, WPP_GLOBAL_Control
0x18000c447  cmp     rcx, rax
0x18000c44a  jz      short loc_18000C423
0x18000c44c  mov     eax, [rcx+2Ch]
0x18000c44f  test    al, 1
0x18000c451  jz      short loc_18000C423
0x18000c453  mov     [rsp+0A8h+var_78], 0D5Bh
0x18000c45b  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c462  mov     [rsp+0A8h+var_80], rax
0x18000c467  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000c46b  jmp     loc_18000C36E
0x18000c470  mov     ebx, 0C0000023h
0x18000c475  jmp     short loc_18000C423
0x18000c477  mov     eax, [rsp+0A8h+cbSecret]
0x18000c47e  mov     edx, 14h
0x18000c483  mov     rcx, [rcx+18h]
0x18000c487  mov     r9, rsi
0x18000c48a  mov     [rsp+0A8h+var_60], r13d
0x18000c48f  mov     [rsp+0A8h+var_68], eax
0x18000c493  mov     [rsp+0A8h+var_70], r12
0x18000c498  mov     [rsp+0A8h+var_78], r14d
0x18000c49d  mov     [rsp+0A8h+var_80], rbx
0x18000c4a2  mov     [rsp+0A8h+var_88], r15
0x18000c4a7  call    WPP_SF_qqqdqdD
0x18000c4ac  jmp     loc_18000C236
0x18000c4b1  cmp     ecx, 6
0x18000c4b4  jz      loc_18000C298
0x18000c4ba  mov     r9d, 0D4Ch
0x18000c4c0  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c4c7  lea     rdx, aStatus; "Status"
0x18000c4ce  mov     ecx, 0C00000BBh
0x18000c4d3  mov     ebx, 0C00000BBh
0x18000c4d8  call    DebugTraceError
0x18000c4dd  jmp     loc_18000C423
0x18000c4e2  mov     rcx, rdi; P
0x18000c4e5  call    MSCryptFree
0x18000c4ea  jmp     loc_18000C42C
```
