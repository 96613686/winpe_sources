# VerifyRealAppAllowedFromRegistry(ushort const *,ushort const *,int,int *)

- ea: `0x180032110`
- end: `0x1800323a4`
- name: `?VerifyRealAppAllowedFromRegistry@@YAJPEBG0HPEAH@Z`
- size: `660`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, const unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800769f4`
- `0x180076d08`

## callees

- `0x18000e420`
- `0x180032110`
- `0x180033da0`
- `0x180077590`
- `0x1800776e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800322ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032372`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800322ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032372`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003224f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003224f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800321b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003227c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800321b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003227c`
- `RDPBASE!TRC_TraceBufferW` at `0x180032205`
- `RDPBASE!TRC_TraceBufferW` at `0x180032362`
- `RDPBASE!TRC_TraceBufferW` at `0x180032205`
- `RDPBASE!TRC_TraceBufferW` at `0x180032362`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18003218a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18003218a`

## string_xrefs

- `0x1800321de`: `VerifyRealAppAllowedFromRegistry`
- `0x18003233c`: `VerifyRealAppAllowedFromRegistry`
- `0x1800321cd`: `RegOpenKeyEx(allow-list apps root) failed`
- `0x18003232a`: `VerifyRealAppAllowedFromRegistry reg error hr[0x%x]`

## pseudocode

```c
__int64 __fastcall VerifyRealAppAllowedFromRegistry(PCNZWCH lpString2, unsigned __int16 *a2, int a3, int *a4)
{
  signed int v4; // ebx
  int v5; // r12d
  bool v6; // zf
  int v9; // edi
  LSTATUS v11; // eax
  DWORD i; // esi
  LSTATUS v13; // eax
  int matched; // eax
  PFILETIME lpftLastWriteTime; // [rsp+38h] [rbp-C8h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v21; // [rsp+58h] [rbp-A8h]
  WCHAR sz[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+270h] [rbp+170h] BYREF

  v4 = 0;
  v21 = a2;
  v5 = 0;
  *a4 = 0;
  v6 = *lpString2 == 34;
  cchName = 0;
  v9 = 1;
  hKey = 0;
  phkResult = 0;
  if ( v6 )
  {
    v4 = StringCchCopyW(sz, 0x104u, lpString2);
    if ( v4 >= 0 )
    {
      PathUnquoteSpacesW(sz);
      v5 = 1;
    }
  }
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server\\TSAppAllowList\\Applications",
          0,
          0x20019u,
          &hKey);
  if ( !v11 )
  {
    for ( i = 0; ; ++i )
    {
      if ( !v9 )
        goto LABEL_29;
      v18 = 0;
      cchName = 256;
      v13 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v13 )
      {
        if ( v13 != 259 )
        {
          if ( v13 > 0 )
            v4 = (unsigned __int16)v13 | 0x80070000;
          else
            v4 = v13;
          LODWORD(lpftLastWriteTime) = v4;
          TRC_TraceBufferW(
            3,
            4096,
            424,
            L"VerifyRealAppAllowedFromRegistry",
            L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
            0,
            L"VerifyRealAppAllowedFromRegistry reg error hr[0x%x]",
            lpftLastWriteTime);
        }
        goto LABEL_29;
      }
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
        break;
LABEL_22:
      ;
    }
    matched = DoesAppMatchAllowListEntry(
                phkResult,
                lpString2,
                (PCNZWCH)((unsigned __int64)sz & -(__int64)(v5 != 0)),
                &v18);
    v4 = matched;
    if ( matched < 0 )
    {
      LODWORD(lpftLastWriteTime) = matched;
      TRC_TraceBufferW(
        3,
        4096,
        396,
        L"VerifyRealAppAllowedFromRegistry",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        L"DoesAppMatchAllowListEntry hr[0x%x]",
        lpftLastWriteTime);
      goto LABEL_29;
    }
    if ( v18 )
    {
      if ( !a3 )
      {
        v4 = 0;
        *a4 = 1;
        goto LABEL_19;
      }
      v4 = VerifyCommandLine(phkResult, v21, a4);
      if ( v4 >= 0 )
      {
LABEL_19:
        if ( *a4 )
          v9 = 0;
      }
    }
    RegCloseKey(phkResult);
    goto LABEL_22;
  }
  if ( v11 > 0 )
    v4 = (unsigned __int16)v11 | 0x80070000;
  else
    v4 = v11;
  TRC_TraceBufferW(
    3,
    4096,
    361,
    L"VerifyRealAppAllowedFromRegistry",
    L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
    0,
    L"RegOpenKeyEx(allow-list apps root) failed");
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180032110  mov     [rsp-8+arg_10], rbx
0x180032115  push    rbp
0x180032116  push    rsi
0x180032117  push    rdi
0x180032118  push    r12
0x18003211a  push    r13
0x18003211c  push    r14
0x18003211e  push    r15
0x180032120  lea     rbp, [rsp-380h]
0x180032128  sub     rsp, 480h
0x18003212f  mov     rax, cs:__security_cookie
0x180032136  xor     rax, rsp
0x180032139  mov     [rbp+3B0h+var_40], rax
0x180032140  xor     ebx, ebx
0x180032142  mov     [rsp+4B0h+var_458], rdx
0x180032147  xor     r12d, r12d
0x18003214a  mov     [r9], ebx
0x18003214d  cmp     word ptr [rcx], 22h ; '"'
0x180032151  mov     r14, r9
0x180032154  mov     r13d, r8d
0x180032157  mov     [rsp+4B0h+cchName], ebx
0x18003215b  lea     edi, [rbx+1]
0x18003215e  mov     [rsp+4B0h+hKey], rbx
0x180032163  mov     r15, rcx
0x180032166  mov     [rsp+4B0h+var_468], rbx
0x18003216b  jnz     short loc_180032193
0x18003216d  mov     r8, rcx; unsigned __int16 *
0x180032170  mov     edx, 104h; unsigned __int64
0x180032175  lea     rcx, [rsp+4B0h+sz]; unsigned __int16 *
0x18003217a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003217f  mov     ebx, eax
0x180032181  test    eax, eax
0x180032183  js      short loc_180032193
0x180032185  lea     rcx, [rsp+4B0h+sz]; lpsz
0x18003218a  call    cs:__imp_PathUnquoteSpacesW
0x180032190  mov     r12d, edi
0x180032193  lea     rax, [rsp+4B0h+hKey]
0x180032198  mov     r9d, 20019h; samDesired
0x18003219e  xor     r8d, r8d; ulOptions
0x1800321a1  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800321a6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800321ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800321b4  call    cs:__imp_RegOpenKeyExW
0x1800321ba  test    eax, eax
0x1800321bc  jz      short loc_180032210
0x1800321be  jg      short loc_1800321C4
0x1800321c0  mov     ebx, eax
0x1800321c2  jmp     short loc_1800321CD
0x1800321c4  movzx   ebx, ax
0x1800321c7  or      ebx, 80070000h
0x1800321cd  lea     rax, aRegopenkeyexAl_1; "RegOpenKeyEx(allow-list apps root) fail"...
0x1800321d4  mov     edx, 1000h
0x1800321d9  mov     [rsp+4B0h+lpcchClass], rax
0x1800321de  lea     r9, aVerifyrealappa_2; "VerifyRealAppAllowedFromRegistry"
0x1800321e5  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x1800321ec  mov     [rsp+4B0h+lpClass], 0
0x1800321f5  mov     ecx, 3
0x1800321fa  mov     [rsp+4B0h+phkResult], rax
0x1800321ff  mov     r8d, 169h
0x180032205  call    cs:__imp_TRC_TraceBufferW
0x18003220b  jmp     loc_180032368
0x180032210  xor     esi, esi
0x180032212  xor     eax, eax
0x180032214  test    edi, edi
0x180032216  jz      loc_180032368
0x18003221c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180032221  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x180032226  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18003222b  lea     r8, [rbp+3B0h+Name]; lpName
0x180032232  mov     [rsp+4B0h+lpcchClass], rax; lpcchClass
0x180032237  mov     edx, esi; dwIndex
0x180032239  mov     [rsp+4B0h+lpClass], rax; lpClass
0x18003223e  mov     [rsp+4B0h+phkResult], rax; lpReserved
0x180032243  mov     [rsp+4B0h+var_46C], eax
0x180032247  mov     [rsp+4B0h+cchName], 100h
0x18003224f  call    cs:__imp_RegEnumKeyExW
0x180032255  test    eax, eax
0x180032257  jnz     loc_18003230A
0x18003225d  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180032262  lea     rax, [rsp+4B0h+var_468]
0x180032267  mov     r9d, 20019h; samDesired
0x18003226d  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180032272  xor     r8d, r8d; ulOptions
0x180032275  lea     rdx, [rbp+3B0h+Name]; lpSubKey
0x18003227c  call    cs:__imp_RegOpenKeyExW
0x180032282  test    eax, eax
0x180032284  jnz     short loc_1800322F0
0x180032286  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18003228b  lea     r9, [rsp+4B0h+var_46C]; int *
0x180032290  mov     eax, r12d
0x180032293  mov     rdx, r15; lpString2
0x180032296  neg     eax
0x180032298  lea     rax, [rsp+4B0h+sz]
0x18003229d  sbb     r8, r8
0x1800322a0  and     r8, rax; PCNZWCH
0x1800322a3  call    ?DoesAppMatchAllowListEntry@@YAJPEAUHKEY__@@PEBG1PEAH@Z; DoesAppMatchAllowListEntry(HKEY__ *,ushort const *,ushort const *,int *)
0x1800322a8  mov     ebx, eax
0x1800322aa  test    eax, eax
0x1800322ac  js      short loc_1800322F7
0x1800322ae  cmp     [rsp+4B0h+var_46C], 0
0x1800322b3  jz      short loc_1800322E5
0x1800322b5  test    r13d, r13d
0x1800322b8  jz      short loc_1800322D4
0x1800322ba  mov     rdx, [rsp+4B0h+var_458]; unsigned __int16 *
0x1800322bf  mov     r8, r14; int *
0x1800322c2  mov     rcx, [rsp+4B0h+var_468]; hKey
0x1800322c7  call    ?VerifyCommandLine@@YAJPEAUHKEY__@@PEBGPEAH@Z; VerifyCommandLine(HKEY__ *,ushort const *,int *)
0x1800322cc  mov     ebx, eax
0x1800322ce  test    eax, eax
0x1800322d0  js      short loc_1800322E5
0x1800322d2  jmp     short loc_1800322DD
0x1800322d4  xor     ebx, ebx
0x1800322d6  mov     dword ptr [r14], 1
0x1800322dd  xor     eax, eax
0x1800322df  cmp     [r14], eax
0x1800322e2  cmovnz  edi, eax
0x1800322e5  mov     rcx, [rsp+4B0h+var_468]; hKey
0x1800322ea  call    cs:__imp_RegCloseKey
0x1800322f0  inc     esi
0x1800322f2  jmp     loc_180032212
0x1800322f7  mov     dword ptr [rsp+4B0h+lpftLastWriteTime], eax
0x1800322fb  mov     r8d, 18Ch
0x180032301  lea     rax, aDoesappmatchal; "DoesAppMatchAllowListEntry hr[0x%x]"
0x180032308  jmp     short loc_180032337
0x18003230a  cmp     eax, 103h
0x18003230f  jz      short loc_180032368
0x180032311  test    eax, eax
0x180032313  jg      short loc_180032319
0x180032315  mov     ebx, eax
0x180032317  jmp     short loc_180032322
0x180032319  movzx   ebx, ax
0x18003231c  or      ebx, 80070000h
0x180032322  test    ebx, ebx
0x180032324  jns     short loc_180032368
0x180032326  mov     dword ptr [rsp+4B0h+lpftLastWriteTime], ebx
0x18003232a  lea     rax, aVerifyrealappa_0; "VerifyRealAppAllowedFromRegistry reg er"...
0x180032331  mov     r8d, 1A8h
0x180032337  mov     [rsp+4B0h+lpcchClass], rax
0x18003233c  lea     r9, aVerifyrealappa_2; "VerifyRealAppAllowedFromRegistry"
0x180032343  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x18003234a  mov     [rsp+4B0h+lpClass], 0
0x180032353  mov     edx, 1000h
0x180032358  mov     [rsp+4B0h+phkResult], rax
0x18003235d  mov     ecx, 3
0x180032362  call    cs:__imp_TRC_TraceBufferW
0x180032368  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18003236d  test    rcx, rcx
0x180032370  jz      short loc_180032378
0x180032372  call    cs:__imp_RegCloseKey
0x180032378  mov     eax, ebx
0x18003237a  mov     rcx, [rbp+3B0h+var_40]
0x180032381  xor     rcx, rsp; StackCookie
0x180032384  call    __security_check_cookie
0x180032389  mov     rbx, [rsp+4B0h+arg_10]
0x180032391  add     rsp, 480h
0x180032398  pop     r15
0x18003239a  pop     r14
0x18003239c  pop     r13
0x18003239e  pop     r12
0x1800323a0  pop     rdi
0x1800323a1  pop     rsi
0x1800323a2  pop     rbp
0x1800323a3  retn
```
