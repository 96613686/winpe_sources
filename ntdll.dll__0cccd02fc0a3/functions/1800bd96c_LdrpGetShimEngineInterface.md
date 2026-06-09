# LdrpGetShimEngineInterface

- ea: `0x1800bd96c`
- end: `0x1800bddd5`
- name: `LdrpGetShimEngineInterface`
- size: `1129`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800bbb90`
- `0x1800bd5e0`
- `0x180105288`

## callees

- `0x18001eb80`
- `0x18004c620`
- `0x180050f70`
- `0x180052930`
- `0x180066da0`
- `0x1800bd96c`
- `0x1800cca40`
- `0x180164360`

## string_xrefs

- `0x1800bdd93`: `Could not locate procedure "%s" in the shim engine DLL\n`
- `0x1800bda11`: `SE_ShimDllLoaded`
- `0x1800bdae5`: `SE_DllUnloaded`
- `0x1800bdab0`: `SE_DllLoaded`
- `0x1800bda7b`: `SE_InstallAfterInit`
- `0x1800bda46`: `SE_InstallBeforeInit`
- `0x1800bdb84`: `SE_LdrResolveDllName`
- `0x1800bdb1a`: `SE_LdrEntryRemoved`

## pseudocode

```c
__int64 LdrpGetShimEngineInterface()
{
  size_t v0; // rax
  int ProcedureAddressForCaller; // ebx
  int ProcedureAddress; // eax
  char v3; // cl
  STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  __int64 v6; // [rsp+40h] [rbp-19h] BYREF
  __int64 v7; // [rsp+48h] [rbp-11h] BYREF
  __int64 v8; // [rsp+50h] [rbp-9h] BYREF
  __int64 v9; // [rsp+58h] [rbp-1h] BYREF
  __int64 v10; // [rsp+60h] [rbp+7h] BYREF
  __int64 v11; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v12; // [rsp+70h] [rbp+17h] BYREF
  __int64 v13; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v14; // [rsp+80h] [rbp+27h] BYREF
  __int64 retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v16; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v17; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v19; // [rsp+D8h] [rbp+7Fh] BYREF

  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  DestinationString.Buffer = "SE_InitializeEngine";
  v0 = strlen("SE_InitializeEngine");
  if ( v0 >= 0xFFFF )
    LOWORD(v0) = -2;
  DestinationString.Length = v0;
  DestinationString.MaximumLength = v0 + 1;
  ProcedureAddressForCaller = LdrGetProcedureAddressForCaller(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v16,
                                0,
                                retaddr);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_ShimDllLoaded");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v17,
                                0);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_InstallBeforeInit");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v18,
                                0);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_InstallAfterInit");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v19,
                                0);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_DllLoaded");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v6,
                                0);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_DllUnloaded");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v7,
                                0);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_LdrEntryRemoved");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v8,
                                0);
  if ( ProcedureAddressForCaller < 0 )
    goto LABEL_21;
  RtlInitAnsiString(&DestinationString, "SE_ProcessDying");
  ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                g_pShimEngineModule,
                                (unsigned int)&DestinationString,
                                0,
                                (unsigned int)&v9,
                                0);
  if ( ProcedureAddressForCaller < 0
    || (RtlInitAnsiString(&DestinationString, "SE_LdrResolveDllName"),
        ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                      g_pShimEngineModule,
                                      (unsigned int)&DestinationString,
                                      0,
                                      (unsigned int)&v11,
                                      0),
        ProcedureAddressForCaller < 0)
    || (RtlInitAnsiString(&DestinationString, "SE_GetProcAddressForCaller"),
        ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                      g_pShimEngineModule,
                                      (unsigned int)&DestinationString,
                                      0,
                                      (unsigned int)&v10,
                                      0),
        ProcedureAddressForCaller < 0)
    || (RtlInitAnsiString(&DestinationString, "ApphelpCheckModule"),
        ProcedureAddressForCaller = LdrGetProcedureAddressEx(
                                      g_pShimEngineModule,
                                      (unsigned int)&DestinationString,
                                      0,
                                      (unsigned int)&v12,
                                      0),
        ProcedureAddressForCaller < 0) )
  {
LABEL_21:
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      3313,
      (int)"LdrpGetShimEngineInterface",
      0,
      "Could not locate procedure \"%s\" in the shim engine DLL\n",
      (char)DestinationString.Buffer);
    g_ShimsEnabled = 0;
    LdrUnloadDll(g_pShimEngineModule);
    g_pShimEngineModule = 0;
  }
  else
  {
    RtlInitAnsiString(&DestinationString, "ApphelpQueryModSettingsAlloc");
    LdrGetProcedureAddressEx(g_pShimEngineModule, (unsigned int)&DestinationString, 0, (unsigned int)&v13, 0);
    RtlInitAnsiString(&DestinationString, "ApphelpQueryModSettings2Alloc");
    ProcedureAddress = LdrGetProcedureAddressEx(
                         g_pShimEngineModule,
                         (unsigned int)&DestinationString,
                         0,
                         (unsigned int)&v14,
                         0);
    ProcedureAddressForCaller = 0;
    if ( ProcedureAddress >= 0 )
      ProcedureAddressForCaller = ProcedureAddress;
    LdrProtectMrdata(0);
    v3 = MEMORY[0x7FFE0330] & 0x3F;
    g_pfnSE_InitializeEngine = __ROR8__(v16 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_ShimDllLoaded = __ROR8__(v17 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_InstallBeforeInit = __ROR8__(v18 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_InstallAfterInit = __ROR8__(v19 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_DllLoaded = __ROR8__(v6 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_DllUnloaded = __ROR8__(v7 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_LdrEntryRemoved = __ROR8__(v8 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_ProcessDying = __ROR8__(v9 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_GetProcAddressForCaller = __ROR8__(v10 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnSE_LdrResolveDllName = __ROR8__(v11 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    g_pfnApphelpCheckModuleProc = __ROR8__(v12 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
    if ( v13 )
      g_pfnApphelpQueryModSettingsAllocProc = __ROR8__(v13 ^ MEMORY[0x7FFE0330], v3);
    if ( v14 )
      g_pfnApphelpQueryModSettings2AllocProc = __ROR8__(v14 ^ MEMORY[0x7FFE0330], v3);
    LdrProtectMrdata(1);
  }
  return (unsigned int)ProcedureAddressForCaller;
}

```

## disassembly

```asm
0x1800bd96c  push    rbp
0x1800bd96e  push    rbx
0x1800bd96f  push    rsi
0x1800bd970  push    rdi
0x1800bd971  lea     rbp, [rsp-3Fh]
0x1800bd976  sub     rsp, 98h
0x1800bd97d  xor     edi, edi
0x1800bd97f  lea     rcx, Str; "SE_InitializeEngine"
0x1800bd986  mov     [rbp+57h+arg_0], rdi
0x1800bd98a  mov     [rbp+57h+arg_8], rdi
0x1800bd98e  mov     [rbp+57h+arg_10], rdi
0x1800bd992  mov     [rbp+57h+arg_18], rdi
0x1800bd996  mov     [rbp+57h+var_70], rdi
0x1800bd99a  mov     [rbp+57h+var_68], rdi
0x1800bd99e  mov     [rbp+57h+var_60], rdi
0x1800bd9a2  mov     [rbp+57h+var_58], rdi
0x1800bd9a6  mov     [rbp+57h+var_48], rdi
0x1800bd9aa  mov     [rbp+57h+var_50], rdi
0x1800bd9ae  mov     [rbp+57h+var_40], rdi
0x1800bd9b2  mov     [rbp+57h+var_38], rdi
0x1800bd9b6  mov     [rbp+57h+var_30], rdi
0x1800bd9ba  mov     dword ptr [rbp+57h+DestinationString+4], edi
0x1800bd9bd  mov     [rbp+57h+DestinationString.Buffer], rcx
0x1800bd9c1  call    strlen
0x1800bd9c6  cmp     rax, 0FFFFh
0x1800bd9cc  lea     esi, [rdi+1]
0x1800bd9cf  mov     ecx, 0FFFEh
0x1800bd9d4  lea     r9, [rbp+57h+arg_0]
0x1800bd9d8  cmovnb  rax, rcx
0x1800bd9dc  lea     rdx, [rbp+57h+DestinationString]
0x1800bd9e0  mov     rcx, cs:g_pShimEngineModule
0x1800bd9e7  xor     r8d, r8d
0x1800bd9ea  mov     [rbp+57h+DestinationString.Length], ax
0x1800bd9ee  add     ax, si
0x1800bd9f1  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x1800bd9f5  mov     rax, [rbp+5Fh]
0x1800bd9f9  mov     qword ptr [rsp+0B0h+ArgList], rax
0x1800bd9fe  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bda02  call    LdrGetProcedureAddressForCaller
0x1800bda07  mov     ebx, eax
0x1800bda09  test    eax, eax
0x1800bda0b  js      loc_1800BDD7C
0x1800bda11  lea     rdx, aSeShimdllloade; "SE_ShimDllLoaded"
0x1800bda18  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bda1c  call    RtlInitAnsiString
0x1800bda21  mov     rcx, cs:g_pShimEngineModule
0x1800bda28  lea     r9, [rbp+57h+arg_8]
0x1800bda2c  xor     r8d, r8d
0x1800bda2f  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bda33  lea     rdx, [rbp+57h+DestinationString]
0x1800bda37  call    LdrGetProcedureAddressEx
0x1800bda3c  mov     ebx, eax
0x1800bda3e  test    eax, eax
0x1800bda40  js      loc_1800BDD7C
0x1800bda46  lea     rdx, aSeInstallbefor; "SE_InstallBeforeInit"
0x1800bda4d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bda51  call    RtlInitAnsiString
0x1800bda56  mov     rcx, cs:g_pShimEngineModule
0x1800bda5d  lea     r9, [rbp+57h+arg_10]
0x1800bda61  xor     r8d, r8d
0x1800bda64  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bda68  lea     rdx, [rbp+57h+DestinationString]
0x1800bda6c  call    LdrGetProcedureAddressEx
0x1800bda71  mov     ebx, eax
0x1800bda73  test    eax, eax
0x1800bda75  js      loc_1800BDD7C
0x1800bda7b  lea     rdx, aSeInstallafter; "SE_InstallAfterInit"
0x1800bda82  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bda86  call    RtlInitAnsiString
0x1800bda8b  mov     rcx, cs:g_pShimEngineModule
0x1800bda92  lea     r9, [rbp+57h+arg_18]
0x1800bda96  xor     r8d, r8d
0x1800bda99  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bda9d  lea     rdx, [rbp+57h+DestinationString]
0x1800bdaa1  call    LdrGetProcedureAddressEx
0x1800bdaa6  mov     ebx, eax
0x1800bdaa8  test    eax, eax
0x1800bdaaa  js      loc_1800BDD7C
0x1800bdab0  lea     rdx, aSeDllloaded; "SE_DllLoaded"
0x1800bdab7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdabb  call    RtlInitAnsiString
0x1800bdac0  mov     rcx, cs:g_pShimEngineModule
0x1800bdac7  lea     r9, [rbp+57h+var_70]
0x1800bdacb  xor     r8d, r8d
0x1800bdace  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdad2  lea     rdx, [rbp+57h+DestinationString]
0x1800bdad6  call    LdrGetProcedureAddressEx
0x1800bdadb  mov     ebx, eax
0x1800bdadd  test    eax, eax
0x1800bdadf  js      loc_1800BDD7C
0x1800bdae5  lea     rdx, aSeDllunloaded; "SE_DllUnloaded"
0x1800bdaec  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdaf0  call    RtlInitAnsiString
0x1800bdaf5  mov     rcx, cs:g_pShimEngineModule
0x1800bdafc  lea     r9, [rbp+57h+var_68]
0x1800bdb00  xor     r8d, r8d
0x1800bdb03  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdb07  lea     rdx, [rbp+57h+DestinationString]
0x1800bdb0b  call    LdrGetProcedureAddressEx
0x1800bdb10  mov     ebx, eax
0x1800bdb12  test    eax, eax
0x1800bdb14  js      loc_1800BDD7C
0x1800bdb1a  lea     rdx, aSeLdrentryremo; "SE_LdrEntryRemoved"
0x1800bdb21  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdb25  call    RtlInitAnsiString
0x1800bdb2a  mov     rcx, cs:g_pShimEngineModule
0x1800bdb31  lea     r9, [rbp+57h+var_60]
0x1800bdb35  xor     r8d, r8d
0x1800bdb38  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdb3c  lea     rdx, [rbp+57h+DestinationString]
0x1800bdb40  call    LdrGetProcedureAddressEx
0x1800bdb45  mov     ebx, eax
0x1800bdb47  test    eax, eax
0x1800bdb49  js      loc_1800BDD7C
0x1800bdb4f  lea     rdx, aSeProcessdying; "SE_ProcessDying"
0x1800bdb56  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdb5a  call    RtlInitAnsiString
0x1800bdb5f  mov     rcx, cs:g_pShimEngineModule
0x1800bdb66  lea     r9, [rbp+57h+var_58]
0x1800bdb6a  xor     r8d, r8d
0x1800bdb6d  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdb71  lea     rdx, [rbp+57h+DestinationString]
0x1800bdb75  call    LdrGetProcedureAddressEx
0x1800bdb7a  mov     ebx, eax
0x1800bdb7c  test    eax, eax
0x1800bdb7e  js      loc_1800BDD7C
0x1800bdb84  lea     rdx, aSeLdrresolvedl; "SE_LdrResolveDllName"
0x1800bdb8b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdb8f  call    RtlInitAnsiString
0x1800bdb94  mov     rcx, cs:g_pShimEngineModule
0x1800bdb9b  lea     r9, [rbp+57h+var_48]
0x1800bdb9f  xor     r8d, r8d
0x1800bdba2  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdba6  lea     rdx, [rbp+57h+DestinationString]
0x1800bdbaa  call    LdrGetProcedureAddressEx
0x1800bdbaf  mov     ebx, eax
0x1800bdbb1  test    eax, eax
0x1800bdbb3  js      loc_1800BDD7C
0x1800bdbb9  lea     rdx, aSeGetprocaddre; "SE_GetProcAddressForCaller"
0x1800bdbc0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdbc4  call    RtlInitAnsiString
0x1800bdbc9  mov     rcx, cs:g_pShimEngineModule
0x1800bdbd0  lea     r9, [rbp+57h+var_50]
0x1800bdbd4  xor     r8d, r8d
0x1800bdbd7  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdbdb  lea     rdx, [rbp+57h+DestinationString]
0x1800bdbdf  call    LdrGetProcedureAddressEx
0x1800bdbe4  mov     ebx, eax
0x1800bdbe6  test    eax, eax
0x1800bdbe8  js      loc_1800BDD7C
0x1800bdbee  lea     rdx, aApphelpcheckmo; "ApphelpCheckModule"
0x1800bdbf5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdbf9  call    RtlInitAnsiString
0x1800bdbfe  mov     rcx, cs:g_pShimEngineModule
0x1800bdc05  lea     r9, [rbp+57h+var_40]
0x1800bdc09  xor     r8d, r8d
0x1800bdc0c  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdc10  lea     rdx, [rbp+57h+DestinationString]
0x1800bdc14  call    LdrGetProcedureAddressEx
0x1800bdc19  mov     ebx, eax
0x1800bdc1b  test    eax, eax
0x1800bdc1d  js      loc_1800BDD7C
0x1800bdc23  lea     rdx, aApphelpquerymo; "ApphelpQueryModSettingsAlloc"
0x1800bdc2a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdc2e  call    RtlInitAnsiString
0x1800bdc33  mov     rcx, cs:g_pShimEngineModule
0x1800bdc3a  lea     r9, [rbp+57h+var_38]
0x1800bdc3e  xor     r8d, r8d
0x1800bdc41  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdc45  lea     rdx, [rbp+57h+DestinationString]
0x1800bdc49  call    LdrGetProcedureAddressEx
0x1800bdc4e  lea     rdx, aApphelpquerymo_0; "ApphelpQueryModSettings2Alloc"
0x1800bdc55  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800bdc59  call    RtlInitAnsiString
0x1800bdc5e  mov     rcx, cs:g_pShimEngineModule
0x1800bdc65  lea     r9, [rbp+57h+var_30]
0x1800bdc69  xor     r8d, r8d
0x1800bdc6c  mov     dword ptr [rsp+0B0h+Format], edi
0x1800bdc70  lea     rdx, [rbp+57h+DestinationString]
0x1800bdc74  call    LdrGetProcedureAddressEx
0x1800bdc79  test    eax, eax
0x1800bdc7b  mov     ebx, edi
0x1800bdc7d  cmovns  ebx, eax
0x1800bdc80  xor     ecx, ecx
0x1800bdc82  call    LdrProtectMrdata
0x1800bdc87  mov     edx, ds:7FFE0330h
0x1800bdc8e  mov     r8, [rbp+57h+var_38]
0x1800bdc92  mov     ecx, edx
0x1800bdc94  and     ecx, 3Fh
0x1800bdc97  mov     eax, edx
0x1800bdc99  xor     rax, [rbp+57h+arg_0]
0x1800bdc9d  ror     rax, cl
0x1800bdca0  mov     cs:g_pfnSE_InitializeEngine, rax
0x1800bdca7  mov     eax, edx
0x1800bdca9  xor     rax, [rbp+57h+arg_8]
0x1800bdcad  ror     rax, cl
0x1800bdcb0  mov     cs:g_pfnSE_ShimDllLoaded, rax
0x1800bdcb7  mov     eax, edx
0x1800bdcb9  xor     rax, [rbp+57h+arg_10]
0x1800bdcbd  ror     rax, cl
0x1800bdcc0  mov     cs:g_pfnSE_InstallBeforeInit, rax
0x1800bdcc7  mov     eax, edx
0x1800bdcc9  xor     rax, [rbp+57h+arg_18]
0x1800bdccd  ror     rax, cl
0x1800bdcd0  mov     cs:g_pfnSE_InstallAfterInit, rax
0x1800bdcd7  mov     eax, edx
0x1800bdcd9  xor     rax, [rbp+57h+var_70]
0x1800bdcdd  ror     rax, cl
0x1800bdce0  mov     cs:g_pfnSE_DllLoaded, rax
0x1800bdce7  mov     eax, edx
0x1800bdce9  xor     rax, [rbp+57h+var_68]
0x1800bdced  ror     rax, cl
0x1800bdcf0  mov     cs:g_pfnSE_DllUnloaded, rax
0x1800bdcf7  mov     eax, edx
0x1800bdcf9  xor     rax, [rbp+57h+var_60]
0x1800bdcfd  ror     rax, cl
0x1800bdd00  mov     cs:g_pfnSE_LdrEntryRemoved, rax
0x1800bdd07  mov     eax, edx
0x1800bdd09  xor     rax, [rbp+57h+var_58]
0x1800bdd0d  ror     rax, cl
0x1800bdd10  mov     cs:g_pfnSE_ProcessDying, rax
0x1800bdd17  mov     eax, edx
0x1800bdd19  xor     rax, [rbp+57h+var_50]
0x1800bdd1d  ror     rax, cl
0x1800bdd20  mov     cs:g_pfnSE_GetProcAddressForCaller, rax
0x1800bdd27  mov     eax, edx
0x1800bdd29  xor     rax, [rbp+57h+var_48]
0x1800bdd2d  ror     rax, cl
0x1800bdd30  mov     cs:g_pfnSE_LdrResolveDllName, rax
0x1800bdd37  mov     eax, edx
0x1800bdd39  xor     rax, [rbp+57h+var_40]
0x1800bdd3d  ror     rax, cl
0x1800bdd40  mov     cs:g_pfnApphelpCheckModuleProc, rax
0x1800bdd47  test    r8, r8
0x1800bdd4a  jz      short loc_1800BDD5B
0x1800bdd4c  mov     eax, edx
0x1800bdd4e  xor     rax, r8
0x1800bdd51  ror     rax, cl
0x1800bdd54  mov     cs:g_pfnApphelpQueryModSettingsAllocProc, rax
0x1800bdd5b  mov     rax, [rbp+57h+var_30]
0x1800bdd5f  test    rax, rax
0x1800bdd62  jz      short loc_1800BDD71
0x1800bdd64  xor     rdx, rax
0x1800bdd67  ror     rdx, cl
0x1800bdd6a  mov     cs:g_pfnApphelpQueryModSettings2AllocProc, rdx
0x1800bdd71  mov     ecx, esi
0x1800bdd73  call    LdrProtectMrdata
0x1800bdd78  test    ebx, ebx
0x1800bdd7a  jns     short loc_1800BDDC6
0x1800bdd7c  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1800bdd80  lea     r8, aLdrpgetshimeng; "LdrpGetShimEngineInterface"
0x1800bdd87  mov     qword ptr [rsp+0B0h+ArgList], rax; ArgList
0x1800bdd8c  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bdd93  lea     rax, aCouldNotLocate; "Could not locate procedure \"%s\" in th"...
0x1800bdd9a  xor     r9d, r9d; int
0x1800bdd9d  mov     edx, 0CF1h; int
0x1800bdda2  mov     [rsp+0B0h+Format], rax; Format
0x1800bdda7  call    LdrpLogInternal
0x1800bddac  mov     rcx, cs:g_pShimEngineModule
0x1800bddb3  mov     cs:g_ShimsEnabled, dil
0x1800bddba  call    LdrUnloadDll
0x1800bddbf  mov     cs:g_pShimEngineModule, rdi
0x1800bddc6  mov     eax, ebx
0x1800bddc8  add     rsp, 98h
0x1800bddcf  pop     rdi
0x1800bddd0  pop     rsi
0x1800bddd1  pop     rbx
0x1800bddd2  pop     rbp
0x1800bddd3  retn
```
