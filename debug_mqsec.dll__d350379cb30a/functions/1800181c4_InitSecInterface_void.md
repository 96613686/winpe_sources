# InitSecInterface(void)

- ea: `0x1800181c4`
- end: `0x180018348`
- name: `?InitSecInterface@@YAJXZ`
- size: `388`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017fd0`
- `0x180018350`

## callees

- `0x180004074`
- `0x180017430`
- `0x1800181c4`

## import_xrefs

- `Secur32!QuerySecurityPackageInfoW` at `0x180018299`
- `Secur32!QuerySecurityPackageInfoW` at `0x180018299`
- `Secur32!InitSecurityInterfaceW` at `0x180018285`
- `Secur32!InitSecurityInterfaceW` at `0x180018285`
- `KERNEL32!GetProcAddress` at `0x180018269`
- `KERNEL32!GetProcAddress` at `0x180018269`
- `KERNEL32!LoadLibraryW` at `0x1800181e5`
- `KERNEL32!LoadLibraryW` at `0x1800181e5`

## string_xrefs

- `0x1800181de`: `SCHANNEL.DLL`
- `0x180018292`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
__int64 InitSecInterface(void)
{
  HMODULE LibraryW; // rax
  __int16 v1; // ax
  SECURITY_STATUS SecurityPackageInfoW; // eax
  __int64 v3; // r9
  __int16 v5; // [rsp+70h] [rbp+10h] BYREF
  int v6; // [rsp+78h] [rbp+18h] BYREF

  if ( !dword_18004313C )
  {
    LibraryW = LoadLibraryW(L"SCHANNEL.DLL");
    g_hSchannelDll = LibraryW;
    if ( !LibraryW )
    {
      v1 = 10;
      goto LABEL_4;
    }
    g_pfnSealMessage = (int (*)(struct _SecHandle *, unsigned int, struct _SecBufferDesc *, unsigned int))GetProcAddress(LibraryW, "SealMessage");
    if ( !g_pfnSealMessage )
    {
      v1 = 20;
LABEL_4:
      v5 = v1;
      v6 = -1072822997;
      if ( !g_pMSMQErrorLoggingTrace )
        return 3222144299LL;
LABEL_11:
      v3 = mqwcslen(L"srvauthn/sspi.cpp") + 1;
      CMSMQTrace::MSMQTraceEvent(g_pMSMQErrorLoggingTrace, 1, 1, 2 * v3, L"srvauthn/sspi.cpp", 2, &v5, 4, &v6, 0, 0);
      return 3222144299LL;
    }
    InitSecurityInterfaceW();
    SecurityPackageInfoW = QuerySecurityPackageInfoW(
                             (LPWSTR)L"Microsoft Unified Security Protocol Provider",
                             &g_PackageInfo);
    if ( SecurityPackageInfoW )
    {
      if ( SecurityPackageInfoW >= 0 )
        return 3222144299LL;
      v5 = 50;
      v6 = SecurityPackageInfoW;
      if ( !g_pMSMQErrorLoggingTrace )
        return 3222144299LL;
      goto LABEL_11;
    }
    dword_18004313C = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800181c4  mov     [rsp-8+arg_10], rbx
0x1800181c9  push    rbp
0x1800181ca  mov     rbp, rsp
0x1800181cd  sub     rsp, 60h
0x1800181d1  cmp     cs:dword_18004313C, 0
0x1800181d8  jnz     loc_180018338
0x1800181de  lea     rcx, aSchannelDll; "SCHANNEL.DLL"
0x1800181e5  call    cs:__imp_LoadLibraryW
0x1800181eb  mov     cs:?g_hSchannelDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hSchannelDll
0x1800181f2  test    rax, rax
0x1800181f5  jnz     short loc_18001825F
0x1800181f7  mov     eax, 0Ah
0x1800181fc  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018204  mov     [rbp+arg_0], ax
0x180018208  mov     [rbp+arg_8], 0C00E052Bh
0x18001820f  jz      loc_180018326
0x180018215  lea     rbx, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x18001821c  mov     rcx, rbx; wchar_t *
0x18001821f  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180018224  mov     [rsp+60h+var_10], 0
0x18001822d  mov     ecx, 1
0x180018232  mov     [rsp+60h+var_18], 0
0x18001823b  lea     r9d, [rcx+rax]
0x18001823f  lea     rax, [rbp+arg_8]
0x180018243  mov     [rsp+60h+var_20], rax
0x180018248  lea     rax, [rbp+arg_0]
0x18001824c  mov     [rsp+60h+var_28], 4
0x180018255  mov     [rsp+60h+var_30], rax
0x18001825a  jmp     loc_180018304
0x18001825f  lea     rdx, aSealmessage; "SealMessage"
0x180018266  mov     rcx, rax; hModule
0x180018269  call    cs:__imp_GetProcAddress
0x18001826f  mov     cs:?g_pfnSealMessage@@3P6AJPEAU_SecHandle@@KPEAU_SecBufferDesc@@K@ZEA, rax; long (*g_pfnSealMessage)(_SecHandle *,ulong,_SecBufferDesc *,ulong)
0x180018276  test    rax, rax
0x180018279  jnz     short loc_180018285
0x18001827b  mov     eax, 14h
0x180018280  jmp     loc_1800181FC
0x180018285  call    cs:__imp_InitSecurityInterfaceW
0x18001828b  lea     rdx, ?g_PackageInfo@@3PEAU_SecPkgInfoW@@EA; ppPackageInfo
0x180018292  lea     rcx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x180018299  call    cs:__imp_QuerySecurityPackageInfoW
0x18001829f  test    eax, eax
0x1800182a1  jz      loc_18001832D
0x1800182a7  jns     short loc_180018326
0x1800182a9  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800182b1  mov     ecx, 32h ; '2'
0x1800182b6  mov     [rbp+arg_0], cx
0x1800182ba  mov     [rbp+arg_8], eax
0x1800182bd  jz      short loc_180018326
0x1800182bf  lea     rbx, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x1800182c6  mov     rcx, rbx; wchar_t *
0x1800182c9  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800182ce  mov     [rsp+60h+var_10], 0
0x1800182d7  lea     rdx, [rbp+arg_0]
0x1800182db  mov     [rsp+60h+var_18], 0
0x1800182e4  mov     ecx, 1
0x1800182e9  lea     r9d, [rcx+rax]
0x1800182ed  lea     rax, [rbp+arg_8]
0x1800182f1  mov     [rsp+60h+var_20], rax
0x1800182f6  mov     [rsp+60h+var_28], 4
0x1800182ff  mov     [rsp+60h+var_30], rdx
0x180018304  mov     r8d, ecx
0x180018307  mov     [rsp+60h+var_38], 2
0x180018310  mov     edx, ecx
0x180018312  mov     [rsp+60h+var_40], rbx
0x180018317  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001831e  add     r9, r9
0x180018321  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180018326  mov     eax, 0C00E052Bh
0x18001832b  jmp     short loc_18001833A
0x18001832d  mov     ecx, 1
0x180018332  mov     cs:dword_18004313C, ecx
0x180018338  xor     eax, eax
0x18001833a  mov     rbx, [rsp+60h+arg_10]
0x180018342  add     rsp, 60h
0x180018346  pop     rbp
0x180018347  retn
```
