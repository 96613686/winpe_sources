# AVrfInitializeVerifier

- ea: `0x180112488`
- end: `0x1801128d9`
- name: `AVrfInitializeVerifier`
- size: `1105`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x1800741c8`
- `0x1800d6508`

## callees

- `0x180007060`
- `0x18001a080`
- `0x18001f070`
- `0x18002a3b8`
- `0x180050f70`
- `0x180054000`
- `0x180066da0`
- `0x180068f24`
- `0x180072290`
- `0x1800733c0`
- `0x180079610`
- `0x1800bbda8`
- `0x1800bf9f8`
- `0x1800e5fcc`
- `0x18010f4e0`
- `0x180112488`
- `0x18011e5b0`
- `0x18011f65c`
- `0x18012281c`
- `0x180136ed4`

## string_xrefs

- `0x180112865`: `VerifierDlls`

## pseudocode

```c
__int64 __fastcall AVrfInitializeVerifier(char a1, __int64 a2, __int64 a3, int a4, __int64 a5, _QWORD *a6)
{
  struct _PEB *v6; // r14
  int Dll; // ebx
  __int64 *i; // rbx
  int LoadedDllByName; // eax
  __int64 v13; // rbx
  int ProcedureAddress; // ebx
  __int64 *j; // rdi
  __int64 v16; // rcx
  __int64 *v17; // rbx
  __int64 v18; // rdx
  _QWORD *v19; // rsi
  unsigned int NtGlobalFlag; // r10d
  int v21; // r14d
  int v22; // ecx
  __int64 v24; // [rsp+20h] [rbp-20h]
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+38h] [rbp-8h] BYREF
  int v27; // [rsp+88h] [rbp+48h] BYREF

  v6 = NtCurrentPeb();
  v25 = 0;
  v26 = 0;
  v27 = 0;
  if ( !a4 )
  {
    v19 = a6;
    if ( !a6 )
      return (unsigned int)-1073741811;
    *a6 = 0;
    NtGlobalFlag = v6->NtGlobalFlag;
    if ( (NtGlobalFlag & 0x2000100) != 0 )
    {
      v21 = 1;
    }
    else
    {
      v21 = 0;
      if ( (unsigned __int8)LdrpPayloadRestrictionMitigationsEnabled() )
        v21 = 2;
    }
    if ( (NtGlobalFlag & 0x100) != 0 || a1 )
      v22 = 294916;
    else
      v22 = 0;
    AVrfpVerifierFlags = v22;
    AVrfpVerifierDllsString = 0;
    if ( a3 )
    {
      RtlQueryImageFileKeyOption(a3, L"VerifierFlags", 4, &v27, 4, 0);
      LOBYTE(v22) = v27;
      if ( v27 )
      {
        AVrfpVerifierFlags = v27;
LABEL_46:
        if ( (v22 & 4) != 0 )
          RtlQueryImageFileKeyOption(a3, L"HandleTraces", 4, &AVrfpHandleTraces, 4, 0);
        RtlQueryImageFileKeyOption(a3, L"VerifierDebug", 4, &AVrfpDebug, 4, 0);
        RtlQueryImageFileKeyOption(a3, L"VerifierDlls", 1, &AVrfpVerifierDllsString, 512, 0);
LABEL_49:
        Dll = AvrfMiniLoadDll((__int64)VerifierDllString, a2, a3, a5, (__int64)AvrfpLoaderEntry);
        if ( Dll >= 0 )
        {
          *v19 = AvrfpLoaderEntry;
          Dll = AVrfpEnableVerifierOptions();
          if ( Dll >= 0 )
          {
            LdrProtectMrdata(0);
            AvrfAppVerifierMode = v21;
            LdrProtectMrdata(1);
          }
        }
        return (unsigned int)Dll;
      }
      LOBYTE(v22) = AVrfpVerifierFlags;
    }
    if ( a1 )
      AVrfpEnabledSystemWide = 1;
    if ( !a3 )
      goto LABEL_49;
    goto LABEL_46;
  }
  if ( a4 != 1 )
    return 0;
  qword_1801CC638 = (__int64)&AVrfpVerifierProvidersList;
  AVrfpVerifierProvidersList = (__int64)&AVrfpVerifierProvidersList;
  Dll = RtlInitializeCriticalSectionEx(AVrfpVerifierLock, 0, 0);
  if ( Dll >= 0 )
  {
    if ( AvrfAppVerifierMode == 2 )
    {
      LOBYTE(v27) = 0;
      Dll = LdrpInitializeGraphRecurse(qword_1801CC798, 0, &v27);
      if ( Dll < 0 )
        return (unsigned int)Dll;
    }
    else
    {
      DbgPrintEx(
        93,
        0,
        "AVRF: %ws: pid 0x%X: flags 0x%X: application verifier enabled\n",
        *(_QWORD *)(qword_1801CA8D0 + 96),
        NtCurrentTeb()->ClientId.UniqueProcess,
        AVrfpVerifierFlags);
      if ( (int)AVrfpParseVerifierDllsString() < 0 )
      {
        LODWORD(v24) = NtCurrentTeb()->ClientId.UniqueProcess;
        DbgPrintEx(
          93,
          0,
          "AVRF: %ws: pid 0x%X: application verifier will be disabled due to an initialization error.\n",
          *(_QWORD *)(qword_1801CA8D0 + 96),
          v24);
        Dll = -1073741823;
        NtCurrentPeb()->NtGlobalFlag = NtCurrentPeb()->NtGlobalFlag & 0xFFFFFEFF;
        return (unsigned int)Dll;
      }
      for ( i = (__int64 *)AVrfpVerifierProvidersList; i != &AVrfpVerifierProvidersList; i = (__int64 *)*i )
      {
        if ( !AVrfpLoadAndInitializeProvider((__int64)i) )
          return (unsigned int)-1073741502;
      }
      AVrfpChainDuplicateVerificationLayers();
      LoadedDllByName = LdrpFindLoadedDllByName((unsigned int)&VrfcoreDllString, 0, 0, (unsigned int)&v25, 0);
      Dll = LoadedDllByName;
      if ( LoadedDllByName < 0 )
      {
        if ( LoadedDllByName != -1073741515 )
          return (unsigned int)Dll;
        LODWORD(v13) = qword_1801CC690;
      }
      else
      {
        v13 = *(_QWORD *)(v25 + 48);
        LdrpDereferenceModule(v25);
      }
      ProcedureAddress = LdrGetProcedureAddressEx(
                           v13,
                           (unsigned int)&AvrfpAPILookupCallbackName,
                           0,
                           (unsigned int)&v26,
                           1);
      LdrProtectMrdata(0);
      if ( ProcedureAddress >= 0 )
      {
        AvrfpAPILookupCallbacksEnabled = 1;
        AvrfpAPILookupCallbackRoutine = __ROR8__(v26 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
      }
      AVrfpEnabled = 1;
      RtlGuardAllowSuppressedCalls = 1;
      LdrProtectMrdata(1);
      AVrfpSnapAlreadyLoadedDlls();
      LdrpInitializeTls();
      for ( j = (__int64 *)AVrfpVerifierProvidersList; j != &AVrfpVerifierProvidersList; j = (__int64 *)*j )
      {
        v16 = j[4];
        LOBYTE(v27) = 0;
        Dll = LdrpInitializeGraphRecurse(*(_QWORD *)(v16 + 152), 0, &v27);
        if ( Dll < 0 )
          return (unsigned int)Dll;
      }
      if ( (AVrfpDebug & 8) != 0 )
      {
        DbgPrint("AVRF: -*- final list of providers -*- \n");
        v17 = (__int64 *)AVrfpVerifierProvidersList;
        while ( v17 != &AVrfpVerifierProvidersList )
        {
          v18 = v17[3];
          v17 = (__int64 *)*v17;
          DbgPrint("AVRF: provider %ws \n", v18);
        }
      }
      AVrfpVerifierStopInitialize();
      RtlImageNtHeaderEx(3, v6->ImageBaseAddress, 0, &v26);
    }
    return 0;
  }
  return (unsigned int)Dll;
}

```

## disassembly

```asm
0x180112488  mov     [rsp-28h+arg_0], rbx
0x18011248d  mov     [rsp-28h+arg_8], rsi
0x180112492  push    rbp
0x180112493  push    rdi
0x180112494  push    r12
0x180112496  push    r14
0x180112498  push    r15
0x18011249a  mov     rbp, rsp
0x18011249d  sub     rsp, 40h
0x1801124a1  mov     r14, gs:60h
0x1801124aa  mov     rbx, r8
0x1801124ad  mov     [rbp+var_10], 0
0x1801124b5  mov     r12, rdx
0x1801124b8  mov     [rbp+var_8], 0
0x1801124c0  mov     r15b, cl
0x1801124c3  mov     [rbp+arg_18], 0
0x1801124ca  test    r9d, r9d
0x1801124cd  jz      loc_180112738
0x1801124d3  cmp     r9d, 1
0x1801124d7  jnz     loc_180112731
0x1801124dd  lea     rsi, AVrfpVerifierProvidersList
0x1801124e4  xor     r8d, r8d
0x1801124e7  xor     edx, edx
0x1801124e9  mov     cs:qword_1801CC638, rsi
0x1801124f0  lea     rcx, AVrfpVerifierLock
0x1801124f7  mov     cs:AVrfpVerifierProvidersList, rsi
0x1801124fe  call    RtlInitializeCriticalSectionEx
0x180112503  mov     ebx, eax
0x180112505  test    eax, eax
0x180112507  js      loc_1801128BF
0x18011250d  mov     ecx, 2
0x180112512  xor     edx, edx
0x180112514  cmp     cs:AvrfAppVerifierMode, ecx
0x18011251a  jz      loc_180112713
0x180112520  mov     rcx, gs:40h
0x180112529  lea     ebx, [rdx+5Dh]
0x18011252c  mov     r9, cs:qword_1801CA8D0
0x180112533  lea     r8, aAvrfWsPid0xXFl; "AVRF: %ws: pid 0x%X: flags 0x%X: applic"...
0x18011253a  mov     eax, cs:AVrfpVerifierFlags
0x180112540  mov     dword ptr [rsp+40h+var_18], eax
0x180112544  mov     dword ptr [rsp+40h+var_20], ecx
0x180112548  mov     ecx, ebx
0x18011254a  mov     r9, [r9+60h]
0x18011254e  call    DbgPrintEx
0x180112553  call    AVrfpParseVerifierDllsString
0x180112558  test    eax, eax
0x18011255a  jns     short loc_1801125B0
0x18011255c  mov     rax, gs:40h
0x180112565  lea     r8, aAvrfWsPid0xXAp; "AVRF: %ws: pid 0x%X: application verifi"...
0x18011256c  mov     r9, cs:qword_1801CA8D0
0x180112573  xor     edx, edx
0x180112575  mov     ecx, ebx
0x180112577  mov     dword ptr [rsp+40h+var_20], eax
0x18011257b  mov     r9, [r9+60h]
0x18011257f  call    DbgPrintEx
0x180112584  mov     rax, gs:60h
0x18011258d  mov     ebx, 0C0000001h
0x180112592  mov     ecx, [rax+0BCh]
0x180112598  mov     rax, gs:60h
0x1801125a1  btr     ecx, 8
0x1801125a5  mov     [rax+0BCh], ecx
0x1801125ab  jmp     loc_1801128BF
0x1801125b0  mov     rbx, cs:AVrfpVerifierProvidersList
0x1801125b7  cmp     rbx, rsi
0x1801125ba  jz      short loc_1801125D7
0x1801125bc  mov     rcx, rbx
0x1801125bf  call    AVrfpLoadAndInitializeProvider
0x1801125c4  test    al, al
0x1801125c6  jz      short loc_1801125CD
0x1801125c8  mov     rbx, [rbx]
0x1801125cb  jmp     short loc_1801125B7
0x1801125cd  mov     ebx, 0C0000142h
0x1801125d2  jmp     loc_1801128BF
0x1801125d7  call    AVrfpChainDuplicateVerificationLayers
0x1801125dc  lea     r9, [rbp+var_10]
0x1801125e0  mov     [rsp+40h+var_20], 0
0x1801125e9  xor     r8d, r8d
0x1801125ec  lea     rcx, VrfcoreDllString
0x1801125f3  xor     edx, edx
0x1801125f5  call    LdrpFindLoadedDllByName
0x1801125fa  mov     ebx, eax
0x1801125fc  test    eax, eax
0x1801125fe  js      short loc_18011260F
0x180112600  mov     rcx, [rbp+var_10]
0x180112604  mov     rbx, [rcx+30h]
0x180112608  call    LdrpDereferenceModule
0x18011260d  jmp     short loc_180112621
0x18011260f  cmp     eax, 0C0000135h
0x180112614  jnz     loc_1801128BF
0x18011261a  mov     rbx, cs:qword_1801CC690
0x180112621  mov     edi, 1
0x180112626  lea     r9, [rbp+var_8]
0x18011262a  xor     r8d, r8d
0x18011262d  mov     dword ptr [rsp+40h+var_20], edi
0x180112631  lea     rdx, AvrfpAPILookupCallbackName
0x180112638  mov     rcx, rbx
0x18011263b  call    LdrGetProcedureAddressEx
0x180112640  xor     ecx, ecx
0x180112642  mov     ebx, eax
0x180112644  call    LdrProtectMrdata
0x180112649  test    ebx, ebx
0x18011264b  js      short loc_18011266E
0x18011264d  mov     eax, ds:7FFE0330h
0x180112654  mov     ecx, eax
0x180112656  mov     cs:AvrfpAPILookupCallbacksEnabled, dil
0x18011265d  xor     rax, [rbp+var_8]
0x180112661  and     ecx, 3Fh
0x180112664  ror     rax, cl
0x180112667  mov     cs:AvrfpAPILookupCallbackRoutine, rax
0x18011266e  mov     ecx, edi
0x180112670  mov     cs:AVrfpEnabled, dil
0x180112677  mov     cs:RtlGuardAllowSuppressedCalls, dil
0x18011267e  call    LdrProtectMrdata
0x180112683  call    AVrfpSnapAlreadyLoadedDlls
0x180112688  call    LdrpInitializeTls
0x18011268d  mov     rdi, cs:AVrfpVerifierProvidersList
0x180112694  cmp     rdi, rsi
0x180112697  jz      short loc_1801126C2
0x180112699  mov     rcx, [rdi+20h]
0x18011269d  lea     r8, [rbp+arg_18]
0x1801126a1  xor     edx, edx
0x1801126a3  mov     byte ptr [rbp+arg_18], 0
0x1801126a7  mov     rcx, [rcx+98h]
0x1801126ae  call    LdrpInitializeGraphRecurse
0x1801126b3  mov     ebx, eax
0x1801126b5  test    eax, eax
0x1801126b7  js      loc_1801128BF
0x1801126bd  mov     rdi, [rdi]
0x1801126c0  jmp     short loc_180112694
0x1801126c2  test    byte ptr cs:AVrfpDebug, 8
0x1801126c9  jz      short loc_1801126F8
0x1801126cb  lea     rcx, aAvrfFinalListO; "AVRF: -*- final list of providers -*- "...
0x1801126d2  call    DbgPrint
0x1801126d7  mov     rbx, cs:AVrfpVerifierProvidersList
0x1801126de  jmp     short loc_1801126F3
0x1801126e0  mov     rdx, [rbx+18h]
0x1801126e4  lea     rcx, aAvrfProviderWs_1; "AVRF: provider %ws \n"
0x1801126eb  mov     rbx, [rbx]
0x1801126ee  call    DbgPrint
0x1801126f3  cmp     rbx, rsi
0x1801126f6  jnz     short loc_1801126E0
0x1801126f8  call    AVrfpVerifierStopInitialize
0x1801126fd  mov     rdx, [r14+10h]
0x180112701  lea     r9, [rbp+var_8]
0x180112705  xor     r8d, r8d
0x180112708  lea     ecx, [r8+3]
0x18011270c  call    RtlImageNtHeaderEx
0x180112711  jmp     short loc_180112731
0x180112713  lea     r8, [rbp+arg_18]
0x180112717  mov     byte ptr [rbp+arg_18], 0
0x18011271b  lea     rcx, qword_1801CC798
0x180112722  call    LdrpInitializeGraphRecurse
0x180112727  mov     ebx, eax
0x180112729  test    eax, eax
0x18011272b  js      loc_1801128BF
0x180112731  xor     ebx, ebx
0x180112733  jmp     loc_1801128BF
0x180112738  mov     rsi, [rbp+arg_28]
0x18011273c  test    rsi, rsi
0x18011273f  jnz     short loc_18011274B
0x180112741  mov     ebx, 0C000000Dh
0x180112746  jmp     loc_1801128BF
0x18011274b  mov     qword ptr [rsi], 0
0x180112752  mov     edi, 1
0x180112757  mov     r10d, [r14+0BCh]
0x18011275e  test    r10d, 2000100h
0x180112765  jz      short loc_18011276C
0x180112767  mov     r14d, edi
0x18011276a  jmp     short loc_18011277E
0x18011276c  xor     r14d, r14d
0x18011276f  call    LdrpPayloadRestrictionMitigationsEnabled
0x180112774  test    al, al
0x180112776  lea     ecx, [r14+2]
0x18011277a  cmovnz  r14d, ecx
0x18011277e  bt      r10d, 8
0x180112783  jb      short loc_18011278E
0x180112785  test    r15b, r15b
0x180112788  jnz     short loc_18011278E
0x18011278a  xor     ecx, ecx
0x18011278c  jmp     short loc_180112793
0x18011278e  mov     ecx, 48004h
0x180112793  xor     eax, eax
0x180112795  mov     cs:AVrfpVerifierFlags, ecx
0x18011279b  mov     cs:AVrfpVerifierDllsString, ax
0x1801127a2  lea     r8d, [rax+4]
0x1801127a6  test    rbx, rbx
0x1801127a9  jz      short loc_1801127DD
0x1801127ab  mov     [rsp+40h+var_18], rax
0x1801127b0  lea     r9, [rbp+arg_18]
0x1801127b4  lea     rdx, aVerifierflags; "VerifierFlags"
0x1801127bb  mov     dword ptr [rsp+40h+var_20], r8d
0x1801127c0  mov     rcx, rbx
0x1801127c3  call    RtlQueryImageFileKeyOption
0x1801127c8  mov     ecx, [rbp+arg_18]
0x1801127cb  test    ecx, ecx
0x1801127cd  jz      short loc_1801127D7
0x1801127cf  mov     cs:AVrfpVerifierFlags, ecx
0x1801127d5  jmp     short loc_1801127F1
0x1801127d7  mov     ecx, cs:AVrfpVerifierFlags
0x1801127dd  test    r15b, r15b
0x1801127e0  jz      short loc_1801127E8
0x1801127e2  mov     cs:AVrfpEnabledSystemWide, edi
0x1801127e8  test    rbx, rbx
0x1801127eb  jz      loc_180112874
0x1801127f1  mov     r15d, 4
0x1801127f7  test    r15b, cl
0x1801127fa  jz      short loc_180112823
0x1801127fc  mov     [rsp+40h+var_18], 0
0x180112805  lea     r9, AVrfpHandleTraces
0x18011280c  mov     r8d, r15d
0x18011280f  mov     dword ptr [rsp+40h+var_20], r15d
0x180112814  lea     rdx, aHandletraces; "HandleTraces"
0x18011281b  mov     rcx, rbx
0x18011281e  call    RtlQueryImageFileKeyOption
0x180112823  mov     [rsp+40h+var_18], 0
0x18011282c  lea     r9, AVrfpDebug
0x180112833  mov     r8d, r15d
0x180112836  mov     dword ptr [rsp+40h+var_20], r15d
0x18011283b  lea     rdx, aVerifierdebug; "VerifierDebug"
0x180112842  mov     rcx, rbx
0x180112845  call    RtlQueryImageFileKeyOption
0x18011284a  lea     r9, AVrfpVerifierDllsString
0x180112851  mov     [rsp+40h+var_18], 0
0x18011285a  mov     r8d, edi
0x18011285d  mov     dword ptr [rsp+40h+var_20], 200h
0x180112865  lea     rdx, aVerifierdlls; "VerifierDlls"
0x18011286c  mov     rcx, rbx
0x18011286f  call    RtlQueryImageFileKeyOption
0x180112874  mov     r9, [rbp+arg_20]
0x180112878  lea     r15, AvrfpLoaderEntry
0x18011287f  mov     r8, rbx
0x180112882  mov     [rsp+40h+var_20], r15
0x180112887  mov     rdx, r12
0x18011288a  lea     rcx, VerifierDllString
0x180112891  call    AvrfMiniLoadDll
0x180112896  mov     ebx, eax
0x180112898  test    eax, eax
0x18011289a  js      short loc_1801128BF
0x18011289c  mov     [rsi], r15
0x18011289f  call    AVrfpEnableVerifierOptions
0x1801128a4  mov     ebx, eax
0x1801128a6  test    eax, eax
0x1801128a8  js      short loc_1801128BF
0x1801128aa  xor     ecx, ecx
0x1801128ac  call    LdrProtectMrdata
0x1801128b1  mov     ecx, edi
0x1801128b3  mov     cs:AvrfAppVerifierMode, r14d
0x1801128ba  call    LdrProtectMrdata
0x1801128bf  mov     rsi, [rsp+40h+arg_8]
0x1801128c4  mov     eax, ebx
0x1801128c6  mov     rbx, [rsp+40h+arg_0]
0x1801128cb  add     rsp, 40h
0x1801128cf  pop     r15
0x1801128d1  pop     r14
0x1801128d3  pop     r12
0x1801128d5  pop     rdi
0x1801128d6  pop     rbp
0x1801128d7  retn
```
