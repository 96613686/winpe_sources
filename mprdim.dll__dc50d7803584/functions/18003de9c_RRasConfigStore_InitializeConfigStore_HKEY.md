# RRasConfigStore::InitializeConfigStore(HKEY__ *)

- ea: `0x18003de9c`
- end: `0x18003e423`
- name: `?InitializeConfigStore@RRasConfigStore@@QEAAKPEAUHKEY__@@@Z`
- size: `1415`
- prototype: `unsigned int __fastcall(RRasConfigStore *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800360bc`

## callees

- `0x18000b604`
- `0x180033f28`
- `0x180034094`
- `0x180038828`
- `0x180038b00`
- `0x180038bc0`
- `0x18003de9c`
- `0x18003e984`
- `0x18003fde0`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003e056`
- `ntdll!RtlReleaseResource` at `0x18003e056`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003df74`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003df74`
- `ADVAPI32!RegOpenKeyExW` at `0x18003dfe6`
- `ADVAPI32!RegOpenKeyExW` at `0x18003e131`
- `ADVAPI32!RegOpenKeyExW` at `0x18003dfe6`
- `ADVAPI32!RegOpenKeyExW` at `0x18003e131`
- `ADVAPI32!RegCloseKey` at `0x18003e066`
- `ADVAPI32!RegCloseKey` at `0x18003e076`
- `ADVAPI32!RegCloseKey` at `0x18003e066`
- `ADVAPI32!RegCloseKey` at `0x18003e076`
- `ADVAPI32!RegEnumKeyExW` at `0x18003e21c`
- `ADVAPI32!RegEnumKeyExW` at `0x18003e21c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003e1a5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003e1a5`

## string_xrefs

- `0x18003e120`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18003e246`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18003dfdc`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18003e003`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18003df3c`: `RRasConfigStore::InitializeConfigStore`
- `0x18003df91`: `%s:Already initialized.`
- `0x18003e00a`: `%s:RegOpenKeyEx (%s) failed: %d.`
- `0x18003e151`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18003e255`: `%s: Error %d occured while enumerating subkeys under  registry key %s.`
- `0x18003e3e7`: `%s: Failed to instantiate a Routing Domain config object.`
- `0x18003e3c1`: `%s: OpenConfigRegKey failed: %d.`
- `0x18003e353`: `%s: rdConfig->PopulateFromRegistry failed for (%ws): %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RRasConfigStore::InitializeConfigStore(RRasConfigStore *this, HKEY a2)
{
  RRasRoutingDomainConfig *v3; // rbx
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v5; // edi
  LSTATUS v6; // eax
  unsigned int v7; // ecx
  const WCHAR *v8; // r9
  const wchar_t *v9; // rdx
  unsigned int v10; // ebx
  DWORD i; // r14d
  unsigned int v13; // eax
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
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  __int128 v29; // [rsp+90h] [rbp-70h]
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  int v32; // [rsp+B8h] [rbp-48h]
  int v33; // [rsp+BCh] [rbp-44h]
  RRasRoutingDomainConfig *v34; // [rsp+C0h] [rbp-40h]
  struct _GUID v35; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v36; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Name[40]; // [rsp+F0h] [rbp-10h] BYREF
  int v38; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v39[2044]; // [rsp+144h] [rbp+44h] BYREF

  v20 = 0;
  hKey = 0;
  v23 = 0;
  memset_0(Name, 0, sizeof(Name));
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  v3 = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v29 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v32 = -1;
  v33 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v28,
      L"RRasConfigStore::InitializeConfigStore",
      &v20,
      v4);
  *((_QWORD *)this + 1) = -2147483646;
  v5 = 1;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
  if ( *((_DWORD *)this + 26) )
  {
    if ( *((_QWORD *)&xmmword_180071090 + 1) )
    {
      LOWORD(v38) = 0;
      FormatRRASErrorString(&v38, L"%s:Already initialized.", L"RRasConfigStore::InitializeConfigStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180071090 + 1),
        &v38);
    }
    goto LABEL_6;
  }
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
         0,
         0x20019u,
         &hKey);
  v7 = v6;
  v20 = v6;
  if ( !v6 )
  {
    RegGetDword(hKey, L"ModernStackEnabled", 0, 1, 0, (char *)this + 4);
    RegGetDword(hKey, L"MultiTenancyEnabled", 0, 1, 0, this);
    if ( !*(_DWORD *)this )
    {
LABEL_6:
      v20 = 0;
      goto LABEL_14;
    }
    *((_DWORD *)this + 1) = 1;
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
           0,
           0xF003Fu,
           &v23);
    v7 = v6;
    v20 = v6;
    if ( v6 )
    {
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_12;
      v8 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains";
      v9 = L"%s: RegOpenKeyEx (%s) failed: %d.";
      goto LABEL_10;
    }
    v6 = RegQueryInfoKeyW(v23, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    v7 = v6;
    v20 = v6;
    if ( v6 )
    {
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_12;
      v8 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains";
      v9 = L"%s: RegQueryInfoKey (%s) failed: %d.";
LABEL_10:
      LOWORD(v38) = 0;
      LODWORD(phkResult) = v6;
      FormatRRASErrorString(&v38, v9, L"RRasConfigStore::InitializeConfigStore", v8, phkResult);
LABEL_11:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v38);
      v7 = v20;
      goto LABEL_12;
    }
    for ( i = 0; ; ++i )
    {
      v3 = 0;
      if ( i >= cSubKeys )
        goto LABEL_12;
      cchName = 40;
      memset_0(Name, 0, sizeof(Name));
      v13 = RegEnumKeyExW(v23, i, Name, &cchName, 0, 0, 0, 0);
      v20 = v13;
      if ( v13 )
      {
        if ( v13 != 234 )
          break;
      }
      v36 = 0;
      v14 = MprConvertStringToGuid(Name, 40, &v36, v13);
      v20 = v14;
      if ( v14 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v38) = 0;
          LODWORD(phkResulta) = v14;
          FormatRRASErrorString(
            &v38,
            L"%s: MprConvertStringToGuid failed for (%ws): %d.",
            L"RRasConfigStore::InitializeConfigStore",
            Name,
            phkResulta);
LABEL_37:
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v38);
        }
LABEL_38:
        v7 = 0;
        v20 = 0;
        continue;
      }
      v15 = (RRasRoutingDomainConfig *)operator new(0x358u);
      v34 = v15;
      if ( v15 )
      {
        v35 = v36;
        v3 = RRasRoutingDomainConfig::RRasRoutingDomainConfig(v15, *((HKEY *)this + 1), &v35);
      }
      else
      {
        v3 = 0;
      }
      if ( !v3 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v38) = 0;
          FormatRRASErrorString(
            &v38,
            L"%s: Failed to instantiate a Routing Domain config object.",
            L"RRasConfigStore::InitializeConfigStore");
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v38);
        }
        v20 = 8;
        goto LABEL_13;
      }
      v16 = RRasRoutingDomainConfig::OpenConfigRegKey(v3);
      v7 = v16;
      v20 = v16;
      if ( v16 )
      {
        if ( !(_QWORD)xmmword_180071090 )
          goto LABEL_12;
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, L"%s: OpenConfigRegKey failed: %d.", L"RRasConfigStore::InitializeConfigStore", v16);
        goto LABEL_11;
      }
      v17 = RRasRoutingDomainConfig::PopulateFromRegistry(v3);
      v20 = v17;
      if ( v17 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v38) = 0;
          LODWORD(phkResulta) = v17;
          FormatRRASErrorString(
            &v38,
            L"%s: rdConfig->PopulateFromRegistry failed for (%ws): %d.",
            L"RRasConfigStore::InitializeConfigStore",
            Name,
            phkResulta);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v38);
        }
        v20 = 0;
      }
      *((_DWORD *)v3 + 133) |= 2u;
      *(_QWORD *)std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::operator[](
                   (__int64)this + 16,
                   (__int128 *)&v36) = v3;
      v7 = v20;
    }
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v38) = 0;
      FormatRRASErrorString(
        &v38,
        L"%s: Error %d occured while enumerating subkeys under  registry key %s.",
        L"RRasConfigStore::InitializeConfigStore",
        v13,
        L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains");
      goto LABEL_37;
    }
    goto LABEL_38;
  }
  if ( (_QWORD)xmmword_180071090 )
  {
    v8 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters";
    v9 = L"%s:RegOpenKeyEx (%s) failed: %d.";
    goto LABEL_10;
  }
LABEL_12:
  if ( v7 )
LABEL_13:
    v5 = 0;
LABEL_14:
  *((_DWORD *)this + 26) = v5;
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  if ( hKey )
    RegCloseKey(hKey);
  if ( v23 )
    RegCloseKey(v23);
  if ( v3 )
    RRasRoutingDomainConfig::`scalar deleting destructor'(v3);
  v10 = v20;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v28);
  return v10;
}

```

## disassembly

```asm
0x18003de9c  push    rbp
0x18003de9e  push    rbx
0x18003de9f  push    rsi
0x18003dea0  push    rdi
0x18003dea1  push    r12
0x18003dea3  push    r13
0x18003dea5  push    r14
0x18003dea7  push    r15
0x18003dea9  lea     rbp, [rsp-858h]
0x18003deb1  sub     rsp, 958h
0x18003deb8  mov     rax, cs:__security_cookie
0x18003debf  xor     rax, rsp
0x18003dec2  mov     [rbp+890h+var_50], rax
0x18003dec9  mov     rsi, rcx
0x18003decc  xor     r12d, r12d
0x18003decf  mov     [rsp+990h+var_930], r12d
0x18003ded4  mov     [rsp+990h+hKey], r12
0x18003ded9  mov     [rsp+990h+var_920], r12
0x18003dede  xor     edx, edx; Val
0x18003dee0  lea     r8d, [r12+50h]; Size
0x18003dee5  lea     rcx, [rbp+890h+Name]; void *
0x18003dee9  call    memset_0
0x18003deee  mov     [rsp+990h+cbMaxValueNameLen], r12d
0x18003def3  mov     [rbp+890h+cValues], r12d
0x18003def7  mov     [rsp+990h+cbMaxValueLen], r12d
0x18003defc  mov     [rsp+990h+cSubKeys], r12d
0x18003df01  mov     ebx, r12d
0x18003df04  mov     [rbp+890h+var_850], r12d
0x18003df08  xor     edx, edx; Val
0x18003df0a  mov     r8d, 7FCh; Size
0x18003df10  lea     rcx, [rbp+890h+var_84C]; void *
0x18003df14  call    memset_0
0x18003df19  xorps   xmm0, xmm0
0x18003df1c  movdqu  [rbp+890h+var_900], xmm0
0x18003df21  mov     [rbp+890h+var_908], r12
0x18003df25  xorps   xmm1, xmm1
0x18003df28  movdqu  [rbp+890h+var_8F0], xmm1
0x18003df2d  mov     [rbp+890h+var_8E0], r12
0x18003df31  mov     [rbp+890h+var_8D8], 0FFFFFFFFh
0x18003df38  mov     [rbp+890h+var_8D4], r12d
0x18003df3c  lea     r13, aRrasconfigstor_30; "RRasConfigStore::InitializeConfigStore"
0x18003df43  cmp     qword ptr cs:xmmword_180071090+8, r12
0x18003df4a  jz      short loc_18003DF5D
0x18003df4c  lea     r8, [rsp+990h+var_930]; unsigned int *
0x18003df51  mov     rdx, r13; unsigned __int16 *
0x18003df54  lea     rcx, [rbp+890h+var_908]; this
0x18003df58  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003df5d  mov     r14, 0FFFFFFFF80000002h
0x18003df64  mov     [rsi+8], r14
0x18003df68  mov     edi, 1
0x18003df6d  mov     dl, dil; Wait
0x18003df70  lea     rcx, [rsi+70h]; Resource
0x18003df74  call    cs:__imp_RtlAcquireResourceExclusive
0x18003df7a  cmp     [rsi+68h], r12d
0x18003df7e  jz      short loc_18003DFC9
0x18003df80  cmp     qword ptr cs:xmmword_180071090+8, r12
0x18003df87  jz      short loc_18003DFBF
0x18003df89  mov     word ptr [rbp+890h+var_850], r12w
0x18003df8e  mov     r8, r13
0x18003df91  lea     rdx, aSAlreadyInitia; "%s:Already initialized."
0x18003df98  lea     rcx, [rbp+890h+var_850]
0x18003df9c  call    FormatRRASErrorString
0x18003dfa1  lea     r8, [rbp+890h+var_850]
0x18003dfa5  mov     rdx, qword ptr cs:xmmword_180071090+8
0x18003dfac  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003dfb3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003dfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfbf  mov     [rsp+990h+var_930], r12d
0x18003dfc4  jmp     loc_18003E04F
0x18003dfc9  lea     rax, [rsp+990h+hKey]
0x18003dfce  mov     [rsp+990h+phkResult], rax; phkResult
0x18003dfd3  mov     r9d, 20019h; samDesired
0x18003dfd9  xor     r8d, r8d; ulOptions
0x18003dfdc  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Re"...
0x18003dfe3  mov     rcx, r14; hKey
0x18003dfe6  call    cs:__imp_RegOpenKeyExW
0x18003dfec  mov     ecx, eax
0x18003dfee  mov     [rsp+990h+var_930], eax
0x18003dff2  test    eax, eax
0x18003dff4  jz      loc_18003E0BB
0x18003dffa  cmp     qword ptr cs:xmmword_180071090, r12
0x18003e001  jz      short loc_18003E048
0x18003e003  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Re"...
0x18003e00a  lea     rdx, aSRegopenkeyexS; "%s:RegOpenKeyEx (%s) failed: %d."
0x18003e011  mov     word ptr [rbp+890h+var_850], r12w
0x18003e016  mov     dword ptr [rsp+990h+phkResult], eax
0x18003e01a  mov     r8, r13
0x18003e01d  lea     rcx, [rbp+890h+var_850]
0x18003e021  call    FormatRRASErrorString
0x18003e026  lea     r8, [rbp+890h+var_850]
0x18003e02a  mov     rdx, qword ptr cs:xmmword_180071090
0x18003e031  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003e038  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003e03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e044  mov     ecx, [rsp+990h+var_930]
0x18003e048  test    ecx, ecx
0x18003e04a  jz      short loc_18003E04F
0x18003e04c  mov     edi, r12d
0x18003e04f  mov     [rsi+68h], edi
0x18003e052  lea     rcx, [rsi+70h]; Resource
0x18003e056  call    cs:__imp_RtlReleaseResource
0x18003e05c  mov     rcx, [rsp+990h+hKey]; hKey
0x18003e061  test    rcx, rcx
0x18003e064  jz      short loc_18003E06C
0x18003e066  call    cs:__imp_RegCloseKey
0x18003e06c  mov     rcx, [rsp+990h+var_920]; hKey
0x18003e071  test    rcx, rcx
0x18003e074  jz      short loc_18003E07C
0x18003e076  call    cs:__imp_RegCloseKey
0x18003e07c  test    rbx, rbx
0x18003e07f  jz      short loc_18003E089
0x18003e081  mov     rcx, rbx; this
0x18003e084  call    ??_GRRasRoutingDomainConfig@@QEAAPEAXI@Z; RRasRoutingDomainConfig::`scalar deleting destructor'(uint)
0x18003e089  mov     ebx, [rsp+990h+var_930]
0x18003e08d  lea     rcx, [rbp+890h+var_908]; this
0x18003e091  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003e096  mov     eax, ebx
0x18003e098  mov     rcx, [rbp+890h+var_50]
0x18003e09f  xor     rcx, rsp; StackCookie
0x18003e0a2  call    __security_check_cookie
0x18003e0a7  add     rsp, 958h
0x18003e0ae  pop     r15
0x18003e0b0  pop     r14
0x18003e0b2  pop     r13
0x18003e0b4  pop     r12
0x18003e0b6  pop     rdi
0x18003e0b7  pop     rsi
0x18003e0b8  pop     rbx
0x18003e0b9  pop     rbp
0x18003e0ba  retn
0x18003e0bb  lea     r14, [rsi+4]
0x18003e0bf  mov     [rsp+990h+lpcbMaxSubKeyLen], r14
0x18003e0c4  mov     dword ptr [rsp+990h+phkResult], r12d
0x18003e0c9  mov     r9d, edi
0x18003e0cc  xor     r8d, r8d
0x18003e0cf  lea     rdx, aModernstackena; "ModernStackEnabled"
0x18003e0d6  mov     rcx, [rsp+990h+hKey]
0x18003e0db  call    RegGetDword
0x18003e0e0  mov     [rsp+990h+lpcbMaxSubKeyLen], rsi
0x18003e0e5  mov     dword ptr [rsp+990h+phkResult], r12d
0x18003e0ea  mov     r9d, edi
0x18003e0ed  xor     r8d, r8d
0x18003e0f0  lea     rdx, aMultitenancyen; "MultiTenancyEnabled"
0x18003e0f7  mov     rcx, [rsp+990h+hKey]
0x18003e0fc  call    RegGetDword
0x18003e101  cmp     [rsi], r12d
0x18003e104  jz      loc_18003DFBF
0x18003e10a  mov     [r14], edi
0x18003e10d  lea     rax, [rsp+990h+var_920]
0x18003e112  mov     [rsp+990h+phkResult], rax; phkResult
0x18003e117  mov     r9d, 0F003Fh; samDesired
0x18003e11d  xor     r8d, r8d; ulOptions
0x18003e120  lea     r14, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18003e127  mov     rdx, r14; lpSubKey
0x18003e12a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e131  call    cs:__imp_RegOpenKeyExW
0x18003e137  mov     ecx, eax
0x18003e139  mov     [rsp+990h+var_930], eax
0x18003e13d  test    eax, eax
0x18003e13f  jz      short loc_18003E15D
0x18003e141  cmp     qword ptr cs:xmmword_180071090, r12
0x18003e148  jz      loc_18003E048
0x18003e14e  mov     r9, r14
0x18003e151  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18003e158  jmp     loc_18003E011
0x18003e15d  mov     [rsp+990h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003e162  mov     [rsp+990h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18003e167  lea     rax, [rsp+990h+cbMaxValueLen]
0x18003e16c  mov     [rsp+990h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18003e171  lea     rax, [rsp+990h+cbMaxValueNameLen]
0x18003e176  mov     [rsp+990h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003e17b  lea     rax, [rbp+890h+cValues]
0x18003e17f  mov     [rsp+990h+lpcValues], rax; lpcValues
0x18003e184  mov     [rsp+990h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18003e189  mov     [rsp+990h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18003e18e  lea     rax, [rsp+990h+cSubKeys]
0x18003e193  mov     [rsp+990h+phkResult], rax; lpcSubKeys
0x18003e198  xor     r9d, r9d; lpReserved
0x18003e19b  xor     r8d, r8d; lpcchClass
0x18003e19e  xor     edx, edx; lpClass
0x18003e1a0  mov     rcx, [rsp+990h+var_920]; hKey
0x18003e1a5  call    cs:__imp_RegQueryInfoKeyW
0x18003e1ab  mov     ecx, eax
0x18003e1ad  mov     [rsp+990h+var_930], eax
0x18003e1b1  test    eax, eax
0x18003e1b3  jz      short loc_18003E1D1
0x18003e1b5  cmp     qword ptr cs:xmmword_180071090, r12
0x18003e1bc  jz      loc_18003E048
0x18003e1c2  mov     r9, r14
0x18003e1c5  lea     rdx, aSRegqueryinfok; "%s: RegQueryInfoKey (%s) failed: %d."
0x18003e1cc  jmp     loc_18003E011
0x18003e1d1  mov     r14d, r12d
0x18003e1d4  mov     rbx, r12
0x18003e1d7  cmp     r14d, [rsp+990h+cSubKeys]
0x18003e1dc  jnb     loc_18003E048
0x18003e1e2  mov     [rbp+890h+cchName], 28h ; '('
0x18003e1e9  xor     edx, edx; Val
0x18003e1eb  lea     r8d, [rdx+50h]; Size
0x18003e1ef  lea     rcx, [rbp+890h+Name]; void *
0x18003e1f3  call    memset_0
0x18003e1f8  mov     [rsp+990h+lpcValues], r12; lpftLastWriteTime
0x18003e1fd  mov     [rsp+990h+lpcbMaxClassLen], r12; lpcchClass
0x18003e202  mov     [rsp+990h+lpcbMaxSubKeyLen], r12; lpClass
0x18003e207  mov     [rsp+990h+phkResult], r12; lpReserved
0x18003e20c  lea     r9, [rbp+890h+cchName]; lpcchName
0x18003e210  lea     r8, [rbp+890h+Name]; lpName
0x18003e214  mov     edx, r14d; dwIndex
0x18003e217  mov     rcx, [rsp+990h+var_920]; hKey
0x18003e21c  call    cs:__imp_RegEnumKeyExW
0x18003e222  mov     r9d, eax
0x18003e225  mov     [rsp+990h+var_930], eax
0x18003e229  test    eax, eax
0x18003e22b  jz      short loc_18003E267
0x18003e22d  cmp     eax, 0EAh
0x18003e232  jz      short loc_18003E267
0x18003e234  cmp     qword ptr cs:xmmword_180071090, r12
0x18003e23b  jz      loc_18003E2CF
0x18003e241  mov     word ptr [rbp+890h+var_850], r12w
0x18003e246  lea     rax, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18003e24d  mov     [rsp+990h+phkResult], rax
0x18003e252  mov     r8, r13
0x18003e255  lea     rdx, aSErrorDOccured; "%s: Error %d occured while enumerating "...
0x18003e25c  lea     rcx, [rbp+890h+var_850]
0x18003e260  call    FormatRRASErrorString
0x18003e265  jmp     short loc_18003E2B1
0x18003e267  xorps   xmm0, xmm0
0x18003e26a  movups  [rbp+890h+var_8B0], xmm0
0x18003e26e  mov     edx, 28h ; '('
0x18003e273  lea     r8, [rbp+890h+var_8B0]
0x18003e277  lea     rcx, [rbp+890h+Name]
0x18003e27b  call    MprConvertStringToGuid
0x18003e280  mov     [rsp+990h+var_930], eax
0x18003e284  test    eax, eax
0x18003e286  jz      short loc_18003E2DB
0x18003e288  cmp     qword ptr cs:xmmword_180071090, r12
0x18003e28f  jz      short loc_18003E2CF
0x18003e291  mov     word ptr [rbp+890h+var_850], r12w
0x18003e296  mov     dword ptr [rsp+990h+phkResult], eax
0x18003e29a  lea     r9, [rbp+890h+Name]
0x18003e29e  mov     r8, r13
0x18003e2a1  lea     rdx, aSMprconvertstr; "%s: MprConvertStringToGuid failed for ("...
0x18003e2a8  lea     rcx, [rbp+890h+var_850]
0x18003e2ac  call    FormatRRASErrorString
0x18003e2b1  lea     r8, [rbp+890h+var_850]
0x18003e2b5  mov     rdx, qword ptr cs:xmmword_180071090
0x18003e2bc  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003e2c3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003e2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2cf  mov     ecx, r12d
0x18003e2d2  mov     [rsp+990h+var_930], ecx
0x18003e2d6  jmp     loc_18003E3A1
0x18003e2db  mov     ecx, 358h; Size
0x18003e2e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e2e5  mov     [rbp+890h+var_8D0], rax
0x18003e2e9  test    rax, rax
0x18003e2ec  jz      short loc_18003E30C
0x18003e2ee  movaps  xmm0, [rbp+890h+var_8B0]
0x18003e2f2  movdqa  xmmword ptr [rbp+890h+var_8C0.Data1], xmm0
0x18003e2f7  lea     r8, [rbp+890h+var_8C0]; struct _GUID
0x18003e2fb  mov     rdx, [rsi+8]; HKEY
0x18003e2ff  mov     rcx, rax; this
0x18003e302  call    ??0RRasRoutingDomainConfig@@QEAA@PEAUHKEY__@@U_GUID@@@Z; RRasRoutingDomainConfig::RRasRoutingDomainConfig(HKEY__ *,_GUID)
0x18003e307  mov     rbx, rax
0x18003e30a  jmp     short loc_18003E30F
0x18003e30c  mov     rbx, r12
0x18003e30f  test    rbx, rbx
0x18003e312  jz      loc_18003E3D6
0x18003e318  mov     rcx, rbx; this
0x18003e31b  call    ?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::OpenConfigRegKey(void)
0x18003e320  mov     ecx, eax
0x18003e322  mov     [rsp+990h+var_930], eax
0x18003e326  test    eax, eax
0x18003e328  jnz     short loc_18003E3A9
0x18003e32a  mov     rcx, rbx; this
0x18003e32d  call    ?PopulateFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::PopulateFromRegistry(void)
0x18003e332  mov     [rsp+990h+var_930], eax
0x18003e336  test    eax, eax
0x18003e338  jz      short loc_18003E386
0x18003e33a  cmp     qword ptr cs:xmmword_180071090, r12
0x18003e341  jz      short loc_18003E381
0x18003e343  mov     word ptr [rbp+890h+var_850], r12w
0x18003e348  mov     dword ptr [rsp+990h+phkResult], eax
0x18003e34c  lea     r9, [rbp+890h+Name]
0x18003e350  mov     r8, r13
0x18003e353  lea     rdx, aSRdconfigPopul; "%s: rdConfig->PopulateFromRegistry fail"...
0x18003e35a  lea     rcx, [rbp+890h+var_850]
0x18003e35e  call    FormatRRASErrorString
0x18003e363  lea     r8, [rbp+890h+var_850]
0x18003e367  mov     rdx, qword ptr cs:xmmword_180071090
0x18003e36e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003e375  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003e37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e381  mov     [rsp+990h+var_930], r12d
0x18003e386  or      dword ptr [rbx+214h], 2
0x18003e38d  lea     rcx, [rsi+10h]
0x18003e391  lea     rdx, [rbp+890h+var_8B0]
0x18003e395  call    ??A?$unordered_map@U_GUID@@PEAVRRasRoutingDomainConfig@@UGuidHash@@UGuidEquality@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@std@@@tr1@std@@QEAAAEAPEAVRRasRoutingDomainConfig@@AEBU_GUID@@@Z; std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::operator[](_GUID const &)
0x18003e39a  mov     [rax], rbx
0x18003e39d  mov     ecx, [rsp+990h+var_930]
0x18003e3a1  add     r14d, edi
  ... truncated ...
```
