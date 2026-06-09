# MSCryptSetRsaProperty

- ea: `0x180040650`
- end: `0x180040748`
- name: `MSCryptSetRsaProperty`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180040650`
- `0x1800407f8`
- `0x18009f616`

## string_xrefs

- `0x1800406a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800406fd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800a3bc2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x180040650  push    rbx
0x180040652  push    rsi
0x180040653  push    rdi
0x180040654  push    r14
0x180040656  sub     rsp, 48h
0x18004065a  cmp     [rsp+68h+arg_20], 0
0x180040662  mov     esi, r9d
0x180040665  mov     r14, r8
0x180040668  mov     rdi, rdx
0x18004066b  jnz     short loc_1800406D6
0x18004066d  call    validateMSCryptRsaKey
0x180040672  mov     rbx, rax
0x180040675  test    rax, rax
0x180040678  jnz     loc_180040713
0x18004067e  mov     ebx, 0C0000008h
0x180040683  mov     rcx, cs:WPP_GLOBAL_Control
0x18004068a  lea     rax, WPP_GLOBAL_Control
0x180040691  cmp     rcx, rax
0x180040694  jz      short loc_1800406C9
0x180040696  mov     eax, [rcx+2Ch]
0x180040699  test    al, 1
0x18004069b  jz      short loc_1800406C9
0x18004069d  mov     [rsp+68h+var_38], 361h
0x1800406a5  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800406ac  mov     [rsp+68h+var_40], r8
0x1800406b1  mov     [rsp+68h+var_48], 0C0000008h
0x1800406b9  mov     rcx, [rcx+18h]
0x1800406bd  lea     r9, aStatus; "Status"
0x1800406c4  call    WPP_SF_sDsd
0x1800406c9  mov     eax, ebx
0x1800406cb  add     rsp, 48h
0x1800406cf  pop     r14
0x1800406d1  pop     rdi
0x1800406d2  pop     rsi
0x1800406d3  pop     rbx
0x1800406d4  retn
0x1800406d6  mov     ebx, 0C000000Dh
0x1800406db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406e2  lea     rax, WPP_GLOBAL_Control
0x1800406e9  cmp     rcx, rax
0x1800406ec  jz      short loc_1800406C9
0x1800406ee  mov     eax, [rcx+2Ch]
0x1800406f1  test    al, 1
0x1800406f3  jz      short loc_1800406C9
0x1800406f5  mov     [rsp+68h+var_38], 358h
0x1800406fd  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040704  mov     [rsp+68h+var_40], r8
0x180040709  mov     [rsp+68h+var_48], 0C000000Dh
0x180040711  jmp     short loc_1800406B9
0x180040713  lea     rdx, aKeylength; "KeyLength"
0x18004071a  mov     rcx, rdi; Str1
0x18004071d  call    wcscmp_0
0x180040722  test    eax, eax
0x180040724  jz      loc_1800A3B90
0x18004072a  lea     rdx, aKeystrength; "KeyStrength"
0x180040731  mov     rcx, rdi; Str1
0x180040734  call    wcscmp_0
0x180040739  test    eax, eax
0x18004073b  jz      loc_1800A3B90
0x180040741  mov     ebx, 0C00000BBh
0x180040746  jmp     short loc_1800406C9
0x1800a3b90  cmp     esi, 4
0x1800a3b93  jz      short loc_1800A3B9D
0x1800a3b95  mov     r9d, 36Eh
0x1800a3b9b  jmp     short loc_1800A3BC2
0x1800a3b9d  mov     ecx, [r14]
0x1800a3ba0  lea     eax, [rcx-200h]
0x1800a3ba6  cmp     eax, 3E00h
0x1800a3bab  ja      short loc_1800A3BBC
0x1800a3bad  test    cl, 7
0x1800a3bb0  jnz     short loc_1800A3BBC
0x1800a3bb2  mov     [rbx+0Ch], ecx
0x1800a3bb5  xor     ebx, ebx
0x1800a3bb7  jmp     loc_1800406C9
0x1800a3bbc  mov     r9d, 37Ah
0x1800a3bc2  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3bc9  mov     ecx, 0C000000Dh
0x1800a3bce  lea     rdx, aStatus; "Status"
0x1800a3bd5  mov     ebx, 0C000000Dh
0x1800a3bda  call    DebugTraceError
0x1800a3bdf  nop
0x1800a3be0  jmp     loc_1800406C9
```
