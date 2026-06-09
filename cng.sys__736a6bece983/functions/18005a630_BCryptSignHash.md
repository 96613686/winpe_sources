# BCryptSignHash

- ea: `0x18005a630`
- end: `0x18005aa40`
- name: `BCryptSignHash`
- size: `1040`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, void *pPaddingInfo, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x1800010ac`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180021af4`
- `0x1800363a0`
- `0x180043004`
- `0x180045c80`
- `0x18005a630`
- `0x18005c4ec`
- `0x180060764`
- `0x180068b64`
- `0x18009f650`
- `0x18009f6d0`

## string_xrefs

- `0x18005a6ff`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005a91d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptSignHash(
        BCRYPT_KEY_HANDLE hKey,
        void *pPaddingInfo,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  void *v8; // r14
  __int64 v9; // rdi
  NTSTATUS v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // rsi
  __int64 v16; // rdi
  int v17; // eax
  __int64 (__fastcall *v18)(_QWORD, _QWORD *, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG); // rdi
  int Property; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  NTSTATUS v25; // r15d
  unsigned int v26; // eax
  char TrustedEnvironment; // al
  _QWORD *v28; // r10
  int v29; // r9d
  UCHAR v31[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v32; // [rsp+64h] [rbp-9Ch] BYREF
  NTSTATUS v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v36; // [rsp+80h] [rbp-80h] BYREF
  ULONG v37; // [rsp+88h] [rbp-78h] BYREF
  char v38[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD **v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  __int64 *v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  NTSTATUS *v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  ULONG *v45; // [rsp+E0h] [rbp-20h]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  char v47[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v48[16]; // [rsp+100h] [rbp+0h] BYREF

  v8 = 0;
  v33 = 0;
  v9 = 0;
  *(_DWORD *)v31 = 0;
  v37 = 0;
  v32 = cbInput;
  v35 = (__int64)pbInput;
  v36 = pPaddingInfo;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      38,
      pbInput,
      hKey,
      pPaddingInfo,
      pbInput,
      cbInput,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
  if ( !pcbResult )
  {
    v11 = -1073741811;
    v12 = 6642;
    v13 = 3221225485LL;
LABEL_6:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
    goto LABEL_36;
  }
  v14 = ValidateBaseKeyHandle(hKey);
  v15 = (_QWORD *)v14;
  if ( !v14 )
  {
    v11 = -1073741816;
    v12 = 6650;
    v13 = 3221225480LL;
    goto LABEL_6;
  }
  v16 = *(_QWORD *)(v14 + 8);
  v34 = v16 + 444;
  v17 = *(_DWORD *)(v16 + 36);
  if ( v17 == 5 )
  {
    v18 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 104);
LABEL_11:
    Property = v18(v15[2], v36, v35, v32, pbOutput, cbOutput, pcbResult, dwFlags);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6783;
LABEL_16:
      v24 = (unsigned int)Property;
LABEL_34:
      DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
      goto LABEL_35;
    }
    goto LABEL_32;
  }
  if ( v17 != 3 )
  {
    v11 = -1073741637;
    v20 = 6705;
    v24 = 3221225659LL;
    goto LABEL_34;
  }
  Property = ShouldRouterPadSignature(*(unsigned int *)(v16 + 440), dwFlags, &v33);
  v11 = Property;
  if ( Property < 0 )
  {
    v20 = 6678;
    goto LABEL_16;
  }
  v25 = v33;
  if ( v33 )
  {
    Property = BCryptGetProperty(v15, L"KeyStrength", v31, 4u, &v37, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6693;
      goto LABEL_16;
    }
    v26 = (unsigned int)(*(_DWORD *)v31 + 7) >> 3;
    *(_DWORD *)v31 = v26;
  }
  else
  {
    v26 = *(_DWORD *)v31;
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 144);
  if ( !v25 )
    goto LABEL_11;
  if ( !pbOutput )
  {
    Property = v18(v15[2], 0, v35, v32, 0, cbOutput, pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6724;
      goto LABEL_16;
    }
    goto LABEL_32;
  }
  v8 = (void *)MSCryptAlloc(v26, v21, v22, v23);
  if ( v8 )
  {
    Property = ApplySignaturePadding(dwFlags, v36, v35, v32, (__int64)v8, *(int *)v31);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6752;
      goto LABEL_16;
    }
    Property = v18(v15[2], 0, (__int64)v8, *(unsigned int *)v31, pbOutput, cbOutput, pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6766;
      goto LABEL_16;
    }
LABEL_32:
    v11 = 0;
    goto LABEL_35;
  }
  v11 = -1073741801;
LABEL_35:
  v9 = v34;
LABEL_36:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && (unsigned int)dword_1800CB5C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800CB5C0, 0x400000000000LL) )
  {
    v36 = v28;
    v39 = &v36;
    v40 = (unsigned int)((_DWORD)v28 + 7);
    v41 = &v35;
    v35 = 0x1000000;
    v43 = &v33;
    v42 = v40;
    v45 = &v32;
    v33 = v11;
    v44 = 4;
    v32 = (unsigned int)v28;
    v46 = 4;
    tlgCreate1Sz_wchar_t(v47, g_processImageName);
    tlgCreate1Sz_wchar_t(v48, v9);
    tlgWriteAgg((unsigned int)&dword_1800CB5C0, (unsigned int)byte_1800C2D6B, 0, v29, (__int64)v38);
  }
  if ( v8 )
    MSCryptFree(v8);
  return v11;
}

```

## disassembly

```asm
0x18005a630  push    rbp
0x18005a632  push    rbx
0x18005a633  push    rsi
0x18005a634  push    rdi
0x18005a635  push    r12
0x18005a637  push    r13
0x18005a639  push    r14
0x18005a63b  push    r15
0x18005a63d  lea     rbp, [rsp-28h]
0x18005a642  sub     rsp, 128h
0x18005a649  mov     rax, cs:__security_cookie
0x18005a650  xor     rax, rsp
0x18005a653  mov     [rbp+60h+var_50], rax
0x18005a657  mov     r13, [rbp+60h+pbOutput]
0x18005a65e  xor     eax, eax
0x18005a660  mov     r12, [rbp+60h+pcbResult]
0x18005a667  mov     r14d, eax
0x18005a66a  mov     [rsp+160h+var_F8], eax
0x18005a66e  mov     edi, eax
0x18005a670  mov     dword ptr [rsp+160h+var_100], eax
0x18005a674  mov     r10, rdx
0x18005a677  mov     [rbp+60h+var_D8], eax
0x18005a67a  mov     rbx, rcx
0x18005a67d  mov     [rsp+160h+var_FC], r9d
0x18005a682  mov     [rsp+160h+var_E8], r8
0x18005a687  mov     [rbp+60h+var_E0], rdx
0x18005a68b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a692  lea     rax, WPP_GLOBAL_Control
0x18005a699  mov     r15d, [rbp+60h+dwFlags]
0x18005a6a0  cmp     rcx, rax
0x18005a6a3  jz      short loc_18005A6E3
0x18005a6a5  mov     eax, [rcx+2Ch]
0x18005a6a8  test    al, 4
0x18005a6aa  jz      short loc_18005A6E3
0x18005a6ac  mov     eax, [rbp+60h+cbOutput]
0x18005a6b2  lea     edx, [rdi+26h]
0x18005a6b5  mov     rcx, [rcx+18h]
0x18005a6b9  mov     [rsp+160h+var_110], r15d
0x18005a6be  mov     [rsp+160h+var_118], r12
0x18005a6c3  mov     [rsp+160h+var_120], eax
0x18005a6c7  mov     [rsp+160h+var_128], r13
0x18005a6cc  mov     dword ptr [rsp+160h+var_130], r9d
0x18005a6d1  mov     r9, rbx
0x18005a6d4  mov     qword ptr [rsp+160h+var_138], r8
0x18005a6d9  mov     [rsp+160h+var_140], r10
0x18005a6de  call    WPP_SF_qqqdqdqD
0x18005a6e3  test    r12, r12
0x18005a6e6  jnz     short loc_18005A710
0x18005a6e8  mov     ebx, 0C000000Dh
0x18005a6ed  mov     r9d, 19F2h
0x18005a6f3  mov     ecx, 0C000000Dh
0x18005a6f8  lea     rdx, aStatus; "Status"
0x18005a6ff  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a706  call    DebugTraceError
0x18005a70b  jmp     loc_18005A935
0x18005a710  mov     rcx, rbx
0x18005a713  call    ValidateBaseKeyHandle
0x18005a718  mov     rsi, rax
0x18005a71b  test    rax, rax
0x18005a71e  jnz     short loc_18005A732
0x18005a720  mov     ebx, 0C0000008h
0x18005a725  mov     r9d, 19FAh
0x18005a72b  mov     ecx, 0C0000008h
0x18005a730  jmp     short loc_18005A6F8
0x18005a732  mov     rdi, [rax+8]
0x18005a736  lea     rax, [rdi+1BCh]
0x18005a73d  mov     [rsp+160h+var_F0], rax
0x18005a742  mov     eax, [rdi+24h]
0x18005a745  cmp     eax, 5
0x18005a748  jnz     short loc_18005A798
0x18005a74a  mov     rdi, [rdi+68h]
0x18005a74e  mov     eax, [rbp+60h+dwFlags]
0x18005a754  mov     r9d, [rsp+160h+var_FC]
0x18005a759  mov     r8, [rsp+160h+var_E8]
0x18005a75e  mov     rdx, [rbp+60h+var_E0]
0x18005a762  mov     rcx, [rsi+10h]
0x18005a766  mov     dword ptr [rsp+160h+var_128], eax
0x18005a76a  mov     eax, [rbp+60h+cbOutput]
0x18005a770  mov     [rsp+160h+var_130], r12
0x18005a775  mov     [rsp+160h+var_138], eax
0x18005a779  mov     rax, rdi
0x18005a77c  mov     [rsp+160h+var_140], r13
0x18005a781  call    _guard_dispatch_icall
0x18005a786  mov     ebx, eax
0x18005a788  test    eax, eax
0x18005a78a  jns     loc_18005A909
0x18005a790  mov     r9d, 1A7Fh
0x18005a796  jmp     short loc_18005A7C0
0x18005a798  cmp     eax, 3
0x18005a79b  jnz     loc_18005A90D
0x18005a7a1  mov     ecx, [rdi+1B8h]
0x18005a7a7  lea     r8, [rsp+160h+var_F8]
0x18005a7ac  mov     edx, r15d
0x18005a7af  call    ShouldRouterPadSignature
0x18005a7b4  mov     ebx, eax
0x18005a7b6  test    eax, eax
0x18005a7b8  jns     short loc_18005A7C7
0x18005a7ba  mov     r9d, 1A16h
0x18005a7c0  mov     ecx, eax
0x18005a7c2  jmp     loc_18005A91D
0x18005a7c7  mov     r15d, [rsp+160h+var_F8]
0x18005a7cc  test    r15d, r15d
0x18005a7cf  jz      short loc_18005A817
0x18005a7d1  lea     rax, [rbp+60h+var_D8]
0x18005a7d5  mov     [rsp+160h+var_138], r14d; dwFlags
0x18005a7da  mov     r9d, 4; cbOutput
0x18005a7e0  mov     [rsp+160h+var_140], rax; pcbResult
0x18005a7e5  lea     r8, [rsp+160h+var_100]; pbOutput
0x18005a7ea  mov     rcx, rsi; hObject
0x18005a7ed  lea     rdx, aKeystrength; "KeyStrength"
0x18005a7f4  call    BCryptGetProperty
0x18005a7f9  mov     ebx, eax
0x18005a7fb  test    eax, eax
0x18005a7fd  jns     short loc_18005A807
0x18005a7ff  mov     r9d, 1A25h
0x18005a805  jmp     short loc_18005A7C0
0x18005a807  mov     eax, dword ptr [rsp+160h+var_100]
0x18005a80b  add     eax, 7
0x18005a80e  shr     eax, 3
0x18005a811  mov     dword ptr [rsp+160h+var_100], eax
0x18005a815  jmp     short loc_18005A81B
0x18005a817  mov     eax, dword ptr [rsp+160h+var_100]
0x18005a81b  mov     rdi, [rdi+90h]
0x18005a822  test    r15d, r15d
0x18005a825  jz      loc_18005A74E
0x18005a82b  test    r13, r13
0x18005a82e  jnz     short loc_18005A876
0x18005a830  mov     eax, [rbp+60h+cbOutput]
0x18005a836  xor     edx, edx
0x18005a838  mov     r9d, [rsp+160h+var_FC]
0x18005a83d  mov     r8, [rsp+160h+var_E8]
0x18005a842  mov     rcx, [rsi+10h]
0x18005a846  mov     dword ptr [rsp+160h+var_128], r14d
0x18005a84b  mov     [rsp+160h+var_130], r12
0x18005a850  mov     [rsp+160h+var_138], eax
0x18005a854  mov     rax, rdi
0x18005a857  mov     [rsp+160h+var_140], r14
0x18005a85c  call    _guard_dispatch_icall
0x18005a861  mov     ebx, eax
0x18005a863  test    eax, eax
0x18005a865  jns     loc_18005A909
0x18005a86b  mov     r9d, 1A44h
0x18005a871  jmp     loc_18005A7C0
0x18005a876  mov     ecx, eax
0x18005a878  call    MSCryptAlloc
0x18005a87d  mov     r14, rax
0x18005a880  test    rax, rax
0x18005a883  jnz     short loc_18005A88F
0x18005a885  mov     ebx, 0C0000017h
0x18005a88a  jmp     loc_18005A930
0x18005a88f  mov     eax, dword ptr [rsp+160h+var_100]
0x18005a893  mov     r9d, [rsp+160h+var_FC]
0x18005a898  mov     r8, [rsp+160h+var_E8]
0x18005a89d  mov     rdx, [rbp+60h+var_E0]
0x18005a8a1  mov     ecx, [rbp+60h+dwFlags]
0x18005a8a7  mov     [rsp+160h+var_138], eax
0x18005a8ab  mov     [rsp+160h+var_140], r14
0x18005a8b0  call    ApplySignaturePadding
0x18005a8b5  mov     ebx, eax
0x18005a8b7  test    eax, eax
0x18005a8b9  jns     short loc_18005A8C6
0x18005a8bb  mov     r9d, 1A60h
0x18005a8c1  jmp     loc_18005A7C0
0x18005a8c6  mov     eax, [rbp+60h+cbOutput]
0x18005a8cc  mov     r8, r14
0x18005a8cf  mov     r9d, dword ptr [rsp+160h+var_100]
0x18005a8d4  xor     edx, edx
0x18005a8d6  mov     rcx, [rsi+10h]
0x18005a8da  mov     dword ptr [rsp+160h+var_128], 0
0x18005a8e2  mov     [rsp+160h+var_130], r12
0x18005a8e7  mov     [rsp+160h+var_138], eax
0x18005a8eb  mov     rax, rdi
0x18005a8ee  mov     [rsp+160h+var_140], r13
0x18005a8f3  call    _guard_dispatch_icall
0x18005a8f8  mov     ebx, eax
0x18005a8fa  test    eax, eax
0x18005a8fc  jns     short loc_18005A909
0x18005a8fe  mov     r9d, 1A6Eh
0x18005a904  jmp     loc_18005A7C0
0x18005a909  xor     ebx, ebx
0x18005a90b  jmp     short loc_18005A930
0x18005a90d  mov     ebx, 0C00000BBh
0x18005a912  mov     r9d, 1A31h
0x18005a918  mov     ecx, 0C00000BBh
0x18005a91d  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a924  lea     rdx, aStatus; "Status"
0x18005a92b  call    DebugTraceError
0x18005a930  mov     rdi, [rsp+160h+var_F0]
0x18005a935  mov     eax, cs:g_TrustedEnvironment
0x18005a93b  test    eax, eax
0x18005a93d  jnz     short loc_18005A944
0x18005a93f  call    GetTrustedEnvironment
0x18005a944  mov     r10d, 1
0x18005a94a  test    r10b, al
0x18005a94d  jz      loc_18005AA10
0x18005a953  mov     eax, cs:dword_1800CB5C0
0x18005a959  cmp     eax, 5
0x18005a95c  jbe     loc_18005AA10
0x18005a962  mov     rdx, 400000000000h
0x18005a96c  lea     rcx, dword_1800CB5C0
0x18005a973  call    _tlgKeywordOn
0x18005a978  test    al, al
0x18005a97a  jz      loc_18005AA10
0x18005a980  lea     rax, [rbp+60h+var_E0]
0x18005a984  mov     [rbp+60h+var_E0], r10
0x18005a988  mov     [rbp+60h+var_B0], rax
0x18005a98c  lea     r9d, [r10+7]
0x18005a990  lea     rax, [rsp+160h+var_E8]
0x18005a995  mov     [rbp+60h+var_A8], r9
0x18005a999  mov     [rbp+60h+var_A0], rax
0x18005a99d  lea     rdx, g_processImageName; "UNKNOWN"
0x18005a9a4  lea     rax, [rsp+160h+var_F8]
0x18005a9a9  mov     [rsp+160h+var_E8], 1000000h
0x18005a9b2  mov     [rbp+60h+var_90], rax
0x18005a9b6  lea     rcx, [rbp+60h+var_70]
0x18005a9ba  lea     rax, [rsp+160h+var_FC]
0x18005a9bf  mov     [rbp+60h+var_98], r9
0x18005a9c3  mov     [rbp+60h+var_80], rax
0x18005a9c7  mov     [rsp+160h+var_F8], ebx
0x18005a9cb  mov     [rbp+60h+var_88], 4
0x18005a9d3  mov     [rsp+160h+var_FC], r10d
0x18005a9d8  mov     [rbp+60h+var_78], 4
0x18005a9e0  call    _tlgCreate1Sz_wchar_t
0x18005a9e5  mov     rdx, rdi
0x18005a9e8  lea     rcx, [rbp+60h+var_60]
0x18005a9ec  call    _tlgCreate1Sz_wchar_t
0x18005a9f1  lea     r10, [rbp+60h+var_D0]
0x18005a9f5  xor     r8d, r8d
0x18005a9f8  lea     rdx, byte_1800C2D6B
0x18005a9ff  mov     [rsp+160h+var_140], r10
0x18005aa04  lea     rcx, dword_1800CB5C0
0x18005aa0b  call    _tlgWriteAgg
0x18005aa10  test    r14, r14
0x18005aa13  jz      short loc_18005AA1D
0x18005aa15  mov     rcx, r14; P
0x18005aa18  call    MSCryptFree
0x18005aa1d  mov     eax, ebx
0x18005aa1f  mov     rcx, [rbp+60h+var_50]
0x18005aa23  xor     rcx, rsp; StackCookie
0x18005aa26  call    __security_check_cookie
0x18005aa2b  add     rsp, 128h
0x18005aa32  pop     r15
0x18005aa34  pop     r14
0x18005aa36  pop     r13
0x18005aa38  pop     r12
0x18005aa3a  pop     rdi
0x18005aa3b  pop     rsi
0x18005aa3c  pop     rbx
0x18005aa3d  pop     rbp
0x18005aa3e  retn
```
