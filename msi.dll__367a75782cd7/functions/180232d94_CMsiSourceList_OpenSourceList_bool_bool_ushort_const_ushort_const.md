# CMsiSourceList::OpenSourceList(bool,bool,ushort const *,ushort const *)

- ea: `0x180232d94`
- end: `0x18023368f`
- name: `?OpenSourceList@CMsiSourceList@@QEAAI_N0PEBG1@Z`
- size: `2299`
- prototype: `unsigned int(CMsiSourceList *__hidden this, bool, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801586bc`
- `0x1801590c8`
- `0x18015c82c`
- `0x1801b3250`
- `0x1801b3380`
- `0x1801b3480`

## callees

- `0x18000a150`
- `0x180025688`
- `0x180025904`
- `0x180025a18`
- `0x18004b560`
- `0x18004ceb0`
- `0x180064a78`
- `0x180068680`
- `0x180074bd0`
- `0x180076e28`
- `0x180092ea0`
- `0x1800a9df0`
- `0x1800b7800`
- `0x180192bd4`
- `0x180232d24`
- `0x180232d94`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x180232f39`
- `ADVAPI32!LookupAccountNameW` at `0x180232ff3`
- `ADVAPI32!LookupAccountNameW` at `0x180232f39`
- `ADVAPI32!LookupAccountNameW` at `0x180232ff3`
- `ADVAPI32!EqualSid` at `0x18023312d`
- `ADVAPI32!EqualSid` at `0x18023312d`
- `ADVAPI32!GetUserNameW` at `0x18023301c`
- `ADVAPI32!GetUserNameW` at `0x18023303f`
- `ADVAPI32!GetUserNameW` at `0x18023301c`
- `ADVAPI32!GetUserNameW` at `0x18023303f`
- `KERNEL32!CloseHandle` at `0x180232f00`
- `KERNEL32!CloseHandle` at `0x180232f00`
- `KERNEL32!GlobalAlloc` at `0x180232f68`
- `KERNEL32!GlobalAlloc` at `0x180232f68`
- `KERNEL32!GlobalFree` at `0x180232fbb`
- `KERNEL32!GlobalFree` at `0x18023308c`
- `KERNEL32!GlobalFree` at `0x180233103`
- `KERNEL32!GlobalFree` at `0x180233207`
- `KERNEL32!GlobalFree` at `0x1802332c9`
- `KERNEL32!GlobalFree` at `0x180232fbb`
- `KERNEL32!GlobalFree` at `0x18023308c`
- `KERNEL32!GlobalFree` at `0x180233103`
- `KERNEL32!GlobalFree` at `0x180233207`
- `KERNEL32!GlobalFree` at `0x1802332c9`
- `KERNEL32!lstrcmpiW` at `0x180233050`
- `KERNEL32!lstrcmpiW` at `0x180233050`

## string_xrefs

- `0x1802330bc`: `Could not retrieve UserName of calling thread.`
- `0x18023328b`: `Could not retrieve UserName of calling thread.`
- `0x180232e68`: `Checking registry for verification purposes only.`
- `0x1802331b7`: `Attempting to modify per-user managed install for user %s.`
- `0x18023323a`: `Non-Admin attempting to open another users per-user product. Access denied.`
- `0x18023333b`: `Opening per-%s SourceList.`
- `0x180233449`: `Managed install not found. Attempting to open per-user non managed SourceList.`
- `0x1802333f1`: `Couldn't open SourceList key, but could open product key. Corrupt SourceList?`
- `0x1802334de`: `Couldn't open SourceList key, but could open product key. Corrupt SourceList?`

## pseudocode

```c
__int64 __fastcall CMsiSourceList::OpenSourceList(
        CMsiSourceList *this,
        char a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpAccountName)
{
  int v5; // r12d
  bool v6; // si
  bool *v10; // rdx
  unsigned int UserSID; // ebx
  __int64 v12; // r8
  signed int v13; // r14d
  _BYTE *v14; // rax
  _BYTE *v15; // r8
  _BYTE *v16; // rbx
  _BYTE *v17; // rax
  int v18; // edx
  __int64 v19; // r8
  unsigned int v20; // ebx
  bool v21; // di
  const char *v23; // rax
  unsigned __int16 *v24; // r8
  int v25; // ebx
  int v26; // ebx
  __int64 v27; // rax
  CMsiSourceList *v28; // rcx
  const unsigned __int16 *v29; // rcx
  const unsigned __int16 *v30; // rax
  unsigned int v31; // [rsp+50h] [rbp-B0h]
  void *v32; // [rsp+58h] [rbp-A8h]
  char v33; // [rsp+60h] [rbp-A0h] BYREF
  bool v34; // [rsp+61h] [rbp-9Fh] BYREF
  bool v35; // [rsp+62h] [rbp-9Eh] BYREF
  DWORD cchReferencedDomainName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbSid; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbBuffer; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v41[8]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+90h] [rbp-70h]
  char v44; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v45; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+A8h] [rbp-58h]
  int v47; // [rsp+ACh] [rbp-54h]
  char v48; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR lpBuffer; // [rsp+B8h] [rbp-48h] BYREF
  int v50; // [rsp+C0h] [rbp-40h]
  WCHAR Buffer; // [rsp+C8h] [rbp-38h] BYREF
  PSID Sid; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+D8h] [rbp-28h]
  _BYTE v54[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v55[80]; // [rsp+130h] [rbp+30h] BYREF
  char pSid2[80]; // [rsp+180h] [rbp+80h] BYREF

  v5 = a3;
  v45 = (unsigned __int16 *)&v48;
  v6 = 1;
  v46 = 1;
  hObject = 0;
  if ( !a4
    || (int)StringCchLengthW(a4, 0x27u, (unsigned __int64 *)&hObject) < 0
    || hObject != (HANDLE)38
    || !(unsigned int)PackGUID(a4, v55, 33)
    || (_BYTE)v5 && lpAccountName && *lpAccountName )
  {
    CAPITempBuffer<unsigned short,1>::Destroy(&v45);
    return 87;
  }
  *((_BYTE *)this + 97) = a2;
  if ( a2 && g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      "Checking registry for verification purposes only.",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      v31,
      v32);
  if ( lpAccountName && *lpAccountName )
  {
    cchReferencedDomainName = 0;
    cbSid = 72;
    v53 = 72;
    Sid = v54;
    ReferencedDomainName = (LPWSTR)&v44;
    peUse = 0;
    v43 = 1;
    hObject = 0;
    if ( (unsigned int)OpenUserToken(&hObject, v10) )
      goto LABEL_57;
    UserSID = GetUserSID(hObject, pSid2);
    CloseHandle(hObject);
    if ( UserSID )
      goto LABEL_57;
    LookupAccountNameW(0, lpAccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    LOBYTE(v12) = 1;
    if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&ReferencedDomainName, cchReferencedDomainName, v12) )
    {
      v13 = cbSid;
      if ( (int)cbSid <= 72 )
      {
        v16 = v54;
        v15 = v54;
        goto LABEL_20;
      }
      v14 = GlobalAlloc(0x40u, (int)cbSid);
      v15 = v14;
      if ( v14 )
      {
        v16 = v14;
LABEL_20:
        v17 = Sid;
        if ( Sid != v16 )
        {
          v18 = v53;
          if ( v13 < v53 )
            v18 = v13;
          for ( ; v18; v17 = Sid )
          {
            --v18;
            v15[v18] = v17[v18];
          }
        }
        if ( v17 != v54 )
          GlobalFree(v17);
        Sid = v16;
        v53 = v13;
        if ( !LookupAccountNameW(0, lpAccountName, v16, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          v50 = 1;
          lpBuffer = &Buffer;
          pcbBuffer = 1;
          GetUserNameW(&Buffer, &pcbBuffer);
          LOBYTE(v19) = 1;
          if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpBuffer, pcbBuffer, v19)
            || !GetUserNameW(lpBuffer, &pcbBuffer) )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                "Could not retrieve UserName of calling thread.",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                v31,
                v32);
            CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
            CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
            if ( v53 > 72 )
              GlobalFree(Sid);
            v20 = 1627;
            goto LABEL_39;
          }
          if ( lstrcmpiW(lpBuffer, lpAccountName) )
          {
            v20 = IsAdmin() ? 2202 : 5;
            CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
            CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
            if ( v53 > 72 )
              GlobalFree(Sid);
LABEL_39:
            v53 = 72;
            Sid = v54;
LABEL_88:
            CAPITempBuffer<unsigned short,1>::Destroy(&v45);
            return v20;
          }
          v21 = 1;
          CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
          goto LABEL_42;
        }
        if ( EqualSid(Sid, pSid2) )
        {
          v21 = 1;
LABEL_42:
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              "Product to be modified belongs to current user.",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              v31,
              v32);
          goto LABEL_47;
        }
        v47 = 1;
        if ( !(unsigned int)GetStringSid(Sid, &v45) )
        {
          v21 = 0;
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Attempting to modify per-user managed install for user %s.",
              v45,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
LABEL_47:
          CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
          if ( v53 > 72 )
            GlobalFree(Sid);
          if ( !(_BYTE)v5 && !v21 && !IsAdmin() )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                "Non-Admin attempting to open another users per-user product. Access denied.",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                v31,
                v32);
            v20 = 5;
            goto LABEL_88;
          }
          goto LABEL_61;
        }
LABEL_57:
        CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
        if ( v53 > 72 )
          GlobalFree(Sid);
        v53 = 72;
        Sid = v54;
        CAPITempBuffer<unsigned short,1>::Destroy(&v45);
        return 1627;
      }
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Could not retrieve UserName of calling thread.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        v31,
        v32);
    goto LABEL_57;
  }
  v21 = (_BYTE)v5 == 0;
LABEL_61:
  v33 = 0;
  v34 = 0;
  if ( g_dmDiagnosticMode )
  {
    v23 = "machine managed";
    if ( !(_BYTE)v5 )
      v23 = "user managed";
    DebugString(9, 0, 0, "Opening per-%s SourceList.", v23, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v31, v32);
  }
  CElevate::CElevate((CElevate *)v41, 1);
  if ( (_BYTE)v5 || v21 )
    v24 = 0;
  else
    v24 = v45;
  v25 = OpenSpecificUsersSourceListKeyPacked(
          2 * v5,
          0,
          (__int64)v24,
          (unsigned __int64)v55,
          (CMsiSourceList *)((char *)this + 8),
          *((_BYTE *)this + 97) == 0,
          &v33,
          &v34,
          0,
          0);
  CElevate::~CElevate((CElevate *)v41);
  if ( v25 )
  {
    if ( v33 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          "Couldn't open SourceList key, but could open product key. Corrupt SourceList?",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          v31,
          v32);
LABEL_73:
      v20 = 1610;
      goto LABEL_88;
    }
    if ( !v21 )
      goto LABEL_83;
    v35 = 0;
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Managed install not found. Attempting to open per-user non managed SourceList.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        v31,
        v32);
    CElevate::CElevate((CElevate *)v41, 1);
    v26 = OpenSpecificUsersSourceListKeyPacked(
            1u,
            0,
            0,
            (unsigned __int64)v55,
            (CMsiSourceList *)((char *)this + 8),
            *((_BYTE *)this + 97) == 0,
            &v33,
            &v35,
            0,
            0);
    if ( v26 && v33 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          "Couldn't open SourceList key, but could open product key. Corrupt SourceList?",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          v31,
          v32);
      CElevate::~CElevate((CElevate *)v41);
      goto LABEL_73;
    }
    CElevate::~CElevate((CElevate *)v41);
    if ( v26 )
    {
LABEL_83:
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SourceList for product %s not found.",
          a4,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v20 = 1605;
      goto LABEL_88;
    }
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 13) + 192LL))(
          *((_QWORD *)this + 13),
          *((unsigned int *)this + 2),
          0xFFFFFFFFLL);
  CComPointer<IMsiDatabase>::operator=((char *)this + 88, v27);
  if ( !*((_QWORD *)this + 11) )
  {
    v20 = 1627;
    goto LABEL_88;
  }
  if ( !IsAdmin() )
    v6 = CMsiSourceList::NonAdminAllowedToModifyByPolicy(v28, v34);
  *((_BYTE *)this + 96) = v6;
  if ( g_dmDiagnosticMode )
  {
    v29 = &Default;
    if ( !v6 )
      v29 = L"not ";
    v30 = L"would";
    if ( !*((_BYTE *)this + 97) )
      v30 = L"will";
    DebugString(
      9,
      0,
      0,
      L"User %s %sbe allowed to modify contents of SourceList.",
      v30,
      v29,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  CAPITempBuffer<unsigned short,1>::Destroy(&v45);
  return 0;
}

```

## disassembly

```asm
0x180232d94  mov     [rsp-8+arg_8], rbx
0x180232d99  push    rbp
0x180232d9a  push    rsi
0x180232d9b  push    rdi
0x180232d9c  push    r12
0x180232d9e  push    r13
0x180232da0  push    r14
0x180232da2  push    r15
0x180232da4  lea     rbp, [rsp-0E0h]
0x180232dac  sub     rsp, 1E0h
0x180232db3  mov     rax, cs:__security_cookie
0x180232dba  xor     rax, rsp
0x180232dbd  mov     [rbp+110h+var_40], rax
0x180232dc4  mov     rdi, [rbp+110h+lpAccountName]
0x180232dcb  lea     rax, [rbp+110h+var_160]
0x180232dcf  xor     r14d, r14d
0x180232dd2  movzx   r12d, r8b
0x180232dd6  mov     [rbp+110h+var_170], rax
0x180232dda  mov     esi, 1
0x180232ddf  mov     [rbp+110h+var_168], esi
0x180232de2  mov     r13, r9
0x180232de5  mov     [rsp+210h+hObject], r14
0x180232dea  mov     bl, dl
0x180232dec  mov     r15, rcx
0x180232def  test    r9, r9
0x180232df2  jz      loc_180233657
0x180232df8  lea     r8, [rsp+210h+hObject]; unsigned __int64 *
0x180232dfd  mov     rcx, r9; unsigned __int16 *
0x180232e00  lea     edx, [rsi+26h]; unsigned __int64
0x180232e03  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180232e08  test    eax, eax
0x180232e0a  js      loc_180233657
0x180232e10  cmp     [rsp+210h+hObject], 26h ; '&'
0x180232e16  jnz     loc_180233657
0x180232e1c  mov     r9d, esi
0x180232e1f  lea     r8d, [rsi+20h]
0x180232e23  lea     rdx, [rbp+110h+var_E0]
0x180232e27  mov     rcx, r13
0x180232e2a  call    ?PackGUID@@YA?AW4Bool@@PEBGPEAGKW4ipgEnum@@@Z; PackGUID(ushort const *,ushort *,ulong,ipgEnum)
0x180232e2f  test    eax, eax
0x180232e31  jz      loc_180233657
0x180232e37  test    r12b, r12b
0x180232e3a  jz      short loc_180232E4B
0x180232e3c  test    rdi, rdi
0x180232e3f  jz      short loc_180232E4B
0x180232e41  cmp     [rdi], r14w
0x180232e45  jnz     loc_180233657
0x180232e4b  mov     [r15+61h], bl
0x180232e4f  lea     rax, aNull_0; "(NULL)"
0x180232e56  test    bl, bl
0x180232e58  jz      short loc_180232E95
0x180232e5a  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180232e61  jz      short loc_180232E95
0x180232e63  mov     [rsp+210h+var_1C8], rax; char *
0x180232e68  lea     r9, aCheckingRegist; "Checking registry for verification purp"...
0x180232e6f  mov     [rsp+210h+var_1D0], rax; char *
0x180232e74  xor     edx, edx; unsigned __int16
0x180232e76  mov     [rsp+210h+var_1D8], rax; char *
0x180232e7b  xor     r8d, r8d; int
0x180232e7e  mov     [rsp+210h+peUse], rax; char *
0x180232e83  mov     [rsp+210h+cchReferencedDomainName], rax; char *
0x180232e88  lea     ecx, [rdx+9]; int
0x180232e8b  mov     [rsp+210h+ReferencedDomainName], rax; char *
0x180232e90  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180232e95  test    rdi, rdi
0x180232e98  jz      loc_1802332F1
0x180232e9e  cmp     [rdi], r14w
0x180232ea2  jz      loc_1802332F1
0x180232ea8  mov     eax, 48h ; 'H'
0x180232ead  mov     [rsp+210h+var_1AC], r14d
0x180232eb2  mov     [rsp+210h+cbSid], eax
0x180232eb6  lea     rcx, [rsp+210h+hObject]; TokenHandle
0x180232ebb  mov     [rbp+110h+var_138], eax
0x180232ebe  lea     rax, [rbp+110h+var_130]
0x180232ec2  mov     [rbp+110h+Sid], rax
0x180232ec6  lea     rax, [rbp+110h+var_178]
0x180232eca  mov     [rbp+110h+var_188], rax
0x180232ece  mov     [rsp+210h+var_198], r14d
0x180232ed3  mov     [rbp+110h+var_180], esi
0x180232ed6  mov     [rsp+210h+hObject], r14
0x180232edb  call    ?OpenUserToken@@YAKAEAPEAXPEA_N@Z; OpenUserToken(void * &,bool *)
0x180232ee0  test    eax, eax
0x180232ee2  jnz     loc_1802332B6
0x180232ee8  mov     rcx, [rsp+210h+hObject]; void *
0x180232eed  lea     rdx, [rbp+110h+pSid2]; char *
0x180232ef4  call    ?GetUserSID@@YAKPEAXQEAD@Z; GetUserSID(void *,char * const)
0x180232ef9  mov     rcx, [rsp+210h+hObject]; hObject
0x180232efe  mov     ebx, eax
0x180232f00  call    cs:__imp_CloseHandle
0x180232f06  test    ebx, ebx
0x180232f08  jnz     loc_1802332B6
0x180232f0e  mov     r8, [rbp+110h+Sid]; Sid
0x180232f12  lea     rax, [rsp+210h+var_198]
0x180232f17  mov     [rsp+210h+peUse], rax; peUse
0x180232f1c  lea     r9, [rsp+210h+cbSid]; cbSid
0x180232f21  lea     rax, [rsp+210h+var_1AC]
0x180232f26  mov     rdx, rdi; lpAccountName
0x180232f29  mov     [rsp+210h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180232f2e  xor     ecx, ecx; lpSystemName
0x180232f30  mov     rax, [rbp+110h+var_188]
0x180232f34  mov     [rsp+210h+ReferencedDomainName], rax; ReferencedDomainName
0x180232f39  call    cs:__imp_LookupAccountNameW
0x180232f3f  mov     edx, [rsp+210h+var_1AC]
0x180232f43  lea     rcx, [rbp+110h+var_188]
0x180232f47  mov     r8b, sil
0x180232f4a  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180232f4f  test    al, al
0x180232f51  jz      loc_180233274
0x180232f57  movsxd  r14, [rsp+210h+cbSid]
0x180232f5c  cmp     r14d, 48h ; 'H'
0x180232f60  jle     short loc_180232F7F
0x180232f62  mov     rdx, r14; dwBytes
0x180232f65  lea     ecx, [rbx+40h]; uFlags
0x180232f68  call    cs:__imp_GlobalAlloc
0x180232f6e  mov     r8, rax
0x180232f71  test    rax, rax
0x180232f74  jz      loc_180233271
0x180232f7a  mov     rbx, rax
0x180232f7d  jmp     short loc_180232F86
0x180232f7f  lea     rbx, [rbp+110h+var_130]
0x180232f83  mov     r8, rbx
0x180232f86  mov     rax, [rbp+110h+Sid]
0x180232f8a  cmp     rax, rbx
0x180232f8d  jz      short loc_180232FAF
0x180232f8f  mov     edx, [rbp+110h+var_138]
0x180232f92  cmp     r14d, edx
0x180232f95  cmovl   edx, r14d
0x180232f99  test    edx, edx
0x180232f9b  jz      short loc_180232FAF
0x180232f9d  sub     edx, esi
0x180232f9f  movsxd  rcx, edx
0x180232fa2  mov     al, [rcx+rax]
0x180232fa5  mov     [rcx+r8], al
0x180232fa9  mov     rax, [rbp+110h+Sid]
0x180232fad  jnz     short loc_180232F9D
0x180232faf  lea     rcx, [rbp+110h+var_130]
0x180232fb3  cmp     rax, rcx
0x180232fb6  jz      short loc_180232FC1
0x180232fb8  mov     rcx, rax; hMem
0x180232fbb  call    cs:__imp_GlobalFree
0x180232fc1  mov     rax, [rbp+110h+var_188]
0x180232fc5  lea     rcx, [rsp+210h+var_198]
0x180232fca  mov     [rsp+210h+peUse], rcx; peUse
0x180232fcf  lea     r9, [rsp+210h+cbSid]; cbSid
0x180232fd4  lea     rcx, [rsp+210h+var_1AC]
0x180232fd9  mov     [rbp+110h+Sid], rbx
0x180232fdd  mov     [rsp+210h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180232fe2  mov     r8, rbx; Sid
0x180232fe5  xor     ecx, ecx; lpSystemName
0x180232fe7  mov     [rbp+110h+var_138], r14d
0x180232feb  mov     rdx, rdi; lpAccountName
0x180232fee  mov     [rsp+210h+ReferencedDomainName], rax; ReferencedDomainName
0x180232ff3  call    cs:__imp_LookupAccountNameW
0x180232ff9  xor     r14d, r14d
0x180232ffc  test    eax, eax
0x180232ffe  jnz     loc_180233122
0x180233004  lea     rax, [rbp+110h+Buffer]
0x180233008  mov     [rbp+110h+var_150], esi
0x18023300b  lea     rdx, [rsp+210h+pcbBuffer]; pcbBuffer
0x180233010  mov     [rbp+110h+lpBuffer], rax
0x180233014  lea     rcx, [rbp+110h+Buffer]; lpBuffer
0x180233018  mov     [rsp+210h+pcbBuffer], esi
0x18023301c  call    cs:__imp_GetUserNameW
0x180233022  mov     edx, [rsp+210h+pcbBuffer]
0x180233026  lea     rcx, [rbp+110h+lpBuffer]
0x18023302a  mov     r8b, sil
0x18023302d  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180233032  test    al, al
0x180233034  jz      short loc_1802330A5
0x180233036  mov     rcx, [rbp+110h+lpBuffer]; lpBuffer
0x18023303a  lea     rdx, [rsp+210h+pcbBuffer]; pcbBuffer
0x18023303f  call    cs:__imp_GetUserNameW
0x180233045  test    eax, eax
0x180233047  jz      short loc_1802330A5
0x180233049  mov     rcx, [rbp+110h+lpBuffer]; lpString1
0x18023304d  mov     rdx, rdi; lpString2
0x180233050  call    cs:__imp_lstrcmpiW
0x180233056  test    eax, eax
0x180233058  jz      short loc_180233094
0x18023305a  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x18023305f  neg     al
0x180233061  lea     rcx, [rbp+110h+lpBuffer]
0x180233065  sbb     ebx, ebx
0x180233067  and     ebx, 895h
0x18023306d  add     ebx, 5
0x180233070  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x180233075  lea     rcx, [rbp+110h+var_188]
0x180233079  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023307e  cmp     [rbp+110h+var_138], 48h ; 'H'
0x180233082  jle     loc_18023310E
0x180233088  mov     rcx, [rbp+110h+Sid]; hMem
0x18023308c  call    cs:__imp_GlobalFree
0x180233092  jmp     short loc_18023310E
0x180233094  lea     rcx, [rbp+110h+lpBuffer]
0x180233098  mov     dil, sil
0x18023309b  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1802330a0  jmp     loc_18023313A
0x1802330a5  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1802330ac  jz      short loc_1802330E7
0x1802330ae  lea     r8, aNull_0; "(NULL)"
0x1802330b5  xor     edx, edx; unsigned __int16
0x1802330b7  mov     [rsp+210h+var_1C8], r8; char *
0x1802330bc  lea     r9, aCouldNotRetrie; "Could not retrieve UserName of calling "...
0x1802330c3  mov     [rsp+210h+var_1D0], r8; char *
0x1802330c8  mov     [rsp+210h+var_1D8], r8; char *
0x1802330cd  mov     [rsp+210h+peUse], r8; char *
0x1802330d2  lea     ecx, [rdx+9]; int
0x1802330d5  mov     [rsp+210h+cchReferencedDomainName], r8; char *
0x1802330da  mov     [rsp+210h+ReferencedDomainName], r8; char *
0x1802330df  xor     r8d, r8d; int
0x1802330e2  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1802330e7  lea     rcx, [rbp+110h+lpBuffer]
0x1802330eb  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1802330f0  lea     rcx, [rbp+110h+var_188]
0x1802330f4  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1802330f9  cmp     [rbp+110h+var_138], 48h ; 'H'
0x1802330fd  jle     short loc_180233109
0x1802330ff  mov     rcx, [rbp+110h+Sid]; hMem
0x180233103  call    cs:__imp_GlobalFree
0x180233109  mov     ebx, 65Bh
0x18023310e  lea     rax, [rbp+110h+var_130]
0x180233112  mov     [rbp+110h+var_138], 48h ; 'H'
0x180233119  mov     [rbp+110h+Sid], rax
0x18023311d  jmp     loc_1802335AA
0x180233122  mov     rcx, [rbp+110h+Sid]; pSid1
0x180233126  lea     rdx, [rbp+110h+pSid2]; pSid2
0x18023312d  call    cs:__imp_EqualSid
0x180233133  test    eax, eax
0x180233135  jz      short loc_180233182
0x180233137  mov     dil, sil
0x18023313a  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180233141  lea     rbx, aNull_0; "(NULL)"
0x180233148  jz      loc_1802331F4
0x18023314e  mov     [rsp+210h+var_1C8], rbx; char *
0x180233153  lea     r9, aProductToBeMod; "Product to be modified belongs to curre"...
0x18023315a  mov     [rsp+210h+var_1D0], rbx; char *
0x18023315f  xor     edx, edx; unsigned __int16
0x180233161  mov     [rsp+210h+var_1D8], rbx; char *
0x180233166  xor     r8d, r8d; int
0x180233169  mov     [rsp+210h+peUse], rbx; char *
0x18023316e  mov     [rsp+210h+cchReferencedDomainName], rbx; char *
0x180233173  lea     ecx, [rdx+9]; int
0x180233176  mov     [rsp+210h+ReferencedDomainName], rbx; char *
0x18023317b  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180233180  jmp     short loc_1802331F4
0x180233182  mov     rcx, [rbp+110h+Sid]
0x180233186  lea     rdx, [rbp+110h+var_170]
0x18023318a  mov     [rbp+110h+var_164], esi
0x18023318d  call    ?GetStringSid@@YAKQEAXAEAV?$CAPITempBufferRef@G@@@Z; GetStringSid(void * const,CAPITempBufferRef<ushort> &)
0x180233192  test    eax, eax
0x180233194  jnz     loc_1802332B6
0x18023319a  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1802331a1  mov     dil, r14b
0x1802331a4  jz      short loc_1802331ED
0x1802331a6  mov     [rsp+210h+var_1B8], r14; void *
0x1802331ab  lea     rax, aNull; "(NULL)"
0x1802331b2  mov     [rsp+210h+var_1C0], r14d; unsigned int
0x1802331b7  lea     r9, aAttemptingToMo; "Attempting to modify per-user managed i"...
0x1802331be  mov     [rsp+210h+var_1C8], rax; unsigned __int16 *
0x1802331c3  xor     edx, edx; unsigned __int16
0x1802331c5  mov     [rsp+210h+var_1D0], rax; unsigned __int16 *
0x1802331ca  xor     r8d, r8d; int
0x1802331cd  mov     [rsp+210h+var_1D8], rax; unsigned __int16 *
0x1802331d2  mov     [rsp+210h+peUse], rax; unsigned __int16 *
0x1802331d7  mov     [rsp+210h+cchReferencedDomainName], rax; unsigned __int16 *
0x1802331dc  lea     ecx, [rdx+9]; int
0x1802331df  mov     rax, [rbp+110h+var_170]
0x1802331e3  mov     [rsp+210h+ReferencedDomainName], rax; unsigned __int16 *
0x1802331e8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802331ed  lea     rbx, aNull_0; "(NULL)"
0x1802331f4  lea     rcx, [rbp+110h+var_188]
0x1802331f8  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1802331fd  cmp     [rbp+110h+var_138], 48h ; 'H'
0x180233201  jle     short loc_18023320D
0x180233203  mov     rcx, [rbp+110h+Sid]; hMem
0x180233207  call    cs:__imp_GlobalFree
0x18023320d  test    r12b, r12b
0x180233210  jnz     loc_1802332F8
0x180233216  test    dil, dil
0x180233219  jnz     loc_1802332F8
0x18023321f  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x180233224  test    al, al
0x180233226  jnz     loc_1802332F8
0x18023322c  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180233233  jz      short loc_180233267
0x180233235  mov     [rsp+210h+var_1C8], rbx; char *
0x18023323a  lea     r9, aNonAdminAttemp; "Non-Admin attempting to open another us"...
0x180233241  mov     [rsp+210h+var_1D0], rbx; char *
0x180233246  xor     edx, edx; unsigned __int16
0x180233248  mov     [rsp+210h+var_1D8], rbx; char *
0x18023324d  xor     r8d, r8d; int
0x180233250  mov     [rsp+210h+peUse], rbx; char *
0x180233255  mov     [rsp+210h+cchReferencedDomainName], rbx; char *
0x18023325a  lea     ecx, [rdx+9]; int
0x18023325d  mov     [rsp+210h+ReferencedDomainName], rbx; char *
0x180233262  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180233267  mov     ebx, 5
0x18023326c  jmp     loc_1802335AA
0x180233271  xor     r14d, r14d
0x180233274  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
  ... truncated ...
```
