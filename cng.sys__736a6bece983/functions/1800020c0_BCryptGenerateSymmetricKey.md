# BCryptGenerateSymmetricKey

- ea: `0x1800020c0`
- end: `0x1800023cf`
- name: `BCryptGenerateSymmetricKey`
- size: `783`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbKeyObject, ULONG cbKeyObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180083c48`
- `0x1800840cc`
- `0x1800843c0`

## callees

- `0x1800020c0`
- `0x1800039d0`
- `0x180003b10`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18005c44c`
- `0x18009f6d0`

## string_xrefs

- `0x18000223a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000228e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800022da`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000233b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800023a0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x1800020c0  push    rbx
0x1800020c2  push    rbp
0x1800020c3  push    rsi
0x1800020c4  push    rdi
0x1800020c5  push    r12
0x1800020c7  push    r13
0x1800020c9  push    r14
0x1800020cb  push    r15
0x1800020cd  sub     rsp, 68h
0x1800020d1  xor     edi, edi
0x1800020d3  mov     r14d, r9d
0x1800020d6  mov     [rsp+0A8h+var_50], rdi
0x1800020db  mov     rbx, r8
0x1800020de  mov     [rsp+0A8h+var_58], edi
0x1800020e2  mov     r15, rdx
0x1800020e5  mov     rsi, rcx
0x1800020e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020ef  lea     rax, WPP_GLOBAL_Control
0x1800020f6  mov     r13d, [rsp+0A8h+dwFlags]
0x1800020fe  mov     r12, [rsp+0A8h+pbSecret]
0x180002106  cmp     rcx, rax
0x180002109  jz      short loc_180002116
0x18000210b  mov     eax, [rcx+2Ch]
0x18000210e  test    al, 4
0x180002110  jnz     loc_180002357
0x180002116  mov     rcx, rsi
0x180002119  call    ValidateBaseAlgHandle
0x18000211e  mov     rbp, rax
0x180002121  test    rax, rax
0x180002124  jz      loc_180002263
0x18000212a  test    rbx, rbx
0x18000212d  jz      loc_1800021D4
0x180002133  test    r15, r15
0x180002136  jz      loc_18000220B
0x18000213c  test    r12, r12
0x18000213f  jz      loc_18000220B
0x180002145  cmp     r14d, 3Eh ; '>'
0x180002149  jb      loc_180002350
0x18000214f  lea     rsi, [rbx+0Fh]
0x180002153  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180002157  mov     dword ptr [rsi], 20h ; ' '
0x18000215d  mov     dword ptr [rsi+4], 55555552h
0x180002164  mov     [rsi+8], rbp
0x180002168  mov     [rsi+18h], rdi
0x18000216c  mov     ecx, [rbp+24h]
0x18000216f  sub     ecx, 1
0x180002172  jnz     loc_180002391
0x180002178  mov     ecx, [rsp+0A8h+cbSecret]
0x18000217f  lea     r8, [rsi+2Fh]
0x180002183  mov     rax, [rbp+58h]
0x180002187  lea     rdx, [rsi+10h]
0x18000218b  and     r8, 0FFFFFFFFFFFFFFF0h
0x18000218f  mov     [rsp+0A8h+var_78], r13d
0x180002194  mov     dword ptr [rsp+0A8h+var_80], ecx
0x180002198  sub     ebx, r8d
0x18000219b  mov     rcx, [rbp+18h]
0x18000219f  mov     [rsp+0A8h+var_88], r12
0x1800021a4  lea     r9d, [r14+rbx]
0x1800021a8  call    _guard_dispatch_icall
0x1800021ad  mov     ebx, eax
0x1800021af  test    eax, eax
0x1800021b1  js      loc_180002319
0x1800021b7  mov     [r15], rsi
0x1800021ba  xor     ebx, ebx
0x1800021bc  lock inc dword ptr [rbp+10h]
0x1800021c0  mov     eax, ebx
0x1800021c2  add     rsp, 68h
0x1800021c6  pop     r15
0x1800021c8  pop     r14
0x1800021ca  pop     r13
0x1800021cc  pop     r12
0x1800021ce  pop     rdi
0x1800021cf  pop     rsi
0x1800021d0  pop     rbp
0x1800021d1  pop     rbx
0x1800021d2  retn
0x1800021d4  test    r14d, r14d
0x1800021d7  jnz     short loc_180002202
0x1800021d9  lea     r8, [rsp+0A8h+var_58]
0x1800021de  mov     rcx, rsi
0x1800021e1  lea     rdx, [rsp+0A8h+var_50]
0x1800021e6  call    AllocateObjectBuffer
0x1800021eb  mov     ebx, eax
0x1800021ed  test    eax, eax
0x1800021ef  js      loc_1800022BB
0x1800021f5  mov     rdi, [rsp+0A8h+var_50]
0x1800021fa  mov     r14d, [rsp+0A8h+var_58]
0x1800021ff  mov     rbx, rdi
0x180002202  test    rbx, rbx
0x180002205  jnz     loc_180002133
0x18000220b  mov     ebx, 0C000000Dh
0x180002210  mov     rcx, cs:WPP_GLOBAL_Control
0x180002217  lea     rax, WPP_GLOBAL_Control
0x18000221e  cmp     rcx, rax
0x180002221  jz      loc_180002303
0x180002227  mov     eax, [rcx+2Ch]
0x18000222a  test    al, 1
0x18000222c  jz      loc_180002303
0x180002232  mov     [rsp+0A8h+var_78], 0D27h
0x18000223a  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002241  mov     [rsp+0A8h+var_80], rax
0x180002246  mov     dword ptr [rsp+0A8h+var_88], 0C000000Dh
0x18000224e  mov     rcx, [rcx+18h]
0x180002252  lea     r9, aStatus; "Status"
0x180002259  call    WPP_SF_sDsd
0x18000225e  jmp     loc_180002303
0x180002263  mov     ebx, 0C0000008h
0x180002268  mov     rcx, cs:WPP_GLOBAL_Control
0x18000226f  lea     rax, WPP_GLOBAL_Control
0x180002276  cmp     rcx, rax
0x180002279  jz      loc_1800021C0
0x18000227f  mov     eax, [rcx+2Ch]
0x180002282  test    al, 1
0x180002284  jz      loc_1800021C0
0x18000228a  mov     rcx, [rcx+18h]
0x18000228e  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002295  mov     [rsp+0A8h+var_78], 0D08h
0x18000229d  lea     r9, aStatus; "Status"
0x1800022a4  mov     [rsp+0A8h+var_80], rax
0x1800022a9  mov     dword ptr [rsp+0A8h+var_88], 0C0000008h
0x1800022b1  call    WPP_SF_sDsd
0x1800022b6  jmp     loc_1800021C0
0x1800022bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022c2  lea     rax, WPP_GLOBAL_Control
0x1800022c9  cmp     rcx, rax
0x1800022cc  jz      short loc_1800022FE
0x1800022ce  mov     edx, [rcx+2Ch]
0x1800022d1  test    dl, 1
0x1800022d4  jz      short loc_1800022FE
0x1800022d6  mov     rcx, [rcx+18h]
0x1800022da  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800022e1  mov     [rsp+0A8h+var_78], 0D16h
0x1800022e9  lea     r9, aStatus; "Status"
0x1800022f0  mov     [rsp+0A8h+var_80], rax
0x1800022f5  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800022f9  call    WPP_SF_sDsd
0x1800022fe  mov     rdi, [rsp+0A8h+var_50]
0x180002303  test    rdi, rdi
0x180002306  jnz     loc_1800023C2
0x18000230c  test    ebx, ebx
0x18000230e  jns     loc_1800021BC
0x180002314  jmp     loc_1800021C0
0x180002319  mov     rcx, cs:WPP_GLOBAL_Control
0x180002320  lea     rax, WPP_GLOBAL_Control
0x180002327  cmp     rcx, rax
0x18000232a  jz      short loc_180002303
0x18000232c  mov     eax, [rcx+2Ch]
0x18000232f  test    al, 1
0x180002331  jz      short loc_180002303
0x180002333  mov     [rsp+0A8h+var_78], 0D5Bh
0x18000233b  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002342  mov     [rsp+0A8h+var_80], rax
0x180002347  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000234b  jmp     loc_18000224E
0x180002350  mov     ebx, 0C0000023h
0x180002355  jmp     short loc_180002303
0x180002357  mov     eax, [rsp+0A8h+cbSecret]
0x18000235e  mov     edx, 14h
0x180002363  mov     rcx, [rcx+18h]
0x180002367  mov     r9, rsi
0x18000236a  mov     [rsp+0A8h+var_60], r13d
0x18000236f  mov     [rsp+0A8h+var_68], eax
0x180002373  mov     [rsp+0A8h+var_70], r12
0x180002378  mov     [rsp+0A8h+var_78], r14d
0x18000237d  mov     [rsp+0A8h+var_80], rbx
0x180002382  mov     [rsp+0A8h+var_88], r15
0x180002387  call    WPP_SF_qqqdqdD
0x18000238c  jmp     loc_180002116
0x180002391  cmp     ecx, 6
0x180002394  jz      loc_180002178
0x18000239a  mov     r9d, 0D4Ch
0x1800023a0  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800023a7  lea     rdx, aStatus; "Status"
0x1800023ae  mov     ecx, 0C00000BBh
0x1800023b3  mov     ebx, 0C00000BBh
0x1800023b8  call    DebugTraceError
0x1800023bd  jmp     loc_180002303
0x1800023c2  mov     rcx, rdi; P
0x1800023c5  call    MSCryptFree
0x1800023ca  jmp     loc_18000230C
```
