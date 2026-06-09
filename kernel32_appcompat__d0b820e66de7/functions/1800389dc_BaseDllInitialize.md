# _BaseDllInitialize

- ea: `0x1800389dc`
- end: `0x180038d3a`
- name: `_BaseDllInitialize`
- size: `862`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1800389a0`

## callees

- `0x1800315f8`
- `0x180036654`
- `0x180038514`
- `0x1800389dc`
- `0x18003a2a4`
- `0x180047770`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlSetProtectedPolicy` at `0x180038af0`
- `ntdll!RtlSetProtectedPolicy` at `0x180038af0`
- `ntdll!RtlGetSuiteMask` at `0x180038c5e`
- `ntdll!RtlGetSuiteMask` at `0x180038c5e`
- `ntdll!RtlImageNtHeader` at `0x180038a43`
- `ntdll!RtlImageNtHeader` at `0x180038a43`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180038ca8`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180038ca8`
- `ntdll!RtlInitUnicodeString` at `0x180038ba9`
- `ntdll!RtlInitUnicodeString` at `0x180038ba9`
- `ntdll!RtlSetThreadPoolStartFunc` at `0x180038a6c`
- `ntdll!RtlSetThreadPoolStartFunc` at `0x180038a6c`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x180038c24`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x180038c24`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180038b02`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180038b02`
- `ntdll!LdrSetDllManifestProber` at `0x180038a8d`
- `ntdll!LdrSetDllManifestProber` at `0x180038d00`
- `ntdll!LdrSetDllManifestProber` at `0x180038a8d`
- `ntdll!LdrSetDllManifestProber` at `0x180038d00`
- `KERNELBASE!GetRegistryExtensionFlags` at `0x180038c99`
- `KERNELBASE!GetRegistryExtensionFlags` at `0x180038c99`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180038a9f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180038a9f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180038a78`

## string_xrefs

- `0x180038c1d`: `SearchPathMode`

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
      qword_1800BE3F8 = v17;
      if ( v17 )
        qword_1800BE3F8 = (__int64)&v16[v17 - *((_QWORD *)v16 + 317)];
      else
        qword_1800BE3F8 = 0;
      if ( (ProcessParameters->Flags & 0x4000) == 0
        && LdrQueryImageFileExecutionOptions(&ProcessParameters->ImagePathName, L"SearchPathMode", 4u, Buffer, 4u, 0) >= 0 )
      {
        SetSearchPathMode(Buffer[0]);
      }
      if ( ProcessParameters && ProcessParameters->DebugFlags )
        __debugbreak();
      qword_1800BE3E8 = (__int64)&BasepAppCertDllsList;
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
0x1800389dc  mov     [rsp-8+arg_8], rbx
0x1800389e1  mov     [rsp-8+arg_10], rsi
0x1800389e6  push    rbp
0x1800389e7  push    rdi
0x1800389e8  push    r12
0x1800389ea  push    r14
0x1800389ec  push    r15
0x1800389ee  lea     rbp, [rsp-160h]
0x1800389f6  sub     rsp, 260h
0x1800389fd  mov     rax, cs:__security_cookie
0x180038a04  xor     rax, rsp
0x180038a07  mov     [rbp+180h+var_30], rax
0x180038a0e  xor     r14b, r14b
0x180038a11  mov     [rsp+280h+Buffer], 0
0x180038a19  mov     rbx, gs:60h
0x180038a22  mov     r15d, edx
0x180038a25  mov     r12, rcx
0x180038a28  mov     eax, edx
0x180038a2a  test    edx, edx
0x180038a2c  jz      loc_180038CB6
0x180038a32  cmp     eax, 1
0x180038a35  jnz     loc_180038CE6
0x180038a3b  mov     rcx, [rbx+10h]; BaseAddress
0x180038a3f  mov     rdi, [rbx+20h]
0x180038a43  call    cs:__imp_RtlImageNtHeader
0x180038a4a  nop     dword ptr [rax+rax+00h]
0x180038a4f  mov     rsi, rax
0x180038a52  test    rax, rax
0x180038a55  jnz     short loc_180038A5E
0x180038a57  xor     bl, bl
0x180038a59  jmp     loc_180038D0C
0x180038a5e  lea     rdx, BaseExitThreadPoolThread; ExitPoolThread
0x180038a65  lea     rcx, BaseCreateThreadPoolThread; StartPoolThread
0x180038a6c  call    cs:__imp_RtlSetThreadPoolStartFunc
0x180038a73  nop     dword ptr [rax+rax+00h]
0x180038a78  mov     r8, cs:__imp_ReleaseActCtx
0x180038a7f  lea     rdx, BasepRegenerateActCtxWithLanguage
0x180038a86  lea     rcx, BasepProbeForDllManifest; Routine
0x180038a8d  call    cs:__imp_LdrSetDllManifestProber
0x180038a94  nop     dword ptr [rax+rax+00h]
0x180038a99  mov     r14d, 1
0x180038a9f  call    cs:__imp_KernelBaseGetGlobalData
0x180038aa6  nop     dword ptr [rax+rax+00h]
0x180038aab  cmp     cs:SystemRangeStart, 0
0x180038ab3  movups  xmm0, xmmword ptr [rax+40h]
0x180038ab7  movsd   xmm1, qword ptr [rax+50h]
0x180038abc  movsd   cs:BaseHeap, xmm0
0x180038ac4  jnz     short loc_180038ACE
0x180038ac6  movsd   cs:SystemRangeStart, xmm1
0x180038ace  movzx   eax, word ptr [rsi+5Ch]
0x180038ad2  sub     ax, r14w
0x180038ad6  cmp     ax, 2
0x180038ada  ja      short loc_180038AE3
0x180038adc  cmp     word ptr [rsi+48h], 6
0x180038ae1  jnb     short loc_180038AFC
0x180038ae3  xor     r8d, r8d
0x180038ae6  lea     rcx, GUID_BasepAllowResourceConversion
0x180038aed  mov     rdx, r14
0x180038af0  call    cs:__imp_RtlSetProtectedPolicy
0x180038af7  nop     dword ptr [rax+rax+00h]
0x180038afc  mov     esi, [rbx+2C0h]
0x180038b02  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180038b09  nop     dword ptr [rax+rax+00h]
0x180038b0e  mov     edx, 200h; cbDest
0x180038b13  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180038b18  cmp     esi, eax
0x180038b1a  jnz     short loc_180038B2A
0x180038b1c  lea     r8, aWindows; "\\Windows"
0x180038b23  call    StringCbCopyW
0x180038b28  jmp     short loc_180038B4D
0x180038b2a  lea     rax, aWindows; "\\Windows"
0x180038b31  mov     [rsp+280h+RetunedLength], rax
0x180038b36  lea     r9, aSessions; "\\Sessions"
0x180038b3d  lea     r8, aWsLdWs; "%ws\\%ld%ws"
0x180038b44  mov     [rsp+280h+BufferSize], esi
0x180038b48  call    StringCbPrintfW
0x180038b4d  mov     rax, gs:60h
0x180038b56  mov     rcx, [rax+98h]
0x180038b5d  mov     rax, gs:60h
0x180038b66  mov     r8, [rcx+8]
0x180038b6a  sub     r8, [rax+380h]
0x180038b71  mov     rax, gs:60h
0x180038b7a  add     r8, [rax+88h]
0x180038b81  mov     cs:BaseStaticServerData, r8
0x180038b88  lea     rdx, [r8+3Ah]; SourceString
0x180038b8c  mov     cs:BaseCSDVersion, rdx
0x180038b93  test    rdx, rdx
0x180038b96  jz      short loc_180038BBC
0x180038b98  cmp     qword ptr [rbx+2F0h], 0
0x180038ba0  jnz     short loc_180038BBC
0x180038ba2  lea     rcx, [rbx+2E8h]; DestinationString
0x180038ba9  call    cs:__imp_RtlInitUnicodeString
0x180038bb0  nop     dword ptr [rax+rax+00h]
0x180038bb5  mov     r8, cs:BaseStaticServerData
0x180038bbc  mov     rax, [r8+7F8h]
0x180038bc3  mov     cs:BaseWindowsSys32x86Directory, rax
0x180038bca  mov     rax, [r8+800h]
0x180038bd1  mov     cs:qword_1800BE3F8, rax
0x180038bd8  test    rax, rax
0x180038bdb  jnz     short loc_180038BE6
0x180038bdd  mov     cs:qword_1800BE3F8, rax
0x180038be4  jmp     short loc_180038BF7
0x180038be6  sub     rax, [r8+9E8h]
0x180038bed  add     rax, r8
0x180038bf0  mov     cs:qword_1800BE3F8, rax
0x180038bf7  test    dword ptr [rdi+8], 4000h
0x180038bfe  jnz     short loc_180038C3D
0x180038c00  mov     r8d, 4; ValueSize
0x180038c06  mov     [rsp+280h+RetunedLength], 0; RetunedLength
0x180038c0f  lea     rcx, [rdi+60h]; SubKey
0x180038c13  mov     [rsp+280h+BufferSize], r8d; BufferSize
0x180038c18  lea     r9, [rsp+280h+Buffer]; Buffer
0x180038c1d  lea     rdx, aSearchpathmode; "SearchPathMode"
0x180038c24  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x180038c2b  nop     dword ptr [rax+rax+00h]
0x180038c30  test    eax, eax
0x180038c32  js      short loc_180038C3D
0x180038c34  mov     ecx, [rsp+280h+Buffer]; Flags
0x180038c38  call    SetSearchPathMode
0x180038c3d  test    rdi, rdi
0x180038c40  jz      short loc_180038C49
0x180038c42  cmp     dword ptr [rdi+0Ch], 0
0x180038c46  jz      short loc_180038C49
0x180038c48  int     3; Trap to Debugger
0x180038c49  lea     rax, BasepAppCertDllsList
0x180038c50  mov     cs:qword_1800BE3E8, rax
0x180038c57  mov     cs:BasepAppCertDllsList, rax
0x180038c5e  call    cs:__imp_RtlGetSuiteMask
0x180038c65  nop     dword ptr [rax+rax+00h]
0x180038c6a  test    al, 10h
0x180038c6c  jz      short loc_180038CA5
0x180038c6e  lea     rdx, [rsp+280h+var_248]
0x180038c73  mov     [rsp+280h+var_250], 0
0x180038c78  lea     rcx, [rsp+280h+var_250]
0x180038c7d  mov     dword ptr [rsp+280h+var_248], 0
0x180038c85  call    InitializeRegTermsrvFpns
0x180038c8a  test    al, al
0x180038c8c  jz      short loc_180038CA5
0x180038c8e  cmp     [rsp+280h+var_250], 0
0x180038c93  jz      short loc_180038CA5
0x180038c95  mov     ecx, dword ptr [rsp+280h+var_248]
0x180038c99  call    cs:__imp_GetRegistryExtensionFlags
0x180038ca0  nop     dword ptr [rax+rax+00h]
0x180038ca5  mov     rcx, r12; BaseAddress
0x180038ca8  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x180038caf  nop     dword ptr [rax+rax+00h]
0x180038cb4  jmp     short loc_180038CE6
0x180038cb6  lea     rax, LoadLibraryAStub
0x180038cbd  mov     [rsp+280h+var_248], rax
0x180038cc2  lea     rax, LoadLibraryWStub
0x180038cc9  mov     [rsp+280h+var_248], rax
0x180038cce  lea     rax, LoadLibraryExAStub
0x180038cd5  mov     [rsp+280h+var_248], rax
0x180038cda  lea     rax, LoadLibraryExWStub
0x180038ce1  mov     [rsp+280h+var_248], rax
0x180038ce6  mov     edx, r15d
0x180038ce9  call    _Kernel32LegacyLib_BaseDllInitialize
0x180038cee  mov     bl, al
0x180038cf0  test    al, al
0x180038cf2  jnz     short loc_180038D0C
0x180038cf4  test    r14b, r14b
0x180038cf7  jz      short loc_180038D0C
0x180038cf9  xor     r8d, r8d
0x180038cfc  xor     edx, edx
0x180038cfe  xor     ecx, ecx; Routine
0x180038d00  call    cs:__imp_LdrSetDllManifestProber
0x180038d07  nop     dword ptr [rax+rax+00h]
0x180038d0c  mov     al, bl
0x180038d0e  mov     rcx, [rbp+180h+var_30]
0x180038d15  xor     rcx, rsp; StackCookie
0x180038d18  call    __security_check_cookie
0x180038d1d  lea     r11, [rsp+280h+var_20]
0x180038d25  mov     rbx, [r11+38h]
0x180038d29  mov     rsi, [r11+40h]
0x180038d2d  mov     rsp, r11
0x180038d30  pop     r15
0x180038d32  pop     r14
0x180038d34  pop     r12
0x180038d36  pop     rdi
0x180038d37  pop     rbp
0x180038d38  retn
```
