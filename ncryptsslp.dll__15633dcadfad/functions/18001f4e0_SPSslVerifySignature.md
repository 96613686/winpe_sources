# SPSslVerifySignature

- ea: `0x18001f4e0`
- end: `0x18001f593`
- name: `SPSslVerifySignature`
- size: `179`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, PBYTE pbSignature, DWORD cbSignature)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x1800121f0`
- `0x18001f4e0`

## import_xrefs

- `ncrypt!NCryptVerifySignature` at `0x18001f573`
- `ncrypt!NCryptVerifySignature` at `0x18001f573`

## string_xrefs

- `0x18001f510`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PBYTE pbSignature,
        DWORD cbSignature)
{
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // ebx
  __int64 v9; // rcx
  BYTE *v10; // r8
  DWORD v11; // r9d
  __int64 v12; // r10
  __int64 *v13; // rdx
  DWORD dwFlags; // ecx
  SECURITY_STATUS v15; // eax
  __int64 v17; // [rsp+40h] [rbp-18h] BYREF

  v17 = 0;
  if ( !SslpValidateProvHandle() )
  {
    v7 = 5386;
LABEL_3:
    v8 = -2146893786;
    v9 = 2148073510LL;
    goto LABEL_4;
  }
  v12 = SslpValidateKeyPairHandle(v6);
  if ( !v12 )
  {
    v7 = 5395;
    goto LABEL_3;
  }
  v13 = &v17;
  dwFlags = 2;
  if ( *(_DWORD *)(v12 + 8) != 196609 )
  {
    dwFlags = 0;
    v13 = 0;
  }
  v15 = NCryptVerifySignature(*(_QWORD *)(v12 + 24), v13, v10, v11, pbSignature, cbSignature, dwFlags);
  v8 = v15;
  if ( v15 >= 0 )
    return 0;
  v7 = 5417;
  v9 = (unsigned int)v15;
LABEL_4:
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v7);
  return v8;
}

```

## disassembly

```asm
0x18001f4e0  push    rbx
0x18001f4e2  sub     rsp, 50h
0x18001f4e6  mov     [rsp+58h+var_18], 0
0x18001f4ef  call    SslpValidateProvHandle
0x18001f4f4  test    rax, rax
0x18001f4f7  jnz     short loc_18001F51E
0x18001f4f9  mov     r9d, 150Ah
0x18001f4ff  mov     ebx, 80090026h
0x18001f504  mov     ecx, 80090026h
0x18001f509  lea     rdx, aStatus; "Status"
0x18001f510  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f517  call    DebugTraceError
0x18001f51c  jmp     short loc_18001F58B
0x18001f51e  mov     rcx, rdx
0x18001f521  call    SslpValidateKeyPairHandle
0x18001f526  mov     r10, rax
0x18001f529  test    rax, rax
0x18001f52c  jnz     short loc_18001F536
0x18001f52e  mov     r9d, 1513h
0x18001f534  jmp     short loc_18001F4FF
0x18001f536  xor     eax, eax
0x18001f538  lea     rdx, [rsp+58h+var_18]
0x18001f53d  mov     r11d, 30001h
0x18001f543  mov     ecx, 2
0x18001f548  cmp     [r10+8], r11d
0x18001f54c  cmovnz  ecx, eax
0x18001f54f  cmovnz  rdx, rax; pPaddingInfo
0x18001f553  mov     eax, [rsp+58h+arg_28]
0x18001f55a  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x18001f55e  mov     rcx, [r10+18h]; hKey
0x18001f562  mov     [rsp+58h+cbSignature], eax; cbSignature
0x18001f566  mov     rax, [rsp+58h+arg_20]
0x18001f56e  mov     [rsp+58h+pbSignature], rax; pbSignature
0x18001f573  call    cs:__imp_NCryptVerifySignature
0x18001f579  mov     ebx, eax
0x18001f57b  test    eax, eax
0x18001f57d  jns     short loc_18001F589
0x18001f57f  mov     r9d, 1529h
0x18001f585  mov     ecx, eax
0x18001f587  jmp     short loc_18001F509
0x18001f589  xor     ebx, ebx
0x18001f58b  mov     eax, ebx
0x18001f58d  add     rsp, 50h
0x18001f591  pop     rbx
0x18001f592  retn
```
