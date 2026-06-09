# SslpExportHybridKey

- ea: `0x180022e04`
- end: `0x180022fa2`
- name: `SslpExportHybridKey`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e320`

## callees

- `0x180003ef0`
- `0x18000b654`
- `0x180014024`
- `0x1800185e0`
- `0x1800229a4`
- `0x180022e04`
- `0x180023a54`

## string_xrefs

- `0x180022e4e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022eeb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022f64`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpExportHybridKey(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4, unsigned int *a5, int a6)
{
  __int64 v6; // rsi
  __int64 v7; // rdi
  const wchar_t *v10; // r10
  __int64 v11; // r14
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  int v15; // edx
  int v16; // eax
  bool v17; // zf
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rcx
  int v22[2]; // [rsp+40h] [rbp-48h] BYREF
  int v23[2]; // [rsp+48h] [rbp-40h] BYREF

  v6 = 0;
  v7 = 0;
  *(_QWORD *)v22 = 0;
  *(_QWORD *)v23 = 0;
  v11 = SslpValidateHybridKeyHandle(a1);
  if ( !v11 )
  {
    v12 = -2146893786;
    v13 = 848;
    v14 = 2148073510LL;
LABEL_3:
    DebugTraceError(v14, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v13);
    return v12;
  }
  if ( !v10 || !a5 )
  {
    v12 = -2146893785;
    v19 = 856;
    v20 = 2148073511LL;
LABEL_16:
    DebugTraceError(v20, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v19);
    goto LABEL_17;
  }
  if ( wcscmp(v10, L"TLS_HYBRID_KEY") )
  {
    v12 = -2146893783;
    v13 = 863;
    v14 = 2148073513LL;
    goto LABEL_3;
  }
  if ( !a3 )
    LOBYTE(v7) = a4 == 0;
  LOBYTE(v15) = v7;
  v16 = SslpExportHybridConstituentKeys(v11, v15, a4, (unsigned int)v22, (__int64)v23, (__int64)a5, a6);
  v12 = v16;
  if ( v16 >= 0 )
  {
    v6 = *(_QWORD *)v22;
    v17 = (_BYTE)v7 == 0;
    v7 = *(_QWORD *)v23;
    if ( !v17 )
      goto LABEL_17;
    v18 = SslpConstructHybridKeyBlob(
            v11,
            *(__int64 *)v22,
            *(_DWORD *)(v11 + 24),
            *(__int64 *)v23,
            *(_DWORD *)(v11 + 40),
            a3,
            a4,
            a5);
    v12 = v18;
    if ( v18 >= 0 )
      goto LABEL_17;
    v19 = 903;
    v20 = (unsigned int)v18;
    goto LABEL_16;
  }
  DebugTraceError((unsigned int)v16, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 883);
  v6 = *(_QWORD *)v22;
  v7 = *(_QWORD *)v23;
LABEL_17:
  if ( v6 )
    MSCryptFree(v6);
  if ( v7 )
    MSCryptFree(v7);
  return v12;
}

```

## disassembly

```asm
0x180022e04  push    rbx
0x180022e06  push    rbp
0x180022e07  push    rsi
0x180022e08  push    rdi
0x180022e09  push    r12
0x180022e0b  push    r14
0x180022e0d  push    r15
0x180022e0f  sub     rsp, 50h
0x180022e13  xor     esi, esi
0x180022e15  xor     edi, edi
0x180022e17  mov     qword ptr [rsp+88h+var_48], rsi
0x180022e1c  mov     r15d, r9d
0x180022e1f  mov     qword ptr [rsp+88h+var_40], rdi
0x180022e24  mov     r12, r8
0x180022e27  mov     r10, rdx
0x180022e2a  call    SslpValidateHybridKeyHandle
0x180022e2f  mov     r14, rax
0x180022e32  test    rax, rax
0x180022e35  jnz     short loc_180022E5F
0x180022e37  mov     ebx, 80090026h
0x180022e3c  mov     r9d, 350h
0x180022e42  mov     ecx, 80090026h
0x180022e47  lea     rdx, aStatus_0; "status"
0x180022e4e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022e55  call    DebugTraceError
0x180022e5a  jmp     loc_180022F91
0x180022e5f  test    r10, r10
0x180022e62  jz      loc_180022F54
0x180022e68  mov     rbp, [rsp+88h+arg_20]
0x180022e70  test    rbp, rbp
0x180022e73  jz      loc_180022F54
0x180022e79  lea     rdx, aTlsHybridKey; "TLS_HYBRID_KEY"
0x180022e80  mov     rcx, r10; String1
0x180022e83  call    wcscmp
0x180022e88  test    eax, eax
0x180022e8a  jz      short loc_180022E9E
0x180022e8c  mov     ebx, 80090029h
0x180022e91  mov     r9d, 35Fh
0x180022e97  mov     ecx, 80090029h
0x180022e9c  jmp     short loc_180022E47
0x180022e9e  test    r12, r12
0x180022ea1  jnz     short loc_180022EB2
0x180022ea3  test    r15d, r15d
0x180022ea6  movzx   edi, dil
0x180022eaa  lea     eax, [r12+1]
0x180022eaf  cmovz   edi, eax
0x180022eb2  mov     eax, [rsp+88h+arg_28]
0x180022eb9  lea     r9, [rsp+88h+var_48]
0x180022ebe  mov     [rsp+88h+var_58], eax
0x180022ec2  mov     r8d, r15d
0x180022ec5  lea     rax, [rsp+88h+var_40]
0x180022eca  mov     [rsp+88h+var_60], rbp
0x180022ecf  mov     dl, dil
0x180022ed2  mov     qword ptr [rsp+88h+var_68], rax
0x180022ed7  mov     rcx, r14
0x180022eda  call    SslpExportHybridConstituentKeys
0x180022edf  mov     ebx, eax
0x180022ee1  test    eax, eax
0x180022ee3  jns     short loc_180022F0C
0x180022ee5  mov     r9d, 373h
0x180022eeb  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022ef2  lea     rdx, aStatus_0; "status"
0x180022ef9  mov     ecx, eax
0x180022efb  call    DebugTraceError
0x180022f00  mov     rsi, qword ptr [rsp+88h+var_48]
0x180022f05  mov     rdi, qword ptr [rsp+88h+var_40]
0x180022f0a  jmp     short loc_180022F77
0x180022f0c  mov     rsi, qword ptr [rsp+88h+var_48]
0x180022f11  test    dil, dil
0x180022f14  mov     rdi, qword ptr [rsp+88h+var_40]
0x180022f19  jnz     short loc_180022F77
0x180022f1b  mov     eax, [r14+28h]
0x180022f1f  mov     r9, rdi; int
0x180022f22  mov     r8d, [r14+18h]; int
0x180022f26  mov     rdx, rsi; int
0x180022f29  mov     [rsp+88h+var_50], rbp; __int64
0x180022f2e  mov     rcx, r14; int
0x180022f31  mov     [rsp+88h+var_58], r15d; int
0x180022f36  mov     [rsp+88h+var_60], r12; void *
0x180022f3b  mov     [rsp+88h+var_68], eax; int
0x180022f3f  call    SslpConstructHybridKeyBlob
0x180022f44  mov     ebx, eax
0x180022f46  test    eax, eax
0x180022f48  jns     short loc_180022F77
0x180022f4a  mov     r9d, 387h
0x180022f50  mov     ecx, eax
0x180022f52  jmp     short loc_180022F64
0x180022f54  mov     ebx, 80090027h
0x180022f59  mov     r9d, 358h
0x180022f5f  mov     ecx, 80090027h
0x180022f64  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022f6b  lea     rdx, aStatus_0; "status"
0x180022f72  call    DebugTraceError
0x180022f77  test    rsi, rsi
0x180022f7a  jz      short loc_180022F84
0x180022f7c  mov     rcx, rsi
0x180022f7f  call    MSCryptFree
0x180022f84  test    rdi, rdi
0x180022f87  jz      short loc_180022F91
0x180022f89  mov     rcx, rdi
0x180022f8c  call    MSCryptFree
0x180022f91  mov     eax, ebx
0x180022f93  add     rsp, 50h
0x180022f97  pop     r15
0x180022f99  pop     r14
0x180022f9b  pop     r12
0x180022f9d  pop     rdi
0x180022f9e  pop     rsi
0x180022f9f  pop     rbp
0x180022fa0  pop     rbx
0x180022fa1  retn
```
