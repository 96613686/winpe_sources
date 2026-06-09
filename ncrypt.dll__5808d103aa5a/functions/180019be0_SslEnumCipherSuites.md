# SslEnumCipherSuites

- ea: `0x180019be0`
- end: `0x180019ddd`
- name: `SslEnumCipherSuites`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180011cd0`
- `0x180019be0`
- `0x180020010`

## string_xrefs

- `0x180019c2a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180019d35`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180019db7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslEnumCipherSuites(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4,
        BYTE *a5,
        DWORD a6,
        DWORD *a7)
{
  NCRYPT_KEY_HANDLE *v9; // rdx
  __int64 v10; // rbp
  NCryptKeyName **v11; // r8
  NCryptAlgorithmName **v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rbx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 *v17; // rdi
  __int64 *v18; // rax
  __int64 *v19; // rax
  __int64 *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rdx
  int v24; // eax

  v10 = ValidateSslProvHandle(a1);
  if ( !v10 )
  {
    v13 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        156);
    return NormalizeNteStatus(v13, v9, v11, v12, a5, a6, a7);
  }
  v14 = 0;
  if ( v9 )
  {
    v14 = ValidateSslKeyHandle(v9);
    if ( !v14 )
    {
      v13 = -2146893786;
      v15 = 1190;
      v16 = 2148073510LL;
LABEL_29:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v15);
      return NormalizeNteStatus(v13, v9, v11, v12, a5, a6, a7);
    }
  }
  if ( !a3 || !a4 )
  {
    v13 = -2146893785;
    v15 = 1198;
    v16 = 2148073511LL;
    goto LABEL_29;
  }
  v17 = 0;
  if ( !*v12 )
  {
    v18 = (__int64 *)SafeAllocaAllocateFromHeap(32);
    v17 = v18;
    if ( !v18 )
    {
      v13 = -2146893810;
      v15 = 1215;
      v16 = 2148073486LL;
      goto LABEL_29;
    }
    *(_OWORD *)v18 = 0;
    *((_OWORD *)v18 + 1) = 0;
  }
  v19 = (__int64 *)SafeAllocaAllocateFromHeap(32);
  v20 = v19;
  if ( !v19 )
  {
    v13 = -2146893810;
    v21 = 2148073486LL;
    v22 = 1231;
LABEL_21:
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v22);
    if ( v17 )
      MSCryptFree(v17);
    if ( v20 )
      MSCryptFree(v20);
    return NormalizeNteStatus(v13, v9, v11, v12, a5, a6, a7);
  }
  *(_OWORD *)v19 = 0;
  *((_OWORD *)v19 + 1) = 0;
  if ( v14 )
    v23 = *(_QWORD *)(v14 + 16);
  else
    v23 = 0;
  v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64 *, _DWORD))(v10 + 96))(
          *(_QWORD *)(v10 + 424),
          v23,
          a3,
          a4,
          (_DWORD)a5);
  v13 = v24;
  if ( v24 < 0 )
  {
    v21 = (unsigned int)v24;
    v22 = 1249;
    goto LABEL_21;
  }
  if ( v17 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
    *v17 = v10;
    v17[1] = *a4;
    MSCryptAddMemoryBuffer(&SslpProviderBufferList, v17);
  }
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
  *v20 = v10;
  v20[1] = *a3;
  MSCryptAddMemoryBuffer(&SslpProviderBufferList, v20);
  v13 = 0;
  return NormalizeNteStatus(v13, v9, v11, v12, a5, a6, a7);
}

```

## disassembly

```asm
0x180019be0  push    rbx
0x180019be2  push    rbp
0x180019be3  push    rsi
0x180019be4  push    rdi
0x180019be5  push    r14
0x180019be7  push    r15
0x180019be9  sub     rsp, 48h
0x180019bed  mov     r14, r9
0x180019bf0  mov     r15, r8
0x180019bf3  call    ValidateSslProvHandle
0x180019bf8  mov     rbp, rax
0x180019bfb  test    rax, rax
0x180019bfe  jnz     short loc_180019C57
0x180019c00  mov     ebx, 80090026h
0x180019c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c0c  lea     rax, WPP_GLOBAL_Control
0x180019c13  cmp     rcx, rax
0x180019c16  jz      loc_180019DCA
0x180019c1c  test    byte ptr [rcx+1Ch], 1
0x180019c20  jz      loc_180019DCA
0x180019c26  mov     rcx, [rcx+10h]
0x180019c2a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019c31  mov     [rsp+78h+var_48], 49Ch
0x180019c39  lea     r9, aStatus; "Status"
0x180019c40  mov     [rsp+78h+var_50], r8
0x180019c45  mov     [rsp+78h+var_58], 80090026h
0x180019c4d  call    WPP_SF_sDsd
0x180019c52  jmp     loc_180019DCA
0x180019c57  xor     ebx, ebx
0x180019c59  test    rdx, rdx
0x180019c5c  jz      short loc_180019C83
0x180019c5e  mov     rcx, rdx
0x180019c61  call    ValidateSslKeyHandle
0x180019c66  mov     rbx, rax
0x180019c69  test    rax, rax
0x180019c6c  jnz     short loc_180019C83
0x180019c6e  mov     ebx, 80090026h
0x180019c73  mov     r9d, 4A6h
0x180019c79  mov     ecx, 80090026h
0x180019c7e  jmp     loc_180019DB7
0x180019c83  test    r15, r15
0x180019c86  jz      loc_180019DA7
0x180019c8c  test    r14, r14
0x180019c8f  jz      loc_180019DA7
0x180019c95  xor     edi, edi
0x180019c97  lea     esi, [rdi+20h]
0x180019c9a  cmp     [r9], rdi
0x180019c9d  jnz     short loc_180019CCD
0x180019c9f  mov     ecx, esi
0x180019ca1  call    SafeAllocaAllocateFromHeap
0x180019ca6  mov     rdi, rax
0x180019ca9  test    rax, rax
0x180019cac  jnz     short loc_180019CC3
0x180019cae  mov     ebx, 8009000Eh
0x180019cb3  mov     r9d, 4BFh
0x180019cb9  mov     ecx, 8009000Eh
0x180019cbe  jmp     loc_180019DB7
0x180019cc3  xorps   xmm0, xmm0
0x180019cc6  movups  xmmword ptr [rax], xmm0
0x180019cc9  movups  xmmword ptr [rax+10h], xmm0
0x180019ccd  mov     rcx, rsi
0x180019cd0  call    SafeAllocaAllocateFromHeap
0x180019cd5  mov     rsi, rax
0x180019cd8  test    rax, rax
0x180019cdb  jnz     short loc_180019CEF
0x180019cdd  mov     ebx, 8009000Eh
0x180019ce2  mov     ecx, 8009000Eh
0x180019ce7  mov     r9d, 4CFh
0x180019ced  jmp     short loc_180019D35
0x180019cef  xorps   xmm0, xmm0
0x180019cf2  movups  xmmword ptr [rax], xmm0
0x180019cf5  movups  xmmword ptr [rax+10h], xmm0
0x180019cf9  test    rbx, rbx
0x180019cfc  jz      short loc_180019D04
0x180019cfe  mov     rdx, [rbx+10h]
0x180019d02  jmp     short loc_180019D06
0x180019d04  xor     edx, edx
0x180019d06  mov     ecx, [rsp+78h+arg_20]
0x180019d0d  mov     r9, r14
0x180019d10  mov     rax, [rbp+60h]
0x180019d14  mov     r8, r15
0x180019d17  mov     [rsp+78h+var_58], ecx
0x180019d1b  mov     rcx, [rbp+1A8h]
0x180019d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d27  mov     ebx, eax
0x180019d29  test    eax, eax
0x180019d2b  jns     short loc_180019D64
0x180019d2d  mov     ecx, eax
0x180019d2f  mov     r9d, 4E1h
0x180019d35  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019d3c  lea     rdx, aStatus; "Status"
0x180019d43  call    DebugTraceError
0x180019d48  test    rdi, rdi
0x180019d4b  jz      short loc_180019D55
0x180019d4d  mov     rcx, rdi
0x180019d50  call    MSCryptFree
0x180019d55  test    rsi, rsi
0x180019d58  jz      short loc_180019DCA
0x180019d5a  mov     rcx, rsi
0x180019d5d  call    MSCryptFree
0x180019d62  jmp     short loc_180019DCA
0x180019d64  test    rdi, rdi
0x180019d67  jz      short loc_180019D86
0x180019d69  lock inc dword ptr [rbp+10h]
0x180019d6d  mov     [rdi], rbp
0x180019d70  lea     rcx, SslpProviderBufferList
0x180019d77  mov     rax, [r14]
0x180019d7a  mov     rdx, rdi
0x180019d7d  mov     [rdi+8], rax
0x180019d81  call    MSCryptAddMemoryBuffer
0x180019d86  lock inc dword ptr [rbp+10h]
0x180019d8a  mov     [rsi], rbp
0x180019d8d  lea     rcx, SslpProviderBufferList
0x180019d94  mov     rax, [r15]
0x180019d97  mov     rdx, rsi
0x180019d9a  mov     [rsi+8], rax
0x180019d9e  call    MSCryptAddMemoryBuffer
0x180019da3  xor     ebx, ebx
0x180019da5  jmp     short loc_180019DCA
0x180019da7  mov     ebx, 80090027h
0x180019dac  mov     r9d, 4AEh
0x180019db2  mov     ecx, 80090027h
0x180019db7  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019dbe  lea     rdx, aStatus; "Status"
0x180019dc5  call    DebugTraceError
0x180019dca  mov     ecx, ebx
0x180019dcc  add     rsp, 48h
0x180019dd0  pop     r15
0x180019dd2  pop     r14
0x180019dd4  pop     rdi
0x180019dd5  pop     rsi
0x180019dd6  pop     rbp
0x180019dd7  pop     rbx
0x180019dd8  jmp     NormalizeNteStatus
```
