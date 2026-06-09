# CMachineInfoV2::GetTelemetryLevelLimitEnhanced(void)

- ea: `0x18003c900`
- end: `0x18003ca15`
- name: `?GetTelemetryLevelLimitEnhanced@CMachineInfoV2@@QEBAIXZ`
- size: `277`
- prototype: `unsigned int __fastcall(CMachineInfoV2 *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x18003c900`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c927`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c927`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c94f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c963`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c94f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9fb`

## string_xrefs

- `0x18003c920`: `policymanager.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMachineInfoV2::GetTelemetryLevelLimitEnhanced(CMachineInfoV2 *this)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v4; // rax
  void (__fastcall *v5)(__int64); // rdi
  signed int LastError; // eax
  int v8; // edx
  unsigned int v9; // r8d
  const int *v10; // [rsp+30h] [rbp-10h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-8h]
  int v12; // [rsp+68h] [rbp+28h] BYREF
  int v13; // [rsp+6Ch] [rbp+2Ch]
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF

  v1 = -1;
  Library = LoadLibraryExW(L"policymanager.dll", 0, 0x800u);
  v10 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "PolicyManager_GetPolicy");
    v4 = GetProcAddress(hModule, "PolicyManager_FreeGetPolicyData");
    v5 = (void (__fastcall *)(__int64))v4;
    if ( ProcAddress )
    {
      if ( v4 )
      {
        v14 = 0;
        v12 = 1;
        v13 = 2;
        if ( ((int (__fastcall *)(const wchar_t *, const wchar_t *, int *, __int64 *))ProcAddress)(
               L"System",
               L"LimitEnhancedDiagnosticDataWindowsAnalytics",
               &v12,
               &v14) >= 0 )
        {
          if ( !v14 )
            goto LABEL_10;
          if ( *(_DWORD *)(v14 + 8) == 1 )
            v1 = *(_DWORD *)(v14 + 16);
        }
        if ( v14 )
          v5(v14);
      }
    }
  }
LABEL_10:
  v10 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v10) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v8, v9);
    JUMPOUT(0x18003CA14LL);
  }
  return v1;
}

```

## disassembly

```asm
0x18003c900  mov     [rsp-18h+arg_0], rbx
0x18003c905  mov     [rsp-18h+arg_18], rsi
0x18003c90a  push    rbp
0x18003c90b  push    rdi
0x18003c90c  push    r14
0x18003c90e  mov     rbp, rsp
0x18003c911  sub     rsp, 40h
0x18003c915  or      ebx, 0FFFFFFFFh
0x18003c918  xor     edx, edx; hFile
0x18003c91a  mov     r8d, 800h; dwFlags
0x18003c920  lea     rcx, aPolicymanagerD; "policymanager.dll"
0x18003c927  call    cs:__imp_LoadLibraryExW
0x18003c92d  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003c934  mov     [rbp+var_10], r14
0x18003c938  mov     [rbp+hModule], rax
0x18003c93c  test    rax, rax
0x18003c93f  jz      loc_18003C9CE
0x18003c945  lea     rdx, aPolicymanagerG_1; "PolicyManager_GetPolicy"
0x18003c94c  mov     rcx, rax; hModule
0x18003c94f  call    cs:__imp_GetProcAddress
0x18003c955  mov     rsi, rax
0x18003c958  lea     rdx, aPolicymanagerF_0; "PolicyManager_FreeGetPolicyData"
0x18003c95f  mov     rcx, [rbp+hModule]; hModule
0x18003c963  call    cs:__imp_GetProcAddress
0x18003c969  mov     rdi, rax
0x18003c96c  test    rsi, rsi
0x18003c96f  jz      short loc_18003C9CE
0x18003c971  test    rax, rax
0x18003c974  jz      short loc_18003C9CE
0x18003c976  mov     [rbp+arg_10], 0
0x18003c97e  mov     [rbp+arg_8], 1
0x18003c985  mov     [rbp+arg_C], 2
0x18003c98c  lea     r9, [rbp+arg_10]
0x18003c990  lea     r8, [rbp+arg_8]
0x18003c994  lea     rdx, aLimitenhancedd; "LimitEnhancedDiagnosticDataWindowsAnaly"...
0x18003c99b  lea     rcx, aSystem; "System"
0x18003c9a2  mov     rax, rsi
0x18003c9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9aa  mov     rcx, [rbp+arg_10]
0x18003c9ae  test    eax, eax
0x18003c9b0  js      short loc_18003C9C0
0x18003c9b2  test    rcx, rcx
0x18003c9b5  jz      short loc_18003C9CE
0x18003c9b7  cmp     dword ptr [rcx+8], 1
0x18003c9bb  jnz     short loc_18003C9C0
0x18003c9bd  mov     ebx, [rcx+10h]
0x18003c9c0  test    rcx, rcx
0x18003c9c3  jz      short loc_18003C9CE
0x18003c9c5  mov     rax, rdi
0x18003c9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9cd  nop
0x18003c9ce  mov     [rbp+var_10], r14
0x18003c9d2  cmp     [rbp+hModule], 0
0x18003c9d7  jz      short loc_18003C9E6
0x18003c9d9  lea     rcx, [rbp+var_10]
0x18003c9dd  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003c9e2  test    al, al
0x18003c9e4  jz      short loc_18003C9FB
0x18003c9e6  mov     eax, ebx
0x18003c9e8  mov     rbx, [rsp+40h+arg_0]
0x18003c9ed  mov     rsi, [rsp+40h+arg_18]
0x18003c9f2  add     rsp, 40h
0x18003c9f6  pop     r14
0x18003c9f8  pop     rdi
0x18003c9f9  pop     rbp
0x18003c9fa  retn
0x18003c9fb  call    cs:__imp_GetLastError
0x18003ca01  test    eax, eax
0x18003ca03  jle     short loc_18003CA0D
0x18003ca05  movzx   eax, ax
0x18003ca08  or      eax, 80070000h
0x18003ca0d  mov     ecx, eax; this
0x18003ca0f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
