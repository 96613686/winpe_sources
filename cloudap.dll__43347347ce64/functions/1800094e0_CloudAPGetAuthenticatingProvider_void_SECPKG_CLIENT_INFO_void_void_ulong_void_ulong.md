# CloudAPGetAuthenticatingProvider(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x1800094e0`
- end: `0x1800099ad`
- name: `?CloudAPGetAuthenticatingProvider@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1229`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180007fc0`
- `0x1800094e0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000f100`
- `0x180041770`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000971d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000971d`
- `ntdll!RtlReleaseResource` at `0x1800096e8`
- `ntdll!RtlReleaseResource` at `0x180009744`
- `ntdll!RtlReleaseResource` at `0x1800098f9`
- `ntdll!RtlReleaseResource` at `0x1800096e8`
- `ntdll!RtlReleaseResource` at `0x180009744`
- `ntdll!RtlReleaseResource` at `0x1800098f9`
- `ntdll!RtlAcquireResourceShared` at `0x18000956f`
- `ntdll!RtlAcquireResourceShared` at `0x18000956f`
- `ntdll!RtlEnterCriticalSection` at `0x180009579`
- `ntdll!RtlEnterCriticalSection` at `0x180009669`
- `ntdll!RtlEnterCriticalSection` at `0x180009579`
- `ntdll!RtlEnterCriticalSection` at `0x180009669`
- `ntdll!RtlLeaveCriticalSection` at `0x1800095ed`
- `ntdll!RtlLeaveCriticalSection` at `0x1800096da`
- `ntdll!RtlLeaveCriticalSection` at `0x1800095ed`
- `ntdll!RtlLeaveCriticalSection` at `0x1800096da`

## string_xrefs

- `0x18000975f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800097bd`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180009828`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180009925`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000996f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180009855`: `No Token Blob with logon session`
- `0x18000998d`: `CopyToClientBuffer`

## pseudocode

```c
__int64 __fastcall CloudAPGetAuthenticatingProvider(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int *a7)
{
  bool v8; // cf
  struct _LOGON_SESSION *v9; // rdi
  _QWORD *v10; // r14
  unsigned int *v11; // r15
  unsigned int v12; // esi
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rax
  const char *v22; // r9
  char v23; // al
  const char *v24; // rdx
  bool v25; // zf
  const char *v26; // r9
  char v27; // al
  const char *v28; // rdx
  bool v29; // zf
  const char *v30; // r9
  char v31; // al
  const char *v32; // rdx
  bool v33; // zf
  __int64 v34; // rax
  struct _LOGON_SESSION **v35; // rdx
  struct _USER_CACHE_ENTRY *v36; // rax
  const char *v37; // r9
  const char *v38; // r9
  struct _LOGON_SESSION *v39; // [rsp+80h] [rbp+18h] BYREF

  v8 = a5 < 0xC;
  v9 = 0;
  v10 = a6;
  v11 = a7;
  v39 = 0;
  *a6 = 0;
  *v11 = 0;
  if ( v8 || !a3 )
  {
    v12 = -1073741811;
    v22 = "";
    while ( 1 )
    {
      v23 = *(v22 - 1);
      v24 = v22--;
      v25 = v23 == 92;
      if ( v23 == 92 )
        break;
      if ( v22 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v25 = v23 == 92;
        break;
      }
    }
    if ( v25 )
      v22 = v24;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v22, 1876, "Invalid Arg(s)", &Class);
  }
  else
  {
    v12 = _AcquireLogonSession(1, (struct _LUID *)(a3 + 4), &v39);
    if ( v12 )
    {
      v26 = "";
      while ( 1 )
      {
        v27 = *(v26 - 1);
        v28 = v26--;
        v29 = v27 == 92;
        if ( v27 == 92 )
          break;
        if ( v26 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
        {
          v29 = v27 == 92;
          break;
        }
      }
      if ( v29 )
        v26 = v28;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v26, 1882, "AcquireLogonSession", &Class);
      v9 = v39;
    }
    else
    {
      v9 = v39;
      v13 = *((_QWORD *)v39 + 7);
      RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v13 + 24) + 24LL), 1u);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v13 + 32));
      if ( !*(_DWORD *)(v13 + 76) )
      {
        v14 = *(_QWORD *)(v13 + 288);
        if ( v14 )
          ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaUnprotectMemory)(
            v14,
            *(unsigned int *)(v13 + 280));
        v15 = *(_QWORD *)(v13 + 264);
        if ( v15 && *(_DWORD *)(v15 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v15 + *(unsigned int *)(v15 + 8));
        v16 = *(_QWORD *)(v13 + 272);
        if ( v16 && *(_DWORD *)(v16 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v16 + *(unsigned int *)(v16 + 8));
      }
      ++*(_DWORD *)(v13 + 76);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v13 + 32));
      if ( *(_DWORD *)(v13 + 280) && *(_QWORD *)(v13 + 288) )
      {
        v12 = ((__int64 (__fastcall *)(void **, __int64, _QWORD *))g_pLsaFunctionTable->AllocateClientBuffer)(
                a1,
                16,
                v10);
        if ( v12 )
        {
          v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v37, 1902, "AllocateClientBuffer", &Class);
        }
        else
        {
          v12 = ((__int64 (__fastcall *)(void **, __int64, _QWORD, char *))g_pLsaFunctionTable->CopyToClientBuffer)(
                  a1,
                  16,
                  *v10,
                  (char *)v9 + 36);
          if ( (v12 & 0x80000000) != 0 )
          {
            ((void (__fastcall *)(void **, _QWORD))g_pLsaFunctionTable->FreeClientBuffer)(a1, *v10);
            *v10 = 0;
            v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v38, 1915, "CopyToClientBuffer", &Class);
          }
          else
          {
            *v11 = 16;
            v12 = 0;
          }
        }
      }
      else
      {
        v12 = -1073741729;
        v30 = "";
        while ( 1 )
        {
          v31 = *(v30 - 1);
          v32 = v30--;
          v33 = v31 == 92;
          if ( v31 == 92 )
            break;
          if ( v30 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
          {
            v33 = v31 == 92;
            break;
          }
        }
        if ( v33 )
          v30 = v32;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225567LL, v30, 1895, "No Token Blob with logon session", &Class);
      }
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v13 + 32));
      v25 = (*(_DWORD *)(v13 + 76))-- == 1;
      if ( v25 )
      {
        v17 = *(_QWORD *)(v13 + 288);
        if ( v17 )
          ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaProtectMemory)(
            v17,
            *(unsigned int *)(v13 + 280));
        v18 = *(_QWORD *)(v13 + 264);
        if ( v18 && *(_DWORD *)(v18 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaProtectMemory)(v18 + *(unsigned int *)(v18 + 8));
        v19 = *(_QWORD *)(v13 + 272);
        if ( v19 && *(_DWORD *)(v19 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaProtectMemory)(v19 + *(unsigned int *)(v19 + 8));
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v13 + 32));
      RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v13 + 24) + 24LL));
    }
  }
  if ( v9 )
  {
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    v20 = *(_QWORD **)((char *)v9 + 28);
    _InterlockedDecrement((volatile signed __int32 *)v9 + 4);
    v25 = *((_DWORD *)v9 + 4) == 0;
    a6 = v20;
    if ( v25 )
    {
      v34 = *(_QWORD *)v9;
      if ( *(struct _LOGON_SESSION **)(*(_QWORD *)v9 + 8LL) != v9
        || (v35 = (struct _LOGON_SESSION **)*((_QWORD *)v9 + 1), *v35 != v9) )
      {
        __fastfail(3u);
      }
      *v35 = (struct _LOGON_SESSION *)v34;
      *(_QWORD *)(v34 + 8) = v35;
      RtlReleaseResource(&g_LogonSessionListLock);
      v36 = _FreeLogonSession(v9);
      if ( v36 )
        _ReleaseUserCacheEntry((struct _LUID *)&a6, v36);
    }
    else
    {
      RtlReleaseResource(&g_LogonSessionListLock);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800094e0  mov     rax, rsp
0x1800094e3  push    rsi
0x1800094e4  push    rdi
0x1800094e5  sub     rsp, 58h
0x1800094e9  mov     [rax+20h], r12
0x1800094ed  mov     r12, rcx
0x1800094f0  mov     [rax-18h], r13
0x1800094f4  xor     r13d, r13d
0x1800094f7  cmp     [rsp+68h+arg_20], 0Ch
0x1800094ff  mov     edi, r13d
0x180009502  mov     [rax-20h], r14
0x180009506  mov     r14, qword ptr [rsp+68h+arg_28.LowPart]
0x18000950e  mov     [rax-28h], r15
0x180009512  mov     r15, [rsp+68h+arg_30]
0x18000951a  mov     [rax+18h], r13
0x18000951e  mov     [r14], r13
0x180009521  mov     [r15], r13d
0x180009524  jb      loc_180009753
0x18000952a  test    r8, r8
0x18000952d  jz      loc_180009753
0x180009533  lea     rdx, [r8+4]; struct _LUID *
0x180009537  mov     ecx, 1; int
0x18000953c  lea     r8, [rax+18h]; struct _LOGON_SESSION **
0x180009540  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x180009545  mov     esi, eax
0x180009547  test    eax, eax
0x180009549  jnz     loc_1800097B6
0x18000954f  mov     rdi, [rsp+68h+arg_10]
0x180009557  mov     dl, 1; Wait
0x180009559  mov     [rsp+68h+arg_0], rbx
0x18000955e  mov     [rsp+68h+arg_8], rbp
0x180009563  mov     rbx, [rdi+38h]
0x180009567  mov     rcx, [rbx+18h]
0x18000956b  add     rcx, 18h; Resource
0x18000956f  call    cs:__imp_RtlAcquireResourceShared
0x180009575  lea     rcx, [rbx+20h]; CriticalSection
0x180009579  call    cs:__imp_RtlEnterCriticalSection
0x18000957f  cmp     [rbx+4Ch], r13d
0x180009583  jnz     short loc_1800095E6
0x180009585  mov     rcx, [rbx+120h]
0x18000958c  test    rcx, rcx
0x18000958f  jz      short loc_1800095AA
0x180009591  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009598  mov     edx, [rbx+118h]
0x18000959e  mov     rax, [rax+168h]
0x1800095a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095aa  mov     rax, [rbx+108h]
0x1800095b1  test    rax, rax
0x1800095b4  jz      short loc_1800095D6
0x1800095b6  mov     edx, [rax+0Ch]
0x1800095b9  test    edx, edx
0x1800095bb  jz      short loc_1800095D6
0x1800095bd  mov     ecx, [rax+8]
0x1800095c0  add     rcx, rax
0x1800095c3  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800095ca  mov     rax, [rax+168h]
0x1800095d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d6  mov     rax, [rbx+110h]
0x1800095dd  test    rax, rax
0x1800095e0  jnz     loc_1800098A8
0x1800095e6  inc     dword ptr [rbx+4Ch]
0x1800095e9  lea     rcx, [rbx+20h]; CriticalSection
0x1800095ed  call    cs:__imp_RtlLeaveCriticalSection
0x1800095f3  cmp     [rbx+118h], r13d
0x1800095fa  jz      loc_18000981C
0x180009600  cmp     [rbx+120h], r13
0x180009607  jz      loc_18000981C
0x18000960d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009614  mov     r8, r14
0x180009617  mov     edx, 10h
0x18000961c  mov     rcx, r12
0x18000961f  mov     rax, [rax+38h]
0x180009623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009628  mov     esi, eax
0x18000962a  test    eax, eax
0x18000962c  jnz     loc_180009925
0x180009632  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009639  lea     r9, [rdi+24h]
0x18000963d  mov     r8, [r14]
0x180009640  mov     edx, 10h
0x180009645  mov     rcx, r12
0x180009648  mov     rax, [rax+48h]
0x18000964c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009651  mov     esi, eax
0x180009653  test    eax, eax
0x180009655  js      loc_180009959
0x18000965b  mov     dword ptr [r15], 10h
0x180009662  mov     esi, r13d
0x180009665  lea     rcx, [rbx+20h]; CriticalSection
0x180009669  call    cs:__imp_RtlEnterCriticalSection
0x18000966f  add     dword ptr [rbx+4Ch], 0FFFFFFFFh
0x180009673  jnz     short loc_1800096D6
0x180009675  mov     rcx, [rbx+120h]
0x18000967c  test    rcx, rcx
0x18000967f  jz      short loc_18000969A
0x180009681  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009688  mov     edx, [rbx+118h]
0x18000968e  mov     rax, [rax+160h]
0x180009695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969a  mov     rax, [rbx+108h]
0x1800096a1  test    rax, rax
0x1800096a4  jz      short loc_1800096C6
0x1800096a6  mov     edx, [rax+0Ch]
0x1800096a9  test    edx, edx
0x1800096ab  jz      short loc_1800096C6
0x1800096ad  mov     ecx, [rax+8]
0x1800096b0  add     rcx, rax
0x1800096b3  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800096ba  mov     rax, [rax+160h]
0x1800096c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c6  mov     rax, [rbx+110h]
0x1800096cd  test    rax, rax
0x1800096d0  jnz     loc_18000987F
0x1800096d6  lea     rcx, [rbx+20h]; CriticalSection
0x1800096da  call    cs:__imp_RtlLeaveCriticalSection
0x1800096e0  mov     rcx, [rbx+18h]
0x1800096e4  add     rcx, 18h; Resource
0x1800096e8  call    cs:__imp_RtlReleaseResource
0x1800096ee  mov     rbp, [rsp+68h+arg_8]
0x1800096f3  mov     rbx, [rsp+68h+arg_0]
0x1800096f8  mov     r15, [rsp+68h+var_28]
0x1800096fd  mov     r14, [rsp+68h+var_20]
0x180009702  mov     r13, [rsp+68h+var_18]
0x180009707  mov     r12, [rsp+68h+arg_18]
0x18000970f  test    rdi, rdi
0x180009712  jz      short loc_18000974A
0x180009714  mov     dl, 1; Wait
0x180009716  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000971d  call    cs:__imp_RtlAcquireResourceExclusive
0x180009723  mov     rax, [rdi+1Ch]
0x180009727  lock dec dword ptr [rdi+10h]
0x18000972b  cmp     dword ptr [rdi+10h], 0
0x18000972f  mov     qword ptr [rsp+68h+arg_28.LowPart], rax
0x180009737  jz      loc_1800098D1
0x18000973d  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180009744  call    cs:__imp_RtlReleaseResource
0x18000974a  mov     eax, esi
0x18000974c  add     rsp, 58h
0x180009750  pop     rdi
0x180009751  pop     rsi
0x180009752  retn
0x180009753  mov     esi, 0C000000Dh
0x180009758  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000975f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180009766  movzx   eax, byte ptr [r9-1]
0x18000976b  mov     rdx, r9
0x18000976e  dec     r9
0x180009771  cmp     al, 5Ch ; '\'
0x180009773  jz      short loc_18000977C
0x180009775  cmp     r9, rcx
0x180009778  ja      short loc_180009766
0x18000977a  cmp     al, 5Ch ; '\'
0x18000977c  cmovz   r9, rdx
0x180009780  lea     rax, Class
0x180009787  mov     [rsp+68h+var_38], rax
0x18000978c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180009793  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000979a  mov     r8d, esi
0x18000979d  mov     [rsp+68h+var_40], rax
0x1800097a2  xor     ecx, ecx
0x1800097a4  mov     [rsp+68h+var_48], 754h
0x1800097ac  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800097b1  jmp     loc_1800096F8
0x1800097b6  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x1800097bd  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800097c4  movzx   eax, byte ptr [r9-1]
0x1800097c9  mov     rdx, r9
0x1800097cc  dec     r9
0x1800097cf  cmp     al, 5Ch ; '\'
0x1800097d1  jz      short loc_1800097DA
0x1800097d3  cmp     r9, rcx
0x1800097d6  ja      short loc_1800097C4
0x1800097d8  cmp     al, 5Ch ; '\'
0x1800097da  cmovz   r9, rdx
0x1800097de  lea     rax, Class
0x1800097e5  mov     [rsp+68h+var_38], rax
0x1800097ea  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800097f1  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x1800097f8  mov     r8d, esi
0x1800097fb  mov     [rsp+68h+var_40], rax
0x180009800  xor     ecx, ecx
0x180009802  mov     [rsp+68h+var_48], 75Ah
0x18000980a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000980f  mov     rdi, [rsp+68h+arg_10]
0x180009817  jmp     loc_1800096F8
0x18000981c  mov     esi, 0C000005Fh
0x180009821  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x180009828  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000982f  movzx   eax, byte ptr [r9-1]
0x180009834  mov     rdx, r9
0x180009837  dec     r9
0x18000983a  cmp     al, 5Ch ; '\'
0x18000983c  jz      short loc_180009845
0x18000983e  cmp     r9, rcx
0x180009841  ja      short loc_18000982F
0x180009843  cmp     al, 5Ch ; '\'
0x180009845  lea     rax, Class
0x18000984c  cmovz   r9, rdx
0x180009850  mov     [rsp+68h+var_38], rax
0x180009855  lea     rax, aNoTokenBlobWit; "No Token Blob with logon session"
0x18000985c  mov     [rsp+68h+var_40], rax
0x180009861  mov     [rsp+68h+var_48], 767h
0x180009869  mov     r8d, esi
0x18000986c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180009873  xor     ecx, ecx
0x180009875  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000987a  jmp     loc_180009665
0x18000987f  mov     edx, [rax+0Ch]
0x180009882  test    edx, edx
0x180009884  jz      loc_1800096D6
0x18000988a  mov     ecx, [rax+8]
0x18000988d  add     rcx, rax
0x180009890  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009897  mov     rax, [rax+160h]
0x18000989e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a3  jmp     loc_1800096D6
0x1800098a8  mov     edx, [rax+0Ch]
0x1800098ab  test    edx, edx
0x1800098ad  jz      loc_1800095E6
0x1800098b3  mov     ecx, [rax+8]
0x1800098b6  add     rcx, rax
0x1800098b9  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800098c0  mov     rax, [rax+168h]
0x1800098c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cc  jmp     loc_1800095E6
0x1800098d1  mov     rax, [rdi]
0x1800098d4  cmp     [rax+8], rdi
0x1800098d8  jnz     loc_1800099A6
0x1800098de  mov     rdx, [rdi+8]
0x1800098e2  cmp     [rdx], rdi
0x1800098e5  jnz     loc_1800099A6
0x1800098eb  mov     [rdx], rax
0x1800098ee  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x1800098f5  mov     [rax+8], rdx
0x1800098f9  call    cs:__imp_RtlReleaseResource
0x1800098ff  mov     rcx, rdi; struct _LOGON_SESSION *
0x180009902  call    ?_FreeLogonSession@@YAPEAU_USER_CACHE_ENTRY@@PEAU_LOGON_SESSION@@@Z; _FreeLogonSession(_LOGON_SESSION *)
0x180009907  test    rax, rax
0x18000990a  jz      loc_18000974A
0x180009910  mov     rdx, rax; struct _USER_CACHE_ENTRY *
0x180009913  lea     rcx, [rsp+68h+arg_28]; struct _LUID *
0x18000991b  call    ?_ReleaseUserCacheEntry@@YAXPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@@Z; _ReleaseUserCacheEntry(_LUID *,_USER_CACHE_ENTRY *)
0x180009920  jmp     loc_18000974A
0x180009925  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000992c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009931  mov     r9, rax
0x180009934  lea     rax, Class
0x18000993b  mov     [rsp+68h+var_38], rax
0x180009940  lea     rax, aAllocateclient; "AllocateClientBuffer"
0x180009947  mov     [rsp+68h+var_40], rax
0x18000994c  mov     [rsp+68h+var_48], 76Eh
0x180009954  jmp     loc_180009869
0x180009959  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009960  mov     rcx, r12
0x180009963  mov     rdx, [r14]
0x180009966  mov     rax, [rax+40h]
0x18000996a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180009976  mov     [r14], r13
0x180009979  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000997e  mov     r9, rax
0x180009981  lea     rax, Class
0x180009988  mov     [rsp+68h+var_38], rax
0x18000998d  lea     rax, aCopytoclientbu; "CopyToClientBuffer"
0x180009994  mov     [rsp+68h+var_40], rax
0x180009999  mov     [rsp+68h+var_48], 77Bh
0x1800099a1  jmp     loc_180009869
0x1800099a6  mov     ecx, 3
0x1800099ab  int     29h; Win8: RtlFailFast(ecx)
```
