# MSCryptHashData

- ea: `0x180031270`
- end: `0x180031404`
- name: `MSCryptHashData`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004820`
- `0x18007cfc4`
- `0x18007da38`
- `0x18007dc94`
- `0x1800801a8`
- `0x18008087c`
- `0x1800813a0`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180031270`
- `0x18003140c`
- `0x18004c3d0`
- `0x18007c720`
- `0x18009d820`

## string_xrefs

- `0x1800312dc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180031385`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800313ea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a0b13`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashData(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  unsigned int v7; // edi
  int v8; // eax
  __int64 v10; // r8
  __int64 v11; // rdx
  _BYTE v12[64]; // [rsp+40h] [rbp-68h] BYREF

  if ( (a4 & 0xFFFFFFFB) != 0 )
  {
    v7 = -1073741811;
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
    v7 = -1073741816;
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
      return (unsigned int)MSCryptHashDataTlsCbcHmacVerify(a1, a2, a3);
    else
      return (unsigned int)-1073741811;
  }
  else
  {
    if ( !a3 )
      return 0;
    if ( *(_DWORD *)(a1 + 28) == 1 && !*(_DWORD *)(a1 + 32) )
    {
      v10 = *(unsigned int *)(a1 + 112);
      v11 = 0;
      for ( *(_DWORD *)(a1 + 32) = 1; (unsigned int)v11 < (unsigned int)v10; v11 = (unsigned int)(v11 + 1) )
        v12[v11] = *(_BYTE *)(v11 + a1 + 48) ^ 0x36;
      v7 = MSCryptHashDataInternal(a1, v12, v10);
      SymCryptWipeAsm(v12, 64);
      if ( (v7 & 0x80000000) != 0 )
      {
        DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 2356);
        return v7;
      }
    }
    v8 = MSCryptHashDataInternal(a1, a2, a3);
    v7 = v8;
    if ( v8 < 0 )
      DebugTraceError(
        (unsigned int)v8,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        2367);
    else
      return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180031270  mov     [rsp+arg_18], rbx
0x180031275  push    rbp
0x180031276  push    rsi
0x180031277  push    rdi
0x180031278  sub     rsp, 90h
0x18003127f  mov     rax, cs:__security_cookie
0x180031286  xor     rax, rsp
0x180031289  mov     [rsp+0A8h+var_28], rax
0x180031291  mov     esi, r8d
0x180031294  mov     rbp, rdx
0x180031297  mov     rbx, rcx
0x18003129a  test    r9d, 0FFFFFFFBh
0x1800312a1  jnz     loc_18003135E
0x1800312a7  test    rcx, rcx
0x1800312aa  jz      short loc_1800312B5
0x1800312ac  cmp     dword ptr [rcx+4], 4D534848h
0x1800312b3  jz      short loc_1800312F5
0x1800312b5  mov     edi, 0C0000008h
0x1800312ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312c1  lea     rax, WPP_GLOBAL_Control
0x1800312c8  cmp     rcx, rax
0x1800312cb  jz      short loc_180031338
0x1800312cd  mov     eax, [rcx+2Ch]
0x1800312d0  test    al, 1
0x1800312d2  jz      short loc_180031338
0x1800312d4  mov     [rsp+0A8h+var_78], 908h
0x1800312dc  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800312e3  mov     [rsp+0A8h+var_80], rax
0x1800312e8  mov     [rsp+0A8h+var_88], 0C0000008h
0x1800312f0  jmp     loc_180031399
0x1800312f5  test    rbx, rbx
0x1800312f8  jz      short loc_1800312B5
0x1800312fa  cmp     dword ptr [rcx+14h], 0
0x1800312fe  jnz     short loc_1800312B5
0x180031300  cmp     dword ptr [rcx+24h], 0
0x180031304  jnz     short loc_1800312B5
0x180031306  test    r9b, 4
0x18003130a  jnz     loc_1800313AB
0x180031310  test    esi, esi
0x180031312  jz      short loc_180031336
0x180031314  cmp     dword ptr [rcx+1Ch], 1
0x180031318  jz      loc_1800313BF
0x18003131e  mov     r8d, esi
0x180031321  mov     rdx, rbp
0x180031324  mov     rcx, rbx
0x180031327  call    MSCryptHashDataInternal
0x18003132c  mov     edi, eax
0x18003132e  test    eax, eax
0x180031330  js      loc_1800313E4
0x180031336  xor     edi, edi
0x180031338  mov     eax, edi
0x18003133a  mov     rcx, [rsp+0A8h+var_28]
0x180031342  xor     rcx, rsp; StackCookie
0x180031345  call    __security_check_cookie
0x18003134a  mov     rbx, [rsp+0A8h+arg_18]
0x180031352  add     rsp, 90h
0x180031359  pop     rdi
0x18003135a  pop     rsi
0x18003135b  pop     rbp
0x18003135c  retn
0x18003135e  mov     edi, 0C000000Dh
0x180031363  mov     rcx, cs:WPP_GLOBAL_Control
0x18003136a  lea     rax, WPP_GLOBAL_Control
0x180031371  cmp     rcx, rax
0x180031374  jz      short loc_180031338
0x180031376  mov     eax, [rcx+2Ch]
0x180031379  test    al, 1
0x18003137b  jz      short loc_180031338
0x18003137d  mov     [rsp+0A8h+var_78], 8FDh
0x180031385  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003138c  mov     [rsp+0A8h+var_80], rax
0x180031391  mov     [rsp+0A8h+var_88], 0C000000Dh
0x180031399  mov     rcx, [rcx+18h]
0x18003139d  lea     r9, aStatus; "Status"
0x1800313a4  call    WPP_SF_sDsd
0x1800313a9  jmp     short loc_180031338
0x1800313ab  cmp     byte ptr [rcx+28h], 0
0x1800313af  jnz     loc_1800A0ACC
0x1800313b5  mov     edi, 0C000000Dh
0x1800313ba  jmp     loc_180031338
0x1800313bf  cmp     dword ptr [rcx+20h], 0
0x1800313c3  jnz     loc_18003131E
0x1800313c9  mov     r8d, [rcx+70h]
0x1800313cd  xor     edx, edx
0x1800313cf  mov     dword ptr [rcx+20h], 1
0x1800313d6  test    r8d, r8d
0x1800313d9  jnz     loc_1800A0AD8
0x1800313df  jmp     loc_1800A0AEA
0x1800313e4  mov     r9d, 93Fh
0x1800313ea  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800313f1  lea     rdx, aStatus; "Status"
0x1800313f8  mov     ecx, eax
0x1800313fa  call    DebugTraceError
0x1800313ff  jmp     loc_180031338
0x1800a0acc  call    MSCryptHashDataTlsCbcHmacVerify
0x1800a0ad1  mov     edi, eax
0x1800a0ad3  jmp     loc_180031338
0x1800a0ad8  movzx   eax, byte ptr [rdx+rcx+30h]
0x1800a0add  xor     al, 36h
0x1800a0adf  mov     [rsp+rdx+0A8h+var_68], al
0x1800a0ae3  inc     edx
0x1800a0ae5  cmp     edx, r8d
0x1800a0ae8  jb      short loc_1800A0AD8
0x1800a0aea  lea     rdx, [rsp+0A8h+var_68]
0x1800a0aef  call    MSCryptHashDataInternal
0x1800a0af4  mov     edx, 40h ; '@'
0x1800a0af9  lea     rcx, [rsp+0A8h+var_68]
0x1800a0afe  mov     edi, eax
0x1800a0b00  call    SymCryptWipeAsm
0x1800a0b05  test    edi, edi
0x1800a0b07  jns     loc_18003131E
0x1800a0b0d  mov     r9d, 934h
0x1800a0b13  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a0b1a  lea     rdx, aStatus; "Status"
0x1800a0b21  mov     ecx, edi
0x1800a0b23  call    DebugTraceError
0x1800a0b28  nop
0x1800a0b29  jmp     loc_180031338
```
