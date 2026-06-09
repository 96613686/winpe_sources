# CleanupPreRS2Names(HKEY__ *,HKEY__ *,ushort const *)

- ea: `0x180014d90`
- end: `0x1800156e0`
- name: `?CleanupPreRS2Names@@YAJPEAUHKEY__@@0PEBG@Z`
- size: `2384`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180018a20`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180014d90`
- `0x1800156f0`
- `0x18003fcdc`
- `0x180042410`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180014f1a`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180014f1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001546c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800156d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001546c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800156d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001539c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001539c`
- `ntdll!RtlReleaseResource` at `0x180015110`
- `ntdll!RtlReleaseResource` at `0x180015110`
- `ntdll!RtlAcquireResourceShared` at `0x180014f32`
- `ntdll!RtlAcquireResourceShared` at `0x180014f32`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800150c7`
- `ntdll!RtlConvertSharedToExclusive` at `0x180015482`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800150c7`
- `ntdll!RtlConvertSharedToExclusive` at `0x180015482`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800150f4`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800154aa`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800150f4`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800154aa`

## string_xrefs

- `0x180014e7a`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800150db`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800151d6`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18001527f`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180014e11`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014f71`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180015191`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180015231`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800154f0`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180014f9d`: `Name2Sid`
- `0x180015351`: `Name2Sid`
- `0x18001501d`: `RegOpenKeyExW`
- `0x180015069`: `RegOpenKeyExW`
- `0x1800153d7`: `RegOpenKeyExW`
- `0x180015296`: `FindUserInCacheByNamePreRS2`
- `0x1800152ea`: `FindUserInCacheByNamePreRS2`
- `0x1800155e3`: `FindUserInCacheByNamePreRS2`
- `0x180015668`: `FindUserInCacheByNamePreRS2`
- `0x180015567`: `RemoveUserFromName2SidCachePreRS2`
- `0x1800155ff`: `RemoveUserFromName2SidCachePreRS2`

## pseudocode

```c
__int64 __fastcall CleanupPreRS2Names(HKEY hKey, HKEY a2, const unsigned __int16 *a3)
{
  __int64 v5; // rbx
  unsigned int v6; // edi
  const UCHAR *v7; // rbx
  char v8; // al
  const UCHAR *v9; // r8
  const char *v10; // r11
  __int64 v11; // r10
  const char *v12; // rcx
  int v13; // eax
  const char *v14; // r9
  unsigned int v15; // r14d
  char v16; // al
  const char *v17; // rcx
  bool v18; // zf
  unsigned __int64 v19; // rbp
  UCHAR *v20; // rax
  UCHAR *v21; // rsi
  unsigned int i; // ebp
  UCHAR *v23; // rdi
  int HashStringPreRS2; // ebp
  const UCHAR *v25; // rbx
  const UCHAR *v26; // r9
  char v27; // al
  const UCHAR *v28; // rcx
  bool v29; // zf
  unsigned int v30; // r11d
  const UCHAR *v31; // rax
  char v32; // cl
  const UCHAR *v33; // r8
  __int64 v34; // r10
  const char *v35; // rdx
  int v36; // ecx
  WCHAR *v37; // r8
  unsigned int v39; // r13d
  char v40; // cl
  const UCHAR *v41; // rdx
  const UCHAR *v42; // r9
  char v43; // al
  const UCHAR *v44; // rcx
  bool v45; // zf
  const char *v46; // rax
  const char *v47; // r9
  char v48; // al
  const char *v49; // rdx
  bool v50; // zf
  int v51; // r13d
  const UCHAR *v52; // r9
  char v53; // al
  const UCHAR *v54; // rcx
  bool v55; // zf
  __int64 v56; // r8
  char v57; // al
  const UCHAR *v58; // rcx
  __int64 v59; // r10
  const char *v60; // rdx
  WCHAR *v61; // rax
  int v62; // ecx
  char v63; // al
  const UCHAR *v64; // rcx
  const char *v65; // rax
  __int64 v66; // r8
  const char *v67; // rax
  __int64 v68; // r8
  const char *v69; // rax
  const char *v70; // rax
  const char *v71; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-2E8h]
  PHKEY phkResulta; // [rsp+20h] [rbp-2E8h]
  PHKEY phkResultb; // [rsp+20h] [rbp-2E8h]
  PHKEY phkResultc; // [rsp+20h] [rbp-2E8h]
  HKEY hKeya; // [rsp+40h] [rbp-2C8h] BYREF
  HKEY v77; // [rsp+48h] [rbp-2C0h]
  WCHAR SubKey[80]; // [rsp+60h] [rbp-2A8h] BYREF
  WCHAR v79[80]; // [rsp+100h] [rbp-208h] BYREF
  unsigned __int16 v80[72]; // [rsp+1A0h] [rbp-168h] BYREF
  unsigned __int16 v81[72]; // [rsp+230h] [rbp-D8h] BYREF

  v77 = a2;
  hKeya = 0;
  if ( !a3 )
  {
    v21 = 0;
    goto LABEL_22;
  }
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  if ( (int)v5 + 1 >= (unsigned int)v5 )
  {
    v19 = 2LL * (unsigned int)(v5 + 1);
    if ( v19 > 0xFFFFFFFF )
    {
      v6 = -1073741675;
      v7 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v12 = "RtlDWordMult";
      v13 = 42;
      goto LABEL_11;
    }
    v20 = (UCHAR *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v19);
    v21 = v20;
    if ( !v20 )
    {
      v6 = -1073741801;
      v7 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v12 = "AllocateLsaHeap";
      v13 = 48;
      goto LABEL_11;
    }
    memcpy_0(v20, a3, (unsigned int)v19);
    for ( i = 0; i < (unsigned int)v5; *(_WORD *)v23 = _o_tolower(*(unsigned __int16 *)v23) )
      v23 = &v21[2 * i++];
LABEL_22:
    RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
    hKeya = 0;
    v15 = -1073741811;
    if ( hKey && v21 )
    {
      HashStringPreRS2 = GetHashStringPreRS2(v21, v80);
      v25 = "";
      if ( HashStringPreRS2 )
      {
        v31 = "";
        do
        {
          v40 = *(v31 - 1);
          v41 = v31--;
        }
        while ( v40 != 92 && v31 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
        v34 = 0;
        v30 = HashStringPreRS2;
        v18 = v40 == 92;
        v37 = (WCHAR *)&Class;
        v36 = 1208;
        if ( v18 )
          v31 = v41;
        v35 = "GetHashString";
      }
      else
      {
        HashStringPreRS2 = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v80);
        if ( HashStringPreRS2 )
        {
          v31 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          v35 = "RtlStringCchPrintfW";
          v36 = 1216;
          v37 = (WCHAR *)&Class;
        }
        else
        {
          HashStringPreRS2 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya);
          if ( !HashStringPreRS2 )
          {
LABEL_42:
            RegCloseKey(hKeya);
            hKeya = 0;
            RtlConvertSharedToExclusive(&g_LookupsCacheLock);
            if ( (unsigned int)_RemoveUserFromName2SidCache(hKey, v21, 1) )
            {
              v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResultb) = 2361;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                v66,
                v65,
                phkResultb,
                "RemoveUserFromName2SidCachePreRS2",
                &Class);
            }
            RtlConvertExclusiveToShared(&g_LookupsCacheLock);
LABEL_45:
            if ( !v77 )
            {
LABEL_46:
              v15 = 0;
              goto LABEL_47;
            }
            hKeya = 0;
            if ( v21 )
            {
              v51 = GetHashStringPreRS2(v21, v81);
              if ( v51 )
              {
                do
                {
                  v63 = *(v25 - 1);
                  v64 = v25--;
                }
                while ( v63 != 92 && v25 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                v59 = 0;
                v60 = "GetHashString";
                v18 = v63 == 92;
                v56 = (unsigned int)v51;
                v61 = (WCHAR *)&Class;
                if ( v18 )
                  v25 = v64;
                v62 = 1208;
              }
              else
              {
                v51 = RtlStringCchPrintfW(v79, 0x4Au, L"%ws\\%ws", L"Name2Sid", v81);
                if ( v51 )
                {
                  v25 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  v60 = "RtlStringCchPrintfW";
                  v61 = (WCHAR *)&Class;
                  v62 = 1216;
                }
                else
                {
                  v51 = RegOpenKeyExW(v77, v79, 0, 0x20019u, &hKeya);
                  if ( !v51 )
                  {
LABEL_98:
                    RegCloseKey(hKeya);
                    hKeya = 0;
                    RtlConvertSharedToExclusive(&g_LookupsCacheLock);
                    if ( (unsigned int)_RemoveUserFromName2SidCache(v77, v21, 1) )
                    {
                      v67 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                      LODWORD(phkResultc) = 2393;
                      WPPTraceLogA(
                        0,
                        "0x%08x %s:%u : %s:%ws",
                        v68,
                        v67,
                        phkResultc,
                        "RemoveUserFromName2SidCachePreRS2",
                        &Class);
                    }
                    RtlConvertExclusiveToShared(&g_LookupsCacheLock);
                    goto LABEL_46;
                  }
                  v52 = "";
                  while ( 1 )
                  {
                    v53 = *(v52 - 1);
                    v54 = v52--;
                    v55 = v53 == 92;
                    if ( v53 == 92 )
                      break;
                    if ( v52 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
                    {
                      v55 = v53 == 92;
                      break;
                    }
                  }
                  if ( v55 )
                    v52 = v54;
                  LODWORD(phkResultc) = 1226;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v51, v52, phkResultc, "RegOpenKeyExW", v79);
                  if ( (unsigned int)(v51 - 2) > 1 )
                  {
                    if ( v51 > 0 )
                      v51 = (unsigned __int16)v51 | 0xC0070000;
                  }
                  else
                  {
                    v51 = -1073741275;
                  }
                  v56 = (unsigned int)v51;
                  do
                  {
                    v57 = *(v25 - 1);
                    v58 = v25--;
                  }
                  while ( v57 != 92 && v25 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                  v59 = 0;
                  v60 = "RegOpenKeyExW";
                  v18 = v57 == 92;
                  v61 = v79;
                  if ( v18 )
                    v25 = v58;
                  v62 = 1236;
                }
              }
              LODWORD(phkResultb) = v62;
              WPPTraceLogA(v59, "0x%08x %s:%u : %s:%ws", v56, v25, phkResultb, v60, v61);
              if ( v51 >= 0 )
                goto LABEL_98;
              v15 = 0;
              if ( v51 != -1073741275 )
                v15 = v51;
              if ( !v15 )
              {
LABEL_120:
                if ( v15 != -1073741670 )
                  goto LABEL_46;
LABEL_121:
                v71 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                LODWORD(phkResultc) = 2407;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v71, phkResultc, "FindUserInCacheByNamePreRS2", &Class);
LABEL_47:
                RtlReleaseResource(&g_LookupsCacheLock);
                if ( v21 )
                  ((void (__fastcall *)(UCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v21);
                goto LABEL_49;
              }
            }
            else
            {
              v69 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(phkResultb) = 1202;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v69, phkResultb, "Invalid Arg(s)", &Class);
            }
            v70 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResultc) = 2403;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v70, phkResultc, "FindUserInCacheByNamePreRS2", &Class);
            if ( v15 == -1073741801 )
              goto LABEL_121;
            goto LABEL_120;
          }
          v26 = "";
          while ( 1 )
          {
            v27 = *(v26 - 1);
            v28 = v26--;
            v29 = v27 == 92;
            if ( v27 == 92 )
              break;
            if ( v26 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
            {
              v29 = v27 == 92;
              break;
            }
          }
          if ( v29 )
            v26 = v28;
          LODWORD(phkResultb) = 1226;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)HashStringPreRS2,
            v26,
            phkResultb,
            "RegOpenKeyExW",
            SubKey);
          if ( (unsigned int)(HashStringPreRS2 - 2) > 1 )
          {
            if ( HashStringPreRS2 > 0 )
              HashStringPreRS2 = (unsigned __int16)HashStringPreRS2 | 0xC0070000;
          }
          else
          {
            HashStringPreRS2 = -1073741275;
          }
          v30 = HashStringPreRS2;
          v31 = "";
          do
          {
            v32 = *(v31 - 1);
            v33 = v31--;
          }
          while ( v32 != 92 && v31 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
          v34 = 0;
          v35 = "RegOpenKeyExW";
          v18 = v32 == 92;
          v36 = 1236;
          if ( v18 )
            v31 = v33;
          v37 = SubKey;
        }
      }
      LODWORD(phkResult) = v36;
      WPPTraceLogA(v34, "0x%08x %s:%u : %s:%ws", v30, v31, phkResult, v35, v37);
      if ( HashStringPreRS2 >= 0 )
        goto LABEL_42;
      v39 = 0;
      if ( HashStringPreRS2 != -1073741275 )
        v39 = HashStringPreRS2;
      if ( !v39 )
      {
LABEL_56:
        if ( v39 != -1073741670 )
          goto LABEL_45;
LABEL_72:
        v47 = "";
        while ( 1 )
        {
          v48 = *(v47 - 1);
          v49 = v47--;
          v50 = v48 == 92;
          if ( v48 == 92 )
            break;
          if ( v47 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
          {
            v50 = v48 == 92;
            break;
          }
        }
        if ( v50 )
          v47 = v49;
        LODWORD(phkResultb) = 2375;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v39, v47, phkResultb, "FindUserInCacheByNamePreRS2", &Class);
        v15 = v39;
        goto LABEL_47;
      }
    }
    else
    {
      v25 = "";
      v42 = "";
      while ( 1 )
      {
        v43 = *(v42 - 1);
        v44 = v42--;
        v45 = v43 == 92;
        if ( v43 == 92 )
          break;
        if ( v42 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
        {
          v45 = v43 == 92;
          break;
        }
      }
      if ( v45 )
        v42 = v44;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v42, 1202, "Invalid Arg(s)", &Class);
      v39 = -1073741811;
    }
    v46 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(phkResultb) = 2371;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v39, v46, phkResultb, "FindUserInCacheByNamePreRS2", &Class);
    if ( v39 == -1073741801 )
      goto LABEL_72;
    goto LABEL_56;
  }
  v6 = -1073741675;
  v7 = "";
  do
  {
    v8 = *(v7 - 1);
    v9 = v7--;
  }
  while ( v8 != 92 && v7 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
  v10 = "0x%08x %s:%u : %s:%ws";
  v11 = 0;
  v12 = "RtlDWordAdd";
  if ( v8 == 92 )
    v7 = v9;
  v13 = 39;
LABEL_11:
  WPPTraceLogA(v11, v10, v6, v7, v13, v12, &Class);
  v14 = "";
  v15 = v6;
  while ( 1 )
  {
    v16 = *(v14 - 1);
    v17 = v14--;
    v18 = v16 == 92;
    if ( v16 == 92 )
      break;
    if ( v14 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
    {
      v18 = v16 == 92;
      break;
    }
  }
  if ( v18 )
    v14 = v17;
  LODWORD(phkResulta) = 2344;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v14, phkResulta, "DuplicateStringPreRS2", &Class);
LABEL_49:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v15;
}

```

## disassembly

```asm
0x180014d90  mov     r11, rsp
0x180014d93  push    r14
0x180014d95  sub     rsp, 300h
0x180014d9c  mov     rax, cs:__security_cookie
0x180014da3  xor     rax, rsp
0x180014da6  mov     [rsp+308h+var_48], rax
0x180014dae  mov     [r11+20h], rbx
0x180014db2  xor     r14d, r14d
0x180014db5  mov     [r11-10h], rbp
0x180014db9  mov     [r11-18h], rsi
0x180014dbd  mov     [r11-20h], rdi
0x180014dc1  mov     rdi, r8
0x180014dc4  mov     [r11-28h], r12
0x180014dc8  mov     [r11-30h], r13
0x180014dcc  mov     r13, rcx
0x180014dcf  mov     [r11-38h], r15
0x180014dd3  mov     [rsp+308h+var_2C0], rdx
0x180014dd8  mov     [rsp+308h+hKey], r14
0x180014ddd  test    r8, r8
0x180014de0  jz      loc_1800154E8
0x180014de6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180014ded  nop     dword ptr [rax]
0x180014df0  inc     rbx
0x180014df3  cmp     [r8+rbx*2], r14w
0x180014df8  jnz     short loc_180014DF0
0x180014dfa  lea     eax, [rbx+1]
0x180014dfd  cmp     eax, ebx
0x180014dff  jnb     loc_180014ECA
0x180014e05  mov     edi, 0C0000095h
0x180014e0a  lea     rbx, pbInput+24h; ""
0x180014e11  lea     r15, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014e18  movzx   eax, byte ptr [rbx-1]
0x180014e1c  mov     r8, rbx
0x180014e1f  dec     rbx
0x180014e22  cmp     al, 5Ch ; '\'
0x180014e24  jz      short loc_180014E2B
0x180014e26  cmp     rbx, r15
0x180014e29  ja      short loc_180014E18
0x180014e2b  cmp     al, 5Ch ; '\'
0x180014e2d  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180014e34  mov     r10, r14
0x180014e37  lea     rcx, aRtldwordadd; "RtlDWordAdd"
0x180014e3e  cmovz   rbx, r8
0x180014e42  mov     eax, 27h ; '''
0x180014e47  lea     r12, Class
0x180014e4e  mov     r9, rbx
0x180014e51  mov     rdx, r12
0x180014e54  mov     r8d, edi
0x180014e57  mov     [rsp+308h+var_2D8], rdx
0x180014e5c  mov     rdx, r11
0x180014e5f  mov     [rsp+308h+var_2E0], rcx
0x180014e64  mov     rcx, r10
0x180014e67  mov     dword ptr [rsp+308h+phkResult], eax
0x180014e6b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180014e70  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x180014e77  mov     r14d, edi
0x180014e7a  lea     rbp, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180014e81  movzx   eax, byte ptr [r9-1]
0x180014e86  mov     rcx, r9
0x180014e89  dec     r9
0x180014e8c  cmp     al, 5Ch ; '\'
0x180014e8e  jz      short loc_180014E97
0x180014e90  cmp     r9, rbp
0x180014e93  ja      short loc_180014E81
0x180014e95  cmp     al, 5Ch ; '\'
0x180014e97  lea     rax, aDuplicatestrin_0; "DuplicateStringPreRS2"
0x180014e9e  mov     [rsp+308h+var_2D8], r12
0x180014ea3  cmovz   r9, rcx
0x180014ea7  mov     [rsp+308h+var_2E0], rax
0x180014eac  mov     r8d, edi
0x180014eaf  mov     dword ptr [rsp+308h+phkResult], 928h
0x180014eb7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180014ebe  xor     ecx, ecx
0x180014ec0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180014ec5  jmp     loc_18001512E
0x180014eca  mov     ebp, eax
0x180014ecc  mov     eax, 0FFFFFFFFh
0x180014ed1  add     rbp, rbp
0x180014ed4  cmp     rbp, rax
0x180014ed7  ja      loc_180015191
0x180014edd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180014ee4  mov     ecx, ebp
0x180014ee6  mov     rax, [rax+28h]
0x180014eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eef  mov     rsi, rax
0x180014ef2  test    rax, rax
0x180014ef5  jz      loc_1800154F0
0x180014efb  mov     r8d, ebp; Size
0x180014efe  mov     rdx, rdi; Src
0x180014f01  mov     rcx, rax; void *
0x180014f04  call    memcpy_0
0x180014f09  mov     ebp, r14d
0x180014f0c  test    ebx, ebx
0x180014f0e  jz      short loc_180014F29
0x180014f10  mov     eax, ebp
0x180014f12  movzx   ecx, word ptr [rsi+rax*2]
0x180014f16  lea     rdi, [rsi+rax*2]
0x180014f1a  call    cs:__imp__o_tolower
0x180014f20  inc     ebp
0x180014f22  mov     [rdi], ax
0x180014f25  cmp     ebp, ebx
0x180014f27  jb      short loc_180014F10
0x180014f29  mov     dl, 1; Wait
0x180014f2b  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180014f32  call    cs:__imp_RtlAcquireResourceShared
0x180014f38  mov     [rsp+308h+hKey], r14
0x180014f3d  mov     edi, 0C0000017h
0x180014f42  lea     rdx, aInvalidArgS; "Invalid Arg(s)"
0x180014f49  mov     r14d, 0C000000Dh
0x180014f4f  test    r13, r13
0x180014f52  jz      loc_180015227
0x180014f58  test    rsi, rsi
0x180014f5b  jz      loc_180015227
0x180014f61  lea     rdx, [rsp+308h+var_168]; unsigned __int16 *
0x180014f69  mov     rcx, rsi; pbInput
0x180014f6c  call    ?GetHashStringPreRS2@@YAJPEBGQEAG@Z; GetHashStringPreRS2(ushort const *,ushort * const)
0x180014f71  lea     r15, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180014f78  mov     ebp, eax
0x180014f7a  lea     r12, Class
0x180014f81  lea     rbx, pbInput+24h; ""
0x180014f88  test    eax, eax
0x180014f8a  jnz     loc_1800151EF
0x180014f90  lea     rax, [rsp+308h+var_168]
0x180014f98  mov     edx, 4Ah ; 'J'; unsigned __int64
0x180014f9d  lea     r9, aName2sid; "Name2Sid"
0x180014fa4  mov     [rsp+308h+phkResult], rax
0x180014fa9  lea     r8, aWsWs_1; "%ws\\%ws"
0x180014fb0  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x180014fb5  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014fba  mov     ebp, eax
0x180014fbc  test    eax, eax
0x180014fbe  jnz     loc_18001551F
0x180014fc4  lea     rax, [rsp+308h+hKey]
0x180014fc9  mov     r9d, 20019h; samDesired
0x180014fcf  xor     r8d, r8d; ulOptions
0x180014fd2  mov     [rsp+308h+phkResult], rax; phkResult
0x180014fd7  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x180014fdc  mov     rcx, r13; hKey
0x180014fdf  call    cs:__imp_RegOpenKeyExW
0x180014fe5  mov     ebp, eax
0x180014fe7  test    eax, eax
0x180014fe9  jz      loc_1800150AC
0x180014fef  mov     r9, rbx
0x180014ff2  movzx   eax, byte ptr [r9-1]
0x180014ff7  mov     rcx, r9
0x180014ffa  dec     r9
0x180014ffd  cmp     al, 5Ch ; '\'
0x180014fff  jz      short loc_180015008
0x180015001  cmp     r9, r15
0x180015004  ja      short loc_180014FF2
0x180015006  cmp     al, 5Ch ; '\'
0x180015008  lea     rax, [rsp+308h+SubKey]
0x18001500d  cmovz   r9, rcx
0x180015011  mov     [rsp+308h+var_2D8], rax
0x180015016  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001501d  lea     rax, aRegopenkeyexw; "RegOpenKeyExW"
0x180015024  mov     r8d, ebp
0x180015027  mov     [rsp+308h+var_2E0], rax
0x18001502c  xor     ecx, ecx
0x18001502e  mov     dword ptr [rsp+308h+phkResult], 4CAh
0x180015036  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001503b  lea     eax, [rbp-2]
0x18001503e  cmp     eax, 1
0x180015041  ja      loc_180015541
0x180015047  mov     ebp, 0C0000225h
0x18001504c  mov     r11d, ebp
0x18001504f  mov     rax, rbx
0x180015052  movzx   ecx, byte ptr [rax-1]
0x180015056  mov     r8, rax
0x180015059  dec     rax
0x18001505c  cmp     cl, 5Ch ; '\'
0x18001505f  jz      short loc_180015066
0x180015061  cmp     rax, r15
0x180015064  ja      short loc_180015052
0x180015066  xor     r10d, r10d
0x180015069  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180015070  cmp     cl, 5Ch ; '\'
0x180015073  mov     ecx, 4D4h
0x180015078  cmovz   rax, r8
0x18001507c  lea     r8, [rsp+308h+SubKey]
0x180015081  mov     [rsp+308h+var_2D8], r8
0x180015086  mov     r9, rax
0x180015089  mov     [rsp+308h+var_2E0], rdx
0x18001508e  mov     r8d, r11d
0x180015091  mov     dword ptr [rsp+308h+phkResult], ecx
0x180015095  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001509c  mov     rcx, r10
0x18001509f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800150a4  test    ebp, ebp
0x1800150a6  js      loc_1800151C0
0x1800150ac  mov     rcx, [rsp+308h+hKey]; hKey
0x1800150b1  call    cs:__imp_RegCloseKey
0x1800150b7  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800150be  mov     [rsp+308h+hKey], 0
0x1800150c7  call    cs:__imp_RtlConvertSharedToExclusive
0x1800150cd  mov     r8b, 1; bool
0x1800150d0  mov     rdx, rsi; lpSrcStr
0x1800150d3  mov     rcx, r13; hKey
0x1800150d6  call    ?_RemoveUserFromName2SidCache@@YAJPEAUHKEY__@@PEAG_N@Z; _RemoveUserFromName2SidCache(HKEY__ *,ushort *,bool)
0x1800150db  lea     rbp, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x1800150e2  mov     r8d, eax
0x1800150e5  test    eax, eax
0x1800150e7  jnz     loc_180015557
0x1800150ed  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800150f4  call    cs:__imp_RtlConvertExclusiveToShared
0x1800150fa  cmp     [rsp+308h+var_2C0], 0
0x180015100  jnz     loc_180015317
0x180015106  xor     r14d, r14d
0x180015109  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180015110  call    cs:__imp_RtlReleaseResource
0x180015116  test    rsi, rsi
0x180015119  jz      short loc_18001512E
0x18001511b  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180015122  mov     rcx, rsi
0x180015125  mov     rax, [rax+30h]
0x180015129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001512e  mov     rcx, [rsp+308h+hKey]; hKey
0x180015133  mov     r15, [rsp+308h+var_38]
0x18001513b  mov     r13, [rsp+308h+var_30]
0x180015143  mov     r12, [rsp+308h+var_28]
0x18001514b  mov     rdi, [rsp+308h+var_20]
0x180015153  mov     rsi, [rsp+308h+var_18]
0x18001515b  mov     rbp, [rsp+308h+var_10]
0x180015163  mov     rbx, [rsp+308h+arg_18]
0x18001516b  test    rcx, rcx
0x18001516e  jnz     loc_1800156D5
0x180015174  mov     eax, r14d
0x180015177  mov     rcx, [rsp+308h+var_48]
0x18001517f  xor     rcx, rsp; StackCookie
0x180015182  call    __security_check_cookie
0x180015187  add     rsp, 300h
0x18001518e  pop     r14
0x180015190  retn
0x180015191  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180015198  mov     edi, 0C0000095h
0x18001519d  mov     r10, r14
0x1800151a0  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800151a7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800151ac  mov     rbx, rax
0x1800151af  lea     rcx, aRtldwordmult; "RtlDWordMult"
0x1800151b6  mov     eax, 2Ah ; '*'
0x1800151bb  jmp     loc_180014E47
0x1800151c0  xor     r13d, r13d
0x1800151c3  cmp     ebp, 0C0000225h
0x1800151c9  cmovnz  r13d, ebp
0x1800151cd  test    r13d, r13d
0x1800151d0  jnz     loc_18001527F
0x1800151d6  lea     rbp, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x1800151dd  cmp     r13d, 0C000009Ah
0x1800151e4  jnz     loc_1800150FA
0x1800151ea  jmp     loc_1800152C4
0x1800151ef  mov     rax, rbx
0x1800151f2  movzx   ecx, byte ptr [rax-1]
0x1800151f6  mov     rdx, rax
0x1800151f9  dec     rax
0x1800151fc  cmp     cl, 5Ch ; '\'
0x1800151ff  jz      short loc_180015206
0x180015201  cmp     rax, r15
0x180015204  ja      short loc_1800151F2
0x180015206  xor     r10d, r10d
0x180015209  mov     r11d, ebp
0x18001520c  cmp     cl, 5Ch ; '\'
0x18001520f  mov     r8, r12
0x180015212  mov     ecx, 4B8h
0x180015217  cmovz   rax, rdx
0x18001521b  lea     rdx, aGethashstring; "GetHashString"
0x180015222  jmp     loc_180015081
0x180015227  lea     rbx, pbInput+24h; ""
0x18001522e  mov     r9, rbx
0x180015231  lea     r15, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180015238  movzx   eax, byte ptr [r9-1]
0x18001523d  mov     rcx, r9
0x180015240  dec     r9
0x180015243  cmp     al, 5Ch ; '\'
0x180015245  jz      short loc_18001524E
0x180015247  cmp     r9, r15
0x18001524a  ja      short loc_180015238
0x18001524c  cmp     al, 5Ch ; '\'
0x18001524e  cmovz   r9, rcx
0x180015252  lea     r12, Class
0x180015259  mov     [rsp+308h+var_2D8], r12
0x18001525e  mov     r8d, r14d
0x180015261  mov     [rsp+308h+var_2E0], rdx
0x180015266  xor     ecx, ecx
0x180015268  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001526f  mov     dword ptr [rsp+308h+phkResult], 4B2h
0x180015277  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001527c  mov     r13d, r14d
0x18001527f  lea     rbp, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180015286  mov     rcx, rbp; char *
0x180015289  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001528e  mov     r9, rax
0x180015291  mov     [rsp+308h+var_2D8], r12
0x180015296  lea     rax, aFinduserincach_1; "FindUserInCacheByNamePreRS2"
0x18001529d  mov     r8d, r13d
0x1800152a0  mov     [rsp+308h+var_2E0], rax
0x1800152a5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800152ac  xor     ecx, ecx
0x1800152ae  mov     dword ptr [rsp+308h+phkResult], 943h
0x1800152b6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
  ... truncated ...
```
