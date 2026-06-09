# ConvertNameToUPN(_ApPluginPkg *,ushort const *,int,ushort *,ushort * *,ushort * *)

- ea: `0x180052978`
- end: `0x180052dff`
- name: `?ConvertNameToUPN@@YAJPEAU_ApPluginPkg@@PEBGHPEAGPEAPEAG3@Z`
- size: `1159`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180029650`

## callees

- `0x180004634`
- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x180031260`
- `0x1800335d4`
- `0x180042410`
- `0x180052978`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052d9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052d9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052b9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052b9e`
- `ntdll!RtlReleaseResource` at `0x180052d7e`
- `ntdll!RtlReleaseResource` at `0x180052d7e`
- `ntdll!RtlAcquireResourceShared` at `0x180052a5c`
- `ntdll!RtlAcquireResourceShared` at `0x180052a5c`

## string_xrefs

- `0x180052b10`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180052b61`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180052bae`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180052c06`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180052c28`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180052a0e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180052aaa`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180052c6c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180052cc9`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180052d22`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180052bbd`: `RegOpenKeyExW`
- `0x180052abe`: `FindUserInCacheBySAMName`
- `0x180052c80`: `FindUserInCacheByAlias`

## pseudocode

```c
__int64 __fastcall ConvertNameToUPN(
        struct _ApPluginPkg *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v8; // r13
  int v10; // eax
  unsigned int HashString; // ebx
  const char *v12; // rax
  HKEY v13; // r15
  const char *v14; // r9
  const char *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r10
  const char *v18; // r11
  int v19; // ecx
  const char *v20; // r15
  const char *v21; // rax
  WCHAR *v22; // rdx
  const char *v23; // r9
  const char *v24; // rax
  const char *v25; // rax
  unsigned __int16 **v26; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int v32; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *Src; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v35; // [rsp+58h] [rbp-A8h] BYREF
  struct _ApPluginSubPkg *v36; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v37; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v38; // [rsp+70h] [rbp-90h]
  struct _ApPluginPkg *v39; // [rsp+78h] [rbp-88h]
  WCHAR SubKey[80]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v41[72]; // [rsp+120h] [rbp+20h] BYREF

  v6 = 0;
  v39 = a1;
  v8 = 0;
  v32 = a3;
  *a5 = 0;
  v38 = a6;
  *a6 = 0;
  v37 = a5;
  hKey = 0;
  Src = 0;
  v35 = 0;
  v36 = 0;
  v10 = RefSubPackage(a1, a2, &v36);
  HashString = 0;
  if ( v10 != -2146893039 )
    HashString = v10;
  if ( HashString )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v12, 752, "RefSubPackage", &Class);
    goto LABEL_34;
  }
  RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
  if ( v36 )
    v13 = (HKEY)*((_QWORD *)v36 + 74);
  else
    v13 = (HKEY)*((_QWORD *)a1 + 44);
  if ( !v32 )
  {
    hKey = 0;
    if ( v13 && a4 )
    {
      HashString = GetHashString(a4, v41);
      if ( HashString )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v19 = 1279;
        v20 = "GetHashString";
      }
      else
      {
        HashString = RtlStringCchPrintfW(SubKey, 0x4Cu, L"%ws\\%ws", L"Alias2Name", v41);
        if ( !HashString )
        {
          HashString = RegOpenKeyExW(v13, SubKey, 0, 0x20019u, &hKey);
          if ( !HashString )
          {
LABEL_28:
            v32 = 0;
            HashString = GetRegVal(hKey, L"IdentityName", 6u, &v32, (void **)&Src);
            if ( HashString )
            {
              v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(phkResultc) = 780;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v24, phkResultc, "GetStringRegVal", &Class);
              v6 = Src;
            }
            else
            {
              v6 = Src;
              HashString = DuplicateString(Src, 1, &v35);
              if ( HashString )
              {
                v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(phkResultc) = 784;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v25, phkResultc, "DuplicateString", &Class);
                v8 = v35;
              }
              else
              {
                v26 = v38;
                *v37 = v6;
                v6 = 0;
                HashString = 0;
                *v26 = v35;
              }
            }
            goto LABEL_33;
          }
          v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          v20 = "RegOpenKeyExW";
          LODWORD(phkResulta) = 1298;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v21, phkResulta, "RegOpenKeyExW", SubKey);
          if ( HashString - 2 <= 1 )
          {
            HashString = -1073741275;
          }
          else if ( (int)HashString > 0 )
          {
            HashString = (unsigned __int16)HashString | 0xC0070000;
          }
          v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          v22 = SubKey;
          v19 = 1308;
LABEL_26:
          LODWORD(phkResult) = v19;
          WPPTraceLogA(v17, v18, v16, v15, phkResult, v20, v22);
          v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(phkResultb) = 773;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v23, phkResultb, "FindUserInCacheByAlias", &Class);
          goto LABEL_33;
        }
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v19 = 1287;
        v20 = "RtlStringCchPrintfW";
      }
    }
    else
    {
      HashString = -1073741811;
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v19 = 1273;
      v20 = "Invalid Arg(s)";
    }
    v22 = (WCHAR *)&Class;
    goto LABEL_26;
  }
  HashString = FindUserInCacheBySAMName(v13, a4, &hKey);
  if ( !HashString )
    goto LABEL_28;
  v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v14, 765, "FindUserInCacheBySAMName", &Class);
LABEL_33:
  RtlReleaseResource(&g_LookupsCacheLock);
LABEL_34:
  DerefSubPackage(v39, v36);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  if ( v8 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  return HashString;
}

```

## disassembly

```asm
0x180052978  mov     [rsp-8+arg_10], rbx
0x18005297d  push    rbp
0x18005297e  push    rsi
0x18005297f  push    rdi
0x180052980  push    r12
0x180052982  push    r13
0x180052984  push    r14
0x180052986  push    r15
0x180052988  lea     rbp, [rsp-0C0h]
0x180052990  sub     rsp, 1C0h
0x180052997  mov     rax, cs:__security_cookie
0x18005299e  xor     rax, rsp
0x1800529a1  mov     [rbp+0F0h+var_40], rax
0x1800529a8  mov     rax, [rbp+0F0h+arg_20]
0x1800529af  xor     esi, esi
0x1800529b1  mov     rdi, rcx
0x1800529b4  mov     [rsp+1F0h+var_178], rcx
0x1800529b9  mov     rcx, [rbp+0F0h+arg_28]
0x1800529c0  xor     r13d, r13d
0x1800529c3  mov     [rsp+1F0h+var_1B0], r8d
0x1800529c8  mov     r12, r9
0x1800529cb  mov     [rax], rsi
0x1800529ce  lea     r8, [rsp+1F0h+var_190]; struct _ApPluginSubPkg **
0x1800529d3  mov     [rsp+1F0h+var_180], rcx
0x1800529d8  mov     [rcx], rsi
0x1800529db  mov     rcx, rdi; struct _ApPluginPkg *
0x1800529de  mov     [rsp+1F0h+var_188], rax
0x1800529e3  mov     [rsp+1F0h+hKey], 0
0x1800529ec  mov     [rsp+1F0h+Src], rsi
0x1800529f1  mov     [rsp+1F0h+var_198], r13
0x1800529f6  mov     [rsp+1F0h+var_190], rsi
0x1800529fb  call    ?RefSubPackage@@YAJPEAU_ApPluginPkg@@PEBGPEAPEAU_ApPluginSubPkg@@@Z; RefSubPackage(_ApPluginPkg *,ushort const *,_ApPluginSubPkg * *)
0x180052a00  xor     ebx, ebx
0x180052a02  cmp     eax, 80090311h
0x180052a07  cmovnz  ebx, eax
0x180052a0a  test    ebx, ebx
0x180052a0c  jz      short loc_180052A53
0x180052a0e  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052a15  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052a1a  mov     r9, rax
0x180052a1d  lea     r14, Class
0x180052a24  lea     rax, aRefsubpackage; "RefSubPackage"
0x180052a2b  mov     [rsp+1F0h+var_1C0], r14
0x180052a30  mov     [rsp+1F0h+var_1C8], rax
0x180052a35  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180052a3c  mov     r8d, ebx
0x180052a3f  mov     dword ptr [rsp+1F0h+phkResult], 2F0h
0x180052a47  xor     ecx, ecx
0x180052a49  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052a4e  jmp     loc_180052D84
0x180052a53  mov     dl, 1; Wait
0x180052a55  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180052a5c  call    cs:__imp_RtlAcquireResourceShared
0x180052a62  mov     rax, [rsp+1F0h+var_190]
0x180052a67  test    rax, rax
0x180052a6a  jz      short loc_180052A75
0x180052a6c  mov     r15, [rax+250h]
0x180052a73  jmp     short loc_180052A7C
0x180052a75  mov     r15, [rdi+160h]
0x180052a7c  lea     r14, Class
0x180052a83  lea     rdi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180052a8a  cmp     [rsp+1F0h+var_1B0], esi
0x180052a8e  jz      short loc_180052AE4
0x180052a90  lea     r8, [rsp+1F0h+hKey]; phkResult
0x180052a95  mov     rdx, r12; unsigned __int16 *
0x180052a98  mov     rcx, r15; hKey
0x180052a9b  call    ?FindUserInCacheBySAMName@@YAJPEAUHKEY__@@PEAGPEAPEAU1@@Z; FindUserInCacheBySAMName(HKEY__ *,ushort *,HKEY__ * *)
0x180052aa0  mov     ebx, eax
0x180052aa2  test    eax, eax
0x180052aa4  jz      loc_180052C99
0x180052aaa  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052ab1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052ab6  mov     [rsp+1F0h+var_1C0], r14
0x180052abb  mov     r9, rax
0x180052abe  lea     rax, aFinduserincach_0; "FindUserInCacheBySAMName"
0x180052ac5  mov     [rsp+1F0h+var_1C8], rax
0x180052aca  mov     dword ptr [rsp+1F0h+phkResult], 2FDh
0x180052ad2  mov     r8d, ebx
0x180052ad5  mov     rdx, rdi
0x180052ad8  xor     ecx, ecx
0x180052ada  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052adf  jmp     loc_180052D77
0x180052ae4  mov     [rsp+1F0h+hKey], rsi
0x180052ae9  test    r15, r15
0x180052aec  jz      loc_180052C23
0x180052af2  test    r12, r12
0x180052af5  jz      loc_180052C23
0x180052afb  lea     rdx, [rbp+0F0h+var_D0]; unsigned __int16 *
0x180052aff  mov     rcx, r12; lpSrcStr
0x180052b02  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x180052b07  mov     ebx, eax
0x180052b09  test    eax, eax
0x180052b0b  jz      short loc_180052B33
0x180052b0d  xor     r10d, r10d
0x180052b10  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180052b17  mov     r11, rdi
0x180052b1a  mov     r8d, eax
0x180052b1d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052b22  mov     ecx, 4FFh
0x180052b27  lea     r15, aGethashstring; "GetHashString"
0x180052b2e  jmp     loc_180052C49
0x180052b33  lea     rax, [rbp+0F0h+var_D0]
0x180052b37  mov     edx, 4Ch ; 'L'; unsigned __int64
0x180052b3c  lea     r9, aAlias2name; "Alias2Name"
0x180052b43  mov     [rsp+1F0h+phkResult], rax
0x180052b48  lea     r8, aWsWs_1; "%ws\\%ws"
0x180052b4f  lea     rcx, [rbp+0F0h+SubKey]; unsigned __int16 *
0x180052b53  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052b58  mov     ebx, eax
0x180052b5a  test    eax, eax
0x180052b5c  jz      short loc_180052B84
0x180052b5e  xor     r10d, r10d
0x180052b61  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180052b68  mov     r11, rdi
0x180052b6b  mov     r8d, eax
0x180052b6e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052b73  mov     ecx, 507h
0x180052b78  lea     r15, aRtlstringcchpr; "RtlStringCchPrintfW"
0x180052b7f  jmp     loc_180052C49
0x180052b84  lea     rax, [rsp+1F0h+hKey]
0x180052b89  mov     r9d, 20019h; samDesired
0x180052b8f  xor     r8d, r8d; ulOptions
0x180052b92  mov     [rsp+1F0h+phkResult], rax; phkResult
0x180052b97  lea     rdx, [rbp+0F0h+SubKey]; lpSubKey
0x180052b9b  mov     rcx, r15; hKey
0x180052b9e  call    cs:__imp_RegOpenKeyExW
0x180052ba4  mov     ebx, eax
0x180052ba6  test    eax, eax
0x180052ba8  jz      loc_180052C99
0x180052bae  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180052bb5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052bba  mov     r9, rax
0x180052bbd  lea     r15, aRegopenkeyexw; "RegOpenKeyExW"
0x180052bc4  lea     rax, [rbp+0F0h+SubKey]
0x180052bc8  mov     r8d, ebx
0x180052bcb  mov     [rsp+1F0h+var_1C0], rax
0x180052bd0  mov     rdx, rdi
0x180052bd3  mov     [rsp+1F0h+var_1C8], r15
0x180052bd8  xor     ecx, ecx
0x180052bda  mov     dword ptr [rsp+1F0h+phkResult], 512h
0x180052be2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052be7  lea     eax, [rbx-2]
0x180052bea  cmp     eax, 1
0x180052bed  jbe     short loc_180052BFE
0x180052bef  test    ebx, ebx
0x180052bf1  jle     short loc_180052C03
0x180052bf3  movzx   ebx, bx
0x180052bf6  or      ebx, 0C0070000h
0x180052bfc  jmp     short loc_180052C03
0x180052bfe  mov     ebx, 0C0000225h
0x180052c03  xor     r10d, r10d
0x180052c06  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180052c0d  mov     r11, rdi
0x180052c10  mov     r8d, ebx
0x180052c13  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052c18  lea     rdx, [rbp+0F0h+SubKey]
0x180052c1c  mov     ecx, 51Ch
0x180052c21  jmp     short loc_180052C4C
0x180052c23  mov     ebx, 0C000000Dh
0x180052c28  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180052c2f  xor     r10d, r10d
0x180052c32  mov     r8d, ebx
0x180052c35  mov     r11, rdi
0x180052c38  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052c3d  mov     ecx, 4F9h
0x180052c42  lea     r15, aInvalidArgS; "Invalid Arg(s)"
0x180052c49  mov     rdx, r14
0x180052c4c  mov     [rsp+1F0h+var_1C0], rdx
0x180052c51  mov     r9, rax
0x180052c54  mov     [rsp+1F0h+var_1C8], r15
0x180052c59  mov     rdx, r11
0x180052c5c  mov     dword ptr [rsp+1F0h+phkResult], ecx
0x180052c60  mov     rcx, r10
0x180052c63  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052c68  test    ebx, ebx
0x180052c6a  jz      short loc_180052C99
0x180052c6c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052c73  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052c78  mov     [rsp+1F0h+var_1C0], r14
0x180052c7d  mov     r9, rax
0x180052c80  lea     rax, aFinduserincach_2; "FindUserInCacheByAlias"
0x180052c87  mov     [rsp+1F0h+var_1C8], rax
0x180052c8c  mov     dword ptr [rsp+1F0h+phkResult], 305h
0x180052c94  jmp     loc_180052AD2
0x180052c99  mov     rcx, [rsp+1F0h+hKey]; hkey
0x180052c9e  lea     rax, [rsp+1F0h+Src]
0x180052ca3  lea     r9, [rsp+1F0h+var_1B0]; unsigned int *
0x180052ca8  mov     [rsp+1F0h+phkResult], rax; void **
0x180052cad  mov     r8d, 6; dwFlags
0x180052cb3  mov     [rsp+1F0h+var_1B0], esi
0x180052cb7  lea     rdx, aIdentityname; "IdentityName"
0x180052cbe  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x180052cc3  mov     ebx, eax
0x180052cc5  test    eax, eax
0x180052cc7  jz      short loc_180052D05
0x180052cc9  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052cd0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052cd5  mov     r9, rax
0x180052cd8  mov     [rsp+1F0h+var_1C0], r14
0x180052cdd  lea     rax, aGetstringregva_3; "GetStringRegVal"
0x180052ce4  mov     r8d, ebx
0x180052ce7  mov     [rsp+1F0h+var_1C8], rax
0x180052cec  mov     rdx, rdi
0x180052cef  xor     ecx, ecx
0x180052cf1  mov     dword ptr [rsp+1F0h+phkResult], 30Ch
0x180052cf9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052cfe  mov     rsi, [rsp+1F0h+Src]
0x180052d03  jmp     short loc_180052D77
0x180052d05  mov     rsi, [rsp+1F0h+Src]
0x180052d0a  lea     r8, [rsp+1F0h+var_198]; unsigned __int16 **
0x180052d0f  mov     rcx, rsi; Src
0x180052d12  mov     edx, 1; int
0x180052d17  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180052d1c  mov     ebx, eax
0x180052d1e  test    eax, eax
0x180052d20  jz      short loc_180052D5E
0x180052d22  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052d29  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052d2e  mov     r9, rax
0x180052d31  mov     [rsp+1F0h+var_1C0], r14
0x180052d36  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x180052d3d  mov     r8d, ebx
0x180052d40  mov     [rsp+1F0h+var_1C8], rax
0x180052d45  mov     rdx, rdi
0x180052d48  xor     ecx, ecx
0x180052d4a  mov     dword ptr [rsp+1F0h+phkResult], 310h
0x180052d52  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052d57  mov     r13, [rsp+1F0h+var_198]
0x180052d5c  jmp     short loc_180052D77
0x180052d5e  mov     rax, [rsp+1F0h+var_188]
0x180052d63  mov     rdx, [rsp+1F0h+var_180]
0x180052d68  mov     [rax], rsi
0x180052d6b  xor     esi, esi
0x180052d6d  mov     rax, [rsp+1F0h+var_198]
0x180052d72  xor     ebx, ebx
0x180052d74  mov     [rdx], rax
0x180052d77  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180052d7e  call    cs:__imp_RtlReleaseResource
0x180052d84  mov     rdx, [rsp+1F0h+var_190]; struct _ApPluginSubPkg *
0x180052d89  mov     rcx, [rsp+1F0h+var_178]; struct _ApPluginPkg *
0x180052d8e  call    ?DerefSubPackage@@YAXPEAU_ApPluginPkg@@PEAU_ApPluginSubPkg@@@Z; DerefSubPackage(_ApPluginPkg *,_ApPluginSubPkg *)
0x180052d93  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180052d98  test    rcx, rcx
0x180052d9b  jz      short loc_180052DA3
0x180052d9d  call    cs:__imp_RegCloseKey
0x180052da3  test    rsi, rsi
0x180052da6  jz      short loc_180052DBB
0x180052da8  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180052daf  mov     rcx, rsi
0x180052db2  mov     rax, [rax+30h]
0x180052db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dbb  test    r13, r13
0x180052dbe  jz      short loc_180052DD3
0x180052dc0  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180052dc7  mov     rcx, r13
0x180052dca  mov     rax, [rax+30h]
0x180052dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dd3  mov     eax, ebx
0x180052dd5  mov     rcx, [rbp+0F0h+var_40]
0x180052ddc  xor     rcx, rsp; StackCookie
0x180052ddf  call    __security_check_cookie
0x180052de4  mov     rbx, [rsp+1F0h+arg_10]
0x180052dec  add     rsp, 1C0h
0x180052df3  pop     r15
0x180052df5  pop     r14
0x180052df7  pop     r13
0x180052df9  pop     r12
0x180052dfb  pop     rdi
0x180052dfc  pop     rsi
0x180052dfd  pop     rbp
0x180052dfe  retn
```
