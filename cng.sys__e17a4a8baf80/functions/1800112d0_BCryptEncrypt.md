# BCryptEncrypt

- ea: `0x1800112d0`
- end: `0x180011555`
- name: `BCryptEncrypt`
- size: `645`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, void *pPaddingInfo, PUCHAR pbIV, ULONG cbIV, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180010e10`
- `0x18004899c`
- `0x180048d30`

## callees

- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x1800112d0`
- `0x18001155c`
- `0x1800123d0`
- `0x1800619c0`
- `0x180065dcc`
- `0x180073148`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180011398`
- `ntoskrnl!KeGetCurrentIrql` at `0x180011398`

## string_xrefs

- `0x180011377`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180011466`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800114b1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a5d54`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptEncrypt(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        void *pPaddingInfo,
        PUCHAR pbIV,
        ULONG cbIV,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  ULONG v10; // r10d
  PUCHAR v11; // r11
  NTSTATUS v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r9
  UCHAR *v17; // rsi
  __int64 (__fastcall *v18)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG); // r14
  int v19; // eax
  int v21; // eax
  __int64 v22; // r9
  NTSTATUS Property; // eax
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  __int64 v27; // r9
  UCHAR v28[4]; // [rsp+60h] [rbp-48h] BYREF
  int v29; // [rsp+64h] [rbp-44h] BYREF
  ULONG v30[16]; // [rsp+68h] [rbp-40h] BYREF

  v10 = cbInput;
  v29 = 0;
  v11 = pbInput;
  *(_DWORD *)v28 = 0;
  v30[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
  {
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      23,
      cbInput,
      hKey,
      pPaddingInfo,
      pbInput,
      cbInput,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
    v10 = cbInput;
    v11 = pbInput;
  }
  if ( pcbResult )
  {
    if ( !hKey || *(_DWORD *)hKey < 0x20u || *((_DWORD *)hKey + 1) != 1431655762 )
      goto LABEL_8;
    if ( !*(_DWORD *)(*((_QWORD *)hKey + 1) + 32LL) )
    {
      if ( KeGetCurrentIrql() >= 2u )
      {
LABEL_8:
        v13 = -1073741816;
        v14 = 3922;
        v15 = 3221225480LL;
LABEL_9:
        DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v14);
        return v13;
      }
      v10 = cbInput;
      v11 = pbInput;
    }
    v16 = *((_QWORD *)hKey + 1);
    v17 = 0;
    if ( *(_DWORD *)(v16 + 36) == 1 )
    {
      v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 96);
LABEL_15:
      v19 = v18(*((_QWORD *)hKey + 2), v11, v10, pPaddingInfo, pbIV, cbIV, pbOutput, cbOutput, pcbResult, dwFlags);
      v13 = v19;
      if ( v19 < 0 )
      {
        v14 = 4062;
        v15 = (unsigned int)v19;
        goto LABEL_9;
      }
      goto LABEL_16;
    }
    if ( *(_DWORD *)(v16 + 36) != 3 )
    {
      v13 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (_DWORD)pbInput,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          137);
      return v13;
    }
    v21 = ShouldRouterPadEncryption(*(unsigned int *)(v16 + 440), dwFlags, &v29);
    v13 = v21;
    if ( v21 < 0 )
    {
      v14 = 3953;
      v15 = (unsigned int)v21;
      goto LABEL_9;
    }
    v18 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))(v22 + 104);
    if ( !v29 )
      goto LABEL_15;
    Property = BCryptGetProperty(hKey, L"KeyStrength", v28, 4u, v30, 0);
    v13 = Property;
    if ( Property < 0 )
    {
      v14 = 3968;
      v15 = (unsigned int)Property;
      goto LABEL_9;
    }
    v10 = cbInput;
    v11 = pbInput;
    *(_DWORD *)v28 = (unsigned int)(*(_DWORD *)v28 + 7) >> 3;
    if ( !v29 )
      goto LABEL_15;
    if ( !pbOutput )
    {
      v25 = v18(*((_QWORD *)hKey + 2), pbInput, cbInput, 0, pbIV, cbIV, 0, cbOutput, pcbResult, 0);
      v13 = v25;
      if ( v25 < 0 )
      {
        v14 = 3998;
        v15 = (unsigned int)v25;
        goto LABEL_9;
      }
      goto LABEL_16;
    }
    v17 = (UCHAR *)MSCryptAlloc(*(unsigned int *)v28, v24);
    if ( !v17 )
    {
      v13 = -1073741801;
      v14 = 4014;
      v15 = 3221225495LL;
      goto LABEL_9;
    }
    v26 = ApplyEncryptionPadding(dwFlags, pPaddingInfo, pbInput, cbInput, v17, *(_DWORD *)v28);
    v13 = v26;
    if ( v26 >= 0 )
    {
      v26 = v18(*((_QWORD *)hKey + 2), v17, cbOutput, 0, pbIV, cbIV, pbOutput, cbOutput, pcbResult, 0);
      v13 = v26;
      if ( v26 >= 0 )
      {
LABEL_16:
        v13 = 0;
        if ( !v17 )
          return v13;
LABEL_28:
        MSCryptFree(v17);
        return v13;
      }
      v27 = 4043;
    }
    else
    {
      v27 = 4027;
    }
    DebugTraceError((unsigned int)v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v27);
    goto LABEL_28;
  }
  v13 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)pbInput,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      74);
  return v13;
}

```

## disassembly

```asm
0x1800112d0  mov     [rsp+arg_18], r9
0x1800112d5  mov     [rsp+arg_10], r8d
0x1800112da  mov     [rsp+arg_8], rdx
0x1800112df  push    rbx
0x1800112e0  push    rbp
0x1800112e1  push    rdi
0x1800112e2  push    r12
0x1800112e4  push    r13
0x1800112e6  push    r14
0x1800112e8  push    r15
0x1800112ea  sub     rsp, 70h
0x1800112ee  xor     ebx, ebx
0x1800112f0  mov     r10d, r8d
0x1800112f3  mov     [rsp+0A8h+var_44], ebx
0x1800112f7  mov     r11, rdx
0x1800112fa  mov     dword ptr [rsp+0A8h+var_48], ebx
0x1800112fe  mov     rdi, rcx
0x180011301  mov     [rsp+0A8h+var_40], ebx
0x180011305  mov     rcx, cs:WPP_GLOBAL_Control
0x18001130c  lea     r14, WPP_GLOBAL_Control
0x180011313  mov     r13d, [rsp+0A8h+dwFlags]
0x18001131b  mov     rbp, [rsp+0A8h+pcbResult]
0x180011323  mov     r12d, [rsp+0A8h+cbOutput]
0x18001132b  mov     r15, [rsp+0A8h+pbOutput]
0x180011333  cmp     rcx, r14
0x180011336  jz      short loc_180011343
0x180011338  mov     eax, [rcx+2Ch]
0x18001133b  test    al, 4
0x18001133d  jnz     loc_1800114C7
0x180011343  mov     [rsp+0A8h+arg_0], rsi
0x18001134b  test    rbp, rbp
0x18001134e  jz      loc_180011446
0x180011354  test    rdi, rdi
0x180011357  jz      short loc_180011367
0x180011359  cmp     dword ptr [rdi], 20h ; ' '
0x18001135c  jb      short loc_180011367
0x18001135e  cmp     dword ptr [rdi+4], 55555552h
0x180011365  jz      short loc_18001138F
0x180011367  mov     ebx, 0C0000008h
0x18001136c  mov     r9d, 0F52h
0x180011372  mov     ecx, 0C0000008h
0x180011377  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001137e  lea     rdx, aStatus; "Status"
0x180011385  call    DebugTraceError
0x18001138a  jmp     loc_18001142B
0x18001138f  mov     rax, [rdi+8]
0x180011393  cmp     [rax+20h], ebx
0x180011396  jnz     short loc_1800113B8
0x180011398  call    cs:__imp_KeGetCurrentIrql
0x18001139f  nop     dword ptr [rax+rax+00h]
0x1800113a4  cmp     al, 2
0x1800113a6  jnb     short loc_180011367
0x1800113a8  mov     r10d, [rsp+0A8h+arg_10]
0x1800113b0  mov     r11, [rsp+0A8h+arg_8]
0x1800113b8  mov     r9, [rdi+8]
0x1800113bc  mov     rsi, rbx
0x1800113bf  mov     ecx, [r9+24h]
0x1800113c3  sub     ecx, 1
0x1800113c6  jnz     loc_18001148C
0x1800113cc  mov     r14, [r9+60h]
0x1800113d0  mov     eax, [rsp+0A8h+cbIV]
0x1800113d7  mov     r8d, r10d
0x1800113da  mov     r9, [rsp+0A8h+arg_18]
0x1800113e2  mov     rdx, r11
0x1800113e5  mov     rcx, [rdi+10h]
0x1800113e9  mov     dword ptr [rsp+0A8h+var_60], r13d
0x1800113ee  mov     [rsp+0A8h+var_68], rbp
0x1800113f3  mov     dword ptr [rsp+0A8h+var_70], r12d
0x1800113f8  mov     [rsp+0A8h+var_78], r15
0x1800113fd  mov     [rsp+0A8h+var_80], eax
0x180011401  mov     rax, [rsp+0A8h+pbIV]
0x180011409  mov     [rsp+0A8h+var_88], rax
0x18001140e  mov     rax, r14
0x180011411  call    _guard_dispatch_icall
0x180011416  mov     ebx, eax
0x180011418  test    eax, eax
0x18001141a  js      loc_18001153B
0x180011420  xor     ebx, ebx
0x180011422  test    rsi, rsi
0x180011425  jnz     loc_180011548
0x18001142b  mov     rsi, [rsp+0A8h+arg_0]
0x180011433  mov     eax, ebx
0x180011435  add     rsp, 70h
0x180011439  pop     r15
0x18001143b  pop     r14
0x18001143d  pop     r13
0x18001143f  pop     r12
0x180011441  pop     rdi
0x180011442  pop     rbp
0x180011443  pop     rbx
0x180011444  retn
0x180011446  mov     ebx, 0C000000Dh
0x18001144b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011452  cmp     rcx, r14
0x180011455  jz      short loc_18001142B
0x180011457  mov     eax, [rcx+2Ch]
0x18001145a  test    al, 1
0x18001145c  jz      short loc_18001142B
0x18001145e  mov     dword ptr [rsp+0A8h+var_78], 0F4Ah
0x180011466  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001146d  mov     qword ptr [rsp+0A8h+var_80], r8
0x180011472  mov     dword ptr [rsp+0A8h+var_88], 0C000000Dh
0x18001147a  mov     rcx, [rcx+18h]
0x18001147e  lea     r9, aStatus; "Status"
0x180011485  call    WPP_SF_sDsd
0x18001148a  jmp     short loc_18001142B
0x18001148c  cmp     ecx, 2
0x18001148f  jz      short loc_180011510
0x180011491  mov     ebx, 0C00000BBh
0x180011496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001149d  cmp     rcx, r14
0x1800114a0  jz      short loc_18001142B
0x1800114a2  mov     eax, [rcx+2Ch]
0x1800114a5  test    al, 1
0x1800114a7  jz      short loc_18001142B
0x1800114a9  mov     dword ptr [rsp+0A8h+var_78], 0F89h
0x1800114b1  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800114b8  mov     qword ptr [rsp+0A8h+var_80], r8
0x1800114bd  mov     dword ptr [rsp+0A8h+var_88], 0C00000BBh
0x1800114c5  jmp     short loc_18001147A
0x1800114c7  mov     rcx, [rcx+18h]
0x1800114cb  mov     edx, 17h
0x1800114d0  mov     [rsp+0A8h+var_58], r13d
0x1800114d5  mov     [rsp+0A8h+var_60], rbp
0x1800114da  mov     dword ptr [rsp+0A8h+var_68], r12d
0x1800114df  mov     [rsp+0A8h+var_70], r15
0x1800114e4  mov     dword ptr [rsp+0A8h+var_78], r8d
0x1800114e9  mov     qword ptr [rsp+0A8h+var_80], r11
0x1800114ee  mov     [rsp+0A8h+var_88], r9
0x1800114f3  mov     r9, rdi
0x1800114f6  call    WPP_SF_qqqdqdqD
0x1800114fb  mov     r10d, [rsp+0A8h+arg_10]
0x180011503  mov     r11, [rsp+0A8h+arg_8]
0x18001150b  jmp     loc_180011343
0x180011510  mov     ecx, [r9+1B8h]
0x180011517  lea     r8, [rsp+0A8h+var_44]
0x18001151c  mov     edx, r13d
0x18001151f  call    ShouldRouterPadEncryption
0x180011524  mov     ebx, eax
0x180011526  test    eax, eax
0x180011528  jns     loc_1800A5C1C
0x18001152e  mov     r9d, 0F71h
0x180011534  mov     ecx, eax
0x180011536  jmp     loc_180011377
0x18001153b  mov     r9d, 0FDEh
0x180011541  mov     ecx, eax
0x180011543  jmp     loc_180011377
0x180011548  mov     rcx, rsi; P
0x18001154b  call    MSCryptFree
0x180011550  jmp     loc_18001142B
0x1800a5c1c  mov     eax, [rsp+0A8h+var_44]
0x1800a5c20  mov     r14, [r9+68h]
0x1800a5c24  test    eax, eax
0x1800a5c26  jz      loc_1800113D0
0x1800a5c2c  lea     rax, [rsp+0A8h+var_40]
0x1800a5c31  mov     [rsp+0A8h+var_80], esi; dwFlags
0x1800a5c35  mov     r9d, 4; cbOutput
0x1800a5c3b  mov     [rsp+0A8h+var_88], rax; pcbResult
0x1800a5c40  lea     r8, [rsp+0A8h+var_48]; pbOutput
0x1800a5c45  mov     rcx, rdi; hObject
0x1800a5c48  lea     rdx, aKeystrength; "KeyStrength"
0x1800a5c4f  call    BCryptGetProperty
0x1800a5c54  mov     ebx, eax
0x1800a5c56  test    eax, eax
0x1800a5c58  jns     short loc_1800A5C67
0x1800a5c5a  mov     r9d, 0F80h
0x1800a5c60  mov     ecx, eax
0x1800a5c62  jmp     loc_180011377
0x1800a5c67  mov     eax, dword ptr [rsp+0A8h+var_48]
0x1800a5c6b  mov     r10d, [rsp+0A8h+arg_10]
0x1800a5c73  add     eax, 7
0x1800a5c76  mov     r11, [rsp+0A8h+arg_8]
0x1800a5c7e  shr     eax, 3
0x1800a5c81  mov     dword ptr [rsp+0A8h+var_48], eax
0x1800a5c85  mov     eax, [rsp+0A8h+var_44]
0x1800a5c89  test    eax, eax
0x1800a5c8b  jz      loc_1800113D0
0x1800a5c91  test    r15, r15
0x1800a5c94  jnz     short loc_1800A5CED
0x1800a5c96  mov     ecx, [rsp+0A8h+cbIV]
0x1800a5c9d  xor     r9d, r9d
0x1800a5ca0  mov     dword ptr [rsp+0A8h+var_60], esi
0x1800a5ca4  mov     r8d, r10d
0x1800a5ca7  mov     [rsp+0A8h+var_68], rbp
0x1800a5cac  mov     rdx, r11
0x1800a5caf  mov     dword ptr [rsp+0A8h+var_70], r12d
0x1800a5cb4  mov     rax, r14
0x1800a5cb7  mov     [rsp+0A8h+var_78], rsi
0x1800a5cbc  mov     [rsp+0A8h+var_80], ecx
0x1800a5cc0  mov     rcx, [rsp+0A8h+pbIV]
0x1800a5cc8  mov     [rsp+0A8h+var_88], rcx
0x1800a5ccd  mov     rcx, [rdi+10h]
0x1800a5cd1  call    _guard_dispatch_icall
0x1800a5cd6  mov     ebx, eax
0x1800a5cd8  test    eax, eax
0x1800a5cda  jns     loc_180011420
0x1800a5ce0  mov     r9d, 0F9Eh
0x1800a5ce6  mov     ecx, eax
0x1800a5ce8  jmp     loc_180011377
0x1800a5ced  mov     ecx, dword ptr [rsp+0A8h+var_48]
0x1800a5cf1  call    MSCryptAlloc
0x1800a5cf6  mov     rsi, rax
0x1800a5cf9  test    rax, rax
0x1800a5cfc  jnz     short loc_1800A5D13
0x1800a5cfe  mov     ebx, 0C0000017h
0x1800a5d03  mov     r9d, 0FAEh
0x1800a5d09  mov     ecx, 0C0000017h
0x1800a5d0e  jmp     loc_180011377
0x1800a5d13  mov     eax, dword ptr [rsp+0A8h+var_48]
0x1800a5d17  mov     ecx, r13d
0x1800a5d1a  mov     r9d, [rsp+0A8h+arg_10]
0x1800a5d22  mov     r8, [rsp+0A8h+arg_8]
0x1800a5d2a  mov     rdx, [rsp+0A8h+arg_18]
0x1800a5d32  mov     [rsp+0A8h+var_80], eax
0x1800a5d36  mov     [rsp+0A8h+var_88], rsi
0x1800a5d3b  call    ApplyEncryptionPadding
0x1800a5d40  mov     ebx, eax
0x1800a5d42  test    eax, eax
0x1800a5d44  jns     short loc_1800A5D6F
0x1800a5d46  mov     r9d, 0FBBh
0x1800a5d4c  jmp     short loc_1800A5D54
0x1800a5d4e  mov     r9d, 0FCBh
0x1800a5d54  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5d5b  mov     ecx, eax
0x1800a5d5d  lea     rdx, aStatus; "Status"
0x1800a5d64  call    DebugTraceError
0x1800a5d69  nop
0x1800a5d6a  jmp     loc_180011548
0x1800a5d6f  mov     eax, [rsp+0A8h+cbIV]
0x1800a5d76  xor     r9d, r9d
0x1800a5d79  mov     rcx, [rdi+10h]
0x1800a5d7d  mov     r8d, r12d
0x1800a5d80  mov     dword ptr [rsp+0A8h+var_60], 0
0x1800a5d88  mov     rdx, rsi
0x1800a5d8b  mov     [rsp+0A8h+var_68], rbp
0x1800a5d90  mov     dword ptr [rsp+0A8h+var_70], r12d
0x1800a5d95  mov     [rsp+0A8h+var_78], r15
0x1800a5d9a  mov     [rsp+0A8h+var_80], eax
0x1800a5d9e  mov     rax, [rsp+0A8h+pbIV]
0x1800a5da6  mov     [rsp+0A8h+var_88], rax
0x1800a5dab  mov     rax, r14
0x1800a5dae  call    _guard_dispatch_icall
0x1800a5db3  mov     ebx, eax
0x1800a5db5  test    eax, eax
0x1800a5db7  jns     loc_180011420
0x1800a5dbd  jmp     short loc_1800A5D4E
```
