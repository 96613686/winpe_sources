# MSCryptSetRsaProperty

- ea: `0x18003fac0`
- end: `0x18003fbb8`
- name: `MSCryptSetRsaProperty`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003fac0`
- `0x18003fc68`
- `0x18009d746`

## string_xrefs

- `0x18003fb15`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003fb6d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800a1d92`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetRsaProperty(__int64 a1, const wchar_t *a2, int *a3, int a4, int a5)
{
  int v8; // edx
  __int64 v9; // rbx
  unsigned int v10; // ebx
  __int64 v12; // r9
  int v13; // ecx

  if ( a5 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        88);
  }
  else
  {
    v9 = validateMSCryptRsaKey(a1);
    if ( v9 )
    {
      if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
      {
        if ( a4 == 4 )
        {
          v13 = *a3;
          if ( (unsigned int)(*a3 - 512) <= 0x3E00 && (v13 & 7) == 0 )
          {
            *(_DWORD *)(v9 + 12) = v13;
            return 0;
          }
          v12 = 890;
        }
        else
        {
          v12 = 878;
        }
        v10 = -1073741811;
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v12);
        return v10;
      }
      return (unsigned int)-1073741637;
    }
    else
    {
      v10 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v8,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          97);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18003fac0  push    rbx
0x18003fac2  push    rsi
0x18003fac3  push    rdi
0x18003fac4  push    r14
0x18003fac6  sub     rsp, 48h
0x18003faca  cmp     [rsp+68h+arg_20], 0
0x18003fad2  mov     esi, r9d
0x18003fad5  mov     r14, r8
0x18003fad8  mov     rdi, rdx
0x18003fadb  jnz     short loc_18003FB46
0x18003fadd  call    validateMSCryptRsaKey
0x18003fae2  mov     rbx, rax
0x18003fae5  test    rax, rax
0x18003fae8  jnz     loc_18003FB83
0x18003faee  mov     ebx, 0C0000008h
0x18003faf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fafa  lea     rax, WPP_GLOBAL_Control
0x18003fb01  cmp     rcx, rax
0x18003fb04  jz      short loc_18003FB39
0x18003fb06  mov     eax, [rcx+2Ch]
0x18003fb09  test    al, 1
0x18003fb0b  jz      short loc_18003FB39
0x18003fb0d  mov     [rsp+68h+var_38], 361h
0x18003fb15  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fb1c  mov     [rsp+68h+var_40], r8
0x18003fb21  mov     [rsp+68h+var_48], 0C0000008h
0x18003fb29  mov     rcx, [rcx+18h]
0x18003fb2d  lea     r9, aStatus; "Status"
0x18003fb34  call    WPP_SF_sDsd
0x18003fb39  mov     eax, ebx
0x18003fb3b  add     rsp, 48h
0x18003fb3f  pop     r14
0x18003fb41  pop     rdi
0x18003fb42  pop     rsi
0x18003fb43  pop     rbx
0x18003fb44  retn
0x18003fb46  mov     ebx, 0C000000Dh
0x18003fb4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb52  lea     rax, WPP_GLOBAL_Control
0x18003fb59  cmp     rcx, rax
0x18003fb5c  jz      short loc_18003FB39
0x18003fb5e  mov     eax, [rcx+2Ch]
0x18003fb61  test    al, 1
0x18003fb63  jz      short loc_18003FB39
0x18003fb65  mov     [rsp+68h+var_38], 358h
0x18003fb6d  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fb74  mov     [rsp+68h+var_40], r8
0x18003fb79  mov     [rsp+68h+var_48], 0C000000Dh
0x18003fb81  jmp     short loc_18003FB29
0x18003fb83  lea     rdx, aKeylength; "KeyLength"
0x18003fb8a  mov     rcx, rdi; Str1
0x18003fb8d  call    wcscmp_0
0x18003fb92  test    eax, eax
0x18003fb94  jz      loc_1800A1D60
0x18003fb9a  lea     rdx, aKeystrength; "KeyStrength"
0x18003fba1  mov     rcx, rdi; Str1
0x18003fba4  call    wcscmp_0
0x18003fba9  test    eax, eax
0x18003fbab  jz      loc_1800A1D60
0x18003fbb1  mov     ebx, 0C00000BBh
0x18003fbb6  jmp     short loc_18003FB39
0x1800a1d60  cmp     esi, 4
0x1800a1d63  jz      short loc_1800A1D6D
0x1800a1d65  mov     r9d, 36Eh
0x1800a1d6b  jmp     short loc_1800A1D92
0x1800a1d6d  mov     ecx, [r14]
0x1800a1d70  lea     eax, [rcx-200h]
0x1800a1d76  cmp     eax, 3E00h
0x1800a1d7b  ja      short loc_1800A1D8C
0x1800a1d7d  test    cl, 7
0x1800a1d80  jnz     short loc_1800A1D8C
0x1800a1d82  mov     [rbx+0Ch], ecx
0x1800a1d85  xor     ebx, ebx
0x1800a1d87  jmp     loc_18003FB39
0x1800a1d8c  mov     r9d, 37Ah
0x1800a1d92  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1d99  mov     ecx, 0C000000Dh
0x1800a1d9e  lea     rdx, aStatus; "Status"
0x1800a1da5  mov     ebx, 0C000000Dh
0x1800a1daa  call    DebugTraceError
0x1800a1daf  nop
0x1800a1db0  jmp     loc_18003FB39
```
