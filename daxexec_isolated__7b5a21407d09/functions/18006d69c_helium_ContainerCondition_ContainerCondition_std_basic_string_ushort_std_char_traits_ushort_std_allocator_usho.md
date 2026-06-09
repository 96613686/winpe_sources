# helium::ContainerCondition::ContainerCondition(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18006d69c`
- end: `0x18006d9fc`
- name: `??0ContainerCondition@helium@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `864`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180053d40`
- `0x180054ea0`
- `0x1800567d0`
- `0x18005b74c`
- `0x180072bf0`

## callees

- `0x180004f70`
- `0x18000ebdc`
- `0x180010d94`
- `0x180012ddc`
- `0x180012fb8`
- `0x180013510`
- `0x180017aa4`
- `0x180021118`
- `0x18002d56c`
- `0x18006d69c`
- `0x18006da64`
- `0x18006daec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d811`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d8e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d941`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d811`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d8e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d7cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d923`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d7cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d923`
- `ntdll!NtCreateMutant` at `0x18006d897`
- `ntdll!NtCreateMutant` at `0x18006d897`
- `ntdll!NtOpenMutant` at `0x18006d791`
- `ntdll!NtOpenMutant` at `0x18006d791`
- `ntdll!RtlInitUnicodeString` at `0x18006d74e`
- `ntdll!RtlInitUnicodeString` at `0x18006d853`
- `ntdll!RtlInitUnicodeString` at `0x18006d74e`
- `ntdll!RtlInitUnicodeString` at `0x18006d853`

## string_xrefs

- `0x18006d99c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18006d9b1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18006d9db`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall helium::ContainerCondition::ContainerCondition(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // r14
  unsigned int v5; // ebx
  int v6; // ebx
  const WCHAR *v7; // rdx
  void **v8; // rax
  NTSTATUS v9; // eax
  __int64 v10; // rax
  const char *v11; // r9
  int v12; // ebx
  const WCHAR *v13; // rdx
  void **v14; // rax
  NTSTATUS v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  HANDLE hObject; // [rsp+20h] [rbp-89h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-81h] BYREF
  int v23; // [rsp+38h] [rbp-71h]
  HANDLE hMutex; // [rsp+40h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES v25; // [rsp+48h] [rbp-61h] BYREF
  _QWORD *v26; // [rsp+78h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  PCWSTR SourceString[3]; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int64 v29; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v26 = a1;
  v23 = 0;
  *a1 = 0;
  v4 = a1 + 1;
  a1[1] = 0;
  memset(&ObjectAttributes, 0, 32);
  std::wstring::_Construct<1,unsigned short const *>(&ObjectAttributes, L"\\DaxMutex_", 10);
  std::operator+<unsigned short>(SourceString, &ObjectAttributes, a2);
  v5 = 1;
  std::wstring::~wstring(&ObjectAttributes);
  while ( !*v4 )
  {
    hObject = 0;
    v6 = v5 | 2;
    v23 = v6;
    DestinationString = 0;
    v7 = (const WCHAR *)SourceString;
    if ( v29 > 7 )
      v7 = SourceString[0];
    RtlInitUnicodeString(&DestinationString, v7);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
    v9 = NtOpenMutant(v8, 0x100000u, &ObjectAttributes);
    if ( v9 != -1073741772 && v9 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\containercondition.cpp",
        (const char *)(unsigned int)v9,
        (int)hObject);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1,
      &hObject);
    v5 = v6 & 0xFFFFFFFD;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (unsigned __int64)(*a1 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      *(_QWORD *)&DestinationString.Length = 0;
      DestinationString.Buffer = 0;
      v12 = v5 | 4;
      v23 = v12;
      *(_OWORD *)&ObjectAttributes.Length = 0;
      v13 = (const WCHAR *)SourceString;
      if ( v29 > 7 )
        v13 = SourceString[0];
      RtlInitUnicodeString((PUNICODE_STRING)&ObjectAttributes, v13);
      *(_QWORD *)&v25.Length = 48;
      memset(&v25.Attributes, 0, 24);
      v25.RootDirectory = 0;
      v25.ObjectName = (PUNICODE_STRING)&ObjectAttributes;
      v14 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&DestinationString.Buffer);
      v15 = NtCreateMutant(v14, 0x1F0001u, &v25, 1u);
      if ( v15 != -1073741771 )
      {
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x51,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\containercondition.cpp",
            (const char *)(unsigned int)v15,
            (int)hObject);
        if ( !DestinationString.Buffer )
          wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xDD6, v16, v17);
        hObject = DestinationString.Buffer;
        __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
          &DestinationString,
          &hObject);
        if ( hObject && !ReleaseMutex(hObject) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v18);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        a1,
        &DestinationString.Buffer);
      __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
        v4,
        &DestinationString);
      v5 = v12 & 0xFFFFFFFB;
      if ( (unsigned __int64)DestinationString.Buffer - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(DestinationString.Buffer);
      if ( *(_QWORD *)&DestinationString.Length && !ReleaseMutex(*(HANDLE *)&DestinationString.Length) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v19);
    }
    else
    {
      v10 = helium::details::AcquireContainerMutex(&hMutex, *a1, 0xFFFFFFFFLL);
      __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
        v4,
        v10);
      if ( hMutex )
      {
        if ( !ReleaseMutex(hMutex) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v11);
      }
    }
  }
  std::wstring::~wstring(SourceString);
  return a1;
}

```

## disassembly

```asm
0x18006d69c  mov     [rsp-8+arg_10], rbx
0x18006d6a1  push    rbp
0x18006d6a2  push    rsi
0x18006d6a3  push    rdi
0x18006d6a4  push    r14
0x18006d6a6  push    r15
0x18006d6a8  lea     rbp, [rsp-37h]
0x18006d6ad  sub     rsp, 0E0h
0x18006d6b4  mov     rax, cs:__security_cookie
0x18006d6bb  xor     rax, rsp
0x18006d6be  mov     [rbp+57h+var_30], rax
0x18006d6c2  mov     rbx, rdx
0x18006d6c5  mov     rdi, rcx
0x18006d6c8  mov     [rbp+57h+var_88], rcx
0x18006d6cc  xor     r15d, r15d
0x18006d6cf  mov     [rbp+57h+var_C8], r15d
0x18006d6d3  mov     [rcx], r15
0x18006d6d6  lea     r14, [rcx+8]
0x18006d6da  mov     [r14], r15
0x18006d6dd  xorps   xmm0, xmm0
0x18006d6e0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006d6e4  xorps   xmm1, xmm1
0x18006d6e7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18006d6ec  lea     r8d, [r15+0Ah]
0x18006d6f0  lea     rdx, aDaxmutex; "\\DaxMutex_"
0x18006d6f7  lea     rcx, [rbp+57h+ObjectAttributes]
0x18006d6fb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006d700  nop
0x18006d701  mov     r8, rbx
0x18006d704  lea     rdx, [rbp+57h+ObjectAttributes]
0x18006d708  lea     rcx, [rbp+57h+SourceString]
0x18006d70c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18006d711  lea     ebx, [r15+1]
0x18006d715  lea     rcx, [rbp+57h+ObjectAttributes]; void *
0x18006d719  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006d71e  nop
0x18006d71f  cmp     [r14], r15
0x18006d722  jnz     loc_18006D956
0x18006d728  mov     [rsp+100h+hObject], r15; int
0x18006d72d  or      ebx, 2
0x18006d730  mov     [rbp+57h+var_C8], ebx
0x18006d733  xorps   xmm0, xmm0
0x18006d736  movups  xmmword ptr [rsp+100h+DestinationString.Length], xmm0
0x18006d73b  lea     rdx, [rbp+57h+SourceString]
0x18006d73f  cmp     [rbp+57h+var_38], 7
0x18006d744  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x18006d749  lea     rcx, [rsp+100h+DestinationString]; DestinationString
0x18006d74e  call    cs:__imp_RtlInitUnicodeString
0x18006d755  nop     dword ptr [rax+rax+00h]
0x18006d75a  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006d762  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r15
0x18006d766  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18006d76a  lea     rax, [rsp+100h+DestinationString]
0x18006d76f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006d773  xorps   xmm0, xmm0
0x18006d776  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d77b  lea     rcx, [rsp+100h+hObject]
0x18006d780  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18006d785  mov     rcx, rax; MutantHandle
0x18006d788  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006d78c  mov     edx, 100000h; DesiredAccess
0x18006d791  call    cs:__imp_NtOpenMutant
0x18006d798  nop     dword ptr [rax+rax+00h]
0x18006d79d  cmp     eax, 0C0000034h
0x18006d7a2  jz      short loc_18006D7B0
0x18006d7a4  mov     rcx, [rbp+5Fh]; this
0x18006d7a8  test    eax, eax
0x18006d7aa  js      loc_18006D9C6
0x18006d7b0  lea     rdx, [rsp+100h+hObject]
0x18006d7b5  mov     rcx, rdi
0x18006d7b8  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006d7bd  and     ebx, 0FFFFFFFDh
0x18006d7c0  mov     rcx, [rsp+100h+hObject]; hObject
0x18006d7c5  lea     rax, [rcx-1]
0x18006d7c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006d7cd  ja      short loc_18006D7DB
0x18006d7cf  call    cs:__imp_CloseHandle
0x18006d7d6  nop     dword ptr [rax+rax+00h]
0x18006d7db  mov     rdx, [rdi]
0x18006d7de  lea     rax, [rdx-1]
0x18006d7e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006d7e6  ja      short loc_18006D82A
0x18006d7e8  or      r8d, 0FFFFFFFFh
0x18006d7ec  lea     rcx, [rbp+57h+hMutex]
0x18006d7f0  call    ?AcquireContainerMutex@details@helium@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXK@Z
0x18006d7f5  mov     rdx, rax
0x18006d7f8  mov     rcx, r14
0x18006d7fb  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18006d800  mov     rcx, [rbp+57h+hMutex]; hMutex
0x18006d804  test    rcx, rcx
0x18006d807  jz      loc_18006D71F
0x18006d80d  mov     rsi, [rbp+5Fh]
0x18006d811  call    cs:__imp_ReleaseMutex
0x18006d818  nop     dword ptr [rax+rax+00h]
0x18006d81d  test    eax, eax
0x18006d81f  jz      loc_18006D99C
0x18006d825  jmp     loc_18006D71F
0x18006d82a  xorps   xmm0, xmm0
0x18006d82d  movdqu  xmmword ptr [rsp+100h+DestinationString.Length], xmm0
0x18006d833  mov     [rbp+57h+DestinationString.Buffer], r15
0x18006d837  or      ebx, 4
0x18006d83a  mov     [rbp+57h+var_C8], ebx
0x18006d83d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006d841  lea     rdx, [rbp+57h+SourceString]
0x18006d845  cmp     [rbp+57h+var_38], 7
0x18006d84a  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x18006d84f  lea     rcx, [rbp+57h+ObjectAttributes]; DestinationString
0x18006d853  call    cs:__imp_RtlInitUnicodeString
0x18006d85a  nop     dword ptr [rax+rax+00h]
0x18006d85f  mov     qword ptr [rbp+57h+var_B8.Length], 30h ; '0'
0x18006d867  mov     qword ptr [rbp+57h+var_B8.Attributes], r15
0x18006d86b  mov     [rbp+57h+var_B8.RootDirectory], r15
0x18006d86f  lea     rax, [rbp+57h+ObjectAttributes]
0x18006d873  mov     [rbp+57h+var_B8.ObjectName], rax
0x18006d877  xorps   xmm0, xmm0
0x18006d87a  movdqu  xmmword ptr [rbp+57h+var_B8.SecurityDescriptor], xmm0
0x18006d87f  lea     rcx, [rbp+57h+DestinationString.Buffer]
0x18006d883  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18006d888  mov     rcx, rax; MutantHandle
0x18006d88b  mov     r9b, 1; InitialOwner
0x18006d88e  lea     r8, [rbp+57h+var_B8]; ObjectAttributes
0x18006d892  mov     edx, 1F0001h; DesiredAccess
0x18006d897  call    cs:__imp_NtCreateMutant
0x18006d89e  nop     dword ptr [rax+rax+00h]
0x18006d8a3  cmp     eax, 0C0000035h
0x18006d8a8  jz      short loc_18006D8F9
0x18006d8aa  mov     rcx, [rbp+5Fh]; this
0x18006d8ae  test    eax, eax
0x18006d8b0  js      loc_18006D987
0x18006d8b6  mov     rax, [rbp+57h+DestinationString.Buffer]
0x18006d8ba  test    rax, rax
0x18006d8bd  jz      loc_18006D9ED
0x18006d8c3  mov     [rsp+100h+hObject], rax
0x18006d8c8  lea     rdx, [rsp+100h+hObject]
0x18006d8cd  lea     rcx, [rsp+100h+DestinationString]
0x18006d8d2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18006d8d7  mov     rcx, [rsp+100h+hObject]; hMutex
0x18006d8dc  test    rcx, rcx
0x18006d8df  jz      short loc_18006D8F9
0x18006d8e1  call    cs:__imp_ReleaseMutex
0x18006d8e8  nop     dword ptr [rax+rax+00h]
0x18006d8ed  mov     rcx, [rbp+5Fh]; this
0x18006d8f1  test    eax, eax
0x18006d8f3  jz      loc_18006D9DB
0x18006d8f9  lea     rdx, [rbp+57h+DestinationString.Buffer]
0x18006d8fd  mov     rcx, rdi
0x18006d900  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006d905  lea     rdx, [rsp+100h+DestinationString]
0x18006d90a  mov     rcx, r14
0x18006d90d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18006d912  and     ebx, 0FFFFFFFBh
0x18006d915  mov     rcx, [rbp+57h+DestinationString.Buffer]; hObject
0x18006d919  lea     rax, [rcx-1]
0x18006d91d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006d921  ja      short loc_18006D92F
0x18006d923  call    cs:__imp_CloseHandle
0x18006d92a  nop     dword ptr [rax+rax+00h]
0x18006d92f  mov     rcx, qword ptr [rsp+100h+DestinationString.Length]; hMutex
0x18006d934  test    rcx, rcx
0x18006d937  jz      loc_18006D71F
0x18006d93d  mov     rsi, [rbp+5Fh]
0x18006d941  call    cs:__imp_ReleaseMutex
0x18006d948  nop     dword ptr [rax+rax+00h]
0x18006d94d  test    eax, eax
0x18006d94f  jz      short loc_18006D9B1
0x18006d951  jmp     loc_18006D71F
0x18006d956  lea     rcx, [rbp+57h+SourceString]; void *
0x18006d95a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006d95f  nop
0x18006d960  mov     rax, rdi
0x18006d963  mov     rcx, [rbp+57h+var_30]
0x18006d967  xor     rcx, rsp; StackCookie
0x18006d96a  call    __security_check_cookie
0x18006d96f  mov     rbx, [rsp+100h+arg_10]
0x18006d977  add     rsp, 0E0h
0x18006d97e  pop     r15
0x18006d980  pop     r14
0x18006d982  pop     rdi
0x18006d983  pop     rsi
0x18006d984  pop     rbp
0x18006d985  retn
0x18006d987  mov     r9d, eax; char *
0x18006d98a  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006d991  mov     edx, 51h ; 'Q'; void *
0x18006d996  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18006d99c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006d9a3  mov     edx, 0A15h; void *
0x18006d9a8  mov     rcx, rsi; this
0x18006d9ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006d9b1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006d9b8  mov     edx, 0A15h; void *
0x18006d9bd  mov     rcx, rsi; this
0x18006d9c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006d9c6  mov     r9d, eax; char *
0x18006d9c9  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006d9d0  mov     edx, 2Bh ; '+'; void *
0x18006d9d5  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18006d9db  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006d9e2  mov     edx, 0A15h; void *
0x18006d9e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006d9ed  mov     rcx, [rbp+5Fh]; this
0x18006d9f1  mov     edx, 0DD6h; void *
0x18006d9f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
