# _BaseDllInitialize

- ea: `0x1800361ec`
- end: `0x180036501`
- name: `_BaseDllInitialize`
- size: `789`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1800361b0`

## callees

- `0x18002f878`
- `0x180035320`
- `0x180035de0`
- `0x1800361ec`
- `0x1800375bc`
- `0x180043400`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlSetProtectedPolicy` at `0x1800362e8`
- `ntdll!RtlSetProtectedPolicy` at `0x1800362e8`
- `ntdll!RtlGetSuiteMask` at `0x18003643e`
- `ntdll!RtlGetSuiteMask` at `0x18003643e`
- `ntdll!RtlImageNtHeader` at `0x180036253`
- `ntdll!RtlImageNtHeader` at `0x180036253`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x18003647c`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x18003647c`
- `ntdll!RtlInitUnicodeString` at `0x180036395`
- `ntdll!RtlInitUnicodeString` at `0x180036395`
- `ntdll!RtlSetThreadPoolStartFunc` at `0x180036276`
- `ntdll!RtlSetThreadPoolStartFunc` at `0x180036276`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x18003640a`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x18003640a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800362f4`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800362f4`
- `ntdll!LdrSetDllManifestProber` at `0x180036291`
- `ntdll!LdrSetDllManifestProber` at `0x1800364ce`
- `ntdll!LdrSetDllManifestProber` at `0x180036291`
- `ntdll!LdrSetDllManifestProber` at `0x1800364ce`
- `KERNELBASE!GetRegistryExtensionFlags` at `0x180036473`
- `KERNELBASE!GetRegistryExtensionFlags` at `0x180036473`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003629d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003629d`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18003627c`

## string_xrefs

- `0x180036403`: `SearchPathMode`

## pseudocode

```c
char __fastcall BaseDllInitialize(PVOID BaseAddress, unsigned int a2)
{
  char v2; // r14
  struct _PEB *v3; // rbx
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rdi
  PIMAGE_NT_HEADERS v7; // rsi
  char v8; // bl
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 GlobalData; // rax
  __int64 v14; // xmm1_8
  ULONG SessionId; // esi
  char *v16; // r8
  __int64 v17; // rax
  _BYTE v19[8]; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE (__stdcall *v20)(LPCWSTR, HANDLE, DWORD); // [rsp+38h] [rbp-C8h] BYREF
  DWORD Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[256]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  Buffer[0] = 0;
  v3 = NtCurrentPeb();
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      ProcessParameters = v3->ProcessParameters;
      v7 = RtlImageNtHeader(v3->ImageBaseAddress);
      if ( !v7 )
        return 0;
      RtlSetThreadPoolStartFunc(BaseCreateThreadPoolThread, BaseExitThreadPoolThread);
      LdrSetDllManifestProber(BasepProbeForDllManifest);
      v2 = 1;
      GlobalData = KernelBaseGetGlobalData(v10, v9, v11, v12);
      v14 = *(_QWORD *)(GlobalData + 80);
      BaseHeap = *(HANDLE *)(GlobalData + 64);
      if ( !SystemRangeStart )
        SystemRangeStart = v14;
      if ( (unsigned __int16)(v7->OptionalHeader.Subsystem - 1) > 2u || v7->OptionalHeader.MajorSubsystemVersion < 6u )
        RtlSetProtectedPolicy(&GUID_BasepAllowResourceConversion, 1, 0);
      SessionId = v3->SessionId;
      if ( SessionId == (unsigned int)RtlGetCurrentServiceSessionId() )
        StringCbCopyW(pszDest, 0x200u, L"\\Windows");
      else
        StringCbPrintfW(pszDest, 0x200u, L"%ws\\%ld%ws", L"\\Sessions", SessionId, L"\\Windows");
      v16 = (char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
          + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
          - (unsigned __int64)NtCurrentPeb()[1].Ldr;
      BaseStaticServerData = (__int64)v16;
      BaseCSDVersion = (__int64)(v16 + 58);
      if ( v16 != (char *)-58LL && !v3->CSDVersion.Buffer )
      {
        RtlInitUnicodeString(&v3->CSDVersion, (PCWSTR)v16 + 29);
        v16 = (char *)BaseStaticServerData;
      }
      BaseWindowsSys32x86Directory = *((_QWORD *)v16 + 255);
      v17 = *((_QWORD *)v16 + 256);
      qword_1800B63F8 = v17;
      if ( v17 )
        qword_1800B63F8 = (__int64)&v16[v17 - *((_QWORD *)v16 + 317)];
      else
        qword_1800B63F8 = 0;
      if ( (ProcessParameters->Flags & 0x4000) == 0
        && LdrQueryImageFileExecutionOptions(&ProcessParameters->ImagePathName, L"SearchPathMode", 4u, Buffer, 4u, 0) >= 0 )
      {
        SetSearchPathMode(Buffer[0]);
      }
      if ( ProcessParameters && ProcessParameters->DebugFlags )
        __debugbreak();
      qword_1800B63E8 = (__int64)&BasepAppCertDllsList;
      BasepAppCertDllsList = (__int64)&BasepAppCertDllsList;
      if ( (RtlGetSuiteMask() & 0x10) != 0 )
      {
        v19[0] = 0;
        LODWORD(v20) = 0;
        if ( (unsigned __int8)InitializeRegTermsrvFpns(v19, &v20) )
        {
          if ( v19[0] )
            GetRegistryExtensionFlags((unsigned int)v20);
        }
      }
      LdrDisableThreadCalloutsForDll(BaseAddress);
    }
  }
  else
  {
    v20 = LoadLibraryExWStub;
  }
  v8 = Kernel32LegacyLib_BaseDllInitialize(BaseAddress, a2);
  if ( !v8 && v2 )
    LdrSetDllManifestProber(0);
  return v8;
}

```

## disassembly

```asm
0x1800361ec  mov     [rsp-8+arg_8], rbx
0x1800361f1  mov     [rsp-8+arg_10], rsi
0x1800361f6  push    rbp
0x1800361f7  push    rdi
0x1800361f8  push    r12
0x1800361fa  push    r14
0x1800361fc  push    r15
0x1800361fe  lea     rbp, [rsp-160h]
0x180036206  sub     rsp, 260h
0x18003620d  mov     rax, cs:__security_cookie
0x180036214  xor     rax, rsp
0x180036217  mov     [rbp+180h+var_30], rax
0x18003621e  xor     r14b, r14b
0x180036221  mov     [rsp+280h+Buffer], 0
0x180036229  mov     rbx, gs:60h
0x180036232  mov     r15d, edx
0x180036235  mov     r12, rcx
0x180036238  mov     eax, edx
0x18003623a  test    edx, edx
0x18003623c  jz      loc_180036484
0x180036242  cmp     eax, 1
0x180036245  jnz     loc_1800364B4
0x18003624b  mov     rcx, [rbx+10h]; BaseAddress
0x18003624f  mov     rdi, [rbx+20h]
0x180036253  call    cs:__imp_RtlImageNtHeader
0x180036259  mov     rsi, rax
0x18003625c  test    rax, rax
0x18003625f  jnz     short loc_180036268
0x180036261  xor     bl, bl
0x180036263  jmp     loc_1800364D4
0x180036268  lea     rdx, BaseExitThreadPoolThread; ExitPoolThread
0x18003626f  lea     rcx, BaseCreateThreadPoolThread; StartPoolThread
0x180036276  call    cs:__imp_RtlSetThreadPoolStartFunc
0x18003627c  mov     r8, cs:__imp_ReleaseActCtx
0x180036283  lea     rdx, BasepRegenerateActCtxWithLanguage
0x18003628a  lea     rcx, BasepProbeForDllManifest; Routine
0x180036291  call    cs:__imp_LdrSetDllManifestProber
0x180036297  mov     r14d, 1
0x18003629d  call    cs:__imp_KernelBaseGetGlobalData
0x1800362a3  cmp     cs:SystemRangeStart, 0
0x1800362ab  movups  xmm0, xmmword ptr [rax+40h]
0x1800362af  movsd   xmm1, qword ptr [rax+50h]
0x1800362b4  movsd   cs:BaseHeap, xmm0
0x1800362bc  jnz     short loc_1800362C6
0x1800362be  movsd   cs:SystemRangeStart, xmm1
0x1800362c6  movzx   eax, word ptr [rsi+5Ch]
0x1800362ca  sub     ax, r14w
0x1800362ce  cmp     ax, 2
0x1800362d2  ja      short loc_1800362DB
0x1800362d4  cmp     word ptr [rsi+48h], 6
0x1800362d9  jnb     short loc_1800362EE
0x1800362db  xor     r8d, r8d
0x1800362de  lea     rcx, GUID_BasepAllowResourceConversion
0x1800362e5  mov     rdx, r14
0x1800362e8  call    cs:__imp_RtlSetProtectedPolicy
0x1800362ee  mov     esi, [rbx+2C0h]
0x1800362f4  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800362fa  mov     edx, 200h; cbDest
0x1800362ff  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180036304  cmp     esi, eax
0x180036306  jnz     short loc_180036316
0x180036308  lea     r8, aWindows; "\\Windows"
0x18003630f  call    StringCbCopyW
0x180036314  jmp     short loc_180036339
0x180036316  lea     rax, aWindows; "\\Windows"
0x18003631d  mov     [rsp+280h+RetunedLength], rax
0x180036322  lea     r9, aSessions; "\\Sessions"
0x180036329  lea     r8, aWsLdWs; "%ws\\%ld%ws"
0x180036330  mov     [rsp+280h+BufferSize], esi
0x180036334  call    StringCbPrintfW
0x180036339  mov     rax, gs:60h
0x180036342  mov     rcx, [rax+98h]
0x180036349  mov     rax, gs:60h
0x180036352  mov     r8, [rcx+8]
0x180036356  sub     r8, [rax+380h]
0x18003635d  mov     rax, gs:60h
0x180036366  add     r8, [rax+88h]
0x18003636d  mov     cs:BaseStaticServerData, r8
0x180036374  lea     rdx, [r8+3Ah]; SourceString
0x180036378  mov     cs:BaseCSDVersion, rdx
0x18003637f  test    rdx, rdx
0x180036382  jz      short loc_1800363A2
0x180036384  cmp     qword ptr [rbx+2F0h], 0
0x18003638c  jnz     short loc_1800363A2
0x18003638e  lea     rcx, [rbx+2E8h]; DestinationString
0x180036395  call    cs:__imp_RtlInitUnicodeString
0x18003639b  mov     r8, cs:BaseStaticServerData
0x1800363a2  mov     rax, [r8+7F8h]
0x1800363a9  mov     cs:BaseWindowsSys32x86Directory, rax
0x1800363b0  mov     rax, [r8+800h]
0x1800363b7  mov     cs:qword_1800B63F8, rax
0x1800363be  test    rax, rax
0x1800363c1  jnz     short loc_1800363CC
0x1800363c3  mov     cs:qword_1800B63F8, rax
0x1800363ca  jmp     short loc_1800363DD
0x1800363cc  sub     rax, [r8+9E8h]
0x1800363d3  add     rax, r8
0x1800363d6  mov     cs:qword_1800B63F8, rax
0x1800363dd  test    dword ptr [rdi+8], 4000h
0x1800363e4  jnz     short loc_18003641D
0x1800363e6  mov     r8d, 4; ValueSize
0x1800363ec  mov     [rsp+280h+RetunedLength], 0; RetunedLength
0x1800363f5  lea     rcx, [rdi+60h]; SubKey
0x1800363f9  mov     [rsp+280h+BufferSize], r8d; BufferSize
0x1800363fe  lea     r9, [rsp+280h+Buffer]; Buffer
0x180036403  lea     rdx, aSearchpathmode; "SearchPathMode"
0x18003640a  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x180036410  test    eax, eax
0x180036412  js      short loc_18003641D
0x180036414  mov     ecx, [rsp+280h+Buffer]; Flags
0x180036418  call    SetSearchPathMode
0x18003641d  test    rdi, rdi
0x180036420  jz      short loc_180036429
0x180036422  cmp     dword ptr [rdi+0Ch], 0
0x180036426  jz      short loc_180036429
0x180036428  int     3; Trap to Debugger
0x180036429  lea     rax, BasepAppCertDllsList
0x180036430  mov     cs:qword_1800B63E8, rax
0x180036437  mov     cs:BasepAppCertDllsList, rax
0x18003643e  call    cs:__imp_RtlGetSuiteMask
0x180036444  test    al, 10h
0x180036446  jz      short loc_180036479
0x180036448  lea     rdx, [rsp+280h+var_248]
0x18003644d  mov     [rsp+280h+var_250], 0
0x180036452  lea     rcx, [rsp+280h+var_250]
0x180036457  mov     dword ptr [rsp+280h+var_248], 0
0x18003645f  call    InitializeRegTermsrvFpns
0x180036464  test    al, al
0x180036466  jz      short loc_180036479
0x180036468  cmp     [rsp+280h+var_250], 0
0x18003646d  jz      short loc_180036479
0x18003646f  mov     ecx, dword ptr [rsp+280h+var_248]
0x180036473  call    cs:__imp_GetRegistryExtensionFlags
0x180036479  mov     rcx, r12; BaseAddress
0x18003647c  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x180036482  jmp     short loc_1800364B4
0x180036484  lea     rax, LoadLibraryAStub
0x18003648b  mov     [rsp+280h+var_248], rax
0x180036490  lea     rax, LoadLibraryWStub
0x180036497  mov     [rsp+280h+var_248], rax
0x18003649c  lea     rax, LoadLibraryExAStub
0x1800364a3  mov     [rsp+280h+var_248], rax
0x1800364a8  lea     rax, LoadLibraryExWStub
0x1800364af  mov     [rsp+280h+var_248], rax
0x1800364b4  mov     edx, r15d
0x1800364b7  call    _Kernel32LegacyLib_BaseDllInitialize
0x1800364bc  mov     bl, al
0x1800364be  test    al, al
0x1800364c0  jnz     short loc_1800364D4
0x1800364c2  test    r14b, r14b
0x1800364c5  jz      short loc_1800364D4
0x1800364c7  xor     r8d, r8d
0x1800364ca  xor     edx, edx
0x1800364cc  xor     ecx, ecx; Routine
0x1800364ce  call    cs:__imp_LdrSetDllManifestProber
0x1800364d4  mov     al, bl
0x1800364d6  mov     rcx, [rbp+180h+var_30]
0x1800364dd  xor     rcx, rsp; StackCookie
0x1800364e0  call    __security_check_cookie
0x1800364e5  lea     r11, [rsp+280h+var_20]
0x1800364ed  mov     rbx, [r11+38h]
0x1800364f1  mov     rsi, [r11+40h]
0x1800364f5  mov     rsp, r11
0x1800364f8  pop     r15
0x1800364fa  pop     r14
0x1800364fc  pop     r12
0x1800364fe  pop     rdi
0x1800364ff  pop     rbp
0x180036500  retn
```
