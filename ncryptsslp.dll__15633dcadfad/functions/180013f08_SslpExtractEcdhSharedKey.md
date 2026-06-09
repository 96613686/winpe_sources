# SslpExtractEcdhSharedKey

- ea: `0x180013f08`
- end: `0x18001401d`
- name: `SslpExtractEcdhSharedKey`
- size: `277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dea0`
- `0x180022fa8`

## callees

- `0x180001fd0`
- `0x180003ef0`
- `0x1800066f0`
- `0x18000b594`
- `0x18000b654`
- `0x180013f08`

## string_xrefs

- `0x180013f8e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x180013fcf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
__int64 __fastcall SslpExtractEcdhSharedKey(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  BYTE *v10; // rbx
  int v11; // edx
  int v12; // edi
  __int64 v13; // rax
  BYTE *v14; // rcx
  DWORD v16; // [rsp+40h] [rbp-38h] BYREF
  BYTE *v17; // [rsp+48h] [rbp-30h] BYREF

  SslpValidateEphemeralHandle(a1);
  v7 = SslpValidateEphemeralHandle(v6);
  v10 = 0;
  v17 = 0;
  v16 = 0;
  if ( v8 && v7 && a3 && v9 )
  {
    v12 = TlsSecretAgreement(*(_QWORD *)(v8 + 24), *(_QWORD *)(v7 + 24), v8, &v17, &v16);
    if ( v12 >= 0 )
    {
      *a3 = v17;
      *a4 = v16;
      return (unsigned int)v12;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        (unsigned int)"status",
        v12,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        75);
    v10 = v17;
  }
  else
  {
    v12 = -2146893785;
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c", 571);
  }
  if ( v10 )
  {
    v13 = v16;
    v14 = v10;
    if ( v16 )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    MSCryptFree(v10);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013f08  push    rbx
0x180013f0a  push    rsi
0x180013f0b  push    rdi
0x180013f0c  push    r14
0x180013f0e  sub     rsp, 58h
0x180013f12  mov     rsi, r9
0x180013f15  mov     r14, r8
0x180013f18  call    SslpValidateEphemeralHandle
0x180013f1d  mov     rcx, rdx
0x180013f20  mov     r8, rax
0x180013f23  call    SslpValidateEphemeralHandle
0x180013f28  xor     ebx, ebx
0x180013f2a  mov     [rsp+78h+var_30], rbx
0x180013f2f  mov     [rsp+78h+var_38], ebx
0x180013f33  test    r8, r8
0x180013f36  jz      loc_180013FC9
0x180013f3c  test    rax, rax
0x180013f3f  jz      loc_180013FC9
0x180013f45  test    r14, r14
0x180013f48  jz      short loc_180013FC9
0x180013f4a  test    r9, r9
0x180013f4d  jz      short loc_180013FC9
0x180013f4f  mov     rdx, [rax+18h]
0x180013f53  lea     rcx, [rsp+78h+var_38]
0x180013f58  mov     [rsp+78h+var_58], rcx
0x180013f5d  lea     r9, [rsp+78h+var_30]
0x180013f62  mov     rcx, [r8+18h]
0x180013f66  call    TlsSecretAgreement
0x180013f6b  mov     edi, eax
0x180013f6d  test    eax, eax
0x180013f6f  jns     short loc_180013FB9
0x180013f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f78  lea     rax, WPP_GLOBAL_Control
0x180013f7f  cmp     rcx, rax
0x180013f82  jz      short loc_180013FB2
0x180013f84  test    byte ptr [rcx+1Ch], 1
0x180013f88  jz      short loc_180013FB2
0x180013f8a  mov     rcx, [rcx+10h]
0x180013f8e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013f95  mov     [rsp+78h+var_48], 24Bh
0x180013f9d  lea     r9, aStatus_0; "status"
0x180013fa4  mov     [rsp+78h+var_50], r8
0x180013fa9  mov     dword ptr [rsp+78h+var_58], edi
0x180013fad  call    WPP_SF_sDsd
0x180013fb2  mov     rbx, [rsp+78h+var_30]
0x180013fb7  jmp     short loc_180013FEC
0x180013fb9  mov     rax, [rsp+78h+var_30]
0x180013fbe  mov     [r14], rax
0x180013fc1  mov     eax, [rsp+78h+var_38]
0x180013fc5  mov     [rsi], eax
0x180013fc7  jmp     short loc_180014011
0x180013fc9  mov     r9d, 23Bh
0x180013fcf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013fd6  lea     rdx, aStatus_0; "status"
0x180013fdd  mov     ecx, 80090027h
0x180013fe2  mov     edi, 80090027h
0x180013fe7  call    DebugTraceError
0x180013fec  test    rbx, rbx
0x180013fef  jz      short loc_180014011
0x180013ff1  mov     eax, [rsp+78h+var_38]
0x180013ff5  mov     rcx, rbx
0x180013ff8  test    rax, rax
0x180013ffb  jz      short loc_180014009
0x180013ffd  mov     byte ptr [rcx], 0
0x180014000  inc     rcx
0x180014003  sub     rax, 1
0x180014007  jnz     short loc_180013FFD
0x180014009  mov     rcx, rbx
0x18001400c  call    MSCryptFree
0x180014011  mov     eax, edi
0x180014013  add     rsp, 58h
0x180014017  pop     r14
0x180014019  pop     rdi
0x18001401a  pop     rsi
0x18001401b  pop     rbx
0x18001401c  retn
```
