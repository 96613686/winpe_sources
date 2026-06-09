# TestSAMNameOk(void *,_UNICODE_STRING *)

- ea: `0x180030ff0`
- end: `0x18003125a`
- name: `?TestSAMNameOk@@YAHPEAXPEAU_UNICODE_STRING@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180030ff0`
- `0x180031494`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800310e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800310e9`

## string_xrefs

- `0x180031081`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180031106`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180031162`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003118d`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180031202`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003111b`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall TestSAMNameOk(HKEY *a1, struct _UNICODE_STRING *a2)
{
  const unsigned __int16 *Buffer; // rcx
  __int64 MaximumLength; // r9
  unsigned __int64 Length; // rdx
  HKEY v6; // rsi
  LPCWSTR v7; // rdi
  int UserSAMNameSubKey; // ebx
  const char *v9; // rax
  const WCHAR *v10; // rsi
  const char *v11; // rax
  __int64 v12; // r8
  const char *v13; // r9
  const char *v14; // r9
  const char *v16; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-38h]
  PHKEY phkResulta; // [rsp+20h] [rbp-38h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  if ( a1
    && a2
    && (Buffer = a2->Buffer) != 0
    && a2->Length
    && (MaximumLength = a2->MaximumLength, (_WORD)MaximumLength)
    && (Length = a2->Length, Length <= MaximumLength - 2)
    && !Buffer[Length >> 1] )
  {
    v6 = *a1;
    v7 = 0;
    lpSubKey = 0;
    hKey = 0;
    if ( v6 )
    {
      UserSAMNameSubKey = GetUserSAMNameSubKey(Buffer, (unsigned __int16 **)&lpSubKey);
      if ( UserSAMNameSubKey )
      {
        v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)UserSAMNameSubKey,
          v9,
          1587,
          "GetUserSAMNameSubKey",
          &Class);
        v7 = lpSubKey;
      }
      else
      {
        v7 = lpSubKey;
        UserSAMNameSubKey = RegOpenKeyExW(v6, lpSubKey, 0, 0x20019u, &hKey);
        if ( UserSAMNameSubKey )
        {
          v10 = &Class;
          v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResult) = 1597;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)UserSAMNameSubKey,
            v11,
            phkResult,
            "RegOpenKeyExW",
            v12);
          if ( (unsigned int)(UserSAMNameSubKey - 2) <= 1 )
          {
            UserSAMNameSubKey = -1073741275;
          }
          else if ( UserSAMNameSubKey > 0 )
          {
            UserSAMNameSubKey = (unsigned __int16)UserSAMNameSubKey | 0xC0070000;
          }
          if ( v7 )
            v10 = v7;
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResulta) = 1607;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)UserSAMNameSubKey,
            v13,
            phkResulta,
            "RegOpenKeyExW",
            v10);
        }
        else
        {
          UserSAMNameSubKey = 0;
        }
      }
    }
    else
    {
      UserSAMNameSubKey = -1073741811;
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v14, 1581, "Invalid Arg(s)", &Class);
    }
    if ( v7 )
      ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v7);
    if ( UserSAMNameSubKey < 0 )
      return 1;
    RegCloseKey(hKey);
  }
  else
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v16, 869, "Internal Error!!Invalid Arg(s)", &Class);
  }
  return 0;
}

```

## disassembly

```asm
0x180030ff0  mov     r11, rsp
0x180030ff3  mov     [r11+10h], rbx
0x180030ff7  mov     [r11+20h], rbp
0x180030ffb  push    rsi
0x180030ffc  push    rdi
0x180030ffd  push    r14
0x180030fff  sub     rsp, 40h
0x180031003  xor     ebp, ebp
0x180031005  mov     r8, rcx
0x180031008  test    rcx, rcx
0x18003100b  jz      loc_180031202
0x180031011  test    rdx, rdx
0x180031014  jz      loc_180031202
0x18003101a  mov     rcx, [rdx+8]; unsigned __int16 *
0x18003101e  test    rcx, rcx
0x180031021  jz      loc_180031202
0x180031027  cmp     bp, [rdx]
0x18003102a  jz      loc_180031202
0x180031030  movzx   r9d, word ptr [rdx+2]
0x180031035  cmp     bp, r9w
0x180031039  jz      loc_180031202
0x18003103f  movzx   edx, word ptr [rdx]
0x180031042  lea     rax, [r9-2]
0x180031046  cmp     rdx, rax
0x180031049  ja      loc_180031202
0x18003104f  shr     rdx, 1
0x180031052  cmp     [rcx+rdx*2], bp
0x180031056  jnz     loc_180031202
0x18003105c  mov     rsi, [r8]
0x18003105f  mov     edi, ebp
0x180031061  mov     [r11+8], rbp
0x180031065  mov     [r11+18h], rbp
0x180031069  test    rsi, rsi
0x18003106c  jz      loc_18003118D
0x180031072  lea     rdx, [r11+8]; unsigned __int16 **
0x180031076  call    ?GetUserSAMNameSubKey@@YAJPEBGPEAPEAG@Z; GetUserSAMNameSubKey(ushort const *,ushort * *)
0x18003107b  mov     ebx, eax
0x18003107d  test    eax, eax
0x18003107f  jz      short loc_1800310CB
0x180031081  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031088  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003108d  mov     r9, rax
0x180031090  lea     rsi, Class
0x180031097  lea     rax, aGetusersamname; "GetUserSAMNameSubKey"
0x18003109e  mov     [rsp+58h+var_28], rsi
0x1800310a3  mov     [rsp+58h+var_30], rax
0x1800310a8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800310af  mov     r8d, ebx
0x1800310b2  mov     dword ptr [rsp+58h+phkResult], 633h
0x1800310ba  xor     ecx, ecx
0x1800310bc  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800310c1  mov     rdi, [rsp+58h+lpSubKey]
0x1800310c6  jmp     loc_1800311D2
0x1800310cb  mov     rdi, [rsp+58h+lpSubKey]
0x1800310d0  lea     rax, [rsp+58h+hKey]
0x1800310d5  mov     rdx, rdi; lpSubKey
0x1800310d8  mov     [rsp+58h+phkResult], rax; phkResult
0x1800310dd  mov     r9d, 20019h; samDesired
0x1800310e3  xor     r8d, r8d; ulOptions
0x1800310e6  mov     rcx, rsi; hKey
0x1800310e9  call    cs:__imp_RegOpenKeyExW
0x1800310ef  mov     ebx, eax
0x1800310f1  test    eax, eax
0x1800310f3  jz      loc_180031189
0x1800310f9  lea     rsi, Class
0x180031100  test    rdi, rdi
0x180031103  mov     r8, rsi
0x180031106  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003110d  cmovnz  r8, rdi
0x180031111  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180031116  mov     [rsp+58h+var_28], r8
0x18003111b  lea     r14, aRegopenkeyexw; "RegOpenKeyExW"
0x180031122  mov     [rsp+58h+var_30], r14
0x180031127  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003112e  mov     r9, rax
0x180031131  mov     dword ptr [rsp+58h+phkResult], 63Dh
0x180031139  mov     r8d, ebx
0x18003113c  xor     ecx, ecx
0x18003113e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180031143  lea     eax, [rbx-2]
0x180031146  cmp     eax, 1
0x180031149  jbe     short loc_18003115A
0x18003114b  test    ebx, ebx
0x18003114d  jle     short loc_18003115F
0x18003114f  movzx   ebx, bx
0x180031152  or      ebx, 0C0070000h
0x180031158  jmp     short loc_18003115F
0x18003115a  mov     ebx, 0C0000225h
0x18003115f  test    rdi, rdi
0x180031162  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031169  cmovnz  rsi, rdi
0x18003116d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180031172  mov     [rsp+58h+var_28], rsi
0x180031177  mov     r9, rax
0x18003117a  mov     [rsp+58h+var_30], r14
0x18003117f  mov     dword ptr [rsp+58h+phkResult], 647h
0x180031187  jmp     short loc_1800311C1
0x180031189  mov     ebx, ebp
0x18003118b  jmp     short loc_1800311D2
0x18003118d  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031194  mov     ebx, 0C000000Dh
0x180031199  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003119e  mov     r9, rax
0x1800311a1  lea     rsi, Class
0x1800311a8  mov     [rsp+58h+var_28], rsi
0x1800311ad  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x1800311b4  mov     [rsp+58h+var_30], rax
0x1800311b9  mov     dword ptr [rsp+58h+phkResult], 62Dh
0x1800311c1  mov     r8d, ebx
0x1800311c4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800311cb  xor     ecx, ecx
0x1800311cd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800311d2  test    rdi, rdi
0x1800311d5  jz      short loc_1800311EA
0x1800311d7  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800311de  mov     rcx, rdi
0x1800311e1  mov     rax, [rax+30h]
0x1800311e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311ea  test    ebx, ebx
0x1800311ec  js      short loc_1800311FB
0x1800311ee  mov     rcx, [rsp+58h+hKey]; hKey
0x1800311f3  call    cs:__imp_RegCloseKey
0x1800311f9  jmp     short loc_180031245
0x1800311fb  mov     eax, 1
0x180031200  jmp     short loc_180031247
0x180031202  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180031209  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003120e  mov     r9, rax
0x180031211  lea     rsi, Class
0x180031218  lea     rax, aInternalErrorI; "Internal Error!!Invalid Arg(s)"
0x18003121f  mov     [rsp+58h+var_28], rsi
0x180031224  mov     [rsp+58h+var_30], rax
0x180031229  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180031230  mov     r8d, 0C000000Dh
0x180031236  mov     dword ptr [rsp+58h+phkResult], 365h
0x18003123e  xor     ecx, ecx
0x180031240  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180031245  xor     eax, eax
0x180031247  mov     rbx, [rsp+58h+arg_8]
0x18003124c  mov     rbp, [rsp+58h+arg_18]
0x180031251  add     rsp, 40h
0x180031255  pop     r14
0x180031257  pop     rdi
0x180031258  pop     rsi
0x180031259  retn
```
