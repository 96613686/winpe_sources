# BCryptKeyDerivation

- ea: `0x18003f740`
- end: `0x18003f905`
- name: `BCryptKeyDerivation`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008d0d4`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18003f740`
- `0x18003f910`
- `0x180065c08`
- `0x1800a4300`

## string_xrefs

- `0x18003f81b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f85d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f89b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f8e3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptKeyDerivation(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, int a6)
{
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  int v16; // r8d
  int v18; // edx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqDqD(*((_QWORD *)WPP_GLOBAL_Control + 3), a2, a3, a1, a2, a3, a4, a5, a6);
  if ( a5 && a3 && a4 )
  {
    v10 = ValidateBaseKeyHandle(a1);
    v13 = v10;
    if ( v10 )
    {
      v14 = *(_QWORD *)(v10 + 8);
      if ( *(_DWORD *)(v14 + 36) == 7 )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, int))(v14 + 104))(
                *(_QWORD *)(v13 + 16),
                a2,
                a3,
                a4,
                a5,
                a6);
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v18 = *((_DWORD *)WPP_GLOBAL_Control + 11);
            if ( (v18 & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v18,
                v16,
                (unsigned int)"Status",
                v15,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                32);
          }
        }
        else
        {
          return 0;
        }
      }
      else
      {
        v15 = -1073741637;
        DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7700);
      }
    }
    else
    {
      v15 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v11,
          v12,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          7);
    }
  }
  else
  {
    v15 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        255);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003f740  push    rbx
0x18003f742  push    rbp
0x18003f743  push    rsi
0x18003f744  push    rdi
0x18003f745  push    r12
0x18003f747  push    r14
0x18003f749  push    r15
0x18003f74b  sub     rsp, 50h
0x18003f74f  mov     ebx, r9d
0x18003f752  mov     rdi, r8
0x18003f755  mov     r14, rdx
0x18003f758  mov     rbp, rcx
0x18003f75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f762  lea     r12, WPP_GLOBAL_Control
0x18003f769  mov     r15d, [rsp+88h+arg_28]
0x18003f771  mov     rsi, [rsp+88h+arg_20]
0x18003f779  cmp     rcx, r12
0x18003f77c  jz      short loc_18003F789
0x18003f77e  mov     eax, [rcx+2Ch]
0x18003f781  test    al, 4
0x18003f783  jnz     loc_18003F8B4
0x18003f789  test    rsi, rsi
0x18003f78c  jz      loc_18003F83D
0x18003f792  test    rdi, rdi
0x18003f795  jz      loc_18003F83D
0x18003f79b  test    ebx, ebx
0x18003f79d  jz      loc_18003F83D
0x18003f7a3  mov     rcx, rbp
0x18003f7a6  call    ValidateBaseKeyHandle
0x18003f7ab  mov     rcx, rax
0x18003f7ae  test    rax, rax
0x18003f7b1  jz      loc_18003F873
0x18003f7b7  mov     rax, [rax+8]
0x18003f7bb  cmp     dword ptr [rax+24h], 7
0x18003f7bf  jnz     loc_18003F8DD
0x18003f7c5  mov     rax, [rax+68h]
0x18003f7c9  mov     r9d, ebx
0x18003f7cc  mov     rcx, [rcx+10h]
0x18003f7d0  mov     r8, rdi
0x18003f7d3  mov     dword ptr [rsp+88h+var_60], r15d
0x18003f7d8  mov     rdx, r14
0x18003f7db  mov     [rsp+88h+var_68], rsi
0x18003f7e0  call    _guard_dispatch_icall
0x18003f7e5  mov     ebx, eax
0x18003f7e7  test    eax, eax
0x18003f7e9  js      short loc_18003F7FF
0x18003f7eb  xor     ebx, ebx
0x18003f7ed  mov     eax, ebx
0x18003f7ef  add     rsp, 50h
0x18003f7f3  pop     r15
0x18003f7f5  pop     r14
0x18003f7f7  pop     r12
0x18003f7f9  pop     rdi
0x18003f7fa  pop     rsi
0x18003f7fb  pop     rbp
0x18003f7fc  pop     rbx
0x18003f7fd  retn
0x18003f7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f806  cmp     rcx, r12
0x18003f809  jz      short loc_18003F7ED
0x18003f80b  mov     edx, [rcx+2Ch]
0x18003f80e  test    dl, 1
0x18003f811  jz      short loc_18003F7ED
0x18003f813  mov     [rsp+88h+var_58], 1E20h
0x18003f81b  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f822  mov     [rsp+88h+var_60], rax
0x18003f827  mov     dword ptr [rsp+88h+var_68], ebx
0x18003f82b  mov     rcx, [rcx+18h]
0x18003f82f  lea     r9, aStatus; "Status"
0x18003f836  call    WPP_SF_sDsd
0x18003f83b  jmp     short loc_18003F7ED
0x18003f83d  mov     ebx, 0C000000Dh
0x18003f842  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f849  cmp     rcx, r12
0x18003f84c  jz      short loc_18003F7ED
0x18003f84e  mov     eax, [rcx+2Ch]
0x18003f851  test    al, 1
0x18003f853  jz      short loc_18003F7ED
0x18003f855  mov     [rsp+88h+var_58], 1DFFh
0x18003f85d  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f864  mov     [rsp+88h+var_60], rax
0x18003f869  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x18003f871  jmp     short loc_18003F82B
0x18003f873  mov     ebx, 0C0000008h
0x18003f878  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f87f  cmp     rcx, r12
0x18003f882  jz      loc_18003F7ED
0x18003f888  mov     eax, [rcx+2Ch]
0x18003f88b  test    al, 1
0x18003f88d  jz      loc_18003F7ED
0x18003f893  mov     [rsp+88h+var_58], 1E07h
0x18003f89b  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f8a2  mov     [rsp+88h+var_60], rax
0x18003f8a7  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18003f8af  jmp     loc_18003F82B
0x18003f8b4  mov     rcx, [rcx+18h]
0x18003f8b8  mov     r9, rbp
0x18003f8bb  mov     [rsp+88h+var_48], r15d
0x18003f8c0  mov     [rsp+88h+var_50], rsi
0x18003f8c5  mov     [rsp+88h+var_58], ebx
0x18003f8c9  mov     [rsp+88h+var_60], rdi
0x18003f8ce  mov     [rsp+88h+var_68], r14
0x18003f8d3  call    WPP_SF_qqqDqD
0x18003f8d8  jmp     loc_18003F789
0x18003f8dd  mov     r9d, 1E14h
0x18003f8e3  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f8ea  lea     rdx, aStatus; "Status"
0x18003f8f1  mov     ecx, 0C00000BBh
0x18003f8f6  mov     ebx, 0C00000BBh
0x18003f8fb  call    DebugTraceError
0x18003f900  jmp     loc_18003F7ED
```
