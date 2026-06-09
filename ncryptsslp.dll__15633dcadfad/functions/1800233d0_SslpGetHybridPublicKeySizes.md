# SslpGetHybridPublicKeySizes

- ea: `0x1800233d0`
- end: `0x1800234a9`
- name: `SslpGetHybridPublicKeySizes`
- size: `217`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _DWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014024`
- `0x1800229a4`

## callees

- `0x18000b654`
- `0x1800185e0`
- `0x1800233a8`
- `0x1800233d0`

## string_xrefs

- `0x18002345b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023480`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpGetHybridPublicKeySizes(__int64 a1, const wchar_t *a2, _DWORD *a3, _DWORD *a4)
{
  __int64 HybridKeyGroup; // rdi
  __int64 v8; // r9
  char v9; // bl

  if ( a2 && a3 && a4 )
  {
    HybridKeyGroup = SslpGetHybridKeyGroup(a1);
    if ( HybridKeyGroup )
    {
      if ( !wcscmp(a2, L"MLKEMPUBLICBLOB") )
      {
        v9 = 1;
      }
      else
      {
        v9 = 0;
        if ( wcscmp(a2, L"TLS_KEM_CIPHERTEXT") )
        {
          DebugTraceError(
            2148073513LL,
            "NTE_NOT_SUPPORTED",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
            167);
          return 2148073513LL;
        }
      }
      *a3 = *(_DWORD *)(HybridKeyGroup + 12);
      *a4 = *(_DWORD *)((-(__int64)(v9 != 0) & 0xFFFFFFFFFFFFFFF4uLL) + HybridKeyGroup + 56);
      return 0;
    }
    v8 = 156;
  }
  else
  {
    v8 = 149;
  }
  DebugTraceError(
    2148073511LL,
    "NTE_INVALID_PARAMETER",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
    v8);
  return 2148073511LL;
}

```

## disassembly

```asm
0x1800233d0  push    rbx
0x1800233d2  push    rsi
0x1800233d3  push    rdi
0x1800233d4  push    r14
0x1800233d6  push    r15
0x1800233d8  sub     rsp, 20h
0x1800233dc  mov     r14, r9
0x1800233df  mov     r15, r8
0x1800233e2  mov     rsi, rdx
0x1800233e5  test    rdx, rdx
0x1800233e8  jz      loc_18002347A
0x1800233ee  test    r8, r8
0x1800233f1  jz      loc_18002347A
0x1800233f7  test    r9, r9
0x1800233fa  jz      short loc_18002347A
0x1800233fc  call    SslpGetHybridKeyGroup
0x180023401  mov     rdi, rax
0x180023404  test    rax, rax
0x180023407  jnz     short loc_180023411
0x180023409  mov     r9d, 9Ch
0x18002340f  jmp     short loc_180023480
0x180023411  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180023418  mov     rcx, rsi; String1
0x18002341b  call    wcscmp
0x180023420  test    eax, eax
0x180023422  jnz     short loc_180023440
0x180023424  mov     bl, 1
0x180023426  mov     eax, [rdi+0Ch]
0x180023429  neg     bl
0x18002342b  mov     [r15], eax
0x18002342e  sbb     rax, rax
0x180023431  and     rax, 0FFFFFFFFFFFFFFF4h
0x180023435  mov     eax, [rax+rdi+38h]
0x180023439  mov     [r14], eax
0x18002343c  xor     eax, eax
0x18002343e  jmp     short loc_18002349D
0x180023440  lea     rdx, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x180023447  mov     rcx, rsi; String1
0x18002344a  xor     bl, bl
0x18002344c  call    wcscmp
0x180023451  test    eax, eax
0x180023453  jz      short loc_180023426
0x180023455  mov     r9d, 0A7h
0x18002345b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023462  lea     rdx, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x180023469  mov     ecx, 80090029h
0x18002346e  call    DebugTraceError
0x180023473  mov     eax, 80090029h
0x180023478  jmp     short loc_18002349D
0x18002347a  mov     r9d, 95h
0x180023480  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023487  mov     ecx, 80090027h
0x18002348c  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180023493  call    DebugTraceError
0x180023498  mov     eax, 80090027h
0x18002349d  add     rsp, 20h
0x1800234a1  pop     r15
0x1800234a3  pop     r14
0x1800234a5  pop     rdi
0x1800234a6  pop     rsi
0x1800234a7  pop     rbx
0x1800234a8  retn
```
