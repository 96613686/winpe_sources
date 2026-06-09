# SslpExportEphemeralKey

- ea: `0x180013c6c`
- end: `0x180013e65`
- name: `SslpExportEphemeralKey`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e320`
- `0x180014024`

## callees

- `0x1800066f0`
- `0x18000b594`
- `0x18000b654`
- `0x180013c6c`
- `0x1800185e0`

## import_xrefs

- `ncrypt!NCryptExportKey` at `0x180013de5`
- `ncrypt!NCryptExportKey` at `0x180013de5`

## string_xrefs

- `0x180013c93`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x180013d9e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x180013df7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x180013e2d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslpExportEphemeralKey(
        __int64 a1,
        const wchar_t *a2,
        BYTE *a3,
        DWORD a4,
        DWORD *pcbResult,
        DWORD dwFlags)
{
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rdi
  SECURITY_STATUS result; // eax
  __int64 v14; // r9
  SECURITY_STATUS v15; // ebx

  v9 = SslpValidateEphemeralHandle(a1);
  v12 = v9;
  if ( !v9 )
  {
    DebugTraceError(2148073510LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c", 257);
    return -2146893786;
  }
  if ( a2 && pcbResult )
  {
    switch ( *(_DWORD *)(v9 + 8) )
    {
      case 0x30001:
        if ( wcscmp(a2, L"RSAPUBLICBLOB") )
        {
          v14 = 275;
          goto LABEL_22;
        }
        break;
      case 0x30002:
        if ( wcscmp(a2, L"DHPUBLICBLOB") )
        {
          v14 = 286;
          goto LABEL_22;
        }
        break;
      case 0x30007:
      case 0x30008:
      case 0x30009:
        if ( wcscmp(a2, L"ECCPUBLICBLOB") && wcscmp(a2, L"ECCFULLPUBLICBLOB") )
        {
          v14 = 300;
          goto LABEL_22;
        }
        break;
      case 0x3000A:
        if ( wcscmp(a2, L"ECCFULLPUBLICBLOB") && wcscmp(a2, L"ECCPUBLICBLOB") )
        {
          v14 = 312;
          goto LABEL_22;
        }
        break;
      default:
        v14 = 321;
LABEL_22:
        DebugTraceError(
          2148073513LL,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
          v14);
        return -2146893783;
    }
    result = NCryptExportKey(*(_QWORD *)(v12 + 24), 0, a2, 0, a3, a4, pcbResult, dwFlags);
    v15 = result;
    if ( result < 0 )
    {
      DebugTraceError(
        (unsigned int)result,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        337);
      return v15;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        8);
    return -2146893785;
  }
  return result;
}

```

## disassembly

```asm
0x180013c6c  push    rbx
0x180013c6e  push    rbp
0x180013c6f  push    rsi
0x180013c70  push    rdi
0x180013c71  push    r14
0x180013c73  sub     rsp, 40h
0x180013c77  mov     ebp, r9d
0x180013c7a  mov     r14, r8
0x180013c7d  mov     rbx, rdx
0x180013c80  call    SslpValidateEphemeralHandle
0x180013c85  mov     rdi, rax
0x180013c88  test    rax, rax
0x180013c8b  jnz     short loc_180013CB5
0x180013c8d  mov     r9d, 101h
0x180013c93  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013c9a  lea     rdx, aStatus_0; "status"
0x180013ca1  mov     ecx, 80090026h
0x180013ca6  call    DebugTraceError
0x180013cab  mov     eax, 80090026h
0x180013cb0  jmp     loc_180013E5A
0x180013cb5  test    rbx, rbx
0x180013cb8  jz      loc_180013E10
0x180013cbe  mov     rsi, [rsp+68h+arg_20]
0x180013cc6  test    rsi, rsi
0x180013cc9  jz      loc_180013E10
0x180013ccf  mov     ecx, [rax+8]
0x180013cd2  sub     ecx, 30001h
0x180013cd8  jz      loc_180013D85
0x180013cde  sub     ecx, 1
0x180013ce1  jz      loc_180013D6A
0x180013ce7  sub     ecx, 5
0x180013cea  jz      short loc_180013D3C
0x180013cec  sub     ecx, 1
0x180013cef  jz      short loc_180013D3C
0x180013cf1  sub     ecx, 1
0x180013cf4  jz      short loc_180013D3C
0x180013cf6  cmp     ecx, 1
0x180013cf9  jz      short loc_180013D06
0x180013cfb  mov     r9d, 141h
0x180013d01  jmp     loc_180013D9E
0x180013d06  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180013d0d  mov     rcx, rbx; String1
0x180013d10  call    wcscmp
0x180013d15  test    eax, eax
0x180013d17  jz      loc_180013DC0
0x180013d1d  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180013d24  mov     rcx, rbx; String1
0x180013d27  call    wcscmp
0x180013d2c  test    eax, eax
0x180013d2e  jz      loc_180013DC0
0x180013d34  mov     r9d, 138h
0x180013d3a  jmp     short loc_180013D9E
0x180013d3c  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180013d43  mov     rcx, rbx; String1
0x180013d46  call    wcscmp
0x180013d4b  test    eax, eax
0x180013d4d  jz      short loc_180013DC0
0x180013d4f  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180013d56  mov     rcx, rbx; String1
0x180013d59  call    wcscmp
0x180013d5e  test    eax, eax
0x180013d60  jz      short loc_180013DC0
0x180013d62  mov     r9d, 12Ch
0x180013d68  jmp     short loc_180013D9E
0x180013d6a  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x180013d71  mov     rcx, rbx; String1
0x180013d74  call    wcscmp
0x180013d79  test    eax, eax
0x180013d7b  jz      short loc_180013DC0
0x180013d7d  mov     r9d, 11Eh
0x180013d83  jmp     short loc_180013D9E
0x180013d85  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180013d8c  mov     rcx, rbx; String1
0x180013d8f  call    wcscmp
0x180013d94  test    eax, eax
0x180013d96  jz      short loc_180013DC0
0x180013d98  mov     r9d, 113h
0x180013d9e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013da5  mov     ecx, 80090029h
0x180013daa  lea     rdx, aStatus_0; "status"
0x180013db1  call    DebugTraceError
0x180013db6  mov     eax, 80090029h
0x180013dbb  jmp     loc_180013E5A
0x180013dc0  mov     eax, [rsp+68h+arg_28]
0x180013dc7  xor     r9d, r9d; pParameterList
0x180013dca  mov     rcx, [rdi+18h]; hKey
0x180013dce  mov     r8, rbx; pszBlobType
0x180013dd1  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180013dd5  xor     edx, edx; hExportKey
0x180013dd7  mov     [rsp+68h+pcbResult], rsi; pcbResult
0x180013ddc  mov     [rsp+68h+cbOutput], ebp; cbOutput
0x180013de0  mov     [rsp+68h+pbOutput], r14; pbOutput
0x180013de5  call    cs:__imp_NCryptExportKey
0x180013deb  mov     ebx, eax
0x180013ded  test    eax, eax
0x180013def  jns     short loc_180013E5A
0x180013df1  mov     r9d, 151h
0x180013df7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013dfe  lea     rdx, aStatus_0; "status"
0x180013e05  mov     ecx, eax
0x180013e07  call    DebugTraceError
0x180013e0c  mov     eax, ebx
0x180013e0e  jmp     short loc_180013E5A
0x180013e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e17  lea     rax, WPP_GLOBAL_Control
0x180013e1e  cmp     rcx, rax
0x180013e21  jz      short loc_180013E55
0x180013e23  test    byte ptr [rcx+1Ch], 1
0x180013e27  jz      short loc_180013E55
0x180013e29  mov     rcx, [rcx+10h]
0x180013e2d  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013e34  mov     dword ptr [rsp+68h+pcbResult], 108h
0x180013e3c  lea     r9, aStatus_0; "status"
0x180013e43  mov     qword ptr [rsp+68h+cbOutput], rax
0x180013e48  mov     dword ptr [rsp+68h+pbOutput], 80090027h
0x180013e50  call    WPP_SF_sDsd
0x180013e55  mov     eax, 80090027h
0x180013e5a  add     rsp, 40h
0x180013e5e  pop     r14
0x180013e60  pop     rdi
0x180013e61  pop     rsi
0x180013e62  pop     rbp
0x180013e63  pop     rbx
0x180013e64  retn
```
