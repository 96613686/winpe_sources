# LdrpGetShimEngineInterface

- ea: `0x1800c1c4c`
- end: `0x1800c20b5`
- name: `LdrpGetShimEngineInterface`
- size: `1129`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800bfe70`
- `0x1800c18c0`
- `0x1801060b8`

## callees

- `0x18001eb80`
- `0x180069220`
- `0x18006d950`
- `0x18006f310`
- `0x180083780`
- `0x1800c1c4c`
- `0x1800ce5d0`
- `0x180164b60`

## string_xrefs

- `0x1800c2073`: `Could not locate procedure "%s" in the shim engine DLL\n`
- `0x1800c1d90`: `SE_DllLoaded`
- `0x1800c1d5b`: `SE_InstallAfterInit`
- `0x1800c1d26`: `SE_InstallBeforeInit`
- `0x1800c1cf1`: `SE_ShimDllLoaded`
- `0x1800c1e64`: `SE_LdrResolveDllName`
- `0x1800c1dfa`: `SE_LdrEntryRemoved`
- `0x1800c1dc5`: `SE_DllUnloaded`

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
0x1800c1c4c  push    rbp
0x1800c1c4e  push    rbx
0x1800c1c4f  push    rsi
0x1800c1c50  push    rdi
0x1800c1c51  lea     rbp, [rsp-3Fh]
0x1800c1c56  sub     rsp, 98h
0x1800c1c5d  xor     edi, edi
0x1800c1c5f  lea     rcx, Str; "SE_InitializeEngine"
0x1800c1c66  mov     [rbp+57h+arg_0], rdi
0x1800c1c6a  mov     [rbp+57h+arg_8], rdi
0x1800c1c6e  mov     [rbp+57h+arg_10], rdi
0x1800c1c72  mov     [rbp+57h+arg_18], rdi
0x1800c1c76  mov     [rbp+57h+var_70], rdi
0x1800c1c7a  mov     [rbp+57h+var_68], rdi
0x1800c1c7e  mov     [rbp+57h+var_60], rdi
0x1800c1c82  mov     [rbp+57h+var_58], rdi
0x1800c1c86  mov     [rbp+57h+var_48], rdi
0x1800c1c8a  mov     [rbp+57h+var_50], rdi
0x1800c1c8e  mov     [rbp+57h+var_40], rdi
0x1800c1c92  mov     [rbp+57h+var_38], rdi
0x1800c1c96  mov     [rbp+57h+var_30], rdi
0x1800c1c9a  mov     dword ptr [rbp+57h+DestinationString+4], edi
0x1800c1c9d  mov     [rbp+57h+DestinationString.Buffer], rcx
0x1800c1ca1  call    strlen
0x1800c1ca6  cmp     rax, 0FFFFh
0x1800c1cac  lea     esi, [rdi+1]
0x1800c1caf  mov     ecx, 0FFFEh
0x1800c1cb4  lea     r9, [rbp+57h+arg_0]
0x1800c1cb8  cmovnb  rax, rcx
0x1800c1cbc  lea     rdx, [rbp+57h+DestinationString]
0x1800c1cc0  mov     rcx, cs:g_pShimEngineModule
0x1800c1cc7  xor     r8d, r8d
0x1800c1cca  mov     [rbp+57h+DestinationString.Length], ax
0x1800c1cce  add     ax, si
0x1800c1cd1  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x1800c1cd5  mov     rax, [rbp+5Fh]
0x1800c1cd9  mov     qword ptr [rsp+0B0h+ArgList], rax
0x1800c1cde  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1ce2  call    LdrGetProcedureAddressForCaller
0x1800c1ce7  mov     ebx, eax
0x1800c1ce9  test    eax, eax
0x1800c1ceb  js      loc_1800C205C
0x1800c1cf1  lea     rdx, SourceString; "SE_ShimDllLoaded"
0x1800c1cf8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1cfc  call    RtlInitAnsiString
0x1800c1d01  mov     rcx, cs:g_pShimEngineModule
0x1800c1d08  lea     r9, [rbp+57h+arg_8]
0x1800c1d0c  xor     r8d, r8d
0x1800c1d0f  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1d13  lea     rdx, [rbp+57h+DestinationString]
0x1800c1d17  call    LdrGetProcedureAddressEx
0x1800c1d1c  mov     ebx, eax
0x1800c1d1e  test    eax, eax
0x1800c1d20  js      loc_1800C205C
0x1800c1d26  lea     rdx, aSeInstallbefor; "SE_InstallBeforeInit"
0x1800c1d2d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1d31  call    RtlInitAnsiString
0x1800c1d36  mov     rcx, cs:g_pShimEngineModule
0x1800c1d3d  lea     r9, [rbp+57h+arg_10]
0x1800c1d41  xor     r8d, r8d
0x1800c1d44  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1d48  lea     rdx, [rbp+57h+DestinationString]
0x1800c1d4c  call    LdrGetProcedureAddressEx
0x1800c1d51  mov     ebx, eax
0x1800c1d53  test    eax, eax
0x1800c1d55  js      loc_1800C205C
0x1800c1d5b  lea     rdx, aSeInstallafter; "SE_InstallAfterInit"
0x1800c1d62  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1d66  call    RtlInitAnsiString
0x1800c1d6b  mov     rcx, cs:g_pShimEngineModule
0x1800c1d72  lea     r9, [rbp+57h+arg_18]
0x1800c1d76  xor     r8d, r8d
0x1800c1d79  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1d7d  lea     rdx, [rbp+57h+DestinationString]
0x1800c1d81  call    LdrGetProcedureAddressEx
0x1800c1d86  mov     ebx, eax
0x1800c1d88  test    eax, eax
0x1800c1d8a  js      loc_1800C205C
0x1800c1d90  lea     rdx, aSeDllloaded; "SE_DllLoaded"
0x1800c1d97  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1d9b  call    RtlInitAnsiString
0x1800c1da0  mov     rcx, cs:g_pShimEngineModule
0x1800c1da7  lea     r9, [rbp+57h+var_70]
0x1800c1dab  xor     r8d, r8d
0x1800c1dae  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1db2  lea     rdx, [rbp+57h+DestinationString]
0x1800c1db6  call    LdrGetProcedureAddressEx
0x1800c1dbb  mov     ebx, eax
0x1800c1dbd  test    eax, eax
0x1800c1dbf  js      loc_1800C205C
0x1800c1dc5  lea     rdx, aSeDllunloaded; "SE_DllUnloaded"
0x1800c1dcc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1dd0  call    RtlInitAnsiString
0x1800c1dd5  mov     rcx, cs:g_pShimEngineModule
0x1800c1ddc  lea     r9, [rbp+57h+var_68]
0x1800c1de0  xor     r8d, r8d
0x1800c1de3  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1de7  lea     rdx, [rbp+57h+DestinationString]
0x1800c1deb  call    LdrGetProcedureAddressEx
0x1800c1df0  mov     ebx, eax
0x1800c1df2  test    eax, eax
0x1800c1df4  js      loc_1800C205C
0x1800c1dfa  lea     rdx, aSeLdrentryremo; "SE_LdrEntryRemoved"
0x1800c1e01  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1e05  call    RtlInitAnsiString
0x1800c1e0a  mov     rcx, cs:g_pShimEngineModule
0x1800c1e11  lea     r9, [rbp+57h+var_60]
0x1800c1e15  xor     r8d, r8d
0x1800c1e18  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1e1c  lea     rdx, [rbp+57h+DestinationString]
0x1800c1e20  call    LdrGetProcedureAddressEx
0x1800c1e25  mov     ebx, eax
0x1800c1e27  test    eax, eax
0x1800c1e29  js      loc_1800C205C
0x1800c1e2f  lea     rdx, aSeProcessdying; "SE_ProcessDying"
0x1800c1e36  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1e3a  call    RtlInitAnsiString
0x1800c1e3f  mov     rcx, cs:g_pShimEngineModule
0x1800c1e46  lea     r9, [rbp+57h+var_58]
0x1800c1e4a  xor     r8d, r8d
0x1800c1e4d  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1e51  lea     rdx, [rbp+57h+DestinationString]
0x1800c1e55  call    LdrGetProcedureAddressEx
0x1800c1e5a  mov     ebx, eax
0x1800c1e5c  test    eax, eax
0x1800c1e5e  js      loc_1800C205C
0x1800c1e64  lea     rdx, aSeLdrresolvedl; "SE_LdrResolveDllName"
0x1800c1e6b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1e6f  call    RtlInitAnsiString
0x1800c1e74  mov     rcx, cs:g_pShimEngineModule
0x1800c1e7b  lea     r9, [rbp+57h+var_48]
0x1800c1e7f  xor     r8d, r8d
0x1800c1e82  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1e86  lea     rdx, [rbp+57h+DestinationString]
0x1800c1e8a  call    LdrGetProcedureAddressEx
0x1800c1e8f  mov     ebx, eax
0x1800c1e91  test    eax, eax
0x1800c1e93  js      loc_1800C205C
0x1800c1e99  lea     rdx, aSeGetprocaddre; "SE_GetProcAddressForCaller"
0x1800c1ea0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1ea4  call    RtlInitAnsiString
0x1800c1ea9  mov     rcx, cs:g_pShimEngineModule
0x1800c1eb0  lea     r9, [rbp+57h+var_50]
0x1800c1eb4  xor     r8d, r8d
0x1800c1eb7  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1ebb  lea     rdx, [rbp+57h+DestinationString]
0x1800c1ebf  call    LdrGetProcedureAddressEx
0x1800c1ec4  mov     ebx, eax
0x1800c1ec6  test    eax, eax
0x1800c1ec8  js      loc_1800C205C
0x1800c1ece  lea     rdx, aApphelpcheckmo; "ApphelpCheckModule"
0x1800c1ed5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1ed9  call    RtlInitAnsiString
0x1800c1ede  mov     rcx, cs:g_pShimEngineModule
0x1800c1ee5  lea     r9, [rbp+57h+var_40]
0x1800c1ee9  xor     r8d, r8d
0x1800c1eec  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1ef0  lea     rdx, [rbp+57h+DestinationString]
0x1800c1ef4  call    LdrGetProcedureAddressEx
0x1800c1ef9  mov     ebx, eax
0x1800c1efb  test    eax, eax
0x1800c1efd  js      loc_1800C205C
0x1800c1f03  lea     rdx, aApphelpquerymo; "ApphelpQueryModSettingsAlloc"
0x1800c1f0a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1f0e  call    RtlInitAnsiString
0x1800c1f13  mov     rcx, cs:g_pShimEngineModule
0x1800c1f1a  lea     r9, [rbp+57h+var_38]
0x1800c1f1e  xor     r8d, r8d
0x1800c1f21  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1f25  lea     rdx, [rbp+57h+DestinationString]
0x1800c1f29  call    LdrGetProcedureAddressEx
0x1800c1f2e  lea     rdx, aApphelpquerymo_0; "ApphelpQueryModSettings2Alloc"
0x1800c1f35  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1f39  call    RtlInitAnsiString
0x1800c1f3e  mov     rcx, cs:g_pShimEngineModule
0x1800c1f45  lea     r9, [rbp+57h+var_30]
0x1800c1f49  xor     r8d, r8d
0x1800c1f4c  mov     dword ptr [rsp+0B0h+Format], edi
0x1800c1f50  lea     rdx, [rbp+57h+DestinationString]
0x1800c1f54  call    LdrGetProcedureAddressEx
0x1800c1f59  test    eax, eax
0x1800c1f5b  mov     ebx, edi
0x1800c1f5d  cmovns  ebx, eax
0x1800c1f60  xor     ecx, ecx
0x1800c1f62  call    LdrProtectMrdata
0x1800c1f67  mov     edx, ds:7FFE0330h
0x1800c1f6e  mov     r8, [rbp+57h+var_38]
0x1800c1f72  mov     ecx, edx
0x1800c1f74  and     ecx, 3Fh
0x1800c1f77  mov     eax, edx
0x1800c1f79  xor     rax, [rbp+57h+arg_0]
0x1800c1f7d  ror     rax, cl
0x1800c1f80  mov     cs:g_pfnSE_InitializeEngine, rax
0x1800c1f87  mov     eax, edx
0x1800c1f89  xor     rax, [rbp+57h+arg_8]
0x1800c1f8d  ror     rax, cl
0x1800c1f90  mov     cs:g_pfnSE_ShimDllLoaded, rax
0x1800c1f97  mov     eax, edx
0x1800c1f99  xor     rax, [rbp+57h+arg_10]
0x1800c1f9d  ror     rax, cl
0x1800c1fa0  mov     cs:g_pfnSE_InstallBeforeInit, rax
0x1800c1fa7  mov     eax, edx
0x1800c1fa9  xor     rax, [rbp+57h+arg_18]
0x1800c1fad  ror     rax, cl
0x1800c1fb0  mov     cs:g_pfnSE_InstallAfterInit, rax
0x1800c1fb7  mov     eax, edx
0x1800c1fb9  xor     rax, [rbp+57h+var_70]
0x1800c1fbd  ror     rax, cl
0x1800c1fc0  mov     cs:g_pfnSE_DllLoaded, rax
0x1800c1fc7  mov     eax, edx
0x1800c1fc9  xor     rax, [rbp+57h+var_68]
0x1800c1fcd  ror     rax, cl
0x1800c1fd0  mov     cs:g_pfnSE_DllUnloaded, rax
0x1800c1fd7  mov     eax, edx
0x1800c1fd9  xor     rax, [rbp+57h+var_60]
0x1800c1fdd  ror     rax, cl
0x1800c1fe0  mov     cs:g_pfnSE_LdrEntryRemoved, rax
0x1800c1fe7  mov     eax, edx
0x1800c1fe9  xor     rax, [rbp+57h+var_58]
0x1800c1fed  ror     rax, cl
0x1800c1ff0  mov     cs:g_pfnSE_ProcessDying, rax
0x1800c1ff7  mov     eax, edx
0x1800c1ff9  xor     rax, [rbp+57h+var_50]
0x1800c1ffd  ror     rax, cl
0x1800c2000  mov     cs:g_pfnSE_GetProcAddressForCaller, rax
0x1800c2007  mov     eax, edx
0x1800c2009  xor     rax, [rbp+57h+var_48]
0x1800c200d  ror     rax, cl
0x1800c2010  mov     cs:g_pfnSE_LdrResolveDllName, rax
0x1800c2017  mov     eax, edx
0x1800c2019  xor     rax, [rbp+57h+var_40]
0x1800c201d  ror     rax, cl
0x1800c2020  mov     cs:g_pfnApphelpCheckModuleProc, rax
0x1800c2027  test    r8, r8
0x1800c202a  jz      short loc_1800C203B
0x1800c202c  mov     eax, edx
0x1800c202e  xor     rax, r8
0x1800c2031  ror     rax, cl
0x1800c2034  mov     cs:g_pfnApphelpQueryModSettingsAllocProc, rax
0x1800c203b  mov     rax, [rbp+57h+var_30]
0x1800c203f  test    rax, rax
0x1800c2042  jz      short loc_1800C2051
0x1800c2044  xor     rdx, rax
0x1800c2047  ror     rdx, cl
0x1800c204a  mov     cs:g_pfnApphelpQueryModSettings2AllocProc, rdx
0x1800c2051  mov     ecx, esi
0x1800c2053  call    LdrProtectMrdata
0x1800c2058  test    ebx, ebx
0x1800c205a  jns     short loc_1800C20A6
0x1800c205c  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1800c2060  lea     r8, aLdrpgetshimeng; "LdrpGetShimEngineInterface"
0x1800c2067  mov     qword ptr [rsp+0B0h+ArgList], rax; ArgList
0x1800c206c  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800c2073  lea     rax, aCouldNotLocate; "Could not locate procedure \"%s\" in th"...
0x1800c207a  xor     r9d, r9d; int
0x1800c207d  mov     edx, 0CF1h; int
0x1800c2082  mov     [rsp+0B0h+Format], rax; Format
0x1800c2087  call    LdrpLogInternal
0x1800c208c  mov     rcx, cs:g_pShimEngineModule
0x1800c2093  mov     cs:g_ShimsEnabled, dil
0x1800c209a  call    LdrUnloadDll
0x1800c209f  mov     cs:g_pShimEngineModule, rdi
0x1800c20a6  mov     eax, ebx
0x1800c20a8  add     rsp, 98h
0x1800c20af  pop     rdi
0x1800c20b0  pop     rsi
0x1800c20b1  pop     rbx
0x1800c20b2  pop     rbp
0x1800c20b3  retn
```
