# BCryptSignHash

- ea: `0x180063f10`
- end: `0x180064320`
- name: `BCryptSignHash`
- size: `1040`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, void *pPaddingInfo, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18002eb64`
- `0x18003f910`
- `0x18004c554`
- `0x18004f2e0`
- `0x180063f10`
- `0x180065dcc`
- `0x18006a044`
- `0x180072304`
- `0x1800a4260`
- `0x1800a4300`

## string_xrefs

- `0x180063fdf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800641fd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
    && (unsigned int)dword_1800D15C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800D15C0, 0x400000000000LL) )
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
    tlgWriteAgg((unsigned int)&dword_1800D15C0, (unsigned int)byte_1800C8FEB, 0, v27, (__int64)v36);
  }
  if ( v8 )
    MSCryptFree(v8);
  return v11;
}

```

## disassembly

```asm
0x180063f10  push    rbp
0x180063f12  push    rbx
0x180063f13  push    rsi
0x180063f14  push    rdi
0x180063f15  push    r12
0x180063f17  push    r13
0x180063f19  push    r14
0x180063f1b  push    r15
0x180063f1d  lea     rbp, [rsp-28h]
0x180063f22  sub     rsp, 128h
0x180063f29  mov     rax, cs:__security_cookie
0x180063f30  xor     rax, rsp
0x180063f33  mov     [rbp+60h+var_50], rax
0x180063f37  mov     r13, [rbp+60h+pbOutput]
0x180063f3e  xor     eax, eax
0x180063f40  mov     r12, [rbp+60h+pcbResult]
0x180063f47  mov     r14d, eax
0x180063f4a  mov     [rsp+160h+var_F8], eax
0x180063f4e  mov     edi, eax
0x180063f50  mov     dword ptr [rsp+160h+var_100], eax
0x180063f54  mov     r10, rdx
0x180063f57  mov     [rbp+60h+var_D8], eax
0x180063f5a  mov     rbx, rcx
0x180063f5d  mov     [rsp+160h+var_FC], r9d
0x180063f62  mov     [rsp+160h+var_E8], r8
0x180063f67  mov     [rbp+60h+var_E0], rdx
0x180063f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063f72  lea     rax, WPP_GLOBAL_Control
0x180063f79  mov     r15d, [rbp+60h+dwFlags]
0x180063f80  cmp     rcx, rax
0x180063f83  jz      short loc_180063FC3
0x180063f85  mov     eax, [rcx+2Ch]
0x180063f88  test    al, 4
0x180063f8a  jz      short loc_180063FC3
0x180063f8c  mov     eax, [rbp+60h+cbOutput]
0x180063f92  lea     edx, [rdi+26h]
0x180063f95  mov     rcx, [rcx+18h]
0x180063f99  mov     [rsp+160h+var_110], r15d
0x180063f9e  mov     [rsp+160h+var_118], r12
0x180063fa3  mov     [rsp+160h+var_120], eax
0x180063fa7  mov     [rsp+160h+var_128], r13
0x180063fac  mov     dword ptr [rsp+160h+var_130], r9d
0x180063fb1  mov     r9, rbx
0x180063fb4  mov     qword ptr [rsp+160h+var_138], r8
0x180063fb9  mov     [rsp+160h+var_140], r10
0x180063fbe  call    WPP_SF_qqqdqdqD
0x180063fc3  test    r12, r12
0x180063fc6  jnz     short loc_180063FF0
0x180063fc8  mov     ebx, 0C000000Dh
0x180063fcd  mov     r9d, 19F2h
0x180063fd3  mov     ecx, 0C000000Dh
0x180063fd8  lea     rdx, aStatus; "Status"
0x180063fdf  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063fe6  call    DebugTraceError
0x180063feb  jmp     loc_180064215
0x180063ff0  mov     rcx, rbx
0x180063ff3  call    ValidateBaseKeyHandle
0x180063ff8  mov     rsi, rax
0x180063ffb  test    rax, rax
0x180063ffe  jnz     short loc_180064012
0x180064000  mov     ebx, 0C0000008h
0x180064005  mov     r9d, 19FAh
0x18006400b  mov     ecx, 0C0000008h
0x180064010  jmp     short loc_180063FD8
0x180064012  mov     rdi, [rax+8]
0x180064016  lea     rax, [rdi+1BCh]
0x18006401d  mov     [rsp+160h+var_F0], rax
0x180064022  mov     eax, [rdi+24h]
0x180064025  cmp     eax, 5
0x180064028  jnz     short loc_180064078
0x18006402a  mov     rdi, [rdi+68h]
0x18006402e  mov     eax, [rbp+60h+dwFlags]
0x180064034  mov     r9d, [rsp+160h+var_FC]
0x180064039  mov     r8, [rsp+160h+var_E8]
0x18006403e  mov     rdx, [rbp+60h+var_E0]
0x180064042  mov     rcx, [rsi+10h]
0x180064046  mov     dword ptr [rsp+160h+var_128], eax
0x18006404a  mov     eax, [rbp+60h+cbOutput]
0x180064050  mov     [rsp+160h+var_130], r12
0x180064055  mov     [rsp+160h+var_138], eax
0x180064059  mov     rax, rdi
0x18006405c  mov     [rsp+160h+var_140], r13
0x180064061  call    _guard_dispatch_icall
0x180064066  mov     ebx, eax
0x180064068  test    eax, eax
0x18006406a  jns     loc_1800641E9
0x180064070  mov     r9d, 1A7Fh
0x180064076  jmp     short loc_1800640A0
0x180064078  cmp     eax, 3
0x18006407b  jnz     loc_1800641ED
0x180064081  mov     ecx, [rdi+1B8h]
0x180064087  lea     r8, [rsp+160h+var_F8]
0x18006408c  mov     edx, r15d
0x18006408f  call    ShouldRouterPadSignature
0x180064094  mov     ebx, eax
0x180064096  test    eax, eax
0x180064098  jns     short loc_1800640A7
0x18006409a  mov     r9d, 1A16h
0x1800640a0  mov     ecx, eax
0x1800640a2  jmp     loc_1800641FD
0x1800640a7  mov     r15d, [rsp+160h+var_F8]
0x1800640ac  test    r15d, r15d
0x1800640af  jz      short loc_1800640F7
0x1800640b1  lea     rax, [rbp+60h+var_D8]
0x1800640b5  mov     [rsp+160h+var_138], r14d; dwFlags
0x1800640ba  mov     r9d, 4; cbOutput
0x1800640c0  mov     [rsp+160h+var_140], rax; pcbResult
0x1800640c5  lea     r8, [rsp+160h+var_100]; pbOutput
0x1800640ca  mov     rcx, rsi; hObject
0x1800640cd  lea     rdx, aKeystrength; "KeyStrength"
0x1800640d4  call    BCryptGetProperty
0x1800640d9  mov     ebx, eax
0x1800640db  test    eax, eax
0x1800640dd  jns     short loc_1800640E7
0x1800640df  mov     r9d, 1A25h
0x1800640e5  jmp     short loc_1800640A0
0x1800640e7  mov     eax, dword ptr [rsp+160h+var_100]
0x1800640eb  add     eax, 7
0x1800640ee  shr     eax, 3
0x1800640f1  mov     dword ptr [rsp+160h+var_100], eax
0x1800640f5  jmp     short loc_1800640FB
0x1800640f7  mov     eax, dword ptr [rsp+160h+var_100]
0x1800640fb  mov     rdi, [rdi+90h]
0x180064102  test    r15d, r15d
0x180064105  jz      loc_18006402E
0x18006410b  test    r13, r13
0x18006410e  jnz     short loc_180064156
0x180064110  mov     eax, [rbp+60h+cbOutput]
0x180064116  xor     edx, edx
0x180064118  mov     r9d, [rsp+160h+var_FC]
0x18006411d  mov     r8, [rsp+160h+var_E8]
0x180064122  mov     rcx, [rsi+10h]
0x180064126  mov     dword ptr [rsp+160h+var_128], r14d
0x18006412b  mov     [rsp+160h+var_130], r12
0x180064130  mov     [rsp+160h+var_138], eax
0x180064134  mov     rax, rdi
0x180064137  mov     [rsp+160h+var_140], r14
0x18006413c  call    _guard_dispatch_icall
0x180064141  mov     ebx, eax
0x180064143  test    eax, eax
0x180064145  jns     loc_1800641E9
0x18006414b  mov     r9d, 1A44h
0x180064151  jmp     loc_1800640A0
0x180064156  mov     ecx, eax
0x180064158  call    MSCryptAlloc
0x18006415d  mov     r14, rax
0x180064160  test    rax, rax
0x180064163  jnz     short loc_18006416F
0x180064165  mov     ebx, 0C0000017h
0x18006416a  jmp     loc_180064210
0x18006416f  mov     eax, dword ptr [rsp+160h+var_100]
0x180064173  mov     r9d, [rsp+160h+var_FC]
0x180064178  mov     r8, [rsp+160h+var_E8]
0x18006417d  mov     rdx, [rbp+60h+var_E0]
0x180064181  mov     ecx, [rbp+60h+dwFlags]
0x180064187  mov     [rsp+160h+var_138], eax
0x18006418b  mov     [rsp+160h+var_140], r14
0x180064190  call    ApplySignaturePadding
0x180064195  mov     ebx, eax
0x180064197  test    eax, eax
0x180064199  jns     short loc_1800641A6
0x18006419b  mov     r9d, 1A60h
0x1800641a1  jmp     loc_1800640A0
0x1800641a6  mov     eax, [rbp+60h+cbOutput]
0x1800641ac  mov     r8, r14
0x1800641af  mov     r9d, dword ptr [rsp+160h+var_100]
0x1800641b4  xor     edx, edx
0x1800641b6  mov     rcx, [rsi+10h]
0x1800641ba  mov     dword ptr [rsp+160h+var_128], 0
0x1800641c2  mov     [rsp+160h+var_130], r12
0x1800641c7  mov     [rsp+160h+var_138], eax
0x1800641cb  mov     rax, rdi
0x1800641ce  mov     [rsp+160h+var_140], r13
0x1800641d3  call    _guard_dispatch_icall
0x1800641d8  mov     ebx, eax
0x1800641da  test    eax, eax
0x1800641dc  jns     short loc_1800641E9
0x1800641de  mov     r9d, 1A6Eh
0x1800641e4  jmp     loc_1800640A0
0x1800641e9  xor     ebx, ebx
0x1800641eb  jmp     short loc_180064210
0x1800641ed  mov     ebx, 0C00000BBh
0x1800641f2  mov     r9d, 1A31h
0x1800641f8  mov     ecx, 0C00000BBh
0x1800641fd  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064204  lea     rdx, aStatus; "Status"
0x18006420b  call    DebugTraceError
0x180064210  mov     rdi, [rsp+160h+var_F0]
0x180064215  mov     eax, cs:g_TrustedEnvironment
0x18006421b  test    eax, eax
0x18006421d  jnz     short loc_180064224
0x18006421f  call    GetTrustedEnvironment
0x180064224  mov     r10d, 1
0x18006422a  test    r10b, al
0x18006422d  jz      loc_1800642F0
0x180064233  mov     eax, cs:dword_1800D15C0
0x180064239  cmp     eax, 5
0x18006423c  jbe     loc_1800642F0
0x180064242  mov     rdx, 400000000000h
0x18006424c  lea     rcx, dword_1800D15C0
0x180064253  call    _tlgKeywordOn
0x180064258  test    al, al
0x18006425a  jz      loc_1800642F0
0x180064260  lea     rax, [rbp+60h+var_E0]
0x180064264  mov     [rbp+60h+var_E0], r10
0x180064268  mov     [rbp+60h+var_B0], rax
0x18006426c  lea     r9d, [r10+7]
0x180064270  lea     rax, [rsp+160h+var_E8]
0x180064275  mov     [rbp+60h+var_A8], r9
0x180064279  mov     [rbp+60h+var_A0], rax
0x18006427d  lea     rdx, g_processImageName; "UNKNOWN"
0x180064284  lea     rax, [rsp+160h+var_F8]
0x180064289  mov     [rsp+160h+var_E8], 1000000h
0x180064292  mov     [rbp+60h+var_90], rax
0x180064296  lea     rcx, [rbp+60h+var_70]
0x18006429a  lea     rax, [rsp+160h+var_FC]
0x18006429f  mov     [rbp+60h+var_98], r9
0x1800642a3  mov     [rbp+60h+var_80], rax
0x1800642a7  mov     [rsp+160h+var_F8], ebx
0x1800642ab  mov     [rbp+60h+var_88], 4
0x1800642b3  mov     [rsp+160h+var_FC], r10d
0x1800642b8  mov     [rbp+60h+var_78], 4
0x1800642c0  call    _tlgCreate1Sz_wchar_t
0x1800642c5  mov     rdx, rdi
0x1800642c8  lea     rcx, [rbp+60h+var_60]
0x1800642cc  call    _tlgCreate1Sz_wchar_t
0x1800642d1  lea     r10, [rbp+60h+var_D0]
0x1800642d5  xor     r8d, r8d
0x1800642d8  lea     rdx, byte_1800C8FEB
0x1800642df  mov     [rsp+160h+var_140], r10
0x1800642e4  lea     rcx, dword_1800D15C0
0x1800642eb  call    _tlgWriteAgg
0x1800642f0  test    r14, r14
0x1800642f3  jz      short loc_1800642FD
0x1800642f5  mov     rcx, r14; P
0x1800642f8  call    MSCryptFree
0x1800642fd  mov     eax, ebx
0x1800642ff  mov     rcx, [rbp+60h+var_50]
0x180064303  xor     rcx, rsp; StackCookie
0x180064306  call    __security_check_cookie
0x18006430b  add     rsp, 128h
0x180064312  pop     r15
0x180064314  pop     r14
0x180064316  pop     r13
0x180064318  pop     r12
0x18006431a  pop     rdi
0x18006431b  pop     rsi
0x18006431c  pop     rbx
0x18006431d  pop     rbp
0x18006431e  retn
```
