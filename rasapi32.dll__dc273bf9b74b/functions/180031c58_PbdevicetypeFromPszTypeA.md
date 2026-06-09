# PbdevicetypeFromPszTypeA

- ea: `0x180031c58`
- end: `0x180031fca`
- name: `PbdevicetypeFromPszTypeA`
- size: `882`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002624`
- `0x18000aa40`
- `0x1800c9f50`
- `0x1800d1a6c`

## callees

- `0x18000b10c`
- `0x180031c58`
- `0x18004e984`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180031dd7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180031dd7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031cba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ce3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d2f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d55`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d7b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031da1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031dc7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031e14`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ea9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ed5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f2d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031cba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ce3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d2f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d55`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031d7b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031da1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031dc7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031e14`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ea9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031ed5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f2d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031f85`

## pseudocode

```c
const WCHAR *__fastcall PbdevicetypeFromPszTypeA(LPCCH lpMultiByteStr)
{
  const WCHAR *result; // rax
  WCHAR *lpString2; // rdi
  unsigned int v4; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  result = (const WCHAR *)StrDupWFromAInternal(lpMultiByteStr, 0xFDE9u);
  lpString2 = (WCHAR *)result;
  if ( result )
  {
    v4 = 1;
    if ( CompareStringW(0x7Fu, 1u, L"modem", -1, result, -1) == 2 )
    {
      v4 = 3;
    }
    else if ( CompareStringW(0x7Fu, 1u, L"null", -1, lpString2, -1) != 2 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"PARALLEL", -1, lpString2, -1) == 2 )
      {
        v4 = 14;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"IRDA", -1, lpString2, -1) == 2 )
      {
        v4 = 10;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"pad", -1, lpString2, -1) == 2 )
      {
        v4 = 4;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"switch", -1, lpString2, -1) == 2 )
      {
        v4 = 5;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"isdn", -1, lpString2, -1) == 2 )
      {
        v4 = 6;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"x25", -1, lpString2, -1) == 2 )
      {
        v4 = 7;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"vpn", -1, lpString2, -1) == 2 )
      {
        v4 = 11;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"ATM", -1, lpString2, -1) == 2 )
      {
        v4 = 13;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"SERIAL", -1, lpString2, -1) == 2 )
      {
        v4 = 12;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"FRAMERELAY", -1, lpString2, -1) == 2 )
      {
        v4 = 17;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"SONET", -1, lpString2, -1) == 2 )
      {
        v4 = 15;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"SW56", -1, lpString2, -1) == 2 )
      {
        v4 = 16;
      }
      else
      {
        v4 = 2;
        if ( CompareStringW(0x7Fu, 1u, L"PPPoE", -1, lpString2, -1) == 2 )
          v4 = 18;
      }
    }
    GlobalFree(lpString2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_38cda081c674317ed40163d707084d83_Traceguids);
    }
    return (const WCHAR *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180031c58  push    rbx
0x180031c5a  push    rbp
0x180031c5b  push    rsi
0x180031c5c  push    rdi
0x180031c5d  push    r14
0x180031c5f  push    r15
0x180031c61  sub     rsp, 38h
0x180031c65  mov     rbx, rcx
0x180031c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c6f  lea     r15, WPP_GLOBAL_Control
0x180031c76  cmp     rcx, r15
0x180031c79  jnz     loc_180031E25
0x180031c7f  mov     edx, 0FDE9h; CodePage
0x180031c84  mov     rcx, rbx; lpMultiByteStr
0x180031c87  call    StrDupWFromAInternal
0x180031c8c  mov     rdi, rax
0x180031c8f  test    rax, rax
0x180031c92  jz      loc_180031E53
0x180031c98  or      esi, 0FFFFFFFFh
0x180031c9b  lea     r8, aModem_0; "modem"
0x180031ca2  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031ca6  mov     r9d, esi; cchCount1
0x180031ca9  mov     [rsp+68h+lpString2], rax; lpString2
0x180031cae  lea     ebx, [rsi+2]
0x180031cb1  lea     r14d, [rbx+7Eh]
0x180031cb5  mov     edx, ebx; dwCmpFlags
0x180031cb7  mov     ecx, r14d; Locale
0x180031cba  call    cs:__imp_CompareStringW
0x180031cc0  lea     ebp, [rsi+3]
0x180031cc3  cmp     eax, ebp
0x180031cc5  jz      loc_180031E55
0x180031ccb  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031ccf  lea     r8, aNull; "null"
0x180031cd6  mov     r9d, esi; cchCount1
0x180031cd9  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031cde  mov     edx, ebx; dwCmpFlags
0x180031ce0  mov     ecx, r14d; Locale
0x180031ce3  call    cs:__imp_CompareStringW
0x180031ce9  cmp     eax, ebp
0x180031ceb  jz      loc_180031DD4
0x180031cf1  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031cf5  lea     r8, aParallel; "PARALLEL"
0x180031cfc  mov     r9d, esi; cchCount1
0x180031cff  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031d04  mov     edx, ebx; dwCmpFlags
0x180031d06  mov     ecx, r14d; Locale
0x180031d09  call    cs:__imp_CompareStringW
0x180031d0f  cmp     eax, ebp
0x180031d11  jz      loc_180031E5F
0x180031d17  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031d1b  lea     r8, aIrda; "IRDA"
0x180031d22  mov     r9d, esi; cchCount1
0x180031d25  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031d2a  mov     edx, ebx; dwCmpFlags
0x180031d2c  mov     ecx, r14d; Locale
0x180031d2f  call    cs:__imp_CompareStringW
0x180031d35  cmp     eax, ebp
0x180031d37  jz      loc_180031E69
0x180031d3d  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031d41  lea     r8, aPad_0; "pad"
0x180031d48  mov     r9d, esi; cchCount1
0x180031d4b  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031d50  mov     edx, ebx; dwCmpFlags
0x180031d52  mov     ecx, r14d; Locale
0x180031d55  call    cs:__imp_CompareStringW
0x180031d5b  cmp     eax, ebp
0x180031d5d  jz      loc_180031E73
0x180031d63  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031d67  lea     r8, aSwitch_0; "switch"
0x180031d6e  mov     r9d, esi; cchCount1
0x180031d71  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031d76  mov     edx, ebx; dwCmpFlags
0x180031d78  mov     ecx, r14d; Locale
0x180031d7b  call    cs:__imp_CompareStringW
0x180031d81  cmp     eax, ebp
0x180031d83  jz      loc_180031E7D
0x180031d89  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031d8d  lea     r8, aIsdn; "isdn"
0x180031d94  mov     r9d, esi; cchCount1
0x180031d97  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031d9c  mov     edx, ebx; dwCmpFlags
0x180031d9e  mov     ecx, r14d; Locale
0x180031da1  call    cs:__imp_CompareStringW
0x180031da7  cmp     eax, ebp
0x180031da9  jz      loc_180031E87
0x180031daf  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031db3  lea     r8, aX25; "x25"
0x180031dba  mov     r9d, esi; cchCount1
0x180031dbd  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031dc2  mov     edx, ebx; dwCmpFlags
0x180031dc4  mov     ecx, r14d; Locale
0x180031dc7  call    cs:__imp_CompareStringW
0x180031dcd  cmp     eax, ebp
0x180031dcf  jnz     short loc_180031DFC
0x180031dd1  lea     ebx, [rsi+8]
0x180031dd4  mov     rcx, rdi; hMem
0x180031dd7  call    cs:__imp_GlobalFree
0x180031ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180031de4  cmp     rcx, r15
0x180031de7  jnz     loc_180031F9C
0x180031ded  mov     eax, ebx
0x180031def  add     rsp, 38h
0x180031df3  pop     r15
0x180031df5  pop     r14
0x180031df7  pop     rdi
0x180031df8  pop     rsi
0x180031df9  pop     rbp
0x180031dfa  pop     rbx
0x180031dfb  retn
0x180031dfc  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031e00  lea     r8, aVpn_0; "vpn"
0x180031e07  mov     r9d, esi; cchCount1
0x180031e0a  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031e0f  mov     edx, ebx; dwCmpFlags
0x180031e11  mov     ecx, r14d; Locale
0x180031e14  call    cs:__imp_CompareStringW
0x180031e1a  cmp     eax, ebp
0x180031e1c  jnz     short loc_180031E91
0x180031e1e  mov     ebx, 0Bh
0x180031e23  jmp     short loc_180031DD4
0x180031e25  test    byte ptr [rcx+1Ch], 80h
0x180031e29  jz      loc_180031C7F
0x180031e2f  cmp     byte ptr [rcx+19h], 6
0x180031e33  jb      loc_180031C7F
0x180031e39  mov     rcx, [rcx+10h]
0x180031e3d  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180031e44  mov     edx, 5Eh ; '^'
0x180031e49  call    WPP_SF_
0x180031e4e  jmp     loc_180031C7F
0x180031e53  jmp     short loc_180031DEF
0x180031e55  mov     ebx, 3
0x180031e5a  jmp     loc_180031DD4
0x180031e5f  mov     ebx, 0Eh
0x180031e64  jmp     loc_180031DD4
0x180031e69  mov     ebx, 0Ah
0x180031e6e  jmp     loc_180031DD4
0x180031e73  mov     ebx, 4
0x180031e78  jmp     loc_180031DD4
0x180031e7d  mov     ebx, 5
0x180031e82  jmp     loc_180031DD4
0x180031e87  mov     ebx, 6
0x180031e8c  jmp     loc_180031DD4
0x180031e91  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031e95  lea     r8, aAtm; "ATM"
0x180031e9c  mov     r9d, esi; cchCount1
0x180031e9f  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031ea4  mov     edx, ebx; dwCmpFlags
0x180031ea6  mov     ecx, r14d; Locale
0x180031ea9  call    cs:__imp_CompareStringW
0x180031eaf  cmp     eax, ebp
0x180031eb1  jnz     short loc_180031EBD
0x180031eb3  mov     ebx, 0Dh
0x180031eb8  jmp     loc_180031DD4
0x180031ebd  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031ec1  lea     r8, aSerial; "SERIAL"
0x180031ec8  mov     r9d, esi; cchCount1
0x180031ecb  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031ed0  mov     edx, ebx; dwCmpFlags
0x180031ed2  mov     ecx, r14d; Locale
0x180031ed5  call    cs:__imp_CompareStringW
0x180031edb  cmp     eax, ebp
0x180031edd  jnz     short loc_180031EE9
0x180031edf  mov     ebx, 0Ch
0x180031ee4  jmp     loc_180031DD4
0x180031ee9  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031eed  lea     r8, aFramerelay; "FRAMERELAY"
0x180031ef4  mov     r9d, esi; cchCount1
0x180031ef7  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031efc  mov     edx, ebx; dwCmpFlags
0x180031efe  mov     ecx, r14d; Locale
0x180031f01  call    cs:__imp_CompareStringW
0x180031f07  cmp     eax, ebp
0x180031f09  jnz     short loc_180031F15
0x180031f0b  mov     ebx, 11h
0x180031f10  jmp     loc_180031DD4
0x180031f15  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031f19  lea     r8, aSonet; "SONET"
0x180031f20  mov     r9d, esi; cchCount1
0x180031f23  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031f28  mov     edx, ebx; dwCmpFlags
0x180031f2a  mov     ecx, r14d; Locale
0x180031f2d  call    cs:__imp_CompareStringW
0x180031f33  cmp     eax, ebp
0x180031f35  jnz     short loc_180031F41
0x180031f37  mov     ebx, 0Fh
0x180031f3c  jmp     loc_180031DD4
0x180031f41  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031f45  lea     r8, aSw56; "SW56"
0x180031f4c  mov     r9d, esi; cchCount1
0x180031f4f  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031f54  mov     edx, ebx; dwCmpFlags
0x180031f56  mov     ecx, r14d; Locale
0x180031f59  call    cs:__imp_CompareStringW
0x180031f5f  cmp     eax, ebp
0x180031f61  jnz     short loc_180031F6D
0x180031f63  mov     ebx, 10h
0x180031f68  jmp     loc_180031DD4
0x180031f6d  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180031f71  lea     r8, aPppoe; "PPPoE"
0x180031f78  mov     r9d, esi; cchCount1
0x180031f7b  mov     [rsp+68h+lpString2], rdi; lpString2
0x180031f80  mov     edx, ebx; dwCmpFlags
0x180031f82  mov     ecx, r14d; Locale
0x180031f85  call    cs:__imp_CompareStringW
0x180031f8b  mov     ebx, ebp
0x180031f8d  mov     ecx, 12h
0x180031f92  cmp     eax, ebp
0x180031f94  cmovz   ebx, ecx
0x180031f97  jmp     loc_180031DD4
0x180031f9c  test    byte ptr [rcx+1Ch], 80h
0x180031fa0  jz      loc_180031DED
0x180031fa6  cmp     byte ptr [rcx+19h], 6
0x180031faa  jb      loc_180031DED
0x180031fb0  mov     rcx, [rcx+10h]
0x180031fb4  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180031fbb  mov     edx, 5Fh ; '_'
0x180031fc0  call    WPP_SF_
0x180031fc5  jmp     loc_180031DED
```
