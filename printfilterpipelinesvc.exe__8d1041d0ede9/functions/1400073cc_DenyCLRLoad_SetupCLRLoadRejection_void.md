# DenyCLRLoad::SetupCLRLoadRejection(void)

- ea: `0x1400073cc`
- end: `0x1400074ad`
- name: `?SetupCLRLoadRejection@DenyCLRLoad@@SAJXZ`
- size: `225`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x140007fb0`

## callees

- `0x140004438`
- `0x1400073cc`
- `0x140056cb0`
- `0x140063010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000742e`
- `KERNEL32!FreeLibrary` at `0x14000742e`
- `KERNEL32!GetLastError` at `0x140007450`
- `KERNEL32!GetLastError` at `0x140007450`
- `KERNEL32!GetProcAddress` at `0x140007402`
- `KERNEL32!GetProcAddress` at `0x140007402`
- `KERNEL32!LoadLibraryExW` at `0x1400073ea`
- `KERNEL32!LoadLibraryExW` at `0x1400073ea`

## string_xrefs

- `0x1400073dc`: `mscoree.dll`
- `0x140007456`: `mscoree.dll`

## pseudocode

```c
__int64 DenyCLRLoad::SetupCLRLoadRejection(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  struct SplLogType *v4; // rax
  int v6; // [rsp+30h] [rbp-58h] BYREF
  __int64 v7; // [rsp+38h] [rbp-50h]
  int v8; // [rsp+40h] [rbp-48h]
  DWORD LastError; // [rsp+48h] [rbp-40h] BYREF
  __int64 v10; // [rsp+50h] [rbp-38h]
  int v11; // [rsp+58h] [rbp-30h]
  _BYTE v12[40]; // [rsp+60h] [rbp-28h] BYREF

  v0 = -2147467259;
  Library = LoadLibraryExW(L"mscoree.dll", 0, 0);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "LockClrVersion");
    if ( ProcAddress )
      return ((unsigned int (__fastcall *)(__int64 (*)(void), int (**)(void), int (**)(void)))ProcAddress)(
               DenyCLRLoad::GenericCLRCallbackRejector,
               &DenyCLRLoad::pfnBeginHostSetup,
               &DenyCLRLoad::pfnEndHostSetup);
    else
      FreeLibrary(v2);
  }
  else
  {
    v6 = 103;
    v7 = 4;
    v8 = 0;
    v10 = 4;
    LastError = GetLastError();
    v11 = 0;
    v4 = SplLogType::SplLogType((SplLogType *)v12, L"mscoree.dll");
    SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, v4, &LastError, &v6, 0);
  }
  return v0;
}

```

## disassembly

```asm
0x1400073cc  mov     [rsp+arg_0], rbx
0x1400073d1  push    rdi
0x1400073d2  sub     rsp, 80h
0x1400073d9  xor     r8d, r8d; dwFlags
0x1400073dc  lea     rcx, ?szCLRBootStrapper@?1??SetupCLRLoadRejection@DenyCLRLoad@@SAJXZ@4QB_WB; "mscoree.dll"
0x1400073e3  xor     edx, edx; hFile
0x1400073e5  mov     edi, 80004005h
0x1400073ea  call    cs:__imp_LoadLibraryExW
0x1400073f0  mov     rbx, rax
0x1400073f3  test    rax, rax
0x1400073f6  jz      short loc_140007436
0x1400073f8  lea     rdx, ?szLockClrVersionExportName@?1??SetupCLRLoadRejection@DenyCLRLoad@@SAJXZ@4QBDB; "LockClrVersion"
0x1400073ff  mov     rcx, rax; hModule
0x140007402  call    cs:__imp_GetProcAddress
0x140007408  test    rax, rax
0x14000740b  jz      short loc_14000742B
0x14000740d  lea     r8, ?pfnEndHostSetup@DenyCLRLoad@@0P6AJXZEA; long (*DenyCLRLoad::pfnEndHostSetup)(void)
0x140007414  lea     rdx, ?pfnBeginHostSetup@DenyCLRLoad@@0P6AJXZEA; long (*DenyCLRLoad::pfnBeginHostSetup)(void)
0x14000741b  lea     rcx, ?GenericCLRCallbackRejector@DenyCLRLoad@@CAJXZ; DenyCLRLoad::GenericCLRCallbackRejector(void)
0x140007422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007427  mov     edi, eax
0x140007429  jmp     short loc_14000749A
0x14000742b  mov     rcx, rbx; hLibModule
0x14000742e  call    cs:__imp_FreeLibrary
0x140007434  jmp     short loc_14000749A
0x140007436  mov     ebx, 4
0x14000743b  mov     [rsp+88h+var_58], 67h ; 'g'
0x140007443  mov     [rsp+88h+var_50], rbx
0x140007448  mov     [rsp+88h+var_48], 0
0x140007450  call    cs:__imp_GetLastError
0x140007456  lea     rdx, ?szCLRBootStrapper@?1??SetupCLRLoadRejection@DenyCLRLoad@@SAJXZ@4QB_WB; "mscoree.dll"
0x14000745d  mov     [rsp+88h+var_38], rbx
0x140007462  lea     rcx, [rsp+88h+var_28]; this
0x140007467  mov     [rsp+88h+var_40], eax
0x14000746b  mov     [rsp+88h+var_30], 0
0x140007473  call    ??0SplLogType@@QEAA@PEB_W@Z; SplLogType::SplLogType(wchar_t const *)
0x140007478  lea     r9, [rsp+88h+var_58]
0x14000747d  mov     [rsp+88h+var_68], 0
0x140007486  lea     r8, [rsp+88h+var_40]
0x14000748b  mov     rdx, rax; struct SplLogType *
0x14000748e  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x140007495  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x14000749a  mov     rbx, [rsp+88h+arg_0]
0x1400074a2  mov     eax, edi
0x1400074a4  add     rsp, 80h
0x1400074ab  pop     rdi
0x1400074ac  retn
```
