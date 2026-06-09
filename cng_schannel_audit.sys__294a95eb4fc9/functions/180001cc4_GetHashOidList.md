# GetHashOidList

- ea: `0x180001cc4`
- end: `0x180001f7a`
- name: `GetHashOidList`
- size: `694`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003fcc0`
- `0x180077e30`

## callees

- `0x180001cc4`
- `0x180002530`
- `0x180003f70`
- `0x180004320`
- `0x180005590`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`

## string_xrefs

- `0x180001e2f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180001e83`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180001eb2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180001eef`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180001f28`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180001f58`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall GetHashOidList(_QWORD *a1, int a2, _QWORD *a3, _DWORD *a4)
{
  int v7; // eax
  int HashProperty; // eax
  int v9; // ebx
  __int64 v10; // rdx
  _QWORD *v11; // rdi
  int v12; // edx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF
  _DWORD *v17; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+20h] BYREF

  v17 = 0;
  LODWORD(v16) = 0;
  v18 = 0;
  if ( !a1 )
  {
    v9 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 149);
    return (unsigned int)v9;
  }
  if ( !*a1 )
  {
    *a3 = 0;
    v9 = 0;
    *a4 = 0;
    return (unsigned int)v9;
  }
  v7 = MSCryptOpenHashProvider(&v17, *a1, 0);
  if ( v7 < 0 )
  {
    DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 169);
    v9 = -1073741637;
    goto LABEL_11;
  }
  HashProperty = MSCryptGetHashProperty(v17, L"HashDigestLength", &v16, 4u, &v18, 0);
  v9 = HashProperty;
  if ( HashProperty < 0 )
  {
    v14 = 183;
    v15 = (unsigned int)HashProperty;
LABEL_26:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v14);
    goto LABEL_11;
  }
  if ( (_DWORD)v16 != a2 )
  {
    v9 = -1073741811;
    v14 = 190;
    v15 = 3221225485LL;
    goto LABEL_26;
  }
  v9 = MSCryptGetHashProperty(v17, L"HashOIDList", 0, 0, &v18, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v10,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        203);
    goto LABEL_11;
  }
  v11 = (_QWORD *)MSCryptAlloc(v18, v10);
  if ( !v11 )
  {
    v9 = -1073741801;
    v14 = 212;
    v15 = 3221225495LL;
    goto LABEL_26;
  }
  v9 = MSCryptGetHashProperty(v17, L"HashOIDList", v11, v18, &v18, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        225);
  }
  else
  {
    if ( *(_DWORD *)v11 )
    {
      v9 = 0;
      *a4 = v18;
      *a3 = v11;
      goto LABEL_11;
    }
    v9 = -1073741595;
    DebugTraceError(3221225701LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 234);
  }
  MSCryptFree(v11);
LABEL_11:
  if ( v17 )
    MSCryptCloseHashProvider(v17, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001cc4  mov     [rsp-18h+arg_8], rbx
0x180001cc9  mov     [rsp-18h+arg_10], rdi
0x180001cce  push    rbp
0x180001ccf  push    r14
0x180001cd1  push    r15
0x180001cd3  mov     rbp, rsp
0x180001cd6  sub     rsp, 50h
0x180001cda  mov     [rbp+var_8], 0
0x180001ce2  mov     r14, r9
0x180001ce5  mov     dword ptr [rbp+var_10], 0
0x180001cec  mov     r15, r8
0x180001cef  mov     [rbp+arg_0], 0
0x180001cf6  mov     edi, edx
0x180001cf8  test    rcx, rcx
0x180001cfb  jz      loc_180001EAC
0x180001d01  mov     rdx, [rcx]
0x180001d04  test    rdx, rdx
0x180001d07  jz      loc_180001ED4
0x180001d0d  xor     r8d, r8d
0x180001d10  lea     rcx, [rbp+var_8]
0x180001d14  call    MSCryptOpenHashProvider
0x180001d19  test    eax, eax
0x180001d1b  js      loc_180001EE9
0x180001d21  mov     rcx, [rbp+var_8]
0x180001d25  lea     rax, [rbp+arg_0]
0x180001d29  mov     dword ptr [rsp+50h+var_28], 0
0x180001d31  lea     r8, [rbp+var_10]
0x180001d35  mov     r9d, 4
0x180001d3b  mov     [rsp+50h+var_30], rax
0x180001d40  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180001d47  call    MSCryptGetHashProperty
0x180001d4c  mov     ebx, eax
0x180001d4e  test    eax, eax
0x180001d50  js      loc_180001F0E
0x180001d56  cmp     dword ptr [rbp+var_10], edi
0x180001d59  jnz     loc_180001F40
0x180001d5f  mov     rcx, [rbp+var_8]
0x180001d63  lea     rax, [rbp+arg_0]
0x180001d67  mov     dword ptr [rsp+50h+var_28], 0
0x180001d6f  lea     rdx, aHashoidlist; "HashOIDList"
0x180001d76  xor     r9d, r9d
0x180001d79  mov     [rsp+50h+var_30], rax
0x180001d7e  xor     r8d, r8d
0x180001d81  call    MSCryptGetHashProperty
0x180001d86  mov     ebx, eax
0x180001d88  test    eax, eax
0x180001d8a  js      loc_180001E5D
0x180001d90  mov     ecx, [rbp+arg_0]
0x180001d93  call    MSCryptAlloc
0x180001d98  mov     rdi, rax
0x180001d9b  test    rax, rax
0x180001d9e  jz      loc_180001F18
0x180001da4  mov     r9d, [rbp+arg_0]
0x180001da8  lea     rax, [rbp+arg_0]
0x180001dac  mov     rcx, [rbp+var_8]
0x180001db0  lea     rdx, aHashoidlist; "HashOIDList"
0x180001db7  mov     dword ptr [rsp+50h+var_28], 0
0x180001dbf  mov     r8, rdi
0x180001dc2  mov     [rsp+50h+var_30], rax
0x180001dc7  call    MSCryptGetHashProperty
0x180001dcc  mov     ebx, eax
0x180001dce  test    eax, eax
0x180001dd0  js      short loc_180001E11
0x180001dd2  cmp     dword ptr [rdi], 0
0x180001dd5  jz      loc_180001F52
0x180001ddb  mov     eax, [rbp+arg_0]
0x180001dde  xor     ebx, ebx
0x180001de0  mov     [r14], eax
0x180001de3  mov     [r15], rdi
0x180001de6  cmp     [rbp+var_8], 0
0x180001deb  jz      short loc_180001DF8
0x180001ded  mov     rcx, [rbp+var_8]
0x180001df1  xor     edx, edx
0x180001df3  call    MSCryptCloseHashProvider
0x180001df8  lea     r11, [rsp+50h+var_s0]
0x180001dfd  mov     eax, ebx
0x180001dff  mov     rbx, [r11+28h]
0x180001e03  mov     rdi, [r11+30h]
0x180001e07  mov     rsp, r11
0x180001e0a  pop     r15
0x180001e0c  pop     r14
0x180001e0e  pop     rbp
0x180001e0f  retn
0x180001e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e18  lea     rax, WPP_GLOBAL_Control
0x180001e1f  cmp     rcx, rax
0x180001e22  jz      short loc_180001E53
0x180001e24  mov     eax, [rcx+2Ch]
0x180001e27  test    al, 1
0x180001e29  jz      short loc_180001E53
0x180001e2b  mov     rcx, [rcx+18h]
0x180001e2f  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001e36  mov     [rsp+50h+var_20], 0E1h
0x180001e3e  lea     r9, aStatus; "Status"
0x180001e45  mov     [rsp+50h+var_28], r8
0x180001e4a  mov     dword ptr [rsp+50h+var_30], ebx
0x180001e4e  call    WPP_SF_sDsd
0x180001e53  mov     rcx, rdi; P
0x180001e56  call    MSCryptFree
0x180001e5b  jmp     short loc_180001DE6
0x180001e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e64  lea     rax, WPP_GLOBAL_Control
0x180001e6b  cmp     rcx, rax
0x180001e6e  jz      loc_180001DE6
0x180001e74  mov     eax, [rcx+2Ch]
0x180001e77  test    al, 1
0x180001e79  jz      loc_180001DE6
0x180001e7f  mov     rcx, [rcx+18h]
0x180001e83  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001e8a  mov     [rsp+50h+var_20], 0CBh
0x180001e92  lea     r9, aStatus; "Status"
0x180001e99  mov     [rsp+50h+var_28], r8
0x180001e9e  mov     dword ptr [rsp+50h+var_30], ebx
0x180001ea2  call    WPP_SF_sDsd
0x180001ea7  jmp     loc_180001DE6
0x180001eac  mov     r9d, 95h
0x180001eb2  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001eb9  lea     rdx, aStatus; "Status"
0x180001ec0  mov     ecx, 0C000000Dh
0x180001ec5  mov     ebx, 0C000000Dh
0x180001eca  call    DebugTraceError
0x180001ecf  jmp     loc_180001DF8
0x180001ed4  mov     qword ptr [r8], 0
0x180001edb  xor     ebx, ebx
0x180001edd  mov     dword ptr [r9], 0
0x180001ee4  jmp     loc_180001DF8
0x180001ee9  mov     r9d, 0A9h
0x180001eef  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001ef6  lea     rdx, aStatus; "Status"
0x180001efd  mov     ecx, eax
0x180001eff  call    DebugTraceError
0x180001f04  mov     ebx, 0C00000BBh
0x180001f09  jmp     loc_180001DE6
0x180001f0e  mov     r9d, 0B7h
0x180001f14  mov     ecx, eax
0x180001f16  jmp     short loc_180001F28
0x180001f18  mov     ebx, 0C0000017h
0x180001f1d  mov     r9d, 0D4h
0x180001f23  mov     ecx, 0C0000017h
0x180001f28  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001f2f  lea     rdx, aStatus; "Status"
0x180001f36  call    DebugTraceError
0x180001f3b  jmp     loc_180001DE6
0x180001f40  mov     ebx, 0C000000Dh
0x180001f45  mov     r9d, 0BEh
0x180001f4b  mov     ecx, 0C000000Dh
0x180001f50  jmp     short loc_180001F28
0x180001f52  mov     r9d, 0EAh
0x180001f58  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001f5f  lea     rdx, aStatus; "Status"
0x180001f66  mov     ecx, 0C00000E5h
0x180001f6b  mov     ebx, 0C00000E5h
0x180001f70  call    DebugTraceError
0x180001f75  jmp     loc_180001E53
```
