# CMsiSourceList::OpenSourceList(bool,bool,ushort const *,ushort const *)

- ea: `0x18023ce34`
- end: `0x18023d718`
- name: `?OpenSourceList@CMsiSourceList@@QEAAI_N0PEBG1@Z`
- size: `2276`
- prototype: `unsigned int(CMsiSourceList *__hidden this, bool, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18015e268`
- `0x18015ec8c`
- `0x1801624d8`
- `0x1801bb020`
- `0x1801bb150`
- `0x1801bb250`

## callees

- `0x18000c4bc`
- `0x180014288`
- `0x180014528`
- `0x180014e38`
- `0x180027634`
- `0x18002e870`
- `0x1800491f0`
- `0x18004a014`
- `0x180067fec`
- `0x18006dc80`
- `0x180080ca0`
- `0x1800b9c08`
- `0x1800bfc6c`
- `0x18019971c`
- `0x18023cdc4`
- `0x18023ce34`
- `0x18023ddf4`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x18023cfdf`
- `ADVAPI32!LookupAccountNameW` at `0x18023d043`
- `ADVAPI32!LookupAccountNameW` at `0x18023cfdf`
- `ADVAPI32!LookupAccountNameW` at `0x18023d043`
- `ADVAPI32!EqualSid` at `0x18023d1a5`
- `ADVAPI32!EqualSid` at `0x18023d1a5`
- `ADVAPI32!GetUserNameW` at `0x18023d06f`
- `ADVAPI32!GetUserNameW` at `0x18023d09c`
- `ADVAPI32!GetUserNameW` at `0x18023d06f`
- `ADVAPI32!GetUserNameW` at `0x18023d09c`
- `KERNEL32!CloseHandle` at `0x18023cfa0`
- `KERNEL32!CloseHandle` at `0x18023cfa0`
- `KERNEL32!GlobalFree` at `0x18023d0f5`
- `KERNEL32!GlobalFree` at `0x18023d175`
- `KERNEL32!GlobalFree` at `0x18023d285`
- `KERNEL32!GlobalFree` at `0x18023d34a`
- `KERNEL32!GlobalFree` at `0x18023d0f5`
- `KERNEL32!GlobalFree` at `0x18023d175`
- `KERNEL32!GlobalFree` at `0x18023d285`
- `KERNEL32!GlobalFree` at `0x18023d34a`
- `KERNEL32!lstrcmpiW` at `0x18023d0b3`
- `KERNEL32!lstrcmpiW` at `0x18023d0b3`

## string_xrefs

- `0x18023d12e`: `Could not retrieve UserName of calling thread.`
- `0x18023d30c`: `Could not retrieve UserName of calling thread.`
- `0x18023cf08`: `Checking registry for verification purposes only.`
- `0x18023d235`: `Attempting to modify per-user managed install for user %s.`
- `0x18023d2be`: `Non-Admin attempting to open another users per-user product. Access denied.`
- `0x18023d3c2`: `Opening per-%s SourceList.`
- `0x18023d4d0`: `Managed install not found. Attempting to open per-user non managed SourceList.`
- `0x18023d478`: `Couldn't open SourceList key, but could open product key. Corrupt SourceList?`
- `0x18023d565`: `Couldn't open SourceList key, but could open product key. Corrupt SourceList?`

## pseudocode

```c
__int64 __fastcall CMsiSourceList::OpenSourceList(
        CMsiSourceList *this,
        char a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpAccountName)
{
  int v5; // r15d
  bool v6; // si
  bool *v10; // rdx
  unsigned int UserSID; // ebx
  __int64 v12; // r8
  __int64 v13; // r8
  unsigned int v14; // ebx
  bool v15; // di
  const char *v17; // rax
  unsigned __int16 *v18; // r8
  int v19; // ebx
  int v20; // ebx
  __int64 v21; // rax
  CMsiSourceList *v22; // rcx
  const unsigned __int16 *v23; // rcx
  const unsigned __int16 *v24; // rax
  int v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+48h] [rbp-B8h]
  unsigned int v27; // [rsp+50h] [rbp-B0h]
  void *v28; // [rsp+58h] [rbp-A8h]
  char v29; // [rsp+60h] [rbp-A0h] BYREF
  bool v30; // [rsp+61h] [rbp-9Fh] BYREF
  _BYTE v31[2]; // [rsp+62h] [rbp-9Eh] BYREF
  DWORD cchReferencedDomainName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbSid; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbBuffer; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[8]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+88h] [rbp-78h] BYREF
  int v39; // [rsp+90h] [rbp-70h]
  char v40; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+ACh] [rbp-54h]
  char v44; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR lpBuffer; // [rsp+B8h] [rbp-48h] BYREF
  int v46; // [rsp+C0h] [rbp-40h]
  WCHAR Buffer; // [rsp+C8h] [rbp-38h] BYREF
  PSID Sid; // [rsp+D0h] [rbp-30h] BYREF
  int v49; // [rsp+D8h] [rbp-28h]
  _BYTE v50[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[80]; // [rsp+130h] [rbp+30h] BYREF
  char pSid2[80]; // [rsp+180h] [rbp+80h] BYREF

  v5 = a3;
  v41 = (unsigned __int16 *)&v44;
  v6 = 1;
  v42 = 1;
  hObject = 0;
  if ( !a4
    || (int)StringCchLengthW(a4, 0x27u, (unsigned __int64 *)&hObject) < 0
    || hObject != (HANDLE)38
    || !(unsigned int)PackGUID(a4, v51, 33, 1)
    || (_BYTE)v5 && lpAccountName && *lpAccountName )
  {
    CAPITempBuffer<unsigned short,1>::Destroy(&v41);
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
      v27,
      v28);
  if ( lpAccountName && *lpAccountName )
  {
    cchReferencedDomainName = 0;
    cbSid = 72;
    v49 = 72;
    Sid = v50;
    ReferencedDomainName = (LPWSTR)&v40;
    peUse = 0;
    v39 = 1;
    hObject = 0;
    if ( !(unsigned int)OpenUserToken(&hObject, v10) )
    {
      UserSID = GetUserSID(hObject, pSid2);
      CloseHandle(hObject);
      if ( !UserSID )
      {
        LookupAccountNameW(0, lpAccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse);
        LOBYTE(v12) = 1;
        if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                &ReferencedDomainName,
                                cchReferencedDomainName,
                                v12)
          && (unsigned __int8)CAPITempBuffer<char,72>::SetSize(&Sid, cbSid) )
        {
          if ( !LookupAccountNameW(
                  0,
                  lpAccountName,
                  Sid,
                  &cbSid,
                  ReferencedDomainName,
                  &cchReferencedDomainName,
                  &peUse) )
          {
            v46 = 1;
            lpBuffer = &Buffer;
            pcbBuffer = 1;
            GetUserNameW(&Buffer, &pcbBuffer);
            LOBYTE(v13) = 1;
            if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpBuffer, pcbBuffer, v13)
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
                  v27,
                  v28);
              CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
              CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
              if ( v49 > 72 )
                GlobalFree(Sid);
              v14 = 1627;
              goto LABEL_29;
            }
            if ( lstrcmpiW(lpBuffer, lpAccountName) )
            {
              v14 = IsAdmin() ? 2202 : 5;
              CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
              CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
              if ( v49 > 72 )
                GlobalFree(Sid);
LABEL_29:
              v49 = 72;
              Sid = v50;
LABEL_78:
              CAPITempBuffer<unsigned short,1>::Destroy(&v41);
              return v14;
            }
            v15 = 1;
            CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
            goto LABEL_32;
          }
          if ( EqualSid(Sid, pSid2) )
          {
            v15 = 1;
LABEL_32:
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
                v27,
                v28);
            goto LABEL_37;
          }
          v43 = 1;
          if ( !(unsigned int)GetStringSid(Sid, &v41) )
          {
            v15 = 0;
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"Attempting to modify per-user managed install for user %s.",
                v41,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
LABEL_37:
            CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
            if ( v49 > 72 )
              GlobalFree(Sid);
            if ( !(_BYTE)v5 && !v15 && !IsAdmin() )
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
                  v27,
                  v28);
              v14 = 5;
              goto LABEL_78;
            }
            goto LABEL_51;
          }
        }
        else if ( g_dmDiagnosticMode )
        {
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
            v27,
            v28);
        }
      }
    }
    CAPITempBuffer<unsigned short,1>::Destroy(&ReferencedDomainName);
    if ( v49 > 72 )
      GlobalFree(Sid);
    v49 = 72;
    Sid = v50;
    CAPITempBuffer<unsigned short,1>::Destroy(&v41);
    return 1627;
  }
  v15 = (_BYTE)v5 == 0;
LABEL_51:
  v29 = 0;
  v30 = 0;
  if ( g_dmDiagnosticMode )
  {
    v17 = "machine managed";
    if ( !(_BYTE)v5 )
      v17 = "user managed";
    DebugString(9, 0, 0, "Opening per-%s SourceList.", v17, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v27, v28);
  }
  CElevate::CElevate((CElevate *)v37, 1);
  if ( (_BYTE)v5 || v15 )
    v18 = 0;
  else
    v18 = v41;
  LOBYTE(v25) = 0;
  v19 = OpenSpecificUsersSourceListKeyPacked(
          (unsigned int)(2 * v5),
          0,
          v18,
          v51,
          (char *)this + 8,
          *((_BYTE *)this + 97) == 0,
          &v29,
          &v30,
          0,
          v25);
  CElevate::~CElevate((CElevate *)v37);
  if ( v19 )
  {
    if ( v29 )
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
          v27,
          v28);
LABEL_63:
      v14 = 1610;
      goto LABEL_78;
    }
    if ( !v15 )
      goto LABEL_73;
    v31[0] = 0;
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
        v27,
        v28);
    CElevate::CElevate((CElevate *)v37, 1);
    LOBYTE(v26) = 0;
    v20 = OpenSpecificUsersSourceListKeyPacked(
            1,
            0,
            0,
            v51,
            (char *)this + 8,
            *((_BYTE *)this + 97) == 0,
            &v29,
            v31,
            0,
            v26);
    if ( v20 && v29 )
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
          v27,
          v28);
      CElevate::~CElevate((CElevate *)v37);
      goto LABEL_63;
    }
    CElevate::~CElevate((CElevate *)v37);
    if ( v20 )
    {
LABEL_73:
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
      v14 = 1605;
      goto LABEL_78;
    }
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 13) + 192LL))(
          *((_QWORD *)this + 13),
          *((unsigned int *)this + 2),
          0xFFFFFFFFLL);
  CComPointer<IMsiDatabase>::operator=((char *)this + 88, v21);
  if ( !*((_QWORD *)this + 11) )
  {
    v14 = 1627;
    goto LABEL_78;
  }
  if ( !IsAdmin() )
    v6 = CMsiSourceList::NonAdminAllowedToModifyByPolicy(v22, v30);
  *((_BYTE *)this + 96) = v6;
  if ( g_dmDiagnosticMode )
  {
    v23 = &Default;
    if ( !v6 )
      v23 = L"not ";
    v24 = L"would";
    if ( !*((_BYTE *)this + 97) )
      v24 = L"will";
    DebugString(
      9,
      0,
      0,
      L"User %s %sbe allowed to modify contents of SourceList.",
      v24,
      v23,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  CAPITempBuffer<unsigned short,1>::Destroy(&v41);
  return 0;
}

```

## disassembly

```asm
0x18023ce34  mov     [rsp-8+arg_8], rbx
0x18023ce39  push    rbp
0x18023ce3a  push    rsi
0x18023ce3b  push    rdi
0x18023ce3c  push    r12
0x18023ce3e  push    r13
0x18023ce40  push    r14
0x18023ce42  push    r15
0x18023ce44  lea     rbp, [rsp-0E0h]
0x18023ce4c  sub     rsp, 1E0h
0x18023ce53  mov     rax, cs:__security_cookie
0x18023ce5a  xor     rax, rsp
0x18023ce5d  mov     [rbp+110h+var_40], rax
0x18023ce64  mov     rdi, [rbp+110h+lpAccountName]
0x18023ce6b  lea     rax, [rbp+110h+var_160]
0x18023ce6f  xor     r12d, r12d
0x18023ce72  movzx   r15d, r8b
0x18023ce76  mov     [rbp+110h+var_170], rax
0x18023ce7a  mov     esi, 1
0x18023ce7f  mov     [rbp+110h+var_168], esi
0x18023ce82  mov     r13, r9
0x18023ce85  mov     [rsp+210h+hObject], r12
0x18023ce8a  mov     bl, dl
0x18023ce8c  mov     r14, rcx
0x18023ce8f  test    r9, r9
0x18023ce92  jz      loc_18023D6DF
0x18023ce98  lea     r8, [rsp+210h+hObject]; unsigned __int64 *
0x18023ce9d  mov     rcx, r9; unsigned __int16 *
0x18023cea0  lea     edx, [rsi+26h]; unsigned __int64
0x18023cea3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18023cea8  test    eax, eax
0x18023ceaa  js      loc_18023D6DF
0x18023ceb0  cmp     [rsp+210h+hObject], 26h ; '&'
0x18023ceb6  jnz     loc_18023D6DF
0x18023cebc  mov     r9d, esi
0x18023cebf  lea     r8d, [rsi+20h]
0x18023cec3  lea     rdx, [rbp+110h+var_E0]
0x18023cec7  mov     rcx, r13
0x18023ceca  call    ?PackGUID@@YA?AW4Bool@@PEBGPEAGKW4ipgEnum@@@Z; PackGUID(ushort const *,ushort *,ulong,ipgEnum)
0x18023cecf  test    eax, eax
0x18023ced1  jz      loc_18023D6DF
0x18023ced7  test    r15b, r15b
0x18023ceda  jz      short loc_18023CEEB
0x18023cedc  test    rdi, rdi
0x18023cedf  jz      short loc_18023CEEB
0x18023cee1  cmp     [rdi], r12w
0x18023cee5  jnz     loc_18023D6DF
0x18023ceeb  mov     [r14+61h], bl
0x18023ceef  lea     rax, aNull_0; "(NULL)"
0x18023cef6  test    bl, bl
0x18023cef8  jz      short loc_18023CF35
0x18023cefa  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18023cf01  jz      short loc_18023CF35
0x18023cf03  mov     [rsp+210h+var_1C8], rax; char *
0x18023cf08  lea     r9, aCheckingRegist; "Checking registry for verification purp"...
0x18023cf0f  mov     [rsp+210h+var_1D0], rax; char *
0x18023cf14  xor     edx, edx; unsigned __int16
0x18023cf16  mov     [rsp+210h+var_1D8], rax; char *
0x18023cf1b  xor     r8d, r8d; int
0x18023cf1e  mov     [rsp+210h+peUse], rax; char *
0x18023cf23  mov     [rsp+210h+cchReferencedDomainName], rax; char *
0x18023cf28  lea     ecx, [rdx+9]; int
0x18023cf2b  mov     [rsp+210h+ReferencedDomainName], rax; char *
0x18023cf30  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023cf35  test    rdi, rdi
0x18023cf38  jz      loc_18023D378
0x18023cf3e  cmp     [rdi], r12w
0x18023cf42  jz      loc_18023D378
0x18023cf48  mov     eax, 48h ; 'H'
0x18023cf4d  mov     [rsp+210h+var_1AC], r12d
0x18023cf52  mov     [rsp+210h+cbSid], eax
0x18023cf56  lea     rcx, [rsp+210h+hObject]; TokenHandle
0x18023cf5b  mov     [rbp+110h+var_138], eax
0x18023cf5e  lea     rax, [rbp+110h+var_130]
0x18023cf62  mov     [rbp+110h+Sid], rax
0x18023cf66  lea     rax, [rbp+110h+var_178]
0x18023cf6a  mov     [rbp+110h+var_188], rax
0x18023cf6e  mov     [rsp+210h+var_198], r12d
0x18023cf73  mov     [rbp+110h+var_180], esi
0x18023cf76  mov     [rsp+210h+hObject], r12
0x18023cf7b  call    ?OpenUserToken@@YAKAEAPEAXPEA_N@Z; OpenUserToken(void * &,bool *)
0x18023cf80  test    eax, eax
0x18023cf82  jnz     loc_18023D337
0x18023cf88  mov     rcx, [rsp+210h+hObject]; void *
0x18023cf8d  lea     rdx, [rbp+110h+pSid2]; char *
0x18023cf94  call    ?GetUserSID@@YAKPEAXQEAD@Z; GetUserSID(void *,char * const)
0x18023cf99  mov     rcx, [rsp+210h+hObject]; hObject
0x18023cf9e  mov     ebx, eax
0x18023cfa0  call    cs:__imp_CloseHandle
0x18023cfa7  nop     dword ptr [rax+rax+00h]
0x18023cfac  test    ebx, ebx
0x18023cfae  jnz     loc_18023D337
0x18023cfb4  mov     r8, [rbp+110h+Sid]; Sid
0x18023cfb8  lea     rax, [rsp+210h+var_198]
0x18023cfbd  mov     [rsp+210h+peUse], rax; peUse
0x18023cfc2  lea     r9, [rsp+210h+cbSid]; cbSid
0x18023cfc7  lea     rax, [rsp+210h+var_1AC]
0x18023cfcc  mov     rdx, rdi; lpAccountName
0x18023cfcf  mov     [rsp+210h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18023cfd4  xor     ecx, ecx; lpSystemName
0x18023cfd6  mov     rax, [rbp+110h+var_188]
0x18023cfda  mov     [rsp+210h+ReferencedDomainName], rax; ReferencedDomainName
0x18023cfdf  call    cs:__imp_LookupAccountNameW
0x18023cfe6  nop     dword ptr [rax+rax+00h]
0x18023cfeb  mov     edx, [rsp+210h+var_1AC]
0x18023cfef  lea     rcx, [rbp+110h+var_188]
0x18023cff3  mov     r8b, sil
0x18023cff6  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18023cffb  test    al, al
0x18023cffd  jz      loc_18023D2F5
0x18023d003  mov     edx, [rsp+210h+cbSid]
0x18023d007  lea     rcx, [rbp+110h+Sid]
0x18023d00b  call    ?SetSize@?$CAPITempBuffer@D$0EI@@@QEAA_NH_N@Z; CAPITempBuffer<char,72>::SetSize(int,bool)
0x18023d010  test    al, al
0x18023d012  jz      loc_18023D2F5
0x18023d018  mov     rax, [rbp+110h+var_188]
0x18023d01c  lea     rcx, [rsp+210h+var_198]
0x18023d021  mov     r8, [rbp+110h+Sid]; Sid
0x18023d025  lea     r9, [rsp+210h+cbSid]; cbSid
0x18023d02a  mov     [rsp+210h+peUse], rcx; peUse
0x18023d02f  mov     rdx, rdi; lpAccountName
0x18023d032  lea     rcx, [rsp+210h+var_1AC]
0x18023d037  mov     [rsp+210h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18023d03c  xor     ecx, ecx; lpSystemName
0x18023d03e  mov     [rsp+210h+ReferencedDomainName], rax; ReferencedDomainName
0x18023d043  call    cs:__imp_LookupAccountNameW
0x18023d04a  nop     dword ptr [rax+rax+00h]
0x18023d04f  test    eax, eax
0x18023d051  jnz     loc_18023D19A
0x18023d057  lea     rax, [rbp+110h+Buffer]
0x18023d05b  mov     [rbp+110h+var_150], esi
0x18023d05e  lea     rdx, [rsp+210h+pcbBuffer]; pcbBuffer
0x18023d063  mov     [rbp+110h+lpBuffer], rax
0x18023d067  lea     rcx, [rbp+110h+Buffer]; lpBuffer
0x18023d06b  mov     [rsp+210h+pcbBuffer], esi
0x18023d06f  call    cs:__imp_GetUserNameW
0x18023d076  nop     dword ptr [rax+rax+00h]
0x18023d07b  mov     edx, [rsp+210h+pcbBuffer]
0x18023d07f  lea     rcx, [rbp+110h+lpBuffer]
0x18023d083  mov     r8b, sil
0x18023d086  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18023d08b  test    al, al
0x18023d08d  jz      loc_18023D117
0x18023d093  mov     rcx, [rbp+110h+lpBuffer]; lpBuffer
0x18023d097  lea     rdx, [rsp+210h+pcbBuffer]; pcbBuffer
0x18023d09c  call    cs:__imp_GetUserNameW
0x18023d0a3  nop     dword ptr [rax+rax+00h]
0x18023d0a8  test    eax, eax
0x18023d0aa  jz      short loc_18023D117
0x18023d0ac  mov     rcx, [rbp+110h+lpBuffer]; lpString1
0x18023d0b0  mov     rdx, rdi; lpString2
0x18023d0b3  call    cs:__imp_lstrcmpiW
0x18023d0ba  nop     dword ptr [rax+rax+00h]
0x18023d0bf  test    eax, eax
0x18023d0c1  jz      short loc_18023D106
0x18023d0c3  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x18023d0c8  neg     al
0x18023d0ca  lea     rcx, [rbp+110h+lpBuffer]
0x18023d0ce  sbb     ebx, ebx
0x18023d0d0  and     ebx, 895h
0x18023d0d6  add     ebx, 5
0x18023d0d9  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d0de  lea     rcx, [rbp+110h+var_188]
0x18023d0e2  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d0e7  cmp     [rbp+110h+var_138], 48h ; 'H'
0x18023d0eb  jle     loc_18023D186
0x18023d0f1  mov     rcx, [rbp+110h+Sid]; hMem
0x18023d0f5  call    cs:__imp_GlobalFree
0x18023d0fc  nop     dword ptr [rax+rax+00h]
0x18023d101  jmp     loc_18023D186
0x18023d106  lea     rcx, [rbp+110h+lpBuffer]
0x18023d10a  mov     dil, sil
0x18023d10d  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d112  jmp     loc_18023D1B8
0x18023d117  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18023d11e  jz      short loc_18023D159
0x18023d120  lea     r8, aNull_0; "(NULL)"
0x18023d127  xor     edx, edx; unsigned __int16
0x18023d129  mov     [rsp+210h+var_1C8], r8; char *
0x18023d12e  lea     r9, aCouldNotRetrie; "Could not retrieve UserName of calling "...
0x18023d135  mov     [rsp+210h+var_1D0], r8; char *
0x18023d13a  mov     [rsp+210h+var_1D8], r8; char *
0x18023d13f  mov     [rsp+210h+peUse], r8; char *
0x18023d144  lea     ecx, [rdx+9]; int
0x18023d147  mov     [rsp+210h+cchReferencedDomainName], r8; char *
0x18023d14c  mov     [rsp+210h+ReferencedDomainName], r8; char *
0x18023d151  xor     r8d, r8d; int
0x18023d154  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023d159  lea     rcx, [rbp+110h+lpBuffer]
0x18023d15d  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d162  lea     rcx, [rbp+110h+var_188]
0x18023d166  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d16b  cmp     [rbp+110h+var_138], 48h ; 'H'
0x18023d16f  jle     short loc_18023D181
0x18023d171  mov     rcx, [rbp+110h+Sid]; hMem
0x18023d175  call    cs:__imp_GlobalFree
0x18023d17c  nop     dword ptr [rax+rax+00h]
0x18023d181  mov     ebx, 65Bh
0x18023d186  lea     rax, [rbp+110h+var_130]
0x18023d18a  mov     [rbp+110h+var_138], 48h ; 'H'
0x18023d191  mov     [rbp+110h+Sid], rax
0x18023d195  jmp     loc_18023D632
0x18023d19a  mov     rcx, [rbp+110h+Sid]; pSid1
0x18023d19e  lea     rdx, [rbp+110h+pSid2]; pSid2
0x18023d1a5  call    cs:__imp_EqualSid
0x18023d1ac  nop     dword ptr [rax+rax+00h]
0x18023d1b1  test    eax, eax
0x18023d1b3  jz      short loc_18023D200
0x18023d1b5  mov     dil, sil
0x18023d1b8  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18023d1bf  lea     rbx, aNull_0; "(NULL)"
0x18023d1c6  jz      loc_18023D272
0x18023d1cc  mov     [rsp+210h+var_1C8], rbx; char *
0x18023d1d1  lea     r9, aProductToBeMod; "Product to be modified belongs to curre"...
0x18023d1d8  mov     [rsp+210h+var_1D0], rbx; char *
0x18023d1dd  xor     edx, edx; unsigned __int16
0x18023d1df  mov     [rsp+210h+var_1D8], rbx; char *
0x18023d1e4  xor     r8d, r8d; int
0x18023d1e7  mov     [rsp+210h+peUse], rbx; char *
0x18023d1ec  mov     [rsp+210h+cchReferencedDomainName], rbx; char *
0x18023d1f1  lea     ecx, [rdx+9]; int
0x18023d1f4  mov     [rsp+210h+ReferencedDomainName], rbx; char *
0x18023d1f9  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023d1fe  jmp     short loc_18023D272
0x18023d200  mov     rcx, [rbp+110h+Sid]
0x18023d204  lea     rdx, [rbp+110h+var_170]
0x18023d208  mov     [rbp+110h+var_164], esi
0x18023d20b  call    ?GetStringSid@@YAKQEAXAEAV?$CAPITempBufferRef@G@@@Z; GetStringSid(void * const,CAPITempBufferRef<ushort> &)
0x18023d210  test    eax, eax
0x18023d212  jnz     loc_18023D337
0x18023d218  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18023d21f  mov     dil, r12b
0x18023d222  jz      short loc_18023D26B
0x18023d224  mov     [rsp+210h+var_1B8], r12; void *
0x18023d229  lea     rax, aNull; "(NULL)"
0x18023d230  mov     [rsp+210h+var_1C0], r12d; unsigned int
0x18023d235  lea     r9, aAttemptingToMo; "Attempting to modify per-user managed i"...
0x18023d23c  mov     [rsp+210h+var_1C8], rax; unsigned __int16 *
0x18023d241  xor     edx, edx; unsigned __int16
0x18023d243  mov     [rsp+210h+var_1D0], rax; unsigned __int16 *
0x18023d248  xor     r8d, r8d; int
0x18023d24b  mov     [rsp+210h+var_1D8], rax; unsigned __int16 *
0x18023d250  mov     [rsp+210h+peUse], rax; unsigned __int16 *
0x18023d255  mov     [rsp+210h+cchReferencedDomainName], rax; unsigned __int16 *
0x18023d25a  lea     ecx, [rdx+9]; int
0x18023d25d  mov     rax, [rbp+110h+var_170]
0x18023d261  mov     [rsp+210h+ReferencedDomainName], rax; unsigned __int16 *
0x18023d266  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18023d26b  lea     rbx, aNull_0; "(NULL)"
0x18023d272  lea     rcx, [rbp+110h+var_188]
0x18023d276  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d27b  cmp     [rbp+110h+var_138], 48h ; 'H'
0x18023d27f  jle     short loc_18023D291
0x18023d281  mov     rcx, [rbp+110h+Sid]; hMem
0x18023d285  call    cs:__imp_GlobalFree
0x18023d28c  nop     dword ptr [rax+rax+00h]
0x18023d291  test    r15b, r15b
0x18023d294  jnz     loc_18023D37F
0x18023d29a  test    dil, dil
0x18023d29d  jnz     loc_18023D37F
0x18023d2a3  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x18023d2a8  test    al, al
0x18023d2aa  jnz     loc_18023D37F
0x18023d2b0  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18023d2b7  jz      short loc_18023D2EB
0x18023d2b9  mov     [rsp+210h+var_1C8], rbx; char *
0x18023d2be  lea     r9, aNonAdminAttemp; "Non-Admin attempting to open another us"...
0x18023d2c5  mov     [rsp+210h+var_1D0], rbx; char *
0x18023d2ca  xor     edx, edx; unsigned __int16
0x18023d2cc  mov     [rsp+210h+var_1D8], rbx; char *
0x18023d2d1  xor     r8d, r8d; int
0x18023d2d4  mov     [rsp+210h+peUse], rbx; char *
0x18023d2d9  mov     [rsp+210h+cchReferencedDomainName], rbx; char *
0x18023d2de  lea     ecx, [rdx+9]; int
0x18023d2e1  mov     [rsp+210h+ReferencedDomainName], rbx; char *
0x18023d2e6  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023d2eb  mov     ebx, 5
0x18023d2f0  jmp     loc_18023D632
0x18023d2f5  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18023d2fc  jz      short loc_18023D337
0x18023d2fe  lea     r8, aNull_0; "(NULL)"
0x18023d305  xor     edx, edx; unsigned __int16
0x18023d307  mov     [rsp+210h+var_1C8], r8; char *
0x18023d30c  lea     r9, aCouldNotRetrie; "Could not retrieve UserName of calling "...
0x18023d313  mov     [rsp+210h+var_1D0], r8; char *
0x18023d318  mov     [rsp+210h+var_1D8], r8; char *
0x18023d31d  mov     [rsp+210h+peUse], r8; char *
0x18023d322  lea     ecx, [rdx+9]; int
0x18023d325  mov     [rsp+210h+cchReferencedDomainName], r8; char *
0x18023d32a  mov     [rsp+210h+ReferencedDomainName], r8; char *
0x18023d32f  xor     r8d, r8d; int
0x18023d332  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023d337  lea     rcx, [rbp+110h+var_188]
0x18023d33b  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18023d340  cmp     [rbp+110h+var_138], 48h ; 'H'
0x18023d344  jle     short loc_18023D356
0x18023d346  mov     rcx, [rbp+110h+Sid]; hMem
0x18023d34a  call    cs:__imp_GlobalFree
0x18023d351  nop     dword ptr [rax+rax+00h]
0x18023d356  lea     rax, [rbp+110h+var_130]
  ... truncated ...
```
