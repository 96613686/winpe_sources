# SslpValidateKeysForHybridCreation

- ea: `0x18002396c`
- end: `0x180023a4e`
- name: `SslpValidateKeysForHybridCreation`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e480`

## callees

- `0x1800066f0`
- `0x18000b654`
- `0x1800238b4`
- `0x18002392c`
- `0x18002396c`
- `0x180023a78`

## string_xrefs

- `0x1800239f1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023a26`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpValidateKeysForHybridCreation(__int16 a1, __int64 a2, _DWORD *a3, __int64 *a4, _QWORD *a5)
{
  __int64 v9; // r9
  __int64 v10; // rsi
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v9 = 317;
    goto LABEL_14;
  }
  if ( (int)SslpValidateHybridGroup(a1) < 0 )
  {
    v9 = 325;
LABEL_14:
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v9);
    return 2148073511LL;
  }
  v10 = SslpValidateEphemeralHandle(a2);
  v11 = SslpValidateKemKeyHandle(a3);
  v12 = v11;
  if ( !v10 || !v11 )
  {
    v9 = 334;
    goto LABEL_14;
  }
  result = SslpValidateHybridAndConstituentGroupsMatch(a1, v10, (__int64)v11);
  if ( (int)result >= 0 )
  {
    *a4 = v10;
    *a5 = v12;
  }
  else
  {
    DebugTraceError(2148073513LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 342);
    return 2148073513LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002396c  push    rbx
0x18002396e  push    rbp
0x18002396f  push    rsi
0x180023970  push    rdi
0x180023971  push    r14
0x180023973  sub     rsp, 20h
0x180023977  mov     r14, r9
0x18002397a  mov     rbx, r8
0x18002397d  mov     rsi, rdx
0x180023980  movzx   ebp, cx
0x180023983  test    rdx, rdx
0x180023986  jz      loc_180023A20
0x18002398c  test    rbx, rbx
0x18002398f  jz      loc_180023A20
0x180023995  test    r9, r9
0x180023998  jz      loc_180023A20
0x18002399e  mov     rdi, [rsp+48h+arg_20]
0x1800239a3  test    rdi, rdi
0x1800239a6  jz      short loc_180023A20
0x1800239a8  call    SslpValidateHybridGroup
0x1800239ad  test    eax, eax
0x1800239af  jns     short loc_1800239B9
0x1800239b1  mov     r9d, 145h
0x1800239b7  jmp     short loc_180023A26
0x1800239b9  mov     rcx, rsi
0x1800239bc  call    SslpValidateEphemeralHandle
0x1800239c1  mov     rcx, rbx
0x1800239c4  mov     rsi, rax
0x1800239c7  call    SslpValidateKemKeyHandle
0x1800239cc  mov     rbx, rax
0x1800239cf  test    rsi, rsi
0x1800239d2  jz      short loc_180023A18
0x1800239d4  test    rax, rax
0x1800239d7  jz      short loc_180023A18
0x1800239d9  mov     r8, rax
0x1800239dc  mov     rdx, rsi
0x1800239df  movzx   ecx, bp
0x1800239e2  call    SslpValidateHybridAndConstituentGroupsMatch
0x1800239e7  test    eax, eax
0x1800239e9  jns     short loc_180023A10
0x1800239eb  mov     r9d, 156h
0x1800239f1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800239f8  lea     rdx, aStatus_0; "status"
0x1800239ff  mov     ecx, 80090029h
0x180023a04  call    DebugTraceError
0x180023a09  mov     eax, 80090029h
0x180023a0e  jmp     short loc_180023A43
0x180023a10  mov     [r14], rsi
0x180023a13  mov     [rdi], rbx
0x180023a16  jmp     short loc_180023A43
0x180023a18  mov     r9d, 14Eh
0x180023a1e  jmp     short loc_180023A26
0x180023a20  mov     r9d, 13Dh
0x180023a26  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023a2d  mov     ecx, 80090027h
0x180023a32  lea     rdx, aStatus_0; "status"
0x180023a39  call    DebugTraceError
0x180023a3e  mov     eax, 80090027h
0x180023a43  add     rsp, 20h
0x180023a47  pop     r14
0x180023a49  pop     rdi
0x180023a4a  pop     rsi
0x180023a4b  pop     rbp
0x180023a4c  pop     rbx
0x180023a4d  retn
```
