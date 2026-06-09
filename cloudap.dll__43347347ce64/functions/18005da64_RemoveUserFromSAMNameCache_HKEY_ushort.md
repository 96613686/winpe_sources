# RemoveUserFromSAMNameCache(HKEY__ *,ushort *)

- ea: `0x18005da64`
- end: `0x18005dc10`
- name: `?RemoveUserFromSAMNameCache@@YAJPEAUHKEY__@@PEAG@Z`
- size: `428`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800307d0`
- `0x180052358`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180031494`
- `0x18005da64`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005db4e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005db4e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005daf9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005daf9`

## string_xrefs

- `0x18005daa4`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005db1a`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005db6f`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005dba1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005db32`: `RegDeleteKey`

## pseudocode

```c
__int64 __fastcall RemoveUserFromSAMNameCache(HKEY hKey, unsigned __int16 *a2)
{
  LPCWSTR v2; // rdi
  unsigned int UserSAMNameSubKey; // ebx
  const char *v5; // rax
  LSTATUS v6; // eax
  const char *v7; // rax
  __int64 v8; // r8
  LSTATUS v9; // eax
  const char *v10; // rax
  __int64 v11; // r8
  const char *v12; // r9
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  lpSubKey = 0;
  if ( hKey && a2 )
  {
    UserSAMNameSubKey = GetUserSAMNameSubKey(a2, (unsigned __int16 **)&lpSubKey);
    if ( UserSAMNameSubKey )
    {
      v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSAMNameSubKey, v5, 1880, "GetUserSAMNameSubKey", &Class);
      v2 = lpSubKey;
    }
    else
    {
      v2 = lpSubKey;
      v6 = RegDeleteKeyW(hKey, lpSubKey);
      UserSAMNameSubKey = v6;
      if ( v6 )
      {
        if ( v6 > 0 )
          UserSAMNameSubKey = (unsigned __int16)v6 | 0xC0070000;
        v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSAMNameSubKey, v7, 1888, "RegDeleteKey", v8);
      }
      else
      {
        v9 = RegFlushKey(hKey);
        UserSAMNameSubKey = v9;
        if ( v9 )
        {
          if ( v9 > 0 )
            UserSAMNameSubKey = (unsigned __int16)v9 | 0xC0070000;
          v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSAMNameSubKey, v10, 1895, "RegFlushKey", v11);
        }
        else
        {
          UserSAMNameSubKey = 0;
        }
      }
    }
  }
  else
  {
    UserSAMNameSubKey = -1073741811;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v12, 1874, "InvalidArg(s)", &Class);
  }
  if ( v2 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v2);
  return UserSAMNameSubKey;
}

```

## disassembly

```asm
0x18005da64  mov     r11, rsp
0x18005da67  mov     [r11+10h], rbx
0x18005da6b  mov     [r11+18h], rsi
0x18005da6f  push    rdi
0x18005da70  sub     rsp, 40h
0x18005da74  xor     edi, edi
0x18005da76  mov     rax, rdx
0x18005da79  mov     [r11+8], rdi
0x18005da7d  mov     rsi, rcx
0x18005da80  test    rcx, rcx
0x18005da83  jz      loc_18005DBA1
0x18005da89  test    rax, rax
0x18005da8c  jz      loc_18005DBA1
0x18005da92  lea     rdx, [r11+8]; unsigned __int16 **
0x18005da96  mov     rcx, rax; unsigned __int16 *
0x18005da99  call    ?GetUserSAMNameSubKey@@YAJPEBGPEAPEAG@Z; GetUserSAMNameSubKey(ushort const *,ushort * *)
0x18005da9e  mov     ebx, eax
0x18005daa0  test    eax, eax
0x18005daa2  jz      short loc_18005DAEE
0x18005daa4  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005daab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005dab0  lea     r8, Class
0x18005dab7  mov     r9, rax
0x18005daba  mov     [rsp+48h+var_18], r8
0x18005dabf  lea     rax, aGetusersamname; "GetUserSAMNameSubKey"
0x18005dac6  mov     [rsp+48h+var_20], rax
0x18005dacb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005dad2  mov     r8d, ebx
0x18005dad5  mov     [rsp+48h+var_28], 758h
0x18005dadd  xor     ecx, ecx
0x18005dadf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005dae4  mov     rdi, [rsp+48h+lpSubKey]
0x18005dae9  jmp     loc_18005DBE6
0x18005daee  mov     rdi, [rsp+48h+lpSubKey]
0x18005daf3  mov     rcx, rsi; hKey
0x18005daf6  mov     rdx, rdi; lpSubKey
0x18005daf9  call    cs:__imp_RegDeleteKeyW
0x18005daff  mov     ebx, eax
0x18005db01  test    eax, eax
0x18005db03  jz      short loc_18005DB4B
0x18005db05  jle     short loc_18005DB10
0x18005db07  movzx   ebx, ax
0x18005db0a  or      ebx, 0C0070000h
0x18005db10  test    rdi, rdi
0x18005db13  lea     r8, Class
0x18005db1a  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005db21  cmovnz  r8, rdi
0x18005db25  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005db2a  mov     [rsp+48h+var_18], r8
0x18005db2f  mov     r9, rax
0x18005db32  lea     rax, aRegdeletekey; "RegDeleteKey"
0x18005db39  mov     [rsp+48h+var_20], rax
0x18005db3e  mov     [rsp+48h+var_28], 760h
0x18005db46  jmp     loc_18005DBD5
0x18005db4b  mov     rcx, rsi; hKey
0x18005db4e  call    cs:__imp_RegFlushKey
0x18005db54  mov     ebx, eax
0x18005db56  test    eax, eax
0x18005db58  jz      short loc_18005DB9D
0x18005db5a  jle     short loc_18005DB65
0x18005db5c  movzx   ebx, ax
0x18005db5f  or      ebx, 0C0070000h
0x18005db65  test    rdi, rdi
0x18005db68  lea     r8, Class
0x18005db6f  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005db76  cmovnz  r8, rdi
0x18005db7a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005db7f  mov     [rsp+48h+var_18], r8
0x18005db84  mov     r9, rax
0x18005db87  lea     rax, aRegflushkey; "RegFlushKey"
0x18005db8e  mov     [rsp+48h+var_20], rax
0x18005db93  mov     [rsp+48h+var_28], 767h
0x18005db9b  jmp     short loc_18005DBD5
0x18005db9d  xor     ebx, ebx
0x18005db9f  jmp     short loc_18005DBE6
0x18005dba1  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005dba8  mov     ebx, 0C000000Dh
0x18005dbad  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005dbb2  mov     r9, rax
0x18005dbb5  lea     r8, Class
0x18005dbbc  mov     [rsp+48h+var_18], r8
0x18005dbc1  lea     rax, aInvalidargS; "InvalidArg(s)"
0x18005dbc8  mov     [rsp+48h+var_20], rax
0x18005dbcd  mov     [rsp+48h+var_28], 752h
0x18005dbd5  mov     r8d, ebx
0x18005dbd8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005dbdf  xor     ecx, ecx
0x18005dbe1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005dbe6  test    rdi, rdi
0x18005dbe9  jz      short loc_18005DBFE
0x18005dbeb  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005dbf2  mov     rcx, rdi
0x18005dbf5  mov     rax, [rax+30h]
0x18005dbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dbfe  mov     rsi, [rsp+48h+arg_10]
0x18005dc03  mov     eax, ebx
0x18005dc05  mov     rbx, [rsp+48h+arg_8]
0x18005dc0a  add     rsp, 40h
0x18005dc0e  pop     rdi
0x18005dc0f  retn
```
