# SPSslEnumCipherSuitesEx

- ea: `0x180012b30`
- end: `0x180012c61`
- name: `SPSslEnumCipherSuitesEx`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x180006904`
- `0x18000b594`
- `0x18000b654`
- `0x1800121f0`
- `0x180012b30`

## string_xrefs

- `0x180012baa`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180012bf6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180012c49`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslEnumCipherSuitesEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 *v7; // r8
  _QWORD *v8; // r9
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx

  if ( SslpValidateProvHandle(a1) )
  {
    LODWORD(v9) = 0;
    if ( v5 )
    {
      v9 = SslpValidateKeyPairHandle(v5);
      if ( !v9 )
      {
        v11 = -2146893786;
        v13 = 2062;
        v14 = 2148073510LL;
LABEL_20:
        DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v13);
        return v11;
      }
    }
    if ( !v7 || !v8 )
    {
      v11 = -2146893785;
      v13 = 2070;
      v14 = 2148073511LL;
      goto LABEL_20;
    }
    if ( a5 )
    {
      v11 = -2146893815;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          29);
    }
    else
    {
      v10 = SslpEnumCipherSuitesEx(v6, v9, v7, v8);
      v11 = v10;
      if ( v10 < 0 )
      {
        v13 = 2094;
        v14 = (unsigned int)v10;
        goto LABEL_20;
      }
      return 0;
    }
  }
  else
  {
    v11 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        3);
  }
  return v11;
}

```

## disassembly

```asm
0x180012b30  push    rbx
0x180012b32  sub     rsp, 40h
0x180012b36  call    SslpValidateProvHandle
0x180012b3b  test    rax, rax
0x180012b3e  jz      loc_180012BD0
0x180012b44  xor     eax, eax
0x180012b46  test    rdx, rdx
0x180012b49  jnz     loc_180012C0C
0x180012b4f  test    r8, r8
0x180012b52  jz      loc_180012C39
0x180012b58  test    r9, r9
0x180012b5b  jz      loc_180012C39
0x180012b61  cmp     [rsp+48h+arg_20], 0
0x180012b66  jnz     short loc_180012B84
0x180012b68  mov     rdx, rax
0x180012b6b  call    SslpEnumCipherSuitesEx
0x180012b70  mov     ebx, eax
0x180012b72  test    eax, eax
0x180012b74  js      loc_180012C2F
0x180012b7a  xor     ebx, ebx
0x180012b7c  mov     eax, ebx
0x180012b7e  add     rsp, 40h
0x180012b82  pop     rbx
0x180012b83  retn
0x180012b84  mov     ebx, 80090009h
0x180012b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b90  lea     rax, WPP_GLOBAL_Control
0x180012b97  cmp     rcx, rax
0x180012b9a  jz      short loc_180012B7C
0x180012b9c  test    byte ptr [rcx+1Ch], 1
0x180012ba0  jz      short loc_180012B7C
0x180012ba2  mov     [rsp+48h+var_18], 81Dh
0x180012baa  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012bb1  mov     [rsp+48h+var_20], r8
0x180012bb6  mov     [rsp+48h+var_28], 80090009h
0x180012bbe  mov     rcx, [rcx+10h]
0x180012bc2  lea     r9, aStatus; "Status"
0x180012bc9  call    WPP_SF_sDsd
0x180012bce  jmp     short loc_180012B7C
0x180012bd0  mov     ebx, 80090026h
0x180012bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bdc  lea     rax, WPP_GLOBAL_Control
0x180012be3  cmp     rcx, rax
0x180012be6  jz      short loc_180012B7C
0x180012be8  test    byte ptr [rcx+1Ch], 1
0x180012bec  jz      short loc_180012B7C
0x180012bee  mov     [rsp+48h+var_18], 803h
0x180012bf6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012bfd  mov     [rsp+48h+var_20], r8
0x180012c02  mov     [rsp+48h+var_28], 80090026h
0x180012c0a  jmp     short loc_180012BBE
0x180012c0c  mov     rcx, rdx
0x180012c0f  call    SslpValidateKeyPairHandle
0x180012c14  test    rax, rax
0x180012c17  jnz     loc_180012B4F
0x180012c1d  mov     ebx, 80090026h
0x180012c22  mov     r9d, 80Eh
0x180012c28  mov     ecx, 80090026h
0x180012c2d  jmp     short loc_180012C49
0x180012c2f  mov     r9d, 82Eh
0x180012c35  mov     ecx, eax
0x180012c37  jmp     short loc_180012C49
0x180012c39  mov     ebx, 80090027h
0x180012c3e  mov     r9d, 816h
0x180012c44  mov     ecx, 80090027h
0x180012c49  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012c50  lea     rdx, aStatus; "Status"
0x180012c57  call    DebugTraceError
0x180012c5c  jmp     loc_180012B7C
```
