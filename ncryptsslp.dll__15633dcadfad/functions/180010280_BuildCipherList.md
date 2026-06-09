# BuildCipherList

- ea: `0x180010280`
- end: `0x180010577`
- name: `BuildCipherList`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006904`
- `0x18001de24`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x180010280`
- `0x180010580`

## string_xrefs

- `0x18001045f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x18001054b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`

## pseudocode

```c
__int64 __fastcall BuildCipherList(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  unsigned int v5; // r14d
  __int64 v7; // r15
  int v9; // ecx
  __int64 v10; // r12
  int v11; // r13d
  __int64 v12; // r11
  __int64 v13; // rdi
  HRESULT v14; // eax
  size_t v15; // rdx
  __int64 v16; // r11
  unsigned int v17; // ebx
  size_t v18; // rdx
  __int64 v19; // r11
  size_t v20; // rdx
  __int64 v21; // r11
  size_t v22; // rdx
  int v23; // r8d
  __int64 v24; // r11
  size_t v25; // rdx
  __int64 v26; // r11
  bool v28; // zf
  int v29; // ecx
  unsigned int v30; // eax
  __int64 v31; // r9
  int v32; // [rsp+A8h] [rbp+20h]

  v5 = 0;
  v7 = 0;
LABEL_2:
  if ( (unsigned int)v7 >= 7 )
  {
    v17 = 0;
    *a5 = v5;
    return v17;
  }
  v9 = (unsigned __int16)ProtocolVersionList[4 * v7];
  v10 = 0;
  v11 = dword_180031A24[2 * v7];
  v32 = v9;
  while ( 1 )
  {
    if ( (unsigned int)v10 >= g_dwCipherSuiteInfoTotalCount )
    {
LABEL_18:
      v7 = (unsigned int)(v7 + 1);
      goto LABEL_2;
    }
    v12 = g_pCipherSuiteInfo[v10];
    if ( !v12 || (v11 & *(_DWORD *)v12) == 0 )
      goto LABEL_17;
    if ( a2 )
    {
      if ( *(_DWORD *)(v12 + 88) != 196609 )
      {
        if ( *(_DWORD *)(v12 + 88) == 196610 )
        {
          v28 = *(_DWORD *)(a2 + 8) == 196611;
LABEL_33:
          if ( !v28 || !*(_QWORD *)(a2 + 24) )
            goto LABEL_17;
          goto LABEL_8;
        }
        v29 = *(_DWORD *)(v12 + 4);
        if ( (unsigned int)(v29 - 49161) <= 1 )
        {
          v9 = v32;
          v28 = *(_DWORD *)(a2 + 8) == 196619;
          goto LABEL_33;
        }
        v30 = v29 - 49171;
        v9 = v32;
        if ( v30 > 1 )
          goto LABEL_8;
      }
      v28 = *(_DWORD *)(a2 + 8) == 196609;
      goto LABEL_33;
    }
LABEL_8:
    if ( v5 >= 0xE1 )
      break;
    v13 = 808LL * v5;
    *(_DWORD *)(v13 + a3 + 4) = v9;
    *(_DWORD *)(v13 + a3) = 1;
    *(_DWORD *)(v13 + a3 + 8) = *(_DWORD *)(v12 + 4);
    *(_DWORD *)(v13 + a3 + 12) = *(_DWORD *)(v12 + 4);
    v14 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + a3 + 16), (size_t)&_ImageBase, *(STRSAFE_LPCWSTR *)(v12 + 8));
    v17 = v14;
    if ( v14 < 0 )
    {
      v31 = 1678;
      goto LABEL_41;
    }
    v14 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + a3 + 144), v15, *(STRSAFE_LPCWSTR *)(v16 + 16));
    v17 = v14;
    if ( v14 < 0 )
    {
      v31 = 1688;
      goto LABEL_41;
    }
    *(_DWORD *)(v13 + a3 + 272) = *(_DWORD *)(v19 + 28);
    *(_DWORD *)(v13 + a3 + 276) = *(_DWORD *)(v19 + 36);
    v14 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + a3 + 280), v18, *(STRSAFE_LPCWSTR *)(v19 + 56));
    v17 = v14;
    if ( v14 < 0 )
    {
      v31 = 1701;
      goto LABEL_41;
    }
    *(_DWORD *)(v13 + a3 + 408) = 8 * *(_DWORD *)(v21 + 68);
    v17 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + a3 + 412), v20, *(STRSAFE_LPCWSTR *)(v21 + 80));
    if ( (v17 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          v23,
          (unsigned int)"Status",
          v17,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c",
          177);
      return v17;
    }
    *(_DWORD *)(v13 + a3 + 540) = *(_DWORD *)(v24 + 92);
    *(_DWORD *)(v13 + a3 + 544) = *(_DWORD *)(v24 + 96);
    v14 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + a3 + 548), v22, *(STRSAFE_LPCWSTR *)(v24 + 120));
    v17 = v14;
    if ( v14 < 0 )
    {
      v31 = 1726;
      goto LABEL_41;
    }
    v14 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + a3 + 680), v25, *(STRSAFE_LPCWSTR *)(v26 + 48));
    v17 = v14;
    if ( v14 < 0 )
    {
      v31 = 1737;
LABEL_41:
      DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", v31);
      return v17;
    }
    if ( ++v5 >= 0xE1 )
      goto LABEL_18;
    v9 = v32;
LABEL_17:
    v10 = (unsigned int)(v10 + 1);
  }
  v17 = 122;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&_ImageBase,
      a3,
      (unsigned int)"Status",
      122,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c",
      125);
  return v17;
}

```

## disassembly

```asm
0x180010280  mov     [rsp+arg_18], r9d
0x180010285  push    rbx
0x180010286  push    rbp
0x180010287  push    rsi
0x180010288  push    rdi
0x180010289  push    r12
0x18001028b  push    r13
0x18001028d  push    r14
0x18001028f  push    r15
0x180010291  sub     rsp, 48h
0x180010295  xor     r14d, r14d
0x180010298  mov     rsi, rdx
0x18001029b  xor     r15d, r15d
0x18001029e  lea     rdx, __ImageBase; cchDest
0x1800102a5  mov     rbp, r8
0x1800102a8  cmp     r15d, 7
0x1800102ac  jnb     loc_180010565
0x1800102b2  movzx   ecx, ds:rva ProtocolVersionList[rdx+r15*8]
0x1800102bb  xor     r12d, r12d
0x1800102be  mov     r13d, ds:rva dword_180031A24[rdx+r15*8]
0x1800102c6  mov     [rsp+88h+arg_18], ecx
0x1800102cd  cmp     r12d, cs:g_dwCipherSuiteInfoTotalCount
0x1800102d4  jnb     loc_180010432
0x1800102da  mov     r11, rva g_pCipherSuiteInfo[rdx+r12*8]
0x1800102e2  test    r11, r11
0x1800102e5  jz      loc_18001042A
0x1800102eb  test    [r11], r13d
0x1800102ee  jz      loc_18001042A
0x1800102f4  test    rsi, rsi
0x1800102f7  jnz     loc_1800104B6
0x1800102fd  cmp     r14d, 0E1h
0x180010304  jnb     loc_18001048E
0x18001030a  mov     eax, r14d
0x18001030d  imul    rdi, rax, 328h
0x180010314  mov     [rdi+rbp+4], ecx
0x180010318  lea     rcx, [rbp+10h]
0x18001031c  mov     dword ptr [rdi+rbp], 1
0x180010323  add     rcx, rdi; pszDest
0x180010326  mov     eax, [r11+4]
0x18001032a  mov     [rdi+rbp+8], eax
0x18001032e  mov     eax, [r11+4]
0x180010332  mov     [rdi+rbp+0Ch], eax
0x180010336  mov     r8, [r11+8]; pszSrc
0x18001033a  call    StringCchCopyW
0x18001033f  mov     ebx, eax
0x180010341  test    eax, eax
0x180010343  js      loc_180010545
0x180010349  mov     r8, [r11+10h]; pszSrc
0x18001034d  lea     rcx, [rbp+90h]
0x180010354  add     rcx, rdi; pszDest
0x180010357  call    StringCchCopyW
0x18001035c  mov     ebx, eax
0x18001035e  test    eax, eax
0x180010360  js      loc_18001053D
0x180010366  mov     eax, [r11+1Ch]
0x18001036a  lea     rcx, [rbp+118h]
0x180010371  mov     [rdi+rbp+110h], eax
0x180010378  add     rcx, rdi; pszDest
0x18001037b  mov     eax, [r11+24h]
0x18001037f  mov     [rdi+rbp+114h], eax
0x180010386  mov     r8, [r11+38h]; pszSrc
0x18001038a  call    StringCchCopyW
0x18001038f  mov     ebx, eax
0x180010391  test    eax, eax
0x180010393  js      loc_180010535
0x180010399  mov     eax, [r11+44h]
0x18001039d  lea     rcx, [rbp+19Ch]
0x1800103a4  shl     eax, 3
0x1800103a7  add     rcx, rdi; pszDest
0x1800103aa  mov     [rdi+rbp+198h], eax
0x1800103b1  mov     r8, [r11+50h]; pszSrc
0x1800103b5  call    StringCchCopyW
0x1800103ba  mov     ebx, eax
0x1800103bc  test    eax, eax
0x1800103be  js      short loc_18001043A
0x1800103c0  mov     eax, [r11+5Ch]
0x1800103c4  lea     rcx, [rbp+224h]
0x1800103cb  mov     [rdi+rbp+21Ch], eax
0x1800103d2  add     rcx, rdi; pszDest
0x1800103d5  mov     eax, [r11+60h]
0x1800103d9  mov     [rdi+rbp+220h], eax
0x1800103e0  mov     r8, [r11+78h]; pszSrc
0x1800103e4  call    StringCchCopyW
0x1800103e9  mov     ebx, eax
0x1800103eb  test    eax, eax
0x1800103ed  js      loc_18001052D
0x1800103f3  mov     r8, [r11+30h]; pszSrc
0x1800103f7  lea     rcx, [rbp+2A8h]
0x1800103fe  add     rcx, rdi; pszDest
0x180010401  call    StringCchCopyW
0x180010406  mov     ebx, eax
0x180010408  test    eax, eax
0x18001040a  js      loc_180010525
0x180010410  inc     r14d
0x180010413  lea     rdx, __ImageBase
0x18001041a  cmp     r14d, 0E1h
0x180010421  jnb     short loc_180010432
0x180010423  mov     ecx, [rsp+88h+arg_18]
0x18001042a  inc     r12d
0x18001042d  jmp     loc_1800102CD
0x180010432  inc     r15d
0x180010435  jmp     loc_1800102A8
0x18001043a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010441  lea     rax, WPP_GLOBAL_Control
0x180010448  cmp     rcx, rax
0x18001044b  jz      short loc_18001047B
0x18001044d  test    byte ptr [rcx+1Ch], 1
0x180010451  jz      short loc_18001047B
0x180010453  mov     [rsp+88h+var_58], 6B1h
0x18001045b  mov     rcx, [rcx+10h]
0x18001045f  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010466  mov     [rsp+88h+var_60], rax
0x18001046b  lea     r9, aStatus; "Status"
0x180010472  mov     [rsp+88h+var_68], ebx
0x180010476  call    WPP_SF_sDsd
0x18001047b  mov     eax, ebx
0x18001047d  add     rsp, 48h
0x180010481  pop     r15
0x180010483  pop     r14
0x180010485  pop     r13
0x180010487  pop     r12
0x180010489  pop     rdi
0x18001048a  pop     rsi
0x18001048b  pop     rbp
0x18001048c  pop     rbx
0x18001048d  retn
0x18001048e  mov     ebx, 7Ah ; 'z'
0x180010493  mov     rcx, cs:WPP_GLOBAL_Control
0x18001049a  lea     rax, WPP_GLOBAL_Control
0x1800104a1  cmp     rcx, rax
0x1800104a4  jz      short loc_18001047B
0x1800104a6  test    byte ptr [rcx+1Ch], 1
0x1800104aa  jz      short loc_18001047B
0x1800104ac  mov     [rsp+88h+var_58], 67Dh
0x1800104b4  jmp     short loc_18001045B
0x1800104b6  cmp     dword ptr [r11+58h], 30001h
0x1800104be  jz      short loc_1800104F8
0x1800104c0  cmp     dword ptr [r11+58h], 30002h
0x1800104c8  jnz     short loc_1800104D3
0x1800104ca  cmp     dword ptr [rsi+8], 30003h
0x1800104d1  jmp     short loc_18001050F
0x1800104d3  mov     ecx, [r11+4]
0x1800104d7  lea     eax, [rcx-0C009h]
0x1800104dd  cmp     eax, 1
0x1800104e0  jbe     short loc_180010501
0x1800104e2  lea     eax, [rcx-0C013h]
0x1800104e8  mov     ecx, [rsp+88h+arg_18]
0x1800104ef  cmp     eax, 1
0x1800104f2  ja      loc_1800102FD
0x1800104f8  cmp     dword ptr [rsi+8], 30001h
0x1800104ff  jmp     short loc_18001050F
0x180010501  mov     ecx, [rsp+88h+arg_18]
0x180010508  cmp     dword ptr [rsi+8], 3000Bh
0x18001050f  jnz     loc_18001042A
0x180010515  cmp     qword ptr [rsi+18h], 0
0x18001051a  jnz     loc_1800102FD
0x180010520  jmp     loc_18001042A
0x180010525  mov     r9d, 6C9h
0x18001052b  jmp     short loc_18001054B
0x18001052d  mov     r9d, 6BEh
0x180010533  jmp     short loc_18001054B
0x180010535  mov     r9d, 6A5h
0x18001053b  jmp     short loc_18001054B
0x18001053d  mov     r9d, 698h
0x180010543  jmp     short loc_18001054B
0x180010545  mov     r9d, 68Eh
0x18001054b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010552  mov     ecx, eax
0x180010554  lea     rdx, aStatus; "Status"
0x18001055b  call    DebugTraceError
0x180010560  jmp     loc_18001047B
0x180010565  mov     rax, [rsp+88h+arg_20]
0x18001056d  xor     ebx, ebx
0x18001056f  mov     [rax], r14d
0x180010572  jmp     loc_18001047B
```
