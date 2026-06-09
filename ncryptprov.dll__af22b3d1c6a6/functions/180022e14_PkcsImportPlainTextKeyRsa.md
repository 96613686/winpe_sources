# _PkcsImportPlainTextKeyRsa

- ea: `0x180022e14`
- end: `0x180023048`
- name: `_PkcsImportPlainTextKeyRsa`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180034c30`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000f6a8`
- `0x180017580`
- `0x180022e14`
- `0x180023050`
- `0x180049d50`
- `0x180049dec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022eb3`
- `CRYPT32!CryptDecodeObjectEx` at `0x180022e9f`
- `CRYPT32!CryptDecodeObjectEx` at `0x180022e9f`

## string_xrefs

- `0x180022f14`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180022fad`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180023019`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall PkcsImportPlainTextKeyRsa(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rcx
  void *v7; // rdi
  int v10; // edx
  unsigned int v11; // ebx
  int v12; // esi
  signed int LastError; // eax
  int v14; // edx
  unsigned int *v15; // rcx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  int v21; // [rsp+40h] [rbp-28h] BYREF
  unsigned int *pvStructInfo; // [rsp+48h] [rbp-20h] BYREF
  void *v23; // [rsp+50h] [rbp-18h] BYREF
  DWORD pcbStructInfo; // [rsp+C0h] [rbp+58h] BYREF

  v23 = 0;
  v6 = *(_QWORD *)(a3 + 48);
  v7 = 0;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  v21 = 0;
  v11 = PkcsScanAttrList(v6, &v21);
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
        (unsigned int)"status",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
        67);
  }
  else
  {
    v12 = v21;
    if ( v21 == -1 )
      v12 = 0xFFFFFF;
    if ( CryptDecodeObjectEx(
           1u,
           (LPCSTR)0x53,
           *(const BYTE **)(a3 + 40),
           *(_DWORD *)(a3 + 32),
           0x8001u,
           &pDecodePara,
           &pvStructInfo,
           &pcbStructInfo) )
    {
      v18 = PkcsCreateKeyObject(&v23, a4, a2, 196609);
      v11 = v18;
      if ( v18 >= 0 )
      {
        v7 = v23;
        v19 = KspImportRsaPrivateKey((__int64)v23, pvStructInfo, pcbStructInfo, 2);
        v11 = v19;
        if ( v19 >= 0 )
        {
          pvStructInfo = 0;
          if ( v12 == 0xFFFFFF || (v19 = PkcsAddKeyUsageProperty((__int64)v7, v12), v11 = v19, v19 >= 0) )
          {
            *a1 = v7;
            return v11;
          }
          v20 = 2432;
        }
        else
        {
          v20 = 2420;
        }
        DebugTraceError(
          (unsigned int)v19,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          v20);
      }
      else
      {
        DebugTraceError(
          (unsigned int)v18,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          2407);
        v7 = v23;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          (unsigned int)"status",
          v11,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          88);
    }
  }
  v15 = pvStructInfo;
  if ( pvStructInfo )
  {
    v17 = pcbStructInfo;
    if ( pcbStructInfo )
    {
      do
      {
        *(_BYTE *)v15 = 0;
        v15 = (unsigned int *)((char *)v15 + 1);
        --v17;
      }
      while ( v17 );
      v15 = pvStructInfo;
    }
    MSCryptFree(v15);
  }
  if ( v7 )
    DeleteKeyObject(v7);
  return v11;
}

```

## disassembly

```asm
0x180022e14  push    rbp
0x180022e16  push    rbx
0x180022e17  push    rsi
0x180022e18  push    rdi
0x180022e19  push    r12
0x180022e1b  push    r13
0x180022e1d  push    r14
0x180022e1f  push    r15
0x180022e21  mov     rbp, rsp
0x180022e24  sub     rsp, 68h
0x180022e28  xor     esi, esi
0x180022e2a  mov     r13, rdx
0x180022e2d  mov     r15, rcx
0x180022e30  mov     [rbp+var_18], rsi
0x180022e34  mov     rcx, [r8+30h]
0x180022e38  lea     rdx, [rbp+var_28]
0x180022e3c  mov     edi, esi
0x180022e3e  mov     [rbp+var_20], rsi
0x180022e42  mov     [rbp+arg_10], esi
0x180022e45  mov     r12, r9
0x180022e48  mov     [rbp+var_28], esi
0x180022e4b  mov     r14, r8
0x180022e4e  call    _PkcsScanAttrList
0x180022e53  mov     ebx, eax
0x180022e55  test    eax, eax
0x180022e57  js      loc_180022F32
0x180022e5d  mov     esi, [rbp+var_28]
0x180022e60  lea     edx, [rdi+53h]; lpszStructType
0x180022e63  mov     r9d, [r14+20h]; cbEncoded
0x180022e67  lea     ecx, [rdi+1]; dwCertEncodingType
0x180022e6a  mov     r8, [r14+28h]; pbEncoded
0x180022e6e  mov     eax, 0FFFFFFh
0x180022e73  cmp     esi, 0FFFFFFFFh
0x180022e76  cmovz   esi, eax
0x180022e79  lea     rax, [rbp+arg_10]
0x180022e7d  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180022e82  lea     rax, [rbp+var_20]
0x180022e86  mov     [rsp+68h+pvStructInfo], rax; pvStructInfo
0x180022e8b  lea     rax, pDecodePara
0x180022e92  mov     [rsp+68h+pDecodePara], rax; pDecodePara
0x180022e97  mov     [rsp+68h+dwFlags], 8001h; dwFlags
0x180022e9f  call    cs:__imp_CryptDecodeObjectEx
0x180022ea6  nop     dword ptr [rax+rax+00h]
0x180022eab  test    eax, eax
0x180022ead  jnz     loc_180022F85
0x180022eb3  call    cs:__imp_GetLastError
0x180022eba  nop     dword ptr [rax+rax+00h]
0x180022ebf  mov     ebx, eax
0x180022ec1  test    eax, eax
0x180022ec3  jg      loc_180022F77
0x180022ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ed0  lea     rax, WPP_GLOBAL_Control
0x180022ed7  cmp     rcx, rax
0x180022eda  jz      short loc_180022EE2
0x180022edc  test    byte ptr [rcx+1Ch], 1
0x180022ee0  jnz     short loc_180022F08
0x180022ee2  mov     rcx, [rbp+var_20]
0x180022ee6  test    rcx, rcx
0x180022ee9  jnz     short loc_180022F55
0x180022eeb  test    rdi, rdi
0x180022eee  jnz     loc_180023033
0x180022ef4  mov     eax, ebx
0x180022ef6  add     rsp, 68h
0x180022efa  pop     r15
0x180022efc  pop     r14
0x180022efe  pop     r13
0x180022f00  pop     r12
0x180022f02  pop     rdi
0x180022f03  pop     rsi
0x180022f04  pop     rbx
0x180022f05  pop     rbp
0x180022f06  retn
0x180022f08  mov     dword ptr [rsp+68h+pvStructInfo], 958h
0x180022f10  mov     rcx, [rcx+10h]
0x180022f14  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022f1b  mov     [rsp+68h+pDecodePara], r8
0x180022f20  lea     r9, aStatus_0; "status"
0x180022f27  mov     [rsp+68h+dwFlags], ebx
0x180022f2b  call    WPP_SF_sDsd
0x180022f30  jmp     short loc_180022EE2
0x180022f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f39  lea     rax, WPP_GLOBAL_Control
0x180022f40  cmp     rcx, rax
0x180022f43  jz      short loc_180022EE2
0x180022f45  test    byte ptr [rcx+1Ch], 1
0x180022f49  jz      short loc_180022EE2
0x180022f4b  mov     dword ptr [rsp+68h+pvStructInfo], 943h
0x180022f53  jmp     short loc_180022F10
0x180022f55  mov     eax, [rbp+arg_10]
0x180022f58  test    rax, rax
0x180022f5b  jz      short loc_180022F6D
0x180022f5d  mov     byte ptr [rcx], 0
0x180022f60  inc     rcx
0x180022f63  sub     rax, 1
0x180022f67  jnz     short loc_180022F5D
0x180022f69  mov     rcx, [rbp+var_20]
0x180022f6d  call    MSCryptFree
0x180022f72  jmp     loc_180022EEB
0x180022f77  movzx   ebx, ax
0x180022f7a  or      ebx, 80070000h
0x180022f80  jmp     loc_180022EC9
0x180022f85  mov     eax, [rbp+arg_20]
0x180022f88  lea     rcx, [rbp+var_18]
0x180022f8c  mov     r9d, 30001h
0x180022f92  mov     dword ptr [rsp+68h+pDecodePara], eax
0x180022f96  mov     r8, r13
0x180022f99  mov     rdx, r12
0x180022f9c  call    _PkcsCreateKeyObject
0x180022fa1  mov     ebx, eax
0x180022fa3  test    eax, eax
0x180022fa5  jns     short loc_180022FCB
0x180022fa7  mov     r9d, 967h
0x180022fad  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022fb4  lea     rdx, aStatus_0; "status"
0x180022fbb  mov     ecx, eax
0x180022fbd  call    DebugTraceError
0x180022fc2  mov     rdi, [rbp+var_18]
0x180022fc6  jmp     loc_180022EE2
0x180022fcb  mov     rdi, [rbp+var_18]
0x180022fcf  mov     r9d, 2
0x180022fd5  mov     r8d, [rbp+arg_10]
0x180022fd9  mov     rcx, rdi
0x180022fdc  mov     rdx, [rbp+var_20]
0x180022fe0  call    KspImportRsaPrivateKey
0x180022fe5  mov     ebx, eax
0x180022fe7  test    eax, eax
0x180022fe9  jns     short loc_180022FF3
0x180022feb  mov     r9d, 974h
0x180022ff1  jmp     short loc_180023019
0x180022ff3  mov     [rbp+var_20], 0
0x180022ffb  cmp     esi, 0FFFFFFh
0x180023001  jz      short loc_180023040
0x180023003  mov     edx, esi
0x180023005  mov     rcx, rdi
0x180023008  call    _PkcsAddKeyUsageProperty
0x18002300d  mov     ebx, eax
0x18002300f  test    eax, eax
0x180023011  jns     short loc_180023040
0x180023013  mov     r9d, 980h
0x180023019  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023020  mov     ecx, eax
0x180023022  lea     rdx, aStatus_0; "status"
0x180023029  call    DebugTraceError
0x18002302e  jmp     loc_180022EE2
0x180023033  mov     rcx, rdi; void *
0x180023036  call    DeleteKeyObject
0x18002303b  jmp     loc_180022EF4
0x180023040  mov     [r15], rdi
0x180023043  jmp     loc_180022EF4
```
