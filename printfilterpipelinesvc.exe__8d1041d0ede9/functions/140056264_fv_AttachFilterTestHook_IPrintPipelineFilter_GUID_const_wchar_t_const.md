# fv::AttachFilterTestHook(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)

- ea: `0x140056264`
- end: `0x14005646f`
- name: `?AttachFilterTestHook@fv@@YAXPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@Z`
- size: `523`
- prototype: `void __fastcall(fv *__hidden this, struct IPrintPipelineFilter **, const struct _GUID *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140014408`

## callees

- `0x140004438`
- `0x14000dce8`
- `0x140056264`
- `0x140056478`
- `0x140056cb0`
- `0x140063010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400563ac`
- `ADVAPI32!RegCloseKey` at `0x1400563ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1400562eb`
- `ADVAPI32!RegOpenKeyExW` at `0x1400562eb`
- `ADVAPI32!RegQueryValueExW` at `0x140056331`
- `ADVAPI32!RegQueryValueExW` at `0x140056384`
- `ADVAPI32!RegQueryValueExW` at `0x140056331`
- `ADVAPI32!RegQueryValueExW` at `0x140056384`
- `KERNEL32!GetLastError` at `0x140056405`
- `KERNEL32!GetLastError` at `0x140056405`
- `KERNEL32!GetProcAddress` at `0x1400562a6`
- `KERNEL32!GetProcAddress` at `0x1400563e4`
- `KERNEL32!GetProcAddress` at `0x1400562a6`
- `KERNEL32!GetProcAddress` at `0x1400563e4`
- `KERNEL32!LoadLibraryW` at `0x1400563cf`
- `KERNEL32!LoadLibraryW` at `0x1400563cf`

## string_xrefs

- `0x140056394`: `FilterHook.dll`
- `0x14005629f`: `CreateFilterTestHook`
- `0x1400563da`: `CreateFilterTestHook`

## pseudocode

```c
void __fastcall fv::AttachFilterTestHook(
        fv *this,
        struct IPrintPipelineFilter **a2,
        const struct _GUID *a3,
        const wchar_t *a4)
{
  HMODULE PrintVerifierModule; // rcx
  int (*ProcAddress)(struct IPrintPipelineFilter **, const struct _GUID *, const wchar_t *); // rax
  int v9; // eax
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  struct SplLogType *v12; // rax
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-35h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-31h] BYREF
  int v16; // [rsp+40h] [rbp-29h] BYREF
  __int64 v17; // [rsp+48h] [rbp-21h]
  int v18; // [rsp+50h] [rbp-19h]
  DWORD v19; // [rsp+58h] [rbp-11h] BYREF
  __int64 v20; // [rsp+60h] [rbp-9h]
  int v21; // [rsp+68h] [rbp-1h]
  _BYTE v22[80]; // [rsp+70h] [rbp+7h] BYREF
  DWORD Type; // [rsp+E8h] [rbp+7Fh] BYREF

  PrintVerifierModule = fv::GetPrintVerifierModule(this);
  if ( PrintVerifierModule )
  {
    ProcAddress = fv::gpfnCreateFilterTestHook;
    if ( fv::gpfnCreateFilterTestHook )
      goto LABEL_21;
    ProcAddress = (int (*)(struct IPrintPipelineFilter **, const struct _GUID *, const wchar_t *))GetProcAddress(
                                                                                                    PrintVerifierModule,
                                                                                                    aCreatefilterte);
    fv::gpfnCreateFilterTestHook = ProcAddress;
    if ( ProcAddress )
      goto LABEL_21;
  }
  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, aSystemCurrentc_2, 0, 0x20019u, &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, aPipelinefilter, 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
    {
      v9 = *(_DWORD *)Data;
    }
    else
    {
      v9 = 0;
      *(_DWORD *)Data = 0;
    }
    if ( v9 == 1 )
    {
      Type = 0;
      cbData = 520;
      if ( RegQueryValueExW(hKey, aFilterhookmodu, 0, &Type, &fv::gszFilterHookModule, &cbData) || Type != 1 )
        StringCchCopyW((wchar_t *)&fv::gszFilterHookModule, 0x104u, L"FilterHook.dll");
    }
    RegCloseKey(hKey);
  }
  if ( *(_DWORD *)Data == 1 )
  {
    ProcAddress = fv::gpfnCreateFilterTestHook;
    if ( fv::gpfnCreateFilterTestHook )
      goto LABEL_21;
    LibraryW = LoadLibraryW((LPCWSTR)&fv::gszFilterHookModule);
    if ( LibraryW )
    {
      ProcAddress = (int (*)(struct IPrintPipelineFilter **, const struct _GUID *, const wchar_t *))GetProcAddress(LibraryW, aCreatefilterte);
      fv::gpfnCreateFilterTestHook = ProcAddress;
    }
    else
    {
      v16 = 104;
      v17 = 4;
      v18 = 0;
      LastError = GetLastError();
      v20 = 4;
      v19 = LastError;
      v21 = 0;
      v12 = SplLogType::SplLogType((SplLogType *)v22, (const wchar_t *)&fv::gszFilterHookModule);
      SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, v12, &v19, &v16, 0);
      ProcAddress = fv::gpfnCreateFilterTestHook;
    }
    if ( ProcAddress )
LABEL_21:
      ((void (__fastcall *)(fv *, struct IPrintPipelineFilter **, const struct _GUID *))ProcAddress)(this, a2, a3);
  }
}

```

## disassembly

```asm
0x140056264  push    rbp
0x140056266  push    rbx
0x140056267  push    rsi
0x140056268  push    rdi
0x140056269  push    r12
0x14005626b  push    r15
0x14005626d  lea     rbp, [rsp-2Fh]
0x140056272  sub     rsp, 98h
0x140056279  mov     rbx, r8
0x14005627c  mov     rdi, rdx
0x14005627f  mov     rsi, rcx
0x140056282  call    ?GetPrintVerifierModule@fv@@YAPEAUHINSTANCE__@@XZ; fv::GetPrintVerifierModule(void)
0x140056287  mov     rcx, rax; hModule
0x14005628a  test    rax, rax
0x14005628d  jz      short loc_1400562BC
0x14005628f  mov     rax, cs:?gpfnCreateFilterTestHook@fv@@3P6AJPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@ZEA; long (*fv::gpfnCreateFilterTestHook)(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)
0x140056296  test    rax, rax
0x140056299  jnz     loc_140056451
0x14005629f  lea     rdx, aCreatefilterte; "CreateFilterTestHook"
0x1400562a6  call    cs:__imp_GetProcAddress
0x1400562ac  mov     cs:?gpfnCreateFilterTestHook@fv@@3P6AJPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@ZEA, rax; long (*fv::gpfnCreateFilterTestHook)(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)
0x1400562b3  test    rax, rax
0x1400562b6  jnz     loc_140056451
0x1400562bc  lea     rax, [rbp+57h+hKey]
0x1400562c0  mov     [rbp+57h+hKey], 0
0x1400562c8  mov     r9d, 20019h; samDesired
0x1400562ce  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1400562d3  xor     r8d, r8d; ulOptions
0x1400562d6  mov     dword ptr [rbp+57h+Data], 0
0x1400562dd  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x1400562e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400562eb  call    cs:__imp_RegOpenKeyExW
0x1400562f1  mov     r15d, 4
0x1400562f7  lea     r12, ?gszFilterHookModule@fv@@3PA_WA; wchar_t near * fv::gszFilterHookModule
0x1400562fe  test    eax, eax
0x140056300  jnz     loc_1400563B2
0x140056306  mov     rcx, [rbp+57h+hKey]; hKey
0x14005630a  lea     r9, [rbp+57h+Type]; lpType
0x14005630e  mov     [rbp+57h+Type], eax
0x140056311  lea     rdx, aPipelinefilter; "PipelineFilterHook"
0x140056318  lea     rax, [rbp+57h+cbData]
0x14005631c  mov     [rbp+57h+cbData], r15d
0x140056320  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x140056325  xor     r8d, r8d; lpReserved
0x140056328  lea     rax, [rbp+57h+Data]
0x14005632c  mov     [rsp+0C0h+phkResult], rax; lpData
0x140056331  call    cs:__imp_RegQueryValueExW
0x140056337  test    eax, eax
0x140056339  jnz     short loc_14005634C
0x14005633b  cmp     [rbp+57h+Type], r15d
0x14005633f  jnz     short loc_14005634C
0x140056341  cmp     [rbp+57h+cbData], r15d
0x140056345  jnz     short loc_14005634C
0x140056347  mov     eax, dword ptr [rbp+57h+Data]
0x14005634a  jmp     short loc_140056351
0x14005634c  xor     eax, eax
0x14005634e  mov     dword ptr [rbp+57h+Data], eax
0x140056351  cmp     eax, 1
0x140056354  jnz     short loc_1400563A8
0x140056356  mov     rcx, [rbp+57h+hKey]; hKey
0x14005635a  lea     rax, [rbp+57h+cbData]
0x14005635e  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x140056363  lea     r9, [rbp+57h+Type]; lpType
0x140056367  xor     r8d, r8d; lpReserved
0x14005636a  mov     [rsp+0C0h+phkResult], r12; lpData
0x14005636f  lea     rdx, aFilterhookmodu; "FilterHookModuleName"
0x140056376  mov     [rbp+57h+Type], 0
0x14005637d  mov     [rbp+57h+cbData], 208h
0x140056384  call    cs:__imp_RegQueryValueExW
0x14005638a  test    eax, eax
0x14005638c  jnz     short loc_140056394
0x14005638e  cmp     [rbp+57h+Type], 1
0x140056392  jz      short loc_1400563A8
0x140056394  lea     r8, aFilterhookDll; "FilterHook.dll"
0x14005639b  mov     edx, 104h; unsigned __int64
0x1400563a0  mov     rcx, r12; wchar_t *
0x1400563a3  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400563a8  mov     rcx, [rbp+57h+hKey]; hKey
0x1400563ac  call    cs:__imp_RegCloseKey
0x1400563b2  cmp     dword ptr [rbp+57h+Data], 1
0x1400563b6  jnz     loc_14005645F
0x1400563bc  mov     rax, cs:?gpfnCreateFilterTestHook@fv@@3P6AJPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@ZEA; long (*fv::gpfnCreateFilterTestHook)(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)
0x1400563c3  test    rax, rax
0x1400563c6  jnz     loc_140056451
0x1400563cc  mov     rcx, r12; lpLibFileName
0x1400563cf  call    cs:__imp_LoadLibraryW
0x1400563d5  test    rax, rax
0x1400563d8  jz      short loc_1400563F3
0x1400563da  lea     rdx, aCreatefilterte; "CreateFilterTestHook"
0x1400563e1  mov     rcx, rax; hModule
0x1400563e4  call    cs:__imp_GetProcAddress
0x1400563ea  mov     cs:?gpfnCreateFilterTestHook@fv@@3P6AJPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@ZEA, rax; long (*fv::gpfnCreateFilterTestHook)(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)
0x1400563f1  jmp     short loc_14005644C
0x1400563f3  mov     [rbp+57h+var_80], 68h ; 'h'
0x1400563fa  mov     [rbp+57h+var_78], r15
0x1400563fe  mov     [rbp+57h+var_70], 0
0x140056405  call    cs:__imp_GetLastError
0x14005640b  mov     rdx, r12; wchar_t *
0x14005640e  mov     [rbp+57h+var_60], r15
0x140056412  lea     rcx, [rbp+57h+var_50]; this
0x140056416  mov     [rbp+57h+var_68], eax
0x140056419  mov     [rbp+57h+var_58], 0
0x140056420  call    ??0SplLogType@@QEAA@PEB_W@Z; SplLogType::SplLogType(wchar_t const *)
0x140056425  lea     r9, [rbp+57h+var_80]
0x140056429  mov     [rsp+0C0h+phkResult], 0
0x140056432  lea     r8, [rbp+57h+var_68]
0x140056436  mov     rdx, rax; struct SplLogType *
0x140056439  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x140056440  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x140056445  mov     rax, cs:?gpfnCreateFilterTestHook@fv@@3P6AJPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@ZEA; long (*fv::gpfnCreateFilterTestHook)(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)
0x14005644c  test    rax, rax
0x14005644f  jz      short loc_14005645F
0x140056451  mov     r8, rbx
0x140056454  mov     rdx, rdi
0x140056457  mov     rcx, rsi
0x14005645a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005645f  add     rsp, 98h
0x140056466  pop     r15
0x140056468  pop     r12
0x14005646a  pop     rdi
0x14005646b  pop     rsi
0x14005646c  pop     rbx
0x14005646d  pop     rbp
0x14005646e  retn
```
