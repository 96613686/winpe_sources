# _GetCensoredAppIdForWindow(HWND__ *)

- ea: `0x1400280ac`
- end: `0x140028256`
- name: `?_GetCensoredAppIdForWindow@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHWND__@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned __int16 **, HWND hWnd)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008b754`
- `0x14012e1e8`
- `0x14012e664`

## callees

- `0x140005810`
- `0x140027ba0`
- `0x1400280ac`
- `0x14002825c`
- `0x140086b94`
- `0x140087664`
- `0x1400ae764`
- `0x140138f34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x140028131`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x140028131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400281ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400281ee`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400281c1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400281c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002823b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002823b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x140028173`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x140028173`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140028202`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140028202`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1400281aa`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1400281aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 **__fastcall _GetCensoredAppIdForWindow(
        unsigned __int16 **a1,
        CallerIdentity *hWnd,
        unsigned __int16 **a3)
{
  unsigned __int16 *v5; // rbx
  WCHAR *FileNameW; // rbx
  const unsigned __int16 *v7; // rcx
  char *v9; // rbx
  unsigned __int16 **v10; // r8
  unsigned __int16 *v11; // [rsp+60h] [rbp+20h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp+30h] BYREF
  LPCWSTR lpStringSource; // [rsp+78h] [rbp+38h] BYREF

  v11 = (unsigned __int16 *)a1;
  *a1 = 0;
  lpStringSource = 0;
  if ( (int)CallerIdentity::GetImmersiveAppIdFromWindow(hWnd, (HWND)&lpStringSource, a3) < 0 )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId((HWND)hWnd, &dwProcessId);
    v9 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpStringSource,
        0);
      CallerIdentity::GetProcessAppIdWithAppResolverFallback(v9, &lpStringSource, v10);
      CloseHandle(v9);
    }
  }
  v5 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&dwProcessId);
    CoTaskMemFree(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&dwProcessId);
  }
  FileNameW = (WCHAR *)lpStringSource;
  *a1 = 0;
  if ( FileNameW )
  {
    if ( FindStringOrdinal(0x100000u, FileNameW, -1, L"Microsoft.Edge.", 15, 0) < 0 )
    {
      if ( !PathIsFileSpecW(FileNameW) )
        FileNameW = PathFindFileNameW(FileNameW);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v11,
        FileNameW,
        -1);
      *a1 = v11;
    }
    else
    {
      LoggingUtil::AppIdCensorUtility::CensorWebAppId(v7, FileNameW, a1);
    }
    FileNameW = (WCHAR *)lpStringSource;
  }
  if ( FileNameW )
    CoTaskMemFree(FileNameW);
  return a1;
}

```

## disassembly

```asm
0x1400280ac  mov     [rsp-18h+arg_0], rcx
0x1400280b1  push    rbp
0x1400280b2  push    rbx
0x1400280b3  push    rdi
0x1400280b4  mov     rbp, rsp
0x1400280b7  sub     rsp, 40h
0x1400280bb  mov     rbx, rdx
0x1400280be  mov     rdi, rcx
0x1400280c1  mov     [rbp+var_10], 0
0x1400280c8  mov     qword ptr [rcx], 0
0x1400280cf  mov     [rbp+var_10], 1
0x1400280d6  mov     [rbp+lpStringSource], 0
0x1400280de  lea     rdx, [rbp+lpStringSource]; HWND
0x1400280e2  mov     rcx, rbx; this
0x1400280e5  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x1400280ea  test    eax, eax
0x1400280ec  js      loc_14002819C
0x1400280f2  mov     rbx, [rdi]
0x1400280f5  test    rbx, rbx
0x1400280f8  jnz     loc_14002822F
0x1400280fe  mov     rbx, [rbp+lpStringSource]
0x140028102  mov     qword ptr [rdi], 0
0x140028109  test    rbx, rbx
0x14002810c  jz      short loc_140028150
0x14002810e  mov     [rsp+40h+bIgnoreCase], 0; bIgnoreCase
0x140028116  mov     [rsp+40h+cchValue], 0Fh; cchValue
0x14002811e  lea     r9, StringValue; "Microsoft.Edge."
0x140028125  or      r8d, 0FFFFFFFFh; cchSource
0x140028129  mov     rdx, rbx; lpStringSource
0x14002812c  mov     ecx, 100000h; dwFindStringOrdinalFlags
0x140028131  call    cs:__imp_FindStringOrdinal
0x140028138  nop     dword ptr [rax+rax+00h]
0x14002813d  test    eax, eax
0x14002813f  js      short loc_140028170
0x140028141  mov     r8, rdi; unsigned __int16 **
0x140028144  mov     rdx, rbx; unsigned __int16 *
0x140028147  call    ?CensorWebAppId@AppIdCensorUtility@LoggingUtil@@CAXPEBG0PEAPEAG@Z; LoggingUtil::AppIdCensorUtility::CensorWebAppId(ushort const *,ushort const *,ushort * *)
0x14002814c  mov     rbx, [rbp+lpStringSource]
0x140028150  test    rbx, rbx
0x140028153  jz      short loc_140028164
0x140028155  mov     rcx, rbx; pv
0x140028158  call    cs:__imp_CoTaskMemFree
0x14002815f  nop     dword ptr [rax+rax+00h]
0x140028164  mov     rax, rdi
0x140028167  add     rsp, 40h
0x14002816b  pop     rdi
0x14002816c  pop     rbx
0x14002816d  pop     rbp
0x14002816e  retn
0x140028170  mov     rcx, rbx; pszPath
0x140028173  call    cs:__imp_PathIsFileSpecW
0x14002817a  nop     dword ptr [rax+rax+00h]
0x14002817f  test    eax, eax
0x140028181  jz      short loc_1400281FF
0x140028183  or      r8, 0FFFFFFFFFFFFFFFFh
0x140028187  mov     rdx, rbx
0x14002818a  lea     rcx, [rbp+arg_0]
0x14002818e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140028193  mov     rax, [rbp+arg_0]
0x140028197  mov     [rdi], rax
0x14002819a  jmp     short loc_14002814C
0x14002819c  mov     [rbp+dwProcessId], 0
0x1400281a3  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1400281a7  mov     rcx, rbx; hWnd
0x1400281aa  call    cs:__imp_GetWindowThreadProcessId
0x1400281b1  nop     dword ptr [rax+rax+00h]
0x1400281b6  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1400281ba  xor     edx, edx; bInheritHandle
0x1400281bc  mov     ecx, 1000h; dwDesiredAccess
0x1400281c1  call    cs:__imp_OpenProcess
0x1400281c8  nop     dword ptr [rax+rax+00h]
0x1400281cd  mov     rbx, rax
0x1400281d0  mov     [rbp+var_8], rax
0x1400281d4  dec     rax
0x1400281d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400281db  jbe     short loc_140028216
0x1400281dd  lea     rax, [rbx-1]
0x1400281e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400281e5  ja      loc_1400280F2
0x1400281eb  mov     rcx, rbx; hObject
0x1400281ee  call    cs:__imp_CloseHandle
0x1400281f5  nop     dword ptr [rax+rax+00h]
0x1400281fa  jmp     loc_1400280F2
0x1400281ff  mov     rcx, rbx; pszPath
0x140028202  call    cs:__imp_PathFindFileNameW
0x140028209  nop     dword ptr [rax+rax+00h]
0x14002820e  mov     rbx, rax
0x140028211  jmp     loc_140028183
0x140028216  xor     edx, edx
0x140028218  lea     rcx, [rbp+lpStringSource]
0x14002821c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140028221  lea     rdx, [rbp+lpStringSource]; void *
0x140028225  mov     rcx, rbx; Process
0x140028228  call    ?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)
0x14002822d  jmp     short loc_1400281DD
0x14002822f  lea     rcx, [rbp+dwProcessId]; this
0x140028233  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140028238  mov     rcx, rbx; pv
0x14002823b  call    cs:__imp_CoTaskMemFree
0x140028242  nop     dword ptr [rax+rax+00h]
0x140028247  lea     rcx, [rbp+dwProcessId]; this
0x14002824b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140028250  jmp     loc_1400280FE
```
