# RRasConfigStore::InitializeConfigStore(HKEY__ *)

- ea: `0x180049728`
- end: `0x180049cdf`
- name: `?InitializeConfigStore@RRasConfigStore@@QEAAKPEAUHKEY__@@@Z`
- size: `1463`
- prototype: `__int64 __fastcall(RRasConfigStore *this, HKEY)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180041c8c`

## callees

- `0x180002718`
- `0x180030498`
- `0x180043e78`
- `0x1800442f8`
- `0x180044384`
- `0x180049728`
- `0x180049f28`
- `0x18004b3ac`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180049918`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800498f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049902`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800498f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049902`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180049a3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180049a3a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180049aae`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180049aae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800499c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800499c6`
- `ntdll!RtlGUIDFromString` at `0x180049b3c`
- `ntdll!RtlGUIDFromString` at `0x180049b3c`
- `ntdll!RtlReleaseResource` at `0x1800498e2`
- `ntdll!RtlReleaseResource` at `0x1800498e2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800497fc`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800497fc`

## string_xrefs

- `0x180049864`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18004988f`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x1800497cb`: `RRasConfigStore::InitializeConfigStore`
- `0x180049819`: `%s:Already initialized.`
- `0x180049896`: `%s:RegOpenKeyEx (%s) failed: %d.`
- `0x1800499b5`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180049ad4`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x1800499e6`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x180049ae3`: `%s: Error %d occured while enumerating subkeys under  registry key %s.`
- `0x180049ca3`: `%s: Failed to instantiate a Routing Domain config object.`
- `0x180049c7d`: `%s: OpenConfigRegKey failed: %d.`
- `0x180049c01`: `%s: rdConfig->PopulateFromRegistry failed for (%ws): %d.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::InitializeConfigStore(RRasConfigStore *this, HKEY a2)
{
  RRasRoutingDomainConfig *v4; // rbx
  void (*v5)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v6; // edi
  LSTATUS v7; // eax
  unsigned int v8; // ecx
  const WCHAR *v9; // r9
  const wchar_t *v10; // rdx
  unsigned int v11; // ebx
  DWORD v13; // r14d
  unsigned int v14; // eax
  RRasRoutingDomainConfig *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v23; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-7Ch] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+C0h] [rbp-40h]
  int v33; // [rsp+C8h] [rbp-38h]
  int v34; // [rsp+CCh] [rbp-34h]
  RRasRoutingDomainConfig *v35; // [rsp+D0h] [rbp-30h]
  struct _GUID v36; // [rsp+E0h] [rbp-20h] BYREF
  GUID Guid; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Name[40]; // [rsp+100h] [rbp+0h] BYREF
  int v39; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v40[2044]; // [rsp+154h] [rbp+54h] BYREF

  v20 = 0;
  hKey = 0;
  v23 = 0;
  memset_0(Name, 0, sizeof(Name));
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  v4 = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v33 = -1;
  v34 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v29,
      L"RRasConfigStore::InitializeConfigStore",
      &v20,
      v5);
  *((_QWORD *)this + 1) = a2;
  v6 = 1;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
  if ( *((_DWORD *)this + 26) )
  {
    if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"%s:Already initialized.", L"RRasConfigStore::InitializeConfigStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180078C50 + 1),
        &v39);
    }
    goto LABEL_6;
  }
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
         0,
         0x20019u,
         &hKey);
  v8 = v7;
  v20 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_12;
    v9 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters";
    v10 = L"%s:RegOpenKeyEx (%s) failed: %d.";
LABEL_10:
    LOWORD(v39) = 0;
    LODWORD(phkResult) = v7;
    FormatRRASErrorString(&v39, v10, L"RRasConfigStore::InitializeConfigStore", v9, phkResult);
    goto LABEL_11;
  }
  RegGetDword(hKey, L"ModernStackEnabled", 0, 1, 0, (char *)this + 4);
  RegGetDword(hKey, L"MultiTenancyEnabled", 0, 1, 0, this);
  if ( !*(_DWORD *)this )
  {
LABEL_6:
    v20 = 0;
    goto LABEL_14;
  }
  *((_DWORD *)this + 1) = 1;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
         0,
         0xF003Fu,
         &v23);
  v8 = v7;
  v20 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_12;
    v9 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains";
    v10 = L"%s: RegOpenKeyEx (%s) failed: %d.";
    goto LABEL_10;
  }
  v7 = RegQueryInfoKeyW(v23, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v8 = v7;
  v20 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_12;
    v9 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains";
    v10 = L"%s: RegQueryInfoKey (%s) failed: %d.";
    goto LABEL_10;
  }
  v13 = 0;
  if ( !cSubKeys )
    goto LABEL_12;
  while ( 1 )
  {
    cchName = 40;
    memset_0(Name, 0, sizeof(Name));
    v14 = RegEnumKeyExW(v23, v13, Name, &cchName, 0, 0, 0, 0);
    v20 = v14;
    if ( !v14 || v14 == 234 )
      break;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(
        &v39,
        L"%s: Error %d occured while enumerating subkeys under  registry key %s.",
        L"RRasConfigStore::InitializeConfigStore",
        v14,
        L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains");
LABEL_33:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v39);
    }
LABEL_34:
    v8 = 0;
    v20 = 0;
LABEL_48:
    v4 = 0;
    if ( ++v13 >= cSubKeys )
      goto LABEL_12;
  }
  Guid = 0;
  *(_QWORD *)&GuidString.Length = 5242960;
  GuidString.Buffer = Name;
  if ( RtlGUIDFromString(&GuidString, &Guid) )
  {
    v20 = 87;
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_34;
    LOWORD(v39) = 0;
    LODWORD(phkResulta) = 87;
    FormatRRASErrorString(
      &v39,
      L"%s: MprConvertStringToGuid failed for (%ws): %d.",
      L"RRasConfigStore::InitializeConfigStore",
      Name,
      phkResulta);
    goto LABEL_33;
  }
  v20 = 0;
  v15 = (RRasRoutingDomainConfig *)operator new(0x358u);
  v35 = v15;
  if ( v15 )
  {
    v36 = Guid;
    v4 = RRasRoutingDomainConfig::RRasRoutingDomainConfig(v15, *((HKEY *)this + 1), &v36);
  }
  else
  {
    v4 = 0;
  }
  if ( !v4 )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(
        &v39,
        L"%s: Failed to instantiate a Routing Domain config object.",
        L"RRasConfigStore::InitializeConfigStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v39);
    }
    v20 = 8;
    goto LABEL_13;
  }
  v16 = RRasRoutingDomainConfig::OpenConfigRegKey(v4);
  v8 = v16;
  v20 = v16;
  if ( !v16 )
  {
    v17 = RRasRoutingDomainConfig::PopulateFromRegistry(v4);
    v20 = v17;
    if ( v17 )
    {
      if ( (_QWORD)xmmword_180078C50 )
      {
        LOWORD(v39) = 0;
        LODWORD(phkResulta) = v17;
        FormatRRASErrorString(
          &v39,
          L"%s: rdConfig->PopulateFromRegistry failed for (%ws): %d.",
          L"RRasConfigStore::InitializeConfigStore",
          Name,
          phkResulta);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C50,
          &v39);
      }
      v20 = 0;
    }
    *((_DWORD *)v4 + 133) |= 2u;
    *(_QWORD *)std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::operator[](
                 (__int64)this + 16,
                 (__int128 *)&Guid) = v4;
    v8 = v20;
    goto LABEL_48;
  }
  if ( !(_QWORD)xmmword_180078C50 )
    goto LABEL_12;
  LOWORD(v39) = 0;
  FormatRRASErrorString(&v39, L"%s: OpenConfigRegKey failed: %d.", L"RRasConfigStore::InitializeConfigStore", v16);
LABEL_11:
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C50,
    &v39);
  v8 = v20;
LABEL_12:
  if ( v8 )
LABEL_13:
    v6 = 0;
LABEL_14:
  *((_DWORD *)this + 26) = v6;
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  if ( hKey )
    RegCloseKey(hKey);
  if ( v23 )
    RegCloseKey(v23);
  if ( v4 )
  {
    RRasRoutingDomainConfig::~RRasRoutingDomainConfig(v4);
    operator delete(v4);
  }
  v11 = v20;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v29);
  return v11;
}

```

## disassembly

```asm
0x180049728  push    rbp
0x18004972a  push    rbx
0x18004972b  push    rsi
0x18004972c  push    rdi
0x18004972d  push    r12
0x18004972f  push    r13
0x180049731  push    r14
0x180049733  push    r15
0x180049735  lea     rbp, [rsp-868h]
0x18004973d  sub     rsp, 968h
0x180049744  mov     rax, cs:__security_cookie
0x18004974b  xor     rax, rsp
0x18004974e  mov     [rbp+8A0h+var_50], rax
0x180049755  mov     rdi, rdx
0x180049758  mov     rsi, rcx
0x18004975b  xor     r12d, r12d
0x18004975e  mov     [rsp+9A0h+var_940], r12d
0x180049763  mov     [rsp+9A0h+hKey], r12
0x180049768  mov     [rsp+9A0h+var_930], r12
0x18004976d  xor     edx, edx; Val
0x18004976f  lea     r8d, [r12+50h]; Size
0x180049774  lea     rcx, [rbp+8A0h+Name]; void *
0x180049778  call    memset_0
0x18004977d  mov     [rsp+9A0h+cbMaxValueNameLen], r12d
0x180049782  mov     [rbp+8A0h+cValues], r12d
0x180049786  mov     [rsp+9A0h+cbMaxValueLen], r12d
0x18004978b  mov     [rsp+9A0h+cSubKeys], r12d
0x180049790  mov     ebx, r12d
0x180049793  mov     [rbp+8A0h+var_850], r12d
0x180049797  xor     edx, edx; Val
0x180049799  mov     r8d, 7FCh; Size
0x18004979f  lea     rcx, [rbp+8A0h+var_84C]; void *
0x1800497a3  call    memset_0
0x1800497a8  xorps   xmm0, xmm0
0x1800497ab  movdqu  [rbp+8A0h+var_900], xmm0
0x1800497b0  mov     [rbp+8A0h+var_908], r12
0x1800497b4  xorps   xmm1, xmm1
0x1800497b7  movdqu  [rbp+8A0h+var_8F0], xmm1
0x1800497bc  mov     [rbp+8A0h+var_8E0], r12
0x1800497c0  mov     [rbp+8A0h+var_8D8], 0FFFFFFFFh
0x1800497c7  mov     [rbp+8A0h+var_8D4], r12d
0x1800497cb  lea     r13, aRrasconfigstor_24; "RRasConfigStore::InitializeConfigStore"
0x1800497d2  cmp     qword ptr cs:xmmword_180078C50+8, r12
0x1800497d9  jz      short loc_1800497EC
0x1800497db  lea     r8, [rsp+9A0h+var_940]; unsigned int *
0x1800497e0  mov     rdx, r13; unsigned __int16 *
0x1800497e3  lea     rcx, [rbp+8A0h+var_908]; this
0x1800497e7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800497ec  mov     [rsi+8], rdi
0x1800497f0  mov     edi, 1
0x1800497f5  mov     dl, dil; Wait
0x1800497f8  lea     rcx, [rsi+70h]; Resource
0x1800497fc  call    cs:__imp_RtlAcquireResourceExclusive
0x180049802  cmp     [rsi+68h], r12d
0x180049806  jz      short loc_180049851
0x180049808  cmp     qword ptr cs:xmmword_180078C50+8, r12
0x18004980f  jz      short loc_180049847
0x180049811  mov     word ptr [rbp+8A0h+var_850], r12w
0x180049816  mov     r8, r13
0x180049819  lea     rdx, aSAlreadyInitia; "%s:Already initialized."
0x180049820  lea     rcx, [rbp+8A0h+var_850]
0x180049824  call    FormatRRASErrorString
0x180049829  lea     r8, [rbp+8A0h+var_850]
0x18004982d  mov     rdx, qword ptr cs:xmmword_180078C50+8
0x180049834  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004983b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180049842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049847  mov     [rsp+9A0h+var_940], r12d
0x18004984c  jmp     loc_1800498DB
0x180049851  lea     rax, [rsp+9A0h+hKey]
0x180049856  mov     [rsp+9A0h+phkResult], rax; phkResult
0x18004985b  mov     r9d, 20019h; samDesired
0x180049861  xor     r8d, r8d; ulOptions
0x180049864  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Re"...
0x18004986b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049872  call    cs:__imp_RegOpenKeyExW
0x180049878  mov     ecx, eax
0x18004987a  mov     [rsp+9A0h+var_940], eax
0x18004987e  test    eax, eax
0x180049880  jz      loc_180049950
0x180049886  cmp     qword ptr cs:xmmword_180078C50, r12
0x18004988d  jz      short loc_1800498D4
0x18004988f  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Re"...
0x180049896  lea     rdx, aSRegopenkeyexS; "%s:RegOpenKeyEx (%s) failed: %d."
0x18004989d  mov     word ptr [rbp+8A0h+var_850], r12w
0x1800498a2  mov     dword ptr [rsp+9A0h+phkResult], eax
0x1800498a6  mov     r8, r13
0x1800498a9  lea     rcx, [rbp+8A0h+var_850]
0x1800498ad  call    FormatRRASErrorString
0x1800498b2  lea     r8, [rbp+8A0h+var_850]
0x1800498b6  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800498bd  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800498c4  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800498cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498d0  mov     ecx, [rsp+9A0h+var_940]
0x1800498d4  test    ecx, ecx
0x1800498d6  jz      short loc_1800498DB
0x1800498d8  mov     edi, r12d
0x1800498db  mov     [rsi+68h], edi
0x1800498de  lea     rcx, [rsi+70h]; Resource
0x1800498e2  call    cs:__imp_RtlReleaseResource
0x1800498e8  mov     rcx, [rsp+9A0h+hKey]; hKey
0x1800498ed  test    rcx, rcx
0x1800498f0  jz      short loc_1800498F8
0x1800498f2  call    cs:__imp_RegCloseKey
0x1800498f8  mov     rcx, [rsp+9A0h+var_930]; hKey
0x1800498fd  test    rcx, rcx
0x180049900  jz      short loc_180049908
0x180049902  call    cs:__imp_RegCloseKey
0x180049908  test    rbx, rbx
0x18004990b  jz      short loc_18004991E
0x18004990d  mov     rcx, rbx; this
0x180049910  call    ??1RRasRoutingDomainConfig@@QEAA@XZ; RRasRoutingDomainConfig::~RRasRoutingDomainConfig(void)
0x180049915  mov     rcx, rbx
0x180049918  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004991e  mov     ebx, [rsp+9A0h+var_940]
0x180049922  lea     rcx, [rbp+8A0h+var_908]; this
0x180049926  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004992b  mov     eax, ebx
0x18004992d  mov     rcx, [rbp+8A0h+var_50]
0x180049934  xor     rcx, rsp; StackCookie
0x180049937  call    __security_check_cookie
0x18004993c  add     rsp, 968h
0x180049943  pop     r15
0x180049945  pop     r14
0x180049947  pop     r13
0x180049949  pop     r12
0x18004994b  pop     rdi
0x18004994c  pop     rsi
0x18004994d  pop     rbx
0x18004994e  pop     rbp
0x18004994f  retn
0x180049950  lea     r14, [rsi+4]
0x180049954  mov     [rsp+9A0h+lpcbMaxSubKeyLen], r14
0x180049959  mov     dword ptr [rsp+9A0h+phkResult], r12d
0x18004995e  mov     r9d, edi
0x180049961  xor     r8d, r8d
0x180049964  lea     rdx, aModernstackena; "ModernStackEnabled"
0x18004996b  mov     rcx, [rsp+9A0h+hKey]
0x180049970  call    RegGetDword
0x180049975  mov     [rsp+9A0h+lpcbMaxSubKeyLen], rsi
0x18004997a  mov     dword ptr [rsp+9A0h+phkResult], r12d
0x18004997f  mov     r9d, edi
0x180049982  xor     r8d, r8d
0x180049985  lea     rdx, aMultitenancyen; "MultiTenancyEnabled"
0x18004998c  mov     rcx, [rsp+9A0h+hKey]
0x180049991  call    RegGetDword
0x180049996  cmp     [rsi], r12d
0x180049999  jz      loc_180049847
0x18004999f  mov     [r14], edi
0x1800499a2  lea     rax, [rsp+9A0h+var_930]
0x1800499a7  mov     [rsp+9A0h+phkResult], rax; phkResult
0x1800499ac  mov     r9d, 0F003Fh; samDesired
0x1800499b2  xor     r8d, r8d; ulOptions
0x1800499b5  lea     r14, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x1800499bc  mov     rdx, r14; lpSubKey
0x1800499bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800499c6  call    cs:__imp_RegOpenKeyExW
0x1800499cc  mov     ecx, eax
0x1800499ce  mov     [rsp+9A0h+var_940], eax
0x1800499d2  test    eax, eax
0x1800499d4  jz      short loc_1800499F2
0x1800499d6  cmp     qword ptr cs:xmmword_180078C50, r12
0x1800499dd  jz      loc_1800498D4
0x1800499e3  mov     r9, r14
0x1800499e6  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x1800499ed  jmp     loc_18004989D
0x1800499f2  mov     [rsp+9A0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800499f7  mov     [rsp+9A0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800499fc  lea     rax, [rsp+9A0h+cbMaxValueLen]
0x180049a01  mov     [rsp+9A0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180049a06  lea     rax, [rsp+9A0h+cbMaxValueNameLen]
0x180049a0b  mov     [rsp+9A0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180049a10  lea     rax, [rbp+8A0h+cValues]
0x180049a14  mov     [rsp+9A0h+lpcValues], rax; lpcValues
0x180049a19  mov     [rsp+9A0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180049a1e  mov     [rsp+9A0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180049a23  lea     rax, [rsp+9A0h+cSubKeys]
0x180049a28  mov     [rsp+9A0h+phkResult], rax; lpcSubKeys
0x180049a2d  xor     r9d, r9d; lpReserved
0x180049a30  xor     r8d, r8d; lpcchClass
0x180049a33  xor     edx, edx; lpClass
0x180049a35  mov     rcx, [rsp+9A0h+var_930]; hKey
0x180049a3a  call    cs:__imp_RegQueryInfoKeyW
0x180049a40  mov     ecx, eax
0x180049a42  mov     [rsp+9A0h+var_940], eax
0x180049a46  test    eax, eax
0x180049a48  jz      short loc_180049A66
0x180049a4a  cmp     qword ptr cs:xmmword_180078C50, r12
0x180049a51  jz      loc_1800498D4
0x180049a57  mov     r9, r14
0x180049a5a  lea     rdx, aSRegqueryinfok; "%s: RegQueryInfoKey (%s) failed: %d."
0x180049a61  jmp     loc_18004989D
0x180049a66  mov     r14d, r12d
0x180049a69  cmp     [rsp+9A0h+cSubKeys], r12d
0x180049a6e  jbe     loc_1800498D4
0x180049a74  mov     [rbp+8A0h+cchName], 28h ; '('
0x180049a7b  xor     edx, edx; Val
0x180049a7d  lea     r8d, [rdx+50h]; Size
0x180049a81  lea     rcx, [rbp+8A0h+Name]; void *
0x180049a85  call    memset_0
0x180049a8a  mov     [rsp+9A0h+lpcValues], r12; lpftLastWriteTime
0x180049a8f  mov     [rsp+9A0h+lpcbMaxClassLen], r12; lpcchClass
0x180049a94  mov     [rsp+9A0h+lpcbMaxSubKeyLen], r12; lpClass
0x180049a99  mov     [rsp+9A0h+phkResult], r12; lpReserved
0x180049a9e  lea     r9, [rbp+8A0h+cchName]; lpcchName
0x180049aa2  lea     r8, [rbp+8A0h+Name]; lpName
0x180049aa6  mov     edx, r14d; dwIndex
0x180049aa9  mov     rcx, [rsp+9A0h+var_930]; hKey
0x180049aae  call    cs:__imp_RegEnumKeyExW
0x180049ab4  mov     r9d, eax
0x180049ab7  mov     [rsp+9A0h+var_940], eax
0x180049abb  test    eax, eax
0x180049abd  jz      short loc_180049B1D
0x180049abf  cmp     eax, 0EAh
0x180049ac4  jz      short loc_180049B1D
0x180049ac6  cmp     qword ptr cs:xmmword_180078C50, r12
0x180049acd  jz      short loc_180049B11
0x180049acf  mov     word ptr [rbp+8A0h+var_850], r12w
0x180049ad4  lea     rax, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x180049adb  mov     [rsp+9A0h+phkResult], rax
0x180049ae0  mov     r8, r13
0x180049ae3  lea     rdx, aSErrorDOccured; "%s: Error %d occured while enumerating "...
0x180049aea  lea     rcx, [rbp+8A0h+var_850]
0x180049aee  call    FormatRRASErrorString
0x180049af3  lea     r8, [rbp+8A0h+var_850]
0x180049af7  mov     rdx, qword ptr cs:xmmword_180078C50
0x180049afe  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180049b05  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180049b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b11  mov     ecx, r12d
0x180049b14  mov     [rsp+9A0h+var_940], ecx
0x180049b18  jmp     loc_180049C4F
0x180049b1d  xorps   xmm0, xmm0
0x180049b20  movups  xmmword ptr [rbp+8A0h+Guid.Data1], xmm0
0x180049b24  mov     qword ptr [rbp+8A0h+GuidString.Length], 500050h
0x180049b2c  lea     rax, [rbp+8A0h+Name]
0x180049b30  mov     [rbp+8A0h+GuidString.Buffer], rax
0x180049b34  lea     rdx, [rbp+8A0h+Guid]; Guid
0x180049b38  lea     rcx, [rbp+8A0h+GuidString]; GuidString
0x180049b3c  call    cs:__imp_RtlGUIDFromString
0x180049b42  test    eax, eax
0x180049b44  jz      short loc_180049B80
0x180049b46  mov     [rsp+9A0h+var_940], 57h ; 'W'
0x180049b4e  cmp     qword ptr cs:xmmword_180078C50, r12
0x180049b55  jz      short loc_180049B11
0x180049b57  mov     word ptr [rbp+8A0h+var_850], r12w
0x180049b5c  mov     dword ptr [rsp+9A0h+phkResult], 57h ; 'W'
0x180049b64  lea     r9, [rbp+8A0h+Name]
0x180049b68  mov     r8, r13
0x180049b6b  lea     rdx, aSMprconvertstr; "%s: MprConvertStringToGuid failed for ("...
0x180049b72  lea     rcx, [rbp+8A0h+var_850]
0x180049b76  call    FormatRRASErrorString
0x180049b7b  jmp     loc_180049AF3
0x180049b80  mov     [rsp+9A0h+var_940], r12d
0x180049b85  mov     ecx, 358h; Size
0x180049b8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049b8f  mov     [rbp+8A0h+var_8D0], rax
0x180049b93  test    rax, rax
0x180049b96  jz      short loc_180049BB6
0x180049b98  movaps  xmm0, xmmword ptr [rbp+8A0h+Guid.Data1]
0x180049b9c  movdqa  xmmword ptr [rbp+8A0h+var_8C0.Data1], xmm0
0x180049ba1  lea     r8, [rbp+8A0h+var_8C0]; struct _GUID
0x180049ba5  mov     rdx, [rsi+8]; HKEY
0x180049ba9  mov     rcx, rax; this
0x180049bac  call    ??0RRasRoutingDomainConfig@@QEAA@PEAUHKEY__@@U_GUID@@@Z; RRasRoutingDomainConfig::RRasRoutingDomainConfig(HKEY__ *,_GUID)
0x180049bb1  mov     rbx, rax
0x180049bb4  jmp     short loc_180049BB9
0x180049bb6  mov     rbx, r12
0x180049bb9  test    rbx, rbx
0x180049bbc  jz      loc_180049C92
0x180049bc2  mov     rcx, rbx; this
0x180049bc5  call    ?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::OpenConfigRegKey(void)
0x180049bca  mov     ecx, eax
0x180049bcc  mov     [rsp+9A0h+var_940], eax
0x180049bd0  test    eax, eax
0x180049bd2  jnz     loc_180049C65
0x180049bd8  mov     rcx, rbx; this
0x180049bdb  call    ?PopulateFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::PopulateFromRegistry(void)
0x180049be0  mov     [rsp+9A0h+var_940], eax
0x180049be4  test    eax, eax
0x180049be6  jz      short loc_180049C34
0x180049be8  cmp     qword ptr cs:xmmword_180078C50, r12
0x180049bef  jz      short loc_180049C2F
0x180049bf1  mov     word ptr [rbp+8A0h+var_850], r12w
0x180049bf6  mov     dword ptr [rsp+9A0h+phkResult], eax
0x180049bfa  lea     r9, [rbp+8A0h+Name]
0x180049bfe  mov     r8, r13
0x180049c01  lea     rdx, aSRdconfigPopul; "%s: rdConfig->PopulateFromRegistry fail"...
0x180049c08  lea     rcx, [rbp+8A0h+var_850]
0x180049c0c  call    FormatRRASErrorString
0x180049c11  lea     r8, [rbp+8A0h+var_850]
0x180049c15  mov     rdx, qword ptr cs:xmmword_180078C50
0x180049c1c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180049c23  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180049c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c2f  mov     [rsp+9A0h+var_940], r12d
0x180049c34  or      dword ptr [rbx+214h], 2
0x180049c3b  lea     rcx, [rsi+10h]
0x180049c3f  lea     rdx, [rbp+8A0h+Guid]
  ... truncated ...
```
