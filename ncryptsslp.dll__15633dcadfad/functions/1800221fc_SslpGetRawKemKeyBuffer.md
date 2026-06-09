# SslpGetRawKemKeyBuffer

- ea: `0x1800221fc`
- end: `0x1800222e9`
- name: `SslpGetRawKemKeyBuffer`
- size: `237`
- prototype: `__int64 __fastcall(__int64, unsigned int, const wchar_t *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800229a4`

## callees

- `0x18000b654`
- `0x1800185e0`
- `0x1800221fc`

## string_xrefs

- `0x18002229c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x1800222c1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpGetRawKemKeyBuffer(__int64 a1, unsigned int a2, const wchar_t *a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v9; // r9
  __int64 v10; // rax
  int v11; // ecx
  __int64 result; // rax

  if ( !a1 || !a3 || !a4 || !a5 )
  {
    v9 = 356;
    goto LABEL_16;
  }
  if ( wcscmp(a3, L"MLKEMPUBLICBLOB") )
  {
    if ( wcscmp(a3, L"TLS_KEM_CIPHERTEXT") )
    {
      DebugTraceError(
        2148073513LL,
        "NTE_NOT_SUPPORTED",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c",
        390);
      return 2148073513LL;
    }
    if ( a2 < 0xC )
    {
      v9 = 380;
      goto LABEL_16;
    }
    v10 = a1;
LABEL_13:
    v11 = *(_DWORD *)(a1 + 8);
    *a4 = v10 + 12;
    result = 0;
    *a5 = v11;
    return result;
  }
  if ( a2 >= 0xC )
  {
    v10 = a1 + *(unsigned int *)(a1 + 4);
    goto LABEL_13;
  }
  v9 = 366;
LABEL_16:
  DebugTraceError(
    2148073511LL,
    "NTE_INVALID_PARAMETER",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c",
    v9);
  return 2148073511LL;
}

```

## disassembly

```asm
0x1800221fc  push    rbx
0x1800221fe  push    rbp
0x1800221ff  push    rsi
0x180022200  push    rdi
0x180022201  push    r14
0x180022203  sub     rsp, 20h
0x180022207  mov     r14, r9
0x18002220a  mov     rdi, r8
0x18002220d  mov     ebp, edx
0x18002220f  mov     rbx, rcx
0x180022212  test    rcx, rcx
0x180022215  jz      loc_1800222BB
0x18002221b  test    r8, r8
0x18002221e  jz      loc_1800222BB
0x180022224  test    r9, r9
0x180022227  jz      loc_1800222BB
0x18002222d  mov     rsi, [rsp+48h+arg_20]
0x180022232  test    rsi, rsi
0x180022235  jz      loc_1800222BB
0x18002223b  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180022242  mov     rcx, r8; String1
0x180022245  call    wcscmp
0x18002224a  test    eax, eax
0x18002224c  jnz     short loc_180022263
0x18002224e  cmp     ebp, 0Ch
0x180022251  jnb     short loc_18002225B
0x180022253  mov     r9d, 16Eh
0x180022259  jmp     short loc_1800222C1
0x18002225b  mov     eax, [rbx+4]
0x18002225e  add     rax, rbx
0x180022261  jmp     short loc_180022286
0x180022263  lea     rdx, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x18002226a  mov     rcx, rdi; String1
0x18002226d  call    wcscmp
0x180022272  test    eax, eax
0x180022274  jnz     short loc_180022296
0x180022276  cmp     ebp, 0Ch
0x180022279  jnb     short loc_180022283
0x18002227b  mov     r9d, 17Ch
0x180022281  jmp     short loc_1800222C1
0x180022283  mov     rax, rbx
0x180022286  mov     ecx, [rbx+8]
0x180022289  add     rax, 0Ch
0x18002228d  mov     [r14], rax
0x180022290  xor     eax, eax
0x180022292  mov     [rsi], ecx
0x180022294  jmp     short loc_1800222DE
0x180022296  mov     r9d, 186h
0x18002229c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800222a3  lea     rdx, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x1800222aa  mov     ecx, 80090029h
0x1800222af  call    DebugTraceError
0x1800222b4  mov     eax, 80090029h
0x1800222b9  jmp     short loc_1800222DE
0x1800222bb  mov     r9d, 164h
0x1800222c1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800222c8  mov     ecx, 80090027h
0x1800222cd  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x1800222d4  call    DebugTraceError
0x1800222d9  mov     eax, 80090027h
0x1800222de  add     rsp, 20h
0x1800222e2  pop     r14
0x1800222e4  pop     rdi
0x1800222e5  pop     rsi
0x1800222e6  pop     rbp
0x1800222e7  pop     rbx
0x1800222e8  retn
```
