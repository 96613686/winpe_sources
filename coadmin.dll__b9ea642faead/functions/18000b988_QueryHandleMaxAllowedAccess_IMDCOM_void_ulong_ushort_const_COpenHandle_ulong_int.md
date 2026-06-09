# QueryHandleMaxAllowedAccess(IMDCOM *,void *,ulong,ushort const *,COpenHandle *,ulong *,int *)

- ea: `0x18000b988`
- end: `0x18000bdd3`
- name: `?QueryHandleMaxAllowedAccess@@YAJPEAUIMDCOM@@PEAXKPEBGPEAVCOpenHandle@@PEAKPEAH@Z`
- size: `1099`
- prototype: `__int64 __fastcall(struct IMDCOM *, void *, DWORD, const unsigned __int16 *, struct COpenHandle *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cec`

## callees

- `0x180001064`
- `0x18000aefc`
- `0x18000b1e4`
- `0x18000b3bc`
- `0x18000b624`
- `0x18000b988`
- `0x18000bddc`
- `0x18000bf98`
- `0x18000c020`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000bb71`
- `msvcrt!wcscpy_s` at `0x18000bb71`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18000bcc4`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18000bcc4`
- `ADVAPI32!AccessCheck` at `0x18000bc1e`
- `ADVAPI32!AccessCheck` at `0x18000bc1e`
- `KERNEL32!CloseHandle` at `0x18000bd31`
- `KERNEL32!CloseHandle` at `0x18000bd31`
- `KERNEL32!GetLastError` at `0x18000bcce`
- `KERNEL32!GetLastError` at `0x18000bcce`
- `IisRTL!PuDbgPrint` at `0x18000ba64`
- `IisRTL!PuDbgPrint` at `0x18000bc65`
- `IisRTL!PuDbgPrint` at `0x18000bd6c`
- `IisRTL!PuDbgPrint` at `0x18000bda4`
- `IisRTL!PuDbgPrint` at `0x18000ba64`
- `IisRTL!PuDbgPrint` at `0x18000bc65`
- `IisRTL!PuDbgPrint` at `0x18000bd6c`
- `IisRTL!PuDbgPrint` at `0x18000bda4`

## string_xrefs

- `0x18000ba58`: `inetsrv\iis\mb\coadmin\admacl.cxx`
- `0x18000bc5e`: `inetsrv\iis\mb\coadmin\admacl.cxx`
- `0x18000bd5a`: `inetsrv\iis\mb\coadmin\admacl.cxx`
- `0x18000bd9d`: `inetsrv\iis\mb\coadmin\admacl.cxx`

## pseudocode

```c
__int64 __fastcall QueryHandleMaxAllowedAccess(
        struct IMDCOM *a1,
        void *a2,
        DWORD a3,
        const unsigned __int16 *a4,
        struct COpenHandle *a5,
        unsigned int *a6,
        int *a7)
{
  struct CAdminAcl *v10; // rdi
  signed int v11; // ebx
  const unsigned __int16 *v12; // rsi
  int ThreadToken; // eax
  __int64 v14; // r8
  CAdminAclCache *v15; // rcx
  int v16; // ebx
  struct CAdminAcl *v17; // rax
  unsigned __int8 *v18; // r12
  int v19; // r15d
  unsigned __int64 v20; // rax
  CAdminAclCache *v21; // rcx
  void *v22; // rcx
  DWORD v23; // ecx
  int *v24; // rbx
  void *v25; // rax
  signed int LastError; // eax
  DWORD GrantedAccess; // [rsp+40h] [rbp-71h] BYREF
  WORD pControl[2]; // [rsp+44h] [rbp-6Dh] BYREF
  DWORD dwRevision; // [rsp+48h] [rbp-69h] BYREF
  HANDLE ClientToken; // [rsp+50h] [rbp-61h] BYREF
  WINBOOL AccessStatus; // [rsp+58h] [rbp-59h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-55h] BYREF
  struct CAdminAcl *v34; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int8 *v35; // [rsp+68h] [rbp-49h] BYREF
  int *v36; // [rsp+70h] [rbp-41h]
  unsigned int *v37; // [rsp+78h] [rbp-39h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+80h] [rbp-31h] BYREF

  dwRevision = a3;
  v37 = a6;
  v10 = 0;
  v36 = a7;
  v34 = 0;
  ClientToken = 0;
  v35 = 0;
  *(_DWORD *)pControl = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 56;
  GrantedAccess = 0;
  if ( !a6 || (*a6 = 0, !a5) || !a1 || !a2 )
  {
    v11 = -2147024809;
    goto LABEL_56;
  }
  v12 = &byte_1800127D8;
  if ( a4 )
    v12 = a4;
  ThreadToken = GetThreadToken(&ClientToken);
  v11 = ThreadToken;
  if ( ThreadToken < 0 )
  {
    if ( (g_dwDebugFlags & 4) == 0 )
      goto LABEL_56;
    v14 = 2221;
    goto LABEL_11;
  }
  ThreadToken = IsTokenLocalSystem(ClientToken);
  v11 = ThreadToken;
  if ( ThreadToken < 0 )
  {
    if ( (g_dwDebugFlags & 4) == 0 )
      goto LABEL_56;
    v14 = 2224;
LABEL_11:
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", v14, &word_1800127E6, "*%08x\n", ThreadToken);
    goto LABEL_56;
  }
  if ( !ThreadToken )
    goto LABEL_38;
  CAdminAclCache::Find(v15, a2, a3, v12, &v34);
  v10 = v34;
  v16 = 0;
  if ( !v34 )
  {
    v17 = (struct CAdminAcl *)operator new(0x240u);
    v10 = v17;
    if ( !v17 )
    {
      v11 = -2147024882;
      v10 = 0;
      goto LABEL_54;
    }
    *((_DWORD *)v17 + 142) = 1;
    *((_DWORD *)v17 + 131) = 0;
    *((_WORD *)v17 + 2) = 0;
    *((_DWORD *)v17 + 136) = 0;
    *((_QWORD *)v17 + 67) = 0;
    *((_QWORD *)v17 + 70) = 0;
    *(_DWORD *)v17 = 1265446345;
    if ( COpenHandle::GetAcl(a5, a1, v12, &v35, (unsigned int *)pControl) )
    {
      v18 = v35;
      v19 = *(_DWORD *)pControl;
    }
    else
    {
      v18 = 0;
      v19 = 0;
    }
    *((_DWORD *)v10 + 132) = dwRevision;
    v20 = -1;
    *((_QWORD *)v10 + 69) = a2;
    do
      ++v20;
    while ( v12[v20] );
    if ( v20 >= 0x104 )
    {
      *((_WORD *)v10 + 2) = 0;
    }
    else
    {
      v16 = 1;
      wcscpy_s((wchar_t *)v10 + 2, 0x104u, v12);
    }
    HashString((char *)v10 + 4, (char *)v10 + 524);
    *((_QWORD *)v10 + 67) = v18;
    *((_DWORD *)v10 + 136) = v19;
    *((_QWORD *)v10 + 70) = a1;
    (*(void (__fastcall **)(struct IMDCOM *))(*(_QWORD *)a1 + 8LL))(a1);
    *(_DWORD *)v10 = 1517104585;
    if ( v16 )
      CAdminAclCache::Add(v21, v10);
  }
  v22 = (void *)*((_QWORD *)v10 + 67);
  if ( v22 )
  {
    if ( !AccessCheck(
            v22,
            ClientToken,
            0x2000000u,
            &g_FileGenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus) )
    {
      v11 = -2147467259;
      if ( (g_dwDebugFlags & 4) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2296, &word_1800127E6, "*%08x\n", -2147467259);
      goto LABEL_54;
    }
    v23 = GrantedAccess;
    if ( (GrantedAccess & 0x20) != 0 )
    {
      v23 = GrantedAccess | 0x40002;
      GrantedAccess |= 0x40002u;
    }
    if ( (v23 & 1) == 0 )
      goto LABEL_40;
    v23 |= 0x80u;
  }
  else
  {
LABEL_38:
    v23 = -1;
  }
  GrantedAccess = v23;
LABEL_40:
  v24 = v36;
  if ( v36 && v10 )
  {
    v25 = (void *)*((_QWORD *)v10 + 67);
    pControl[0] = 0;
    dwRevision = 0;
    if ( v25 )
    {
      if ( GetSecurityDescriptorControl(v25, pControl, &dwRevision) )
      {
        *v24 = (pControl[0] >> 4) & 1;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v11 = -2147467259;
        }
        if ( v11 < 0 )
          goto LABEL_54;
      }
      v23 = GrantedAccess;
    }
    else
    {
      *v36 = 0;
    }
  }
  v11 = 0;
  *v37 = v23;
LABEL_54:
  if ( v10 )
    CAdminAcl::Release(v10);
LABEL_56:
  if ( ClientToken )
  {
    CloseHandle(ClientToken);
    ClientToken = 0;
  }
  if ( v11 >= 0 )
  {
    if ( (g_dwDebugFlags & 1) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2333, &word_1800127E6, "\n");
  }
  else if ( (g_dwDebugFlags & 8) != 0 )
  {
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2333, &word_1800127E6, "*%08x\n", v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000b988  mov     [rsp-8+arg_8], rbx
0x18000b98d  push    rbp
0x18000b98e  push    rsi
0x18000b98f  push    rdi
0x18000b990  push    r12
0x18000b992  push    r13
0x18000b994  push    r14
0x18000b996  push    r15
0x18000b998  lea     rbp, [rsp-0Fh]
0x18000b99d  sub     rsp, 0C0h
0x18000b9a4  mov     rax, cs:__security_cookie
0x18000b9ab  xor     rax, rsp
0x18000b9ae  mov     [rbp+3Fh+var_38], rax
0x18000b9b2  mov     rax, [rbp+3Fh+arg_30]
0x18000b9b6  xor     esi, esi
0x18000b9b8  mov     r15, [rbp+3Fh+arg_20]
0x18000b9bc  mov     r13, rcx
0x18000b9bf  mov     rcx, [rbp+3Fh+arg_28]
0x18000b9c3  mov     r12d, r8d
0x18000b9c6  mov     [rbp+3Fh+dwRevision], r8d
0x18000b9ca  mov     r14, rdx
0x18000b9cd  mov     [rbp+3Fh+var_78], rcx
0x18000b9d1  mov     edi, esi
0x18000b9d3  mov     [rbp+3Fh+var_80], rax
0x18000b9d7  mov     [rbp+3Fh+var_90], rsi
0x18000b9db  mov     [rbp+3Fh+ClientToken], rsi
0x18000b9df  mov     [rbp+3Fh+var_88], rsi
0x18000b9e3  mov     dword ptr [rbp+3Fh+pControl], esi
0x18000b9e6  mov     [rbp+3Fh+var_98], esi
0x18000b9e9  mov     [rbp+3Fh+var_94], 38h ; '8'
0x18000b9f0  mov     [rbp+3Fh+var_B0], esi
0x18000b9f3  test    rcx, rcx
0x18000b9f6  jnz     short loc_18000BA02
0x18000b9f8  mov     ebx, 80070057h
0x18000b9fd  jmp     loc_18000BD21
0x18000ba02  mov     [rcx], esi
0x18000ba04  test    r15, r15
0x18000ba07  jz      short loc_18000B9F8
0x18000ba09  test    r13, r13
0x18000ba0c  jz      short loc_18000B9F8
0x18000ba0e  test    r14, r14
0x18000ba11  jz      short loc_18000B9F8
0x18000ba13  test    r9, r9
0x18000ba16  lea     rsi, byte_1800127D8
0x18000ba1d  lea     rcx, [rbp+3Fh+ClientToken]; TokenHandle
0x18000ba21  cmovnz  rsi, r9
0x18000ba25  call    ?GetThreadToken@@YAJPEAPEAX@Z; GetThreadToken(void * *)
0x18000ba2a  mov     ebx, eax
0x18000ba2c  test    eax, eax
0x18000ba2e  jns     short loc_18000BA71
0x18000ba30  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ba37  lea     r14, a08x; "*%08x\n"
0x18000ba3e  jz      short loc_18000BA6A
0x18000ba40  mov     r8d, 8ADh
0x18000ba46  mov     rcx, cs:g_pDebug
0x18000ba4d  lea     r9, word_1800127E6
0x18000ba54  mov     dword ptr [rsp+0F0h+PrivilegeSetLength], eax
0x18000ba58  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x18000ba5f  mov     [rsp+0F0h+PrivilegeSet], r14
0x18000ba64  call    cs:__imp_PuDbgPrint
0x18000ba6a  xor     esi, esi
0x18000ba6c  jmp     loc_18000BD28
0x18000ba71  mov     rcx, [rbp+3Fh+ClientToken]; ClientToken
0x18000ba75  call    _IsTokenLocalSystem
0x18000ba7a  mov     ebx, eax
0x18000ba7c  test    eax, eax
0x18000ba7e  jns     short loc_18000BA9C
0x18000ba80  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ba87  jz      loc_18000BD1F
0x18000ba8d  lea     r14, a08x; "*%08x\n"
0x18000ba94  mov     r8d, 8B0h
0x18000ba9a  jmp     short loc_18000BA46
0x18000ba9c  jz      loc_18000BC8C
0x18000baa2  lea     rax, [rbp+3Fh+var_90]
0x18000baa6  mov     r9, rsi; unsigned __int16 *
0x18000baa9  mov     r8d, r12d; unsigned int
0x18000baac  mov     [rsp+0F0h+PrivilegeSet], rax; struct CAdminAcl **
0x18000bab1  mov     rdx, r14; void *
0x18000bab4  call    ?Find@CAdminAclCache@@QEAAJPEAXKPEBGPEAPEAVCAdminAcl@@@Z; CAdminAclCache::Find(void *,ulong,ushort const *,CAdminAcl * *)
0x18000bab9  mov     rdi, [rbp+3Fh+var_90]
0x18000babd  xor     ebx, ebx
0x18000babf  test    rdi, rdi
0x18000bac2  jnz     loc_18000BBD7
0x18000bac8  mov     ecx, 240h; Size
0x18000bacd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bad2  mov     rdi, rax
0x18000bad5  test    rax, rax
0x18000bad8  jz      loc_18000BBC9
0x18000bade  mov     dword ptr [rax+238h], 1
0x18000bae8  lea     r9, [rbp+3Fh+var_88]; unsigned __int8 **
0x18000baec  mov     [rax+20Ch], ebx
0x18000baf2  mov     r8, rsi; unsigned __int16 *
0x18000baf5  mov     [rax+4], bx
0x18000baf9  mov     rdx, r13; struct IMDCOM *
0x18000bafc  mov     [rax+220h], ebx
0x18000bb02  mov     rcx, r15; this
0x18000bb05  mov     [rax+218h], rbx
0x18000bb0c  mov     [rax+230h], rbx
0x18000bb13  mov     dword ptr [rax], 4B6D2DC9h
0x18000bb19  lea     rax, [rbp+3Fh+pControl]
0x18000bb1d  mov     [rsp+0F0h+PrivilegeSet], rax; unsigned int *
0x18000bb22  call    ?GetAcl@COpenHandle@@QEAAHPEAUIMDCOM@@PEBGPEAPEAEPEAK@Z; COpenHandle::GetAcl(IMDCOM *,ushort const *,uchar * *,ulong *)
0x18000bb27  test    eax, eax
0x18000bb29  jnz     short loc_18000BB33
0x18000bb2b  mov     r12d, ebx
0x18000bb2e  mov     r15d, ebx
0x18000bb31  jmp     short loc_18000BB3B
0x18000bb33  mov     r12, [rbp+3Fh+var_88]
0x18000bb37  mov     r15d, dword ptr [rbp+3Fh+pControl]
0x18000bb3b  mov     eax, [rbp+3Fh+dwRevision]
0x18000bb3e  mov     [rdi+210h], eax
0x18000bb44  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb48  mov     [rdi+228h], r14
0x18000bb4f  lea     r14, [rdi+4]
0x18000bb53  inc     rax
0x18000bb56  cmp     [rsi+rax*2], bx
0x18000bb5a  jnz     short loc_18000BB53
0x18000bb5c  mov     edx, 104h; SizeInWords
0x18000bb61  cmp     rax, rdx
0x18000bb64  jnb     short loc_18000BB7B
0x18000bb66  mov     r8, rsi; Source
0x18000bb69  mov     rcx, r14; Destination
0x18000bb6c  mov     ebx, 1
0x18000bb71  call    cs:__imp_wcscpy_s
0x18000bb77  xor     esi, esi
0x18000bb79  jmp     short loc_18000BB81
0x18000bb7b  xor     esi, esi
0x18000bb7d  mov     [r14], si
0x18000bb81  lea     rdx, [rdi+20Ch]
0x18000bb88  mov     rcx, r14
0x18000bb8b  call    _HashString
0x18000bb90  mov     [rdi+218h], r12
0x18000bb97  mov     rcx, r13
0x18000bb9a  mov     [rdi+220h], r15d
0x18000bba1  mov     [rdi+230h], r13
0x18000bba8  mov     rax, [r13+0]
0x18000bbac  mov     rax, [rax+8]
0x18000bbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb5  mov     dword ptr [rdi], 5A6D2DC9h
0x18000bbbb  test    ebx, ebx
0x18000bbbd  jz      short loc_18000BBD9
0x18000bbbf  mov     rdx, rdi; struct CAdminAcl *
0x18000bbc2  call    ?Add@CAdminAclCache@@QEAAJPEAVCAdminAcl@@@Z; CAdminAclCache::Add(CAdminAcl *)
0x18000bbc7  jmp     short loc_18000BBD9
0x18000bbc9  xor     esi, esi
0x18000bbcb  mov     ebx, 8007000Eh
0x18000bbd0  mov     edi, esi
0x18000bbd2  jmp     loc_18000BD09
0x18000bbd7  xor     esi, esi
0x18000bbd9  mov     rcx, [rdi+218h]; pSecurityDescriptor
0x18000bbe0  test    rcx, rcx
0x18000bbe3  jz      loc_18000BC8E
0x18000bbe9  mov     rdx, [rbp+3Fh+ClientToken]; ClientToken
0x18000bbed  lea     rax, [rbp+3Fh+var_98]
0x18000bbf1  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x18000bbf6  lea     r9, ?g_FileGenericMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000bbfd  lea     rax, [rbp+3Fh+var_B0]
0x18000bc01  mov     r8d, 2000000h; DesiredAccess
0x18000bc07  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x18000bc0c  lea     rax, [rbp+3Fh+var_94]
0x18000bc10  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000bc15  lea     rax, [rbp+3Fh+var_70]
0x18000bc19  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x18000bc1e  call    cs:__imp_AccessCheck
0x18000bc24  test    eax, eax
0x18000bc26  jnz     short loc_18000BC70
0x18000bc28  test    byte ptr cs:g_dwDebugFlags, 4
0x18000bc2f  mov     ebx, 80004005h
0x18000bc34  jz      loc_18000BD09
0x18000bc3a  mov     rcx, cs:g_pDebug
0x18000bc41  lea     r14, a08x; "*%08x\n"
0x18000bc48  mov     dword ptr [rsp+0F0h+PrivilegeSetLength], ebx
0x18000bc4c  lea     r9, word_1800127E6
0x18000bc53  mov     r8d, 8F8h
0x18000bc59  mov     [rsp+0F0h+PrivilegeSet], r14
0x18000bc5e  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x18000bc65  call    cs:__imp_PuDbgPrint
0x18000bc6b  jmp     loc_18000BD10
0x18000bc70  mov     ecx, [rbp+3Fh+var_B0]
0x18000bc73  test    cl, 20h
0x18000bc76  jz      short loc_18000BC81
0x18000bc78  or      ecx, 40002h
0x18000bc7e  mov     [rbp+3Fh+var_B0], ecx
0x18000bc81  test    cl, 1
0x18000bc84  jz      short loc_18000BC94
0x18000bc86  bts     ecx, 7
0x18000bc8a  jmp     short loc_18000BC91
0x18000bc8c  xor     esi, esi
0x18000bc8e  or      ecx, 0FFFFFFFFh
0x18000bc91  mov     [rbp+3Fh+var_B0], ecx
0x18000bc94  mov     rbx, [rbp+3Fh+var_80]
0x18000bc98  test    rbx, rbx
0x18000bc9b  jz      short loc_18000BD01
0x18000bc9d  test    rdi, rdi
0x18000bca0  jz      short loc_18000BD01
0x18000bca2  mov     rax, [rdi+218h]
0x18000bca9  mov     [rbp+3Fh+pControl], si
0x18000bcad  mov     [rbp+3Fh+dwRevision], esi
0x18000bcb0  test    rax, rax
0x18000bcb3  jnz     short loc_18000BCB9
0x18000bcb5  mov     [rbx], esi
0x18000bcb7  jmp     short loc_18000BD01
0x18000bcb9  lea     r8, [rbp+3Fh+dwRevision]; lpdwRevision
0x18000bcbd  mov     rcx, rax; pSecurityDescriptor
0x18000bcc0  lea     rdx, [rbp+3Fh+pControl]; pControl
0x18000bcc4  call    cs:__imp_GetSecurityDescriptorControl
0x18000bcca  test    eax, eax
0x18000bccc  jnz     short loc_18000BCF2
0x18000bcce  call    cs:__imp_GetLastError
0x18000bcd4  mov     ebx, eax
0x18000bcd6  test    eax, eax
0x18000bcd8  jz      short loc_18000BCE7
0x18000bcda  jle     short loc_18000BCEC
0x18000bcdc  movzx   ebx, ax
0x18000bcdf  or      ebx, 80070000h
0x18000bce5  jmp     short loc_18000BCEC
0x18000bce7  mov     ebx, 80004005h
0x18000bcec  test    ebx, ebx
0x18000bcee  js      short loc_18000BD09
0x18000bcf0  jmp     short loc_18000BCFE
0x18000bcf2  movzx   eax, [rbp+3Fh+pControl]
0x18000bcf6  shr     eax, 4
0x18000bcf9  and     eax, 1
0x18000bcfc  mov     [rbx], eax
0x18000bcfe  mov     ecx, [rbp+3Fh+var_B0]
0x18000bd01  mov     rax, [rbp+3Fh+var_78]
0x18000bd05  mov     ebx, esi
0x18000bd07  mov     [rax], ecx
0x18000bd09  lea     r14, a08x; "*%08x\n"
0x18000bd10  test    rdi, rdi
0x18000bd13  jz      short loc_18000BD28
0x18000bd15  mov     rcx, rdi; this
0x18000bd18  call    ?Release@CAdminAcl@@QEAAKXZ; CAdminAcl::Release(void)
0x18000bd1d  jmp     short loc_18000BD28
0x18000bd1f  xor     esi, esi
0x18000bd21  lea     r14, a08x; "*%08x\n"
0x18000bd28  mov     rcx, [rbp+3Fh+ClientToken]; hObject
0x18000bd2c  test    rcx, rcx
0x18000bd2f  jz      short loc_18000BD3B
0x18000bd31  call    cs:__imp_CloseHandle
0x18000bd37  mov     [rbp+3Fh+ClientToken], rsi
0x18000bd3b  test    ebx, ebx
0x18000bd3d  jns     short loc_18000BD74
0x18000bd3f  test    byte ptr cs:g_dwDebugFlags, 8
0x18000bd46  jz      short loc_18000BDAA
0x18000bd48  mov     rcx, cs:g_pDebug
0x18000bd4f  lea     r9, word_1800127E6
0x18000bd56  mov     dword ptr [rsp+0F0h+PrivilegeSetLength], ebx
0x18000bd5a  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x18000bd61  mov     r8d, 91Dh
0x18000bd67  mov     [rsp+0F0h+PrivilegeSet], r14
0x18000bd6c  call    cs:__imp_PuDbgPrint
0x18000bd72  jmp     short loc_18000BDAA
0x18000bd74  test    byte ptr cs:g_dwDebugFlags, 1
0x18000bd7b  jz      short loc_18000BDAA
0x18000bd7d  mov     rcx, cs:g_pDebug
0x18000bd84  lea     rax, asc_1800127E4; "\n"
0x18000bd8b  lea     r9, word_1800127E6
0x18000bd92  mov     [rsp+0F0h+PrivilegeSet], rax
0x18000bd97  mov     r8d, 91Dh
0x18000bd9d  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x18000bda4  call    cs:__imp_PuDbgPrint
0x18000bdaa  mov     eax, ebx
0x18000bdac  mov     rcx, [rbp+3Fh+var_38]
0x18000bdb0  xor     rcx, rsp; StackCookie
0x18000bdb3  call    __security_check_cookie
0x18000bdb8  mov     rbx, [rsp+0F0h+arg_8]
0x18000bdc0  add     rsp, 0C0h
0x18000bdc7  pop     r15
0x18000bdc9  pop     r14
0x18000bdcb  pop     r13
0x18000bdcd  pop     r12
0x18000bdcf  pop     rdi
0x18000bdd0  pop     rsi
0x18000bdd1  pop     rbp
0x18000bdd2  retn
```
