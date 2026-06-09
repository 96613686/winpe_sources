# SPSslGetSessionTicketProtectionHeaderSize

- ea: `0x18001f230`
- end: `0x18001f2b0`
- name: `SPSslGetSessionTicketProtectionHeaderSize`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001f230`

## string_xrefs

- `0x18001f250`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGetSessionTicketProtectionHeaderSize(__int64 a1)
{
  int v1; // edx
  _DWORD *v2; // r8
  int v3; // r9d
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rcx

  if ( !SslpValidateProvHandle(a1) )
  {
    v4 = -2146893786;
    v5 = 7208;
    v6 = 2148073510LL;
    goto LABEL_3;
  }
  if ( !v2 )
  {
    v5 = 7216;
LABEL_6:
    v4 = -2146893785;
    v6 = 2148073511LL;
    goto LABEL_3;
  }
  if ( v1 )
  {
    v5 = 7224;
    goto LABEL_6;
  }
  if ( !v3 )
  {
    v4 = 0;
    *v2 = 68;
    return v4;
  }
  v4 = -2146893815;
  v5 = 7231;
  v6 = 2148073481LL;
LABEL_3:
  DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v5);
  return v4;
}

```

## disassembly

```asm
0x18001f230  push    rbx
0x18001f232  sub     rsp, 20h
0x18001f236  call    SslpValidateProvHandle
0x18001f23b  test    rax, rax
0x18001f23e  jnz     short loc_18001F265
0x18001f240  mov     ebx, 80090026h
0x18001f245  mov     r9d, 1C28h
0x18001f24b  mov     ecx, 80090026h
0x18001f250  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f257  lea     rdx, aStatus; "Status"
0x18001f25e  call    DebugTraceError
0x18001f263  jmp     short loc_18001F2A8
0x18001f265  test    r8, r8
0x18001f268  jnz     short loc_18001F27C
0x18001f26a  mov     r9d, 1C30h
0x18001f270  mov     ebx, 80090027h
0x18001f275  mov     ecx, 80090027h
0x18001f27a  jmp     short loc_18001F250
0x18001f27c  test    edx, edx
0x18001f27e  jz      short loc_18001F288
0x18001f280  mov     r9d, 1C38h
0x18001f286  jmp     short loc_18001F270
0x18001f288  test    r9d, r9d
0x18001f28b  jz      short loc_18001F29F
0x18001f28d  mov     ebx, 80090009h
0x18001f292  mov     r9d, 1C3Fh
0x18001f298  mov     ecx, 80090009h
0x18001f29d  jmp     short loc_18001F250
0x18001f29f  xor     ebx, ebx
0x18001f2a1  mov     dword ptr [r8], 44h ; 'D'
0x18001f2a8  mov     eax, ebx
0x18001f2aa  add     rsp, 20h
0x18001f2ae  pop     rbx
0x18001f2af  retn
```
