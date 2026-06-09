# BCryptKeyDerivation

- ea: `0x1800356d0`
- end: `0x180035895`
- name: `BCryptKeyDerivation`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180082ee4`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x1800356d0`
- `0x1800358a0`
- `0x18005ba38`
- `0x18009d860`

## string_xrefs

- `0x1800357ab`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800357ed`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003582b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180035873`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x1800356d0  push    rbx
0x1800356d2  push    rbp
0x1800356d3  push    rsi
0x1800356d4  push    rdi
0x1800356d5  push    r12
0x1800356d7  push    r14
0x1800356d9  push    r15
0x1800356db  sub     rsp, 50h
0x1800356df  mov     ebx, r9d
0x1800356e2  mov     rdi, r8
0x1800356e5  mov     r14, rdx
0x1800356e8  mov     rbp, rcx
0x1800356eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356f2  lea     r12, WPP_GLOBAL_Control
0x1800356f9  mov     r15d, [rsp+88h+arg_28]
0x180035701  mov     rsi, [rsp+88h+arg_20]
0x180035709  cmp     rcx, r12
0x18003570c  jz      short loc_180035719
0x18003570e  mov     eax, [rcx+2Ch]
0x180035711  test    al, 4
0x180035713  jnz     loc_180035844
0x180035719  test    rsi, rsi
0x18003571c  jz      loc_1800357CD
0x180035722  test    rdi, rdi
0x180035725  jz      loc_1800357CD
0x18003572b  test    ebx, ebx
0x18003572d  jz      loc_1800357CD
0x180035733  mov     rcx, rbp
0x180035736  call    ValidateBaseKeyHandle
0x18003573b  mov     rcx, rax
0x18003573e  test    rax, rax
0x180035741  jz      loc_180035803
0x180035747  mov     rax, [rax+8]
0x18003574b  cmp     dword ptr [rax+24h], 7
0x18003574f  jnz     loc_18003586D
0x180035755  mov     rax, [rax+68h]
0x180035759  mov     r9d, ebx
0x18003575c  mov     rcx, [rcx+10h]
0x180035760  mov     r8, rdi
0x180035763  mov     dword ptr [rsp+88h+var_60], r15d
0x180035768  mov     rdx, r14
0x18003576b  mov     [rsp+88h+var_68], rsi
0x180035770  call    _guard_dispatch_icall
0x180035775  mov     ebx, eax
0x180035777  test    eax, eax
0x180035779  js      short loc_18003578F
0x18003577b  xor     ebx, ebx
0x18003577d  mov     eax, ebx
0x18003577f  add     rsp, 50h
0x180035783  pop     r15
0x180035785  pop     r14
0x180035787  pop     r12
0x180035789  pop     rdi
0x18003578a  pop     rsi
0x18003578b  pop     rbp
0x18003578c  pop     rbx
0x18003578d  retn
0x18003578f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035796  cmp     rcx, r12
0x180035799  jz      short loc_18003577D
0x18003579b  mov     edx, [rcx+2Ch]
0x18003579e  test    dl, 1
0x1800357a1  jz      short loc_18003577D
0x1800357a3  mov     [rsp+88h+var_58], 1E20h
0x1800357ab  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800357b2  mov     [rsp+88h+var_60], rax
0x1800357b7  mov     dword ptr [rsp+88h+var_68], ebx
0x1800357bb  mov     rcx, [rcx+18h]
0x1800357bf  lea     r9, aStatus; "Status"
0x1800357c6  call    WPP_SF_sDsd
0x1800357cb  jmp     short loc_18003577D
0x1800357cd  mov     ebx, 0C000000Dh
0x1800357d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357d9  cmp     rcx, r12
0x1800357dc  jz      short loc_18003577D
0x1800357de  mov     eax, [rcx+2Ch]
0x1800357e1  test    al, 1
0x1800357e3  jz      short loc_18003577D
0x1800357e5  mov     [rsp+88h+var_58], 1DFFh
0x1800357ed  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800357f4  mov     [rsp+88h+var_60], rax
0x1800357f9  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180035801  jmp     short loc_1800357BB
0x180035803  mov     ebx, 0C0000008h
0x180035808  mov     rcx, cs:WPP_GLOBAL_Control
0x18003580f  cmp     rcx, r12
0x180035812  jz      loc_18003577D
0x180035818  mov     eax, [rcx+2Ch]
0x18003581b  test    al, 1
0x18003581d  jz      loc_18003577D
0x180035823  mov     [rsp+88h+var_58], 1E07h
0x18003582b  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035832  mov     [rsp+88h+var_60], rax
0x180035837  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18003583f  jmp     loc_1800357BB
0x180035844  mov     rcx, [rcx+18h]
0x180035848  mov     r9, rbp
0x18003584b  mov     [rsp+88h+var_48], r15d
0x180035850  mov     [rsp+88h+var_50], rsi
0x180035855  mov     [rsp+88h+var_58], ebx
0x180035859  mov     [rsp+88h+var_60], rdi
0x18003585e  mov     [rsp+88h+var_68], r14
0x180035863  call    WPP_SF_qqqDqD
0x180035868  jmp     loc_180035719
0x18003586d  mov     r9d, 1E14h
0x180035873  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003587a  lea     rdx, aStatus; "Status"
0x180035881  mov     ecx, 0C00000BBh
0x180035886  mov     ebx, 0C00000BBh
0x18003588b  call    DebugTraceError
0x180035890  jmp     loc_18003577D
```
