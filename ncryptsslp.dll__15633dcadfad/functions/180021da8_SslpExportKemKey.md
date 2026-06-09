# SslpExportKemKey

- ea: `0x180021da8`
- end: `0x180021ef3`
- name: `SslpExportKemKey`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e320`
- `0x180014024`

## callees

- `0x18000b654`
- `0x1800185e0`
- `0x180021cbc`
- `0x180021da8`
- `0x180023a78`

## import_xrefs

- `ncrypt!NCryptExportKey` at `0x180021e43`
- `ncrypt!NCryptExportKey` at `0x180021e43`

## string_xrefs

- `0x180021dcf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x180021e55`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x180021ea6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x180021ecb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpExportKemKey(_DWORD *a1, const WCHAR *a2, BYTE *a3, DWORD a4, DWORD *pcbResult, DWORD dwFlags)
{
  _DWORD *v9; // rsi
  SECURITY_STATUS v11; // ebx
  __int64 v12; // r9

  v9 = SslpValidateKemKeyHandle(a1);
  if ( !v9 )
  {
    DebugTraceError(2148073510LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", 237);
    return 2148073510LL;
  }
  if ( a2 && pcbResult )
  {
    if ( !wcscmp(a2, L"MLKEMPUBLICBLOB") )
    {
      v11 = NCryptExportKey(*((_QWORD *)v9 + 3), 0, a2, 0, a3, a4, pcbResult, dwFlags);
      if ( v11 >= 0 )
        return (unsigned int)v11;
      v12 = 261;
LABEL_8:
      DebugTraceError((unsigned int)v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v12);
      return (unsigned int)v11;
    }
    if ( !wcscmp(a2, L"TLS_KEM_CIPHERTEXT") )
    {
      v11 = SslpExportKemCipherText(v9, a3, a4, pcbResult);
      if ( v11 >= 0 )
        return (unsigned int)v11;
      v12 = 274;
      goto LABEL_8;
    }
    DebugTraceError(2148073513LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", 281);
    return 2148073513LL;
  }
  else
  {
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", 244);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x180021da8  push    rbx
0x180021daa  push    rbp
0x180021dab  push    rsi
0x180021dac  push    rdi
0x180021dad  push    r14
0x180021daf  sub     rsp, 40h
0x180021db3  mov     ebp, r9d
0x180021db6  mov     r14, r8
0x180021db9  mov     rbx, rdx
0x180021dbc  call    SslpValidateKemKeyHandle
0x180021dc1  mov     rsi, rax
0x180021dc4  test    rax, rax
0x180021dc7  jnz     short loc_180021DF1
0x180021dc9  mov     r9d, 0EDh
0x180021dcf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021dd6  lea     rdx, aStatus_0; "status"
0x180021ddd  mov     ecx, 80090026h
0x180021de2  call    DebugTraceError
0x180021de7  mov     eax, 80090026h
0x180021dec  jmp     loc_180021EE8
0x180021df1  test    rbx, rbx
0x180021df4  jz      loc_180021EC5
0x180021dfa  mov     rdi, [rsp+68h+arg_20]
0x180021e02  test    rdi, rdi
0x180021e05  jz      loc_180021EC5
0x180021e0b  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180021e12  mov     rcx, rbx; String1
0x180021e15  call    wcscmp
0x180021e1a  test    eax, eax
0x180021e1c  jnz     short loc_180021E6E
0x180021e1e  mov     eax, [rsp+68h+arg_28]
0x180021e25  xor     r9d, r9d; pParameterList
0x180021e28  mov     rcx, [rsi+18h]; hKey
0x180021e2c  mov     r8, rbx; pszBlobType
0x180021e2f  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180021e33  xor     edx, edx; hExportKey
0x180021e35  mov     [rsp+68h+pcbResult], rdi; pcbResult
0x180021e3a  mov     [rsp+68h+cbOutput], ebp; cbOutput
0x180021e3e  mov     [rsp+68h+pbOutput], r14; pbOutput
0x180021e43  call    cs:__imp_NCryptExportKey
0x180021e49  mov     ebx, eax
0x180021e4b  test    eax, eax
0x180021e4d  jns     short loc_180021E6A
0x180021e4f  mov     r9d, 105h
0x180021e55  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021e5c  mov     ecx, ebx
0x180021e5e  lea     rdx, aStatus_0; "status"
0x180021e65  call    DebugTraceError
0x180021e6a  mov     eax, ebx
0x180021e6c  jmp     short loc_180021EE8
0x180021e6e  lea     rdx, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x180021e75  mov     rcx, rbx; String1
0x180021e78  call    wcscmp
0x180021e7d  test    eax, eax
0x180021e7f  jnz     short loc_180021EA0
0x180021e81  mov     r9, rdi
0x180021e84  mov     r8d, ebp
0x180021e87  mov     rdx, r14
0x180021e8a  mov     rcx, rsi
0x180021e8d  call    SslpExportKemCipherText
0x180021e92  mov     ebx, eax
0x180021e94  test    eax, eax
0x180021e96  jns     short loc_180021E6A
0x180021e98  mov     r9d, 112h
0x180021e9e  jmp     short loc_180021E55
0x180021ea0  mov     r9d, 119h
0x180021ea6  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021ead  lea     rdx, aStatus_0; "status"
0x180021eb4  mov     ecx, 80090029h
0x180021eb9  call    DebugTraceError
0x180021ebe  mov     eax, 80090029h
0x180021ec3  jmp     short loc_180021EE8
0x180021ec5  mov     r9d, 0F4h
0x180021ecb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021ed2  lea     rdx, aStatus_0; "status"
0x180021ed9  mov     ecx, 80090027h
0x180021ede  call    DebugTraceError
0x180021ee3  mov     eax, 80090027h
0x180021ee8  add     rsp, 40h
0x180021eec  pop     r14
0x180021eee  pop     rdi
0x180021eef  pop     rsi
0x180021ef0  pop     rbp
0x180021ef1  pop     rbx
0x180021ef2  retn
```
