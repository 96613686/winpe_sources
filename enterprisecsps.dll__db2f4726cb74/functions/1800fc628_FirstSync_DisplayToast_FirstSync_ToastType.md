# FirstSync::DisplayToast(FirstSync::ToastType)

- ea: `0x1800fc628`
- end: `0x1800fc8b3`
- name: `?DisplayToast@FirstSync@@YAJW4ToastType@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fb0a4`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x180025a78`
- `0x18005bd10`
- `0x180062e30`
- `0x1800fc628`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc6bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc6e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc711`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc74e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc776`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc79e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc6bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc6e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc711`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc74e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc776`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800fc79e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800fc648`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800fc648`
- `DMCmnUtils!DmRaiseToastNotification` at `0x1800fc869`
- `DMCmnUtils!DmRaiseToastNotification` at `0x1800fc869`

## string_xrefs

- `0x1800fc641`: `DMAppsRes.dll`
- `0x1800fc84d`: `protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FirstSync::DisplayToast(int a1)
{
  HMODULE Library; // rax
  const char *v3; // r9
  HINSTANCE v4; // rbx
  __int64 v5; // rdx
  int v6; // edi
  unsigned int LastError; // ebx
  int StringW; // edi
  int v9; // esi
  const unsigned __int16 *v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-20h]
  const unsigned __int16 *v16; // [rsp+30h] [rbp-10h] BYREF
  HMODULE v17; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp+28h] BYREF
  __int64 Buffer; // [rsp+70h] [rbp+30h] BYREF
  __int64 v21; // [rsp+78h] [rbp+38h] BYREF

  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v4 = Library;
  v17 = Library;
  if ( !Library )
  {
    v5 = 892;
LABEL_13:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
                  v3);
    goto LABEL_29;
  }
  Buffer = 0;
  v21 = 0;
  if ( a1 )
  {
    v6 = a1 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        LastError = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
          (const char *)0x80070057LL,
          v15);
        goto LABEL_29;
      }
      StringW = LoadStringW(Library, 0x65F8u, (LPWSTR)&Buffer, 0);
      if ( !StringW )
      {
        v5 = 920;
        goto LABEL_13;
      }
      v9 = LoadStringW(v4, 0x65F7u, (LPWSTR)&v21, 0);
      if ( !v9 )
      {
        v5 = 923;
        goto LABEL_13;
      }
    }
    else
    {
      StringW = LoadStringW(Library, 0x65F1u, (LPWSTR)&Buffer, 0);
      if ( !StringW )
      {
        v5 = 904;
        goto LABEL_13;
      }
      v9 = LoadStringW(v4, 0x65F0u, (LPWSTR)&v21, 0);
      if ( !v9 )
      {
        v5 = 907;
        goto LABEL_13;
      }
    }
  }
  else
  {
    StringW = LoadStringW(Library, 0x65F2u, (LPWSTR)&Buffer, 0);
    if ( !StringW )
    {
      v5 = 912;
      goto LABEL_13;
    }
    v9 = LoadStringW(v4, 0x65F6u, (LPWSTR)&v21, 0);
    if ( !v9 )
    {
      v5 = 915;
      goto LABEL_13;
    }
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v19,
    Buffer,
    StringW);
  v10 = v19;
  if ( v19 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v16,
      v21,
      v9);
    if ( v16 )
    {
      v13 = DmRaiseToastNotification(
              L"Windows.SystemToast.DeviceManagement",
              L"FirstSyncStatus",
              L"ms-settings:workplace",
              L"protocol",
              v16,
              v10);
      LastError = v13;
      if ( v13 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
        LastError = 0;
        goto LABEL_29;
      }
      v11 = (unsigned int)v13;
      v12 = 936;
    }
    else
    {
      LastError = -2147024882;
      v11 = 2147942414LL;
      v12 = 934;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)v11,
      v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x8007000ELL,
      v15);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v17);
  return LastError;
}

```

## disassembly

```asm
0x1800fc628  mov     [rsp-18h+arg_0], rbx
0x1800fc62d  push    rbp
0x1800fc62e  push    rsi
0x1800fc62f  push    rdi
0x1800fc630  mov     rbp, rsp
0x1800fc633  sub     rsp, 40h
0x1800fc637  mov     edi, ecx
0x1800fc639  xor     edx, edx; hFile
0x1800fc63b  mov     r8d, 800h; dwFlags
0x1800fc641  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x1800fc648  call    cs:__imp_LoadLibraryExW
0x1800fc64f  nop     dword ptr [rax+rax+00h]
0x1800fc654  mov     rbx, rax
0x1800fc657  mov     [rbp+var_8], rax
0x1800fc65b  test    rax, rax
0x1800fc65e  jnz     short loc_1800FC66A
0x1800fc660  mov     edx, 37Ch
0x1800fc665  jmp     loc_1800FC728
0x1800fc66a  mov     [rbp+Buffer], 0
0x1800fc672  mov     [rbp+arg_18], 0
0x1800fc67a  test    edi, edi
0x1800fc67c  jz      loc_1800FC767
0x1800fc682  sub     edi, 1
0x1800fc685  jz      short loc_1800FC702
0x1800fc687  cmp     edi, 1
0x1800fc68a  jz      short loc_1800FC6AE
0x1800fc68c  mov     rcx, [rbp+18h]; this
0x1800fc690  mov     ebx, 80070057h
0x1800fc695  mov     r9d, ebx; char *
0x1800fc698  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fc69f  mov     edx, 39Fh; void *
0x1800fc6a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc6a9  jmp     loc_1800FC89A
0x1800fc6ae  xor     r9d, r9d; cchBufferMax
0x1800fc6b1  lea     r8, [rbp+Buffer]; lpBuffer
0x1800fc6b5  mov     edx, 65F8h; uID
0x1800fc6ba  mov     rcx, rbx; hInstance
0x1800fc6bd  call    cs:__imp_LoadStringW
0x1800fc6c4  nop     dword ptr [rax+rax+00h]
0x1800fc6c9  mov     edi, eax
0x1800fc6cb  test    eax, eax
0x1800fc6cd  jnz     short loc_1800FC6D6
0x1800fc6cf  mov     edx, 398h
0x1800fc6d4  jmp     short loc_1800FC728
0x1800fc6d6  xor     r9d, r9d; cchBufferMax
0x1800fc6d9  lea     r8, [rbp+arg_18]; lpBuffer
0x1800fc6dd  mov     edx, 65F7h; uID
0x1800fc6e2  mov     rcx, rbx; hInstance
0x1800fc6e5  call    cs:__imp_LoadStringW
0x1800fc6ec  nop     dword ptr [rax+rax+00h]
0x1800fc6f1  mov     esi, eax
0x1800fc6f3  test    eax, eax
0x1800fc6f5  jnz     loc_1800FC7BA
0x1800fc6fb  mov     edx, 39Bh
0x1800fc700  jmp     short loc_1800FC728
0x1800fc702  xor     r9d, r9d; cchBufferMax
0x1800fc705  lea     r8, [rbp+Buffer]; lpBuffer
0x1800fc709  mov     edx, 65F1h; uID
0x1800fc70e  mov     rcx, rbx; hInstance
0x1800fc711  call    cs:__imp_LoadStringW
0x1800fc718  nop     dword ptr [rax+rax+00h]
0x1800fc71d  mov     edi, eax
0x1800fc71f  test    eax, eax
0x1800fc721  jnz     short loc_1800FC73F
0x1800fc723  mov     edx, 388h; void *
0x1800fc728  mov     rcx, [rbp+18h]; this
0x1800fc72c  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fc733  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fc738  mov     ebx, eax
0x1800fc73a  jmp     loc_1800FC89A
0x1800fc73f  xor     r9d, r9d; cchBufferMax
0x1800fc742  lea     r8, [rbp+arg_18]; lpBuffer
0x1800fc746  mov     edx, 65F0h; uID
0x1800fc74b  mov     rcx, rbx; hInstance
0x1800fc74e  call    cs:__imp_LoadStringW
0x1800fc755  nop     dword ptr [rax+rax+00h]
0x1800fc75a  mov     esi, eax
0x1800fc75c  test    eax, eax
0x1800fc75e  jnz     short loc_1800FC7BA
0x1800fc760  mov     edx, 38Bh
0x1800fc765  jmp     short loc_1800FC728
0x1800fc767  xor     r9d, r9d; cchBufferMax
0x1800fc76a  lea     r8, [rbp+Buffer]; lpBuffer
0x1800fc76e  mov     edx, 65F2h; uID
0x1800fc773  mov     rcx, rbx; hInstance
0x1800fc776  call    cs:__imp_LoadStringW
0x1800fc77d  nop     dword ptr [rax+rax+00h]
0x1800fc782  mov     edi, eax
0x1800fc784  test    eax, eax
0x1800fc786  jnz     short loc_1800FC78F
0x1800fc788  mov     edx, 390h
0x1800fc78d  jmp     short loc_1800FC728
0x1800fc78f  xor     r9d, r9d; cchBufferMax
0x1800fc792  lea     r8, [rbp+arg_18]; lpBuffer
0x1800fc796  mov     edx, 65F6h; uID
0x1800fc79b  mov     rcx, rbx; hInstance
0x1800fc79e  call    cs:__imp_LoadStringW
0x1800fc7a5  nop     dword ptr [rax+rax+00h]
0x1800fc7aa  mov     esi, eax
0x1800fc7ac  test    eax, eax
0x1800fc7ae  jnz     short loc_1800FC7BA
0x1800fc7b0  mov     edx, 393h
0x1800fc7b5  jmp     loc_1800FC728
0x1800fc7ba  movsxd  r8, edi
0x1800fc7bd  mov     rdx, [rbp+Buffer]
0x1800fc7c1  lea     rcx, [rbp+arg_8]
0x1800fc7c5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800fc7ca  nop
0x1800fc7cb  mov     rbx, [rbp+arg_8]
0x1800fc7cf  test    rbx, rbx
0x1800fc7d2  jnz     short loc_1800FC800
0x1800fc7d4  mov     rcx, [rbp+18h]; this
0x1800fc7d8  mov     ebx, 8007000Eh
0x1800fc7dd  mov     r9d, ebx; char *
0x1800fc7e0  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fc7e7  mov     edx, 3A3h; void *
0x1800fc7ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc7f1  nop
0x1800fc7f2  lea     rcx, [rbp+arg_8]
0x1800fc7f6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fc7fb  jmp     loc_1800FC89A
0x1800fc800  movsxd  r8, esi
0x1800fc803  mov     rdx, [rbp+arg_18]
0x1800fc807  lea     rcx, [rbp+var_10]
0x1800fc80b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800fc810  nop
0x1800fc811  mov     rax, [rbp+var_10]
0x1800fc815  test    rax, rax
0x1800fc818  jnz     short loc_1800FC843
0x1800fc81a  mov     ebx, 8007000Eh
0x1800fc81f  mov     r9d, ebx; char *
0x1800fc822  mov     edx, 3A6h; void *
0x1800fc827  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fc82e  mov     rcx, [rbp+18h]; this
0x1800fc832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc837  nop
0x1800fc838  lea     rcx, [rbp+var_10]
0x1800fc83c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fc841  jmp     short loc_1800FC7F2
0x1800fc843  mov     [rsp+40h+var_18], rbx
0x1800fc848  mov     [rsp+40h+var_20], rax
0x1800fc84d  lea     r9, aProtocol; "protocol"
0x1800fc854  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x1800fc85b  lea     rdx, aFirstsyncstatu; "FirstSyncStatus"
0x1800fc862  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceManagement"
0x1800fc869  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800fc870  nop     dword ptr [rax+rax+00h]
0x1800fc875  mov     ebx, eax
0x1800fc877  test    eax, eax
0x1800fc879  jns     short loc_1800FC885
0x1800fc87b  mov     r9d, eax
0x1800fc87e  mov     edx, 3A8h
0x1800fc883  jmp     short loc_1800FC827
0x1800fc885  lea     rcx, [rbp+var_10]
0x1800fc889  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fc88e  nop
0x1800fc88f  lea     rcx, [rbp+arg_8]
0x1800fc893  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fc898  xor     ebx, ebx
0x1800fc89a  lea     rcx, [rbp+var_8]
0x1800fc89e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800fc8a3  mov     eax, ebx
0x1800fc8a5  mov     rbx, [rsp+40h+arg_0]
0x1800fc8aa  add     rsp, 40h
0x1800fc8ae  pop     rdi
0x1800fc8af  pop     rsi
0x1800fc8b0  pop     rbp
0x1800fc8b1  retn
```
