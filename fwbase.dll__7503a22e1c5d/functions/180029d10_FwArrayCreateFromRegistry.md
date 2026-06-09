# FwArrayCreateFromRegistry

- ea: `0x180029d10`
- end: `0x180029f26`
- name: `FwArrayCreateFromRegistry`
- size: `534`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001720`
- `0x1800028e0`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x180006ac0`
- `0x18000c060`
- `0x18001188c`
- `0x180012960`
- `0x18001e1d0`
- `0x18001f3a0`
- `0x180029d10`
- `0x18002f43c`
- `0x180030010`

## string_xrefs

- `0x180029db4`: `FwArrayCreateFromRegistry`
- `0x180029ded`: `FwArrayCreateFromRegistry`

## pseudocode

```c
__int64 __fastcall FwArrayCreateFromRegistry(
        HKEY hKey,
        LPCWSTR lpSubKey,
        __int64 a3,
        __int64 (__fastcall *a4)(__int64, HKEY, __int64, __int64, int *),
        __int64 a5,
        __int64 a6,
        _OWORD *a7)
{
  DWORD v7; // r14d
  DWORD v11; // esi
  int v12; // eax
  HKEY v13; // r12
  int v14; // ebx
  __int64 v15; // rdx
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r15
  __int64 v19; // rax
  __int64 v21; // [rsp+30h] [rbp-61h] BYREF
  __int128 v22; // [rsp+38h] [rbp-59h] BYREF
  __int64 v23; // [rsp+48h] [rbp-49h]
  HKEY hKeya; // [rsp+50h] [rbp-41h] BYREF
  __int64 v25; // [rsp+58h] [rbp-39h] BYREF
  __int64 v26; // [rsp+60h] [rbp-31h]
  __int64 (__fastcall *v27)(__int64, HKEY, __int64, __int64, int *); // [rsp+68h] [rbp-29h]
  _OWORD *v28; // [rsp+70h] [rbp-21h]
  DWORD cValues; // [rsp+78h] [rbp-19h] BYREF
  int v30; // [rsp+7Ch] [rbp-15h] BYREF

  v7 = 0;
  v27 = a4;
  v26 = a6;
  v28 = a7;
  v11 = 0;
  hKeya = 0;
  LODWORD(v21) = 0;
  cValues = 0;
  v25 = 0;
  v22 = 0u;
  v23 = 0;
  v30 = 0;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(hKey);
  *a7 = 0;
  v12 = FwRegOpenKey(hKey, lpSubKey, 1u, &hKeya, (int *)&v21);
  v13 = hKeya;
  v14 = v12;
  if ( v12 >= 0 )
  {
    if ( (_DWORD)v21 )
    {
      v12 = FwRegQueryNumValues(hKeya, &cValues);
      v14 = v12;
      if ( v12 < 0 )
        goto LABEL_4;
      v16 = cValues;
    }
    else
    {
      v16 = 0;
      cValues = 0;
    }
    if ( v16 )
    {
      v12 = FwSizeTMultiply(v16, a3, &v25);
      v14 = v12;
      if ( v12 < 0 )
        goto LABEL_4;
      *((_QWORD *)&v22 + 1) = FwAlloc(v25, v17);
      v18 = *((_QWORD *)&v22 + 1);
      if ( !*((_QWORD *)&v22 + 1) )
      {
        v14 = FwReportErrorAsWinError("FwArrayCreateFromRegistry", "FwAlloc", 8);
        goto LABEL_24;
      }
      while ( v11 < cValues )
      {
        v12 = FwRegEnumValueName(v13, v7);
        v14 = v12;
        if ( v12 < 0 )
          goto LABEL_4;
        if ( !(_DWORD)v21 )
          break;
        v19 = FwArrayEnd(a3, &v22);
        v14 = v27(v26, v13, v23, v19, &v30);
        FwFree(v23);
        if ( v14 < 0 )
        {
          v15 = (unsigned int)v14;
          goto LABEL_5;
        }
        ++v7;
        if ( v30 )
          LODWORD(v22) = ++v11;
      }
      if ( !v11 )
      {
        FwFree(v18);
        *((_QWORD *)&v22 + 1) = 0;
      }
    }
    *v28 = v22;
LABEL_24:
    if ( v14 >= 0 )
      goto LABEL_26;
    goto LABEL_25;
  }
LABEL_4:
  v15 = (unsigned int)v12;
LABEL_5:
  FwReportReturnError("FwArrayCreateFromRegistry", v15);
LABEL_25:
  FwArrayDestroy(a3, a5, &v22);
LABEL_26:
  FwRegCloseKey(v13);
  if ( v14 < 0 )
    return (unsigned int)FwReportReturnError("FwArrayCreateFromRegistry", (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180029d10  push    rbp
0x180029d12  push    rbx
0x180029d13  push    rsi
0x180029d14  push    rdi
0x180029d15  push    r12
0x180029d17  push    r13
0x180029d19  push    r14
0x180029d1b  push    r15
0x180029d1d  lea     rbp, [rsp-7]
0x180029d22  sub     rsp, 98h
0x180029d29  mov     rax, cs:__security_cookie
0x180029d30  xor     rax, rsp
0x180029d33  mov     [rbp+3Fh+var_50], rax
0x180029d37  mov     rax, [rbp+3Fh+arg_28]
0x180029d3b  xor     r14d, r14d
0x180029d3e  mov     r12, [rbp+3Fh+arg_30]
0x180029d42  mov     r13, r8
0x180029d45  mov     [rbp+3Fh+var_68], r9
0x180029d49  mov     rdi, rdx
0x180029d4c  mov     [rbp+3Fh+var_70], rax
0x180029d50  mov     rbx, rcx
0x180029d53  mov     [rbp+3Fh+var_60], r12
0x180029d57  mov     esi, r14d
0x180029d5a  mov     [rbp+3Fh+hKey], r14
0x180029d5e  mov     dword ptr [rbp+3Fh+var_A0], r14d
0x180029d62  mov     [rbp+3Fh+cValues], r14d
0x180029d66  mov     [rbp+3Fh+var_78], r14
0x180029d6a  mov     qword ptr [rbp+3Fh+var_98], r14
0x180029d6e  mov     qword ptr [rbp+3Fh+var_98+8], r14
0x180029d72  mov     [rbp+3Fh+var_88], r14
0x180029d76  mov     [rbp+3Fh+var_54], r14d
0x180029d7a  test    r8, r8
0x180029d7d  jnz     short loc_180029D84
0x180029d7f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x180029d84  xorps   xmm0, xmm0
0x180029d87  lea     rax, [rbp+3Fh+var_A0]
0x180029d8b  lea     r9, [rbp+3Fh+hKey]
0x180029d8f  mov     [rsp+0D0h+var_B0], rax; __int64
0x180029d94  mov     r8d, 1; samDesired
0x180029d9a  mov     rdx, rdi; lpSubKey
0x180029d9d  mov     rcx, rbx; hKey
0x180029da0  movups  xmmword ptr [r12], xmm0
0x180029da5  call    FwRegOpenKey
0x180029daa  mov     r12, [rbp+3Fh+hKey]
0x180029dae  mov     ebx, eax
0x180029db0  test    eax, eax
0x180029db2  jns     short loc_180029DCA
0x180029db4  lea     rdi, aFwarraycreatef_0; "FwArrayCreateFromRegistry"
0x180029dbb  mov     edx, eax
0x180029dbd  mov     rcx, rdi
0x180029dc0  call    FwReportReturnError
0x180029dc5  jmp     loc_180029EDC
0x180029dca  cmp     dword ptr [rbp+3Fh+var_A0], r14d
0x180029dce  jz      short loc_180029DE7
0x180029dd0  lea     rdx, [rbp+3Fh+cValues]; lpcValues
0x180029dd4  mov     rcx, r12; hKey
0x180029dd7  call    FwRegQueryNumValues
0x180029ddc  mov     ebx, eax
0x180029dde  test    eax, eax
0x180029de0  js      short loc_180029DB4
0x180029de2  mov     eax, [rbp+3Fh+cValues]
0x180029de5  jmp     short loc_180029DED
0x180029de7  mov     eax, r14d
0x180029dea  mov     [rbp+3Fh+cValues], eax
0x180029ded  lea     rdi, aFwarraycreatef_0; "FwArrayCreateFromRegistry"
0x180029df4  test    eax, eax
0x180029df6  jz      loc_180029ECC
0x180029dfc  mov     ecx, eax
0x180029dfe  lea     r8, [rbp+3Fh+var_78]
0x180029e02  mov     rdx, r13
0x180029e05  call    FwSizeTMultiply
0x180029e0a  mov     ebx, eax
0x180029e0c  test    eax, eax
0x180029e0e  js      short loc_180029DBB
0x180029e10  mov     rcx, [rbp+3Fh+var_78]
0x180029e14  call    FwAlloc
0x180029e19  mov     qword ptr [rbp+3Fh+var_98+8], rax
0x180029e1d  mov     r15, rax
0x180029e20  test    rax, rax
0x180029e23  jnz     short loc_180029E3F
0x180029e25  lea     r8d, [rax+8]
0x180029e29  mov     rcx, rdi
0x180029e2c  lea     rdx, aFwalloc_0; "FwAlloc"
0x180029e33  call    FwReportErrorAsWinError
0x180029e38  mov     ebx, eax
0x180029e3a  jmp     loc_180029ED8
0x180029e3f  cmp     esi, [rbp+3Fh+cValues]
0x180029e42  jnb     short loc_180029EB9
0x180029e44  lea     r9, [rbp+3Fh+var_A0]
0x180029e48  mov     edx, r14d; dwIndex
0x180029e4b  lea     r8, [rbp+3Fh+var_88]
0x180029e4f  mov     rcx, r12; hKey
0x180029e52  call    FwRegEnumValueName
0x180029e57  mov     ebx, eax
0x180029e59  test    eax, eax
0x180029e5b  js      loc_180029DBB
0x180029e61  cmp     dword ptr [rbp+3Fh+var_A0], 0
0x180029e65  jz      short loc_180029EB9
0x180029e67  lea     rdx, [rbp+3Fh+var_98]
0x180029e6b  mov     rcx, r13
0x180029e6e  call    FwArrayEnd
0x180029e73  mov     r8, [rbp+3Fh+var_88]
0x180029e77  lea     rcx, [rbp+3Fh+var_54]
0x180029e7b  mov     [rsp+0D0h+var_B0], rcx
0x180029e80  mov     r9, rax
0x180029e83  mov     rcx, [rbp+3Fh+var_70]
0x180029e87  mov     rdx, r12
0x180029e8a  mov     rax, [rbp+3Fh+var_68]
0x180029e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e93  mov     rcx, [rbp+3Fh+var_88]
0x180029e97  mov     ebx, eax
0x180029e99  call    FwFree
0x180029e9e  test    ebx, ebx
0x180029ea0  js      short loc_180029EB2
0x180029ea2  inc     r14d
0x180029ea5  cmp     [rbp+3Fh+var_54], 0
0x180029ea9  jz      short loc_180029E3F
0x180029eab  inc     esi
0x180029ead  mov     dword ptr [rbp+3Fh+var_98], esi
0x180029eb0  jmp     short loc_180029E3F
0x180029eb2  mov     edx, ebx
0x180029eb4  jmp     loc_180029DBD
0x180029eb9  xor     r14d, r14d
0x180029ebc  test    esi, esi
0x180029ebe  jnz     short loc_180029ECC
0x180029ec0  mov     rcx, r15
0x180029ec3  call    FwFree
0x180029ec8  mov     qword ptr [rbp+3Fh+var_98+8], r14
0x180029ecc  mov     rax, [rbp+3Fh+var_60]
0x180029ed0  movups  xmm0, [rbp+3Fh+var_98]
0x180029ed4  movdqu  xmmword ptr [rax], xmm0
0x180029ed8  test    ebx, ebx
0x180029eda  jns     short loc_180029EEC
0x180029edc  mov     rdx, [rbp+3Fh+arg_20]
0x180029ee0  lea     r8, [rbp+3Fh+var_98]
0x180029ee4  mov     rcx, r13
0x180029ee7  call    FwArrayDestroy
0x180029eec  mov     rcx, r12
0x180029eef  call    FwRegCloseKey
0x180029ef4  test    ebx, ebx
0x180029ef6  jns     short loc_180029F04
0x180029ef8  mov     edx, ebx
0x180029efa  mov     rcx, rdi
0x180029efd  call    FwReportReturnError
0x180029f02  mov     ebx, eax
0x180029f04  mov     eax, ebx
0x180029f06  mov     rcx, [rbp+3Fh+var_50]
0x180029f0a  xor     rcx, rsp; StackCookie
0x180029f0d  call    __security_check_cookie
0x180029f12  add     rsp, 98h
0x180029f19  pop     r15
0x180029f1b  pop     r14
0x180029f1d  pop     r13
0x180029f1f  pop     r12
0x180029f21  pop     rdi
0x180029f22  pop     rsi
0x180029f23  pop     rbx
0x180029f24  pop     rbp
0x180029f25  retn
```
