# ReSyncSysTime(void)

- ea: `0x1800174e4`
- end: `0x180017625`
- name: `?ReSyncSysTime@@YAJXZ`
- size: `321`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ebe0`

## callees

- `0x180014660`
- `0x180017078`
- `0x1800174e4`
- `0x18001762c`
- `0x1800177d4`
- `0x18001c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001754b`
- `KERNEL32!LoadLibraryW` at `0x18001754b`
- `KERNEL32!FreeLibrary` at `0x1800175db`
- `KERNEL32!FreeLibrary` at `0x1800175db`
- `KERNEL32!GetProcAddress` at `0x180017567`
- `KERNEL32!GetProcAddress` at `0x180017567`

## string_xrefs

- `0x180017512`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x1800175c2`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x1800175fd`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180017544`: `w32time.dll`

## pseudocode

```c
__int64 ReSyncSysTime(void)
{
  signed int started; // eax
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // r9d
  int v5; // ebp
  HMODULE LibraryW; // rax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  HMODULE v9; // rsi
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  FARPROC ProcAddress; // r14
  unsigned int v13; // eax
  unsigned int i; // edi

  started = IsW32TimeRunning();
  v3 = started;
  if ( started == -2147023834 )
  {
    started = StartW32Time();
    v3 = started;
    if ( started < 0 )
    {
      v4 = 900;
LABEL_4:
      CEventLogger::LogError(
        v2,
        v1,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        v4,
        L"ReSyncSysTime",
        started);
      return v3;
    }
    v5 = 1;
  }
  else
  {
    if ( started < 0 )
    {
      v4 = 905;
      goto LABEL_4;
    }
    v5 = 0;
  }
  LibraryW = LoadLibraryW(L"w32time.dll");
  v9 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "W32TimeSyncNow");
    if ( ProcAddress )
    {
      v13 = 0;
      for ( i = 0; i < 2; ++i )
      {
        v13 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
        if ( !v13 )
        {
          v3 = 0;
          goto LABEL_20;
        }
      }
      if ( !v13 )
        goto LABEL_20;
      CEventLogger::LogError(
        v11,
        v10,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        0x3A6u,
        L"ReSyncSysTime",
        v13);
    }
    else
    {
      CEventLogger::LogError(
        v11,
        v10,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        0x390u,
        L"ReSyncSysTime",
        0);
    }
    v3 = -2147467259;
LABEL_20:
    FreeLibrary(v9);
    goto LABEL_22;
  }
  CEventLogger::LogError(v8, v7, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x38Cu, L"ReSyncSysTime", 0);
  v3 = -2147467259;
LABEL_22:
  if ( v5 == 1 )
    StopW32Time();
  return v3;
}

```

## disassembly

```asm
0x1800174e4  push    rbx
0x1800174e6  push    rbp
0x1800174e7  push    rsi
0x1800174e8  push    rdi
0x1800174e9  push    r14
0x1800174eb  sub     rsp, 30h
0x1800174ef  call    ?IsW32TimeRunning@@YAJXZ; IsW32TimeRunning(void)
0x1800174f4  mov     ebx, eax
0x1800174f6  cmp     eax, 80070426h
0x1800174fb  jnz     short loc_180017536
0x1800174fd  call    ?StartW32Time@@YAJXZ; StartW32Time(void)
0x180017502  mov     ebx, eax
0x180017504  test    eax, eax
0x180017506  jns     short loc_18001752F
0x180017508  mov     r9d, 384h; unsigned int
0x18001750e  mov     [rsp+58h+var_30], eax; unsigned int
0x180017512  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017519  lea     rax, aResyncsystime; "ReSyncSysTime"
0x180017520  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180017525  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001752a  jmp     loc_180017618
0x18001752f  mov     ebp, 1
0x180017534  jmp     short loc_180017544
0x180017536  test    eax, eax
0x180017538  jns     short loc_180017542
0x18001753a  mov     r9d, 389h
0x180017540  jmp     short loc_18001750E
0x180017542  xor     ebp, ebp
0x180017544  lea     rcx, aW32timeDll; "w32time.dll"
0x18001754b  call    cs:__imp_LoadLibraryW
0x180017551  mov     rsi, rax
0x180017554  test    rax, rax
0x180017557  jz      loc_1800175E3
0x18001755d  lea     rdx, aW32timesyncnow; "W32TimeSyncNow"
0x180017564  mov     rcx, rax; hModule
0x180017567  call    cs:__imp_GetProcAddress
0x18001756d  mov     r14, rax
0x180017570  test    rax, rax
0x180017573  jz      short loc_1800175AD
0x180017575  xor     eax, eax
0x180017577  xor     edi, edi
0x180017579  cmp     edi, 2
0x18001757c  jnb     short loc_18001759D
0x18001757e  mov     edx, 1
0x180017583  xor     ecx, ecx
0x180017585  mov     rax, r14
0x180017588  lea     r8d, [rdx+11h]
0x18001758c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017591  test    eax, eax
0x180017593  jz      short loc_180017599
0x180017595  inc     edi
0x180017597  jmp     short loc_180017579
0x180017599  xor     ebx, ebx
0x18001759b  jmp     short loc_1800175D8
0x18001759d  test    eax, eax
0x18001759f  jz      short loc_1800175D8
0x1800175a1  mov     [rsp+58h+var_30], eax
0x1800175a5  mov     r9d, 3A6h
0x1800175ab  jmp     short loc_1800175BB
0x1800175ad  mov     [rsp+58h+var_30], 0; unsigned int
0x1800175b5  mov     r9d, 390h; unsigned int
0x1800175bb  lea     rax, aResyncsystime; "ReSyncSysTime"
0x1800175c2  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x1800175c9  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800175ce  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800175d3  mov     ebx, 80004005h
0x1800175d8  mov     rcx, rsi; hLibModule
0x1800175db  call    cs:__imp_FreeLibrary
0x1800175e1  jmp     short loc_18001760E
0x1800175e3  lea     rax, aResyncsystime; "ReSyncSysTime"
0x1800175ea  mov     [rsp+58h+var_30], 0; unsigned int
0x1800175f2  mov     r9d, 38Ch; unsigned int
0x1800175f8  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800175fd  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017604  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180017609  mov     ebx, 80004005h
0x18001760e  cmp     ebp, 1
0x180017611  jnz     short loc_180017618
0x180017613  call    ?StopW32Time@@YAJXZ; StopW32Time(void)
0x180017618  mov     eax, ebx
0x18001761a  add     rsp, 30h
0x18001761e  pop     r14
0x180017620  pop     rdi
0x180017621  pop     rsi
0x180017622  pop     rbp
0x180017623  pop     rbx
0x180017624  retn
```
