# MSCryptSetRsaProperty

- ea: `0x180049a80`
- end: `0x180049b78`
- name: `MSCryptSetRsaProperty`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180049a80`
- `0x180049c28`
- `0x1800a4232`

## string_xrefs

- `0x180049ad5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180049b2d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800a8b30`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x180049a80  push    rbx
0x180049a82  push    rsi
0x180049a83  push    rdi
0x180049a84  push    r14
0x180049a86  sub     rsp, 48h
0x180049a8a  cmp     [rsp+68h+arg_20], 0
0x180049a92  mov     esi, r9d
0x180049a95  mov     r14, r8
0x180049a98  mov     rdi, rdx
0x180049a9b  jnz     short loc_180049B06
0x180049a9d  call    validateMSCryptRsaKey
0x180049aa2  mov     rbx, rax
0x180049aa5  test    rax, rax
0x180049aa8  jnz     loc_180049B43
0x180049aae  mov     ebx, 0C0000008h
0x180049ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180049aba  lea     rax, WPP_GLOBAL_Control
0x180049ac1  cmp     rcx, rax
0x180049ac4  jz      short loc_180049AF9
0x180049ac6  mov     eax, [rcx+2Ch]
0x180049ac9  test    al, 1
0x180049acb  jz      short loc_180049AF9
0x180049acd  mov     [rsp+68h+var_38], 361h
0x180049ad5  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049adc  mov     [rsp+68h+var_40], r8
0x180049ae1  mov     [rsp+68h+var_48], 0C0000008h
0x180049ae9  mov     rcx, [rcx+18h]
0x180049aed  lea     r9, aStatus; "Status"
0x180049af4  call    WPP_SF_sDsd
0x180049af9  mov     eax, ebx
0x180049afb  add     rsp, 48h
0x180049aff  pop     r14
0x180049b01  pop     rdi
0x180049b02  pop     rsi
0x180049b03  pop     rbx
0x180049b04  retn
0x180049b06  mov     ebx, 0C000000Dh
0x180049b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b12  lea     rax, WPP_GLOBAL_Control
0x180049b19  cmp     rcx, rax
0x180049b1c  jz      short loc_180049AF9
0x180049b1e  mov     eax, [rcx+2Ch]
0x180049b21  test    al, 1
0x180049b23  jz      short loc_180049AF9
0x180049b25  mov     [rsp+68h+var_38], 358h
0x180049b2d  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049b34  mov     [rsp+68h+var_40], r8
0x180049b39  mov     [rsp+68h+var_48], 0C000000Dh
0x180049b41  jmp     short loc_180049AE9
0x180049b43  lea     rdx, aKeylength; "KeyLength"
0x180049b4a  mov     rcx, rdi; Str1
0x180049b4d  call    wcscmp_0
0x180049b52  test    eax, eax
0x180049b54  jz      loc_1800A8AFE
0x180049b5a  lea     rdx, aKeystrength; "KeyStrength"
0x180049b61  mov     rcx, rdi; Str1
0x180049b64  call    wcscmp_0
0x180049b69  test    eax, eax
0x180049b6b  jz      loc_1800A8AFE
0x180049b71  mov     ebx, 0C00000BBh
0x180049b76  jmp     short loc_180049AF9
0x1800a8afe  cmp     esi, 4
0x1800a8b01  jz      short loc_1800A8B0B
0x1800a8b03  mov     r9d, 36Eh
0x1800a8b09  jmp     short loc_1800A8B30
0x1800a8b0b  mov     ecx, [r14]
0x1800a8b0e  lea     eax, [rcx-200h]
0x1800a8b14  cmp     eax, 3E00h
0x1800a8b19  ja      short loc_1800A8B2A
0x1800a8b1b  test    cl, 7
0x1800a8b1e  jnz     short loc_1800A8B2A
0x1800a8b20  mov     [rbx+0Ch], ecx
0x1800a8b23  xor     ebx, ebx
0x1800a8b25  jmp     loc_180049AF9
0x1800a8b2a  mov     r9d, 37Ah
0x1800a8b30  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8b37  mov     ecx, 0C000000Dh
0x1800a8b3c  lea     rdx, aStatus; "Status"
0x1800a8b43  mov     ebx, 0C000000Dh
0x1800a8b48  call    DebugTraceError
0x1800a8b4d  nop
0x1800a8b4e  jmp     loc_180049AF9
```
