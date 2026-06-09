# InitializeRpcVerifier(void)

- ea: `0x1800a2acc`
- end: `0x1800a32b0`
- name: `?InitializeRpcVerifier@@YAXXZ`
- size: `2020`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18002499c`

## callees

- `0x180021e70`
- `0x1800a2acc`
- `0x1800a32b8`
- `0x1800d2010`

## import_xrefs

- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2c64`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2cca`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2dcf`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2e0b`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2e3c`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2e68`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2eaa`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2ed6`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f02`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f2e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f5a`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f86`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2fb2`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2fde`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a300a`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a303f`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a306e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a30b5`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a30eb`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a3117`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a3143`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a316f`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a31a1`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a31cd`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a31ff`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a322b`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2c64`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2cca`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2dcf`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2e0b`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2e3c`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2e68`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2eaa`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2ed6`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f02`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f2e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f5a`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2f86`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2fb2`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a2fde`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a300a`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a303f`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a306e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a30b5`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a30eb`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a3117`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a3143`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a316f`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a31a1`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a31cd`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a31ff`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a322b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2c7c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800a2c8d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800a2c8d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a329b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a329b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a2bbe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a2bbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2bd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2bd6`

## string_xrefs

- `0x1800a2bb5`: `verifier.dll`
- `0x1800a2e2d`: `RpcVerifierProbFaultInjectImpersonateClient`
- `0x1800a2e49`: `RpcVerifierDelayFaultInjectImpersonateClient`
- `0x1800a3030`: `NDRVerifierMaxExtensionFactor`
- `0x1800a304c`: `NDRVerifierMaxExtensionBufferLength`

## pseudocode

```c
void InitializeRpcVerifier(void)
{
  char *v0; // rax
  bool v1; // zf
  HMODULE Library; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  void *v5; // rbx
  SIZE_T v6; // rdi
  HANDLE ProcessHeap; // rax
  void *v8; // rax
  unsigned int v9; // eax
  struct _tRpcVerifierSettings *v10; // rcx
  struct _tRpcVerifierSettings *v11; // r9
  struct _UNICODE_STRING *v12; // rcx
  struct _tRpcVerifierSettings *v13; // rax
  struct _tRpcVerifierSettings *v14; // rax
  unsigned int Buffer; // [rsp+70h] [rbp+40h] BYREF
  int v16; // [rsp+78h] [rbp+48h] BYREF
  int v17; // [rsp+80h] [rbp+50h] BYREF
  int v18; // [rsp+88h] [rbp+58h] BYREF

  v0 = (char *)AllocWrapper(0xE0u);
  pRpcVerifierSettings = (struct _tRpcVerifierSettings *)v0;
  if ( v0 )
  {
    v1 = gfAppVerifierEnabled == 0;
    *(_DWORD *)v0 = 0;
    *((_DWORD *)v0 + 11) = 10;
    *(_QWORD *)(v0 + 76) = 10;
    *((_DWORD *)v0 + 22) = 10;
    *((_DWORD *)v0 + 31) = 10;
    DispatchToStubInC = DispatchToStubInCAvrf;
    *(_QWORD *)(v0 + 4) = 100;
    *(_QWORD *)(v0 + 12) = 0;
    *(_QWORD *)(v0 + 20) = 0;
    *(_QWORD *)(v0 + 28) = 0;
    *((_DWORD *)v0 + 9) = 100;
    *((_DWORD *)v0 + 10) = 100;
    *((_DWORD *)v0 + 12) = 4;
    *((_DWORD *)v0 + 13) = 1;
    *((_QWORD *)v0 + 7) = 2;
    *((_DWORD *)v0 + 16) = 0;
    *(_QWORD *)(v0 + 68) = 16;
    *((_DWORD *)v0 + 21) = 0;
    *(_QWORD *)(v0 + 92) = 100;
    *((_DWORD *)v0 + 25) = 1;
    *((_DWORD *)v0 + 26) = 100;
    *((_DWORD *)v0 + 27) = 1;
    *((_QWORD *)v0 + 14) = 150;
    *((_DWORD *)v0 + 30) = 100;
    *((_DWORD *)v0 + 33) = 0;
    *((_QWORD *)v0 + 17) = 0;
    *((_QWORD *)v0 + 18) = 0;
    *((_DWORD *)v0 + 38) = 20;
    *(_QWORD *)(v0 + 156) = 0x2000000;
    *((_QWORD *)v0 + 27) = 0;
    if ( v1 )
    {
      gfRPCVerifierEnabled = 1;
      v3 = 0;
      *((_DWORD *)v0 + 33) = 1;
    }
    else
    {
      Library = LoadLibraryExW(L"verifier.dll", 0, 0);
      v3 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "VerifierQueryRuntimeFlags");
        if ( ProcAddress )
        {
          v17 = 0;
          v18 = 0;
          if ( !((unsigned int (__fastcall *)(int *, int *))ProcAddress)(&v17, &v18) && v17 && (v18 & 0x80u) != 0 )
            gfRPCVerifierEnabled = 1;
        }
      }
    }
    if ( gfRPCVerifierEnabled )
    {
      v16 = 0;
      if ( RpcEvents )
      {
        Buffer = 2 * EventArrayLength;
        LdrQueryImageFileExecutionOptions(pBaseNameUnicodeString, L"RpcLogSize", 4u, &Buffer, 4u, 0);
        v5 = RpcEvents;
        v6 = 72LL * Buffer;
        ProcessHeap = GetProcessHeap();
        v8 = HeapReAlloc(ProcessHeap, 0, v5, v6);
        if ( v8 )
        {
          RpcEvents = v8;
          EventArrayLength = Buffer;
        }
      }
      LdrQueryImageFileExecutionOptions(pBaseNameUnicodeString, L"RpcVerifierFlags", 4u, &RpcVerifierFlags, 4u, 0);
      v9 = RpcVerifierFlags;
      v10 = pRpcVerifierSettings;
      if ( (RpcVerifierFlags & 1) != 0 )
      {
        *(_DWORD *)pRpcVerifierSettings = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x10) != 0 )
      {
        *((_DWORD *)v10 + 3) = 1;
        v9 = RpcVerifierFlags;
        gfRpcVerifierCorruptionExpected = 1;
      }
      if ( (v9 & 0x20) != 0 )
      {
        *((_DWORD *)v10 + 4) = 1;
        v9 = RpcVerifierFlags;
        gfRpcVerifierCorruptionExpected = 1;
      }
      if ( (v9 & 0x40) != 0 )
      {
        *((_DWORD *)v10 + 5) = 1;
        v9 = RpcVerifierFlags;
        gfRpcVerifierCorruptionExpected = 1;
      }
      if ( (v9 & 0x80u) != 0 )
      {
        *((_DWORD *)v10 + 6) = 1;
        *((_DWORD *)v10 + 8) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x40000) != 0 )
      {
        *((_DWORD *)v10 + 7) = 1;
        *((_DWORD *)v10 + 8) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x100) != 0 )
      {
        *((_DWORD *)v10 + 18) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x200) != 0 )
      {
        *((_DWORD *)v10 + 21) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x1000) != 0 )
      {
        *((_DWORD *)v10 + 24) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x2000) != 0 )
      {
        *((_DWORD *)v10 + 29) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x10000) != 0 )
      {
        *((_DWORD *)v10 + 33) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x20000) != 0 )
        LODWORD(gBCacheMode) = 1;
      LdrQueryImageFileExecutionOptions(pBaseNameUnicodeString, L"PageHeapFaultProbability", 4u, &v16, 4u, 0);
      if ( v16 )
      {
        v11 = pRpcVerifierSettings;
        v12 = pBaseNameUnicodeString;
        *(_DWORD *)pRpcVerifierSettings = 1;
        *((_DWORD *)v11 + 1) = v16;
        LdrQueryImageFileExecutionOptions(v12, L"PageHeapFaultTimeOut", 4u, (char *)v11 + 8, 4u, 0);
      }
      v13 = pRpcVerifierSettings;
      if ( *(_DWORD *)pRpcVerifierSettings )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbFaultInjectImpersonateClient",
          4u,
          (char *)pRpcVerifierSettings + 4,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierDelayFaultInjectImpersonateClient",
          4u,
          (char *)pRpcVerifierSettings + 8,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 3) || *((_DWORD *)v13 + 4) || *((_DWORD *)v13 + 5) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbRpcHeaderCorruption",
          4u,
          (char *)v13 + 36,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbDataCorruption",
          4u,
          (char *)pRpcVerifierSettings + 40,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbSecureDataCorruption",
          4u,
          (char *)pRpcVerifierSettings + 44,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionPattern",
          4u,
          (char *)pRpcVerifierSettings + 48,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionSizeType",
          4u,
          (char *)pRpcVerifierSettings + 52,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionSize",
          4u,
          (char *)pRpcVerifierSettings + 56,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionDistributionType",
          4u,
          (char *)pRpcVerifierSettings + 60,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbBufferTruncation",
          4u,
          (char *)pRpcVerifierSettings + 64,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierMaxBufferTruncationSize",
          4u,
          (char *)pRpcVerifierSettings + 68,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 8) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"NDRVerifierMaxExtensionFactor",
          4u,
          (char *)v13 + 152,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"NDRVerifierMaxExtensionBufferLength",
          4u,
          (char *)pRpcVerifierSettings + 156,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 3) || *((_DWORD *)v13 + 4) || *((_DWORD *)v13 + 5) || *((_DWORD *)v13 + 8) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierDelayCorruption",
          4u,
          (char *)v13 + 160,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 24) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectIntervalType",
          4u,
          (char *)v13 + 100,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectIntervalLength",
          4u,
          (char *)pRpcVerifierSettings + 104,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectPauseType",
          4u,
          (char *)pRpcVerifierSettings + 108,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectPauseLength",
          4u,
          (char *)pRpcVerifierSettings + 112,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 18) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbFaultInjectTransports",
          4u,
          (char *)v13 + 76,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierDelayFaultInjectTransports",
          4u,
          (char *)pRpcVerifierSettings + 80,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 21) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierSendReplaySentBufferListSize",
          4u,
          (char *)v13 + 88,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierSendReplayReplayFrequency",
          4u,
          (char *)pRpcVerifierSettings + 92,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 3)
        || *((_DWORD *)v13 + 4)
        || *((_DWORD *)v13 + 5)
        || *((_DWORD *)v13 + 8)
        || *((_DWORD *)v13 + 24)
        || *((_DWORD *)v13 + 21)
        || *((_DWORD *)v13 + 18) )
      {
        if ( (unsigned int)LoadRpcShim() )
        {
          v14 = pRpcVerifierSettings;
          *(_QWORD *)((char *)pRpcVerifierSettings + 12) = 0;
          *(_QWORD *)((char *)v14 + 20) = 0;
          *(_QWORD *)((char *)v14 + 28) = 0;
          *((_DWORD *)v14 + 24) = 0;
          *((_DWORD *)v14 + 21) = 0;
          *((_DWORD *)v14 + 18) = 0;
        }
      }
    }
    else
    {
      LODWORD(gBCacheMode) = 1;
    }
    if ( v3 )
      FreeLibrary(v3);
  }
}

```

## disassembly

```asm
0x1800a2acc  push    rbp
0x1800a2ace  push    rbx
0x1800a2acf  push    rsi
0x1800a2ad0  push    rdi
0x1800a2ad1  push    r12
0x1800a2ad3  push    r14
0x1800a2ad5  push    r15
0x1800a2ad7  mov     rbp, rsp
0x1800a2ada  sub     rsp, 30h
0x1800a2ade  mov     ecx, 0E0h; dwBytes
0x1800a2ae3  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a2ae8  xor     r14d, r14d
0x1800a2aeb  mov     cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA, rax; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2af2  test    rax, rax
0x1800a2af5  jz      loc_1800A32A1
0x1800a2afb  cmp     cs:?gfAppVerifierEnabled@@3HA, r14d; int gfAppVerifierEnabled
0x1800a2b02  lea     edx, [r14+64h]
0x1800a2b06  lea     ecx, [rdx-5Ah]
0x1800a2b09  mov     [rax], r14d
0x1800a2b0c  lea     r12d, [r14+1]
0x1800a2b10  mov     [rax+2Ch], ecx
0x1800a2b13  mov     [rax+4Ch], rcx
0x1800a2b17  lea     r15d, [r14+4]
0x1800a2b1b  mov     [rax+58h], ecx
0x1800a2b1e  mov     [rax+7Ch], ecx
0x1800a2b21  lea     rcx, DispatchToStubInCAvrf
0x1800a2b28  mov     cs:DispatchToStubInC, rcx
0x1800a2b2f  mov     [rax+4], rdx
0x1800a2b33  mov     [rax+0Ch], r14
0x1800a2b37  mov     [rax+14h], r14
0x1800a2b3b  mov     [rax+1Ch], r14
0x1800a2b3f  mov     [rax+24h], edx
0x1800a2b42  mov     [rax+28h], edx
0x1800a2b45  mov     [rax+30h], r15d
0x1800a2b49  mov     [rax+34h], r12d
0x1800a2b4d  mov     qword ptr [rax+38h], 2
0x1800a2b55  mov     [rax+40h], r14d
0x1800a2b59  mov     qword ptr [rax+44h], 10h
0x1800a2b61  mov     [rax+54h], r14d
0x1800a2b65  mov     [rax+5Ch], rdx
0x1800a2b69  mov     [rax+64h], r12d
0x1800a2b6d  mov     [rax+68h], edx
0x1800a2b70  mov     [rax+6Ch], r12d
0x1800a2b74  mov     qword ptr [rax+70h], 96h
0x1800a2b7c  mov     [rax+78h], edx
0x1800a2b7f  mov     [rax+84h], r14d
0x1800a2b86  mov     [rax+88h], r14
0x1800a2b8d  mov     [rax+90h], r14
0x1800a2b94  mov     dword ptr [rax+98h], 14h
0x1800a2b9e  mov     qword ptr [rax+9Ch], 2000000h
0x1800a2ba9  mov     [rax+0D8h], r14
0x1800a2bb0  jz      short loc_1800A2C0F
0x1800a2bb2  xor     r8d, r8d; dwFlags
0x1800a2bb5  lea     rcx, aVerifierDll; "verifier.dll"
0x1800a2bbc  xor     edx, edx; hFile
0x1800a2bbe  call    cs:__imp_LoadLibraryExW
0x1800a2bc4  mov     rsi, rax
0x1800a2bc7  test    rax, rax
0x1800a2bca  jz      short loc_1800A2C20
0x1800a2bcc  lea     rdx, aVerifierqueryr; "VerifierQueryRuntimeFlags"
0x1800a2bd3  mov     rcx, rax; hModule
0x1800a2bd6  call    cs:__imp_GetProcAddress
0x1800a2bdc  test    rax, rax
0x1800a2bdf  jz      short loc_1800A2C20
0x1800a2be1  lea     rdx, [rbp+arg_18]
0x1800a2be5  mov     [rbp+arg_10], r14d
0x1800a2be9  lea     rcx, [rbp+arg_10]
0x1800a2bed  mov     [rbp+arg_18], r14d
0x1800a2bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2bf6  test    eax, eax
0x1800a2bf8  jnz     short loc_1800A2C20
0x1800a2bfa  cmp     [rbp+arg_10], r14d
0x1800a2bfe  jz      short loc_1800A2C20
0x1800a2c00  test    byte ptr [rbp+arg_18], 80h
0x1800a2c04  jz      short loc_1800A2C20
0x1800a2c06  mov     cs:?gfRPCVerifierEnabled@@3HA, r12d; int gfRPCVerifierEnabled
0x1800a2c0d  jmp     short loc_1800A2C20
0x1800a2c0f  mov     cs:?gfRPCVerifierEnabled@@3HA, r12d; int gfRPCVerifierEnabled
0x1800a2c16  mov     rsi, r14
0x1800a2c19  mov     [rax+84h], r12d
0x1800a2c20  cmp     cs:?gfRPCVerifierEnabled@@3HA, r14d; int gfRPCVerifierEnabled
0x1800a2c27  jz      loc_1800A328C
0x1800a2c2d  cmp     cs:?RpcEvents@@3PEAURPC_EVENT@@EA, r14; RPC_EVENT * RpcEvents
0x1800a2c34  mov     [rbp+arg_8], r14d
0x1800a2c38  jz      short loc_1800A2CA8
0x1800a2c3a  mov     eax, cs:?EventArrayLength@@3KA; ulong EventArrayLength
0x1800a2c40  lea     r9, [rbp+Buffer]; Buffer
0x1800a2c44  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2c4b  lea     rdx, aRpclogsize; "RpcLogSize"
0x1800a2c52  add     eax, eax
0x1800a2c54  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2c59  mov     r8d, r15d; ValueSize
0x1800a2c5c  mov     [rbp+Buffer], eax
0x1800a2c5f  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2c64  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2c6a  mov     eax, [rbp+Buffer]
0x1800a2c6d  mov     rbx, cs:?RpcEvents@@3PEAURPC_EVENT@@EA; RPC_EVENT * RpcEvents
0x1800a2c74  lea     rdi, [rax+rax*8]
0x1800a2c78  shl     rdi, 3
0x1800a2c7c  call    cs:__imp_GetProcessHeap
0x1800a2c82  mov     r9, rdi; dwBytes
0x1800a2c85  mov     r8, rbx; lpMem
0x1800a2c88  mov     rcx, rax; hHeap
0x1800a2c8b  xor     edx, edx; dwFlags
0x1800a2c8d  call    cs:__imp_HeapReAlloc
0x1800a2c93  test    rax, rax
0x1800a2c96  jz      short loc_1800A2CA8
0x1800a2c98  mov     cs:?RpcEvents@@3PEAURPC_EVENT@@EA, rax; RPC_EVENT * RpcEvents
0x1800a2c9f  mov     eax, [rbp+Buffer]
0x1800a2ca2  mov     cs:?EventArrayLength@@3KA, eax; ulong EventArrayLength
0x1800a2ca8  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2caf  lea     r9, ?RpcVerifierFlags@@3KA; Buffer
0x1800a2cb6  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2cbb  lea     rdx, aRpcverifierfla; "RpcVerifierFlags"
0x1800a2cc2  mov     r8d, r15d; ValueSize
0x1800a2cc5  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2cca  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2cd0  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2cd6  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2cdd  test    r12b, al
0x1800a2ce0  jz      short loc_1800A2CEB
0x1800a2ce2  mov     [rcx], r12d
0x1800a2ce5  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2ceb  test    al, 10h
0x1800a2ced  jz      short loc_1800A2D00
0x1800a2cef  mov     [rcx+0Ch], r12d
0x1800a2cf3  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2cf9  mov     cs:?gfRpcVerifierCorruptionExpected@@3HA, r12d; int gfRpcVerifierCorruptionExpected
0x1800a2d00  test    al, 20h
0x1800a2d02  jz      short loc_1800A2D15
0x1800a2d04  mov     [rcx+10h], r12d
0x1800a2d08  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d0e  mov     cs:?gfRpcVerifierCorruptionExpected@@3HA, r12d; int gfRpcVerifierCorruptionExpected
0x1800a2d15  test    al, 40h
0x1800a2d17  jz      short loc_1800A2D2A
0x1800a2d19  mov     [rcx+14h], r12d
0x1800a2d1d  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d23  mov     cs:?gfRpcVerifierCorruptionExpected@@3HA, r12d; int gfRpcVerifierCorruptionExpected
0x1800a2d2a  test    al, al
0x1800a2d2c  jns     short loc_1800A2D3C
0x1800a2d2e  mov     [rcx+18h], r12d
0x1800a2d32  mov     [rcx+20h], r12d
0x1800a2d36  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d3c  bt      eax, 12h
0x1800a2d40  jnb     short loc_1800A2D50
0x1800a2d42  mov     [rcx+1Ch], r12d
0x1800a2d46  mov     [rcx+20h], r12d
0x1800a2d4a  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d50  bt      eax, 8
0x1800a2d54  jnb     short loc_1800A2D60
0x1800a2d56  mov     [rcx+48h], r12d
0x1800a2d5a  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d60  bt      eax, 9
0x1800a2d64  jnb     short loc_1800A2D70
0x1800a2d66  mov     [rcx+54h], r12d
0x1800a2d6a  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d70  bt      eax, 0Ch
0x1800a2d74  jnb     short loc_1800A2D80
0x1800a2d76  mov     [rcx+60h], r12d
0x1800a2d7a  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d80  bt      eax, 0Dh
0x1800a2d84  jnb     short loc_1800A2D90
0x1800a2d86  mov     [rcx+74h], r12d
0x1800a2d8a  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2d90  bt      eax, 10h
0x1800a2d94  jnb     short loc_1800A2DA3
0x1800a2d96  mov     [rcx+84h], r12d
0x1800a2d9d  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a2da3  bt      eax, 11h
0x1800a2da7  jnb     short loc_1800A2DB0
0x1800a2da9  mov     cs:?gBCacheMode@@3W4BCacheMode@@A, r12d; BCacheMode gBCacheMode
0x1800a2db0  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2db7  lea     r9, [rbp+arg_8]; Buffer
0x1800a2dbb  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2dc0  lea     rdx, aPageheapfaultp; "PageHeapFaultProbability"
0x1800a2dc7  mov     r8d, r15d; ValueSize
0x1800a2dca  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2dcf  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2dd5  cmp     [rbp+arg_8], r14d
0x1800a2dd9  jz      short loc_1800A2E11
0x1800a2ddb  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2de2  lea     rdx, aPageheapfaultt; "PageHeapFaultTimeOut"
0x1800a2de9  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2df0  mov     r8d, r15d; ValueSize
0x1800a2df3  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2df8  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2dfd  mov     [r9], r12d
0x1800a2e00  mov     eax, [rbp+arg_8]
0x1800a2e03  mov     [r9+4], eax
0x1800a2e07  add     r9, 8; Buffer
0x1800a2e0b  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2e11  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2e18  cmp     [rax], r14d
0x1800a2e1b  jz      short loc_1800A2E75
0x1800a2e1d  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2e24  lea     r9, [rax+4]; Buffer
0x1800a2e28  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2e2d  lea     rdx, aRpcverifierpro; "RpcVerifierProbFaultInjectImpersonateCl"...
0x1800a2e34  mov     r8d, r15d; ValueSize
0x1800a2e37  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2e3c  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2e42  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2e49  lea     rdx, aRpcverifierdel_1; "RpcVerifierDelayFaultInjectImpersonateC"...
0x1800a2e50  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2e57  add     r9, 8; Buffer
0x1800a2e5b  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2e60  mov     r8d, r15d; ValueSize
0x1800a2e63  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2e68  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2e6e  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2e75  cmp     [rax+0Ch], r14d
0x1800a2e79  jnz     short loc_1800A2E8B
0x1800a2e7b  cmp     [rax+10h], r14d
0x1800a2e7f  jnz     short loc_1800A2E8B
0x1800a2e81  cmp     [rax+14h], r14d
0x1800a2e85  jz      loc_1800A3017
0x1800a2e8b  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2e92  lea     r9, [rax+24h]; Buffer
0x1800a2e96  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2e9b  lea     rdx, aRpcverifierpro_3; "RpcVerifierProbRpcHeaderCorruption"
0x1800a2ea2  mov     r8d, r15d; ValueSize
0x1800a2ea5  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2eaa  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2eb0  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2eb7  lea     rdx, aRpcverifierpro_4; "RpcVerifierProbDataCorruption"
0x1800a2ebe  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2ec5  add     r9, 28h ; '('; Buffer
0x1800a2ec9  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2ece  mov     r8d, r15d; ValueSize
0x1800a2ed1  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2ed6  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2edc  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2ee3  lea     rdx, aRpcverifierpro_2; "RpcVerifierProbSecureDataCorruption"
0x1800a2eea  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2ef1  add     r9, 2Ch ; ','; Buffer
0x1800a2ef5  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2efa  mov     r8d, r15d; ValueSize
0x1800a2efd  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2f02  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2f08  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2f0f  lea     rdx, aRpcverifiercor_2; "RpcVerifierCorruptionPattern"
0x1800a2f16  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2f1d  add     r9, 30h ; '0'; Buffer
0x1800a2f21  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2f26  mov     r8d, r15d; ValueSize
0x1800a2f29  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2f2e  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2f34  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2f3b  lea     rdx, aRpcverifiercor_0; "RpcVerifierCorruptionSizeType"
0x1800a2f42  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2f49  add     r9, 34h ; '4'; Buffer
0x1800a2f4d  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2f52  mov     r8d, r15d; ValueSize
0x1800a2f55  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2f5a  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2f60  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2f67  lea     rdx, aRpcverifiercor_1; "RpcVerifierCorruptionSize"
0x1800a2f6e  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2f75  add     r9, 38h ; '8'; Buffer
0x1800a2f79  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2f7e  mov     r8d, r15d; ValueSize
0x1800a2f81  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2f86  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2f8c  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2f93  lea     rdx, aRpcverifiercor; "RpcVerifierCorruptionDistributionType"
0x1800a2f9a  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2fa1  add     r9, 3Ch ; '<'; Buffer
0x1800a2fa5  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2faa  mov     r8d, r15d; ValueSize
0x1800a2fad  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2fb2  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2fb8  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2fbf  lea     rdx, aRpcverifierpro_0; "RpcVerifierProbBufferTruncation"
0x1800a2fc6  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2fcd  add     r9, 40h ; '@'; Buffer
0x1800a2fd1  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a2fd6  mov     r8d, r15d; ValueSize
0x1800a2fd9  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a2fde  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a2fe4  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a2feb  lea     rdx, aRpcverifiermax; "RpcVerifierMaxBufferTruncationSize"
0x1800a2ff2  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a2ff9  add     r9, 44h ; 'D'; Buffer
0x1800a2ffd  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a3002  mov     r8d, r15d; ValueSize
0x1800a3005  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a300a  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a3010  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a3017  cmp     [rax+20h], r14d
0x1800a301b  jz      short loc_1800A307B
0x1800a301d  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a3024  lea     r9, [rax+98h]; Buffer
0x1800a302b  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a3030  lea     rdx, aNdrverifiermax; "NDRVerifierMaxExtensionFactor"
0x1800a3037  mov     r8d, r15d; ValueSize
0x1800a303a  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a303f  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a3045  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a304c  lea     rdx, aNdrverifiermax_0; "NDRVerifierMaxExtensionBufferLength"
0x1800a3053  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
  ... truncated ...
```
