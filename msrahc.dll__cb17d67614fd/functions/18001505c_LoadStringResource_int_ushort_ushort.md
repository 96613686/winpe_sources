# LoadStringResource(int,ushort *,ushort * *)

- ea: `0x18001505c`
- end: `0x18001521c`
- name: `?LoadStringResource@@YAJHPEAGPEAPEAG@Z`
- size: `448`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800114d0`

## callees

- `0x180006b48`
- `0x180014660`
- `0x18001505c`
- `0x18001a5e0`

## import_xrefs

- `USER32!LoadStringW` at `0x1800151ad`
- `USER32!LoadStringW` at `0x1800151ad`
- `KERNEL32!LoadLibraryExW` at `0x180015116`
- `KERNEL32!LoadLibraryExW` at `0x180015116`
- `KERNEL32!FreeLibrary` at `0x1800151e1`
- `KERNEL32!FreeLibrary` at `0x1800151e1`
- `KERNEL32!GetProcessHeap` at `0x180015150`
- `KERNEL32!GetProcessHeap` at `0x180015150`
- `KERNEL32!HeapAlloc` at `0x180015164`
- `KERNEL32!HeapAlloc` at `0x180015164`
- `SHELL32!SHGetKnownFolderPath` at `0x1800150a3`
- `SHELL32!SHGetKnownFolderPath` at `0x1800150a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151f1`

## string_xrefs

- `0x1800150db`: `FirewallAPI.DLL`
- `0x1800150b9`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x180015128`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x18001518c`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x1800151bb`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall LoadStringResource(UINT uID, unsigned __int16 *a2, unsigned __int16 **a3)
{
  HRESULT v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // r9d
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  HMODULE Library; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v14; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  PWSTR ppszPath; // [rsp+30h] [rbp-248h] BYREF
  WCHAR LibFileName[264]; // [rsp+40h] [rbp-238h] BYREF

  *a3 = 0;
  ppszPath = 0;
  v5 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
  v8 = v5;
  if ( v5 < 0 )
  {
    v9 = 303;
LABEL_3:
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      v9,
      L"LoadStringResource",
      v5);
    goto LABEL_13;
  }
  v5 = StringCchPrintfW(LibFileName, 0x104u, L"%s\\%s", ppszPath, L"FirewallAPI.DLL");
  v8 = v5;
  if ( v5 < 0 )
  {
    v9 = 310;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(LibFileName, 0, 2u);
  if ( Library )
  {
    ProcessHeap = GetProcessHeap();
    v14 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
    *a3 = v14;
    if ( v14 )
    {
      if ( !LoadStringW(Library, uID, v14, 260) )
      {
        CEventLogger::LogError(
          v18,
          v17,
          L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
          0x148u,
          L"LoadStringResource",
          0);
        v8 = -2147467259;
      }
    }
    else
    {
      v8 = -2147024882;
      CEventLogger::LogError(
        v16,
        v15,
        L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
        0x140u,
        L"LoadStringResource",
        0x8007000E);
    }
    FreeLibrary(Library);
  }
  else
  {
    CEventLogger::LogError(
      v11,
      v10,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x13Cu,
      L"LoadStringResource",
      0);
    v8 = -2147467259;
  }
LABEL_13:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return v8;
}

```

## disassembly

```asm
0x18001505c  mov     [rsp+arg_8], rbx
0x180015061  push    rbp
0x180015062  push    rsi
0x180015063  push    rdi
0x180015064  sub     rsp, 260h
0x18001506b  mov     rax, cs:__security_cookie
0x180015072  xor     rax, rsp
0x180015075  mov     [rsp+278h+var_28], rax
0x18001507d  mov     rsi, r8
0x180015080  mov     qword ptr [r8], 0
0x180015087  mov     ebp, ecx
0x180015089  mov     [rsp+278h+ppszPath], 0
0x180015092  xor     r8d, r8d; hToken
0x180015095  lea     rcx, FOLDERID_System; rfid
0x18001509c  lea     r9, [rsp+278h+ppszPath]; ppszPath
0x1800150a1  xor     edx, edx; dwFlags
0x1800150a3  call    cs:__imp_SHGetKnownFolderPath
0x1800150a9  mov     ebx, eax
0x1800150ab  test    eax, eax
0x1800150ad  jns     short loc_1800150D6
0x1800150af  mov     r9d, 12Fh; unsigned int
0x1800150b5  mov     [rsp+278h+var_250], eax; unsigned int
0x1800150b9  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x1800150c0  lea     rax, aLoadstringreso; "LoadStringResource"
0x1800150c7  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x1800150cc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800150d1  jmp     loc_1800151E7
0x1800150d6  mov     r9, [rsp+278h+ppszPath]
0x1800150db  lea     rax, aFirewallapiDll_0; "FirewallAPI.DLL"
0x1800150e2  lea     r8, aSS; "%s\\%s"
0x1800150e9  mov     [rsp+278h+var_258], rax
0x1800150ee  mov     edx, 104h; unsigned __int64
0x1800150f3  lea     rcx, [rsp+278h+LibFileName]; unsigned __int16 *
0x1800150f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800150fd  mov     ebx, eax
0x1800150ff  test    eax, eax
0x180015101  jns     short loc_18001510B
0x180015103  mov     r9d, 136h
0x180015109  jmp     short loc_1800150B5
0x18001510b  xor     edx, edx; hFile
0x18001510d  lea     rcx, [rsp+278h+LibFileName]; lpLibFileName
0x180015112  lea     r8d, [rdx+2]; dwFlags
0x180015116  call    cs:__imp_LoadLibraryExW
0x18001511c  mov     rdi, rax
0x18001511f  test    rax, rax
0x180015122  jnz     short loc_180015150
0x180015124  mov     [rsp+278h+var_250], eax; unsigned int
0x180015128  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x18001512f  lea     rax, aLoadstringreso; "LoadStringResource"
0x180015136  mov     r9d, 13Ch; unsigned int
0x18001513c  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x180015141  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180015146  mov     ebx, 80004005h
0x18001514b  jmp     loc_1800151E7
0x180015150  call    cs:__imp_GetProcessHeap
0x180015156  mov     edx, 8; dwFlags
0x18001515b  mov     r8d, 208h; dwBytes
0x180015161  mov     rcx, rax; hHeap
0x180015164  call    cs:__imp_HeapAlloc
0x18001516a  mov     [rsi], rax
0x18001516d  test    rax, rax
0x180015170  jnz     short loc_18001519F
0x180015172  lea     rax, aLoadstringreso; "LoadStringResource"
0x180015179  mov     [rsp+278h+var_250], 8007000Eh; unsigned int
0x180015181  mov     r9d, 140h; unsigned int
0x180015187  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001518c  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x180015193  mov     ebx, 8007000Eh
0x180015198  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001519d  jmp     short loc_1800151DE
0x18001519f  mov     r9d, 104h; cchBufferMax
0x1800151a5  mov     r8, rax; lpBuffer
0x1800151a8  mov     edx, ebp; uID
0x1800151aa  mov     rcx, rdi; hInstance
0x1800151ad  call    cs:__imp_LoadStringW
0x1800151b3  test    eax, eax
0x1800151b5  jnz     short loc_1800151DE
0x1800151b7  mov     [rsp+278h+var_250], eax; unsigned int
0x1800151bb  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x1800151c2  lea     rax, aLoadstringreso; "LoadStringResource"
0x1800151c9  mov     r9d, 148h; unsigned int
0x1800151cf  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x1800151d4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800151d9  mov     ebx, 80004005h
0x1800151de  mov     rcx, rdi; hLibModule
0x1800151e1  call    cs:__imp_FreeLibrary
0x1800151e7  mov     rcx, [rsp+278h+ppszPath]; pv
0x1800151ec  test    rcx, rcx
0x1800151ef  jz      short loc_1800151F7
0x1800151f1  call    cs:__imp_CoTaskMemFree
0x1800151f7  mov     eax, ebx
0x1800151f9  mov     rcx, [rsp+278h+var_28]
0x180015201  xor     rcx, rsp; StackCookie
0x180015204  call    __security_check_cookie
0x180015209  mov     rbx, [rsp+278h+arg_8]
0x180015211  add     rsp, 260h
0x180015218  pop     rdi
0x180015219  pop     rsi
0x18001521a  pop     rbp
0x18001521b  retn
```
