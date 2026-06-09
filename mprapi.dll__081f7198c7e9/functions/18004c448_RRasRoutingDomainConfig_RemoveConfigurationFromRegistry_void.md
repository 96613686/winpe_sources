# RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(void)

- ea: `0x18004c448`
- end: `0x18004c6d5`
- name: `?RemoveConfigurationFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `653`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180046ea8`

## callees

- `0x1800302d0`
- `0x180049f28`
- `0x18004c448`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c596`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c6a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c596`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c6a0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004c611`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004c611`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c5c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c5c4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004c564`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004c564`

## string_xrefs

- `0x18004c5b6`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18004c5e1`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18004c5e8`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18004c4e4`: `RRasRoutingDomainConfig::RemoveConfigurationFromRegistry`
- `0x18004c52a`: `%s: Failed to open the routing domin key: %d.`
- `0x18004c581`: `%s: RegDeleteTree failed: %d.`
- `0x18004c62e`: `%s: RegDeleteKeyEx  failed for (%ws): %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  HKEY v6; // rcx
  LSTATUS v7; // eax
  WCHAR *v8; // r9
  const wchar_t *v9; // rdx
  GUID *v10; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h]
  __int128 v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  int v20; // [rsp+84h] [rbp-7Ch]
  GUID v21; // [rsp+88h] [rbp-78h] BYREF
  int v22; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+9Ch] [rbp-64h]
  __int128 v24; // [rsp+ACh] [rbp-54h]
  int v25; // [rsp+BCh] [rbp-44h]
  WCHAR SubKey[40]; // [rsp+C0h] [rbp-40h] BYREF
  int v27; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v28[2044]; // [rsp+114h] [rbp+14h] BYREF

  v13 = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  hKey = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"RRasRoutingDomainConfig::RemoveConfigurationFromRegistry",
      &v13,
      v2,
      (struct _GUID *)((char *)this + 516));
  v3 = RRasRoutingDomainConfig::OpenConfigRegKey(this);
  v4 = v3;
  v13 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_22;
    v5 = L"%s: Failed to open the routing domin key: %d.";
LABEL_6:
    LOWORD(v22) = 0;
    v21 = GUID_NULL;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, v5, L"RRasRoutingDomainConfig::RemoveConfigurationFromRegistry", v3);
    goto LABEL_19;
  }
  v3 = RegDeleteTreeW(*((HKEY *)this + 103), 0);
  v4 = v3;
  v13 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_22;
    v5 = L"%s: RegDeleteTree failed: %d.";
    goto LABEL_6;
  }
  v6 = (HKEY)*((_QWORD *)this + 103);
  if ( v6 )
  {
    RegCloseKey(v6);
    *((_QWORD *)this + 103) = 0;
  }
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
         0,
         0xF003Fu,
         &hKey);
  v4 = v7;
  v13 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_22;
    v8 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains";
    v9 = L"%s: RegOpenKeyEx (%s) failed: %d.";
  }
  else
  {
    MprConvertGuidToString((char *)this + 516, 40, SubKey);
    v7 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
    v4 = v7;
    v13 = v7;
    if ( !v7 || !(_QWORD)xmmword_180078C60 )
      goto LABEL_22;
    v8 = SubKey;
    v9 = L"%s: RegDeleteKeyEx  failed for (%ws): %d.";
  }
  LODWORD(phkResult) = v7;
  LOWORD(v27) = 0;
  v21 = GUID_NULL;
  LOWORD(v22) = 0;
  FormatRRASErrorString(&v27, v9, L"RRasRoutingDomainConfig::RemoveConfigurationFromRegistry", v8, phkResult);
LABEL_19:
  v10 = &v21;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v10 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C60,
    &v27,
    v10,
    0,
    &v22);
  v4 = v13;
LABEL_22:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v4 = v13;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v4;
}

```

## disassembly

```asm
0x18004c448  push    rbp
0x18004c44a  push    rbx
0x18004c44b  push    rsi
0x18004c44c  push    rdi
0x18004c44d  push    r14
0x18004c44f  push    r15
0x18004c451  lea     rbp, [rsp-828h]
0x18004c459  sub     rsp, 928h
0x18004c460  mov     rax, cs:__security_cookie
0x18004c467  xor     rax, rsp
0x18004c46a  mov     [rbp+850h+var_40], rax
0x18004c471  mov     rdi, rcx
0x18004c474  xor     r14d, r14d
0x18004c477  mov     [rsp+950h+var_910], r14d
0x18004c47c  xor     edx, edx; Val
0x18004c47e  lea     r8d, [r14+50h]; Size
0x18004c482  lea     rcx, [rbp+850h+SubKey]; void *
0x18004c486  call    memset_0
0x18004c48b  mov     [rsp+950h+hKey], r14
0x18004c490  mov     [rbp+850h+var_840], r14d
0x18004c494  xor     edx, edx; Val
0x18004c496  mov     r8d, 7FCh; Size
0x18004c49c  lea     rcx, [rbp+850h+var_83C]; void *
0x18004c4a0  call    memset_0
0x18004c4a5  mov     [rbp+850h+var_8B8], r14d
0x18004c4a9  xorps   xmm0, xmm0
0x18004c4ac  xor     eax, eax
0x18004c4ae  movups  [rbp+850h+var_8B4], xmm0
0x18004c4b2  movups  [rbp+850h+var_8A4], xmm0
0x18004c4b6  mov     [rbp+850h+var_894], eax
0x18004c4b9  movdqu  [rsp+950h+var_8F8], xmm0
0x18004c4bf  mov     [rsp+950h+var_900], r14
0x18004c4c4  xorps   xmm1, xmm1
0x18004c4c7  movdqu  [rsp+950h+var_8E8], xmm1
0x18004c4cd  mov     [rsp+950h+var_8D8], r14
0x18004c4d2  mov     [rbp+850h+var_8D0], 0FFFFFFFFh
0x18004c4d9  mov     [rbp+850h+var_8CC], r14d
0x18004c4dd  lea     rsi, [rdi+204h]
0x18004c4e4  lea     r15, aRrasroutingdom_49; "RRasRoutingDomainConfig::RemoveConfigur"...
0x18004c4eb  cmp     qword ptr cs:xmmword_180078C60+8, r14
0x18004c4f2  jz      short loc_18004C50B
0x18004c4f4  mov     [rsp+950h+phkResult], rsi; struct _GUID *
0x18004c4f9  lea     r8, [rsp+950h+var_910]; unsigned int *
0x18004c4fe  mov     rdx, r15; unsigned __int16 *
0x18004c501  lea     rcx, [rsp+950h+var_900]; this
0x18004c506  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004c50b  mov     rcx, rdi; this
0x18004c50e  call    ?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::OpenConfigRegKey(void)
0x18004c513  mov     ebx, eax
0x18004c515  mov     [rsp+950h+var_910], eax
0x18004c519  test    eax, eax
0x18004c51b  jz      short loc_18004C55B
0x18004c51d  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c524  jz      loc_18004C696
0x18004c52a  lea     rdx, aSFailedToOpenT; "%s: Failed to open the routing domin ke"...
0x18004c531  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c538  mov     r8, r15
0x18004c53b  mov     r9d, eax
0x18004c53e  mov     word ptr [rbp+850h+var_8B8], r14w
0x18004c543  movdqu  [rbp+850h+var_8C8], xmm0
0x18004c548  mov     word ptr [rbp+850h+var_840], r14w
0x18004c54d  lea     rcx, [rbp+850h+var_840]
0x18004c551  call    FormatRRASErrorString
0x18004c556  jmp     loc_18004C65B
0x18004c55b  xor     edx, edx; lpSubKey
0x18004c55d  mov     rcx, [rdi+338h]; hKey
0x18004c564  call    cs:__imp_RegDeleteTreeW
0x18004c56a  mov     ebx, eax
0x18004c56c  mov     [rsp+950h+var_910], eax
0x18004c570  test    eax, eax
0x18004c572  jz      short loc_18004C58A
0x18004c574  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c57b  jz      loc_18004C696
0x18004c581  lea     rdx, aSRegdeletetree; "%s: RegDeleteTree failed: %d."
0x18004c588  jmp     short loc_18004C531
0x18004c58a  mov     rcx, [rdi+338h]; hKey
0x18004c591  test    rcx, rcx
0x18004c594  jz      short loc_18004C5A3
0x18004c596  call    cs:__imp_RegCloseKey
0x18004c59c  mov     [rdi+338h], r14
0x18004c5a3  lea     rax, [rsp+950h+hKey]
0x18004c5a8  mov     [rsp+950h+phkResult], rax; phkResult
0x18004c5ad  mov     r9d, 0F003Fh; samDesired
0x18004c5b3  xor     r8d, r8d; ulOptions
0x18004c5b6  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18004c5bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c5c4  call    cs:__imp_RegOpenKeyExW
0x18004c5ca  mov     ebx, eax
0x18004c5cc  mov     [rsp+950h+var_910], eax
0x18004c5d0  test    eax, eax
0x18004c5d2  jz      short loc_18004C5F1
0x18004c5d4  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c5db  jz      loc_18004C696
0x18004c5e1  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18004c5e8  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18004c5ef  jmp     short loc_18004C635
0x18004c5f1  lea     r8, [rbp+850h+SubKey]
0x18004c5f5  mov     edx, 28h ; '('
0x18004c5fa  mov     rcx, rsi
0x18004c5fd  call    MprConvertGuidToString
0x18004c602  xor     r9d, r9d; Reserved
0x18004c605  xor     r8d, r8d; samDesired
0x18004c608  lea     rdx, [rbp+850h+SubKey]; lpSubKey
0x18004c60c  mov     rcx, [rsp+950h+hKey]; hKey
0x18004c611  call    cs:__imp_RegDeleteKeyExW
0x18004c617  mov     ebx, eax
0x18004c619  mov     [rsp+950h+var_910], eax
0x18004c61d  test    eax, eax
0x18004c61f  jz      short loc_18004C696
0x18004c621  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c628  jz      short loc_18004C696
0x18004c62a  lea     r9, [rbp+850h+SubKey]
0x18004c62e  lea     rdx, aSRegdeletekeye; "%s: RegDeleteKeyEx  failed for (%ws): %"...
0x18004c635  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c63c  mov     dword ptr [rsp+950h+phkResult], eax
0x18004c640  mov     word ptr [rbp+850h+var_840], r14w
0x18004c645  movdqu  [rbp+850h+var_8C8], xmm0
0x18004c64a  mov     word ptr [rbp+850h+var_8B8], r14w
0x18004c64f  mov     r8, r15
0x18004c652  lea     rcx, [rbp+850h+var_840]
0x18004c656  call    FormatRRASErrorString
0x18004c65b  lea     rax, [rbp+850h+var_8B8]
0x18004c65f  mov     [rsp+950h+var_928], rax
0x18004c664  lea     r9, [rbp+850h+var_8C8]
0x18004c668  test    rsi, rsi
0x18004c66b  mov     [rsp+950h+phkResult], r14
0x18004c670  cmovnz  r9, rsi
0x18004c674  lea     r8, [rbp+850h+var_840]
0x18004c678  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004c67f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004c686  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004c68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c692  mov     ebx, [rsp+950h+var_910]
0x18004c696  mov     rcx, [rsp+950h+hKey]; hKey
0x18004c69b  test    rcx, rcx
0x18004c69e  jz      short loc_18004C6AA
0x18004c6a0  call    cs:__imp_RegCloseKey
0x18004c6a6  mov     ebx, [rsp+950h+var_910]
0x18004c6aa  lea     rcx, [rsp+950h+var_900]; this
0x18004c6af  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004c6b4  mov     eax, ebx
0x18004c6b6  mov     rcx, [rbp+850h+var_40]
0x18004c6bd  xor     rcx, rsp; StackCookie
0x18004c6c0  call    __security_check_cookie
0x18004c6c5  add     rsp, 928h
0x18004c6cc  pop     r15
0x18004c6ce  pop     r14
0x18004c6d0  pop     rdi
0x18004c6d1  pop     rsi
0x18004c6d2  pop     rbx
0x18004c6d3  pop     rbp
0x18004c6d4  retn
```
