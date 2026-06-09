# _RemoveUserFromName2SidCache(HKEY__ *,ushort *,bool)

- ea: `0x18003fcdc`
- end: `0x18003ff23`
- name: `?_RemoveUserFromName2SidCache@@YAJPEAUHKEY__@@PEAG_N@Z`
- size: `583`
- prototype: `__int64 __fastcall(HKEY hKey, UCHAR *lpSrcStr, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180004e80`
- `0x180014d90`
- `0x180048e60`
- `0x180052358`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x1800156f0`
- `0x18003fcdc`
- `0x180042410`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003fe59`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003fe59`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003fe0d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003fe0d`

## string_xrefs

- `0x18003fd2e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003fd6d`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003fdd1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003fe24`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003fe70`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003feaf`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003fdae`: `Name2Sid`
- `0x18003fe3d`: `RegDeleteKey`

## pseudocode

```c
__int64 __fastcall _RemoveUserFromName2SidCache(HKEY hKey, UCHAR *lpSrcStr, char a3)
{
  unsigned int HashStringPreRS2; // ebx
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  LSTATUS v8; // eax
  const char *v9; // r9
  LSTATUS v10; // eax
  const char *v11; // r9
  const UCHAR *v12; // r9
  const UCHAR *v13; // rax
  bool v14; // zf
  __int64 v16; // [rsp+20h] [rbp-168h]
  WCHAR SubKey[80]; // [rsp+40h] [rbp-148h] BYREF
  unsigned __int16 v18[72]; // [rsp+E0h] [rbp-A8h] BYREF

  if ( hKey && lpSrcStr )
  {
    if ( a3 )
    {
      HashStringPreRS2 = GetHashStringPreRS2(lpSrcStr, v18);
      if ( HashStringPreRS2 )
      {
        v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v5, 1645, "GetHashString", &Class);
        return HashStringPreRS2;
      }
    }
    else
    {
      HashStringPreRS2 = GetHashString((LPCWSTR)lpSrcStr, v18);
      if ( HashStringPreRS2 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v6, 1652, "GetHashString", &Class);
        return HashStringPreRS2;
      }
    }
    HashStringPreRS2 = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v18);
    if ( HashStringPreRS2 )
    {
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(v16) = 1661;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v7, v16, "RtlStringCchPrintfW", &Class);
    }
    else
    {
      v8 = RegDeleteKeyW(hKey, SubKey);
      HashStringPreRS2 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          HashStringPreRS2 = (unsigned __int16)v8 | 0xC0070000;
        v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(v16) = 1669;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v9, v16, "RegDeleteKey", SubKey);
      }
      else
      {
        v10 = RegFlushKey(hKey);
        HashStringPreRS2 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            HashStringPreRS2 = (unsigned __int16)v10 | 0xC0070000;
          v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(v16) = 1676;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v11, v16, "RegFlushKey", SubKey);
        }
        else
        {
          return 0;
        }
      }
    }
  }
  else
  {
    HashStringPreRS2 = -1073741811;
    v12 = "";
    while ( 1 )
    {
      v13 = v12--;
      v14 = *v12 == 92;
      if ( *v12 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v14 = *v12 == 92;
        break;
      }
    }
    if ( v14 )
      v12 = v13;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v12, 1637, "Invalid Arg(s)", &Class);
  }
  return HashStringPreRS2;
}

```

## disassembly

```asm
0x18003fcdc  mov     [rsp+arg_10], rbx
0x18003fce1  push    rdi
0x18003fce2  sub     rsp, 180h
0x18003fce9  mov     rax, cs:__security_cookie
0x18003fcf0  xor     rax, rsp
0x18003fcf3  mov     [rsp+188h+var_18], rax
0x18003fcfb  mov     rax, rdx
0x18003fcfe  mov     rdi, rcx
0x18003fd01  test    rcx, rcx
0x18003fd04  jz      loc_18003FEA3
0x18003fd0a  test    rax, rax
0x18003fd0d  jz      loc_18003FEA3
0x18003fd13  lea     rdx, [rsp+188h+var_A8]; unsigned __int16 *
0x18003fd1b  mov     rcx, rax; lpSrcStr
0x18003fd1e  test    r8b, r8b
0x18003fd21  jz      short loc_18003FD62
0x18003fd23  call    ?GetHashStringPreRS2@@YAJPEBGQEAG@Z; GetHashStringPreRS2(ushort const *,ushort * const)
0x18003fd28  mov     ebx, eax
0x18003fd2a  test    eax, eax
0x18003fd2c  jz      short loc_18003FDA1
0x18003fd2e  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003fd35  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fd3a  mov     r9, rax
0x18003fd3d  lea     rax, Class
0x18003fd44  mov     [rsp+188h+var_158], rax
0x18003fd49  lea     rax, aGethashstring; "GetHashString"
0x18003fd50  mov     [rsp+188h+var_160], rax
0x18003fd55  mov     dword ptr [rsp+188h+var_168], 66Dh
0x18003fd5d  jmp     loc_18003FEEF
0x18003fd62  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18003fd67  mov     ebx, eax
0x18003fd69  test    eax, eax
0x18003fd6b  jz      short loc_18003FDA1
0x18003fd6d  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003fd74  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fd79  mov     r9, rax
0x18003fd7c  lea     rax, Class
0x18003fd83  mov     [rsp+188h+var_158], rax
0x18003fd88  lea     rax, aGethashstring; "GetHashString"
0x18003fd8f  mov     [rsp+188h+var_160], rax
0x18003fd94  mov     dword ptr [rsp+188h+var_168], 674h
0x18003fd9c  jmp     loc_18003FEEF
0x18003fda1  lea     rax, [rsp+188h+var_A8]
0x18003fda9  mov     edx, 4Ah ; 'J'; unsigned __int64
0x18003fdae  lea     r9, aName2sid; "Name2Sid"
0x18003fdb5  mov     [rsp+188h+var_168], rax
0x18003fdba  lea     r8, aWsWs_1; "%ws\\%ws"
0x18003fdc1  lea     rcx, [rsp+188h+SubKey]; unsigned __int16 *
0x18003fdc6  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fdcb  mov     ebx, eax
0x18003fdcd  test    eax, eax
0x18003fdcf  jz      short loc_18003FE05
0x18003fdd1  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003fdd8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fddd  mov     r9, rax
0x18003fde0  lea     rax, Class
0x18003fde7  mov     [rsp+188h+var_158], rax
0x18003fdec  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18003fdf3  mov     [rsp+188h+var_160], rax
0x18003fdf8  mov     dword ptr [rsp+188h+var_168], 67Dh
0x18003fe00  jmp     loc_18003FEEF
0x18003fe05  lea     rdx, [rsp+188h+SubKey]; lpSubKey
0x18003fe0a  mov     rcx, rdi; hKey
0x18003fe0d  call    cs:__imp_RegDeleteKeyW
0x18003fe13  mov     ebx, eax
0x18003fe15  test    eax, eax
0x18003fe17  jz      short loc_18003FE56
0x18003fe19  jle     short loc_18003FE24
0x18003fe1b  movzx   ebx, ax
0x18003fe1e  or      ebx, 0C0070000h
0x18003fe24  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003fe2b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fe30  mov     r9, rax
0x18003fe33  lea     rax, [rsp+188h+SubKey]
0x18003fe38  mov     [rsp+188h+var_158], rax
0x18003fe3d  lea     rax, aRegdeletekey; "RegDeleteKey"
0x18003fe44  mov     [rsp+188h+var_160], rax
0x18003fe49  mov     dword ptr [rsp+188h+var_168], 685h
0x18003fe51  jmp     loc_18003FEEF
0x18003fe56  mov     rcx, rdi; hKey
0x18003fe59  call    cs:__imp_RegFlushKey
0x18003fe5f  mov     ebx, eax
0x18003fe61  test    eax, eax
0x18003fe63  jz      short loc_18003FE9F
0x18003fe65  jle     short loc_18003FE70
0x18003fe67  movzx   ebx, ax
0x18003fe6a  or      ebx, 0C0070000h
0x18003fe70  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003fe77  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fe7c  mov     r9, rax
0x18003fe7f  lea     rax, [rsp+188h+SubKey]
0x18003fe84  mov     [rsp+188h+var_158], rax
0x18003fe89  lea     rax, aRegflushkey; "RegFlushKey"
0x18003fe90  mov     [rsp+188h+var_160], rax
0x18003fe95  mov     dword ptr [rsp+188h+var_168], 68Ch
0x18003fe9d  jmp     short loc_18003FEEF
0x18003fe9f  xor     ebx, ebx
0x18003fea1  jmp     short loc_18003FF00
0x18003fea3  mov     ebx, 0C000000Dh
0x18003fea8  lea     r9, pbInput+24h; ""
0x18003feaf  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003feb6  mov     rax, r9
0x18003feb9  dec     r9
0x18003febc  cmp     byte ptr [r9], 5Ch ; '\'
0x18003fec0  jz      short loc_18003FECB
0x18003fec2  cmp     r9, rcx
0x18003fec5  ja      short loc_18003FEB6
0x18003fec7  cmp     byte ptr [r9], 5Ch ; '\'
0x18003fecb  cmovz   r9, rax
0x18003fecf  lea     rax, Class
0x18003fed6  mov     [rsp+188h+var_158], rax
0x18003fedb  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18003fee2  mov     [rsp+188h+var_160], rax
0x18003fee7  mov     dword ptr [rsp+188h+var_168], 665h
0x18003feef  mov     r8d, ebx
0x18003fef2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003fef9  xor     ecx, ecx
0x18003fefb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003ff00  mov     eax, ebx
0x18003ff02  mov     rcx, [rsp+188h+var_18]
0x18003ff0a  xor     rcx, rsp; StackCookie
0x18003ff0d  call    __security_check_cookie
0x18003ff12  mov     rbx, [rsp+188h+arg_10]
0x18003ff1a  add     rsp, 180h
0x18003ff21  pop     rdi
0x18003ff22  retn
```
