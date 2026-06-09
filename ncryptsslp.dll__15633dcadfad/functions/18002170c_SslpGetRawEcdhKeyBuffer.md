# SslpGetRawEcdhKeyBuffer

- ea: `0x18002170c`
- end: `0x180021770`
- name: `SslpGetRawEcdhKeyBuffer`
- size: `100`
- prototype: `__int64 __fastcall(__int64, unsigned int, char, _QWORD *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800229a4`

## callees

- `0x18000b654`
- `0x18002170c`

## string_xrefs

- `0x18002174e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
__int64 __fastcall SslpGetRawEcdhKeyBuffer(__int64 a1, unsigned int a2, char a3, _QWORD *a4, int *a5)
{
  int v6; // ecx

  if ( a1 && a2 >= 8 && a4 && a5 )
  {
    v6 = *(_DWORD *)(a1 + 4);
    if ( a3 )
      v6 = 2 * v6 + 1;
    *a5 = v6;
    *a4 = a1 + 8;
    return 0;
  }
  else
  {
    DebugTraceError(
      2148073511LL,
      "NTE_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
      357);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x18002170c  sub     rsp, 28h
0x180021710  mov     rax, rcx
0x180021713  test    rcx, rcx
0x180021716  jz      short loc_180021748
0x180021718  cmp     edx, 8
0x18002171b  jb      short loc_180021748
0x18002171d  test    r9, r9
0x180021720  jz      short loc_180021748
0x180021722  mov     rdx, [rsp+28h+arg_20]
0x180021727  test    rdx, rdx
0x18002172a  jz      short loc_180021748
0x18002172c  mov     ecx, [rcx+4]
0x18002172f  test    r8b, r8b
0x180021732  jz      short loc_18002173B
0x180021734  lea     ecx, ds:1[rcx*2]
0x18002173b  add     rax, 8
0x18002173f  mov     [rdx], ecx
0x180021741  mov     [r9], rax
0x180021744  xor     eax, eax
0x180021746  jmp     short loc_18002176B
0x180021748  mov     r9d, 165h
0x18002174e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021755  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18002175c  mov     ecx, 80090027h
0x180021761  call    DebugTraceError
0x180021766  mov     eax, 80090027h
0x18002176b  add     rsp, 28h
0x18002176f  retn
```
