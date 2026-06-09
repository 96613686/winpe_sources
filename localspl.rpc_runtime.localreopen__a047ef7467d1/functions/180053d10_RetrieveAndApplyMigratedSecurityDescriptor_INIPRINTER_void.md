# RetrieveAndApplyMigratedSecurityDescriptor(_INIPRINTER *,void *)

- ea: `0x180053d10`
- end: `0x18005401d`
- name: `?RetrieveAndApplyMigratedSecurityDescriptor@@YAXPEAU_INIPRINTER@@PEAX@Z`
- size: `781`
- prototype: `void(struct _INIPRINTER *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180051d10`

## callees

- `0x180004fb8`
- `0x180013b00`
- `0x1800170a0`
- `0x18002c780`
- `0x18003e984`
- `0x18003ea2c`
- `0x18003fac8`
- `0x180053d10`
- `0x1800547e0`
- `0x1800978dc`
- `0x180098ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053fed`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180053dfa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180053dfa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180053f66`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180053f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053fd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053fd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053d87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053d87`

## string_xrefs

- `0x180053dd9`: `Migrated Security descriptor retrieved successfully `
- `0x180053d71`: `RetrieveAndApplyMigratedSecurityDescriptor`
- `0x180053dcf`: `RetrieveAndApplyMigratedSecurityDescriptor`
- `0x180053fe4`: `RetrieveAndApplyMigratedSecurityDescriptor`
- `0x180053ffd`: `RetrieveAndApplyMigratedSecurityDescriptor`
- `0x180053fdd`: `Failed to extract security descriptor %d`
- `0x180053e39`: `Migrated Security descriptor doesn't contain entries for App Container, Fixing it.`
- `0x180053e51`: `Migrated Security descriptor doesn't contain entries for LPAC, Fixing it.`
- `0x180053ece`: `Migrated Security descriptor doesn't contain entries for Restricted Spooler Worker, Fixing it.`
- `0x180053f10`: `Applying Migrated Security descriptor `
- `0x180053f9b`: `Updated Registry with new security descriptor Successfully `
- `0x180053fa9`: `Failed to update Registry with security Descriptor`
- `0x180053fc3`: `Failed to apply Migrated Security descriptor %d`
- `0x180053ff6`: `Memory allocation for Security descriptor failed %d`
- `0x180053d6a`: `Failed to query Security descriptor `
- `0x180053d32`: `Security`
- `0x180053da4`: `Security`
- `0x180053f7c`: `Security`

## pseudocode

```c
void __fastcall RetrieveAndApplyMigratedSecurityDescriptor(struct _INIPRINTER *a1, void *a2)
{
  unsigned int v4; // r14d
  int Value; // eax
  unsigned int v6; // edi
  HLOCAL v7; // rax
  void *v8; // rbx
  int v9; // esi
  int v10; // ebx
  int v11; // r14d
  unsigned int v12; // r8d
  __int64 v13; // rcx
  unsigned int fixed; // eax
  unsigned int v15; // eax
  __int64 v16; // rbx
  DWORD SecurityDescriptorLength; // eax
  DWORD LastError; // eax
  struct _INISPOOLER *v19; // [rsp+28h] [rbp-28h]
  int v20; // [rsp+30h] [rbp-20h] BYREF
  DWORD dwRevision; // [rsp+34h] [rbp-1Ch] BYREF
  void *v22; // [rsp+38h] [rbp-18h] BYREF
  void *v23[2]; // [rsp+40h] [rbp-10h] BYREF
  WORD pControl; // [rsp+80h] [rbp+30h] BYREF
  SIZE_T uBytes; // [rsp+90h] [rbp+40h] BYREF
  int v26; // [rsp+98h] [rbp+48h] BYREF

  v19 = (struct _INISPOOLER *)*((_QWORD *)a1 + 35);
  LODWORD(uBytes) = 0;
  v4 = 0;
  Value = SplRegQueryValue(a2, L"Security", 0, 0, (unsigned int *)&uBytes, v19);
  v6 = Value;
  if ( Value != 234 && Value )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "RetrieveAndApplyMigratedSecurityDescriptor",
      L"Failed to query Security descriptor ");
    return;
  }
  v7 = LocalAlloc(0, (unsigned int)uBytes);
  v22 = v7;
  v8 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "RetrieveAndApplyMigratedSecurityDescriptor",
      L"Memory allocation for Security descriptor failed %d",
      LastError);
    return;
  }
  if ( SplRegQueryValue(
         a2,
         L"Security",
         0,
         (unsigned __int8 *)v7,
         (unsigned int *)&uBytes,
         *((struct _INISPOOLER **)a1 + 35)) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "RetrieveAndApplyMigratedSecurityDescriptor",
      L"Failed to extract security descriptor %d",
      v6);
    goto LABEL_29;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "RetrieveAndApplyMigratedSecurityDescriptor",
    L"Migrated Security descriptor retrieved successfully ");
  dwRevision = 0;
  pControl = 0;
  if ( GetSecurityDescriptorControl(v8, &pControl, &dwRevision) )
    v9 = pControl & 8;
  else
    v9 = 1;
  v26 = 0;
  v20 = 0;
  if ( !ContainsAccessEntriesForAppContainer(v8, &v26, &v20) )
  {
    v10 = v26;
    if ( !v26 )
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "RetrieveAndApplyMigratedSecurityDescriptor",
        L"Migrated Security descriptor doesn't contain entries for App Container, Fixing it.");
    v11 = v20;
    if ( !v20 )
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "RetrieveAndApplyMigratedSecurityDescriptor",
        L"Migrated Security descriptor doesn't contain entries for LPAC, Fixing it.");
    v12 = 0;
    *(_OWORD *)v23 = 0;
    if ( !v10 )
    {
      v12 = 1;
      v23[0] = gAppContainerAllAppsSid;
    }
    if ( !v11 )
    {
      v13 = v12++;
      v23[v13] = gLPACCapabilitySid;
    }
    fixed = FixPrinterSecurityDescriptor(&v22, v23, v12, 0x20008u, v9);
    v8 = v22;
    v4 = fixed;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
    && !ContainsAccessEntriesForRestrictedSpoolerWorker(v8) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "RetrieveAndApplyMigratedSecurityDescriptor",
      L"Migrated Security descriptor doesn't contain entries for Restricted Spooler Worker, Fixing it.");
    v15 = FixPrinterSecurityDescriptor(&v22, &gRestrictedSpoolerServiceSid, 1u, 0xF000Cu, v9);
    v8 = v22;
    v4 = v15;
  }
  if ( v4 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "RetrieveAndApplyMigratedSecurityDescriptor",
      L"Failed to apply Migrated Security descriptor %d",
      v4);
LABEL_29:
    LocalFree(v8);
    return;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "RetrieveAndApplyMigratedSecurityDescriptor",
    L"Applying Migrated Security descriptor ");
  LocalFree(*((HLOCAL *)a1 + 24));
  *((_QWORD *)a1 + 24) = v8;
  v22 = 0;
  if ( (int)OpenPrinterKey(a1, 131103, &v22, 0, 1) >= 0 )
  {
    v16 = *((_QWORD *)a1 + 35);
    SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)a1 + 24));
    if ( (unsigned int)RegSetBinaryData(v22, L"Security", *((_QWORD *)a1 + 24), SecurityDescriptorLength, &v26, v16) )
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "RetrieveAndApplyMigratedSecurityDescriptor",
        L"Updated Registry with new security descriptor Successfully ");
    else
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "RetrieveAndApplyMigratedSecurityDescriptor",
        L"Failed to update Registry with security Descriptor");
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
}

```

## disassembly

```asm
0x180053d10  mov     [rsp-28h+arg_8], rbx
0x180053d15  push    rbp
0x180053d16  push    rsi
0x180053d17  push    rdi
0x180053d18  push    r14
0x180053d1a  push    r15
0x180053d1c  mov     rbp, rsp
0x180053d1f  sub     rsp, 50h
0x180053d23  mov     rax, [rcx+118h]
0x180053d2a  mov     rsi, rdx
0x180053d2d  mov     [rsp+50h+var_28], rax; struct _INISPOOLER *
0x180053d32  lea     rdx, szSecurity; "Security"
0x180053d39  lea     rax, [rbp+uBytes]
0x180053d3d  mov     dword ptr [rbp+uBytes], 0
0x180053d44  mov     r15, rcx
0x180053d47  mov     [rsp+50h+var_30], rax; unsigned int *
0x180053d4c  xor     r9d, r9d; unsigned __int8 *
0x180053d4f  xor     r8d, r8d; unsigned int *
0x180053d52  mov     rcx, rsi; void *
0x180053d55  xor     r14d, r14d
0x180053d58  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180053d5d  mov     edi, eax
0x180053d5f  cmp     eax, 0EAh
0x180053d64  jz      short loc_180053D82
0x180053d66  test    eax, eax
0x180053d68  jz      short loc_180053D82
0x180053d6a  lea     rdx, aFailedToQueryS; "Failed to query Security descriptor "
0x180053d71  lea     rcx, aRetrieveandapp; "RetrieveAndApplyMigratedSecurityDescrip"...
0x180053d78  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180053d7d  jmp     loc_180054009
0x180053d82  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180053d85  xor     ecx, ecx; uFlags
0x180053d87  call    cs:__imp_LocalAlloc
0x180053d8d  mov     [rbp+var_18], rax
0x180053d91  mov     rbx, rax
0x180053d94  test    rax, rax
0x180053d97  jz      loc_180053FED
0x180053d9d  mov     rax, [r15+118h]
0x180053da4  lea     rdx, szSecurity; "Security"
0x180053dab  mov     [rsp+50h+var_28], rax; struct _INISPOOLER *
0x180053db0  mov     r9, rbx; unsigned __int8 *
0x180053db3  lea     rax, [rbp+uBytes]
0x180053db7  xor     r8d, r8d; unsigned int *
0x180053dba  mov     rcx, rsi; void *
0x180053dbd  mov     [rsp+50h+var_30], rax; unsigned int *
0x180053dc2  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180053dc7  test    eax, eax
0x180053dc9  jnz     loc_180053FDA
0x180053dcf  lea     rdi, aRetrieveandapp; "RetrieveAndApplyMigratedSecurityDescrip"...
0x180053dd6  mov     rcx, rdi; char *
0x180053dd9  lea     rdx, aMigratedSecuri_1; "Migrated Security descriptor retrieved "...
0x180053de0  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180053de5  xor     eax, eax
0x180053de7  mov     [rbp+dwRevision], r14d
0x180053deb  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180053def  mov     [rbp+pControl], ax
0x180053df3  lea     rdx, [rbp+pControl]; pControl
0x180053df7  mov     rcx, rbx; pSecurityDescriptor
0x180053dfa  call    cs:__imp_GetSecurityDescriptorControl
0x180053e00  test    eax, eax
0x180053e02  jz      short loc_180053E0D
0x180053e04  movzx   esi, [rbp+pControl]
0x180053e08  and     esi, 8
0x180053e0b  jmp     short loc_180053E12
0x180053e0d  mov     esi, 1
0x180053e12  lea     r8, [rbp+var_20]; int *
0x180053e16  mov     [rbp+arg_18], r14d
0x180053e1a  lea     rdx, [rbp+arg_18]; int *
0x180053e1e  mov     [rbp+var_20], r14d
0x180053e22  mov     rcx, rbx; void *
0x180053e25  call    ?ContainsAccessEntriesForAppContainer@@YA_NPEAXPEAH1@Z; ContainsAccessEntriesForAppContainer(void *,int *,int *)
0x180053e2a  test    al, al
0x180053e2c  jnz     loc_180053EB2
0x180053e32  mov     ebx, [rbp+arg_18]
0x180053e35  test    ebx, ebx
0x180053e37  jnz     short loc_180053E48
0x180053e39  lea     rdx, aMigratedSecuri_2; "Migrated Security descriptor doesn't co"...
0x180053e40  mov     rcx, rdi; char *
0x180053e43  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180053e48  mov     r14d, [rbp+var_20]
0x180053e4c  test    r14d, r14d
0x180053e4f  jnz     short loc_180053E60
0x180053e51  lea     rdx, aMigratedSecuri; "Migrated Security descriptor doesn't co"...
0x180053e58  mov     rcx, rdi; char *
0x180053e5b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180053e60  xor     r8d, r8d
0x180053e63  xorps   xmm0, xmm0
0x180053e66  movups  xmmword ptr [rbp+var_10], xmm0
0x180053e6a  test    ebx, ebx
0x180053e6c  jnz     short loc_180053E7D
0x180053e6e  mov     rax, cs:?gAppContainerAllAppsSid@@3PEAXEA; void * gAppContainerAllAppsSid
0x180053e75  lea     r8d, [rbx+1]
0x180053e79  mov     [rbp+var_10], rax
0x180053e7d  test    r14d, r14d
0x180053e80  jnz     short loc_180053E94
0x180053e82  mov     rax, cs:?gLPACCapabilitySid@@3PEAXEA; void * gLPACCapabilitySid
0x180053e89  mov     ecx, r8d
0x180053e8c  inc     r8d; unsigned int
0x180053e8f  mov     [rbp+rcx*8+var_10], rax
0x180053e94  mov     r9d, 20008h; unsigned int
0x180053e9a  mov     dword ptr [rsp+50h+var_30], esi; int
0x180053e9e  lea     rdx, [rbp+var_10]; void **
0x180053ea2  lea     rcx, [rbp+var_18]; void **
0x180053ea6  call    ?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z; FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)
0x180053eab  mov     rbx, [rbp+var_18]
0x180053eaf  mov     r14d, eax
0x180053eb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180053eb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180053ebe  test    al, al
0x180053ec0  jz      short loc_180053F04
0x180053ec2  mov     rcx, rbx; void *
0x180053ec5  call    ?ContainsAccessEntriesForRestrictedSpoolerWorker@@YA_NPEAX@Z; ContainsAccessEntriesForRestrictedSpoolerWorker(void *)
0x180053eca  test    al, al
0x180053ecc  jnz     short loc_180053F04
0x180053ece  lea     rdx, aMigratedSecuri_0; "Migrated Security descriptor doesn't co"...
0x180053ed5  mov     rcx, rdi; char *
0x180053ed8  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180053edd  mov     r9d, 0F000Ch; unsigned int
0x180053ee3  mov     dword ptr [rsp+50h+var_30], esi; int
0x180053ee7  mov     r8d, 1; unsigned int
0x180053eed  lea     rdx, ?gRestrictedSpoolerServiceSid@@3PEAXEA; void **
0x180053ef4  lea     rcx, [rbp+var_18]; void **
0x180053ef8  call    ?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z; FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)
0x180053efd  mov     rbx, [rbp+var_18]
0x180053f01  mov     r14d, eax
0x180053f04  mov     rcx, rdi; char *
0x180053f07  test    r14d, r14d
0x180053f0a  jnz     loc_180053FC0
0x180053f10  lea     rdx, aApplyingMigrat; "Applying Migrated Security descriptor "
0x180053f17  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180053f1c  mov     rcx, [r15+0C0h]; hMem
0x180053f23  call    cs:__imp_LocalFree
0x180053f29  xor     r9d, r9d
0x180053f2c  mov     [r15+0C0h], rbx
0x180053f33  lea     r8, [rbp+var_18]
0x180053f37  mov     [rbp+var_18], 0
0x180053f3f  mov     edx, 2001Fh
0x180053f44  mov     dword ptr [rsp+50h+var_30], 1
0x180053f4c  mov     rcx, r15
0x180053f4f  call    OpenPrinterKey
0x180053f54  test    eax, eax
0x180053f56  js      short loc_180053FB5
0x180053f58  mov     rcx, [r15+0C0h]; pSecurityDescriptor
0x180053f5f  mov     rbx, [r15+118h]
0x180053f66  call    cs:__imp_GetSecurityDescriptorLength
0x180053f6c  mov     r8, [r15+0C0h]
0x180053f73  lea     rcx, [rbp+arg_18]
0x180053f77  mov     [rsp+50h+var_28], rbx
0x180053f7c  lea     rdx, szSecurity; "Security"
0x180053f83  mov     [rsp+50h+var_30], rcx
0x180053f88  mov     r9d, eax
0x180053f8b  mov     rcx, [rbp+var_18]
0x180053f8f  call    RegSetBinaryData
0x180053f94  mov     rcx, rdi; char *
0x180053f97  test    eax, eax
0x180053f99  jz      short loc_180053FA9
0x180053f9b  lea     rdx, aUpdatedRegistr; "Updated Registry with new security desc"...
0x180053fa2  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180053fa7  jmp     short loc_180053FB5
0x180053fa9  lea     rdx, aFailedToUpdate_2; "Failed to update Registry with security"...
0x180053fb0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180053fb5  lea     rcx, [rbp+var_18]
0x180053fb9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180053fbe  jmp     short loc_180054009
0x180053fc0  mov     r8d, r14d
0x180053fc3  lea     rdx, aFailedToApplyM; "Failed to apply Migrated Security descr"...
0x180053fca  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180053fcf  mov     rcx, rbx; hMem
0x180053fd2  call    cs:__imp_LocalFree
0x180053fd8  jmp     short loc_180054009
0x180053fda  mov     r8d, edi
0x180053fdd  lea     rdx, aFailedToExtrac; "Failed to extract security descriptor %"...
0x180053fe4  lea     rcx, aRetrieveandapp; "RetrieveAndApplyMigratedSecurityDescrip"...
0x180053feb  jmp     short loc_180053FCA
0x180053fed  call    cs:__imp_GetLastError
0x180053ff3  mov     r8d, eax
0x180053ff6  lea     rdx, aMemoryAllocati; "Memory allocation for Security descript"...
0x180053ffd  lea     rcx, aRetrieveandapp; "RetrieveAndApplyMigratedSecurityDescrip"...
0x180054004  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180054009  mov     rbx, [rsp+50h+arg_8]
0x180054011  add     rsp, 50h
0x180054015  pop     r15
0x180054017  pop     r14
0x180054019  pop     rdi
0x18005401a  pop     rsi
0x18005401b  pop     rbp
0x18005401c  retn
```
