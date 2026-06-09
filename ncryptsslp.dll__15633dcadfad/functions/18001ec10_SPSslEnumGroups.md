# SPSslEnumGroups

- ea: `0x18001ec10`
- end: `0x18001ecd6`
- name: `SPSslEnumGroups`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001e0dc`
- `0x18001ec10`

## string_xrefs

- `0x18001ec26`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001ec5d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001ec90`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001ecb3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslEnumGroups(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // r9d
  int v6; // eax
  unsigned int v7; // ebx

  v1 = SslpValidateProvHandle(a1);
  if ( v1 )
  {
    if ( v2 && v3 )
    {
      if ( v4 )
      {
        DebugTraceError(
          2148073481LL,
          "NTE_BAD_FLAGS",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          7484);
        return 2148073481LL;
      }
      else
      {
        v6 = SslpEnumGroups(v1);
        v7 = v6;
        if ( v6 >= 0 )
        {
          return 0;
        }
        else
        {
          DebugTraceError(
            (unsigned int)v6,
            "status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            7494);
          return v7;
        }
      }
    }
    else
    {
      DebugTraceError(
        2148073511LL,
        "NTE_INVALID_PARAMETER",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        7478);
      return 2148073511LL;
    }
  }
  else
  {
    DebugTraceError(
      2148073510LL,
      "NTE_INVALID_HANDLE",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      7471);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x18001ec10  push    rbx
0x18001ec12  sub     rsp, 20h
0x18001ec16  call    SslpValidateProvHandle
0x18001ec1b  test    rax, rax
0x18001ec1e  jnz     short loc_18001EC48
0x18001ec20  mov     r9d, 1D2Fh
0x18001ec26  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ec2d  lea     rdx, aNteInvalidHand; "NTE_INVALID_HANDLE"
0x18001ec34  mov     ecx, 80090026h
0x18001ec39  call    DebugTraceError
0x18001ec3e  mov     eax, 80090026h
0x18001ec43  jmp     loc_18001ECD0
0x18001ec48  test    rdx, rdx
0x18001ec4b  jz      short loc_18001ECAD
0x18001ec4d  test    r8, r8
0x18001ec50  jz      short loc_18001ECAD
0x18001ec52  test    r9d, r9d
0x18001ec55  jz      short loc_18001EC7C
0x18001ec57  mov     r9d, 1D3Ch
0x18001ec5d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ec64  lea     rdx, aNteBadFlags; "NTE_BAD_FLAGS"
0x18001ec6b  mov     ecx, 80090009h
0x18001ec70  call    DebugTraceError
0x18001ec75  mov     eax, 80090009h
0x18001ec7a  jmp     short loc_18001ECD0
0x18001ec7c  mov     rcx, rax
0x18001ec7f  call    SslpEnumGroups
0x18001ec84  mov     ebx, eax
0x18001ec86  test    eax, eax
0x18001ec88  jns     short loc_18001ECA9
0x18001ec8a  mov     r9d, 1D46h
0x18001ec90  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ec97  lea     rdx, aStatus_0; "status"
0x18001ec9e  mov     ecx, eax
0x18001eca0  call    DebugTraceError
0x18001eca5  mov     eax, ebx
0x18001eca7  jmp     short loc_18001ECD0
0x18001eca9  xor     eax, eax
0x18001ecab  jmp     short loc_18001ECD0
0x18001ecad  mov     r9d, 1D36h
0x18001ecb3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ecba  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18001ecc1  mov     ecx, 80090027h
0x18001ecc6  call    DebugTraceError
0x18001eccb  mov     eax, 80090027h
0x18001ecd0  add     rsp, 20h
0x18001ecd4  pop     rbx
0x18001ecd5  retn
```
