# _GetCensoredAppIdForWindow(HWND__ *)

- ea: `0x140036230`
- end: `0x1400363bc`
- name: `?_GetCensoredAppIdForWindow@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHWND__@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(unsigned __int16 **, HWND hWnd)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140085794`
- `0x140122be4`
- `0x140123020`

## callees

- `0x140036230`
- `0x1400363c4`
- `0x140036508`
- `0x140065b60`
- `0x1400811ac`
- `0x14008194c`
- `0x1400a89f4`
- `0x14012d330`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1400362b5`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1400362b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140036366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140036366`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003633f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003633f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400362d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400363a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400362d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400363a7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140036374`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140036374`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1400362e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1400362e8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x14003632e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x14003632e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 **__fastcall _GetCensoredAppIdForWindow(
        unsigned __int16 **a1,
        CallerIdentity *hWnd,
        unsigned __int16 **a3)
{
  void *v5; // rbx
  const WCHAR *FileNameW; // rbx
  const unsigned __int16 *v7; // rcx
  unsigned __int16 **cotaskmem_string_nothrow; // rax
  unsigned __int16 *v10; // rcx
  char *v11; // rbx
  unsigned __int16 **v12; // r8
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp+30h] BYREF
  LPCWSTR lpStringSource; // [rsp+78h] [rbp+38h] BYREF

  pv = a1;
  *a1 = 0;
  lpStringSource = 0;
  if ( (int)CallerIdentity::GetImmersiveAppIdFromWindow(hWnd, (HWND)&lpStringSource, a3) < 0 )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId((HWND)hWnd, &dwProcessId);
    v11 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpStringSource,
        0);
      CallerIdentity::GetProcessAppIdWithAppResolverFallback(v11, &lpStringSource, v12);
      CloseHandle(v11);
    }
  }
  v5 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&dwProcessId);
    CoTaskMemFree(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&dwProcessId);
  }
  FileNameW = lpStringSource;
  *a1 = 0;
  if ( FileNameW )
  {
    if ( FindStringOrdinal(0x100000u, FileNameW, -1, L"Microsoft.Edge.", 15, 0) < 0 )
    {
      if ( !PathIsFileSpecW(FileNameW) )
        FileNameW = PathFindFileNameW(FileNameW);
      cotaskmem_string_nothrow = (unsigned __int16 **)wil::make_cotaskmem_string_nothrow(
                                                        (wil *)&pv,
                                                        FileNameW,
                                                        0xFFFFFFFFFFFFFFFFuLL);
      v10 = *cotaskmem_string_nothrow;
      *cotaskmem_string_nothrow = 0;
      *a1 = v10;
      if ( pv )
        CoTaskMemFree(pv);
    }
    else
    {
      LoggingUtil::AppIdCensorUtility::CensorWebAppId(v7, FileNameW, a1);
    }
  }
  if ( lpStringSource )
    CoTaskMemFree((LPVOID)lpStringSource);
  return a1;
}

```

## disassembly

```asm
0x140036230  mov     [rsp-18h+pv], rcx
0x140036235  push    rbp
0x140036236  push    rbx
0x140036237  push    rdi
0x140036238  mov     rbp, rsp
0x14003623b  sub     rsp, 40h
0x14003623f  mov     rbx, rdx
0x140036242  mov     rdi, rcx
0x140036245  mov     [rbp+var_10], 0
0x14003624c  mov     qword ptr [rcx], 0
0x140036253  mov     [rbp+var_10], 1
0x14003625a  mov     [rbp+lpStringSource], 0
0x140036262  lea     rdx, [rbp+lpStringSource]; HWND
0x140036266  mov     rcx, rbx; this
0x140036269  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x14003626e  test    eax, eax
0x140036270  js      loc_140036320
0x140036276  mov     rbx, [rdi]
0x140036279  test    rbx, rbx
0x14003627c  jnz     loc_14003639B
0x140036282  mov     rbx, [rbp+lpStringSource]
0x140036286  mov     qword ptr [rdi], 0
0x14003628d  test    rbx, rbx
0x140036290  jz      short loc_1400362CB
0x140036292  mov     [rsp+40h+bIgnoreCase], 0; bIgnoreCase
0x14003629a  mov     [rsp+40h+cchValue], 0Fh; cchValue
0x1400362a2  lea     r9, StringValue; "Microsoft.Edge."
0x1400362a9  or      r8d, 0FFFFFFFFh; cchSource
0x1400362ad  mov     rdx, rbx; lpStringSource
0x1400362b0  mov     ecx, 100000h; dwFindStringOrdinalFlags
0x1400362b5  call    cs:__imp_FindStringOrdinal
0x1400362bb  test    eax, eax
0x1400362bd  js      short loc_1400362E5
0x1400362bf  mov     r8, rdi; unsigned __int16 **
0x1400362c2  mov     rdx, rbx; unsigned __int16 *
0x1400362c5  call    ?CensorWebAppId@AppIdCensorUtility@LoggingUtil@@CAXPEBG0PEAPEAG@Z; LoggingUtil::AppIdCensorUtility::CensorWebAppId(ushort const *,ushort const *,ushort * *)
0x1400362ca  nop
0x1400362cb  mov     rcx, [rbp+lpStringSource]; pv
0x1400362cf  test    rcx, rcx
0x1400362d2  jz      short loc_1400362DA
0x1400362d4  call    cs:__imp_CoTaskMemFree
0x1400362da  mov     rax, rdi
0x1400362dd  add     rsp, 40h
0x1400362e1  pop     rdi
0x1400362e2  pop     rbx
0x1400362e3  pop     rbp
0x1400362e4  retn
0x1400362e5  mov     rcx, rbx; pszPath
0x1400362e8  call    cs:__imp_PathIsFileSpecW
0x1400362ee  test    eax, eax
0x1400362f0  jz      short loc_140036371
0x1400362f2  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1400362f6  mov     rdx, rbx; unsigned __int16 *
0x1400362f9  lea     rcx, [rbp+pv]; this
0x1400362fd  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x140036302  mov     rcx, [rax]
0x140036305  mov     qword ptr [rax], 0
0x14003630c  mov     [rdi], rcx
0x14003630f  mov     rcx, [rbp+pv]; pv
0x140036313  test    rcx, rcx
0x140036316  jz      short loc_1400362CB
0x140036318  call    cs:__imp_CoTaskMemFree
0x14003631e  jmp     short loc_1400362CB
0x140036320  mov     [rbp+dwProcessId], 0
0x140036327  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x14003632b  mov     rcx, rbx; hWnd
0x14003632e  call    cs:__imp_GetWindowThreadProcessId
0x140036334  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x140036338  xor     edx, edx; bInheritHandle
0x14003633a  mov     ecx, 1000h; dwDesiredAccess
0x14003633f  call    cs:__imp_OpenProcess
0x140036345  mov     rbx, rax
0x140036348  mov     [rbp+var_8], rax
0x14003634c  dec     rax
0x14003634f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140036353  jbe     short loc_140036382
0x140036355  lea     rax, [rbx-1]
0x140036359  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003635d  ja      loc_140036276
0x140036363  mov     rcx, rbx; hObject
0x140036366  call    cs:__imp_CloseHandle
0x14003636c  jmp     loc_140036276
0x140036371  mov     rcx, rbx; pszPath
0x140036374  call    cs:__imp_PathFindFileNameW
0x14003637a  mov     rbx, rax
0x14003637d  jmp     loc_1400362F2
0x140036382  xor     edx, edx
0x140036384  lea     rcx, [rbp+lpStringSource]
0x140036388  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14003638d  lea     rdx, [rbp+lpStringSource]; void *
0x140036391  mov     rcx, rbx; Process
0x140036394  call    ?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)
0x140036399  jmp     short loc_140036355
0x14003639b  lea     rcx, [rbp+dwProcessId]; this
0x14003639f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400363a4  mov     rcx, rbx; pv
0x1400363a7  call    cs:__imp_CoTaskMemFree
0x1400363ad  lea     rcx, [rbp+dwProcessId]; this
0x1400363b1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400363b6  jmp     loc_140036282
```
