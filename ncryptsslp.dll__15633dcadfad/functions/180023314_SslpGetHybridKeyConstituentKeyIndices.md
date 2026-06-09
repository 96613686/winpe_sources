# SslpGetHybridKeyConstituentKeyIndices

- ea: `0x180023314`
- end: `0x1800233a1`
- name: `SslpGetHybridKeyConstituentKeyIndices`
- size: `141`
- prototype: `__int64 __fastcall(__int16, _DWORD *, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022608`
- `0x1800229a4`
- `0x180022fa8`

## callees

- `0x18000b654`
- `0x180023314`
- `0x18002392c`

## string_xrefs

- `0x180023337`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x18002337b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpGetHybridKeyConstituentKeyIndices(__int16 a1, _DWORD *a2, _DWORD *a3)
{
  int v6; // eax
  unsigned int v7; // ebx

  v6 = SslpValidateHybridGroup(a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    DebugTraceError((unsigned int)v6, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 191);
    return v7;
  }
  if ( a2 && a3 )
  {
    *a2 = a1 == 4588;
    *a3 = a1 != 4588;
    return v7;
  }
  DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 198);
  return 2148073511LL;
}

```

## disassembly

```asm
0x180023314  push    rbx
0x180023316  push    rbp
0x180023317  push    rsi
0x180023318  push    rdi
0x180023319  sub     rsp, 28h
0x18002331d  mov     rdi, r8
0x180023320  mov     rsi, rdx
0x180023323  movzx   ebp, cx
0x180023326  call    SslpValidateHybridGroup
0x18002332b  mov     ebx, eax
0x18002332d  test    eax, eax
0x18002332f  jns     short loc_180023350
0x180023331  mov     r9d, 0BFh
0x180023337  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002333e  lea     rdx, aStatus_0; "status"
0x180023345  mov     ecx, eax
0x180023347  call    DebugTraceError
0x18002334c  mov     eax, ebx
0x18002334e  jmp     short loc_180023398
0x180023350  test    rsi, rsi
0x180023353  jz      short loc_180023375
0x180023355  test    rdi, rdi
0x180023358  jz      short loc_180023375
0x18002335a  xor     eax, eax
0x18002335c  mov     ecx, 11ECh
0x180023361  cmp     bp, cx
0x180023364  setz    al
0x180023367  mov     [rsi], eax
0x180023369  xor     eax, eax
0x18002336b  cmp     bp, cx
0x18002336e  setnz   al
0x180023371  mov     [rdi], eax
0x180023373  jmp     short loc_18002334C
0x180023375  mov     r9d, 0C6h
0x18002337b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023382  lea     rdx, aStatus_0; "status"
0x180023389  mov     ecx, 80090027h
0x18002338e  call    DebugTraceError
0x180023393  mov     eax, 80090027h
0x180023398  add     rsp, 28h
0x18002339c  pop     rdi
0x18002339d  pop     rsi
0x18002339e  pop     rbp
0x18002339f  pop     rbx
0x1800233a0  retn
```
