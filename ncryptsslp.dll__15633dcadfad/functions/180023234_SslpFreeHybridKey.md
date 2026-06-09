# SslpFreeHybridKey

- ea: `0x180023234`
- end: `0x18002330d`
- name: `SslpFreeHybridKey`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800022a0`
- `0x18001e480`
- `0x1800234b0`

## callees

- `0x180003ef0`
- `0x18000b654`
- `0x180013e6c`
- `0x180022164`
- `0x180023234`
- `0x1800237a0`

## string_xrefs

- `0x18002325e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x18002329b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpFreeHybridKey(unsigned int *a1)
{
  int v3; // edi
  __int64 v4; // r9
  __int64 v5; // rax
  _BYTE *v6; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v8 = 0;
  if ( !a1 )
  {
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 443);
    return 2148073511LL;
  }
  v3 = SslpValidateConstituentKeys((__int64)a1, &v7, &v8);
  if ( v3 >= 0 )
  {
    v3 = SslpFreeEphemeralKey(v7);
    if ( v3 >= 0 )
    {
      v3 = SslpFreeKemKey(v8);
      if ( v3 >= 0 )
      {
        v5 = *a1;
        v6 = a1;
        if ( *a1 )
        {
          do
          {
            *v6++ = 0;
            --v5;
          }
          while ( v5 );
        }
        MSCryptFree(a1);
        return (unsigned int)v3;
      }
      v4 = 467;
    }
    else
    {
      v4 = 460;
    }
  }
  else
  {
    v4 = 453;
  }
  DebugTraceError((unsigned int)v3, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180023234  mov     [rsp+arg_10], rbx
0x180023239  push    rdi
0x18002323a  sub     rsp, 20h
0x18002323e  mov     [rsp+28h+arg_0], 0
0x180023247  mov     rbx, rcx
0x18002324a  mov     [rsp+28h+arg_8], 0
0x180023253  test    rcx, rcx
0x180023256  jnz     short loc_180023280
0x180023258  mov     r9d, 1BBh
0x18002325e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023265  lea     rdx, aStatus_0; "status"
0x18002326c  mov     ecx, 80090027h
0x180023271  call    DebugTraceError
0x180023276  mov     eax, 80090027h
0x18002327b  jmp     loc_180023302
0x180023280  lea     r8, [rsp+28h+arg_8]
0x180023285  lea     rdx, [rsp+28h+arg_0]
0x18002328a  call    SslpValidateConstituentKeys
0x18002328f  mov     edi, eax
0x180023291  test    eax, eax
0x180023293  jns     short loc_1800232B2
0x180023295  mov     r9d, 1C5h
0x18002329b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800232a2  mov     ecx, edi
0x1800232a4  lea     rdx, aStatus_0; "status"
0x1800232ab  call    DebugTraceError
0x1800232b0  jmp     short loc_180023300
0x1800232b2  mov     rcx, [rsp+28h+arg_0]
0x1800232b7  call    SslpFreeEphemeralKey
0x1800232bc  mov     edi, eax
0x1800232be  test    eax, eax
0x1800232c0  jns     short loc_1800232CA
0x1800232c2  mov     r9d, 1CCh
0x1800232c8  jmp     short loc_18002329B
0x1800232ca  mov     rcx, [rsp+28h+arg_8]
0x1800232cf  call    SslpFreeKemKey
0x1800232d4  mov     edi, eax
0x1800232d6  test    eax, eax
0x1800232d8  jns     short loc_1800232E2
0x1800232da  mov     r9d, 1D3h
0x1800232e0  jmp     short loc_18002329B
0x1800232e2  mov     eax, [rbx]
0x1800232e4  mov     rcx, rbx
0x1800232e7  test    rax, rax
0x1800232ea  jz      short loc_1800232F8
0x1800232ec  mov     byte ptr [rcx], 0
0x1800232ef  inc     rcx
0x1800232f2  sub     rax, 1
0x1800232f6  jnz     short loc_1800232EC
0x1800232f8  mov     rcx, rbx
0x1800232fb  call    MSCryptFree
0x180023300  mov     eax, edi
0x180023302  mov     rbx, [rsp+28h+arg_10]
0x180023307  add     rsp, 20h
0x18002330b  pop     rdi
0x18002330c  retn
```
