# BCryptDecapsulate

- ea: `0x180057c70`
- end: `0x180057ea5`
- name: `BCryptDecapsulate`
- size: `565`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800010ac`
- `0x18000743c`
- `0x180024a34`
- `0x1800358a0`
- `0x1800451f0`
- `0x180057c70`
- `0x18005b4ec`
- `0x18005fe74`
- `0x18009d820`
- `0x18009d860`

## string_xrefs

- `0x180057d08`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180057d5a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptDecapsulate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6, int a7)
{
  unsigned int v8; // esi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdi
  unsigned int v14; // ebx
  __int64 v15; // rax
  bool v16; // zf
  __int64 v17; // r9
  __int64 v18; // rcx
  int v19; // eax
  char TrustedEnvironment; // al
  __int64 v21; // r10
  int v22; // r9d
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  char v28[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int64 *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  unsigned int *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  __int64 *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  char v37[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v38[16]; // [rsp+E0h] [rbp-20h] BYREF

  v8 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqDqDqD(*((_QWORD *)WPP_GLOBAL_Control + 3), a2, a3, a1, a2, a3, a4, a5, a6, a7);
  v11 = ValidateBaseKeyHandle(a1);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 0;
    v14 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7900);
    goto LABEL_13;
  }
  v15 = *(_QWORD *)(v11 + 8);
  v16 = *(_DWORD *)(v15 + 36) == 8;
  v24 = v15 + 444;
  if ( v16 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, __int64, int))(v15 + 112))(
            *(_QWORD *)(v12 + 16),
            a2,
            v8,
            a4,
            a5,
            a6,
            a7);
    v14 = v19;
    if ( v19 >= 0 )
    {
      v14 = 0;
      goto LABEL_12;
    }
    v17 = 7925;
    v18 = (unsigned int)v19;
  }
  else
  {
    v14 = -1073741637;
    v17 = 7910;
    v18 = 3221225659LL;
  }
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v17);
LABEL_12:
  v13 = v24;
LABEL_13:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && (unsigned int)dword_1800C95C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800C95C0, 0x400000000000LL) )
  {
    v26 = v21;
    v29 = &v26;
    v30 = (unsigned int)(v21 + 7);
    v31 = &v27;
    v27 = 0x1000000;
    v33 = &v25;
    v32 = v30;
    v35 = &v24;
    v25 = v14;
    v34 = 4;
    LODWORD(v24) = v21;
    v36 = 4;
    tlgCreate1Sz_wchar_t(v37, g_processImageName);
    tlgCreate1Sz_wchar_t(v38, v13);
    tlgWriteAgg((unsigned int)&dword_1800C95C0, (unsigned int)byte_1800C0873, 0, v22, (__int64)v28);
  }
  return v14;
}

```

## disassembly

```asm
0x180057c70  push    rbp
0x180057c72  push    rbx
0x180057c73  push    rsi
0x180057c74  push    rdi
0x180057c75  push    r12
0x180057c77  push    r13
0x180057c79  push    r14
0x180057c7b  push    r15
0x180057c7d  lea     rbp, [rsp-8]
0x180057c82  sub     rsp, 108h
0x180057c89  mov     rax, cs:__security_cookie
0x180057c90  xor     rax, rsp
0x180057c93  mov     [rbp+40h+var_50], rax
0x180057c97  mov     r15, [rbp+40h+arg_28]
0x180057c9b  mov     r14, r9
0x180057c9e  mov     esi, r8d
0x180057ca1  mov     rdi, rdx
0x180057ca4  mov     rbx, rcx
0x180057ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180057cae  lea     rax, WPP_GLOBAL_Control
0x180057cb5  mov     r12d, [rbp+40h+arg_30]
0x180057cbc  mov     r13d, [rbp+40h+arg_20]
0x180057cc0  cmp     rcx, rax
0x180057cc3  jz      short loc_180057CF6
0x180057cc5  mov     eax, [rcx+2Ch]
0x180057cc8  test    al, 4
0x180057cca  jz      short loc_180057CF6
0x180057ccc  mov     rcx, [rcx+18h]
0x180057cd0  mov     [rsp+140h+var_F8], r12d
0x180057cd5  mov     [rsp+140h+var_100], r15
0x180057cda  mov     [rsp+140h+var_108], r13d
0x180057cdf  mov     [rsp+140h+var_110], r9
0x180057ce4  mov     r9, rbx
0x180057ce7  mov     dword ptr [rsp+140h+var_118], r8d
0x180057cec  mov     [rsp+140h+var_120], rdx
0x180057cf1  call    WPP_SF_qqDqDqD
0x180057cf6  mov     rcx, rbx
0x180057cf9  call    ValidateBaseKeyHandle
0x180057cfe  mov     rcx, rax
0x180057d01  test    rax, rax
0x180057d04  jnz     short loc_180057D2D
0x180057d06  xor     edi, edi
0x180057d08  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057d0f  mov     r9d, 1EDCh
0x180057d15  lea     rdx, aStatus; "Status"
0x180057d1c  mov     ecx, 0C0000008h
0x180057d21  mov     ebx, 0C0000008h
0x180057d26  call    DebugTraceError
0x180057d2b  jmp     short loc_180057DA4
0x180057d2d  mov     rax, [rax+8]
0x180057d31  cmp     dword ptr [rax+24h], 8
0x180057d35  lea     rdx, [rax+1BCh]
0x180057d3c  mov     [rsp+140h+var_F0], rdx
0x180057d41  jz      short loc_180057D68
0x180057d43  mov     ebx, 0C00000BBh
0x180057d48  mov     r9d, 1EE6h
0x180057d4e  mov     ecx, 0C00000BBh
0x180057d53  lea     rdx, aStatus; "Status"
0x180057d5a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057d61  call    DebugTraceError
0x180057d66  jmp     short loc_180057D9F
0x180057d68  mov     rax, [rax+70h]
0x180057d6c  mov     r9, r14
0x180057d6f  mov     rcx, [rcx+10h]
0x180057d73  mov     r8d, esi
0x180057d76  mov     dword ptr [rsp+140h+var_110], r12d
0x180057d7b  mov     rdx, rdi
0x180057d7e  mov     [rsp+140h+var_118], r15
0x180057d83  mov     dword ptr [rsp+140h+var_120], r13d
0x180057d88  call    _guard_dispatch_icall
0x180057d8d  mov     ebx, eax
0x180057d8f  test    eax, eax
0x180057d91  jns     short loc_180057D9D
0x180057d93  mov     r9d, 1EF5h
0x180057d99  mov     ecx, eax
0x180057d9b  jmp     short loc_180057D53
0x180057d9d  xor     ebx, ebx
0x180057d9f  mov     rdi, [rsp+140h+var_F0]
0x180057da4  mov     eax, cs:g_TrustedEnvironment
0x180057daa  test    eax, eax
0x180057dac  jnz     short loc_180057DB3
0x180057dae  call    GetTrustedEnvironment
0x180057db3  mov     r10d, 1
0x180057db9  test    r10b, al
0x180057dbc  jz      loc_180057E82
0x180057dc2  mov     eax, cs:dword_1800C95C0
0x180057dc8  cmp     eax, 5
0x180057dcb  jbe     loc_180057E82
0x180057dd1  mov     rdx, 400000000000h
0x180057ddb  lea     rcx, dword_1800C95C0
0x180057de2  call    _tlgKeywordOn
0x180057de7  test    al, al
0x180057de9  jz      loc_180057E82
0x180057def  lea     rax, [rsp+140h+var_E0]
0x180057df4  mov     [rsp+140h+var_E0], r10
0x180057df9  mov     [rbp+40h+var_B0], rax
0x180057dfd  lea     r9d, [r10+7]
0x180057e01  lea     rax, [rsp+140h+var_D8]
0x180057e06  mov     [rbp+40h+var_A8], r9
0x180057e0a  mov     [rbp+40h+var_A0], rax
0x180057e0e  lea     rdx, g_processImageName; "UNKNOWN"
0x180057e15  lea     rax, [rsp+140h+var_E8]
0x180057e1a  mov     [rsp+140h+var_D8], 1000000h
0x180057e23  mov     [rbp+40h+var_90], rax
0x180057e27  lea     rcx, [rbp+40h+var_70]
0x180057e2b  lea     rax, [rsp+140h+var_F0]
0x180057e30  mov     [rbp+40h+var_98], r9
0x180057e34  mov     [rbp+40h+var_80], rax
0x180057e38  mov     [rsp+140h+var_E8], ebx
0x180057e3c  mov     [rbp+40h+var_88], 4
0x180057e44  mov     dword ptr [rsp+140h+var_F0], r10d
0x180057e49  mov     [rbp+40h+var_78], 4
0x180057e51  call    _tlgCreate1Sz_wchar_t
0x180057e56  mov     rdx, rdi
0x180057e59  lea     rcx, [rbp+40h+var_60]
0x180057e5d  call    _tlgCreate1Sz_wchar_t
0x180057e62  lea     r10, [rsp+140h+var_D0]
0x180057e67  xor     r8d, r8d
0x180057e6a  lea     rdx, byte_1800C0873
0x180057e71  mov     [rsp+140h+var_120], r10
0x180057e76  lea     rcx, dword_1800C95C0
0x180057e7d  call    _tlgWriteAgg
0x180057e82  mov     eax, ebx
0x180057e84  mov     rcx, [rbp+40h+var_50]
0x180057e88  xor     rcx, rsp; StackCookie
0x180057e8b  call    __security_check_cookie
0x180057e90  add     rsp, 108h
0x180057e97  pop     r15
0x180057e99  pop     r14
0x180057e9b  pop     r13
0x180057e9d  pop     r12
0x180057e9f  pop     rdi
0x180057ea0  pop     rsi
0x180057ea1  pop     rbx
0x180057ea2  pop     rbp
0x180057ea3  retn
```
