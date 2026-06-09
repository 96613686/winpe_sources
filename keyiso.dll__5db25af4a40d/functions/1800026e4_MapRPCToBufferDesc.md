# _MapRPCToBufferDesc

- ea: `0x1800026e4`
- end: `0x1800027fa`
- name: `_MapRPCToBufferDesc`
- size: `278`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003880`
- `0x1800057a0`
- `0x1800064b0`
- `0x18000df70`
- `0x18000e3f0`
- `0x18000f250`

## callees

- `0x1800026e4`
- `0x180002d20`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`

## string_xrefs

- `0x180002780`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800027d2`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall MapRPCToBufferDesc(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int i; // r8d
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // edx
  int v7; // r8d
  __int64 v8; // rbx

  v1 = 0;
  if ( *(_DWORD *)(a1 + 4) )
  {
    v1 = MSCryptAlloc(16LL * *(unsigned int *)(a1 + 4));
    if ( !v1 )
    {
      v8 = 0;
      DebugTraceError(
        2148073486LL,
        "NTE_NO_MEMORY",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        71);
      return v8;
    }
    for ( i = 0; i < *(_DWORD *)(a1 + 4); *(_DWORD *)(v1 + 8 * v4 + 4) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4 + 4) )
    {
      v4 = i++;
      v4 *= 2;
      *(_DWORD *)(v1 + 8 * v4) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4);
      *(_QWORD *)(v1 + 8 * v4 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4 + 8);
    }
  }
  v5 = MSCryptAlloc(16);
  v8 = v5;
  if ( v5 )
  {
    *(_DWORD *)v5 = *(_DWORD *)a1;
    *(_DWORD *)(v5 + 4) = *(_DWORD *)(a1 + 4);
    *(_QWORD *)(v5 + 8) = v1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        (unsigned int)"NTE_NO_MEMORY",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        88);
    if ( v1 )
      MSCryptFree(v1);
  }
  return v8;
}

```

## disassembly

```asm
0x1800026e4  mov     [rsp+arg_0], rbx
0x1800026e9  mov     [rsp+arg_8], rsi
0x1800026ee  push    rdi
0x1800026ef  sub     rsp, 40h
0x1800026f3  xor     edi, edi
0x1800026f5  mov     rsi, rcx
0x1800026f8  cmp     [rcx+4], edi
0x1800026fb  jbe     short loc_180002751
0x1800026fd  mov     ecx, [rcx+4]
0x180002700  shl     rcx, 4
0x180002704  call    MSCryptAlloc
0x180002709  mov     rdi, rax
0x18000270c  test    rax, rax
0x18000270f  jz      loc_1800027D0
0x180002715  xor     r8d, r8d
0x180002718  cmp     [rsi+4], r8d
0x18000271c  jbe     short loc_180002751
0x18000271e  mov     rax, [rsi+8]
0x180002722  mov     edx, r8d
0x180002725  inc     r8d
0x180002728  add     rdx, rdx
0x18000272b  mov     ecx, [rax+rdx*8]
0x18000272e  mov     [rdi+rdx*8], ecx
0x180002731  mov     rax, [rsi+8]
0x180002735  mov     rcx, [rax+rdx*8+8]
0x18000273a  mov     [rdi+rdx*8+8], rcx
0x18000273f  mov     rax, [rsi+8]
0x180002743  mov     ecx, [rax+rdx*8+4]
0x180002747  mov     [rdi+rdx*8+4], ecx
0x18000274b  cmp     r8d, [rsi+4]
0x18000274f  jb      short loc_18000271E
0x180002751  mov     ecx, 10h
0x180002756  call    MSCryptAlloc
0x18000275b  mov     rbx, rax
0x18000275e  test    rax, rax
0x180002761  jnz     short loc_1800027C0
0x180002763  mov     rcx, cs:WPP_GLOBAL_Control
0x18000276a  lea     rax, WPP_GLOBAL_Control
0x180002771  cmp     rcx, rax
0x180002774  jz      short loc_1800027A8
0x180002776  test    byte ptr [rcx+1Ch], 1
0x18000277a  jz      short loc_1800027A8
0x18000277c  mov     rcx, [rcx+10h]
0x180002780  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002787  mov     [rsp+48h+var_18], 58h ; 'X'
0x18000278f  lea     r9, aNteNoMemory; "NTE_NO_MEMORY"
0x180002796  mov     [rsp+48h+var_20], rax
0x18000279b  mov     [rsp+48h+var_28], 8009000Eh
0x1800027a3  call    WPP_SF_sDsd
0x1800027a8  test    rdi, rdi
0x1800027ab  jnz     short loc_1800027F0
0x1800027ad  mov     rsi, [rsp+48h+arg_8]
0x1800027b2  mov     rax, rbx
0x1800027b5  mov     rbx, [rsp+48h+arg_0]
0x1800027ba  add     rsp, 40h
0x1800027be  pop     rdi
0x1800027bf  retn
0x1800027c0  mov     ecx, [rsi]
0x1800027c2  mov     [rax], ecx
0x1800027c4  mov     ecx, [rsi+4]
0x1800027c7  mov     [rax+4], ecx
0x1800027ca  mov     [rax+8], rdi
0x1800027ce  jmp     short loc_1800027AD
0x1800027d0  xor     ebx, ebx
0x1800027d2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800027d9  lea     rdx, aNteNoMemory; "NTE_NO_MEMORY"
0x1800027e0  mov     ecx, 8009000Eh
0x1800027e5  lea     r9d, [rbx+47h]
0x1800027e9  call    DebugTraceError
0x1800027ee  jmp     short loc_1800027AD
0x1800027f0  mov     rcx, rdi
0x1800027f3  call    MSCryptFree
0x1800027f8  jmp     short loc_1800027AD
```
