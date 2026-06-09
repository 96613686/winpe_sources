# MSCryptHashData

- ea: `0x180031d70`
- end: `0x180031f04`
- name: `MSCryptHashData`
- size: `404`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004820`
- `0x18007dfb4`
- `0x18007ea28`
- `0x18007ec84`
- `0x180081198`
- `0x18008186c`
- `0x180082390`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180031d70`
- `0x180031f0c`
- `0x18004cc10`
- `0x18007d710`
- `0x18009f650`

## string_xrefs

- `0x180031ddc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180031e85`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180031eea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a2943`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
0x180031d70  mov     [rsp+arg_18], rbx
0x180031d75  push    rbp
0x180031d76  push    rsi
0x180031d77  push    rdi
0x180031d78  sub     rsp, 90h
0x180031d7f  mov     rax, cs:__security_cookie
0x180031d86  xor     rax, rsp
0x180031d89  mov     [rsp+0A8h+var_28], rax
0x180031d91  mov     esi, r8d
0x180031d94  mov     rbp, rdx
0x180031d97  mov     rbx, rcx
0x180031d9a  test    r9d, 0FFFFFFFBh
0x180031da1  jnz     loc_180031E5E
0x180031da7  test    rcx, rcx
0x180031daa  jz      short loc_180031DB5
0x180031dac  cmp     dword ptr [rcx+4], 4D534848h
0x180031db3  jz      short loc_180031DF5
0x180031db5  mov     edi, 0C0000008h
0x180031dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dc1  lea     rax, WPP_GLOBAL_Control
0x180031dc8  cmp     rcx, rax
0x180031dcb  jz      short loc_180031E38
0x180031dcd  mov     eax, [rcx+2Ch]
0x180031dd0  test    al, 1
0x180031dd2  jz      short loc_180031E38
0x180031dd4  mov     [rsp+0A8h+var_78], 908h
0x180031ddc  lea     rax, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180031de3  mov     [rsp+0A8h+var_80], rax
0x180031de8  mov     [rsp+0A8h+var_88], 0C0000008h
0x180031df0  jmp     loc_180031E99
0x180031df5  test    rbx, rbx
0x180031df8  jz      short loc_180031DB5
0x180031dfa  cmp     dword ptr [rcx+14h], 0
0x180031dfe  jnz     short loc_180031DB5
0x180031e00  cmp     dword ptr [rcx+24h], 0
0x180031e04  jnz     short loc_180031DB5
0x180031e06  test    r9b, 4
0x180031e0a  jnz     loc_180031EAB
0x180031e10  test    esi, esi
0x180031e12  jz      short loc_180031E36
0x180031e14  cmp     dword ptr [rcx+1Ch], 1
0x180031e18  jz      loc_180031EBF
0x180031e1e  mov     r8d, esi
0x180031e21  mov     rdx, rbp
0x180031e24  mov     rcx, rbx
0x180031e27  call    MSCryptHashDataInternal
0x180031e2c  mov     edi, eax
0x180031e2e  test    eax, eax
0x180031e30  js      loc_180031EE4
0x180031e36  xor     edi, edi
0x180031e38  mov     eax, edi
0x180031e3a  mov     rcx, [rsp+0A8h+var_28]
0x180031e42  xor     rcx, rsp; StackCookie
0x180031e45  call    __security_check_cookie
0x180031e4a  mov     rbx, [rsp+0A8h+arg_18]
0x180031e52  add     rsp, 90h
0x180031e59  pop     rdi
0x180031e5a  pop     rsi
0x180031e5b  pop     rbp
0x180031e5c  retn
0x180031e5e  mov     edi, 0C000000Dh
0x180031e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e6a  lea     rax, WPP_GLOBAL_Control
0x180031e71  cmp     rcx, rax
0x180031e74  jz      short loc_180031E38
0x180031e76  mov     eax, [rcx+2Ch]
0x180031e79  test    al, 1
0x180031e7b  jz      short loc_180031E38
0x180031e7d  mov     [rsp+0A8h+var_78], 8FDh
0x180031e85  lea     rax, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180031e8c  mov     [rsp+0A8h+var_80], rax
0x180031e91  mov     [rsp+0A8h+var_88], 0C000000Dh
0x180031e99  mov     rcx, [rcx+18h]
0x180031e9d  lea     r9, aStatus; "Status"
0x180031ea4  call    WPP_SF_sDsd
0x180031ea9  jmp     short loc_180031E38
0x180031eab  cmp     byte ptr [rcx+28h], 0
0x180031eaf  jnz     loc_1800A28FC
0x180031eb5  mov     edi, 0C000000Dh
0x180031eba  jmp     loc_180031E38
0x180031ebf  cmp     dword ptr [rcx+20h], 0
0x180031ec3  jnz     loc_180031E1E
0x180031ec9  mov     r8d, [rcx+70h]
0x180031ecd  xor     edx, edx
0x180031ecf  mov     dword ptr [rcx+20h], 1
0x180031ed6  test    r8d, r8d
0x180031ed9  jnz     loc_1800A2908
0x180031edf  jmp     loc_1800A291A
0x180031ee4  mov     r9d, 93Fh
0x180031eea  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180031ef1  lea     rdx, aStatus; "Status"
0x180031ef8  mov     ecx, eax
0x180031efa  call    DebugTraceError
0x180031eff  jmp     loc_180031E38
0x1800a28fc  call    MSCryptHashDataTlsCbcHmacVerify
0x1800a2901  mov     edi, eax
0x1800a2903  jmp     loc_180031E38
0x1800a2908  movzx   eax, byte ptr [rdx+rcx+30h]
0x1800a290d  xor     al, 36h
0x1800a290f  mov     [rsp+rdx+0A8h+var_68], al
0x1800a2913  inc     edx
0x1800a2915  cmp     edx, r8d
0x1800a2918  jb      short loc_1800A2908
0x1800a291a  lea     rdx, [rsp+0A8h+var_68]
0x1800a291f  call    MSCryptHashDataInternal
0x1800a2924  mov     edx, 40h ; '@'
0x1800a2929  lea     rcx, [rsp+0A8h+var_68]
0x1800a292e  mov     edi, eax
0x1800a2930  call    SymCryptWipeAsm
0x1800a2935  test    edi, edi
0x1800a2937  jns     loc_180031E1E
0x1800a293d  mov     r9d, 934h
0x1800a2943  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a294a  lea     rdx, aStatus; "Status"
0x1800a2951  mov     ecx, edi
0x1800a2953  call    DebugTraceError
0x1800a2958  nop
0x1800a2959  jmp     loc_180031E38
```
