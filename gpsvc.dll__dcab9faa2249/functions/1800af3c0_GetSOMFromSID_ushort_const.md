# GetSOMFromSID(ushort const *)

- ea: `0x1800af3c0`
- end: `0x1800af818`
- name: `?GetSOMFromSID@@YAPEAGPEBG@Z`
- size: `1112`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180071890`
- `0x1800ae920`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001ee6c`
- `0x180022bd4`
- `0x180072a08`
- `0x1800af3c0`
- `0x1800b30a0`
- `0x1800b6908`
- `0x1800b8f98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af4b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af7fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af4b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af7fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af46b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af46b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af784`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af431`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af5d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af431`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af5d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800af511`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800af511`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800af5a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800af62a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800af5a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800af62a`

## string_xrefs

- `0x1800af455`: `GetSOMFromSID: Failed to allocate memory. Error - %d`
- `0x1800af525`: `GetSOMFromSID: Failed to open state key for %s. Error - %d`
- `0x1800af5b1`: `GetSOMFromSID: Failed to get the size of DN value. Error - %d`
- `0x1800af637`: `GetSOMFromSID: Failed to get the size of DN value. Error - %d`
- `0x1800af6ab`: `GetSOMFromSID: Som for SID <%s> in registry is %s.`
- `0x1800af6d6`: `GetSOMFromSID: Cannot get the domain from the som path. Error - %d`
- `0x1800af71a`: `GetSOMFromSID: Couldn't get the machine account. Error - %d`
- `0x1800af75c`: `GetSOMFromSID: Translate name failed for machine account. Error - %d`
- `0x1800af78a`: `GetSOMFromSID: Translate name failed for user account. Error - %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned __int16 *__fastcall GetSOMFromSID(const unsigned __int16 *a1)
{
  DWORD LastError; // edi
  const wchar_t *v3; // r15
  __int64 v4; // rax
  unsigned __int64 v5; // r14
  HLOCAL v6; // rax
  const WCHAR *v7; // rbx
  DWORD v8; // eax
  DWORD v9; // ebx
  DWORD v10; // ecx
  int v12; // r12d
  const wchar_t *v13; // r9
  int v14; // eax
  LSTATUS v15; // eax
  unsigned int Domain; // r14d
  unsigned int v17; // eax
  __int64 v18; // r9
  HLOCAL v19; // rax
  const WCHAR *v20; // rbx
  enum DS_NAME_FORMAT v21; // r9d
  unsigned __int16 *ComputerName; // rax
  enum DS_NAME_FORMAT v23; // r9d
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD v26; // eax
  unsigned __int16 *v27; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v29; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+48h] BYREF
  DWORD v35; // [rsp+B8h] [rbp+50h]
  DWORD Type; // [rsp+C0h] [rbp+58h] BYREF
  LPBYTE lpData; // [rsp+C8h] [rbp+60h] BYREF

  LastError = GetLastError();
  v35 = LastError;
  lpData = 0;
  v29 = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  lpSubKey[0] = 0;
  v32 = 0;
  v30 = 0;
  v3 = a1;
  if ( !a1 )
    v3 = L"Machine";
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  v5 = v4 + 65;
  v6 = LocalAlloc(0x40u, 2 * (v4 + 65));
  XPtrLF<unsigned short>::operator=((void **)lpSubKey, v6);
  v7 = lpSubKey[0];
  if ( !lpSubKey[0] )
  {
    v8 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"GetSOMFromSID: Failed to allocate memory. Error - %d", v8);
    v9 = GetLastError();
LABEL_7:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v30);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v32);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)lpSubKey);
    XKey::Free((XKey *)&hKey);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v29);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpData);
    v10 = v9;
LABEL_8:
    SetLastError(v10);
    return 0;
  }
  if ( a1 )
  {
    v12 = 0;
    v13 = a1;
  }
  else
  {
    v12 = 1;
    v13 = L"Machine";
  }
  v14 = StringCchPrintfW(
          (unsigned __int16 *)lpSubKey[0],
          v5,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\%ws",
          v13);
  if ( v14 < 0 )
  {
    v9 = (unsigned __int16)v14;
    goto LABEL_7;
  }
  cbData = 0;
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  Domain = v15;
  if ( v15 )
  {
    LODWORD(phkResult) = v15;
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      2u,
      L"GetSOMFromSID: Failed to open state key for %s. Error - %d",
      v7,
      phkResult);
LABEL_16:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v30);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v32);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)lpSubKey);
    XKey::Free((XKey *)&hKey);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v29);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpData);
    v10 = Domain;
    goto LABEL_8;
  }
  v17 = RegQueryValueExW(hKey, L"Distinguished-Name", 0, &Type, 0, &cbData);
  v9 = v17;
  if ( v17 )
  {
    v18 = v17;
LABEL_19:
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      2u,
      L"GetSOMFromSID: Failed to get the size of DN value. Error - %d",
      v18);
    goto LABEL_7;
  }
  v19 = LocalAlloc(0x40u, cbData + 2);
  XPtrLF<unsigned short>::operator=((void **)&lpData, v19);
  v20 = (const WCHAR *)lpData;
  if ( !lpData )
  {
    v9 = GetLastError();
    v35 = v9;
    v18 = GetLastError();
    goto LABEL_19;
  }
  Domain = RegQueryValueExW(hKey, L"Distinguished-Name", 0, &Type, lpData, &cbData);
  if ( Domain )
  {
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      2u,
      L"GetSOMFromSID: Failed to get the size of DN value. Error - %d",
      Domain);
    goto LABEL_16;
  }
  if ( !*v20 )
  {
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v30);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v32);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)lpSubKey);
    XKey::Free((XKey *)&hKey);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v29);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpData);
    v10 = 1258;
    goto LABEL_8;
  }
  CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"GetSOMFromSID: Som for SID <%s> in registry is %s.", v3, v20);
  Domain = GetDomain(v20);
  if ( Domain )
  {
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      2u,
      L"GetSOMFromSID: Cannot get the domain from the som path. Error - %d",
      Domain);
    goto LABEL_16;
  }
  if ( !v12 )
  {
    if ( !TranslateNameXForest(v30, a1, DS_SID_OR_SID_HISTORY_NAME, v21, &v29) )
    {
      v26 = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"GetSOMFromSID: Translate name failed for user account. Error - %d",
        v26);
      goto LABEL_38;
    }
    goto LABEL_37;
  }
  ComputerName = MyGetComputerName(NameSamCompatible);
  XPtrLF<unsigned short>::operator=((void **)&v32, ComputerName);
  if ( v32 )
  {
    if ( !TranslateNameXForest(v30, v32, DS_NT4_ACCOUNT_NAME, v23, &v29) )
    {
      v25 = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"GetSOMFromSID: Translate name failed for machine account. Error - %d",
        v25);
LABEL_38:
      lpData = 0;
      goto LABEL_39;
    }
LABEL_37:
    v27 = v29;
    v29 = 0;
    XPtrLF<unsigned short>::operator=((void **)&lpData, v27);
    v20 = (const WCHAR *)lpData;
    goto LABEL_38;
  }
  LastError = GetLastError();
  v35 = LastError;
  v24 = GetLastError();
  CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"GetSOMFromSID: Couldn't get the machine account. Error - %d", v24);
  v20 = 0;
LABEL_39:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v30);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v32);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)lpSubKey);
  XKey::Free((XKey *)&hKey);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v29);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpData);
  SetLastError(LastError);
  return (unsigned __int16 *)v20;
}

```

## disassembly

```asm
0x1800af3c0  push    rbp
0x1800af3c2  push    rbx
0x1800af3c3  push    rsi
0x1800af3c4  push    rdi
0x1800af3c5  push    r12
0x1800af3c7  push    r13
0x1800af3c9  push    r14
0x1800af3cb  push    r15
0x1800af3cd  mov     rbp, rsp
0x1800af3d0  sub     rsp, 68h
0x1800af3d4  mov     rsi, rcx
0x1800af3d7  call    cs:__imp_GetLastError
0x1800af3dd  mov     edi, eax
0x1800af3df  mov     [rbp+arg_8], eax
0x1800af3e2  xor     r13d, r13d
0x1800af3e5  mov     [rbp+lpData], r13
0x1800af3e9  mov     [rbp+var_38], r13
0x1800af3ed  mov     [rbp+Type], r13d
0x1800af3f1  mov     [rbp+cbData], r13d
0x1800af3f5  mov     [rbp+hKey], r13
0x1800af3f9  mov     [rbp+lpSubKey], r13
0x1800af3fd  mov     [rbp+var_20], r13
0x1800af401  mov     [rbp+var_30], r13
0x1800af405  lea     rax, aMachine; "Machine"
0x1800af40c  mov     r15, rsi
0x1800af40f  test    rsi, rsi
0x1800af412  cmovz   r15, rax
0x1800af416  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800af41a  inc     rax
0x1800af41d  cmp     [r15+rax*2], r13w
0x1800af422  jnz     short loc_1800AF41A
0x1800af424  lea     r14, [rax+41h]
0x1800af428  lea     rdx, [r14+r14]; uBytes
0x1800af42c  mov     ecx, 40h ; '@'; uFlags
0x1800af431  call    cs:__imp_LocalAlloc
0x1800af437  mov     rdx, rax
0x1800af43a  lea     rcx, [rbp+lpSubKey]
0x1800af43e  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800af443  mov     rbx, [rbp+lpSubKey]
0x1800af447  test    rbx, rbx
0x1800af44a  jnz     short loc_1800AF4BE
0x1800af44c  call    cs:__imp_GetLastError
0x1800af452  mov     r9d, eax
0x1800af455  lea     r8, aGetsomfromsidF_1; "GetSOMFromSID: Failed to allocate memor"...
0x1800af45c  lea     edx, [rbx+2]; unsigned int
0x1800af45f  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af466  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af46b  call    cs:__imp_GetLastError
0x1800af471  mov     ebx, eax
0x1800af473  lea     rcx, [rbp+var_30]
0x1800af477  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af47c  nop
0x1800af47d  lea     rcx, [rbp+var_20]
0x1800af481  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af486  nop
0x1800af487  lea     rcx, [rbp+lpSubKey]
0x1800af48b  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af490  nop
0x1800af491  lea     rcx, [rbp+hKey]; this
0x1800af495  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x1800af49a  nop
0x1800af49b  lea     rcx, [rbp+var_38]
0x1800af49f  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af4a4  nop
0x1800af4a5  lea     rcx, [rbp+lpData]
0x1800af4a9  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af4ae  nop
0x1800af4af  mov     ecx, ebx; dwErrCode
0x1800af4b1  call    cs:__imp_SetLastError
0x1800af4b7  xor     eax, eax
0x1800af4b9  jmp     loc_1800AF807
0x1800af4be  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800af4c5  mov     rdx, r14; unsigned __int64
0x1800af4c8  mov     rcx, rbx; unsigned __int16 *
0x1800af4cb  test    rsi, rsi
0x1800af4ce  jnz     short loc_1800AF4DD
0x1800af4d0  lea     r12d, [rsi+1]
0x1800af4d4  lea     r9, aMachine; "Machine"
0x1800af4db  jmp     short loc_1800AF4E3
0x1800af4dd  mov     r12d, r13d
0x1800af4e0  mov     r9, rsi
0x1800af4e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800af4e8  test    eax, eax
0x1800af4ea  jns     short loc_1800AF4F1
0x1800af4ec  movzx   ebx, ax
0x1800af4ef  jmp     short loc_1800AF473
0x1800af4f1  mov     [rbp+cbData], r13d
0x1800af4f5  lea     rax, [rbp+hKey]
0x1800af4f9  mov     [rsp+68h+phkResult], rax; phkResult
0x1800af4fe  mov     r9d, 20019h; samDesired
0x1800af504  xor     r8d, r8d; ulOptions
0x1800af507  mov     rdx, rbx; lpSubKey
0x1800af50a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800af511  call    cs:__imp_RegOpenKeyExW
0x1800af517  mov     r14d, eax
0x1800af51a  test    eax, eax
0x1800af51c  jz      short loc_1800AF582
0x1800af51e  mov     dword ptr [rsp+68h+phkResult], eax
0x1800af522  mov     r9, rbx
0x1800af525  lea     r8, aGetsomfromsidF_0; "GetSOMFromSID: Failed to open state key"...
0x1800af52c  mov     edx, 2; unsigned int
0x1800af531  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af538  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af53d  nop
0x1800af53e  lea     rcx, [rbp+var_30]
0x1800af542  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af547  nop
0x1800af548  lea     rcx, [rbp+var_20]
0x1800af54c  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af551  nop
0x1800af552  lea     rcx, [rbp+lpSubKey]
0x1800af556  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af55b  nop
0x1800af55c  lea     rcx, [rbp+hKey]; this
0x1800af560  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x1800af565  nop
0x1800af566  lea     rcx, [rbp+var_38]
0x1800af56a  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af56f  nop
0x1800af570  lea     rcx, [rbp+lpData]
0x1800af574  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af579  nop
0x1800af57a  mov     ecx, r14d
0x1800af57d  jmp     loc_1800AF4B1
0x1800af582  lea     rax, [rbp+cbData]
0x1800af586  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800af58b  mov     [rsp+68h+phkResult], r13; lpData
0x1800af590  lea     r9, [rbp+Type]; lpType
0x1800af594  xor     r8d, r8d; lpReserved
0x1800af597  lea     rdx, aDistinguishedN; "Distinguished-Name"
0x1800af59e  mov     rcx, [rbp+hKey]; hKey
0x1800af5a2  call    cs:__imp_RegQueryValueExW
0x1800af5a8  mov     ebx, eax
0x1800af5aa  test    eax, eax
0x1800af5ac  jz      short loc_1800AF5CE
0x1800af5ae  mov     r9d, eax
0x1800af5b1  lea     r8, aGetsomfromsidF; "GetSOMFromSID: Failed to get the size o"...
0x1800af5b8  mov     edx, 2; unsigned int
0x1800af5bd  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af5c4  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af5c9  jmp     loc_1800AF473
0x1800af5ce  mov     edx, [rbp+cbData]
0x1800af5d1  add     edx, 2; uBytes
0x1800af5d4  mov     ecx, 40h ; '@'; uFlags
0x1800af5d9  call    cs:__imp_LocalAlloc
0x1800af5df  mov     rdx, rax
0x1800af5e2  lea     rcx, [rbp+lpData]
0x1800af5e6  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800af5eb  mov     rbx, [rbp+lpData]
0x1800af5ef  test    rbx, rbx
0x1800af5f2  jnz     short loc_1800AF60A
0x1800af5f4  call    cs:__imp_GetLastError
0x1800af5fa  mov     ebx, eax
0x1800af5fc  mov     [rbp+arg_8], eax
0x1800af5ff  call    cs:__imp_GetLastError
0x1800af605  mov     r9d, eax
0x1800af608  jmp     short loc_1800AF5B1
0x1800af60a  lea     rax, [rbp+cbData]
0x1800af60e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800af613  mov     [rsp+68h+phkResult], rbx; lpData
0x1800af618  lea     r9, [rbp+Type]; lpType
0x1800af61c  xor     r8d, r8d; lpReserved
0x1800af61f  lea     rdx, aDistinguishedN; "Distinguished-Name"
0x1800af626  mov     rcx, [rbp+hKey]; hKey
0x1800af62a  call    cs:__imp_RegQueryValueExW
0x1800af630  mov     r14d, eax
0x1800af633  test    eax, eax
0x1800af635  jz      short loc_1800AF657
0x1800af637  lea     r8, aGetsomfromsidF; "GetSOMFromSID: Failed to get the size o"...
0x1800af63e  mov     r9d, r14d
0x1800af641  mov     edx, 2; unsigned int
0x1800af646  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af64d  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af652  jmp     loc_1800AF53E
0x1800af657  cmp     [rbx], r13w
0x1800af65b  jnz     short loc_1800AF6A3
0x1800af65d  lea     rcx, [rbp+var_30]
0x1800af661  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af666  nop
0x1800af667  lea     rcx, [rbp+var_20]
0x1800af66b  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af670  nop
0x1800af671  lea     rcx, [rbp+lpSubKey]
0x1800af675  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af67a  nop
0x1800af67b  lea     rcx, [rbp+hKey]; this
0x1800af67f  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x1800af684  nop
0x1800af685  lea     rcx, [rbp+var_38]
0x1800af689  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af68e  nop
0x1800af68f  lea     rcx, [rbp+lpData]
0x1800af693  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af698  nop
0x1800af699  mov     ecx, 4EAh
0x1800af69e  jmp     loc_1800AF4B1
0x1800af6a3  mov     [rsp+68h+phkResult], rbx
0x1800af6a8  mov     r9, r15
0x1800af6ab  lea     r8, aGetsomfromsidS; "GetSOMFromSID: Som for SID <%s> in regi"...
0x1800af6b2  mov     edx, 4; unsigned int
0x1800af6b7  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af6be  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af6c3  lea     rdx, [rbp+var_30]
0x1800af6c7  mov     rcx, rbx; lpString1
0x1800af6ca  call    GetDomain
0x1800af6cf  mov     r14d, eax
0x1800af6d2  test    eax, eax
0x1800af6d4  jz      short loc_1800AF6E2
0x1800af6d6  lea     r8, aGetsomfromsidC_0; "GetSOMFromSID: Cannot get the domain fr"...
0x1800af6dd  jmp     loc_1800AF63E
0x1800af6e2  test    r12d, r12d
0x1800af6e5  jz      short loc_1800AF765
0x1800af6e7  mov     ecx, 2; NameFormat
0x1800af6ec  call    ?MyGetComputerName@@YAPEAGW4EXTENDED_NAME_FORMAT@@@Z; MyGetComputerName(EXTENDED_NAME_FORMAT)
0x1800af6f1  mov     rdx, rax
0x1800af6f4  lea     rcx, [rbp+var_20]
0x1800af6f8  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800af6fd  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x1800af701  test    rdx, rdx
0x1800af704  jnz     short loc_1800AF73A
0x1800af706  call    cs:__imp_GetLastError
0x1800af70c  mov     edi, eax
0x1800af70e  mov     [rbp+arg_8], eax
0x1800af711  call    cs:__imp_GetLastError
0x1800af717  mov     r9d, eax
0x1800af71a  lea     r8, aGetsomfromsidC; "GetSOMFromSID: Couldn't get the machine"...
0x1800af721  mov     edx, 2; unsigned int
0x1800af726  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af72d  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af732  mov     rbx, r13
0x1800af735  jmp     loc_1800AF7C0
0x1800af73a  lea     rax, [rbp+var_38]
0x1800af73e  mov     [rsp+68h+phkResult], rax; unsigned __int16 **
0x1800af743  mov     r8d, 2; enum DS_NAME_FORMAT
0x1800af749  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800af74d  call    ?TranslateNameXForest@@YAEPEBG0W4DS_NAME_FORMAT@@1PEAPEAG@Z; TranslateNameXForest(ushort const *,ushort const *,DS_NAME_FORMAT,DS_NAME_FORMAT,ushort * *)
0x1800af752  test    al, al
0x1800af754  jnz     short loc_1800AF7A7
0x1800af756  call    cs:__imp_GetLastError
0x1800af75c  lea     r8, aGetsomfromsidT; "GetSOMFromSID: Translate name failed fo"...
0x1800af763  jmp     short loc_1800AF791
0x1800af765  lea     rax, [rbp+var_38]
0x1800af769  mov     [rsp+68h+phkResult], rax; unsigned __int16 **
0x1800af76e  mov     r8d, 0Bh; enum DS_NAME_FORMAT
0x1800af774  mov     rdx, rsi; unsigned __int16 *
0x1800af777  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800af77b  call    ?TranslateNameXForest@@YAEPEBG0W4DS_NAME_FORMAT@@1PEAPEAG@Z; TranslateNameXForest(ushort const *,ushort const *,DS_NAME_FORMAT,DS_NAME_FORMAT,ushort * *)
0x1800af780  test    al, al
0x1800af782  jnz     short loc_1800AF7A7
0x1800af784  call    cs:__imp_GetLastError
0x1800af78a  lea     r8, aGetsomfromsidT_0; "GetSOMFromSID: Translate name failed fo"...
0x1800af791  mov     r9d, eax
0x1800af794  mov     edx, 2; unsigned int
0x1800af799  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800af7a0  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800af7a5  jmp     short loc_1800AF7BC
0x1800af7a7  mov     rdx, [rbp+var_38]
0x1800af7ab  mov     [rbp+var_38], r13
0x1800af7af  lea     rcx, [rbp+lpData]
0x1800af7b3  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800af7b8  mov     rbx, [rbp+lpData]
0x1800af7bc  mov     [rbp+lpData], r13
0x1800af7c0  lea     rcx, [rbp+var_30]
0x1800af7c4  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af7c9  nop
0x1800af7ca  lea     rcx, [rbp+var_20]
0x1800af7ce  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af7d3  nop
0x1800af7d4  lea     rcx, [rbp+lpSubKey]
0x1800af7d8  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af7dd  nop
0x1800af7de  lea     rcx, [rbp+hKey]; this
0x1800af7e2  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x1800af7e7  nop
0x1800af7e8  lea     rcx, [rbp+var_38]
0x1800af7ec  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af7f1  nop
0x1800af7f2  lea     rcx, [rbp+lpData]
0x1800af7f6  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800af7fb  nop
0x1800af7fc  mov     ecx, edi; dwErrCode
0x1800af7fe  call    cs:__imp_SetLastError
0x1800af804  mov     rax, rbx
0x1800af807  add     rsp, 68h
0x1800af80b  pop     r15
0x1800af80d  pop     r14
0x1800af80f  pop     r13
0x1800af811  pop     r12
0x1800af813  pop     rdi
0x1800af814  pop     rsi
0x1800af815  pop     rbx
0x1800af816  pop     rbp
0x1800af817  retn
```
