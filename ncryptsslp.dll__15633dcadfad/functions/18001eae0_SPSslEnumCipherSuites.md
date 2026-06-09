# SPSslEnumCipherSuites

- ea: `0x18001eae0`
- end: `0x18001eb88`
- name: `SPSslEnumCipherSuites`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x1800121f0`
- `0x18001de24`
- `0x18001eae0`

## string_xrefs

- `0x18001eb6d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslEnumCipherSuites(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 *v7; // r8
  _QWORD *v8; // r9
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // eax

  if ( !SslpValidateProvHandle(a1) )
  {
    v9 = 1965;
LABEL_3:
    v10 = -2146893786;
    v11 = 2148073510LL;
LABEL_15:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v9);
    return v10;
  }
  LODWORD(v12) = 0;
  if ( v5 )
  {
    v12 = SslpValidateKeyPairHandle(v5);
    if ( !v12 )
    {
      v9 = 1976;
      goto LABEL_3;
    }
  }
  if ( !v7 || !v8 )
  {
    v10 = -2146893785;
    v9 = 1984;
    v11 = 2148073511LL;
    goto LABEL_15;
  }
  if ( a5 )
  {
    v10 = -2146893815;
    v9 = 1991;
    v11 = 2148073481LL;
    goto LABEL_15;
  }
  v13 = SslpEnumCipherSuites(v6, v12, v7, v8);
  v10 = v13;
  if ( v13 < 0 )
  {
    v9 = 2008;
    v11 = (unsigned int)v13;
    goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x18001eae0  push    rbx
0x18001eae2  sub     rsp, 20h
0x18001eae6  call    SslpValidateProvHandle
0x18001eaeb  test    rax, rax
0x18001eaee  jnz     short loc_18001EB02
0x18001eaf0  mov     r9d, 7ADh
0x18001eaf6  mov     ebx, 80090026h
0x18001eafb  mov     ecx, 80090026h
0x18001eb00  jmp     short loc_18001EB6D
0x18001eb02  xor     eax, eax
0x18001eb04  test    rdx, rdx
0x18001eb07  jz      short loc_18001EB1E
0x18001eb09  mov     rcx, rdx
0x18001eb0c  call    SslpValidateKeyPairHandle
0x18001eb11  test    rax, rax
0x18001eb14  jnz     short loc_18001EB1E
0x18001eb16  mov     r9d, 7B8h
0x18001eb1c  jmp     short loc_18001EAF6
0x18001eb1e  test    r8, r8
0x18001eb21  jz      short loc_18001EB5D
0x18001eb23  test    r9, r9
0x18001eb26  jz      short loc_18001EB5D
0x18001eb28  cmp     [rsp+28h+arg_20], 0
0x18001eb2d  jz      short loc_18001EB41
0x18001eb2f  mov     ebx, 80090009h
0x18001eb34  mov     r9d, 7C7h
0x18001eb3a  mov     ecx, 80090009h
0x18001eb3f  jmp     short loc_18001EB6D
0x18001eb41  mov     rdx, rax
0x18001eb44  call    SslpEnumCipherSuites
0x18001eb49  mov     ebx, eax
0x18001eb4b  test    eax, eax
0x18001eb4d  jns     short loc_18001EB59
0x18001eb4f  mov     r9d, 7D8h
0x18001eb55  mov     ecx, eax
0x18001eb57  jmp     short loc_18001EB6D
0x18001eb59  xor     ebx, ebx
0x18001eb5b  jmp     short loc_18001EB80
0x18001eb5d  mov     ebx, 80090027h
0x18001eb62  mov     r9d, 7C0h
0x18001eb68  mov     ecx, 80090027h
0x18001eb6d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001eb74  lea     rdx, aStatus; "Status"
0x18001eb7b  call    DebugTraceError
0x18001eb80  mov     eax, ebx
0x18001eb82  add     rsp, 20h
0x18001eb86  pop     rbx
0x18001eb87  retn
```
