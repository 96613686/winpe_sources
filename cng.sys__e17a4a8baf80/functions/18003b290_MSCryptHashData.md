# MSCryptHashData

- ea: `0x18003b290`
- end: `0x18003b424`
- name: `MSCryptHashData`
- size: `404`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e940`
- `0x1800871c4`
- `0x180087c38`
- `0x180087e94`
- `0x18008a398`
- `0x18008aa6c`
- `0x18008b590`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18003b290`
- `0x18003b42c`
- `0x1800564d0`
- `0x180086920`
- `0x1800a4260`

## string_xrefs

- `0x18003b2fc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18003b3a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18003b40a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a78b1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashData(__int64 a1, __int64 a2, int a3, int a4)
{
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _BYTE v11[64]; // [rsp+40h] [rbp-68h] BYREF

  if ( (a4 & 0xFFFFFFFB) != 0 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        253);
  }
  else if ( !a1 || *(_DWORD *)(a1 + 4) != 1297303624 || *(_DWORD *)(a1 + 20) || *(_DWORD *)(a1 + 36) )
  {
    v6 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        8);
  }
  else if ( (a4 & 4) != 0 )
  {
    if ( *(_BYTE *)(a1 + 40) )
      return (unsigned int)MSCryptHashDataTlsCbcHmacVerify();
    else
      return (unsigned int)-1073741811;
  }
  else
  {
    if ( !a3 )
      return 0;
    if ( *(_DWORD *)(a1 + 28) == 1 && !*(_DWORD *)(a1 + 32) )
    {
      v9 = *(_DWORD *)(a1 + 112);
      v10 = 0;
      for ( *(_DWORD *)(a1 + 32) = 1; (unsigned int)v10 < v9; v10 = (unsigned int)(v10 + 1) )
        v11[v10] = *(_BYTE *)(v10 + a1 + 48) ^ 0x36;
      v6 = MSCryptHashDataInternal(a1, v11);
      SymCryptWipeAsm(v11, 64);
      if ( (v6 & 0x80000000) != 0 )
      {
        DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 2356);
        return v6;
      }
    }
    v7 = MSCryptHashDataInternal(a1, a2);
    v6 = v7;
    if ( v7 < 0 )
      DebugTraceError(
        (unsigned int)v7,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        2367);
    else
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18003b290  mov     [rsp+arg_18], rbx
0x18003b295  push    rbp
0x18003b296  push    rsi
0x18003b297  push    rdi
0x18003b298  sub     rsp, 90h
0x18003b29f  mov     rax, cs:__security_cookie
0x18003b2a6  xor     rax, rsp
0x18003b2a9  mov     [rsp+0A8h+var_28], rax
0x18003b2b1  mov     esi, r8d
0x18003b2b4  mov     rbp, rdx
0x18003b2b7  mov     rbx, rcx
0x18003b2ba  test    r9d, 0FFFFFFFBh
0x18003b2c1  jnz     loc_18003B37E
0x18003b2c7  test    rcx, rcx
0x18003b2ca  jz      short loc_18003B2D5
0x18003b2cc  cmp     dword ptr [rcx+4], 4D534848h
0x18003b2d3  jz      short loc_18003B315
0x18003b2d5  mov     edi, 0C0000008h
0x18003b2da  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2e1  lea     rax, WPP_GLOBAL_Control
0x18003b2e8  cmp     rcx, rax
0x18003b2eb  jz      short loc_18003B358
0x18003b2ed  mov     eax, [rcx+2Ch]
0x18003b2f0  test    al, 1
0x18003b2f2  jz      short loc_18003B358
0x18003b2f4  mov     [rsp+0A8h+var_78], 908h
0x18003b2fc  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b303  mov     [rsp+0A8h+var_80], rax
0x18003b308  mov     [rsp+0A8h+var_88], 0C0000008h
0x18003b310  jmp     loc_18003B3B9
0x18003b315  test    rbx, rbx
0x18003b318  jz      short loc_18003B2D5
0x18003b31a  cmp     dword ptr [rcx+14h], 0
0x18003b31e  jnz     short loc_18003B2D5
0x18003b320  cmp     dword ptr [rcx+24h], 0
0x18003b324  jnz     short loc_18003B2D5
0x18003b326  test    r9b, 4
0x18003b32a  jnz     loc_18003B3CB
0x18003b330  test    esi, esi
0x18003b332  jz      short loc_18003B356
0x18003b334  cmp     dword ptr [rcx+1Ch], 1
0x18003b338  jz      loc_18003B3DF
0x18003b33e  mov     r8d, esi
0x18003b341  mov     rdx, rbp
0x18003b344  mov     rcx, rbx
0x18003b347  call    MSCryptHashDataInternal
0x18003b34c  mov     edi, eax
0x18003b34e  test    eax, eax
0x18003b350  js      loc_18003B404
0x18003b356  xor     edi, edi
0x18003b358  mov     eax, edi
0x18003b35a  mov     rcx, [rsp+0A8h+var_28]
0x18003b362  xor     rcx, rsp; StackCookie
0x18003b365  call    __security_check_cookie
0x18003b36a  mov     rbx, [rsp+0A8h+arg_18]
0x18003b372  add     rsp, 90h
0x18003b379  pop     rdi
0x18003b37a  pop     rsi
0x18003b37b  pop     rbp
0x18003b37c  retn
0x18003b37e  mov     edi, 0C000000Dh
0x18003b383  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b38a  lea     rax, WPP_GLOBAL_Control
0x18003b391  cmp     rcx, rax
0x18003b394  jz      short loc_18003B358
0x18003b396  mov     eax, [rcx+2Ch]
0x18003b399  test    al, 1
0x18003b39b  jz      short loc_18003B358
0x18003b39d  mov     [rsp+0A8h+var_78], 8FDh
0x18003b3a5  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b3ac  mov     [rsp+0A8h+var_80], rax
0x18003b3b1  mov     [rsp+0A8h+var_88], 0C000000Dh
0x18003b3b9  mov     rcx, [rcx+18h]
0x18003b3bd  lea     r9, aStatus; "Status"
0x18003b3c4  call    WPP_SF_sDsd
0x18003b3c9  jmp     short loc_18003B358
0x18003b3cb  cmp     byte ptr [rcx+28h], 0
0x18003b3cf  jnz     loc_1800A786A
0x18003b3d5  mov     edi, 0C000000Dh
0x18003b3da  jmp     loc_18003B358
0x18003b3df  cmp     dword ptr [rcx+20h], 0
0x18003b3e3  jnz     loc_18003B33E
0x18003b3e9  mov     r8d, [rcx+70h]
0x18003b3ed  xor     edx, edx
0x18003b3ef  mov     dword ptr [rcx+20h], 1
0x18003b3f6  test    r8d, r8d
0x18003b3f9  jnz     loc_1800A7876
0x18003b3ff  jmp     loc_1800A7888
0x18003b404  mov     r9d, 93Fh
0x18003b40a  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b411  lea     rdx, aStatus; "Status"
0x18003b418  mov     ecx, eax
0x18003b41a  call    DebugTraceError
0x18003b41f  jmp     loc_18003B358
0x1800a786a  call    MSCryptHashDataTlsCbcHmacVerify
0x1800a786f  mov     edi, eax
0x1800a7871  jmp     loc_18003B358
0x1800a7876  movzx   eax, byte ptr [rdx+rcx+30h]
0x1800a787b  xor     al, 36h
0x1800a787d  mov     [rsp+rdx+0A8h+var_68], al
0x1800a7881  inc     edx
0x1800a7883  cmp     edx, r8d
0x1800a7886  jb      short loc_1800A7876
0x1800a7888  lea     rdx, [rsp+0A8h+var_68]
0x1800a788d  call    MSCryptHashDataInternal
0x1800a7892  mov     edx, 40h ; '@'
0x1800a7897  lea     rcx, [rsp+0A8h+var_68]
0x1800a789c  mov     edi, eax
0x1800a789e  call    SymCryptWipeAsm
0x1800a78a3  test    edi, edi
0x1800a78a5  jns     loc_18003B33E
0x1800a78ab  mov     r9d, 934h
0x1800a78b1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a78b8  lea     rdx, aStatus; "Status"
0x1800a78bf  mov     ecx, edi
0x1800a78c1  call    DebugTraceError
0x1800a78c6  nop
0x1800a78c7  jmp     loc_18003B358
```
