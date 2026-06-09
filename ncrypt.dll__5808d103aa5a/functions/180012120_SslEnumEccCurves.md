# SslEnumEccCurves

- ea: `0x180012120`
- end: `0x1800122be`
- name: `SslEnumEccCurves`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180011cd0`
- `0x180012120`
- `0x180020010`

## string_xrefs

- `0x18001216d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012224`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012295`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslEnumEccCurves(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        BYTE *a5,
        DWORD a6,
        DWORD *a7)
{
  NCRYPT_KEY_HANDLE *v8; // rdx
  __int64 v9; // rdi
  NCryptKeyName **v10; // r8
  NCryptAlgorithmName **v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 (__fastcall *v15)(_QWORD); // rax
  __int64 v16; // rax

  v9 = ValidateSslProvHandle(a1);
  if ( !v9 )
  {
    v12 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v8,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        193);
    return NormalizeNteStatus(v12, v8, v10, v11, a5, a6, a7);
  }
  if ( !a3 || !v8 )
  {
    v12 = -2146893785;
    v13 = 1480;
    v14 = 2148073511LL;
    goto LABEL_21;
  }
  *(_DWORD *)v8 = 0;
  *v10 = 0;
  if ( *(_WORD *)(v9 + 32) < 3u )
  {
    v13 = 1496;
LABEL_10:
    v12 = -2146893783;
    v14 = 2148073513LL;
    goto LABEL_21;
  }
  v15 = *(__int64 (__fastcall **)(_QWORD))(v9 + 264);
  if ( !v15 )
  {
    v13 = 1507;
    goto LABEL_10;
  }
  v12 = v15(*(_QWORD *)(v9 + 424));
  if ( (v12 & 0x80000000) == 0 )
  {
    v16 = SafeAllocaAllocateFromHeap(32);
    if ( v16 )
    {
      *(_OWORD *)v16 = 0;
      *(_OWORD *)(v16 + 16) = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 16));
      *(_QWORD *)v16 = v9;
      *(_QWORD *)(v16 + 8) = *a3;
      MSCryptAddMemoryBuffer(&SslpProviderBufferList, v16);
      v12 = 0;
      return NormalizeNteStatus(v12, v8, v10, v11, a5, a6, a7);
    }
    v12 = -2146893810;
    v13 = 1533;
    v14 = 2148073486LL;
LABEL_21:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v13);
    return NormalizeNteStatus(v12, v8, v10, v11, a5, a6, a7);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v8,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      (unsigned int)"Status",
      v12,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      241);
  return NormalizeNteStatus(v12, v8, v10, v11, a5, a6, a7);
}

```

## disassembly

```asm
0x180012120  mov     [rsp+arg_0], rbx
0x180012125  mov     [rsp+arg_8], rsi
0x18001212a  push    rdi
0x18001212b  sub     rsp, 40h
0x18001212f  mov     rsi, r8
0x180012132  call    ValidateSslProvHandle
0x180012137  mov     rdi, rax
0x18001213a  test    rax, rax
0x18001213d  jnz     short loc_180012196
0x18001213f  mov     ebx, 80090026h
0x180012144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001214b  lea     rax, WPP_GLOBAL_Control
0x180012152  cmp     rcx, rax
0x180012155  jz      loc_1800122A8
0x18001215b  test    byte ptr [rcx+1Ch], 1
0x18001215f  jz      loc_1800122A8
0x180012165  mov     [rsp+48h+var_18], 5C1h
0x18001216d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012174  mov     [rsp+48h+var_20], r8
0x180012179  mov     [rsp+48h+var_28], 80090026h
0x180012181  mov     rcx, [rcx+10h]
0x180012185  lea     r9, aStatus; "Status"
0x18001218c  call    WPP_SF_sDsd
0x180012191  jmp     loc_1800122A8
0x180012196  test    rsi, rsi
0x180012199  jz      loc_180012285
0x18001219f  test    rdx, rdx
0x1800121a2  jz      loc_180012285
0x1800121a8  mov     dword ptr [rdx], 0
0x1800121ae  mov     eax, 3
0x1800121b3  mov     qword ptr [r8], 0
0x1800121ba  cmp     ax, [rdi+20h]
0x1800121be  jbe     short loc_1800121D5
0x1800121c0  mov     r9d, 5D8h
0x1800121c6  mov     ebx, 80090029h
0x1800121cb  mov     ecx, 80090029h
0x1800121d0  jmp     loc_180012295
0x1800121d5  mov     rax, [rdi+108h]
0x1800121dc  test    rax, rax
0x1800121df  jnz     short loc_1800121E9
0x1800121e1  mov     r9d, 5E3h
0x1800121e7  jmp     short loc_1800121C6
0x1800121e9  mov     rcx, [rdi+1A8h]
0x1800121f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121f5  mov     ebx, eax
0x1800121f7  test    eax, eax
0x1800121f9  jns     short loc_180012239
0x1800121fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012202  lea     rax, WPP_GLOBAL_Control
0x180012209  cmp     rcx, rax
0x18001220c  jz      loc_1800122A8
0x180012212  test    byte ptr [rcx+1Ch], 1
0x180012216  jz      loc_1800122A8
0x18001221c  mov     [rsp+48h+var_18], 5F1h
0x180012224  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001222b  mov     [rsp+48h+var_20], r8
0x180012230  mov     [rsp+48h+var_28], ebx
0x180012234  jmp     loc_180012181
0x180012239  mov     ecx, 20h ; ' '
0x18001223e  call    SafeAllocaAllocateFromHeap
0x180012243  mov     rdx, rax
0x180012246  test    rax, rax
0x180012249  jnz     short loc_18001225D
0x18001224b  mov     ebx, 8009000Eh
0x180012250  mov     r9d, 5FDh
0x180012256  mov     ecx, 8009000Eh
0x18001225b  jmp     short loc_180012295
0x18001225d  xorps   xmm0, xmm0
0x180012260  movups  xmmword ptr [rax], xmm0
0x180012263  movups  xmmword ptr [rax+10h], xmm0
0x180012267  lock inc dword ptr [rdi+10h]
0x18001226b  mov     [rax], rdi
0x18001226e  lea     rcx, SslpProviderBufferList
0x180012275  mov     rax, [rsi]
0x180012278  mov     [rdx+8], rax
0x18001227c  call    MSCryptAddMemoryBuffer
0x180012281  xor     ebx, ebx
0x180012283  jmp     short loc_1800122A8
0x180012285  mov     ebx, 80090027h
0x18001228a  mov     r9d, 5C8h
0x180012290  mov     ecx, 80090027h
0x180012295  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001229c  lea     rdx, aStatus; "Status"
0x1800122a3  call    DebugTraceError
0x1800122a8  mov     ecx, ebx
0x1800122aa  mov     rbx, [rsp+48h+arg_0]
0x1800122af  mov     rsi, [rsp+48h+arg_8]
0x1800122b4  add     rsp, 40h
0x1800122b8  pop     rdi
0x1800122b9  jmp     NormalizeNteStatus
```
