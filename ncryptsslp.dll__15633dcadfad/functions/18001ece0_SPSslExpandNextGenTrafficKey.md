# SPSslExpandNextGenTrafficKey

- ea: `0x18001ece0`
- end: `0x18001eda6`
- name: `SPSslExpandNextGenTrafficKey`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800037a0`
- `0x1800068e0`
- `0x18000b654`
- `0x18000e7f0`
- `0x18001ece0`

## string_xrefs

- `0x18001ed8b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandNextGenTrafficKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r9
  BCRYPT_KEY_HANDLE **v6; // r8
  __int64 v7; // r10
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // eax

  SslpValidateKeyHandle(a2);
  if ( !SslpValidateProvHandle(v5) || !v7 || !*(_QWORD *)(v7 + 32) )
  {
    v8 = -2146893786;
    v9 = 7026;
    v10 = 2148073510LL;
    goto LABEL_12;
  }
  if ( *(_DWORD *)(v7 + 8) != 772 || *(_DWORD *)(v7 + 108) != 4 )
  {
    v8 = -2146893783;
    v9 = 7034;
    v10 = 2148073513LL;
    goto LABEL_12;
  }
  if ( a5 )
  {
    v8 = -2146893815;
    v9 = 7041;
    v10 = 2148073481LL;
LABEL_12:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v9);
    return v8;
  }
  v11 = TlsDeriveSecret(v7, "traffic upd", 0, 0, 4, v6);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = 7060;
    v10 = (unsigned int)v11;
    goto LABEL_12;
  }
  return v8;
}

```

## disassembly

```asm
0x18001ece0  push    rbx
0x18001ece2  sub     rsp, 30h
0x18001ece6  mov     r9, rcx
0x18001ece9  mov     rcx, rdx
0x18001ecec  call    SslpValidateKeyHandle
0x18001ecf1  mov     rcx, r9
0x18001ecf4  mov     r10, rax
0x18001ecf7  call    SslpValidateProvHandle
0x18001ecfc  test    rax, rax
0x18001ecff  jz      short loc_18001ED7B
0x18001ed01  test    r10, r10
0x18001ed04  jz      short loc_18001ED7B
0x18001ed06  cmp     qword ptr [r10+20h], 0
0x18001ed0b  jz      short loc_18001ED7B
0x18001ed0d  cmp     dword ptr [r10+8], 304h
0x18001ed15  jnz     short loc_18001ED69
0x18001ed17  cmp     dword ptr [r10+6Ch], 4
0x18001ed1c  jnz     short loc_18001ED69
0x18001ed1e  cmp     [rsp+38h+arg_20], 0
0x18001ed23  jz      short loc_18001ED37
0x18001ed25  mov     ebx, 80090009h
0x18001ed2a  mov     r9d, 1B81h
0x18001ed30  mov     ecx, 80090009h
0x18001ed35  jmp     short loc_18001ED8B
0x18001ed37  mov     [rsp+38h+var_10], r8
0x18001ed3c  lea     rdx, aTrafficUpd; "traffic upd"
0x18001ed43  xor     r8d, r8d
0x18001ed46  mov     [rsp+38h+var_18], 4
0x18001ed4e  xor     r9d, r9d
0x18001ed51  mov     rcx, r10
0x18001ed54  call    TlsDeriveSecret
0x18001ed59  mov     ebx, eax
0x18001ed5b  test    eax, eax
0x18001ed5d  jns     short loc_18001ED9E
0x18001ed5f  mov     r9d, 1B94h
0x18001ed65  mov     ecx, eax
0x18001ed67  jmp     short loc_18001ED8B
0x18001ed69  mov     ebx, 80090029h
0x18001ed6e  mov     r9d, 1B7Ah
0x18001ed74  mov     ecx, 80090029h
0x18001ed79  jmp     short loc_18001ED8B
0x18001ed7b  mov     ebx, 80090026h
0x18001ed80  mov     r9d, 1B72h
0x18001ed86  mov     ecx, 80090026h
0x18001ed8b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ed92  lea     rdx, aStatus; "Status"
0x18001ed99  call    DebugTraceError
0x18001ed9e  mov     eax, ebx
0x18001eda0  add     rsp, 30h
0x18001eda4  pop     rbx
0x18001eda5  retn
```
