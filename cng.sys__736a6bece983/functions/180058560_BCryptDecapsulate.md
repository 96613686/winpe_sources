# BCryptDecapsulate

- ea: `0x180058560`
- end: `0x180058795`
- name: `BCryptDecapsulate`
- size: `565`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800010ac`
- `0x18000743c`
- `0x180021af4`
- `0x1800363a0`
- `0x180045c80`
- `0x180058560`
- `0x18005bddc`
- `0x180060764`
- `0x18009f650`
- `0x18009f6d0`

## string_xrefs

- `0x1800585f8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005864a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
    && (unsigned int)dword_1800CB5C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800CB5C0, 0x400000000000LL) )
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
    tlgWriteAgg((unsigned int)&dword_1800CB5C0, (unsigned int)byte_1800C2E73, 0, v22, (__int64)v28);
  }
  return v14;
}

```

## disassembly

```asm
0x180058560  push    rbp
0x180058562  push    rbx
0x180058563  push    rsi
0x180058564  push    rdi
0x180058565  push    r12
0x180058567  push    r13
0x180058569  push    r14
0x18005856b  push    r15
0x18005856d  lea     rbp, [rsp-8]
0x180058572  sub     rsp, 108h
0x180058579  mov     rax, cs:__security_cookie
0x180058580  xor     rax, rsp
0x180058583  mov     [rbp+40h+var_50], rax
0x180058587  mov     r15, [rbp+40h+arg_28]
0x18005858b  mov     r14, r9
0x18005858e  mov     esi, r8d
0x180058591  mov     rdi, rdx
0x180058594  mov     rbx, rcx
0x180058597  mov     rcx, cs:WPP_GLOBAL_Control
0x18005859e  lea     rax, WPP_GLOBAL_Control
0x1800585a5  mov     r12d, [rbp+40h+arg_30]
0x1800585ac  mov     r13d, [rbp+40h+arg_20]
0x1800585b0  cmp     rcx, rax
0x1800585b3  jz      short loc_1800585E6
0x1800585b5  mov     eax, [rcx+2Ch]
0x1800585b8  test    al, 4
0x1800585ba  jz      short loc_1800585E6
0x1800585bc  mov     rcx, [rcx+18h]
0x1800585c0  mov     [rsp+140h+var_F8], r12d
0x1800585c5  mov     [rsp+140h+var_100], r15
0x1800585ca  mov     [rsp+140h+var_108], r13d
0x1800585cf  mov     [rsp+140h+var_110], r9
0x1800585d4  mov     r9, rbx
0x1800585d7  mov     dword ptr [rsp+140h+var_118], r8d
0x1800585dc  mov     [rsp+140h+var_120], rdx
0x1800585e1  call    WPP_SF_qqDqDqD
0x1800585e6  mov     rcx, rbx
0x1800585e9  call    ValidateBaseKeyHandle
0x1800585ee  mov     rcx, rax
0x1800585f1  test    rax, rax
0x1800585f4  jnz     short loc_18005861D
0x1800585f6  xor     edi, edi
0x1800585f8  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800585ff  mov     r9d, 1EDCh
0x180058605  lea     rdx, aStatus; "Status"
0x18005860c  mov     ecx, 0C0000008h
0x180058611  mov     ebx, 0C0000008h
0x180058616  call    DebugTraceError
0x18005861b  jmp     short loc_180058694
0x18005861d  mov     rax, [rax+8]
0x180058621  cmp     dword ptr [rax+24h], 8
0x180058625  lea     rdx, [rax+1BCh]
0x18005862c  mov     [rsp+140h+var_F0], rdx
0x180058631  jz      short loc_180058658
0x180058633  mov     ebx, 0C00000BBh
0x180058638  mov     r9d, 1EE6h
0x18005863e  mov     ecx, 0C00000BBh
0x180058643  lea     rdx, aStatus; "Status"
0x18005864a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058651  call    DebugTraceError
0x180058656  jmp     short loc_18005868F
0x180058658  mov     rax, [rax+70h]
0x18005865c  mov     r9, r14
0x18005865f  mov     rcx, [rcx+10h]
0x180058663  mov     r8d, esi
0x180058666  mov     dword ptr [rsp+140h+var_110], r12d
0x18005866b  mov     rdx, rdi
0x18005866e  mov     [rsp+140h+var_118], r15
0x180058673  mov     dword ptr [rsp+140h+var_120], r13d
0x180058678  call    _guard_dispatch_icall
0x18005867d  mov     ebx, eax
0x18005867f  test    eax, eax
0x180058681  jns     short loc_18005868D
0x180058683  mov     r9d, 1EF5h
0x180058689  mov     ecx, eax
0x18005868b  jmp     short loc_180058643
0x18005868d  xor     ebx, ebx
0x18005868f  mov     rdi, [rsp+140h+var_F0]
0x180058694  mov     eax, cs:g_TrustedEnvironment
0x18005869a  test    eax, eax
0x18005869c  jnz     short loc_1800586A3
0x18005869e  call    GetTrustedEnvironment
0x1800586a3  mov     r10d, 1
0x1800586a9  test    r10b, al
0x1800586ac  jz      loc_180058772
0x1800586b2  mov     eax, cs:dword_1800CB5C0
0x1800586b8  cmp     eax, 5
0x1800586bb  jbe     loc_180058772
0x1800586c1  mov     rdx, 400000000000h
0x1800586cb  lea     rcx, dword_1800CB5C0
0x1800586d2  call    _tlgKeywordOn
0x1800586d7  test    al, al
0x1800586d9  jz      loc_180058772
0x1800586df  lea     rax, [rsp+140h+var_E0]
0x1800586e4  mov     [rsp+140h+var_E0], r10
0x1800586e9  mov     [rbp+40h+var_B0], rax
0x1800586ed  lea     r9d, [r10+7]
0x1800586f1  lea     rax, [rsp+140h+var_D8]
0x1800586f6  mov     [rbp+40h+var_A8], r9
0x1800586fa  mov     [rbp+40h+var_A0], rax
0x1800586fe  lea     rdx, g_processImageName; "UNKNOWN"
0x180058705  lea     rax, [rsp+140h+var_E8]
0x18005870a  mov     [rsp+140h+var_D8], 1000000h
0x180058713  mov     [rbp+40h+var_90], rax
0x180058717  lea     rcx, [rbp+40h+var_70]
0x18005871b  lea     rax, [rsp+140h+var_F0]
0x180058720  mov     [rbp+40h+var_98], r9
0x180058724  mov     [rbp+40h+var_80], rax
0x180058728  mov     [rsp+140h+var_E8], ebx
0x18005872c  mov     [rbp+40h+var_88], 4
0x180058734  mov     dword ptr [rsp+140h+var_F0], r10d
0x180058739  mov     [rbp+40h+var_78], 4
0x180058741  call    _tlgCreate1Sz_wchar_t
0x180058746  mov     rdx, rdi
0x180058749  lea     rcx, [rbp+40h+var_60]
0x18005874d  call    _tlgCreate1Sz_wchar_t
0x180058752  lea     r10, [rsp+140h+var_D0]
0x180058757  xor     r8d, r8d
0x18005875a  lea     rdx, byte_1800C2E73
0x180058761  mov     [rsp+140h+var_120], r10
0x180058766  lea     rcx, dword_1800CB5C0
0x18005876d  call    _tlgWriteAgg
0x180058772  mov     eax, ebx
0x180058774  mov     rcx, [rbp+40h+var_50]
0x180058778  xor     rcx, rsp; StackCookie
0x18005877b  call    __security_check_cookie
0x180058780  add     rsp, 108h
0x180058787  pop     r15
0x180058789  pop     r14
0x18005878b  pop     r13
0x18005878d  pop     r12
0x18005878f  pop     rdi
0x180058790  pop     rsi
0x180058791  pop     rbx
0x180058792  pop     rbp
0x180058793  retn
```
