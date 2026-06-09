# PbdevicetypeFromPszTypeA

- ea: `0x180084144`
- end: `0x1800844d8`
- name: `PbdevicetypeFromPszTypeA`
- size: `916`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006907c`
- `0x180074ad4`
- `0x18008408c`
- `0x180085c14`

## callees

- `0x180005bcc`
- `0x18005fd80`
- `0x180084144`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008448f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008448f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800841c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800841f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084222`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084254`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084286`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800842b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800842ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008431c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008434e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084380`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800843b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800843e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084416`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084445`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084474`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800841c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800841f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084222`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084254`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084286`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800842b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800842ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008431c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008434e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084380`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800843b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800843e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084416`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084445`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180084474`

## pseudocode

```c
const WCHAR *__fastcall PbdevicetypeFromPszTypeA(LPCCH lpMultiByteStr)
{
  const WCHAR *result; // rax
  WCHAR *lpString2; // rdi
  unsigned int v4; // ebx

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 94, WPP_38cda081c674317ed40163d707084d83_Traceguids);
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
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 95, WPP_38cda081c674317ed40163d707084d83_Traceguids);
    }
    return (const WCHAR *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180084144  push    rbx
0x180084146  push    rbp
0x180084147  push    rsi
0x180084148  push    rdi
0x180084149  push    r14
0x18008414b  push    r15
0x18008414d  sub     rsp, 38h
0x180084151  mov     rbx, rcx
0x180084154  mov     rcx, cs:WPP_GLOBAL_Control
0x18008415b  lea     r15, WPP_GLOBAL_Control
0x180084162  cmp     rcx, r15
0x180084165  jz      short loc_180084188
0x180084167  test    byte ptr [rcx+1Ch], 80h
0x18008416b  jz      short loc_180084188
0x18008416d  cmp     byte ptr [rcx+19h], 6
0x180084171  jb      short loc_180084188
0x180084173  mov     rcx, [rcx+10h]
0x180084177  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x18008417e  mov     edx, 5Eh ; '^'
0x180084183  call    WPP_SF_
0x180084188  mov     edx, 0FDE9h; CodePage
0x18008418d  mov     rcx, rbx; lpMultiByteStr
0x180084190  call    StrDupWFromAInternal
0x180084195  mov     rdi, rax
0x180084198  test    rax, rax
0x18008419b  jz      loc_1800844CA
0x1800841a1  or      esi, 0FFFFFFFFh
0x1800841a4  lea     r8, aModem_1; "modem"
0x1800841ab  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800841af  mov     r9d, esi; cchCount1
0x1800841b2  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800841b7  lea     ebx, [rsi+2]
0x1800841ba  lea     r14d, [rbx+7Eh]
0x1800841be  mov     edx, ebx; dwCmpFlags
0x1800841c0  mov     ecx, r14d; Locale
0x1800841c3  call    cs:__imp_CompareStringW
0x1800841ca  nop     dword ptr [rax+rax+00h]
0x1800841cf  lea     ebp, [rsi+3]
0x1800841d2  cmp     eax, ebp
0x1800841d4  jnz     short loc_1800841DE
0x1800841d6  lea     ebx, [rsi+4]
0x1800841d9  jmp     loc_18008448C
0x1800841de  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800841e2  lea     r8, aNull; "null"
0x1800841e9  mov     r9d, esi; cchCount1
0x1800841ec  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800841f1  mov     edx, ebx; dwCmpFlags
0x1800841f3  mov     ecx, r14d; Locale
0x1800841f6  call    cs:__imp_CompareStringW
0x1800841fd  nop     dword ptr [rax+rax+00h]
0x180084202  cmp     eax, ebp
0x180084204  jz      loc_18008448C
0x18008420a  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008420e  lea     r8, aParallel; "PARALLEL"
0x180084215  mov     r9d, esi; cchCount1
0x180084218  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008421d  mov     edx, ebx; dwCmpFlags
0x18008421f  mov     ecx, r14d; Locale
0x180084222  call    cs:__imp_CompareStringW
0x180084229  nop     dword ptr [rax+rax+00h]
0x18008422e  cmp     eax, ebp
0x180084230  jnz     short loc_18008423C
0x180084232  mov     ebx, 0Eh
0x180084237  jmp     loc_18008448C
0x18008423c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180084240  lea     r8, aIrda; "IRDA"
0x180084247  mov     r9d, esi; cchCount1
0x18008424a  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008424f  mov     edx, ebx; dwCmpFlags
0x180084251  mov     ecx, r14d; Locale
0x180084254  call    cs:__imp_CompareStringW
0x18008425b  nop     dword ptr [rax+rax+00h]
0x180084260  cmp     eax, ebp
0x180084262  jnz     short loc_18008426E
0x180084264  mov     ebx, 0Ah
0x180084269  jmp     loc_18008448C
0x18008426e  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180084272  lea     r8, aPad_1; "pad"
0x180084279  mov     r9d, esi; cchCount1
0x18008427c  mov     [rsp+68h+lpString2], rdi; lpString2
0x180084281  mov     edx, ebx; dwCmpFlags
0x180084283  mov     ecx, r14d; Locale
0x180084286  call    cs:__imp_CompareStringW
0x18008428d  nop     dword ptr [rax+rax+00h]
0x180084292  cmp     eax, ebp
0x180084294  jnz     short loc_1800842A0
0x180084296  mov     ebx, 4
0x18008429b  jmp     loc_18008448C
0x1800842a0  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800842a4  lea     r8, aSwitch_1; "switch"
0x1800842ab  mov     r9d, esi; cchCount1
0x1800842ae  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800842b3  mov     edx, ebx; dwCmpFlags
0x1800842b5  mov     ecx, r14d; Locale
0x1800842b8  call    cs:__imp_CompareStringW
0x1800842bf  nop     dword ptr [rax+rax+00h]
0x1800842c4  cmp     eax, ebp
0x1800842c6  jnz     short loc_1800842D2
0x1800842c8  mov     ebx, 5
0x1800842cd  jmp     loc_18008448C
0x1800842d2  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800842d6  lea     r8, aIsdn; "isdn"
0x1800842dd  mov     r9d, esi; cchCount1
0x1800842e0  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800842e5  mov     edx, ebx; dwCmpFlags
0x1800842e7  mov     ecx, r14d; Locale
0x1800842ea  call    cs:__imp_CompareStringW
0x1800842f1  nop     dword ptr [rax+rax+00h]
0x1800842f6  cmp     eax, ebp
0x1800842f8  jnz     short loc_180084304
0x1800842fa  mov     ebx, 6
0x1800842ff  jmp     loc_18008448C
0x180084304  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180084308  lea     r8, aX25; "x25"
0x18008430f  mov     r9d, esi; cchCount1
0x180084312  mov     [rsp+68h+lpString2], rdi; lpString2
0x180084317  mov     edx, ebx; dwCmpFlags
0x180084319  mov     ecx, r14d; Locale
0x18008431c  call    cs:__imp_CompareStringW
0x180084323  nop     dword ptr [rax+rax+00h]
0x180084328  cmp     eax, ebp
0x18008432a  jnz     short loc_180084336
0x18008432c  mov     ebx, 7
0x180084331  jmp     loc_18008448C
0x180084336  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008433a  lea     r8, aVpn_2; "vpn"
0x180084341  mov     r9d, esi; cchCount1
0x180084344  mov     [rsp+68h+lpString2], rdi; lpString2
0x180084349  mov     edx, ebx; dwCmpFlags
0x18008434b  mov     ecx, r14d; Locale
0x18008434e  call    cs:__imp_CompareStringW
0x180084355  nop     dword ptr [rax+rax+00h]
0x18008435a  cmp     eax, ebp
0x18008435c  jnz     short loc_180084368
0x18008435e  mov     ebx, 0Bh
0x180084363  jmp     loc_18008448C
0x180084368  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008436c  lea     r8, aAtm; "ATM"
0x180084373  mov     r9d, esi; cchCount1
0x180084376  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008437b  mov     edx, ebx; dwCmpFlags
0x18008437d  mov     ecx, r14d; Locale
0x180084380  call    cs:__imp_CompareStringW
0x180084387  nop     dword ptr [rax+rax+00h]
0x18008438c  cmp     eax, ebp
0x18008438e  jnz     short loc_18008439A
0x180084390  mov     ebx, 0Dh
0x180084395  jmp     loc_18008448C
0x18008439a  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008439e  lea     r8, aSerial; "SERIAL"
0x1800843a5  mov     r9d, esi; cchCount1
0x1800843a8  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800843ad  mov     edx, ebx; dwCmpFlags
0x1800843af  mov     ecx, r14d; Locale
0x1800843b2  call    cs:__imp_CompareStringW
0x1800843b9  nop     dword ptr [rax+rax+00h]
0x1800843be  cmp     eax, ebp
0x1800843c0  jnz     short loc_1800843CC
0x1800843c2  mov     ebx, 0Ch
0x1800843c7  jmp     loc_18008448C
0x1800843cc  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800843d0  lea     r8, aFramerelay; "FRAMERELAY"
0x1800843d7  mov     r9d, esi; cchCount1
0x1800843da  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800843df  mov     edx, ebx; dwCmpFlags
0x1800843e1  mov     ecx, r14d; Locale
0x1800843e4  call    cs:__imp_CompareStringW
0x1800843eb  nop     dword ptr [rax+rax+00h]
0x1800843f0  cmp     eax, ebp
0x1800843f2  jnz     short loc_1800843FE
0x1800843f4  mov     ebx, 11h
0x1800843f9  jmp     loc_18008448C
0x1800843fe  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180084402  lea     r8, aSonet; "SONET"
0x180084409  mov     r9d, esi; cchCount1
0x18008440c  mov     [rsp+68h+lpString2], rdi; lpString2
0x180084411  mov     edx, ebx; dwCmpFlags
0x180084413  mov     ecx, r14d; Locale
0x180084416  call    cs:__imp_CompareStringW
0x18008441d  nop     dword ptr [rax+rax+00h]
0x180084422  cmp     eax, ebp
0x180084424  jnz     short loc_18008442D
0x180084426  mov     ebx, 0Fh
0x18008442b  jmp     short loc_18008448C
0x18008442d  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180084431  lea     r8, aSw56; "SW56"
0x180084438  mov     r9d, esi; cchCount1
0x18008443b  mov     [rsp+68h+lpString2], rdi; lpString2
0x180084440  mov     edx, ebx; dwCmpFlags
0x180084442  mov     ecx, r14d; Locale
0x180084445  call    cs:__imp_CompareStringW
0x18008444c  nop     dword ptr [rax+rax+00h]
0x180084451  cmp     eax, ebp
0x180084453  jnz     short loc_18008445C
0x180084455  mov     ebx, 10h
0x18008445a  jmp     short loc_18008448C
0x18008445c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180084460  lea     r8, aPppoe; "PPPoE"
0x180084467  mov     r9d, esi; cchCount1
0x18008446a  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008446f  mov     edx, ebx; dwCmpFlags
0x180084471  mov     ecx, r14d; Locale
0x180084474  call    cs:__imp_CompareStringW
0x18008447b  nop     dword ptr [rax+rax+00h]
0x180084480  mov     ebx, ebp
0x180084482  mov     ecx, 12h
0x180084487  cmp     eax, ebp
0x180084489  cmovz   ebx, ecx
0x18008448c  mov     rcx, rdi; hMem
0x18008448f  call    cs:__imp_GlobalFree
0x180084496  nop     dword ptr [rax+rax+00h]
0x18008449b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800844a2  cmp     rcx, r15
0x1800844a5  jz      short loc_1800844C8
0x1800844a7  test    byte ptr [rcx+1Ch], 80h
0x1800844ab  jz      short loc_1800844C8
0x1800844ad  cmp     byte ptr [rcx+19h], 6
0x1800844b1  jb      short loc_1800844C8
0x1800844b3  mov     rcx, [rcx+10h]
0x1800844b7  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800844be  mov     edx, 5Fh ; '_'
0x1800844c3  call    WPP_SF_
0x1800844c8  mov     eax, ebx
0x1800844ca  add     rsp, 38h
0x1800844ce  pop     r15
0x1800844d0  pop     r14
0x1800844d2  pop     rdi
0x1800844d3  pop     rsi
0x1800844d4  pop     rbp
0x1800844d5  pop     rbx
0x1800844d6  retn
```
