# GetSupportedKeyLengths(ushort const *,__BCRYPT_KEY_LENGTHS_STRUCT *,ulong *)

- ea: `0x18002f910`
- end: `0x18002fbe4`
- name: `?GetSupportedKeyLengths@@YAJPEBGPEAU__BCRYPT_KEY_LENGTHS_STRUCT@@PEAK@Z`
- size: `724`
- prototype: `int(const unsigned __int16 *, struct __BCRYPT_KEY_LENGTHS_STRUCT *, unsigned int *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e130`
- `0x180024bb0`
- `0x18003c220`
- `0x18003c598`
- `0x18003cd70`
- `0x18005f84c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002f910`
- `0x180042410`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002f9fb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002f9fb`
- `bcrypt!BCryptGetProperty` at `0x18002f9a8`
- `bcrypt!BCryptGetProperty` at `0x18002fb48`
- `bcrypt!BCryptGetProperty` at `0x18002f9a8`
- `bcrypt!BCryptGetProperty` at `0x18002fb48`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f973`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f973`

## string_xrefs

- `0x18002fa20`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002fab8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002faec`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002fb54`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002fb93`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002fbd8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002fa49`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
__int64 __fastcall GetSupportedKeyLengths(
        const unsigned __int16 *a1,
        struct __BCRYPT_KEY_LENGTHS_STRUCT *a2,
        UCHAR *a3)
{
  unsigned int Property; // edi
  ULONG v6; // eax
  const char *v8; // r9
  char v9; // al
  const char *v10; // rcx
  bool v11; // zf
  char v12; // al
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  ULONG *pcbResult; // [rsp+20h] [rbp-68h]
  int pcbResulta; // [rsp+20h] [rbp-68h]
  ULONG *pcbResultb; // [rsp+20h] [rbp-68h]
  const char *dwFlags; // [rsp+28h] [rbp-60h]
  ULONG v21; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-40h] BYREF
  UCHAR pbOutput[8]; // [rsp+50h] [rbp-38h] BYREF
  ULONG v24; // [rsp+58h] [rbp-30h]

  *(_QWORD *)pbOutput = 0;
  phAlgorithm = 0;
  v24 = 0;
  v21 = 0;
  if ( !a2 )
  {
    Property = -1073741811;
    v8 = "";
    while ( 1 )
    {
      v12 = *(v8 - 1);
      v10 = v8--;
      v11 = v12 == 92;
      if ( v12 == 92 )
        break;
      if ( v8 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v11 = v12 == 92;
        break;
      }
    }
    dwFlags = "InvalidArgs";
    pcbResulta = 469;
    goto LABEL_17;
  }
  if ( a3 )
    *(_DWORD *)a3 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property )
  {
    v8 = "";
    while ( 1 )
    {
      v9 = *(v8 - 1);
      v10 = v8--;
      v11 = v9 == 92;
      if ( v9 == 92 )
        break;
      if ( v8 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v11 = v9 == 92;
        break;
      }
    }
    dwFlags = "BCryptOpenAlgorithmProvider";
    pcbResulta = 483;
LABEL_17:
    if ( v11 )
      v8 = v10;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v8, pcbResulta, dwFlags, &Class);
    goto LABEL_9;
  }
  Property = BCryptGetProperty(phAlgorithm, L"KeyLengths", pbOutput, 0xCu, &v21, 0);
  if ( Property )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
    LODWORD(pcbResult) = 493;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v13, pcbResult, "BCryptGetProperty", &Class);
  }
  else if ( v21 == 12 )
  {
    if ( !a3 )
    {
LABEL_8:
      v6 = v24;
      *(_QWORD *)&a2->dwMinLength = *(_QWORD *)pbOutput;
      a2->dwIncrement = v6;
      goto LABEL_9;
    }
    Property = BCryptGetProperty(phAlgorithm, L"BlockLength", a3, 4u, &v21, 0);
    if ( Property )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      LODWORD(pcbResultb) = 511;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v15, pcbResultb, "BCryptGetProperty", &Class);
    }
    else
    {
      if ( v21 == 4 )
        goto LABEL_8;
      Property = -1073741595;
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      LODWORD(pcbResultb) = 516;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v16, pcbResultb, "BCryptGetProperty", &Class);
    }
  }
  else
  {
    Property = -1073741595;
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
    LODWORD(pcbResult) = 498;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v14, pcbResult, "BCryptGetProperty", &Class);
  }
LABEL_9:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return Property;
}

```

## disassembly

```asm
0x18002f910  mov     r11, rsp
0x18002f913  push    rdi
0x18002f914  sub     rsp, 80h
0x18002f91b  mov     rax, cs:__security_cookie
0x18002f922  xor     rax, rsp
0x18002f925  mov     [rsp+88h+var_28], rax
0x18002f92a  mov     [r11+8], rbx
0x18002f92e  xor     eax, eax
0x18002f930  mov     [r11-10h], rbp
0x18002f934  mov     rbx, r8
0x18002f937  xor     ebp, ebp
0x18002f939  mov     [r11-18h], rsi
0x18002f93d  mov     [r11-38h], rax
0x18002f941  mov     rsi, rdx
0x18002f944  mov     [r11-40h], rbp
0x18002f948  mov     [rsp+88h+var_30], eax
0x18002f94c  mov     [rsp+88h+var_48], ebp
0x18002f950  test    rdx, rdx
0x18002f953  jz      loc_18002FBCC
0x18002f959  test    rbx, rbx
0x18002f95c  jz      short loc_18002F961
0x18002f95e  mov     [r8], ebp
0x18002f961  xor     r9d, r9d; dwFlags
0x18002f964  lea     rdx, aAes; "AES"
0x18002f96b  xor     r8d, r8d; pszImplementation
0x18002f96e  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x18002f973  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002f979  mov     edi, eax
0x18002f97b  test    eax, eax
0x18002f97d  jnz     loc_18002FA19
0x18002f983  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x18002f988  lea     rax, [rsp+88h+var_48]
0x18002f98d  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x18002f991  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18002f996  mov     r9d, 0Ch; cbOutput
0x18002f99c  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18002f9a1  lea     rdx, aKeylengths; "KeyLengths"
0x18002f9a8  call    cs:__imp_BCryptGetProperty
0x18002f9ae  mov     edi, eax
0x18002f9b0  test    eax, eax
0x18002f9b2  jnz     loc_18002FAB8
0x18002f9b8  cmp     [rsp+88h+var_48], 0Ch
0x18002f9bd  jnz     loc_18002FAEC
0x18002f9c3  test    rbx, rbx
0x18002f9c6  jnz     loc_18002FB25
0x18002f9cc  movsd   xmm0, qword ptr [rsp+88h+pbOutput]
0x18002f9d2  mov     eax, [rsp+88h+var_30]
0x18002f9d6  movsd   qword ptr [rsi], xmm0
0x18002f9da  mov     [rsi+8], eax
0x18002f9dd  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18002f9e2  mov     rsi, [rsp+88h+var_18]
0x18002f9e7  mov     rbp, [rsp+88h+var_10]
0x18002f9ec  mov     rbx, [rsp+88h+arg_0]
0x18002f9f4  test    rcx, rcx
0x18002f9f7  jz      short loc_18002FA01
0x18002f9f9  xor     edx, edx; dwFlags
0x18002f9fb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002fa01  mov     eax, edi
0x18002fa03  mov     rcx, [rsp+88h+var_28]
0x18002fa08  xor     rcx, rsp; StackCookie
0x18002fa0b  call    __security_check_cookie
0x18002fa10  add     rsp, 80h
0x18002fa17  pop     rdi
0x18002fa18  retn
0x18002fa19  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18002fa20  lea     rdx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002fa27  movzx   eax, byte ptr [r9-1]
0x18002fa2c  mov     rcx, r9
0x18002fa2f  dec     r9
0x18002fa32  cmp     al, 5Ch ; '\'
0x18002fa34  jz      short loc_18002FA3D
0x18002fa36  cmp     r9, rdx
0x18002fa39  ja      short loc_18002FA27
0x18002fa3b  cmp     al, 5Ch ; '\'
0x18002fa3d  lea     rax, Class
0x18002fa44  mov     [rsp+88h+var_58], rax
0x18002fa49  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x18002fa50  mov     qword ptr [rsp+88h+dwFlags], rax
0x18002fa55  mov     dword ptr [rsp+88h+pcbResult], 1E3h
0x18002fa5d  cmovz   r9, rcx
0x18002fa61  mov     r8d, edi
0x18002fa64  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002fa6b  xor     ecx, ecx
0x18002fa6d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002fa72  jmp     loc_18002F9DD
0x18002fa80  movzx   eax, byte ptr [r9-1]
0x18002fa85  mov     rcx, r9
0x18002fa88  dec     r9
0x18002fa8b  cmp     al, 5Ch ; '\'
0x18002fa8d  jz      short loc_18002FA96
0x18002fa8f  cmp     r9, rdx
0x18002fa92  ja      short loc_18002FA80
0x18002fa94  cmp     al, 5Ch ; '\'
0x18002fa96  lea     rax, Class
0x18002fa9d  mov     [rsp+88h+var_58], rax
0x18002faa2  lea     rax, aInvalidargs; "InvalidArgs"
0x18002faa9  mov     qword ptr [rsp+88h+dwFlags], rax
0x18002faae  mov     dword ptr [rsp+88h+pcbResult], 1D5h
0x18002fab6  jmp     short loc_18002FA5D
0x18002fab8  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002fabf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002fac4  mov     r9, rax
0x18002fac7  lea     rax, Class
0x18002face  mov     [rsp+88h+var_58], rax
0x18002fad3  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18002fada  mov     qword ptr [rsp+88h+dwFlags], rax
0x18002fadf  mov     dword ptr [rsp+88h+pcbResult], 1EDh
0x18002fae7  jmp     loc_18002FA61
0x18002faec  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002faf3  mov     edi, 0C00000E5h
0x18002faf8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002fafd  mov     r9, rax
0x18002fb00  lea     rax, Class
0x18002fb07  mov     [rsp+88h+var_58], rax
0x18002fb0c  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18002fb13  mov     qword ptr [rsp+88h+dwFlags], rax
0x18002fb18  mov     dword ptr [rsp+88h+pcbResult], 1F2h
0x18002fb20  jmp     loc_18002FA61
0x18002fb25  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x18002fb2a  lea     rax, [rsp+88h+var_48]
0x18002fb2f  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x18002fb33  lea     rdx, aBlocklength; "BlockLength"
0x18002fb3a  mov     r9d, 4; cbOutput
0x18002fb40  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18002fb45  mov     r8, rbx; pbOutput
0x18002fb48  call    cs:__imp_BCryptGetProperty
0x18002fb4e  mov     edi, eax
0x18002fb50  test    eax, eax
0x18002fb52  jz      short loc_18002FB88
0x18002fb54  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002fb5b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002fb60  mov     r9, rax
0x18002fb63  lea     rax, Class
0x18002fb6a  mov     [rsp+88h+var_58], rax
0x18002fb6f  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18002fb76  mov     qword ptr [rsp+88h+dwFlags], rax
0x18002fb7b  mov     dword ptr [rsp+88h+pcbResult], 1FFh
0x18002fb83  jmp     loc_18002FA61
0x18002fb88  cmp     [rsp+88h+var_48], 4
0x18002fb8d  jz      loc_18002F9CC
0x18002fb93  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002fb9a  mov     edi, 0C00000E5h
0x18002fb9f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002fba4  mov     r9, rax
0x18002fba7  lea     rax, Class
0x18002fbae  mov     [rsp+88h+var_58], rax
0x18002fbb3  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18002fbba  mov     qword ptr [rsp+88h+dwFlags], rax
0x18002fbbf  mov     dword ptr [rsp+88h+pcbResult], 204h
0x18002fbc7  jmp     loc_18002FA61
0x18002fbcc  mov     edi, 0C000000Dh
0x18002fbd1  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18002fbd8  lea     rdx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002fbdf  jmp     loc_18002FA80
```
