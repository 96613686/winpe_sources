# SslpExportKemCipherText

- ea: `0x180021cbc`
- end: `0x180021d9f`
- name: `SslpExportKemCipherText`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021da8`

## callees

- `0x18000b654`
- `0x180021cbc`
- `0x180024fb0`

## string_xrefs

- `0x180021d26`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x180021d77`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpExportKemCipherText(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  int v5; // eax
  __int64 v7; // r9
  int v8; // edi

  if ( !a1 || !*(_QWORD *)(a1 + 32) || (v5 = *(_DWORD *)(a1 + 40)) == 0 || !a4 )
  {
    v7 = 303;
    goto LABEL_15;
  }
  if ( !a2 )
  {
    if ( !a3 )
    {
      *a4 = v5 + 12;
      return 0;
    }
    goto LABEL_10;
  }
  if ( !a3 )
  {
LABEL_10:
    v7 = 311;
LABEL_15:
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v7);
    return 2148073511LL;
  }
  v8 = v5 + 12;
  if ( a3 >= v5 + 12 )
  {
    *(_DWORD *)a2 = 1129008205;
    *(_WORD *)(a2 + 4) = *(_WORD *)(a1 + 44);
    *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 40);
    memmove((void *)(a2 + 12), *(const void **)(a1 + 32), *(unsigned int *)(a1 + 40));
    *a4 = v8;
    return 0;
  }
  *a4 = v8;
  DebugTraceError(2148073512LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", 326);
  return 2148073512LL;
}

```

## disassembly

```asm
0x180021cbc  mov     [rsp+arg_0], rbx
0x180021cc1  push    rdi
0x180021cc2  sub     rsp, 20h
0x180021cc6  mov     rbx, r9
0x180021cc9  mov     r9, rdx
0x180021ccc  mov     rdx, rcx
0x180021ccf  test    rcx, rcx
0x180021cd2  jz      loc_180021D71
0x180021cd8  cmp     qword ptr [rcx+20h], 0
0x180021cdd  jz      loc_180021D71
0x180021ce3  mov     eax, [rcx+28h]
0x180021ce6  test    eax, eax
0x180021ce8  jz      loc_180021D71
0x180021cee  test    rbx, rbx
0x180021cf1  jz      short loc_180021D71
0x180021cf3  test    r9, r9
0x180021cf6  jnz     short loc_180021D09
0x180021cf8  test    r8d, r8d
0x180021cfb  jnz     short loc_180021D0E
0x180021cfd  add     eax, 0Ch
0x180021d00  mov     [rbx], eax
0x180021d02  xor     eax, eax
0x180021d04  jmp     loc_180021D94
0x180021d09  test    r8d, r8d
0x180021d0c  jnz     short loc_180021D16
0x180021d0e  mov     r9d, 137h
0x180021d14  jmp     short loc_180021D77
0x180021d16  lea     edi, [rax+0Ch]
0x180021d19  cmp     r8d, edi
0x180021d1c  jnb     short loc_180021D45
0x180021d1e  mov     r9d, 146h
0x180021d24  mov     [rbx], edi
0x180021d26  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021d2d  mov     ecx, 80090028h
0x180021d32  lea     rdx, aStatus_0; "status"
0x180021d39  call    DebugTraceError
0x180021d3e  mov     eax, 80090028h
0x180021d43  jmp     short loc_180021D94
0x180021d45  mov     dword ptr [r9], 434B4C4Dh
0x180021d4c  movzx   eax, word ptr [rcx+2Ch]
0x180021d50  mov     [r9+4], ax
0x180021d55  mov     eax, [rcx+28h]
0x180021d58  mov     [r9+8], eax
0x180021d5c  mov     r8d, [rcx+28h]; Size
0x180021d60  lea     rcx, [r9+0Ch]; void *
0x180021d64  mov     rdx, [rdx+20h]; Src
0x180021d68  call    memmove
0x180021d6d  mov     [rbx], edi
0x180021d6f  jmp     short loc_180021D02
0x180021d71  mov     r9d, 12Fh
0x180021d77  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021d7e  mov     ecx, 80090027h
0x180021d83  lea     rdx, aStatus_0; "status"
0x180021d8a  call    DebugTraceError
0x180021d8f  mov     eax, 80090027h
0x180021d94  mov     rbx, [rsp+28h+arg_0]
0x180021d99  add     rsp, 20h
0x180021d9d  pop     rdi
0x180021d9e  retn
```
