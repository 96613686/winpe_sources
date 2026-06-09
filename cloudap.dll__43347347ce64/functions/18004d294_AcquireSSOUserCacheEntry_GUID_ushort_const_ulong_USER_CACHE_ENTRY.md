# AcquireSSOUserCacheEntry(_GUID *,ushort const *,ulong,_USER_CACHE_ENTRY * *)

- ea: `0x18004d294`
- end: `0x18004d50c`
- name: `?AcquireSSOUserCacheEntry@@YAJPEAU_GUID@@PEBGKPEAPEAU_USER_CACHE_ENTRY@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(struct _GUID *Buf1, const unsigned __int16 *Src, int, struct _LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800035b4`

## callees

- `0x180003e70`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x180042410`
- `0x18004317c`
- `0x18004d294`
- `0x18007f9f0`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18004d394`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004d394`
- `ntdll!RtlReleaseResource` at `0x18004d4bf`
- `ntdll!RtlReleaseResource` at `0x18004d4bf`

## string_xrefs

- `0x18004d300`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d35a`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d3f8`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d473`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d41a`: `Rename operation in progress for this identity`
- `0x18004d44c`: `AcquireSSOUserCacheEntry`

## pseudocode

```c
__int64 __fastcall AcquireSSOUserCacheEntry(
        struct _GUID *Buf1,
        const unsigned __int16 *Src,
        int a3,
        struct _LIST_ENTRY **a4)
{
  unsigned int HashString; // ebx
  const char *v9; // r9
  const char *v10; // r9
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v12; // rdi
  const char *v13; // r9
  const char *v14; // rax
  const char *v15; // r9
  int v17; // [rsp+20h] [rbp-F8h]
  int v18; // [rsp+20h] [rbp-F8h]
  int v19; // [rsp+20h] [rbp-F8h]
  int v20; // [rsp+20h] [rbp-F8h]
  int v21; // [rsp+20h] [rbp-F8h]
  LPCWSTR lpSrcStr; // [rsp+40h] [rbp-D8h] BYREF
  WCHAR v23[72]; // [rsp+50h] [rbp-C8h] BYREF

  memset_0(v23, 0, 0x82u);
  lpSrcStr = 0;
  *a4 = 0;
  HashString = DuplicateString(Src, 1, (unsigned __int16 **)&lpSrcStr);
  if ( HashString )
  {
    v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    v17 = 744;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v9, v17, "DuplicateString", &Class);
  }
  else
  {
    HashString = GetHashString(lpSrcStr, v23);
    if ( HashString )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
      v18 = 749;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v10, v18, "GetHashString", &Class);
    }
    else
    {
      RtlAcquireResourceExclusive(&g_UserCacheListLock, 1u);
      Flink = g_UserCacheList.Flink;
      if ( g_UserCacheList.Flink == &g_UserCacheList )
        goto LABEL_15;
      do
      {
        if ( !(unsigned int)CloudAPCompareStrings((PCWSTR)&Flink[6].Blink, v23)
          && !memcmp_0(Buf1, &Flink[15].Blink, 0x10u) )
        {
          v12 = Flink;
          if ( LODWORD(Flink[21].Blink) == a3 )
            break;
        }
        Flink = Flink->Flink;
        v12 = 0;
      }
      while ( Flink != &g_UserCacheList );
      if ( !v12 )
      {
LABEL_15:
        HashString = -1073741724;
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
        v21 = 773;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225572LL, v15, v21, "No SSO entry", &Class);
      }
      else if ( LODWORD(v12[5].Flink) )
      {
        HashString = -1073740682;
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
        v19 = 782;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221226614LL,
          v13,
          v19,
          "Rename operation in progress for this identity",
          &Class);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)&v12[1]);
        v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
        v20 = 787;
        WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", 0, v14, v20, "AcquireSSOUserCacheEntry", v12[6].Flink);
        HashString = 0;
        *a4 = v12;
      }
      RtlReleaseResource(&g_UserCacheListLock);
    }
  }
  if ( lpSrcStr )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(lpSrcStr);
  return HashString;
}

```

## disassembly

```asm
0x18004d294  mov     [rsp+arg_0], rbx
0x18004d299  push    rbp
0x18004d29a  push    rdi
0x18004d29b  push    r13
0x18004d29d  push    r14
0x18004d29f  push    r15
0x18004d2a1  sub     rsp, 0F0h
0x18004d2a8  mov     rax, cs:__security_cookie
0x18004d2af  xor     rax, rsp
0x18004d2b2  mov     [rsp+118h+var_38], rax
0x18004d2ba  mov     ebp, r8d
0x18004d2bd  mov     rbx, rdx
0x18004d2c0  mov     r14, rcx
0x18004d2c3  xor     edx, edx; Val
0x18004d2c5  mov     r8d, 82h; Size
0x18004d2cb  lea     rcx, [rsp+118h+var_C8]; void *
0x18004d2d0  mov     r15, r9
0x18004d2d3  call    memset_0
0x18004d2d8  lea     r8, [rsp+118h+lpSrcStr]; unsigned __int16 **
0x18004d2dd  mov     [rsp+118h+lpSrcStr], 0
0x18004d2e6  mov     edx, 1; int
0x18004d2eb  mov     qword ptr [r15], 0
0x18004d2f2  mov     rcx, rbx; Src
0x18004d2f5  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18004d2fa  mov     ebx, eax
0x18004d2fc  test    eax, eax
0x18004d2fe  jz      short loc_18004D345
0x18004d300  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d307  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004d30c  mov     r9, rax
0x18004d30f  lea     rax, Class
0x18004d316  mov     [rsp+118h+var_E8], rax
0x18004d31b  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18004d322  mov     [rsp+118h+var_F0], rax
0x18004d327  mov     [rsp+118h+var_F8], 2E8h
0x18004d32f  mov     r8d, ebx
0x18004d332  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004d339  xor     ecx, ecx
0x18004d33b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004d340  jmp     loc_18004D4C5
0x18004d345  mov     rcx, [rsp+118h+lpSrcStr]; lpSrcStr
0x18004d34a  lea     rdx, [rsp+118h+var_C8]; unsigned __int16 *
0x18004d34f  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18004d354  mov     ebx, eax
0x18004d356  test    eax, eax
0x18004d358  jz      short loc_18004D38B
0x18004d35a  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d361  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004d366  mov     r9, rax
0x18004d369  lea     rax, Class
0x18004d370  mov     [rsp+118h+var_E8], rax
0x18004d375  lea     rax, aGethashstring; "GetHashString"
0x18004d37c  mov     [rsp+118h+var_F0], rax
0x18004d381  mov     [rsp+118h+var_F8], 2EDh
0x18004d389  jmp     short loc_18004D32F
0x18004d38b  mov     dl, 1; Wait
0x18004d38d  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004d394  call    cs:__imp_RtlAcquireResourceExclusive
0x18004d39a  mov     rbx, cs:?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x18004d3a1  lea     r13, ?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x18004d3a8  cmp     rbx, r13
0x18004d3ab  jz      loc_18004D473
0x18004d3b1  lea     rcx, [rbx+68h]; SourceString
0x18004d3b5  lea     rdx, [rsp+118h+var_C8]; PCWSTR
0x18004d3ba  call    ?CloudAPCompareStrings@@YAHPEBG0@Z; CloudAPCompareStrings(ushort const *,ushort const *)
0x18004d3bf  test    eax, eax
0x18004d3c1  jnz     short loc_18004D3E5
0x18004d3c3  lea     rdx, [rbx+0F8h]; Buf2
0x18004d3ca  mov     rcx, r14; Buf1
0x18004d3cd  lea     r8d, [rax+10h]; Size
0x18004d3d1  call    memcmp_0
0x18004d3d6  test    eax, eax
0x18004d3d8  jnz     short loc_18004D3E5
0x18004d3da  mov     rdi, rbx
0x18004d3dd  cmp     [rbx+158h], ebp
0x18004d3e3  jz      short loc_18004D3EF
0x18004d3e5  mov     rbx, [rbx]
0x18004d3e8  xor     edi, edi
0x18004d3ea  cmp     rbx, r13
0x18004d3ed  jnz     short loc_18004D3B1
0x18004d3ef  test    rdi, rdi
0x18004d3f2  jz      short loc_18004D473
0x18004d3f4  cmp     dword ptr [rdi+50h], 0
0x18004d3f8  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d3ff  jz      short loc_18004D430
0x18004d401  mov     ebx, 0C0000476h
0x18004d406  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004d40b  mov     r9, rax
0x18004d40e  lea     rax, Class
0x18004d415  mov     [rsp+118h+var_E8], rax
0x18004d41a  lea     rax, aRenameOperatio; "Rename operation in progress for this i"...
0x18004d421  mov     [rsp+118h+var_F0], rax
0x18004d426  mov     [rsp+118h+var_F8], 30Eh
0x18004d42e  jmp     short loc_18004D4A7
0x18004d430  lock inc dword ptr [rdi+10h]
0x18004d434  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004d439  mov     rcx, [rdi+60h]
0x18004d43d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004d444  mov     [rsp+118h+var_E8], rcx
0x18004d449  xor     r8d, r8d
0x18004d44c  lea     rcx, aAcquiressouser; "AcquireSSOUserCacheEntry"
0x18004d453  mov     r9, rax
0x18004d456  mov     [rsp+118h+var_F0], rcx
0x18004d45b  mov     [rsp+118h+var_F8], 313h
0x18004d463  lea     ecx, [r8+2]
0x18004d467  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004d46c  xor     ebx, ebx
0x18004d46e  mov     [r15], rdi
0x18004d471  jmp     short loc_18004D4B8
0x18004d473  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d47a  mov     ebx, 0C0000064h
0x18004d47f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004d484  mov     r9, rax
0x18004d487  lea     rax, Class
0x18004d48e  mov     [rsp+118h+var_E8], rax
0x18004d493  lea     rax, aNoSsoEntry; "No SSO entry"
0x18004d49a  mov     [rsp+118h+var_F0], rax
0x18004d49f  mov     [rsp+118h+var_F8], 305h
0x18004d4a7  mov     r8d, ebx
0x18004d4aa  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004d4b1  xor     ecx, ecx
0x18004d4b3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004d4b8  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004d4bf  call    cs:__imp_RtlReleaseResource
0x18004d4c5  cmp     [rsp+118h+lpSrcStr], 0
0x18004d4cb  jz      short loc_18004D4E2
0x18004d4cd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004d4d4  mov     rcx, [rsp+118h+lpSrcStr]
0x18004d4d9  mov     rax, [rax+30h]
0x18004d4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4e2  mov     eax, ebx
0x18004d4e4  mov     rcx, [rsp+118h+var_38]
0x18004d4ec  xor     rcx, rsp; StackCookie
0x18004d4ef  call    __security_check_cookie
0x18004d4f4  mov     rbx, [rsp+118h+arg_0]
0x18004d4fc  add     rsp, 0F0h
0x18004d503  pop     r15
0x18004d505  pop     r14
0x18004d507  pop     r13
0x18004d509  pop     rdi
0x18004d50a  pop     rbp
0x18004d50b  retn
```
