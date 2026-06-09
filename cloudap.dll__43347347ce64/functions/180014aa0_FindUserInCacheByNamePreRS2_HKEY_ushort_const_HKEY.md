# FindUserInCacheByNamePreRS2(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x180014aa0`
- end: `0x180014d85`
- name: `?FindUserInCacheByNamePreRS2@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `741`
- prototype: `__int64 __fastcall(HKEY hKey, PUCHAR pbInput, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18004e3b4`
- `0x18004f600`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180014aa0`
- `0x1800156f0`
- `0x180042410`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014b54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014b54`

## string_xrefs

- `0x180014b6e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014c45`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014ca7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014d0a`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014d3b`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014b17`: `Name2Sid`
- `0x180014b99`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall FindUserInCacheByNamePreRS2(HKEY hKey, PUCHAR pbInput, PHKEY phkResult)
{
  unsigned int HashStringPreRS2; // ebp
  unsigned int v6; // edi
  const UCHAR *v7; // rbx
  const UCHAR *v8; // r9
  char v9; // al
  const UCHAR *v10; // rcx
  bool v11; // zf
  char v12; // cl
  const UCHAR *v13; // rdx
  bool v14; // zf
  const UCHAR *v16; // rbx
  char v17; // al
  const UCHAR *v18; // rcx
  bool v19; // zf
  const UCHAR *v20; // rbx
  char v21; // cl
  const UCHAR *v22; // rdx
  bool v23; // zf
  const char *v24; // r9
  const char *v25; // r9
  PHKEY phkResulta; // [rsp+20h] [rbp-178h]
  PHKEY phkResultb; // [rsp+20h] [rbp-178h]
  PHKEY phkResultc; // [rsp+20h] [rbp-178h]
  WCHAR SubKey[80]; // [rsp+40h] [rbp-158h] BYREF
  unsigned __int16 v30[72]; // [rsp+E0h] [rbp-B8h] BYREF

  if ( !phkResult )
  {
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v24, 1194, "Invalid out arg", &Class);
    return 3221225485LL;
  }
  *phkResult = 0;
  if ( !hKey || !pbInput )
  {
    v20 = "";
    while ( 1 )
    {
      v21 = *(v20 - 1);
      v22 = v20--;
      v23 = v21 == 92;
      if ( v21 == 92 )
        break;
      if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v23 = v21 == 92;
        break;
      }
    }
    if ( v23 )
      v20 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v20, 1202, "Invalid Arg(s)", &Class);
    return 3221225485LL;
  }
  HashStringPreRS2 = GetHashStringPreRS2(pbInput, v30);
  if ( HashStringPreRS2 )
  {
    v16 = "";
    while ( 1 )
    {
      v17 = *(v16 - 1);
      v18 = v16--;
      v19 = v17 == 92;
      if ( v17 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v19 = v17 == 92;
        break;
      }
    }
    if ( v19 )
      v16 = v18;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v16, 1208, "GetHashString", &Class);
    return HashStringPreRS2;
  }
  HashStringPreRS2 = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v30);
  if ( HashStringPreRS2 )
  {
    v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(phkResulta) = 1216;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v25, phkResulta, "RtlStringCchPrintfW", &Class);
    return HashStringPreRS2;
  }
  v6 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, phkResult);
  if ( !v6 )
    return 0;
  v7 = "";
  v8 = "";
  while ( 1 )
  {
    v9 = *(v8 - 1);
    v10 = v8--;
    v11 = v9 == 92;
    if ( v9 == 92 )
      break;
    if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
    {
      v11 = v9 == 92;
      break;
    }
  }
  if ( v11 )
    v8 = v10;
  LODWORD(phkResultb) = 1226;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v8, phkResultb, "RegOpenKeyExW", SubKey);
  if ( v6 - 2 > 1 )
  {
    if ( (int)v6 > 0 )
      v6 = (unsigned __int16)v6 | 0xC0070000;
  }
  else
  {
    v6 = -1073741275;
  }
  while ( 1 )
  {
    v12 = *(v7 - 1);
    v13 = v7--;
    v14 = v12 == 92;
    if ( v12 == 92 )
      break;
    if ( v7 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
    {
      v14 = v12 == 92;
      break;
    }
  }
  if ( v14 )
    v7 = v13;
  LODWORD(phkResultc) = 1236;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v7, phkResultc, "RegOpenKeyExW", SubKey);
  return v6;
}

```

## disassembly

```asm
0x180014aa0  push    rbx
0x180014aa2  push    rsi
0x180014aa3  push    rdi
0x180014aa4  sub     rsp, 180h
0x180014aab  mov     rax, cs:__security_cookie
0x180014ab2  xor     rax, rsp
0x180014ab5  mov     [rsp+198h+var_28], rax
0x180014abd  mov     rbx, r8
0x180014ac0  mov     rax, rdx
0x180014ac3  mov     rdi, rcx
0x180014ac6  test    r8, r8
0x180014ac9  jz      loc_180014D0A
0x180014acf  mov     qword ptr [r8], 0
0x180014ad6  test    rcx, rcx
0x180014ad9  jz      loc_180014CA0
0x180014adf  test    rdx, rdx
0x180014ae2  jz      loc_180014CA0
0x180014ae8  lea     rdx, [rsp+198h+var_B8]; unsigned __int16 *
0x180014af0  mov     [rsp+198h+arg_18], rbp
0x180014af8  mov     rcx, rax; pbInput
0x180014afb  call    ?GetHashStringPreRS2@@YAJPEBGQEAG@Z; GetHashStringPreRS2(ushort const *,ushort * const)
0x180014b00  mov     ebp, eax
0x180014b02  test    eax, eax
0x180014b04  jnz     loc_180014C3E
0x180014b0a  lea     rax, [rsp+198h+var_B8]
0x180014b12  mov     edx, 4Ah ; 'J'; unsigned __int64
0x180014b17  lea     r9, aName2sid; "Name2Sid"
0x180014b1e  mov     [rsp+198h+phkResult], rax
0x180014b23  lea     r8, aWsWs_1; "%ws\\%ws"
0x180014b2a  lea     rcx, [rsp+198h+SubKey]; unsigned __int16 *
0x180014b2f  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014b34  mov     ebp, eax
0x180014b36  test    eax, eax
0x180014b38  jnz     loc_180014D3B
0x180014b3e  mov     r9d, 20019h; samDesired
0x180014b44  mov     [rsp+198h+phkResult], rbx; phkResult
0x180014b49  xor     r8d, r8d; ulOptions
0x180014b4c  lea     rdx, [rsp+198h+SubKey]; lpSubKey
0x180014b51  mov     rcx, rdi; hKey
0x180014b54  call    cs:__imp_RegOpenKeyExW
0x180014b5a  mov     edi, eax
0x180014b5c  test    eax, eax
0x180014b5e  jz      loc_180014C3A
0x180014b64  lea     rbx, pbInput+24h; ""
0x180014b6b  mov     r9, rbx
0x180014b6e  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014b75  movzx   eax, byte ptr [r9-1]
0x180014b7a  mov     rcx, r9
0x180014b7d  dec     r9
0x180014b80  cmp     al, 5Ch ; '\'
0x180014b82  jz      short loc_180014B8B
0x180014b84  cmp     r9, rsi
0x180014b87  ja      short loc_180014B75
0x180014b89  cmp     al, 5Ch ; '\'
0x180014b8b  lea     rax, [rsp+198h+SubKey]
0x180014b90  cmovz   r9, rcx
0x180014b94  mov     [rsp+198h+var_168], rax
0x180014b99  lea     rbp, aRegopenkeyexw; "RegOpenKeyExW"
0x180014ba0  mov     [rsp+198h+var_170], rbp
0x180014ba5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180014bac  mov     r8d, edi
0x180014baf  mov     dword ptr [rsp+198h+phkResult], 4CAh
0x180014bb7  xor     ecx, ecx
0x180014bb9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180014bbe  lea     eax, [rdi-2]
0x180014bc1  cmp     eax, 1
0x180014bc4  ja      loc_180014D6F
0x180014bca  mov     edi, 0C0000225h
0x180014bcf  movzx   ecx, byte ptr [rbx-1]
0x180014bd3  mov     rdx, rbx
0x180014bd6  dec     rbx
0x180014bd9  cmp     cl, 5Ch ; '\'
0x180014bdc  jz      short loc_180014BE6
0x180014bde  cmp     rbx, rsi
0x180014be1  ja      short loc_180014BCF
0x180014be3  cmp     cl, 5Ch ; '\'
0x180014be6  cmovz   rbx, rdx
0x180014bea  lea     rax, [rsp+198h+SubKey]
0x180014bef  mov     [rsp+198h+var_168], rax
0x180014bf4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180014bfb  mov     [rsp+198h+var_170], rbp
0x180014c00  mov     r9, rbx
0x180014c03  mov     r8d, edi
0x180014c06  mov     dword ptr [rsp+198h+phkResult], 4D4h
0x180014c0e  xor     ecx, ecx
0x180014c10  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180014c15  mov     eax, edi
0x180014c17  mov     rbp, [rsp+198h+arg_18]
0x180014c1f  mov     rcx, [rsp+198h+var_28]
0x180014c27  xor     rcx, rsp; StackCookie
0x180014c2a  call    __security_check_cookie
0x180014c2f  add     rsp, 180h
0x180014c36  pop     rdi
0x180014c37  pop     rsi
0x180014c38  pop     rbx
0x180014c39  retn
0x180014c3a  xor     eax, eax
0x180014c3c  jmp     short loc_180014C17
0x180014c3e  lea     rbx, pbInput+24h; ""
0x180014c45  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014c4c  movzx   eax, byte ptr [rbx-1]
0x180014c50  mov     rcx, rbx
0x180014c53  dec     rbx
0x180014c56  cmp     al, 5Ch ; '\'
0x180014c58  jz      short loc_180014C61
0x180014c5a  cmp     rbx, rsi
0x180014c5d  ja      short loc_180014C4C
0x180014c5f  cmp     al, 5Ch ; '\'
0x180014c61  lea     rax, Class
0x180014c68  cmovz   rbx, rcx
0x180014c6c  mov     [rsp+198h+var_168], rax
0x180014c71  mov     r9, rbx
0x180014c74  lea     rax, aGethashstring; "GetHashString"
0x180014c7b  mov     [rsp+198h+var_170], rax
0x180014c80  mov     dword ptr [rsp+198h+phkResult], 4B8h
0x180014c88  mov     r8d, ebp
0x180014c8b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180014c92  xor     ecx, ecx
0x180014c94  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180014c99  mov     eax, ebp
0x180014c9b  jmp     loc_180014C17
0x180014ca0  lea     rbx, pbInput+24h; ""
0x180014ca7  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014cae  movzx   ecx, byte ptr [rbx-1]
0x180014cb2  mov     rdx, rbx
0x180014cb5  dec     rbx
0x180014cb8  cmp     cl, 5Ch ; '\'
0x180014cbb  jz      short loc_180014CC5
0x180014cbd  cmp     rbx, rsi
0x180014cc0  ja      short loc_180014CAE
0x180014cc2  cmp     cl, 5Ch ; '\'
0x180014cc5  lea     rax, Class
0x180014ccc  cmovz   rbx, rdx
0x180014cd0  mov     [rsp+198h+var_168], rax
0x180014cd5  mov     r9, rbx
0x180014cd8  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x180014cdf  mov     [rsp+198h+var_170], rax
0x180014ce4  mov     dword ptr [rsp+198h+phkResult], 4B2h
0x180014cec  mov     r8d, 0C000000Dh
0x180014cf2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180014cf9  xor     ecx, ecx
0x180014cfb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180014d00  mov     eax, 0C000000Dh
0x180014d05  jmp     loc_180014C1F
0x180014d0a  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014d11  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014d16  mov     r9, rax
0x180014d19  lea     rax, Class
0x180014d20  mov     [rsp+198h+var_168], rax
0x180014d25  lea     rax, aInvalidOutArg; "Invalid out arg"
0x180014d2c  mov     [rsp+198h+var_170], rax
0x180014d31  mov     dword ptr [rsp+198h+phkResult], 4AAh
0x180014d39  jmp     short loc_180014CEC
0x180014d3b  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014d42  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014d47  mov     r9, rax
0x180014d4a  lea     rax, Class
0x180014d51  mov     [rsp+198h+var_168], rax
0x180014d56  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x180014d5d  mov     [rsp+198h+var_170], rax
0x180014d62  mov     dword ptr [rsp+198h+phkResult], 4C0h
0x180014d6a  jmp     loc_180014C88
0x180014d6f  test    edi, edi
0x180014d71  jle     loc_180014BCF
0x180014d77  movzx   edi, di
0x180014d7a  or      edi, 0C0070000h
0x180014d80  jmp     loc_180014BCF
```
