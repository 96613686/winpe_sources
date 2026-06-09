# ConnectToNameSpace(_GPOINFO *,ushort const *,int,IWbemLocator *,IWbemServices * *,int *)

- ea: `0x18006ea44`
- end: `0x18006f45c`
- name: `?ConnectToNameSpace@@YAHPEAU_GPOINFO@@PEBGHPEAUIWbemLocator@@PEAPEAUIWbemServices@@PEAH@Z`
- size: `2584`
- prototype: `_BOOL8 __fastcall(struct _GPOINFO *, const unsigned __int16 *, int, struct IWbemLocator *, struct IWbemServices **, int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005541c`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001d0c0`
- `0x18001d220`
- `0x18001ee6c`
- `0x18002c690`
- `0x180033140`
- `0x18003d630`
- `0x180049bf0`
- `0x18004b090`
- `0x18004b300`
- `0x18004dfd0`
- `0x18004e164`
- `0x18004f03c`
- `0x180053510`
- `0x1800535a0`
- `0x1800585e8`
- `0x18006ea44`
- `0x180075ec0`
- `0x1800b038c`
- `0x1800b5ca8`
- `0x1800b7494`
- `0x1800b74e0`
- `0x1800b8bcc`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ebd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f14e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ebd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f14e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f176`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ead3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006eb32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ec2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ecb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006eeb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ead3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006eb32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ec2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ecb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006eeb1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18006f12f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18006f12f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ee2b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ee8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ef3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f116`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f2e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f36a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ee2b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ee8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ef3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f116`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f2e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f36a`

## string_xrefs

- `0x18006eb0c`: `Computer`
- `0x18006ee4a`: `ConnectToNameSpace: ConnectServer failed with 0x%x, trying to recreate the name space`
- `0x18006ee72`: `ConnectToNameSpace: ConnectServer failed with 0x%x, trying to recreate the name space`
- `0x18006f397`: `ConnectToNameSpace: Minor schema upg happened. copying classes. `
- `0x18006f3bc`: `ConnectToNameSpace: Minor schema upg happened. copying classes. `
- `0x18006f40f`: `ConnectToNameSpace: CopyNameSpace failed with 0x%x`
- `0x18006f445`: `ConnectToNameSpace: CopyNameSpace failed with 0x%x`
- `0x18006efaa`: `ConnectToNameSpace::GetUserSid failed with %d`
- `0x18006efd9`: `ConnectToNameSpace::GetUserSid failed with %d`
- `0x18006f154`: `ConnectToNameSpace::SetSecurityDescriptorControl failed with %d`
- `0x18006f17c`: `ConnectToNameSpace::SetSecurityDescriptorControl failed with %d`
- `0x18006f1d0`: `ConnectToNameSpace:: CreateAndCopyNameSpace failed. Error=0x%08X.`
- `0x18006f1f9`: `ConnectToNameSpace:: CreateAndCopyNameSpace failed. Error=0x%08X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall ConnectToNameSpace(
        struct _GPOINFO *a1,
        const unsigned __int16 *a2,
        int a3,
        struct IWbemLocator *a4,
        struct IWbemServices **a5,
        int *a6)
{
  int *v8; // r13
  int v10; // eax
  __int64 v11; // rsi
  bool v12; // zf
  __int64 v13; // rax
  unsigned __int64 v14; // rdi
  HLOCAL v15; // rax
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rbx
  HLOCAL v21; // rax
  _WORD *v22; // r14
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  BOOL v25; // edi
  DWORD v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned __int64 v29; // rdi
  HLOCAL v30; // rax
  unsigned __int16 *v31; // rax
  int v32; // eax
  __int64 v33; // rcx
  HLOCAL v34; // rax
  OLECHAR *v35; // rbx
  unsigned int v36; // edi
  int v37; // ecx
  void (*v38)(unsigned int, const unsigned __int16 *, ...); // rax
  struct IWbemServices *v39; // rax
  unsigned __int64 v40; // rsi
  int *v41; // rax
  unsigned __int16 *v42; // rdi
  unsigned __int16 *v43; // rax
  void *UserSid; // rsi
  void (*v45)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v46; // eax
  DWORD v47; // eax
  struct _SECURITY_DESCRIPTOR *SelfRelativeSD; // rax
  PSECURITY_DESCRIPTOR v49; // rsi
  void (*v50)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v51; // eax
  const wchar_t *v52; // rdx
  __int64 v53; // r8
  void (*v54)(unsigned int, const unsigned __int16 *, ...); // rax
  DWORD v55; // eax
  const unsigned __int16 *v56; // rdx
  int v57; // esi
  struct IWbemLocator *v58; // rdi
  int v59; // eax
  struct IWbemServices *v60; // rax
  int v61; // edi
  struct IWbemServices *v62; // rax
  int v63; // eax
  void *Src; // [rsp+30h] [rbp-61h]
  struct IWbemServices *v65; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int16 *v66; // [rsp+60h] [rbp-31h] BYREF
  void *v67; // [rsp+68h] [rbp-29h] BYREF
  _WORD *v68; // [rsp+70h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-19h] BYREF
  _BYTE v70[88]; // [rsp+80h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+E8h] [rbp+57h] BYREF
  int v72; // [rsp+F8h] [rbp+67h]
  struct IWbemLocator *v73; // [rsp+100h] [rbp+6Fh]

  v73 = a4;
  v72 = a3;
  v66 = 0;
  v65 = 0;
  v68 = 0;
  LODWORD(pSecurityDescriptor) = 0;
  *a5 = 0;
  v8 = a6;
  if ( a6 )
    *a6 = 0;
  if ( !a1 )
    return 0;
  v10 = *(_DWORD *)a1 & 1;
  v11 = -1;
  if ( a3 )
  {
    v33 = -1;
    do
      ++v33;
    while ( a2[v33] );
    if ( !v10 )
    {
      v14 = v33 + 9;
      v34 = LocalAlloc(0x40u, 2 * (v33 + 9));
      XPtrLF<unsigned short>::operator=((void **)&v66, v34);
      v16 = v66;
      if ( !v66 || (int)StringCchCopyW(v66, v14, a2) < 0 )
        goto LABEL_18;
      v17 = CheckSlash(v16);
      v18 = L"User";
LABEL_37:
      v32 = StringCchCopyW(v17, v14 - (v17 - v16), v18);
      goto LABEL_38;
    }
    v14 = v33 + 13;
LABEL_9:
    v15 = LocalAlloc(0x40u, 2 * v14);
    XPtrLF<unsigned short>::operator=((void **)&v66, v15);
    v16 = v66;
    if ( !v66 || (int)StringCchCopyW(v66, v14, a2) < 0 )
      goto LABEL_18;
    v17 = CheckSlash(v16);
    v18 = L"Computer";
    goto LABEL_37;
  }
  v12 = v10 == 0;
  v13 = -1;
  if ( !v12 )
  {
    do
      ++v13;
    while ( a2[v13] );
    v14 = v13 + 13;
    goto LABEL_9;
  }
  v19 = *((_QWORD *)a1 + 9);
  do
    ++v13;
  while ( *(_WORD *)(v19 + 2 * v13) );
  v20 = v13 + 1;
  v21 = LocalAlloc(0x40u, 2 * (v13 + 1));
  XPtrLF<unsigned short>::operator=((void **)&v68, v21);
  v22 = v68;
  if ( !v68 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v23 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        LastError = GetLastError();
        v23(2u, L"ConnectToNameSpace: couldn't allocate memory with error %d", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v26 = GetLastError();
        RedirectDebugMsg(2u, L"ConnectToNameSpace: couldn't allocate memory with error %d", v26);
      }
    }
    goto LABEL_18;
  }
  ConvertSidToWMIName(*((_QWORD *)a1 + 9), v20, v68);
  v27 = -1;
  do
    ++v27;
  while ( a2[v27] );
  v28 = -1;
  do
    ++v28;
  while ( v22[v28] );
  v29 = v27 + v28 + 12;
  v30 = LocalAlloc(0x40u, 2 * v29);
  XPtrLF<unsigned short>::operator=((void **)&v66, v30);
  v16 = v66;
  if ( !v66 || (int)StringCchCopyW(v66, v29, a2) < 0 )
    goto LABEL_18;
  v31 = CheckSlash(v16);
  v32 = StringCchPrintfW(v31, v29 - (v31 - v16), L"User\\%s", v22);
LABEL_38:
  if ( v32 >= 0 )
  {
    XBStr::XBStr((XBStr *)&bstrString, v16);
    v35 = bstrString;
    v36 = ((__int64 (__fastcall *)(struct IWbemLocator *, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, struct IWbemServices **))v73->lpVtbl->ConnectServer)(
            v73,
            bstrString,
            0,
            0,
            0,
            0,
            0,
            0,
            &v65);
    v37 = *(_DWORD *)&g_dwDebugLevel;
    v38 = g_lpDebugMsg;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_46;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ConnectToNameSpace: ConnectServer returned 0x%x", v36);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_46:
        if ( v72 )
        {
          if ( (v36 & 0x80000000) != 0 && v37 )
          {
            if ( v38 )
            {
              v38(2u, L"ConnectToNameSpace: ConnectServer failed with 0x%x", v36);
            }
            else if ( g_lpDebugMsgContextInstance )
            {
              if ( g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"ConnectToNameSpace: ConnectServer failed with 0x%x", v36);
            }
          }
          v39 = v65;
          v65 = 0;
          *a5 = v39;
          v25 = (v36 & 0x80000000) == 0;
          SysFreeString(v35);
          goto LABEL_19;
        }
        if ( (v36 & 0x80000000) == 0 )
        {
          v57 = 0;
          if ( (int)GetRsopSchemaVersionNumber(v65, (unsigned int *)&pSecurityDescriptor) >= 0 )
          {
            v61 = (int)pSecurityDescriptor;
            if ( !(_DWORD)pSecurityDescriptor )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    (_DWORD)pSecurityDescriptor + 4,
                    L"ConnectToNameSpace: Rsop data has not been logged before or a major schema upg happened. relogging..");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    4u,
                    L"ConnectToNameSpace: Rsop data has not been logged before or a major schema upg happened. relogging..");
                }
              }
              if ( v8 )
                *v8 = 1;
            }
            if ( (*(_BYTE *)a1 & 1) != 0 || v61 == 2228228 )
              goto LABEL_132;
            LODWORD(a6) = 0;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"ConnectToNameSpace: Minor schema upg happened. copying classes. ");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"ConnectToNameSpace: Minor schema upg happened. copying classes. ");
              }
            }
            v63 = CopyNameSpace(L"\\\\.\\Root\\Rsop\\User", v35, 0, &a6, v73);
            if ( v63 >= 0 )
            {
LABEL_132:
              v62 = v65;
              v65 = 0;
              *a5 = v62;
              SysFreeString(v35);
              v25 = 1;
              goto LABEL_19;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"ConnectToNameSpace: CopyNameSpace failed with 0x%x", (unsigned int)v63);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"ConnectToNameSpace: CopyNameSpace failed with 0x%x", (unsigned int)v63);
              }
            }
          }
        }
        else
        {
          if ( v37 )
          {
            if ( v38 )
            {
              v38(4u, L"ConnectToNameSpace: ConnectServer failed with 0x%x, trying to recreate the name space", v36);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"ConnectToNameSpace: ConnectServer failed with 0x%x, trying to recreate the name space",
                v36);
            }
          }
          if ( (*(_BYTE *)a1 & 1) != 0 )
            goto LABEL_63;
          do
            ++v11;
          while ( a2[v11] );
          v40 = v11 + 24;
          v41 = (int *)LocalAlloc(0x40u, 2 * v40);
          v42 = (unsigned __int16 *)v41;
          a6 = v41;
          if ( !v41 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"ConnectToNameSpace: Failed to allocate memory.3");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"ConnectToNameSpace: Failed to allocate memory.3");
              }
            }
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&a6);
LABEL_63:
            SysFreeString(v35);
            goto LABEL_18;
          }
          if ( (int)StringCchCopyW((unsigned __int16 *)v41, v40, a2) < 0
            || (v43 = CheckSlash(v42), (int)StringCchCopyW(v43, v40 - (v43 - v42), L"User") < 0) )
          {
LABEL_74:
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&a6);
            SysFreeString(v35);
            v25 = 0;
            goto LABEL_19;
          }
          UserSid = GetUserSid(*((HANDLE *)a1 + 1));
          v67 = UserSid;
          if ( !UserSid )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v45 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v46 = GetLastError();
                v45(2u, L"ConnectToNameSpace::GetUserSid failed with %d", v46);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v47 = GetLastError();
                RedirectDebugMsg(2u, L"ConnectToNameSpace::GetUserSid failed with %d", v47);
              }
            }
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v67);
            goto LABEL_74;
          }
          pSecurityDescriptor = 0;
          CSecDesc::CSecDesc((CSecDesc *)v70);
          CSecDesc::AddLocalSystem((CSecDesc *)v70, 393279, 2);
          CSecDesc::AddAdministrators((CSecDesc *)v70, 393279, 2);
          CSecDesc::AddNetworkService((CSecDesc *)v70, 393279, 2);
          CSecDesc::AddSid((CSecDesc *)v70, UserSid, 131107, 2);
          CSecDesc::AddAdministratorsAsOwner((CSecDesc *)v70);
          CSecDesc::AddAdministratorsAsGroup((CSecDesc *)v70);
          SelfRelativeSD = CSecDesc::MakeSelfRelativeSD((CSecDesc *)v70);
          XPtrLF<_SECURITY_DESCRIPTOR>::operator=(&pSecurityDescriptor, SelfRelativeSD);
          v49 = pSecurityDescriptor;
          if ( !pSecurityDescriptor )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v50 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v51 = GetLastError();
                v52 = L"ConnectToNameSpace::MakeselfRelativeSD failed with %d";
LABEL_88:
                v53 = v51;
                v54 = v50;
LABEL_89:
                v54(2u, v52, v53);
                goto LABEL_95;
              }
              if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                goto LABEL_95;
              v55 = GetLastError();
              v56 = L"ConnectToNameSpace::MakeselfRelativeSD failed with %d";
LABEL_94:
              RedirectDebugMsg(2u, v56, v55);
            }
LABEL_95:
            CSecDesc::~CSecDesc((CSecDesc *)v70);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v67);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&a6);
            SysFreeString(v35);
            v25 = 0;
            goto LABEL_19;
          }
          if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1000u, 0x1000u) )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_95;
            v50 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v51 = GetLastError();
              v52 = L"ConnectToNameSpace::SetSecurityDescriptorControl failed with %d";
              goto LABEL_88;
            }
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              goto LABEL_95;
            v55 = GetLastError();
            v56 = L"ConnectToNameSpace::SetSecurityDescriptorControl failed with %d";
            goto LABEL_94;
          }
          Src = v49;
          v57 = 1;
          v58 = v73;
          v55 = CreateAndCopyNameSpace(v73, 1, Src, 0);
          if ( (v55 & 0x80000000) != 0 )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_95;
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"ConnectToNameSpace:: CreateAndCopyNameSpace failed. Error=0x%08X.", v55);
              goto LABEL_95;
            }
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              goto LABEL_95;
            v56 = L"ConnectToNameSpace:: CreateAndCopyNameSpace failed. Error=0x%08X.";
            goto LABEL_94;
          }
          v59 = ((__int64 (__fastcall *)(struct IWbemLocator *, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, struct IWbemServices **))v58->lpVtbl->ConnectServer)(
                  v58,
                  v35,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  &v65);
          v53 = (unsigned int)v59;
          if ( v59 < 0 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v54 = g_lpDebugMsg;
              if ( !g_lpDebugMsg )
              {
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"ConnectToNameSpace:: ConnectServer failed. hr=0x%08X.", v53);
                goto LABEL_95;
              }
              v52 = L"ConnectToNameSpace:: ConnectServer failed. hr=0x%08X.";
              goto LABEL_89;
            }
            goto LABEL_95;
          }
          v60 = v65;
          v65 = 0;
          *a5 = v60;
          if ( v8 )
            *v8 = 1;
          CSecDesc::~CSecDesc((CSecDesc *)v70);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v67);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&a6);
        }
        SysFreeString(v35);
        v25 = v57;
        goto LABEL_19;
      }
      RedirectDebugMsg(4u, L"ConnectToNameSpace: ConnectServer returned 0x%x", v36);
    }
    v38 = g_lpDebugMsg;
    v37 = *(_DWORD *)&g_dwDebugLevel;
    goto LABEL_46;
  }
LABEL_18:
  v25 = 0;
LABEL_19:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v68);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v65);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v66);
  return v25;
}

```

## disassembly

```asm
0x18006ea44  mov     rax, rsp
0x18006ea47  mov     [rax+10h], rbx
0x18006ea4b  mov     [rax+20h], r9
0x18006ea4f  mov     [rax+18h], r8d
0x18006ea53  push    rbp
0x18006ea54  push    rsi
0x18006ea55  push    rdi
0x18006ea56  push    r12
0x18006ea58  push    r13
0x18006ea5a  push    r14
0x18006ea5c  push    r15
0x18006ea5e  lea     rbp, [rax-4Fh]
0x18006ea62  sub     rsp, 0A0h
0x18006ea69  mov     r15, rdx
0x18006ea6c  mov     r12, rcx
0x18006ea6f  xor     edx, edx
0x18006ea71  mov     [rbp+47h+var_78], rdx
0x18006ea75  mov     [rbp+47h+var_80], rdx
0x18006ea79  mov     r14d, edx
0x18006ea7c  mov     [rbp+47h+var_68], rdx
0x18006ea80  mov     dword ptr [rbp+47h+pSecurityDescriptor], edx
0x18006ea83  mov     rax, [rbp+47h+arg_20]
0x18006ea87  mov     [rax], rdx
0x18006ea8a  mov     r13, [rbp+47h+arg_28]
0x18006ea8e  test    r13, r13
0x18006ea91  jz      short loc_18006EA97
0x18006ea93  mov     [r13+0], edx
0x18006ea97  test    r12, r12
0x18006ea9a  jnz     short loc_18006EAA3
0x18006ea9c  xor     eax, eax
0x18006ea9e  jmp     loc_18006EBA3
0x18006eaa3  mov     eax, [rcx]
0x18006eaa5  and     eax, 1
0x18006eaa8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006eaac  test    r8d, r8d
0x18006eaaf  jnz     loc_18006EC8D
0x18006eab5  test    eax, eax
0x18006eab7  mov     rax, rsi
0x18006eaba  jz      short loc_18006EB18
0x18006eabc  inc     rax
0x18006eabf  cmp     [r15+rax*2], dx
0x18006eac4  jnz     short loc_18006EABC
0x18006eac6  lea     rdi, [rax+0Dh]
0x18006eaca  lea     rdx, [rdi+rdi]; uBytes
0x18006eace  mov     ecx, 40h ; '@'; uFlags
0x18006ead3  call    cs:__imp_LocalAlloc
0x18006ead9  mov     rdx, rax
0x18006eadc  lea     rcx, [rbp+47h+var_78]
0x18006eae0  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18006eae5  mov     rbx, [rbp+47h+var_78]
0x18006eae9  test    rbx, rbx
0x18006eaec  jz      loc_18006EB82
0x18006eaf2  mov     r8, r15; unsigned __int16 *
0x18006eaf5  mov     rdx, rdi; unsigned __int64
0x18006eaf8  mov     rcx, rbx; unsigned __int16 *
0x18006eafb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006eb00  test    eax, eax
0x18006eb02  js      short loc_18006EB82
0x18006eb04  mov     rcx, rbx; unsigned __int16 *
0x18006eb07  call    ?CheckSlash@@YAPEAGPEAG@Z; CheckSlash(ushort *)
0x18006eb0c  lea     r8, aComputer; "Computer"
0x18006eb13  jmp     loc_18006ECF8
0x18006eb18  mov     rcx, [rcx+48h]
0x18006eb1c  inc     rax
0x18006eb1f  cmp     [rcx+rax*2], dx
0x18006eb23  jnz     short loc_18006EB1C
0x18006eb25  lea     rbx, [rax+1]
0x18006eb29  lea     rdx, [rbx+rbx]; uBytes
0x18006eb2d  mov     ecx, 40h ; '@'; uFlags
0x18006eb32  call    cs:__imp_LocalAlloc
0x18006eb38  mov     rdx, rax
0x18006eb3b  lea     rcx, [rbp+47h+var_68]
0x18006eb3f  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18006eb44  mov     r14, [rbp+47h+var_68]
0x18006eb48  test    r14, r14
0x18006eb4b  jnz     loc_18006EBEE
0x18006eb51  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006eb58  jz      short loc_18006EB82
0x18006eb5a  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006eb61  test    rbx, rbx
0x18006eb64  jz      short loc_18006EBBE
0x18006eb66  call    cs:__imp_GetLastError
0x18006eb6c  mov     r8d, eax
0x18006eb6f  lea     rdx, aConnecttonames_7; "ConnectToNameSpace: couldn't allocate m"...
0x18006eb76  lea     ecx, [r14+2]
0x18006eb7a  mov     rax, rbx
0x18006eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb82  xor     edi, edi
0x18006eb84  lea     rcx, [rbp+47h+var_68]
0x18006eb88  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18006eb8d  nop
0x18006eb8e  lea     rcx, [rbp+47h+var_80]
0x18006eb92  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006eb97  nop
0x18006eb98  lea     rcx, [rbp+47h+var_78]
0x18006eb9c  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18006eba1  mov     eax, edi
0x18006eba3  mov     rbx, [rsp+0D0h+arg_8]
0x18006ebab  add     rsp, 0A0h
0x18006ebb2  pop     r15
0x18006ebb4  pop     r14
0x18006ebb6  pop     r13
0x18006ebb8  pop     r12
0x18006ebba  pop     rdi
0x18006ebbb  pop     rsi
0x18006ebbc  pop     rbp
0x18006ebbd  retn
0x18006ebbe  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18006ebc6  jz      short loc_18006EB82
0x18006ebc8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006ebd0  jz      short loc_18006EB82
0x18006ebd2  call    cs:__imp_GetLastError
0x18006ebd8  mov     r8d, eax
0x18006ebdb  lea     rdx, aConnecttonames_7; "ConnectToNameSpace: couldn't allocate m"...
0x18006ebe2  mov     ecx, 2; unsigned int
0x18006ebe7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006ebec  jmp     short loc_18006EB82
0x18006ebee  mov     r8, r14
0x18006ebf1  mov     rdx, rbx
0x18006ebf4  mov     rcx, [r12+48h]
0x18006ebf9  call    ConvertSidToWMIName
0x18006ebfe  mov     rcx, rsi
0x18006ec01  xor     edx, edx
0x18006ec03  inc     rcx
0x18006ec06  cmp     [r15+rcx*2], dx
0x18006ec0b  jnz     short loc_18006EC03
0x18006ec0d  mov     rax, rsi
0x18006ec10  inc     rax
0x18006ec13  cmp     [r14+rax*2], dx
0x18006ec18  jnz     short loc_18006EC10
0x18006ec1a  lea     rdi, [rax+0Ch]
0x18006ec1e  add     rdi, rcx
0x18006ec21  lea     rdx, [rdi+rdi]; uBytes
0x18006ec25  mov     ecx, 40h ; '@'; uFlags
0x18006ec2a  call    cs:__imp_LocalAlloc
0x18006ec30  mov     rdx, rax
0x18006ec33  lea     rcx, [rbp+47h+var_78]
0x18006ec37  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18006ec3c  mov     rbx, [rbp+47h+var_78]
0x18006ec40  test    rbx, rbx
0x18006ec43  jz      loc_18006EB82
0x18006ec49  mov     r8, r15; unsigned __int16 *
0x18006ec4c  mov     rdx, rdi; unsigned __int64
0x18006ec4f  mov     rcx, rbx; unsigned __int16 *
0x18006ec52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ec57  test    eax, eax
0x18006ec59  js      loc_18006EB82
0x18006ec5f  mov     rcx, rbx; unsigned __int16 *
0x18006ec62  call    ?CheckSlash@@YAPEAGPEAG@Z; CheckSlash(ushort *)
0x18006ec67  mov     rcx, rax
0x18006ec6a  sub     rcx, rbx
0x18006ec6d  sar     rcx, 1
0x18006ec70  sub     rdi, rcx
0x18006ec73  mov     r9, r14
0x18006ec76  lea     r8, aUserS; "User\\%s"
0x18006ec7d  mov     rdx, rdi; unsigned __int64
0x18006ec80  mov     rcx, rax; unsigned __int16 *
0x18006ec83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006ec88  jmp     loc_18006ED0F
0x18006ec8d  mov     rcx, rsi
0x18006ec90  inc     rcx
0x18006ec93  cmp     [r15+rcx*2], dx
0x18006ec98  jnz     short loc_18006EC90
0x18006ec9a  test    eax, eax
0x18006ec9c  jz      short loc_18006ECA7
0x18006ec9e  lea     rdi, [rcx+0Dh]
0x18006eca2  jmp     loc_18006EACA
0x18006eca7  lea     rdi, [rcx+9]
0x18006ecab  lea     rdx, [rdi+rdi]; uBytes
0x18006ecaf  mov     ecx, 40h ; '@'; uFlags
0x18006ecb4  call    cs:__imp_LocalAlloc
0x18006ecba  mov     rdx, rax
0x18006ecbd  lea     rcx, [rbp+47h+var_78]
0x18006ecc1  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18006ecc6  mov     rbx, [rbp+47h+var_78]
0x18006ecca  test    rbx, rbx
0x18006eccd  jz      loc_18006EB82
0x18006ecd3  mov     r8, r15; unsigned __int16 *
0x18006ecd6  mov     rdx, rdi; unsigned __int64
0x18006ecd9  mov     rcx, rbx; unsigned __int16 *
0x18006ecdc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ece1  test    eax, eax
0x18006ece3  js      loc_18006EB82
0x18006ece9  mov     rcx, rbx; unsigned __int16 *
0x18006ecec  call    ?CheckSlash@@YAPEAGPEAG@Z; CheckSlash(ushort *)
0x18006ecf1  lea     r8, aUser; "User"
0x18006ecf8  mov     rcx, rax
0x18006ecfb  sub     rcx, rbx
0x18006ecfe  sar     rcx, 1
0x18006ed01  sub     rdi, rcx
0x18006ed04  mov     rdx, rdi; unsigned __int64
0x18006ed07  mov     rcx, rax; unsigned __int16 *
0x18006ed0a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ed0f  test    eax, eax
0x18006ed11  js      loc_18006EB82
0x18006ed17  mov     rdx, rbx; unsigned __int16 *
0x18006ed1a  lea     rcx, [rbp+47h+bstrString]; this
0x18006ed1e  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x18006ed23  nop
0x18006ed24  mov     rcx, [rbp+47h+arg_18]
0x18006ed28  mov     rax, [rcx]
0x18006ed2b  lea     rdx, [rbp+47h+var_80]
0x18006ed2f  mov     [rsp+40h], rdx
0x18006ed34  xor     edx, edx
0x18006ed36  mov     [rsp+0D0h+var_98], rdx
0x18006ed3b  mov     [rsp+0D0h+var_A0], rdx
0x18006ed40  mov     dword ptr [rsp+0D0h+Src], edx
0x18006ed44  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x18006ed49  xor     r9d, r9d
0x18006ed4c  xor     r8d, r8d
0x18006ed4f  mov     rbx, [rbp+47h+bstrString]
0x18006ed53  mov     rdx, rbx
0x18006ed56  mov     rax, [rax+18h]
0x18006ed5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed5f  mov     edi, eax
0x18006ed61  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18006ed67  xor     edx, edx
0x18006ed69  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006ed70  test    ecx, ecx
0x18006ed72  jz      short loc_18006EDC4
0x18006ed74  test    rax, rax
0x18006ed77  jz      short loc_18006ED8F
0x18006ed79  mov     r8d, edi
0x18006ed7c  lea     rdx, aConnecttonames; "ConnectToNameSpace: ConnectServer retur"...
0x18006ed83  mov     ecx, 4
0x18006ed88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed8d  jmp     short loc_18006EDB5
0x18006ed8f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdx; void * g_lpDebugMsgContextInstance
0x18006ed96  jz      short loc_18006EDC4
0x18006ed98  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006ed9f  jz      short loc_18006EDC4
0x18006eda1  mov     r8d, edi
0x18006eda4  lea     rdx, aConnecttonames; "ConnectToNameSpace: ConnectServer retur"...
0x18006edab  mov     ecx, 4; unsigned int
0x18006edb0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006edb5  xor     edx, edx
0x18006edb7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006edbe  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18006edc4  cmp     [rbp+47h+arg_10], edx
0x18006edc7  jz      short loc_18006EE36
0x18006edc9  test    edi, edi
0x18006edcb  jns     short loc_18006EE14
0x18006edcd  test    ecx, ecx
0x18006edcf  jz      short loc_18006EE14
0x18006edd1  test    rax, rax
0x18006edd4  jz      short loc_18006EDEC
0x18006edd6  mov     r8d, edi
0x18006edd9  lea     rdx, aConnecttonames_6; "ConnectToNameSpace: ConnectServer faile"...
0x18006ede0  mov     ecx, 2
0x18006ede5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006edea  jmp     short loc_18006EE12
0x18006edec  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdx; void * g_lpDebugMsgContextInstance
0x18006edf3  jz      short loc_18006EE14
0x18006edf5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006edfc  jz      short loc_18006EE14
0x18006edfe  mov     r8d, edi
0x18006ee01  lea     rdx, aConnecttonames_6; "ConnectToNameSpace: ConnectServer faile"...
0x18006ee08  mov     ecx, 2; unsigned int
0x18006ee0d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006ee12  xor     edx, edx
0x18006ee14  mov     rax, [rbp+47h+var_80]
0x18006ee18  mov     [rbp+47h+var_80], rdx
0x18006ee1c  mov     rcx, [rbp+47h+arg_20]
0x18006ee20  mov     [rcx], rax
0x18006ee23  not     edi
0x18006ee25  shr     edi, 1Fh
0x18006ee28  mov     rcx, rbx; bstrString
0x18006ee2b  call    cs:__imp_SysFreeString
0x18006ee31  jmp     loc_18006EB84
0x18006ee36  test    edi, edi
0x18006ee38  jns     loc_18006F2CD
0x18006ee3e  test    ecx, ecx
0x18006ee40  jz      short loc_18006EE85
0x18006ee42  test    rax, rax
0x18006ee45  jz      short loc_18006EE5D
0x18006ee47  mov     r8d, edi
0x18006ee4a  lea     rdx, aConnecttonames_2; "ConnectToNameSpace: ConnectServer faile"...
0x18006ee51  mov     ecx, 4
0x18006ee56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee5b  jmp     short loc_18006EE83
0x18006ee5d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdx; void * g_lpDebugMsgContextInstance
0x18006ee64  jz      short loc_18006EE85
0x18006ee66  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006ee6d  jz      short loc_18006EE85
0x18006ee6f  mov     r8d, edi
0x18006ee72  lea     rdx, aConnecttonames_2; "ConnectToNameSpace: ConnectServer faile"...
0x18006ee79  mov     ecx, 4; unsigned int
0x18006ee7e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006ee83  xor     edx, edx
0x18006ee85  test    byte ptr [r12], 1
0x18006ee8a  jz      short loc_18006EE9A
0x18006ee8c  mov     rcx, rbx; bstrString
0x18006ee8f  call    cs:__imp_SysFreeString
0x18006ee95  jmp     loc_18006EB82
0x18006ee9a  inc     rsi
0x18006ee9d  cmp     [r15+rsi*2], dx
0x18006eea2  jnz     short loc_18006EE9A
0x18006eea4  add     rsi, 18h
0x18006eea8  lea     rdx, [rsi+rsi]; uBytes
0x18006eeac  mov     ecx, 40h ; '@'; uFlags
  ... truncated ...
```
