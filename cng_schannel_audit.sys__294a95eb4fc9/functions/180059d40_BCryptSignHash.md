# BCryptSignHash

- ea: `0x180059d40`
- end: `0x18005a150`
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
- `0x180024a34`
- `0x1800358a0`
- `0x180042574`
- `0x1800451f0`
- `0x180059d40`
- `0x18005bbfc`
- `0x18005fe74`
- `0x180068164`
- `0x18009d820`
- `0x18009d860`

## string_xrefs

- `0x180059e0f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005a02d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  __int64 v22; // rcx
  NTSTATUS v23; // r15d
  unsigned int v24; // eax
  char TrustedEnvironment; // al
  _QWORD *v26; // r10
  int v27; // r9d
  UCHAR v29[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v30; // [rsp+64h] [rbp-9Ch] BYREF
  NTSTATUS v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v34; // [rsp+80h] [rbp-80h] BYREF
  ULONG v35; // [rsp+88h] [rbp-78h] BYREF
  char v36[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD **v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  NTSTATUS *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  ULONG *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  char v45[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v46[16]; // [rsp+100h] [rbp+0h] BYREF

  v8 = 0;
  v31 = 0;
  v9 = 0;
  *(_DWORD *)v29 = 0;
  v35 = 0;
  v30 = cbInput;
  v33 = (__int64)pbInput;
  v34 = pPaddingInfo;
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
  v32 = v16 + 444;
  v17 = *(_DWORD *)(v16 + 36);
  if ( v17 == 5 )
  {
    v18 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 104);
LABEL_11:
    Property = v18(v15[2], v34, v33, v30, pbOutput, cbOutput, pcbResult, dwFlags);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6783;
LABEL_16:
      v22 = (unsigned int)Property;
LABEL_34:
      DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
      goto LABEL_35;
    }
    goto LABEL_32;
  }
  if ( v17 != 3 )
  {
    v11 = -1073741637;
    v20 = 6705;
    v22 = 3221225659LL;
    goto LABEL_34;
  }
  Property = ShouldRouterPadSignature(*(unsigned int *)(v16 + 440), dwFlags, &v31);
  v11 = Property;
  if ( Property < 0 )
  {
    v20 = 6678;
    goto LABEL_16;
  }
  v23 = v31;
  if ( v31 )
  {
    Property = BCryptGetProperty(v15, L"KeyStrength", v29, 4u, &v35, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6693;
      goto LABEL_16;
    }
    v24 = (unsigned int)(*(_DWORD *)v29 + 7) >> 3;
    *(_DWORD *)v29 = v24;
  }
  else
  {
    v24 = *(_DWORD *)v29;
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 144);
  if ( !v23 )
    goto LABEL_11;
  if ( !pbOutput )
  {
    Property = v18(v15[2], 0, v33, v30, 0, cbOutput, pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6724;
      goto LABEL_16;
    }
    goto LABEL_32;
  }
  v8 = (void *)MSCryptAlloc(v24, v21);
  if ( v8 )
  {
    Property = ApplySignaturePadding(dwFlags, v34, v33, v30, (__int64)v8, *(int *)v29);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6752;
      goto LABEL_16;
    }
    Property = v18(v15[2], 0, (__int64)v8, *(unsigned int *)v29, pbOutput, cbOutput, pcbResult, 0);
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
  v9 = v32;
LABEL_36:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && (unsigned int)dword_1800C95C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800C95C0, 0x400000000000LL) )
  {
    v34 = v26;
    v37 = &v34;
    v38 = (unsigned int)((_DWORD)v26 + 7);
    v39 = &v33;
    v33 = 0x1000000;
    v41 = &v31;
    v40 = v38;
    v43 = &v30;
    v31 = v11;
    v42 = 4;
    v30 = (unsigned int)v26;
    v44 = 4;
    tlgCreate1Sz_wchar_t(v45, g_processImageName);
    tlgCreate1Sz_wchar_t(v46, v9);
    tlgWriteAgg((unsigned int)&dword_1800C95C0, (unsigned int)byte_1800C076B, 0, v27, (__int64)v36);
  }
  if ( v8 )
    MSCryptFree(v8);
  return v11;
}

```

## disassembly

```asm
0x180059d40  push    rbp
0x180059d42  push    rbx
0x180059d43  push    rsi
0x180059d44  push    rdi
0x180059d45  push    r12
0x180059d47  push    r13
0x180059d49  push    r14
0x180059d4b  push    r15
0x180059d4d  lea     rbp, [rsp-28h]
0x180059d52  sub     rsp, 128h
0x180059d59  mov     rax, cs:__security_cookie
0x180059d60  xor     rax, rsp
0x180059d63  mov     [rbp+60h+var_50], rax
0x180059d67  mov     r13, [rbp+60h+pbOutput]
0x180059d6e  xor     eax, eax
0x180059d70  mov     r12, [rbp+60h+pcbResult]
0x180059d77  mov     r14d, eax
0x180059d7a  mov     [rsp+160h+var_F8], eax
0x180059d7e  mov     edi, eax
0x180059d80  mov     dword ptr [rsp+160h+var_100], eax
0x180059d84  mov     r10, rdx
0x180059d87  mov     [rbp+60h+var_D8], eax
0x180059d8a  mov     rbx, rcx
0x180059d8d  mov     [rsp+160h+var_FC], r9d
0x180059d92  mov     [rsp+160h+var_E8], r8
0x180059d97  mov     [rbp+60h+var_E0], rdx
0x180059d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059da2  lea     rax, WPP_GLOBAL_Control
0x180059da9  mov     r15d, [rbp+60h+dwFlags]
0x180059db0  cmp     rcx, rax
0x180059db3  jz      short loc_180059DF3
0x180059db5  mov     eax, [rcx+2Ch]
0x180059db8  test    al, 4
0x180059dba  jz      short loc_180059DF3
0x180059dbc  mov     eax, [rbp+60h+cbOutput]
0x180059dc2  lea     edx, [rdi+26h]
0x180059dc5  mov     rcx, [rcx+18h]
0x180059dc9  mov     [rsp+160h+var_110], r15d
0x180059dce  mov     [rsp+160h+var_118], r12
0x180059dd3  mov     [rsp+160h+var_120], eax
0x180059dd7  mov     [rsp+160h+var_128], r13
0x180059ddc  mov     dword ptr [rsp+160h+var_130], r9d
0x180059de1  mov     r9, rbx
0x180059de4  mov     qword ptr [rsp+160h+var_138], r8
0x180059de9  mov     [rsp+160h+var_140], r10
0x180059dee  call    WPP_SF_qqqdqdqD
0x180059df3  test    r12, r12
0x180059df6  jnz     short loc_180059E20
0x180059df8  mov     ebx, 0C000000Dh
0x180059dfd  mov     r9d, 19F2h
0x180059e03  mov     ecx, 0C000000Dh
0x180059e08  lea     rdx, aStatus; "Status"
0x180059e0f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180059e16  call    DebugTraceError
0x180059e1b  jmp     loc_18005A045
0x180059e20  mov     rcx, rbx
0x180059e23  call    ValidateBaseKeyHandle
0x180059e28  mov     rsi, rax
0x180059e2b  test    rax, rax
0x180059e2e  jnz     short loc_180059E42
0x180059e30  mov     ebx, 0C0000008h
0x180059e35  mov     r9d, 19FAh
0x180059e3b  mov     ecx, 0C0000008h
0x180059e40  jmp     short loc_180059E08
0x180059e42  mov     rdi, [rax+8]
0x180059e46  lea     rax, [rdi+1BCh]
0x180059e4d  mov     [rsp+160h+var_F0], rax
0x180059e52  mov     eax, [rdi+24h]
0x180059e55  cmp     eax, 5
0x180059e58  jnz     short loc_180059EA8
0x180059e5a  mov     rdi, [rdi+68h]
0x180059e5e  mov     eax, [rbp+60h+dwFlags]
0x180059e64  mov     r9d, [rsp+160h+var_FC]
0x180059e69  mov     r8, [rsp+160h+var_E8]
0x180059e6e  mov     rdx, [rbp+60h+var_E0]
0x180059e72  mov     rcx, [rsi+10h]
0x180059e76  mov     dword ptr [rsp+160h+var_128], eax
0x180059e7a  mov     eax, [rbp+60h+cbOutput]
0x180059e80  mov     [rsp+160h+var_130], r12
0x180059e85  mov     [rsp+160h+var_138], eax
0x180059e89  mov     rax, rdi
0x180059e8c  mov     [rsp+160h+var_140], r13
0x180059e91  call    _guard_dispatch_icall
0x180059e96  mov     ebx, eax
0x180059e98  test    eax, eax
0x180059e9a  jns     loc_18005A019
0x180059ea0  mov     r9d, 1A7Fh
0x180059ea6  jmp     short loc_180059ED0
0x180059ea8  cmp     eax, 3
0x180059eab  jnz     loc_18005A01D
0x180059eb1  mov     ecx, [rdi+1B8h]
0x180059eb7  lea     r8, [rsp+160h+var_F8]
0x180059ebc  mov     edx, r15d
0x180059ebf  call    ShouldRouterPadSignature
0x180059ec4  mov     ebx, eax
0x180059ec6  test    eax, eax
0x180059ec8  jns     short loc_180059ED7
0x180059eca  mov     r9d, 1A16h
0x180059ed0  mov     ecx, eax
0x180059ed2  jmp     loc_18005A02D
0x180059ed7  mov     r15d, [rsp+160h+var_F8]
0x180059edc  test    r15d, r15d
0x180059edf  jz      short loc_180059F27
0x180059ee1  lea     rax, [rbp+60h+var_D8]
0x180059ee5  mov     [rsp+160h+var_138], r14d; dwFlags
0x180059eea  mov     r9d, 4; cbOutput
0x180059ef0  mov     [rsp+160h+var_140], rax; pcbResult
0x180059ef5  lea     r8, [rsp+160h+var_100]; pbOutput
0x180059efa  mov     rcx, rsi; hObject
0x180059efd  lea     rdx, aKeystrength; "KeyStrength"
0x180059f04  call    BCryptGetProperty
0x180059f09  mov     ebx, eax
0x180059f0b  test    eax, eax
0x180059f0d  jns     short loc_180059F17
0x180059f0f  mov     r9d, 1A25h
0x180059f15  jmp     short loc_180059ED0
0x180059f17  mov     eax, dword ptr [rsp+160h+var_100]
0x180059f1b  add     eax, 7
0x180059f1e  shr     eax, 3
0x180059f21  mov     dword ptr [rsp+160h+var_100], eax
0x180059f25  jmp     short loc_180059F2B
0x180059f27  mov     eax, dword ptr [rsp+160h+var_100]
0x180059f2b  mov     rdi, [rdi+90h]
0x180059f32  test    r15d, r15d
0x180059f35  jz      loc_180059E5E
0x180059f3b  test    r13, r13
0x180059f3e  jnz     short loc_180059F86
0x180059f40  mov     eax, [rbp+60h+cbOutput]
0x180059f46  xor     edx, edx
0x180059f48  mov     r9d, [rsp+160h+var_FC]
0x180059f4d  mov     r8, [rsp+160h+var_E8]
0x180059f52  mov     rcx, [rsi+10h]
0x180059f56  mov     dword ptr [rsp+160h+var_128], r14d
0x180059f5b  mov     [rsp+160h+var_130], r12
0x180059f60  mov     [rsp+160h+var_138], eax
0x180059f64  mov     rax, rdi
0x180059f67  mov     [rsp+160h+var_140], r14
0x180059f6c  call    _guard_dispatch_icall
0x180059f71  mov     ebx, eax
0x180059f73  test    eax, eax
0x180059f75  jns     loc_18005A019
0x180059f7b  mov     r9d, 1A44h
0x180059f81  jmp     loc_180059ED0
0x180059f86  mov     ecx, eax
0x180059f88  call    MSCryptAlloc
0x180059f8d  mov     r14, rax
0x180059f90  test    rax, rax
0x180059f93  jnz     short loc_180059F9F
0x180059f95  mov     ebx, 0C0000017h
0x180059f9a  jmp     loc_18005A040
0x180059f9f  mov     eax, dword ptr [rsp+160h+var_100]
0x180059fa3  mov     r9d, [rsp+160h+var_FC]
0x180059fa8  mov     r8, [rsp+160h+var_E8]
0x180059fad  mov     rdx, [rbp+60h+var_E0]
0x180059fb1  mov     ecx, [rbp+60h+dwFlags]
0x180059fb7  mov     [rsp+160h+var_138], eax
0x180059fbb  mov     [rsp+160h+var_140], r14
0x180059fc0  call    ApplySignaturePadding
0x180059fc5  mov     ebx, eax
0x180059fc7  test    eax, eax
0x180059fc9  jns     short loc_180059FD6
0x180059fcb  mov     r9d, 1A60h
0x180059fd1  jmp     loc_180059ED0
0x180059fd6  mov     eax, [rbp+60h+cbOutput]
0x180059fdc  mov     r8, r14
0x180059fdf  mov     r9d, dword ptr [rsp+160h+var_100]
0x180059fe4  xor     edx, edx
0x180059fe6  mov     rcx, [rsi+10h]
0x180059fea  mov     dword ptr [rsp+160h+var_128], 0
0x180059ff2  mov     [rsp+160h+var_130], r12
0x180059ff7  mov     [rsp+160h+var_138], eax
0x180059ffb  mov     rax, rdi
0x180059ffe  mov     [rsp+160h+var_140], r13
0x18005a003  call    _guard_dispatch_icall
0x18005a008  mov     ebx, eax
0x18005a00a  test    eax, eax
0x18005a00c  jns     short loc_18005A019
0x18005a00e  mov     r9d, 1A6Eh
0x18005a014  jmp     loc_180059ED0
0x18005a019  xor     ebx, ebx
0x18005a01b  jmp     short loc_18005A040
0x18005a01d  mov     ebx, 0C00000BBh
0x18005a022  mov     r9d, 1A31h
0x18005a028  mov     ecx, 0C00000BBh
0x18005a02d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a034  lea     rdx, aStatus; "Status"
0x18005a03b  call    DebugTraceError
0x18005a040  mov     rdi, [rsp+160h+var_F0]
0x18005a045  mov     eax, cs:g_TrustedEnvironment
0x18005a04b  test    eax, eax
0x18005a04d  jnz     short loc_18005A054
0x18005a04f  call    GetTrustedEnvironment
0x18005a054  mov     r10d, 1
0x18005a05a  test    r10b, al
0x18005a05d  jz      loc_18005A120
0x18005a063  mov     eax, cs:dword_1800C95C0
0x18005a069  cmp     eax, 5
0x18005a06c  jbe     loc_18005A120
0x18005a072  mov     rdx, 400000000000h
0x18005a07c  lea     rcx, dword_1800C95C0
0x18005a083  call    _tlgKeywordOn
0x18005a088  test    al, al
0x18005a08a  jz      loc_18005A120
0x18005a090  lea     rax, [rbp+60h+var_E0]
0x18005a094  mov     [rbp+60h+var_E0], r10
0x18005a098  mov     [rbp+60h+var_B0], rax
0x18005a09c  lea     r9d, [r10+7]
0x18005a0a0  lea     rax, [rsp+160h+var_E8]
0x18005a0a5  mov     [rbp+60h+var_A8], r9
0x18005a0a9  mov     [rbp+60h+var_A0], rax
0x18005a0ad  lea     rdx, g_processImageName; "UNKNOWN"
0x18005a0b4  lea     rax, [rsp+160h+var_F8]
0x18005a0b9  mov     [rsp+160h+var_E8], 1000000h
0x18005a0c2  mov     [rbp+60h+var_90], rax
0x18005a0c6  lea     rcx, [rbp+60h+var_70]
0x18005a0ca  lea     rax, [rsp+160h+var_FC]
0x18005a0cf  mov     [rbp+60h+var_98], r9
0x18005a0d3  mov     [rbp+60h+var_80], rax
0x18005a0d7  mov     [rsp+160h+var_F8], ebx
0x18005a0db  mov     [rbp+60h+var_88], 4
0x18005a0e3  mov     [rsp+160h+var_FC], r10d
0x18005a0e8  mov     [rbp+60h+var_78], 4
0x18005a0f0  call    _tlgCreate1Sz_wchar_t
0x18005a0f5  mov     rdx, rdi
0x18005a0f8  lea     rcx, [rbp+60h+var_60]
0x18005a0fc  call    _tlgCreate1Sz_wchar_t
0x18005a101  lea     r10, [rbp+60h+var_D0]
0x18005a105  xor     r8d, r8d
0x18005a108  lea     rdx, byte_1800C076B
0x18005a10f  mov     [rsp+160h+var_140], r10
0x18005a114  lea     rcx, dword_1800C95C0
0x18005a11b  call    _tlgWriteAgg
0x18005a120  test    r14, r14
0x18005a123  jz      short loc_18005A12D
0x18005a125  mov     rcx, r14; P
0x18005a128  call    MSCryptFree
0x18005a12d  mov     eax, ebx
0x18005a12f  mov     rcx, [rbp+60h+var_50]
0x18005a133  xor     rcx, rsp; StackCookie
0x18005a136  call    __security_check_cookie
0x18005a13b  add     rsp, 128h
0x18005a142  pop     r15
0x18005a144  pop     r14
0x18005a146  pop     r13
0x18005a148  pop     r12
0x18005a14a  pop     rdi
0x18005a14b  pop     rsi
0x18005a14c  pop     rbx
0x18005a14d  pop     rbp
0x18005a14e  retn
```
