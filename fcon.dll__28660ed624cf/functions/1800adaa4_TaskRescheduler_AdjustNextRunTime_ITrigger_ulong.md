# TaskRescheduler::AdjustNextRunTime(ITrigger *,ulong)

- ea: `0x1800adaa4`
- end: `0x1800adbe5`
- name: `?AdjustNextRunTime@TaskRescheduler@@CAXPEAUITrigger@@K@Z`
- size: `321`
- prototype: `void __fastcall(struct ITrigger *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800adf1c`

## callees

- `0x1800109ac`
- `0x180016678`
- `0x1800166f4`
- `0x1800ada74`
- `0x1800adaa4`
- `0x1800ae5b8`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800adae4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800adae4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800adac7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800adac7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800adb06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800adb06`

## string_xrefs

- `0x1800adba6`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adbbe`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adbd3`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adac0`: `dmiso8601utils.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TaskRescheduler::AdjustNextRunTime(struct ITrigger *a1, unsigned int a2)
{
  __int64 v2; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  HMODULE v9; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  v2 = a2;
  Library = LoadLibraryExW(L"dmiso8601utils.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "FileTimeToISO8601String");
    if ( !ProcAddress )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)0x8007007FLL,
        v8);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    SystemTimeAsFileTime = (struct _FILETIME)(SystemTimeAsFileTime.dwLowDateTime
                                            + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)
                                            + 600000000 * v2);
    v12 = 0;
    v6 = ((__int64 (__fastcall *)(struct _FILETIME *, __int64, __int64 *))ProcAddress)(&SystemTimeAsFileTime, 2, &v12);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)(unsigned int)v6,
        v8);
    wil::make_bstr(&v8, v12);
    v7 = ((__int64 (__fastcall *)(struct ITrigger *, __int64))a1->lpVtbl->put_StartBoundary)(a1, v8);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)(unsigned int)v7,
        v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x1800adaa4  mov     [rsp-18h+arg_0], rbx
0x1800adaa9  push    rbp
0x1800adaaa  push    rsi
0x1800adaab  push    rdi
0x1800adaac  mov     rbp, rsp
0x1800adaaf  sub     rsp, 30h
0x1800adab3  mov     esi, edx
0x1800adab5  mov     rdi, rcx
0x1800adab8  xor     edx, edx; hFile
0x1800adaba  mov     r8d, 800h; dwFlags
0x1800adac0  lea     rcx, aDmiso8601utils; "dmiso8601utils.dll"
0x1800adac7  call    cs:__imp_LoadLibraryExW
0x1800adacd  mov     [rbp+var_8], rax
0x1800adad1  test    rax, rax
0x1800adad4  jz      loc_1800ADB89
0x1800adada  lea     rdx, aFiletimetoiso8; "FileTimeToISO8601String"
0x1800adae1  mov     rcx, rax; hModule
0x1800adae4  call    cs:__imp_GetProcAddress
0x1800adaea  mov     rbx, rax
0x1800adaed  mov     rcx, [rbp+18h]; this
0x1800adaf1  test    rax, rax
0x1800adaf4  jz      loc_1800ADBB8
0x1800adafa  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800adb02  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800adb06  call    cs:__imp_GetSystemTimeAsFileTime
0x1800adb0c  imul    rcx, rsi, 23C34600h
0x1800adb13  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800adb16  shl     rax, 20h
0x1800adb1a  add     rcx, rax
0x1800adb1d  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800adb20  add     rcx, rax
0x1800adb23  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800adb27  mov     [rbp+arg_18], 0
0x1800adb2f  lea     r8, [rbp+arg_18]
0x1800adb33  mov     edx, 2
0x1800adb38  lea     rcx, [rbp+SystemTimeAsFileTime]
0x1800adb3c  mov     rax, rbx
0x1800adb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb44  mov     rcx, [rbp+18h]; this
0x1800adb48  test    eax, eax
0x1800adb4a  js      loc_1800ADBD0
0x1800adb50  mov     rdx, [rbp+arg_18]
0x1800adb54  lea     rcx, [rbp+var_10]
0x1800adb58  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800adb5d  nop
0x1800adb5e  mov     rax, [rdi]
0x1800adb61  mov     rdx, [rbp+var_10]
0x1800adb65  mov     rcx, rdi
0x1800adb68  mov     rax, [rax+78h]
0x1800adb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb71  test    eax, eax
0x1800adb73  js      short loc_1800ADB9F
0x1800adb75  lea     rcx, [rbp+var_10]
0x1800adb79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800adb7e  nop
0x1800adb7f  lea     rcx, [rbp+arg_18]
0x1800adb83  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800adb88  nop
0x1800adb89  lea     rcx, [rbp+var_8]
0x1800adb8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800adb92  mov     rbx, [rsp+30h+arg_0]
0x1800adb97  add     rsp, 30h
0x1800adb9b  pop     rdi
0x1800adb9c  pop     rsi
0x1800adb9d  pop     rbp
0x1800adb9e  retn
0x1800adb9f  mov     rcx, [rbp+18h]; this
0x1800adba3  mov     r9d, eax; char *
0x1800adba6  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adbad  mov     edx, 6Ah ; 'j'; void *
0x1800adbb2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adbb8  mov     r9d, 8007007Fh; char *
0x1800adbbe  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adbc5  mov     edx, 5Eh ; '^'; void *
0x1800adbca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adbd0  mov     r9d, eax; char *
0x1800adbd3  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adbda  mov     edx, 67h ; 'g'; void *
0x1800adbdf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
