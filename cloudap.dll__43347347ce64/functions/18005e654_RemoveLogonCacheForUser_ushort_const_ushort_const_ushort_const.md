# _RemoveLogonCacheForUser(ushort const *,ushort const *,ushort const *)

- ea: `0x18005e654`
- end: `0x18005e915`
- name: `?_RemoveLogonCacheForUser@@YAJPEBG00@Z`
- size: `705`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180052358`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x180042410`
- `0x18005e654`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e87a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005e824`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005e824`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005e870`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005e870`

## string_xrefs

- `0x18005e69d`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e6f7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e769`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e7d7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e834`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e895`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e84b`: `SetFileAttributesW`
- `0x18005e7a2`: `Cache`
- `0x18005e8a9`: `DeleteFile`

## pseudocode

```c
__int64 __fastcall _RemoveLogonCacheForUser(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int HashString; // ebx
  const char *v6; // r9
  const char *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rdi
  const char *v12; // r9
  const char *v13; // r9
  const char *v14; // rax
  __int64 v15; // r8
  signed int LastError; // eax
  const char *v17; // r9
  __int64 v18; // r8
  __int64 v20; // [rsp+20h] [rbp-F8h]
  LPCWSTR lpSrcStr; // [rsp+40h] [rbp-D8h] BYREF
  unsigned __int16 v22[72]; // [rsp+50h] [rbp-C8h] BYREF

  lpSrcStr = 0;
  HashString = DuplicateString(a2, 1, (unsigned __int16 **)&lpSrcStr);
  if ( HashString )
  {
    v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v6, 2497, "DuplicateString", &Class);
  }
  else
  {
    HashString = GetHashString(lpSrcStr, v22);
    if ( HashString )
    {
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v7, 2502, "GetHashString", &Class);
    }
    else
    {
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( v22[v9] );
      do
        ++v8;
      while ( a1[v8] );
      v10 = v9 + v8 + 18;
      v11 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD, unsigned __int16 *))g_pLsaFunctionTable->AllocateLsaHeap)(
                                  2 * v10,
                                  v22);
      if ( v11 )
      {
        HashString = RtlStringCchPrintfW(v11, v10, L"%ws\\%ws\\%ws\\%ws", a1, v22, L"Cache", a3);
        if ( HashString )
        {
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(v20) = 2521;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v13, v20, "RtlStringCchPrintfW", &Class);
        }
        else
        {
          if ( !SetFileAttributesW(v11, 0x80u) )
          {
            GetLastError();
            v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            LODWORD(v20) = 2531;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, v20, "SetFileAttributesW", v11);
          }
          if ( DeleteFileW(v11) )
          {
            HashString = 0;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              HashString = (unsigned __int16)LastError | 0xC0070000;
            else
              HashString = LastError;
            v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            LODWORD(v20) = 2538;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, v20, "DeleteFile", v11);
          }
        }
        ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
      }
      else
      {
        HashString = -1073741801;
        v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v12, 2510, "AllocateLsaHeap", &Class);
      }
    }
  }
  if ( lpSrcStr )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(lpSrcStr);
  return HashString;
}

```

## disassembly

```asm
0x18005e654  push    rbx
0x18005e656  push    rbp
0x18005e657  push    rdi
0x18005e658  push    r14
0x18005e65a  push    r15
0x18005e65c  sub     rsp, 0F0h
0x18005e663  mov     rax, cs:__security_cookie
0x18005e66a  xor     rax, rsp
0x18005e66d  mov     [rsp+118h+var_38], rax
0x18005e675  mov     rax, rdx
0x18005e678  xor     r15d, r15d
0x18005e67b  mov     r14, r8
0x18005e67e  mov     [rsp+118h+lpSrcStr], r15
0x18005e683  mov     rbp, rcx
0x18005e686  lea     r8, [rsp+118h+lpSrcStr]; unsigned __int16 **
0x18005e68b  mov     rcx, rax; Src
0x18005e68e  lea     edx, [r15+1]; int
0x18005e692  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18005e697  mov     ebx, eax
0x18005e699  test    eax, eax
0x18005e69b  jz      short loc_18005E6E2
0x18005e69d  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e6a4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005e6a9  mov     r9, rax
0x18005e6ac  lea     rax, Class
0x18005e6b3  mov     [rsp+118h+var_E8], rax
0x18005e6b8  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18005e6bf  mov     [rsp+118h+var_F0], rax
0x18005e6c4  mov     dword ptr [rsp+118h+var_F8], 9C1h
0x18005e6cc  mov     r8d, ebx
0x18005e6cf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005e6d6  xor     ecx, ecx
0x18005e6d8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005e6dd  jmp     loc_18005E8D8
0x18005e6e2  mov     rcx, [rsp+118h+lpSrcStr]; lpSrcStr
0x18005e6e7  lea     rdx, [rsp+118h+var_C8]; unsigned __int16 *
0x18005e6ec  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18005e6f1  mov     ebx, eax
0x18005e6f3  test    eax, eax
0x18005e6f5  jz      short loc_18005E728
0x18005e6f7  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e6fe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005e703  mov     r9, rax
0x18005e706  lea     rax, Class
0x18005e70d  mov     [rsp+118h+var_E8], rax
0x18005e712  lea     rax, aGethashstring; "GetHashString"
0x18005e719  mov     [rsp+118h+var_F0], rax
0x18005e71e  mov     dword ptr [rsp+118h+var_F8], 9C6h
0x18005e726  jmp     short loc_18005E6CC
0x18005e728  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e72c  lea     rdx, [rsp+118h+var_C8]
0x18005e731  mov     rcx, rax
0x18005e734  inc     rcx
0x18005e737  cmp     [rdx+rcx*2], r15w
0x18005e73c  jnz     short loc_18005E734
0x18005e73e  inc     rax
0x18005e741  cmp     [rbp+rax*2+0], r15w
0x18005e747  jnz     short loc_18005E73E
0x18005e749  lea     ebx, [rax+12h]
0x18005e74c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005e753  add     ebx, ecx
0x18005e755  mov     rax, [rax+28h]
0x18005e759  lea     ecx, [rbx+rbx]
0x18005e75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e761  mov     rdi, rax
0x18005e764  test    rax, rax
0x18005e767  jnz     short loc_18005E7A2
0x18005e769  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e770  mov     ebx, 0C0000017h
0x18005e775  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005e77a  mov     r9, rax
0x18005e77d  lea     rax, Class
0x18005e784  mov     [rsp+118h+var_E8], rax
0x18005e789  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18005e790  mov     [rsp+118h+var_F0], rax
0x18005e795  mov     dword ptr [rsp+118h+var_F8], 9CEh
0x18005e79d  jmp     loc_18005E6CC
0x18005e7a2  lea     rax, aCache; "Cache"
0x18005e7a9  mov     [rsp+118h+var_E8], r14
0x18005e7ae  mov     [rsp+118h+var_F0], rax
0x18005e7b3  lea     r8, aWsWsWsWs; "%ws\\%ws\\%ws\\%ws"
0x18005e7ba  lea     rax, [rsp+118h+var_C8]
0x18005e7bf  mov     edx, ebx; unsigned __int64
0x18005e7c1  mov     r9, rbp
0x18005e7c4  mov     [rsp+118h+var_F8], rax
0x18005e7c9  mov     rcx, rdi; unsigned __int16 *
0x18005e7cc  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e7d1  mov     ebx, eax
0x18005e7d3  test    eax, eax
0x18005e7d5  jz      short loc_18005E81C
0x18005e7d7  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e7de  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005e7e3  mov     r9, rax
0x18005e7e6  mov     r8d, ebx
0x18005e7e9  lea     rax, Class
0x18005e7f0  mov     [rsp+118h+var_E8], rax
0x18005e7f5  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18005e7fc  mov     [rsp+118h+var_F0], rax
0x18005e801  mov     dword ptr [rsp+118h+var_F8], 9D9h
0x18005e809  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005e810  xor     ecx, ecx
0x18005e812  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005e817  jmp     loc_18005E8C5
0x18005e81c  mov     edx, 80h; dwFileAttributes
0x18005e821  mov     rcx, rdi; lpFileName
0x18005e824  call    cs:__imp_SetFileAttributesW
0x18005e82a  test    eax, eax
0x18005e82c  jnz     short loc_18005E86D
0x18005e82e  call    cs:__imp_GetLastError
0x18005e834  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e83b  mov     r8d, eax
0x18005e83e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005e843  mov     r9, rax
0x18005e846  mov     [rsp+118h+var_E8], rdi
0x18005e84b  lea     rax, aSetfileattribu; "SetFileAttributesW"
0x18005e852  xor     ecx, ecx
0x18005e854  mov     [rsp+118h+var_F0], rax
0x18005e859  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005e860  mov     dword ptr [rsp+118h+var_F8], 9E3h
0x18005e868  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005e86d  mov     rcx, rdi; lpFileName
0x18005e870  call    cs:__imp_DeleteFileW
0x18005e876  test    eax, eax
0x18005e878  jnz     short loc_18005E8C2
0x18005e87a  call    cs:__imp_GetLastError
0x18005e880  mov     r8d, eax
0x18005e883  test    eax, eax
0x18005e885  jg      short loc_18005E88B
0x18005e887  mov     ebx, eax
0x18005e889  jmp     short loc_18005E895
0x18005e88b  movzx   ebx, r8w
0x18005e88f  or      ebx, 0C0070000h
0x18005e895  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e89c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005e8a1  mov     [rsp+118h+var_E8], rdi
0x18005e8a6  mov     r9, rax
0x18005e8a9  lea     rax, aDeletefile; "DeleteFile"
0x18005e8b0  mov     [rsp+118h+var_F0], rax
0x18005e8b5  mov     dword ptr [rsp+118h+var_F8], 9EAh
0x18005e8bd  jmp     loc_18005E809
0x18005e8c2  mov     ebx, r15d
0x18005e8c5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005e8cc  mov     rcx, rdi
0x18005e8cf  mov     rax, [rax+30h]
0x18005e8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8d8  cmp     [rsp+118h+lpSrcStr], r15
0x18005e8dd  jz      short loc_18005E8F4
0x18005e8df  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005e8e6  mov     rcx, [rsp+118h+lpSrcStr]
0x18005e8eb  mov     rax, [rax+30h]
0x18005e8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8f4  mov     eax, ebx
0x18005e8f6  mov     rcx, [rsp+118h+var_38]
0x18005e8fe  xor     rcx, rsp; StackCookie
0x18005e901  call    __security_check_cookie
0x18005e906  add     rsp, 0F0h
0x18005e90d  pop     r15
0x18005e90f  pop     r14
0x18005e911  pop     rdi
0x18005e912  pop     rbp
0x18005e913  pop     rbx
0x18005e914  retn
```
