# SslEnumGroups

- ea: `0x18001add0`
- end: `0x18001aee7`
- name: `SslEnumGroups`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009ea0`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001add0`
- `0x180020010`

## string_xrefs

- `0x18001ade6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001ae25`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001ae58`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001ae99`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001aec4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslEnumGroups(__int64 a1, __int64 a2, __int64 a3, __int64 a4, DWORD a5)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // r9d
  int v10; // eax
  unsigned int v11; // ebx
  NCRYPT_KEY_HANDLE *v12; // rdx
  NCryptKeyName **v13; // r8
  PVOID *v14; // r9

  v5 = ValidateSslProvHandle();
  if ( v5 )
  {
    if ( v6 && v7 )
    {
      if ( v8 )
      {
        DebugTraceError(
          2148073481LL,
          "NTE_BAD_FLAGS",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          5259);
        return -2146893815;
      }
      else if ( *(_WORD *)(v5 + 32) >= 8u )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(v5 + 416))(*(_QWORD *)(v5 + 424), v6, v7, 0);
        v11 = v10;
        if ( v10 >= 0 )
        {
          return 0;
        }
        else
        {
          DebugTraceError(
            (unsigned int)v10,
            "status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            5277);
          return NormalizeNteStatus(v11, v12, v13, v14, a5);
        }
      }
      else
      {
        DebugTraceError(
          2148073513LL,
          "NTE_NOT_SUPPORTED",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          5266);
        return -2146893783;
      }
    }
    else
    {
      DebugTraceError(
        2148073511LL,
        "NTE_INVALID_PARAMETER",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        5253);
      return -2146893785;
    }
  }
  else
  {
    DebugTraceError(
      2148073510LL,
      "NTE_INVALID_HANDLE",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      5247);
    return -2146893786;
  }
}

```

## disassembly

```asm
0x18001add0  push    rbx
0x18001add2  sub     rsp, 30h
0x18001add6  call    ValidateSslProvHandle
0x18001addb  test    rax, rax
0x18001adde  jnz     short loc_18001AE08
0x18001ade0  mov     r9d, 147Fh
0x18001ade6  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001aded  lea     rdx, aNteInvalidHand; "NTE_INVALID_HANDLE"
0x18001adf4  mov     ecx, 80090026h
0x18001adf9  call    DebugTraceError
0x18001adfe  mov     eax, 80090026h
0x18001ae03  jmp     loc_18001AEE1
0x18001ae08  test    rdx, rdx
0x18001ae0b  jz      loc_18001AEBE
0x18001ae11  test    r8, r8
0x18001ae14  jz      loc_18001AEBE
0x18001ae1a  test    r9d, r9d
0x18001ae1d  jz      short loc_18001AE47
0x18001ae1f  mov     r9d, 148Bh
0x18001ae25  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ae2c  lea     rdx, aNteBadFlags; "NTE_BAD_FLAGS"
0x18001ae33  mov     ecx, 80090009h
0x18001ae38  call    DebugTraceError
0x18001ae3d  mov     eax, 80090009h
0x18001ae42  jmp     loc_18001AEE1
0x18001ae47  mov     ecx, 8
0x18001ae4c  cmp     cx, [rax+20h]
0x18001ae50  jbe     short loc_18001AE77
0x18001ae52  mov     r9d, 1492h
0x18001ae58  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ae5f  lea     rdx, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x18001ae66  mov     ecx, 80090029h
0x18001ae6b  call    DebugTraceError
0x18001ae70  mov     eax, 80090029h
0x18001ae75  jmp     short loc_18001AEE1
0x18001ae77  mov     rcx, [rax+1A8h]
0x18001ae7e  xor     r9d, r9d
0x18001ae81  mov     rax, [rax+1A0h]
0x18001ae88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae8d  mov     ebx, eax
0x18001ae8f  test    eax, eax
0x18001ae91  jns     short loc_18001AEBA
0x18001ae93  mov     r9d, 149Dh
0x18001ae99  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001aea0  lea     rdx, aStatus_0; "status"
0x18001aea7  mov     ecx, eax
0x18001aea9  call    DebugTraceError
0x18001aeae  mov     ecx, ebx
0x18001aeb0  add     rsp, 30h
0x18001aeb4  pop     rbx
0x18001aeb5  jmp     NormalizeNteStatus
0x18001aeba  xor     eax, eax
0x18001aebc  jmp     short loc_18001AEE1
0x18001aebe  mov     r9d, 1485h
0x18001aec4  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001aecb  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18001aed2  mov     ecx, 80090027h
0x18001aed7  call    DebugTraceError
0x18001aedc  mov     eax, 80090027h
0x18001aee1  add     rsp, 30h
0x18001aee5  pop     rbx
0x18001aee6  retn
```
