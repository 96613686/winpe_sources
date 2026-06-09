# EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *)

- ea: `0x180076674`
- end: `0x18007675d`
- name: `?ReadSkuUpdateManagementGroup@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `233`
- prototype: `static int(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800752d8`

## callees

- `0x180017988`
- `0x1800179ac`
- `0x18006f800`
- `0x180076674`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800766e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800766e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800766c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800766c0`

## string_xrefs

- `0x1800766b9`: `ext-ms-win-security-slc-l1-1-0`
- `0x18007670b`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *a1)
{
  unsigned int LastError; // ebx
  HMODULE Library; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v12; // [rsp+30h] [rbp+8h] BYREF
  HMODULE v13; // [rsp+38h] [rbp+10h] BYREF

  v12 = 0;
  if ( a1 )
  {
    Library = LoadLibraryExW(L"ext-ms-win-security-slc-l1-1-0", 0, 0x800u);
    v13 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        v7 = ((__int64 (__fastcall *)(const wchar_t *, int *))ProcAddress)(L"UpdatePolicy-UpdateManagementGroup", &v12);
        v8 = v7;
        if ( v7 >= 0 )
        {
          *a1 = v12 == 0;
          LastError = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
            (const char *)(unsigned int)v7,
            v10);
          LastError = v8;
        }
        goto LABEL_11;
      }
      v5 = 190;
    }
    else
    {
      v5 = 186;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                  v4);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v13);
    return LastError;
  }
  LastError = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB7,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)0x80004003LL,
    v10);
  return LastError;
}

```

## disassembly

```asm
0x180076674  mov     [rsp+arg_10], rbx
0x180076679  push    rdi; int
0x18007667a  sub     rsp, 20h
0x18007667e  mov     rbx, rcx
0x180076681  mov     [rsp+28h+arg_0], 0
0x180076689  test    rcx, rcx
0x18007668c  jnz     short loc_1800766B1
0x18007668e  mov     rcx, [rsp+28h]; this
0x180076693  mov     ebx, 80004003h
0x180076698  mov     r9d, ebx; char *
0x18007669b  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800766a2  mov     edx, 0B7h; void *
0x1800766a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800766ac  jmp     loc_180076750
0x1800766b1  xor     edx, edx; hFile
0x1800766b3  mov     r8d, 800h; dwFlags
0x1800766b9  lea     rcx, aExtMsWinSecuri; "ext-ms-win-security-slc-l1-1-0"
0x1800766c0  call    cs:__imp_LoadLibraryExW
0x1800766c6  mov     [rsp+28h+arg_8], rax
0x1800766cb  test    rax, rax
0x1800766ce  jnz     short loc_1800766D7
0x1800766d0  mov     edx, 0BAh
0x1800766d5  jmp     short loc_1800766F1
0x1800766d7  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x1800766de  mov     rcx, rax; hModule
0x1800766e1  call    cs:__imp_GetProcAddress
0x1800766e7  test    rax, rax
0x1800766ea  jnz     short loc_180076706
0x1800766ec  mov     edx, 0BEh; void *
0x1800766f1  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800766f8  mov     rcx, [rsp+28h]; this
0x1800766fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180076702  mov     ebx, eax
0x180076704  jmp     short loc_180076746
0x180076706  lea     rdx, [rsp+28h+arg_0]
0x18007670b  lea     rcx, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x180076712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076717  mov     edi, eax
0x180076719  test    eax, eax
0x18007671b  jns     short loc_18007673A
0x18007671d  mov     rcx, [rsp+28h]; this
0x180076722  mov     r9d, eax; char *
0x180076725  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18007672c  mov     edx, 0BFh; void *
0x180076731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076736  mov     ebx, edi
0x180076738  jmp     short loc_180076746
0x18007673a  cmp     [rsp+28h+arg_0], 0
0x18007673f  setz    al
0x180076742  mov     [rbx], al
0x180076744  xor     ebx, ebx
0x180076746  lea     rcx, [rsp+28h+arg_8]
0x18007674b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180076750  mov     eax, ebx
0x180076752  mov     rbx, [rsp+28h+arg_10]
0x180076757  add     rsp, 20h
0x18007675b  pop     rdi
0x18007675c  retn
```
