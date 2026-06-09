# BCryptKeyDerivation

- ea: `0x1800361d0`
- end: `0x180036395`
- name: `BCryptKeyDerivation`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180083ed4`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x1800361d0`
- `0x1800363a0`
- `0x18005c328`
- `0x18009f6d0`

## string_xrefs

- `0x1800362ab`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800362ed`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003632b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180036373`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x1800361d0  push    rbx
0x1800361d2  push    rbp
0x1800361d3  push    rsi
0x1800361d4  push    rdi
0x1800361d5  push    r12
0x1800361d7  push    r14
0x1800361d9  push    r15
0x1800361db  sub     rsp, 50h
0x1800361df  mov     ebx, r9d
0x1800361e2  mov     rdi, r8
0x1800361e5  mov     r14, rdx
0x1800361e8  mov     rbp, rcx
0x1800361eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361f2  lea     r12, WPP_GLOBAL_Control
0x1800361f9  mov     r15d, [rsp+88h+arg_28]
0x180036201  mov     rsi, [rsp+88h+arg_20]
0x180036209  cmp     rcx, r12
0x18003620c  jz      short loc_180036219
0x18003620e  mov     eax, [rcx+2Ch]
0x180036211  test    al, 4
0x180036213  jnz     loc_180036344
0x180036219  test    rsi, rsi
0x18003621c  jz      loc_1800362CD
0x180036222  test    rdi, rdi
0x180036225  jz      loc_1800362CD
0x18003622b  test    ebx, ebx
0x18003622d  jz      loc_1800362CD
0x180036233  mov     rcx, rbp
0x180036236  call    ValidateBaseKeyHandle
0x18003623b  mov     rcx, rax
0x18003623e  test    rax, rax
0x180036241  jz      loc_180036303
0x180036247  mov     rax, [rax+8]
0x18003624b  cmp     dword ptr [rax+24h], 7
0x18003624f  jnz     loc_18003636D
0x180036255  mov     rax, [rax+68h]
0x180036259  mov     r9d, ebx
0x18003625c  mov     rcx, [rcx+10h]
0x180036260  mov     r8, rdi
0x180036263  mov     dword ptr [rsp+88h+var_60], r15d
0x180036268  mov     rdx, r14
0x18003626b  mov     [rsp+88h+var_68], rsi
0x180036270  call    _guard_dispatch_icall
0x180036275  mov     ebx, eax
0x180036277  test    eax, eax
0x180036279  js      short loc_18003628F
0x18003627b  xor     ebx, ebx
0x18003627d  mov     eax, ebx
0x18003627f  add     rsp, 50h
0x180036283  pop     r15
0x180036285  pop     r14
0x180036287  pop     r12
0x180036289  pop     rdi
0x18003628a  pop     rsi
0x18003628b  pop     rbp
0x18003628c  pop     rbx
0x18003628d  retn
0x18003628f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036296  cmp     rcx, r12
0x180036299  jz      short loc_18003627D
0x18003629b  mov     edx, [rcx+2Ch]
0x18003629e  test    dl, 1
0x1800362a1  jz      short loc_18003627D
0x1800362a3  mov     [rsp+88h+var_58], 1E20h
0x1800362ab  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800362b2  mov     [rsp+88h+var_60], rax
0x1800362b7  mov     dword ptr [rsp+88h+var_68], ebx
0x1800362bb  mov     rcx, [rcx+18h]
0x1800362bf  lea     r9, aStatus; "Status"
0x1800362c6  call    WPP_SF_sDsd
0x1800362cb  jmp     short loc_18003627D
0x1800362cd  mov     ebx, 0C000000Dh
0x1800362d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362d9  cmp     rcx, r12
0x1800362dc  jz      short loc_18003627D
0x1800362de  mov     eax, [rcx+2Ch]
0x1800362e1  test    al, 1
0x1800362e3  jz      short loc_18003627D
0x1800362e5  mov     [rsp+88h+var_58], 1DFFh
0x1800362ed  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800362f4  mov     [rsp+88h+var_60], rax
0x1800362f9  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180036301  jmp     short loc_1800362BB
0x180036303  mov     ebx, 0C0000008h
0x180036308  mov     rcx, cs:WPP_GLOBAL_Control
0x18003630f  cmp     rcx, r12
0x180036312  jz      loc_18003627D
0x180036318  mov     eax, [rcx+2Ch]
0x18003631b  test    al, 1
0x18003631d  jz      loc_18003627D
0x180036323  mov     [rsp+88h+var_58], 1E07h
0x18003632b  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036332  mov     [rsp+88h+var_60], rax
0x180036337  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18003633f  jmp     loc_1800362BB
0x180036344  mov     rcx, [rcx+18h]
0x180036348  mov     r9, rbp
0x18003634b  mov     [rsp+88h+var_48], r15d
0x180036350  mov     [rsp+88h+var_50], rsi
0x180036355  mov     [rsp+88h+var_58], ebx
0x180036359  mov     [rsp+88h+var_60], rdi
0x18003635e  mov     [rsp+88h+var_68], r14
0x180036363  call    WPP_SF_qqqDqD
0x180036368  jmp     loc_180036219
0x18003636d  mov     r9d, 1E14h
0x180036373  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003637a  lea     rdx, aStatus; "Status"
0x180036381  mov     ecx, 0C00000BBh
0x180036386  mov     ebx, 0C00000BBh
0x18003638b  call    DebugTraceError
0x180036390  jmp     loc_18003627D
```
