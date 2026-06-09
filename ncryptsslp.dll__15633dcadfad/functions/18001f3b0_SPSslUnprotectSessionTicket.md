# SPSslUnprotectSessionTicket

- ea: `0x18001f3b0`
- end: `0x18001f4d7`
- name: `SPSslUnprotectSessionTicket`
- size: `295`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, unsigned int, UCHAR *pbOutput, ULONG *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001f3b0`
- `0x180021464`
- `0x180023a9c`
- `0x180025a00`

## string_xrefs

- `0x18001f4b7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslUnprotectSessionTicket(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        unsigned int a4,
        UCHAR *pbOutput,
        ULONG *a6,
        int a7)
{
  unsigned __int64 cbInput; // r14
  __int64 v9; // rbx
  __int64 v10; // r10
  __int64 v11; // r8
  size_t v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // eax

  cbInput = a4;
  v9 = SslpValidateSessionTicketKeyHandle(a2);
  if ( !SslpValidateProvHandle(v10) || !v9 )
  {
    v13 = -2146893786;
    v14 = 7332;
    v15 = 2148073510LL;
    goto LABEL_18;
  }
  if ( !v11 || (v12 = *(unsigned int *)(v9 + 56), cbInput < v12 + 8) || !pbOutput || !a6 || !*a6 )
  {
    v14 = 7344;
    goto LABEL_15;
  }
  if ( a7 )
  {
    v13 = -2146893815;
    v14 = 7351;
    v15 = 2148073481LL;
LABEL_18:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v14);
    return v13;
  }
  if ( *a3 != *(_DWORD *)(v9 + 8) || memcmp(a3 + 1, *(const void **)(v9 + 64), v12) )
  {
    v14 = 7361;
LABEL_15:
    v13 = -2146893785;
    v15 = 2148073511LL;
    goto LABEL_18;
  }
  v16 = UnprotectSessionTicket(*(BCRYPT_KEY_HANDLE *)(v9 + 16), cbInput, pbOutput, a6);
  v13 = v16;
  if ( v16 < 0 )
  {
    v14 = 7377;
    v15 = (unsigned int)v16;
    goto LABEL_18;
  }
  return v13;
}

```

## disassembly

```asm
0x18001f3b0  push    rbx
0x18001f3b2  push    rbp
0x18001f3b3  push    rsi
0x18001f3b4  push    rdi
0x18001f3b5  push    r14
0x18001f3b7  sub     rsp, 40h
0x18001f3bb  mov     r10, rcx
0x18001f3be  mov     r14d, r9d
0x18001f3c1  mov     rcx, rdx
0x18001f3c4  mov     rsi, r8
0x18001f3c7  call    SslpValidateSessionTicketKeyHandle
0x18001f3cc  mov     rcx, r10
0x18001f3cf  mov     rbx, rax
0x18001f3d2  call    SslpValidateProvHandle
0x18001f3d7  test    rax, rax
0x18001f3da  jz      loc_18001F4A7
0x18001f3e0  test    rbx, rbx
0x18001f3e3  jz      loc_18001F4A7
0x18001f3e9  test    r8, r8
0x18001f3ec  jz      loc_18001F49F
0x18001f3f2  mov     r8d, [rbx+38h]; Size
0x18001f3f6  lea     rcx, [r8+8]
0x18001f3fa  cmp     r14, rcx
0x18001f3fd  jb      loc_18001F49F
0x18001f403  mov     rbp, [rsp+68h+arg_20]
0x18001f40b  test    rbp, rbp
0x18001f40e  jz      loc_18001F49F
0x18001f414  mov     rdi, [rsp+68h+arg_28]
0x18001f41c  test    rdi, rdi
0x18001f41f  jz      short loc_18001F49F
0x18001f421  cmp     dword ptr [rdi], 0
0x18001f424  jz      short loc_18001F49F
0x18001f426  cmp     [rsp+68h+arg_30], 0
0x18001f42e  jz      short loc_18001F442
0x18001f430  mov     ebx, 80090009h
0x18001f435  mov     r9d, 1CB7h
0x18001f43b  mov     ecx, 80090009h
0x18001f440  jmp     short loc_18001F4B7
0x18001f442  mov     eax, [rbx+8]
0x18001f445  cmp     [rsi], eax
0x18001f447  jnz     short loc_18001F48D
0x18001f449  mov     rdx, [rbx+40h]; Buf2
0x18001f44d  lea     rcx, [rsi+4]; Buf1
0x18001f451  call    memcmp
0x18001f456  test    eax, eax
0x18001f458  jnz     short loc_18001F48D
0x18001f45a  mov     r8d, [rbx+28h]
0x18001f45e  mov     r9, rsi
0x18001f461  mov     rdx, [rbx+30h]
0x18001f465  mov     rcx, [rbx+10h]; hKey
0x18001f469  mov     [rsp+68h+var_38], rdi; ULONG *
0x18001f46e  mov     [rsp+68h+pbOutput], rbp; pbOutput
0x18001f473  mov     [rsp+68h+cbInput], r14d; cbInput
0x18001f478  call    UnprotectSessionTicket
0x18001f47d  mov     ebx, eax
0x18001f47f  test    eax, eax
0x18001f481  jns     short loc_18001F4CA
0x18001f483  mov     r9d, 1CD1h
0x18001f489  mov     ecx, eax
0x18001f48b  jmp     short loc_18001F4B7
0x18001f48d  mov     r9d, 1CC1h
0x18001f493  mov     ebx, 80090027h
0x18001f498  mov     ecx, 80090027h
0x18001f49d  jmp     short loc_18001F4B7
0x18001f49f  mov     r9d, 1CB0h
0x18001f4a5  jmp     short loc_18001F493
0x18001f4a7  mov     ebx, 80090026h
0x18001f4ac  mov     r9d, 1CA4h
0x18001f4b2  mov     ecx, 80090026h
0x18001f4b7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f4be  lea     rdx, aStatus; "Status"
0x18001f4c5  call    DebugTraceError
0x18001f4ca  mov     eax, ebx
0x18001f4cc  add     rsp, 40h
0x18001f4d0  pop     r14
0x18001f4d2  pop     rdi
0x18001f4d3  pop     rsi
0x18001f4d4  pop     rbp
0x18001f4d5  pop     rbx
0x18001f4d6  retn
```
