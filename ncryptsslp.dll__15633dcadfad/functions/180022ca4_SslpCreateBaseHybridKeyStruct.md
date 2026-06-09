# SslpCreateBaseHybridKeyStruct

- ea: `0x180022ca4`
- end: `0x180022dfd`
- name: `SslpCreateBaseHybridKeyStruct`
- size: `345`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e480`
- `0x1800234b0`

## callees

- `0x1800066f0`
- `0x180007940`
- `0x18000b654`
- `0x180022ca4`
- `0x1800238b4`
- `0x180023a78`

## string_xrefs

- `0x180022d23`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022daa`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022dd9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpCreateBaseHybridKeyStruct(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v8; // r14
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rsi
  int v12; // ebx
  __int64 v14; // rax
  __int64 v15; // r9
  __int64 v16; // rcx

  if ( !a3 || !a4 || !a5 )
  {
    v12 = -2146893785;
    v15 = 370;
    v16 = 2148073511LL;
    goto LABEL_13;
  }
  v8 = SslpValidateEphemeralHandle(a3);
  v10 = SslpValidateKemKeyHandle(v9);
  v11 = v10;
  if ( !v8 || !v10 )
  {
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 386);
    return 2148073511LL;
  }
  v12 = SslpValidateHybridAndConstituentGroupsMatch(a2, v8, v10);
  if ( v12 < 0 )
  {
    DebugTraceError(2148073513LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 394);
    return 2148073513LL;
  }
  v14 = SafeAllocaAllocateFromHeap(48);
  if ( !v14 )
  {
    v12 = -2146893810;
    v15 = 404;
    v16 = 2148073486LL;
LABEL_13:
    DebugTraceError(v16, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v15);
    return (unsigned int)v12;
  }
  *(_DWORD *)(v14 + 10) = 0;
  *(_WORD *)(v14 + 14) = 0;
  *(_QWORD *)(v14 + 24) = 0;
  *(_QWORD *)(v14 + 40) = 0;
  *(_DWORD *)v14 = 48;
  *(_DWORD *)(v14 + 4) = 1936944187;
  *(_WORD *)(v14 + 8) = a2;
  *(_QWORD *)(v14 + 16) = a3;
  *(_QWORD *)(v14 + 32) = a4;
  ++*(_DWORD *)(v8 + 36);
  ++*(_DWORD *)(v11 + 48);
  *a5 = v14;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180022ca4  push    rbx
0x180022ca6  push    rbp
0x180022ca7  push    rsi
0x180022ca8  push    rdi
0x180022ca9  push    r12
0x180022cab  push    r14
0x180022cad  push    r15
0x180022caf  sub     rsp, 20h
0x180022cb3  mov     rdi, r9
0x180022cb6  mov     rbp, r8
0x180022cb9  movzx   r12d, dx
0x180022cbd  test    r8, r8
0x180022cc0  jz      loc_180022DC9
0x180022cc6  test    r9, r9
0x180022cc9  jz      loc_180022DC9
0x180022ccf  mov     r15, [rsp+58h+arg_20]
0x180022cd7  test    r15, r15
0x180022cda  jz      loc_180022DC9
0x180022ce0  mov     rcx, r8
0x180022ce3  call    SslpValidateEphemeralHandle
0x180022ce8  mov     rcx, r9
0x180022ceb  mov     r14, rax
0x180022cee  call    SslpValidateKemKeyHandle
0x180022cf3  mov     rsi, rax
0x180022cf6  test    r14, r14
0x180022cf9  jz      loc_180022DA4
0x180022cff  test    rax, rax
0x180022d02  jz      loc_180022DA4
0x180022d08  mov     r8, rax
0x180022d0b  mov     rdx, r14
0x180022d0e  movzx   ecx, r12w
0x180022d12  call    SslpValidateHybridAndConstituentGroupsMatch
0x180022d17  mov     ebx, eax
0x180022d19  test    eax, eax
0x180022d1b  jns     short loc_180022D45
0x180022d1d  mov     r9d, 18Ah
0x180022d23  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022d2a  lea     rdx, aStatus_0; "status"
0x180022d31  mov     ecx, 80090029h
0x180022d36  call    DebugTraceError
0x180022d3b  mov     eax, 80090029h
0x180022d40  jmp     loc_180022DEE
0x180022d45  mov     ecx, 30h ; '0'
0x180022d4a  call    SafeAllocaAllocateFromHeap
0x180022d4f  mov     rcx, rax
0x180022d52  test    rax, rax
0x180022d55  jnz     short loc_180022D69
0x180022d57  mov     ebx, 8009000Eh
0x180022d5c  mov     r9d, 194h
0x180022d62  mov     ecx, 8009000Eh
0x180022d67  jmp     short loc_180022DD9
0x180022d69  mov     dword ptr [rax+0Ah], 0
0x180022d70  xor     eax, eax
0x180022d72  mov     [rcx+0Eh], ax
0x180022d76  mov     [rcx+18h], rax
0x180022d7a  mov     [rcx+28h], rax
0x180022d7e  mov     dword ptr [rcx], 30h ; '0'
0x180022d84  mov     dword ptr [rcx+4], 73736C3Bh
0x180022d8b  mov     [rcx+8], r12w
0x180022d90  mov     [rcx+10h], rbp
0x180022d94  mov     [rcx+20h], rdi
0x180022d98  inc     dword ptr [r14+24h]
0x180022d9c  inc     dword ptr [rsi+30h]
0x180022d9f  mov     [r15], rcx
0x180022da2  jmp     short loc_180022DEC
0x180022da4  mov     r9d, 182h
0x180022daa  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022db1  lea     rdx, aStatus_0; "status"
0x180022db8  mov     ecx, 80090027h
0x180022dbd  call    DebugTraceError
0x180022dc2  mov     eax, 80090027h
0x180022dc7  jmp     short loc_180022DEE
0x180022dc9  mov     ebx, 80090027h
0x180022dce  mov     r9d, 172h
0x180022dd4  mov     ecx, 80090027h
0x180022dd9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022de0  lea     rdx, aStatus_0; "status"
0x180022de7  call    DebugTraceError
0x180022dec  mov     eax, ebx
0x180022dee  add     rsp, 20h
0x180022df2  pop     r15
0x180022df4  pop     r14
0x180022df6  pop     r12
0x180022df8  pop     rdi
0x180022df9  pop     rsi
0x180022dfa  pop     rbp
0x180022dfb  pop     rbx
0x180022dfc  retn
```
