# AVrfInitializeVerifier

- ea: `0x180113878`
- end: `0x180113cc9`
- name: `AVrfInitializeVerifier`
- size: `1105`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x180050718`
- `0x1800d5428`

## callees

- `0x180007060`
- `0x18001a080`
- `0x18001f070`
- `0x18002a2a8`
- `0x180058fb0`
- `0x18006d950`
- `0x1800709e0`
- `0x180083780`
- `0x180085904`
- `0x1800c0088`
- `0x1800c3cd8`
- `0x1800d4620`
- `0x1800d5bac`
- `0x1800e634c`
- `0x180110840`
- `0x180113878`
- `0x18011f0a0`
- `0x18012014c`
- `0x18012330c`
- `0x1801379c4`

## string_xrefs

- `0x180113c55`: `VerifierDlls`

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
0x180113878  mov     [rsp-28h+arg_0], rbx
0x18011387d  mov     [rsp-28h+arg_8], rsi
0x180113882  push    rbp
0x180113883  push    rdi
0x180113884  push    r12
0x180113886  push    r14
0x180113888  push    r15
0x18011388a  mov     rbp, rsp
0x18011388d  sub     rsp, 40h
0x180113891  mov     r14, gs:60h
0x18011389a  mov     rbx, r8
0x18011389d  mov     [rbp+var_10], 0
0x1801138a5  mov     r12, rdx
0x1801138a8  mov     [rbp+var_8], 0
0x1801138b0  mov     r15b, cl
0x1801138b3  mov     [rbp+arg_18], 0
0x1801138ba  test    r9d, r9d
0x1801138bd  jz      loc_180113B28
0x1801138c3  cmp     r9d, 1
0x1801138c7  jnz     loc_180113B21
0x1801138cd  lea     rsi, AVrfpVerifierProvidersList
0x1801138d4  xor     r8d, r8d
0x1801138d7  xor     edx, edx
0x1801138d9  mov     cs:qword_1801CC638, rsi
0x1801138e0  lea     rcx, AVrfpVerifierLock
0x1801138e7  mov     cs:AVrfpVerifierProvidersList, rsi
0x1801138ee  call    RtlInitializeCriticalSectionEx
0x1801138f3  mov     ebx, eax
0x1801138f5  test    eax, eax
0x1801138f7  js      loc_180113CAF
0x1801138fd  mov     ecx, 2
0x180113902  xor     edx, edx
0x180113904  cmp     cs:AvrfAppVerifierMode, ecx
0x18011390a  jz      loc_180113B03
0x180113910  mov     rcx, gs:40h
0x180113919  lea     ebx, [rdx+5Dh]
0x18011391c  mov     r9, cs:qword_1801CA8D0
0x180113923  lea     r8, aAvrfWsPid0xXFl; "AVRF: %ws: pid 0x%X: flags 0x%X: applic"...
0x18011392a  mov     eax, cs:AVrfpVerifierFlags
0x180113930  mov     dword ptr [rsp+40h+var_18], eax
0x180113934  mov     dword ptr [rsp+40h+var_20], ecx
0x180113938  mov     ecx, ebx
0x18011393a  mov     r9, [r9+60h]
0x18011393e  call    DbgPrintEx
0x180113943  call    AVrfpParseVerifierDllsString
0x180113948  test    eax, eax
0x18011394a  jns     short loc_1801139A0
0x18011394c  mov     rax, gs:40h
0x180113955  lea     r8, aAvrfWsPid0xXAp; "AVRF: %ws: pid 0x%X: application verifi"...
0x18011395c  mov     r9, cs:qword_1801CA8D0
0x180113963  xor     edx, edx
0x180113965  mov     ecx, ebx
0x180113967  mov     dword ptr [rsp+40h+var_20], eax
0x18011396b  mov     r9, [r9+60h]
0x18011396f  call    DbgPrintEx
0x180113974  mov     rax, gs:60h
0x18011397d  mov     ebx, 0C0000001h
0x180113982  mov     ecx, [rax+0BCh]
0x180113988  mov     rax, gs:60h
0x180113991  btr     ecx, 8
0x180113995  mov     [rax+0BCh], ecx
0x18011399b  jmp     loc_180113CAF
0x1801139a0  mov     rbx, cs:AVrfpVerifierProvidersList
0x1801139a7  cmp     rbx, rsi
0x1801139aa  jz      short loc_1801139C7
0x1801139ac  mov     rcx, rbx
0x1801139af  call    AVrfpLoadAndInitializeProvider
0x1801139b4  test    al, al
0x1801139b6  jz      short loc_1801139BD
0x1801139b8  mov     rbx, [rbx]
0x1801139bb  jmp     short loc_1801139A7
0x1801139bd  mov     ebx, 0C0000142h
0x1801139c2  jmp     loc_180113CAF
0x1801139c7  call    AVrfpChainDuplicateVerificationLayers
0x1801139cc  lea     r9, [rbp+var_10]
0x1801139d0  mov     [rsp+40h+var_20], 0
0x1801139d9  xor     r8d, r8d
0x1801139dc  lea     rcx, VrfcoreDllString
0x1801139e3  xor     edx, edx
0x1801139e5  call    LdrpFindLoadedDllByName
0x1801139ea  mov     ebx, eax
0x1801139ec  test    eax, eax
0x1801139ee  js      short loc_1801139FF
0x1801139f0  mov     rcx, [rbp+var_10]
0x1801139f4  mov     rbx, [rcx+30h]
0x1801139f8  call    LdrpDereferenceModule
0x1801139fd  jmp     short loc_180113A11
0x1801139ff  cmp     eax, 0C0000135h
0x180113a04  jnz     loc_180113CAF
0x180113a0a  mov     rbx, cs:qword_1801CC690
0x180113a11  mov     edi, 1
0x180113a16  lea     r9, [rbp+var_8]
0x180113a1a  xor     r8d, r8d
0x180113a1d  mov     dword ptr [rsp+40h+var_20], edi
0x180113a21  lea     rdx, AvrfpAPILookupCallbackName
0x180113a28  mov     rcx, rbx
0x180113a2b  call    LdrGetProcedureAddressEx
0x180113a30  xor     ecx, ecx
0x180113a32  mov     ebx, eax
0x180113a34  call    LdrProtectMrdata
0x180113a39  test    ebx, ebx
0x180113a3b  js      short loc_180113A5E
0x180113a3d  mov     eax, ds:7FFE0330h
0x180113a44  mov     ecx, eax
0x180113a46  mov     cs:AvrfpAPILookupCallbacksEnabled, dil
0x180113a4d  xor     rax, [rbp+var_8]
0x180113a51  and     ecx, 3Fh
0x180113a54  ror     rax, cl
0x180113a57  mov     cs:AvrfpAPILookupCallbackRoutine, rax
0x180113a5e  mov     ecx, edi
0x180113a60  mov     cs:AVrfpEnabled, dil
0x180113a67  mov     cs:RtlGuardAllowSuppressedCalls, dil
0x180113a6e  call    LdrProtectMrdata
0x180113a73  call    AVrfpSnapAlreadyLoadedDlls
0x180113a78  call    LdrpInitializeTls
0x180113a7d  mov     rdi, cs:AVrfpVerifierProvidersList
0x180113a84  cmp     rdi, rsi
0x180113a87  jz      short loc_180113AB2
0x180113a89  mov     rcx, [rdi+20h]
0x180113a8d  lea     r8, [rbp+arg_18]
0x180113a91  xor     edx, edx
0x180113a93  mov     byte ptr [rbp+arg_18], 0
0x180113a97  mov     rcx, [rcx+98h]
0x180113a9e  call    LdrpInitializeGraphRecurse
0x180113aa3  mov     ebx, eax
0x180113aa5  test    eax, eax
0x180113aa7  js      loc_180113CAF
0x180113aad  mov     rdi, [rdi]
0x180113ab0  jmp     short loc_180113A84
0x180113ab2  test    byte ptr cs:AVrfpDebug, 8
0x180113ab9  jz      short loc_180113AE8
0x180113abb  lea     rcx, aAvrfFinalListO; "AVRF: -*- final list of providers -*- "...
0x180113ac2  call    DbgPrint
0x180113ac7  mov     rbx, cs:AVrfpVerifierProvidersList
0x180113ace  jmp     short loc_180113AE3
0x180113ad0  mov     rdx, [rbx+18h]
0x180113ad4  lea     rcx, aAvrfProviderWs_1; "AVRF: provider %ws \n"
0x180113adb  mov     rbx, [rbx]
0x180113ade  call    DbgPrint
0x180113ae3  cmp     rbx, rsi
0x180113ae6  jnz     short loc_180113AD0
0x180113ae8  call    AVrfpVerifierStopInitialize
0x180113aed  mov     rdx, [r14+10h]
0x180113af1  lea     r9, [rbp+var_8]
0x180113af5  xor     r8d, r8d
0x180113af8  lea     ecx, [r8+3]
0x180113afc  call    RtlImageNtHeaderEx
0x180113b01  jmp     short loc_180113B21
0x180113b03  lea     r8, [rbp+arg_18]
0x180113b07  mov     byte ptr [rbp+arg_18], 0
0x180113b0b  lea     rcx, qword_1801CC798
0x180113b12  call    LdrpInitializeGraphRecurse
0x180113b17  mov     ebx, eax
0x180113b19  test    eax, eax
0x180113b1b  js      loc_180113CAF
0x180113b21  xor     ebx, ebx
0x180113b23  jmp     loc_180113CAF
0x180113b28  mov     rsi, [rbp+arg_28]
0x180113b2c  test    rsi, rsi
0x180113b2f  jnz     short loc_180113B3B
0x180113b31  mov     ebx, 0C000000Dh
0x180113b36  jmp     loc_180113CAF
0x180113b3b  mov     qword ptr [rsi], 0
0x180113b42  mov     edi, 1
0x180113b47  mov     r10d, [r14+0BCh]
0x180113b4e  test    r10d, 2000100h
0x180113b55  jz      short loc_180113B5C
0x180113b57  mov     r14d, edi
0x180113b5a  jmp     short loc_180113B6E
0x180113b5c  xor     r14d, r14d
0x180113b5f  call    LdrpPayloadRestrictionMitigationsEnabled
0x180113b64  test    al, al
0x180113b66  lea     ecx, [r14+2]
0x180113b6a  cmovnz  r14d, ecx
0x180113b6e  bt      r10d, 8
0x180113b73  jb      short loc_180113B7E
0x180113b75  test    r15b, r15b
0x180113b78  jnz     short loc_180113B7E
0x180113b7a  xor     ecx, ecx
0x180113b7c  jmp     short loc_180113B83
0x180113b7e  mov     ecx, 48004h
0x180113b83  xor     eax, eax
0x180113b85  mov     cs:AVrfpVerifierFlags, ecx
0x180113b8b  mov     cs:AVrfpVerifierDllsString, ax
0x180113b92  lea     r8d, [rax+4]
0x180113b96  test    rbx, rbx
0x180113b99  jz      short loc_180113BCD
0x180113b9b  mov     [rsp+40h+var_18], rax
0x180113ba0  lea     r9, [rbp+arg_18]
0x180113ba4  lea     rdx, aVerifierflags; "VerifierFlags"
0x180113bab  mov     dword ptr [rsp+40h+var_20], r8d
0x180113bb0  mov     rcx, rbx
0x180113bb3  call    RtlQueryImageFileKeyOption
0x180113bb8  mov     ecx, [rbp+arg_18]
0x180113bbb  test    ecx, ecx
0x180113bbd  jz      short loc_180113BC7
0x180113bbf  mov     cs:AVrfpVerifierFlags, ecx
0x180113bc5  jmp     short loc_180113BE1
0x180113bc7  mov     ecx, cs:AVrfpVerifierFlags
0x180113bcd  test    r15b, r15b
0x180113bd0  jz      short loc_180113BD8
0x180113bd2  mov     cs:AVrfpEnabledSystemWide, edi
0x180113bd8  test    rbx, rbx
0x180113bdb  jz      loc_180113C64
0x180113be1  mov     r15d, 4
0x180113be7  test    r15b, cl
0x180113bea  jz      short loc_180113C13
0x180113bec  mov     [rsp+40h+var_18], 0
0x180113bf5  lea     r9, AVrfpHandleTraces
0x180113bfc  mov     r8d, r15d
0x180113bff  mov     dword ptr [rsp+40h+var_20], r15d
0x180113c04  lea     rdx, aHandletraces; "HandleTraces"
0x180113c0b  mov     rcx, rbx
0x180113c0e  call    RtlQueryImageFileKeyOption
0x180113c13  mov     [rsp+40h+var_18], 0
0x180113c1c  lea     r9, AVrfpDebug
0x180113c23  mov     r8d, r15d
0x180113c26  mov     dword ptr [rsp+40h+var_20], r15d
0x180113c2b  lea     rdx, aVerifierdebug; "VerifierDebug"
0x180113c32  mov     rcx, rbx
0x180113c35  call    RtlQueryImageFileKeyOption
0x180113c3a  lea     r9, AVrfpVerifierDllsString
0x180113c41  mov     [rsp+40h+var_18], 0
0x180113c4a  mov     r8d, edi
0x180113c4d  mov     dword ptr [rsp+40h+var_20], 200h
0x180113c55  lea     rdx, aVerifierdlls; "VerifierDlls"
0x180113c5c  mov     rcx, rbx
0x180113c5f  call    RtlQueryImageFileKeyOption
0x180113c64  mov     r9, [rbp+arg_20]
0x180113c68  lea     r15, AvrfpLoaderEntry
0x180113c6f  mov     r8, rbx
0x180113c72  mov     [rsp+40h+var_20], r15
0x180113c77  mov     rdx, r12
0x180113c7a  lea     rcx, VerifierDllString
0x180113c81  call    AvrfMiniLoadDll
0x180113c86  mov     ebx, eax
0x180113c88  test    eax, eax
0x180113c8a  js      short loc_180113CAF
0x180113c8c  mov     [rsi], r15
0x180113c8f  call    AVrfpEnableVerifierOptions
0x180113c94  mov     ebx, eax
0x180113c96  test    eax, eax
0x180113c98  js      short loc_180113CAF
0x180113c9a  xor     ecx, ecx
0x180113c9c  call    LdrProtectMrdata
0x180113ca1  mov     ecx, edi
0x180113ca3  mov     cs:AvrfAppVerifierMode, r14d
0x180113caa  call    LdrProtectMrdata
0x180113caf  mov     rsi, [rsp+40h+arg_8]
0x180113cb4  mov     eax, ebx
0x180113cb6  mov     rbx, [rsp+40h+arg_0]
0x180113cbb  add     rsp, 40h
0x180113cbf  pop     r15
0x180113cc1  pop     r14
0x180113cc3  pop     r12
0x180113cc5  pop     rdi
0x180113cc6  pop     rbp
0x180113cc7  retn
```
