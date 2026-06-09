# CheckSignaturePadding

- ea: `0x180069424`
- end: `0x180069791`
- name: `CheckSignaturePadding`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005aa50`

## callees

- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180068390`
- `0x180068438`
- `0x1800691b8`
- `0x180069424`
- `0x1800699e8`

## string_xrefs

- `0x18006947c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800694ae`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800695ab`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180069755`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall CheckSignaturePadding(char a1, __int64 a2, __int64 a3, int a4, void *Buf2, size_t Size)
{
  BCRYPT_HANDLE v6; // rsi
  __int64 v7; // rdi
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // r9
  NTSTATUS Property; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  NTSTATUS v22; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  int v25; // eax
  size_t dwFlags; // [rsp+28h] [rbp-28h]
  size_t dwFlagsa; // [rsp+28h] [rbp-28h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-10h] BYREF
  UCHAR v30[4]; // [rsp+44h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+80h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v30 = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( (a1 & 2) == 0 )
  {
    if ( (a1 & 8) == 0 )
    {
      v17 = 1721;
      goto LABEL_44;
    }
    if ( !a2 || !*(_QWORD *)a2 )
    {
      v11 = 1665;
      goto LABEL_4;
    }
    v14 = CachedOpenAlgorithmProvider(&hObject);
    v12 = v14;
    if ( v14 < 0 )
    {
      v15 = 1676;
      goto LABEL_9;
    }
    v6 = hObject;
    Property = BCryptGetProperty(hObject, L"ObjectLength", v30, 4u, &cbOutput, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1688;
      goto LABEL_12;
    }
    Property = BCryptGetProperty(v6, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1700;
      goto LABEL_12;
    }
    Property = CheckPSSPadding(
                 v6,
                 *(unsigned int *)pbOutput,
                 *(unsigned int *)v30,
                 *(unsigned int *)(a2 + 8),
                 a3,
                 a4,
                 Buf2,
                 Size);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1714;
      goto LABEL_12;
    }
    goto LABEL_40;
  }
  if ( !a2 )
  {
    v11 = 1549;
LABEL_4:
    v12 = -1073741811;
    v13 = 3221225485LL;
LABEL_5:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v11);
    return v12;
  }
  if ( !*(_QWORD *)a2 )
  {
    LODWORD(dwFlags) = Size;
    v25 = VerifyPKCS1SigningFormat(0, 0, a3, a4, Buf2, dwFlags, 0);
    v12 = v25;
    if ( v25 < 0 )
    {
      v11 = 1653;
      v13 = (unsigned int)v25;
      goto LABEL_5;
    }
    goto LABEL_40;
  }
  v14 = CachedOpenAlgorithmProvider(&hObject);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1562;
LABEL_9:
    DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v15);
    v6 = hObject;
    goto LABEL_46;
  }
  v6 = hObject;
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  v12 = Property;
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput != a4 )
    {
      v17 = 1580;
LABEL_44:
      v18 = 3221225485LL;
      v12 = -1073741811;
      goto LABEL_45;
    }
    Property = BCryptGetProperty(v6, L"HashOIDList", 0, 0, &cbOutput, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1592;
      goto LABEL_12;
    }
    v7 = MSCryptAlloc(cbOutput, v19, v20, v21);
    if ( !v7 )
    {
      v12 = -1073741801;
      v17 = 1602;
      v18 = 3221225495LL;
      goto LABEL_45;
    }
    v22 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v12 = v22;
    if ( v22 < 0 )
    {
      v23 = 1614;
LABEL_21:
      v24 = (unsigned int)v22;
LABEL_22:
      DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v23);
LABEL_41:
      MSCryptFree((PVOID)v7);
      goto LABEL_46;
    }
    if ( !*(_DWORD *)v7 )
    {
      v12 = -1073741595;
      v23 = 1623;
      v24 = 3221225701LL;
      goto LABEL_22;
    }
    LODWORD(dwFlagsa) = Size;
    v22 = VerifyPKCS1SigningFormat(*(_DWORD *)v7, *(_QWORD *)(v7 + 8), a3, a4, Buf2, dwFlagsa, 1);
    v12 = v22;
    if ( v22 < 0 )
    {
      v23 = 1637;
      goto LABEL_21;
    }
LABEL_40:
    v12 = 0;
    if ( !v7 )
      goto LABEL_46;
    goto LABEL_41;
  }
  v17 = 1574;
LABEL_12:
  v18 = (unsigned int)Property;
LABEL_45:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v17);
LABEL_46:
  if ( v6 )
    CachedCloseAlgorithmProvider(v6);
  return v12;
}

```

## disassembly

```asm
0x180069424  mov     [rsp-28h+arg_8], rbx
0x180069429  mov     [rsp-28h+arg_10], rsi
0x18006942e  push    rbp
0x18006942f  push    rdi
0x180069430  push    r12
0x180069432  push    r14
0x180069434  push    r15
0x180069436  mov     rbp, rsp
0x180069439  sub     rsp, 50h
0x18006943d  xor     esi, esi
0x18006943f  xor     edi, edi
0x180069441  mov     [rbp+hObject], rsi
0x180069445  mov     r15d, r9d
0x180069448  mov     dword ptr [rbp+var_C], esi
0x18006944b  mov     r12, r8
0x18006944e  mov     dword ptr [rbp+pbOutput], esi
0x180069451  mov     r14, rdx
0x180069454  mov     [rbp+cbOutput], esi
0x180069457  test    cl, 2
0x18006945a  jz      loc_180069641
0x180069460  test    rdx, rdx
0x180069463  jnz     short loc_18006948D
0x180069465  mov     r9d, 60Dh
0x18006946b  mov     ebx, 0C000000Dh
0x180069470  mov     ecx, 0C000000Dh
0x180069475  lea     rdx, aStatus; "Status"
0x18006947c  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069483  call    DebugTraceError
0x180069488  jmp     loc_180069775
0x18006948d  mov     rdx, [rdx]
0x180069490  test    rdx, rdx
0x180069493  jz      loc_18006960D
0x180069499  lea     rcx, [rbp+hObject]
0x18006949d  call    CachedOpenAlgorithmProvider
0x1800694a2  mov     ebx, eax
0x1800694a4  test    eax, eax
0x1800694a6  jns     short loc_1800694CC
0x1800694a8  mov     r9d, 61Ah
0x1800694ae  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800694b5  mov     ecx, eax
0x1800694b7  lea     rdx, aStatus; "Status"
0x1800694be  call    DebugTraceError
0x1800694c3  mov     rsi, [rbp+hObject]
0x1800694c7  jmp     loc_180069768
0x1800694cc  mov     dword ptr [rsp+50h+dwFlags], esi; dwFlags
0x1800694d0  lea     rax, [rbp+cbOutput]
0x1800694d4  mov     rsi, [rbp+hObject]
0x1800694d8  lea     r8, [rbp+pbOutput]; pbOutput
0x1800694dc  mov     rcx, rsi; hObject
0x1800694df  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800694e4  mov     r9d, 4; cbOutput
0x1800694ea  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800694f1  call    BCryptGetProperty
0x1800694f6  mov     ebx, eax
0x1800694f8  test    eax, eax
0x1800694fa  jns     short loc_180069509
0x1800694fc  mov     r9d, 626h
0x180069502  mov     ecx, eax
0x180069504  jmp     loc_180069755
0x180069509  cmp     dword ptr [rbp+pbOutput], r15d
0x18006950d  jz      short loc_18006951A
0x18006950f  mov     r9d, 62Ch
0x180069515  jmp     loc_18006974B
0x18006951a  lea     rax, [rbp+cbOutput]
0x18006951e  mov     dword ptr [rsp+50h+dwFlags], edi; dwFlags
0x180069522  xor     r9d, r9d; cbOutput
0x180069525  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18006952a  xor     r8d, r8d; pbOutput
0x18006952d  lea     rdx, aHashoidlist; "HashOIDList"
0x180069534  mov     rcx, rsi; hObject
0x180069537  call    BCryptGetProperty
0x18006953c  mov     ebx, eax
0x18006953e  test    eax, eax
0x180069540  jns     short loc_18006954A
0x180069542  mov     r9d, 638h
0x180069548  jmp     short loc_180069502
0x18006954a  mov     ecx, [rbp+cbOutput]
0x18006954d  call    MSCryptAlloc
0x180069552  mov     rdi, rax
0x180069555  test    rax, rax
0x180069558  jnz     short loc_18006956F
0x18006955a  mov     ebx, 0C0000017h
0x18006955f  mov     r9d, 642h
0x180069565  mov     ecx, 0C0000017h
0x18006956a  jmp     loc_180069755
0x18006956f  mov     r9d, [rbp+cbOutput]; cbOutput
0x180069573  lea     rax, [rbp+cbOutput]
0x180069577  mov     dword ptr [rsp+50h+dwFlags], 0; dwFlags
0x18006957f  lea     rdx, aHashoidlist; "HashOIDList"
0x180069586  mov     r8, rdi; pbOutput
0x180069589  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18006958e  mov     rcx, rsi; hObject
0x180069591  call    BCryptGetProperty
0x180069596  mov     ebx, eax
0x180069598  test    eax, eax
0x18006959a  jns     short loc_1800695BC
0x18006959c  mov     r9d, 64Eh
0x1800695a2  mov     ecx, eax
0x1800695a4  lea     rdx, aStatus; "Status"
0x1800695ab  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800695b2  call    DebugTraceError
0x1800695b7  jmp     loc_180069730
0x1800695bc  mov     ecx, [rdi]; int
0x1800695be  test    ecx, ecx
0x1800695c0  jnz     short loc_1800695D4
0x1800695c2  mov     ebx, 0C00000E5h
0x1800695c7  mov     r9d, 657h
0x1800695cd  mov     ecx, 0C00000E5h
0x1800695d2  jmp     short loc_1800695A4
0x1800695d4  mov     eax, dword ptr [rbp+Size]
0x1800695d7  mov     r9d, r15d; int
0x1800695da  mov     rdx, [rdi+8]; int
0x1800695de  mov     r8, r12; int
0x1800695e1  mov     [rsp+50h+var_20], 1; int
0x1800695e9  mov     dword ptr [rsp+50h+dwFlags], eax; Size
0x1800695ed  mov     rax, [rbp+Buf2]
0x1800695f1  mov     [rsp+50h+pcbResult], rax; Buf2
0x1800695f6  call    VerifyPKCS1SigningFormat
0x1800695fb  mov     ebx, eax
0x1800695fd  test    eax, eax
0x1800695ff  jns     loc_180069729
0x180069605  mov     r9d, 665h; int
0x18006960b  jmp     short loc_1800695A2
0x18006960d  mov     eax, dword ptr [rbp+Size]
0x180069610  xor     edx, edx; int
0x180069612  mov     [rsp+50h+var_20], esi; int
0x180069616  xor     ecx, ecx; int
0x180069618  mov     dword ptr [rsp+50h+dwFlags], eax; Size
0x18006961c  mov     rax, [rbp+Buf2]
0x180069620  mov     [rsp+50h+pcbResult], rax; Buf2
0x180069625  call    VerifyPKCS1SigningFormat
0x18006962a  mov     ebx, eax
0x18006962c  test    eax, eax
0x18006962e  jns     loc_180069729
0x180069634  mov     r9d, 675h
0x18006963a  mov     ecx, eax
0x18006963c  jmp     loc_180069475
0x180069641  test    cl, 8
0x180069644  jz      loc_180069745
0x18006964a  test    r14, r14
0x18006964d  jz      loc_18006973A
0x180069653  mov     rdx, [rdx]
0x180069656  test    rdx, rdx
0x180069659  jz      loc_18006973A
0x18006965f  lea     rcx, [rbp+hObject]
0x180069663  call    CachedOpenAlgorithmProvider
0x180069668  mov     ebx, eax
0x18006966a  test    eax, eax
0x18006966c  jns     short loc_180069679
0x18006966e  mov     r9d, 68Ch
0x180069674  jmp     loc_1800694AE
0x180069679  mov     dword ptr [rsp+50h+dwFlags], esi; dwFlags
0x18006967d  lea     rax, [rbp+cbOutput]
0x180069681  mov     rsi, [rbp+hObject]
0x180069685  lea     r8, [rbp+var_C]; pbOutput
0x180069689  mov     rcx, rsi; hObject
0x18006968c  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180069691  mov     r9d, 4; cbOutput
0x180069697  lea     rdx, aObjectlength; "ObjectLength"
0x18006969e  call    BCryptGetProperty
0x1800696a3  mov     ebx, eax
0x1800696a5  test    eax, eax
0x1800696a7  jns     short loc_1800696B4
0x1800696a9  mov     r9d, 698h
0x1800696af  jmp     loc_180069502
0x1800696b4  lea     rax, [rbp+cbOutput]
0x1800696b8  mov     dword ptr [rsp+50h+dwFlags], edi; dwFlags
0x1800696bc  mov     r9d, 4; cbOutput
0x1800696c2  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800696c7  lea     r8, [rbp+pbOutput]; pbOutput
0x1800696cb  mov     rcx, rsi; hObject
0x1800696ce  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800696d5  call    BCryptGetProperty
0x1800696da  mov     ebx, eax
0x1800696dc  test    eax, eax
0x1800696de  jns     short loc_1800696EB
0x1800696e0  mov     r9d, 6A4h
0x1800696e6  jmp     loc_180069502
0x1800696eb  mov     eax, dword ptr [rbp+Size]
0x1800696ee  mov     rcx, rsi
0x1800696f1  mov     r9d, [r14+8]
0x1800696f5  mov     r8d, dword ptr [rbp+var_C]
0x1800696f9  mov     edx, dword ptr [rbp+pbOutput]
0x1800696fc  mov     [rsp+50h+var_18], eax
0x180069700  mov     rax, [rbp+Buf2]
0x180069704  mov     qword ptr [rsp+50h+var_20], rax
0x180069709  mov     dword ptr [rsp+50h+dwFlags], r15d
0x18006970e  mov     [rsp+50h+pcbResult], r12
0x180069713  call    CheckPSSPadding
0x180069718  mov     ebx, eax
0x18006971a  test    eax, eax
0x18006971c  jns     short loc_180069729
0x18006971e  mov     r9d, 6B2h
0x180069724  jmp     loc_180069502
0x180069729  xor     ebx, ebx
0x18006972b  test    rdi, rdi
0x18006972e  jz      short loc_180069768
0x180069730  mov     rcx, rdi; P
0x180069733  call    MSCryptFree
0x180069738  jmp     short loc_180069768
0x18006973a  mov     r9d, 681h
0x180069740  jmp     loc_18006946B
0x180069745  mov     r9d, 6B9h
0x18006974b  mov     ecx, 0C000000Dh
0x180069750  mov     ebx, 0C000000Dh
0x180069755  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006975c  lea     rdx, aStatus; "Status"
0x180069763  call    DebugTraceError
0x180069768  test    rsi, rsi
0x18006976b  jz      short loc_180069775
0x18006976d  mov     rcx, rsi; hAlgorithm
0x180069770  call    CachedCloseAlgorithmProvider
0x180069775  lea     r11, [rsp+50h+var_s0]
0x18006977a  mov     eax, ebx
0x18006977c  mov     rbx, [r11+38h]
0x180069780  mov     rsi, [r11+40h]
0x180069784  mov     rsp, r11
0x180069787  pop     r15
0x180069789  pop     r14
0x18006978b  pop     r12
0x18006978d  pop     rdi
0x18006978e  pop     rbp
0x18006978f  retn
```
