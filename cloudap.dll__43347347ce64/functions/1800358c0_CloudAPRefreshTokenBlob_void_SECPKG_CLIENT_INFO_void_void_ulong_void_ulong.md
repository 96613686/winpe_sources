# CloudAPRefreshTokenBlob(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x1800358c0`
- end: `0x180035c4e`
- name: `?CloudAPRefreshTokenBlob@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `910`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int Size, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000c450`
- `0x18000e900`
- `0x18000ee60`
- `0x180010320`
- `0x1800358c0`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b6d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180035b4f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180035b4f`

## string_xrefs

- `0x180035924`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18003596f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800359ce`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180035a31`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180035a96`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180035af6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180035b7c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180035bbc`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180035ab1`: `CheckPkgSID`

## pseudocode

```c
__int64 __fastcall CloudAPRefreshTokenBlob(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int Size,
        void **a6,
        unsigned int *a7)
{
  void *v7; // rdi
  struct _LOGON_SESSION *v8; // r13
  struct _ApPluginPkg *v9; // rbp
  struct _SECPKG_CLIENT_INFO *v11; // r14
  int v12; // eax
  unsigned int v13; // eax
  unsigned int LastError; // ebx
  const char *v15; // r9
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // rax
  const char *v20; // rax
  void *v21; // rax
  __int64 v22; // rcx
  _BYTE *v23; // rax
  int v25; // [rsp+20h] [rbp-68h]
  const char *v26; // [rsp+28h] [rbp-60h]
  struct _LOGON_SESSION *v27; // [rsp+40h] [rbp-48h] BYREF
  struct _ApPluginPkg *v28; // [rsp+48h] [rbp-40h] BYREF

  v7 = 0;
  v8 = 0;
  v9 = 0;
  v11 = a2;
  v27 = 0;
  *a6 = 0;
  v28 = 0;
  *a7 = 0;
  if ( Size < 0x14 || !a3 )
  {
    LastError = -1073741811;
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v26 = "Invalid Arg(s)";
    v25 = 2640;
    goto LABEL_29;
  }
  v12 = *((_DWORD *)a3 + 3);
  if ( v12 )
  {
    v13 = v12 + 19;
    if ( v13 < 0x13 )
    {
      LastError = -1073741675;
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "RtlDWordAdd";
      v25 = 2649;
      goto LABEL_6;
    }
    if ( Size < v13 )
    {
      LastError = -1073741811;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, 2654, "Invalid length", &Class);
      goto LABEL_30;
    }
  }
  if ( a2->HasTcbPrivilege )
    a2 = (struct _SECPKG_CLIENT_INFO *)(a3 + 4);
  else
    *(LUID *)(a3 + 4) = a2->LogonId;
  LastError = _AcquireLogonSession(1, &a2->LogonId, &v27);
  if ( LastError )
  {
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v19, 2669, "AcquireLogonSession", &Class);
    v8 = v27;
    goto LABEL_30;
  }
  v8 = v27;
  LastError = RefPackage((struct _GUID *)((char *)v27 + 36), &v28);
  if ( LastError )
  {
    v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v20, 2674, "RefPackage", &Class);
    v9 = v28;
    goto LABEL_30;
  }
  v9 = v28;
  if ( !*((_DWORD *)a3 + 3) || (LastError = CheckPkgSID(v11, v28)) == 0 )
  {
    if ( *((_QWORD *)v9 + 32) )
    {
      v21 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(Size);
      v7 = v21;
      if ( !v21 )
      {
        LastError = -1073741801;
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "AllocateLsaHeap";
        v25 = 2695;
        goto LABEL_6;
      }
      memcpy_0(v21, a3, Size);
      if ( !QueueUserWorkItem(RefreshTokenBlobWkItem, v7, 0) )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          LastError = GetLastError();
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "QueueUserWorkItem";
        v25 = 2705;
        goto LABEL_6;
      }
    }
    LastError = 0;
    v7 = 0;
    goto LABEL_30;
  }
  v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  v26 = "CheckPkgSID";
  v25 = 2680;
LABEL_6:
  v16 = LastError;
LABEL_29:
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v15, v25, v26, &Class);
LABEL_30:
  DerefPackage(v9);
  ReleaseLogonSession(v8);
  if ( v7 )
  {
    v22 = Size;
    v23 = v7;
    if ( Size )
    {
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
    }
    ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800358c0  push    rbx
0x1800358c2  push    rbp
0x1800358c3  push    rsi
0x1800358c4  push    rdi
0x1800358c5  push    r13
0x1800358c7  push    r14
0x1800358c9  sub     rsp, 58h
0x1800358cd  mov     rax, [rsp+88h+arg_28]
0x1800358d5  xor     edi, edi
0x1800358d7  xor     r13d, r13d
0x1800358da  xor     ebp, ebp
0x1800358dc  cmp     dword ptr [rsp+88h+Size], 14h
0x1800358e4  mov     rsi, r8
0x1800358e7  mov     r14, rdx
0x1800358ea  mov     [rsp+88h+var_48], r13
0x1800358ef  mov     [rax], rdi
0x1800358f2  mov     rax, [rsp+88h+arg_30]
0x1800358fa  mov     [rsp+88h+var_40], rbp
0x1800358ff  mov     [rax], edi
0x180035901  jb      loc_180035BB6
0x180035907  test    r8, r8
0x18003590a  jz      loc_180035BB6
0x180035910  mov     eax, [r8+0Ch]
0x180035914  test    eax, eax
0x180035916  jz      loc_1800359A6
0x18003591c  add     eax, 13h
0x18003591f  cmp     eax, 13h
0x180035922  jnb     short loc_180035960
0x180035924  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18003592b  mov     ebx, 0C0000095h
0x180035930  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035935  mov     r9, rax
0x180035938  lea     rax, Class
0x18003593f  mov     [rsp+88h+var_58], rax
0x180035944  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18003594b  mov     [rsp+88h+var_60], rax
0x180035950  mov     [rsp+88h+var_68], 0A59h
0x180035958  mov     r8d, ebx
0x18003595b  jmp     loc_180035BEE
0x180035960  cmp     dword ptr [rsp+88h+Size], eax
0x180035967  jnb     short loc_1800359A6
0x180035969  mov     r8d, 0C000000Dh
0x18003596f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180035976  mov     ebx, r8d
0x180035979  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003597e  mov     r9, rax
0x180035981  lea     rax, Class
0x180035988  mov     [rsp+88h+var_58], rax
0x18003598d  lea     rax, aInvalidLength; "Invalid length"
0x180035994  mov     [rsp+88h+var_60], rax
0x180035999  mov     [rsp+88h+var_68], 0A5Eh
0x1800359a1  jmp     loc_180035BEE
0x1800359a6  cmp     [rdx+10h], dil
0x1800359aa  jz      short loc_1800359B2
0x1800359ac  lea     rdx, [r8+4]; struct _LUID *
0x1800359b0  jmp     short loc_1800359B9
0x1800359b2  mov     rax, [rdx]
0x1800359b5  mov     [r8+4], rax
0x1800359b9  lea     r8, [rsp+88h+var_48]; struct _LOGON_SESSION **
0x1800359be  mov     ecx, 1; int
0x1800359c3  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x1800359c8  mov     ebx, eax
0x1800359ca  test    eax, eax
0x1800359cc  jz      short loc_180035A18
0x1800359ce  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800359d5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800359da  mov     r9, rax
0x1800359dd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800359e4  lea     rax, Class
0x1800359eb  mov     r8d, ebx
0x1800359ee  mov     [rsp+88h+var_58], rax
0x1800359f3  xor     ecx, ecx
0x1800359f5  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x1800359fc  mov     [rsp+88h+var_60], rax
0x180035a01  mov     [rsp+88h+var_68], 0A6Dh
0x180035a09  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180035a0e  mov     r13, [rsp+88h+var_48]
0x180035a13  jmp     loc_180035BFC
0x180035a18  mov     r13, [rsp+88h+var_48]
0x180035a1d  lea     rdx, [rsp+88h+var_40]; struct _ApPluginPkg **
0x180035a22  lea     rcx, [r13+24h]; struct _GUID *
0x180035a26  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180035a2b  mov     ebx, eax
0x180035a2d  test    eax, eax
0x180035a2f  jz      short loc_180035A7B
0x180035a31  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180035a38  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035a3d  mov     r9, rax
0x180035a40  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180035a47  lea     rax, Class
0x180035a4e  mov     r8d, ebx
0x180035a51  mov     [rsp+88h+var_58], rax
0x180035a56  xor     ecx, ecx
0x180035a58  lea     rax, aRefpackage; "RefPackage"
0x180035a5f  mov     [rsp+88h+var_60], rax
0x180035a64  mov     [rsp+88h+var_68], 0A72h
0x180035a6c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180035a71  mov     rbp, [rsp+88h+var_40]
0x180035a76  jmp     loc_180035BFC
0x180035a7b  mov     rbp, [rsp+88h+var_40]
0x180035a80  cmp     [rsi+0Ch], edi
0x180035a83  jbe     short loc_180035ACA
0x180035a85  mov     rdx, rbp; struct _ApPluginPkg *
0x180035a88  mov     rcx, r14; struct _SECPKG_CLIENT_INFO *
0x180035a8b  call    ?CheckPkgSID@@YAJPEAU_SECPKG_CLIENT_INFO@@PEAU_ApPluginPkg@@@Z; CheckPkgSID(_SECPKG_CLIENT_INFO *,_ApPluginPkg *)
0x180035a90  mov     ebx, eax
0x180035a92  test    eax, eax
0x180035a94  jz      short loc_180035ACA
0x180035a96  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180035a9d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035aa2  mov     r9, rax
0x180035aa5  lea     rax, Class
0x180035aac  mov     [rsp+88h+var_58], rax
0x180035ab1  lea     rax, aCheckpkgsid; "CheckPkgSID"
0x180035ab8  mov     [rsp+88h+var_60], rax
0x180035abd  mov     [rsp+88h+var_68], 0A78h
0x180035ac5  jmp     loc_180035958
0x180035aca  cmp     [rbp+100h], rdi
0x180035ad1  jz      loc_180035BB0
0x180035ad7  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180035ade  mov     ecx, dword ptr [rsp+88h+Size]
0x180035ae5  mov     rax, [rax+28h]
0x180035ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035aee  mov     rdi, rax
0x180035af1  test    rax, rax
0x180035af4  jnz     short loc_180035B2F
0x180035af6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180035afd  mov     ebx, 0C0000017h
0x180035b02  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035b07  mov     r9, rax
0x180035b0a  lea     rax, Class
0x180035b11  mov     [rsp+88h+var_58], rax
0x180035b16  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180035b1d  mov     [rsp+88h+var_60], rax
0x180035b22  mov     [rsp+88h+var_68], 0A87h
0x180035b2a  jmp     loc_180035958
0x180035b2f  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x180035b37  mov     rdx, rsi; Src
0x180035b3a  mov     rcx, rdi; void *
0x180035b3d  call    memcpy_0
0x180035b42  xor     r8d, r8d; Flags
0x180035b45  lea     rcx, ?RefreshTokenBlobWkItem@@YAKPEAX@Z; Function
0x180035b4c  mov     rdx, rdi; Context
0x180035b4f  call    cs:__imp_QueueUserWorkItem
0x180035b55  test    eax, eax
0x180035b57  jnz     short loc_180035BB0
0x180035b59  call    cs:__imp_GetLastError
0x180035b5f  test    eax, eax
0x180035b61  jg      short loc_180035B6D
0x180035b63  call    cs:__imp_GetLastError
0x180035b69  mov     ebx, eax
0x180035b6b  jmp     short loc_180035B7C
0x180035b6d  call    cs:__imp_GetLastError
0x180035b73  movzx   ebx, ax
0x180035b76  or      ebx, 0C0070000h
0x180035b7c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180035b83  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035b88  mov     r9, rax
0x180035b8b  lea     rax, Class
0x180035b92  mov     [rsp+88h+var_58], rax
0x180035b97  lea     rax, aQueueuserworki; "QueueUserWorkItem"
0x180035b9e  mov     [rsp+88h+var_60], rax
0x180035ba3  mov     [rsp+88h+var_68], 0A91h
0x180035bab  jmp     loc_180035958
0x180035bb0  xor     ebx, ebx
0x180035bb2  xor     edi, edi
0x180035bb4  jmp     short loc_180035BFC
0x180035bb6  mov     r8d, 0C000000Dh
0x180035bbc  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180035bc3  mov     ebx, r8d
0x180035bc6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035bcb  mov     r9, rax
0x180035bce  lea     rax, Class
0x180035bd5  mov     [rsp+88h+var_58], rax
0x180035bda  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x180035be1  mov     [rsp+88h+var_60], rax
0x180035be6  mov     [rsp+88h+var_68], 0A50h
0x180035bee  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180035bf5  xor     ecx, ecx
0x180035bf7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180035bfc  mov     rcx, rbp; struct _ApPluginPkg *
0x180035bff  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x180035c04  mov     rcx, r13; struct _LOGON_SESSION *
0x180035c07  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x180035c0c  test    rdi, rdi
0x180035c0f  jz      short loc_180035C3F
0x180035c11  mov     ecx, dword ptr [rsp+88h+Size]
0x180035c18  mov     rax, rdi
0x180035c1b  test    rcx, rcx
0x180035c1e  jz      short loc_180035C2C
0x180035c20  mov     byte ptr [rax], 0
0x180035c23  inc     rax
0x180035c26  sub     rcx, 1
0x180035c2a  jnz     short loc_180035C20
0x180035c2c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180035c33  mov     rcx, rdi
0x180035c36  mov     rax, [rax+30h]
0x180035c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c3f  mov     eax, ebx
0x180035c41  add     rsp, 58h
0x180035c45  pop     r14
0x180035c47  pop     r13
0x180035c49  pop     rdi
0x180035c4a  pop     rsi
0x180035c4b  pop     rbp
0x180035c4c  pop     rbx
0x180035c4d  retn
```
