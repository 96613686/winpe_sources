# _anonymous_namespace_::GetAppTimestamp

- ea: `0x180062828`
- end: `0x180062a0c`
- name: `_anonymous_namespace_::GetAppTimestamp`
- size: `484`
- prototype: `__int64 __fastcall(HANDLE hProcess, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180062ee0`

## callees

- `0x180021d38`
- `0x18004f890`
- `0x180053a98`
- `0x1800627e4`
- `0x180062808`
- `0x180062828`
- `0x180062bfc`
- `0x180083bc2`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180062924`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180062924`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062964`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062964`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180062857`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180062857`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180062906`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180062906`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180062864`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180062864`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800628a6`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800628a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::GetAppTimestamp(HANDLE hProcess, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 v4; // rsi
  DWORD ProcessId; // eax
  HANDLE Toolhelp32Snapshot; // rbx
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  HMODULE Library; // rax
  const char *v12; // r9
  const void *v13; // rbx
  HANDLE CurrentProcess; // rax
  int TimestampFromProcessModule; // eax
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  HMODULE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  MODULEENTRY32W me; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  v4 = a2;
  ProcessId = GetProcessId(hProcess);
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, ProcessId);
  v20[0] = Toolhelp32Snapshot;
  if ( (((unsigned __int64)Toolhelp32Snapshot + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v9 = 139;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                  v8);
    goto LABEL_18;
  }
  memset_0(&me.th32ModuleID, 0, 0x434u);
  me.dwSize = 1080;
  if ( !Module32FirstW(Toolhelp32Snapshot, &me) )
  {
    v9 = 143;
    goto LABEL_5;
  }
  if ( (int)anonymous_namespace_::GetTimestampFromProcessModule(hProcess, me.hModule) < 0 )
  {
    if ( !K32GetModuleFileNameExW(hProcess, me.hModule, Filename, 0x104u) )
    {
      v9 = 151;
      goto LABEL_5;
    }
    Library = LoadLibraryExW(Filename, 0, 2u);
    v19 = Library;
    if ( !Library )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x9A,
                    (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                    v12);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v19);
      goto LABEL_18;
    }
    v13 = (const void *)((unsigned __int64)Library & 0xFFFFFFFFFFFFFFFCuLL);
    CurrentProcess = GetCurrentProcess();
    TimestampFromProcessModule = anonymous_namespace_::GetTimestampFromProcessModule(CurrentProcess, v13);
    LastError = TimestampFromProcessModule;
    if ( TimestampFromProcessModule < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
        (const char *)(unsigned int)TimestampFromProcessModule,
        0);
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v19);
  }
  v16 = StringCchPrintfW(a3, v4, L"%08x", 0, 0, v19, v20[0]);
  LastError = v16;
  if ( v16 >= 0 )
    LastError = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
      (const char *)(unsigned int)v16,
      v18);
LABEL_18:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
  return LastError;
}

```

## disassembly

```asm
0x180062828  push    rbp
0x18006282a  push    rbx
0x18006282b  push    rsi
0x18006282c  push    rdi
0x18006282d  push    r14
0x18006282f  lea     rbp, [rsp-5A0h]
0x180062837  sub     rsp, 6A0h
0x18006283e  mov     rax, cs:__security_cookie
0x180062845  xor     rax, rsp
0x180062848  mov     [rbp+5C0h+var_30], rax
0x18006284f  mov     r14, r8
0x180062852  mov     esi, edx
0x180062854  mov     rdi, rcx
0x180062857  call    cs:__imp_GetProcessId
0x18006285d  mov     edx, eax; th32ProcessID
0x18006285f  mov     ecx, 8; dwFlags
0x180062864  call    cs:__imp_CreateToolhelp32Snapshot
0x18006286a  mov     rbx, rax
0x18006286d  mov     [rsp+6C0h+var_690], rax
0x180062872  inc     rax
0x180062875  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006287b  jnz     short loc_180062884
0x18006287d  mov     edx, 8Bh
0x180062882  jmp     short loc_1800628B5
0x180062884  xor     edx, edx; Val
0x180062886  mov     r8d, 434h; Size
0x18006288c  lea     rcx, [rsp+6C0h+me.th32ModuleID]; void *
0x180062891  call    memset_0
0x180062896  mov     [rsp+6C0h+me.dwSize], 438h
0x18006289e  lea     rdx, [rsp+6C0h+me]; lpme
0x1800628a3  mov     rcx, rbx; hSnapshot
0x1800628a6  call    cs:__imp_Module32FirstW
0x1800628ac  test    eax, eax
0x1800628ae  jnz     short loc_1800628CF
0x1800628b0  mov     edx, 8Fh; void *
0x1800628b5  mov     rcx, [rbp+5C8h]; this
0x1800628bc  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x1800628c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800628c8  mov     ebx, eax
0x1800628ca  jmp     loc_1800629E3
0x1800628cf  mov     [rsp+6C0h+var_6A0], 0; int
0x1800628d7  lea     r8, [rsp+6C0h+var_6A0]
0x1800628dc  mov     rdx, [rsp+6C0h+me.hModule]; lpBaseAddress
0x1800628e1  mov     rcx, rdi; hProcess
0x1800628e4  call    _anonymous_namespace___GetTimestampFromProcessModule
0x1800628e9  test    eax, eax
0x1800628eb  jns     loc_1800629A7
0x1800628f1  mov     r9d, 104h; nSize
0x1800628f7  lea     r8, [rbp+5C0h+Filename]; lpFilename
0x1800628fe  mov     rdx, [rsp+6C0h+me.hModule]; hModule
0x180062903  mov     rcx, rdi; hProcess
0x180062906  call    cs:__imp_K32GetModuleFileNameExW
0x18006290c  test    eax, eax
0x18006290e  jnz     short loc_180062917
0x180062910  mov     edx, 97h
0x180062915  jmp     short loc_1800628B5
0x180062917  xor     edx, edx; hFile
0x180062919  lea     r8d, [rdx+2]; dwFlags
0x18006291d  lea     rcx, [rbp+5C0h+Filename]; lpLibFileName
0x180062924  call    cs:__imp_LoadLibraryExW
0x18006292a  mov     rbx, rax
0x18006292d  mov     [rsp+6C0h+var_698], rax
0x180062932  test    rax, rax
0x180062935  jnz     short loc_180062960
0x180062937  mov     rcx, [rbp+5C8h]; this
0x18006293e  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x180062945  mov     edx, 9Ah; void *
0x18006294a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006294f  mov     ebx, eax
0x180062951  lea     rcx, [rsp+6C0h+var_698]
0x180062956  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18006295b  jmp     loc_1800629E3
0x180062960  and     rbx, 0FFFFFFFFFFFFFFFCh
0x180062964  call    cs:__imp_GetCurrentProcess
0x18006296a  mov     rcx, rax; hProcess
0x18006296d  lea     r8, [rsp+6C0h+var_6A0]
0x180062972  mov     rdx, rbx; lpBaseAddress
0x180062975  call    _anonymous_namespace___GetTimestampFromProcessModule
0x18006297a  mov     ebx, eax
0x18006297c  test    eax, eax
0x18006297e  jns     short loc_18006299D
0x180062980  mov     rcx, [rbp+5C8h]; this
0x180062987  mov     r9d, eax; char *
0x18006298a  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x180062991  mov     edx, 9Eh; void *
0x180062996  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006299b  jmp     short loc_180062951
0x18006299d  lea     rcx, [rsp+6C0h+var_698]
0x1800629a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800629a7  mov     rdx, rsi; unsigned __int64
0x1800629aa  mov     r9d, [rsp+6C0h+var_6A0]
0x1800629af  lea     r8, a08x; "%08x"
0x1800629b6  mov     rcx, r14; unsigned __int16 *
0x1800629b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800629be  mov     ebx, eax
0x1800629c0  test    eax, eax
0x1800629c2  jns     short loc_1800629E1
0x1800629c4  mov     rcx, [rbp+5C8h]; this
0x1800629cb  mov     r9d, eax; char *
0x1800629ce  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x1800629d5  mov     edx, 0A1h; void *
0x1800629da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800629df  jmp     short loc_1800629E3
0x1800629e1  xor     ebx, ebx
0x1800629e3  lea     rcx, [rsp+6C0h+var_690]
0x1800629e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800629ed  mov     eax, ebx
0x1800629ef  mov     rcx, [rbp+5C0h+var_30]
0x1800629f6  xor     rcx, rsp; StackCookie
0x1800629f9  call    __security_check_cookie
0x1800629fe  add     rsp, 6A0h
0x180062a05  pop     r14
0x180062a07  pop     rdi
0x180062a08  pop     rsi
0x180062a09  pop     rbx
0x180062a0a  pop     rbp
0x180062a0b  retn
```
