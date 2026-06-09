# GetBufferChecksumSize(ushort const *,ulong *)

- ea: `0x18002b090`
- end: `0x18002b250`
- name: `?GetBufferChecksumSize@@YAJPEBGPEAK@Z`
- size: `448`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180061600`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002b090`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002b13b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002b13b`
- `bcrypt!BCryptGetProperty` at `0x18002b104`
- `bcrypt!BCryptGetProperty` at `0x18002b104`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002b0cf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002b0cf`

## string_xrefs

- `0x18002b19d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002b1ce`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002b1ff`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002b244`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18002b1b8`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
__int64 __fastcall GetBufferChecksumSize(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int Property; // ebx
  char v5; // al
  const char *v6; // rcx
  const char *v7; // r9
  bool v8; // zf
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  ULONG *pcbResult; // [rsp+20h] [rbp-38h]
  ULONG v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+64h] [rbp+Ch]
  unsigned int pbOutput; // [rsp+70h] [rbp+18h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+78h] [rbp+20h] BYREF

  v14 = HIDWORD(a1);
  hObject = 0;
  pbOutput = 0;
  v13 = 0;
  if ( a2 )
  {
    *a2 = 0;
    Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", 0, 0);
    if ( Property )
    {
      v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v9, 667, "BCryptOpenAlgorithmProvider", &Class);
    }
    else
    {
      Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &v13, 0);
      if ( Property )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
        LODWORD(pcbResult) = 677;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v10, pcbResult, "BCryptGetProperty", &Class);
      }
      else if ( v13 == 4 )
      {
        *a2 = pbOutput;
      }
      else
      {
        Property = -1073741595;
        v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
        LODWORD(pcbResult) = 682;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v11, pcbResult, "BCryptGetProperty", &Class);
      }
    }
  }
  else
  {
    Property = -1073741811;
    v7 = "";
    while ( 1 )
    {
      v5 = *(v7 - 1);
      v6 = v7--;
      v8 = v5 == 92;
      if ( v5 == 92 )
        break;
      if ( v7 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v8 = v5 == 92;
        break;
      }
    }
    if ( v8 )
      v7 = v6;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v7, 656, "InvalidArgs", &Class);
  }
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  return Property;
}

```

## disassembly

```asm
0x18002b090  mov     rax, rsp
0x18002b093  mov     [rax+8], rcx
0x18002b097  push    rbx
0x18002b098  sub     rsp, 50h
0x18002b09c  mov     [rax-10h], rsi
0x18002b0a0  xor     esi, esi
0x18002b0a2  mov     [rax-18h], rdi
0x18002b0a6  mov     rdi, rdx
0x18002b0a9  mov     [rax+20h], rsi
0x18002b0ad  mov     [rax+18h], esi
0x18002b0b0  mov     [rax+8], esi
0x18002b0b3  test    rdx, rdx
0x18002b0b6  jz      loc_18002B238
0x18002b0bc  mov     [rdx], esi
0x18002b0be  lea     rcx, [rax+20h]; phAlgorithm
0x18002b0c2  lea     rdx, pszAlgId; "SHA256"
0x18002b0c9  xor     r9d, r9d; dwFlags
0x18002b0cc  xor     r8d, r8d; pszImplementation
0x18002b0cf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002b0d5  mov     ebx, eax
0x18002b0d7  test    eax, eax
0x18002b0d9  jnz     loc_18002B19D
0x18002b0df  mov     rcx, [rsp+58h+hObject]; hObject
0x18002b0e4  lea     rax, [rsp+58h+arg_0]
0x18002b0e9  mov     [rsp+58h+dwFlags], esi; dwFlags
0x18002b0ed  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x18002b0f2  mov     r9d, 4; cbOutput
0x18002b0f8  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18002b0fd  lea     rdx, pszProperty; "HashDigestLength"
0x18002b104  call    cs:__imp_BCryptGetProperty
0x18002b10a  mov     ebx, eax
0x18002b10c  test    eax, eax
0x18002b10e  jnz     loc_18002B1CE
0x18002b114  cmp     [rsp+58h+arg_0], 4
0x18002b119  jnz     loc_18002B1FF
0x18002b11f  mov     eax, [rsp+58h+pbOutput]
0x18002b123  mov     [rdi], eax
0x18002b125  mov     rcx, [rsp+58h+hObject]; hAlgorithm
0x18002b12a  mov     rdi, [rsp+58h+var_18]
0x18002b12f  mov     rsi, [rsp+58h+var_10]
0x18002b134  test    rcx, rcx
0x18002b137  jz      short loc_18002B141
0x18002b139  xor     edx, edx; dwFlags
0x18002b13b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002b141  mov     eax, ebx
0x18002b143  add     rsp, 50h
0x18002b147  pop     rbx
0x18002b148  retn
0x18002b150  movzx   eax, byte ptr [r9-1]
0x18002b155  mov     rcx, r9
0x18002b158  dec     r9
0x18002b15b  cmp     al, 5Ch ; '\'
0x18002b15d  jz      short loc_18002B166
0x18002b15f  cmp     r9, rdx
0x18002b162  ja      short loc_18002B150
0x18002b164  cmp     al, 5Ch ; '\'
0x18002b166  lea     rax, Class
0x18002b16d  cmovz   r9, rcx
0x18002b171  mov     [rsp+58h+var_28], rax
0x18002b176  lea     rax, aInvalidargs; "InvalidArgs"
0x18002b17d  mov     qword ptr [rsp+58h+dwFlags], rax
0x18002b182  mov     dword ptr [rsp+58h+pcbResult], 290h
0x18002b18a  mov     r8d, ebx
0x18002b18d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002b194  xor     ecx, ecx
0x18002b196  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002b19b  jmp     short loc_18002B125
0x18002b19d  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002b1a4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002b1a9  mov     r9, rax
0x18002b1ac  lea     rax, Class
0x18002b1b3  mov     [rsp+58h+var_28], rax
0x18002b1b8  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x18002b1bf  mov     qword ptr [rsp+58h+dwFlags], rax
0x18002b1c4  mov     dword ptr [rsp+58h+pcbResult], 29Bh
0x18002b1cc  jmp     short loc_18002B18A
0x18002b1ce  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002b1d5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002b1da  mov     r9, rax
0x18002b1dd  lea     rax, Class
0x18002b1e4  mov     [rsp+58h+var_28], rax
0x18002b1e9  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18002b1f0  mov     qword ptr [rsp+58h+dwFlags], rax
0x18002b1f5  mov     dword ptr [rsp+58h+pcbResult], 2A5h
0x18002b1fd  jmp     short loc_18002B18A
0x18002b1ff  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002b206  mov     ebx, 0C00000E5h
0x18002b20b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002b210  mov     r9, rax
0x18002b213  lea     rax, Class
0x18002b21a  mov     [rsp+58h+var_28], rax
0x18002b21f  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18002b226  mov     qword ptr [rsp+58h+dwFlags], rax
0x18002b22b  mov     dword ptr [rsp+58h+pcbResult], 2AAh
0x18002b233  jmp     loc_18002B18A
0x18002b238  mov     ebx, 0C000000Dh
0x18002b23d  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18002b244  lea     rdx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002b24b  jmp     loc_18002B150
```
