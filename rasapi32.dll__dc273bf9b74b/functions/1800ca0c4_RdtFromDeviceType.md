# RdtFromDeviceType

- ea: `0x1800ca0c4`
- end: `0x1800ca2f0`
- name: `RdtFromDeviceType`
- size: `556`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180095f90`

## callees

- `0x18007e650`
- `0x1800ca0c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca12e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca154`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca17a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca1a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca1c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca1ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca212`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca239`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca28a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca2ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca2d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca12e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca154`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca17a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca1a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca1c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca1ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca212`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca239`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca28a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca2ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca2d4`

## pseudocode

```c
__int64 __fastcall RdtFromDeviceType(LPCWCH lpString1, int a2)
{
  unsigned int v4; // ebx
  int v5; // edi
  int v6; // edi
  int v7; // edi

  v4 = 6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_38cda081c674317ed40163d707084d83_Traceguids,
      (_DWORD)lpString1,
      a2);
  }
  if ( CompareStringOrdinal(lpString1, -1, L"modem", -1, 1) == 2 )
  {
    return 0;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"isdn", -1, 1) == 2 )
  {
    return 2;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"SERIAL", -1, 1) == 2 )
  {
    return 3;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"FRAMERELAY", -1, 1) == 2 )
  {
    return 4;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"ATM", -1, 1) == 2 )
  {
    return 5;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"SONET", -1, 1) != 2 )
  {
    if ( CompareStringOrdinal(lpString1, -1, L"SW56", -1, 1) == 2 )
    {
      return 7;
    }
    else if ( CompareStringOrdinal(lpString1, -1, L"vpn", -1, 1) == 2 )
    {
      v4 = 8;
      v5 = a2 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 30;
          if ( v7 )
          {
            if ( v7 == 32 )
              return 15;
          }
          else
          {
            return 14;
          }
        }
        else
        {
          return 9;
        }
      }
    }
    else if ( CompareStringOrdinal(lpString1, -1, L"IRDA", -1, 1) == 2 )
    {
      return 10;
    }
    else if ( CompareStringOrdinal(lpString1, -1, L"PARALLEL", -1, 1) == 2 )
    {
      return 11;
    }
    else
    {
      v4 = 0;
      if ( CompareStringOrdinal(lpString1, -1, L"PPPoE", -1, 1) == 2 )
        return 13;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800ca0c4  push    rbx
0x1800ca0c6  push    rbp
0x1800ca0c7  push    rsi
0x1800ca0c8  push    rdi
0x1800ca0c9  push    r15
0x1800ca0cb  sub     rsp, 30h
0x1800ca0cf  mov     edi, edx
0x1800ca0d1  mov     rsi, rcx
0x1800ca0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca0db  lea     rax, WPP_GLOBAL_Control
0x1800ca0e2  mov     ebx, 6
0x1800ca0e7  cmp     rcx, rax
0x1800ca0ea  jz      short loc_1800CA111
0x1800ca0ec  test    byte ptr [rcx+1Ch], 80h
0x1800ca0f0  jz      short loc_1800CA111
0x1800ca0f2  cmp     [rcx+19h], bl
0x1800ca0f5  jb      short loc_1800CA111
0x1800ca0f7  mov     rcx, [rcx+10h]
0x1800ca0fb  lea     edx, [rbx+8]
0x1800ca0fe  mov     r9, rsi
0x1800ca101  mov     [rsp+58h+bIgnoreCase], edi
0x1800ca105  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800ca10c  call    WPP_SF_Sd
0x1800ca111  or      ebp, 0FFFFFFFFh
0x1800ca114  lea     r8, aModem_0; "modem"
0x1800ca11b  mov     r15d, 1
0x1800ca121  mov     r9d, ebp; cchCount2
0x1800ca124  mov     edx, ebp; cchCount1
0x1800ca126  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca12b  mov     rcx, rsi; lpString1
0x1800ca12e  call    cs:__imp_CompareStringOrdinal
0x1800ca134  cmp     eax, 2
0x1800ca137  jnz     short loc_1800CA140
0x1800ca139  xor     ebx, ebx
0x1800ca13b  jmp     loc_1800CA2E3
0x1800ca140  mov     r9d, ebp; cchCount2
0x1800ca143  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca148  lea     r8, aIsdn; "isdn"
0x1800ca14f  mov     edx, ebp; cchCount1
0x1800ca151  mov     rcx, rsi; lpString1
0x1800ca154  call    cs:__imp_CompareStringOrdinal
0x1800ca15a  cmp     eax, 2
0x1800ca15d  jnz     short loc_1800CA166
0x1800ca15f  mov     ebx, eax
0x1800ca161  jmp     loc_1800CA2E3
0x1800ca166  mov     r9d, ebp; cchCount2
0x1800ca169  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca16e  lea     r8, aSerial; "SERIAL"
0x1800ca175  mov     edx, ebp; cchCount1
0x1800ca177  mov     rcx, rsi; lpString1
0x1800ca17a  call    cs:__imp_CompareStringOrdinal
0x1800ca180  cmp     eax, 2
0x1800ca183  jnz     short loc_1800CA18D
0x1800ca185  lea     ebx, [rax+1]
0x1800ca188  jmp     loc_1800CA2E3
0x1800ca18d  mov     r9d, ebp; cchCount2
0x1800ca190  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca195  lea     r8, aFramerelay; "FRAMERELAY"
0x1800ca19c  mov     edx, ebp; cchCount1
0x1800ca19e  mov     rcx, rsi; lpString1
0x1800ca1a1  call    cs:__imp_CompareStringOrdinal
0x1800ca1a7  cmp     eax, 2
0x1800ca1aa  jnz     short loc_1800CA1B4
0x1800ca1ac  lea     ebx, [rax+2]
0x1800ca1af  jmp     loc_1800CA2E3
0x1800ca1b4  mov     r9d, ebp; cchCount2
0x1800ca1b7  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca1bc  lea     r8, aAtm; "ATM"
0x1800ca1c3  mov     edx, ebp; cchCount1
0x1800ca1c5  mov     rcx, rsi; lpString1
0x1800ca1c8  call    cs:__imp_CompareStringOrdinal
0x1800ca1ce  cmp     eax, 2
0x1800ca1d1  jnz     short loc_1800CA1DB
0x1800ca1d3  lea     ebx, [rax+3]
0x1800ca1d6  jmp     loc_1800CA2E3
0x1800ca1db  mov     r9d, ebp; cchCount2
0x1800ca1de  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca1e3  lea     r8, aSonet; "SONET"
0x1800ca1ea  mov     edx, ebp; cchCount1
0x1800ca1ec  mov     rcx, rsi; lpString1
0x1800ca1ef  call    cs:__imp_CompareStringOrdinal
0x1800ca1f5  cmp     eax, 2
0x1800ca1f8  jz      loc_1800CA2E3
0x1800ca1fe  mov     r9d, ebp; cchCount2
0x1800ca201  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca206  lea     r8, aSw56; "SW56"
0x1800ca20d  mov     edx, ebp; cchCount1
0x1800ca20f  mov     rcx, rsi; lpString1
0x1800ca212  call    cs:__imp_CompareStringOrdinal
0x1800ca218  cmp     eax, 2
0x1800ca21b  jnz     short loc_1800CA225
0x1800ca21d  lea     ebx, [rax+5]
0x1800ca220  jmp     loc_1800CA2E3
0x1800ca225  mov     r9d, ebp; cchCount2
0x1800ca228  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca22d  lea     r8, aVpn_0; "vpn"
0x1800ca234  mov     edx, ebp; cchCount1
0x1800ca236  mov     rcx, rsi; lpString1
0x1800ca239  call    cs:__imp_CompareStringOrdinal
0x1800ca23f  cmp     eax, 2
0x1800ca242  jnz     short loc_1800CA276
0x1800ca244  lea     ebx, [rax+6]
0x1800ca247  sub     edi, r15d
0x1800ca24a  jz      loc_1800CA2E3
0x1800ca250  sub     edi, r15d
0x1800ca253  jz      short loc_1800CA26F
0x1800ca255  sub     edi, 1Eh
0x1800ca258  jz      short loc_1800CA268
0x1800ca25a  cmp     edi, 20h ; ' '
0x1800ca25d  jnz     loc_1800CA2E3
0x1800ca263  lea     ebx, [rax+0Dh]
0x1800ca266  jmp     short loc_1800CA2E3
0x1800ca268  mov     ebx, 0Eh
0x1800ca26d  jmp     short loc_1800CA2E3
0x1800ca26f  mov     ebx, 9
0x1800ca274  jmp     short loc_1800CA2E3
0x1800ca276  mov     r9d, ebp; cchCount2
0x1800ca279  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca27e  lea     r8, aIrda; "IRDA"
0x1800ca285  mov     edx, ebp; cchCount1
0x1800ca287  mov     rcx, rsi; lpString1
0x1800ca28a  call    cs:__imp_CompareStringOrdinal
0x1800ca290  cmp     eax, 2
0x1800ca293  jnz     short loc_1800CA29A
0x1800ca295  lea     ebx, [rax+8]
0x1800ca298  jmp     short loc_1800CA2E3
0x1800ca29a  mov     r9d, ebp; cchCount2
0x1800ca29d  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca2a2  lea     r8, aParallel; "PARALLEL"
0x1800ca2a9  mov     edx, ebp; cchCount1
0x1800ca2ab  mov     rcx, rsi; lpString1
0x1800ca2ae  call    cs:__imp_CompareStringOrdinal
0x1800ca2b4  cmp     eax, 2
0x1800ca2b7  jnz     short loc_1800CA2BE
0x1800ca2b9  lea     ebx, [rax+9]
0x1800ca2bc  jmp     short loc_1800CA2E3
0x1800ca2be  mov     r9d, ebp; cchCount2
0x1800ca2c1  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1800ca2c6  lea     r8, aPppoe; "PPPoE"
0x1800ca2cd  mov     edx, ebp; cchCount1
0x1800ca2cf  mov     rcx, rsi; lpString1
0x1800ca2d2  xor     ebx, ebx
0x1800ca2d4  call    cs:__imp_CompareStringOrdinal
0x1800ca2da  cmp     eax, 2
0x1800ca2dd  lea     ecx, [rbx+0Dh]
0x1800ca2e0  cmovz   ebx, ecx
0x1800ca2e3  mov     eax, ebx
0x1800ca2e5  add     rsp, 30h
0x1800ca2e9  pop     r15
0x1800ca2eb  pop     rdi
0x1800ca2ec  pop     rsi
0x1800ca2ed  pop     rbp
0x1800ca2ee  pop     rbx
0x1800ca2ef  retn
```
