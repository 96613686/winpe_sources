# helium::ContainerCondition::ContainerCondition(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18006be00`
- end: `0x18006c180`
- name: `??0ContainerCondition@helium@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `896`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1800521b8`
- `0x180053390`
- `0x180054ce0`
- `0x180059b7c`
- `0x180071290`

## callees

- `0x1800053a0`
- `0x18000cf44`
- `0x18000f1c8`
- `0x18000f368`
- `0x180011300`
- `0x180011820`
- `0x180013188`
- `0x180015ec8`
- `0x180020338`
- `0x18002ca40`
- `0x18006be00`
- `0x18006c1e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006bfb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006c0d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006bfb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006c0d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bf65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bf65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c0b9`
- `ntdll!NtCreateMutant` at `0x18006c03a`
- `ntdll!NtCreateMutant` at `0x18006c03a`
- `ntdll!NtOpenMutant` at `0x18006bf29`
- `ntdll!NtOpenMutant` at `0x18006bf29`
- `ntdll!RtlInitUnicodeString` at `0x18006bee8`
- `ntdll!RtlInitUnicodeString` at `0x18006bff5`
- `ntdll!RtlInitUnicodeString` at `0x18006bee8`
- `ntdll!RtlInitUnicodeString` at `0x18006bff5`

## string_xrefs

- `0x18006c132`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18006c147`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HANDLE *__fastcall helium::ContainerCondition::ContainerCondition(HANDLE *a1)
{
  HANDLE *v2; // rsi
  __int64 v3; // rax
  unsigned int v4; // edi
  int v5; // edi
  const WCHAR *v6; // rdx
  void **v7; // rax
  NTSTATUS v8; // eax
  HANDLE *v9; // r14
  const char *v10; // r9
  int v11; // edi
  const WCHAR *v12; // rdx
  void **v13; // rax
  NTSTATUS v14; // eax
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v17; // rcx
  const char *v18; // r9
  HANDLE v20[2]; // [rsp+20h] [rbp-89h] BYREF
  int v21; // [rsp+30h] [rbp-79h]
  HANDLE hObject; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  HANDLE hMutex[2]; // [rsp+80h] [rbp-29h] BYREF
  PCWSTR SourceString[2]; // [rsp+90h] [rbp-19h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-9h]
  _OWORD Src[2]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  hMutex[1] = a1;
  v21 = 0;
  *a1 = 0;
  v2 = a1 + 1;
  a1[1] = 0;
  memset(Src, 0, sizeof(Src));
  std::wstring::_Construct<1,unsigned short const *>(Src, L"\\DaxMutex_", 10);
  v3 = std::wstring::append(Src);
  *(_OWORD *)SourceString = 0;
  v27 = 0u;
  *(_OWORD *)SourceString = *(_OWORD *)v3;
  v27 = *(_OWORD *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 7;
  *(_WORD *)v3 = 0;
  v4 = 3;
  std::wstring::~wstring(Src);
  while ( !*v2 )
  {
    hObject = 0;
    v5 = v4 | 4;
    v21 = v5;
    DestinationString = 0;
    v6 = (const WCHAR *)SourceString;
    if ( *((_QWORD *)&v27 + 1) > 7u )
      v6 = SourceString[0];
    RtlInitUnicodeString(&DestinationString, v6);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    v7 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
    v8 = NtOpenMutant(v7, 0x100000u, &ObjectAttributes);
    if ( v8 != -1073741772 && v8 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\containercondition.cpp",
        (const char *)(unsigned int)v8,
        (int)v20[0]);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1,
      &hObject);
    v4 = v5 & 0xFFFFFFFB;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (char *)*a1 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v20[0] = 0;
      v20[1] = 0;
      v11 = v4 | 8;
      v21 = v11;
      DestinationString = 0;
      v12 = (const WCHAR *)SourceString;
      if ( *((_QWORD *)&v27 + 1) > 7u )
        v12 = SourceString[0];
      RtlInitUnicodeString(&DestinationString, v12);
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.Attributes, 0, 24);
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      v13 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&v20[1]);
      v14 = NtCreateMutant(v13, 0x1F0001u, &ObjectAttributes, 1u);
      if ( v14 != -1073741771 )
      {
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x51,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\containercondition.cpp",
            (const char *)(unsigned int)v14,
            (int)v20[0]);
        if ( !v20[1] )
          wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xC0C, v15, v16);
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(v20);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        a1,
        &v20[1]);
      if ( v2 == v20 )
      {
        v17 = v20[0];
      }
      else
      {
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(v2);
        v17 = 0;
        v20[0] = 0;
      }
      v4 = v11 & 0xFFFFFFF7;
      if ( (unsigned __int64)v20[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v20[1]);
        v17 = v20[0];
      }
      if ( v17 && !ReleaseMutex(v17) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9E7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v18);
    }
    else
    {
      v9 = (HANDLE *)helium::details::AcquireContainerMutex(hMutex, *a1, 0xFFFFFFFFLL);
      if ( v2 != v9 )
      {
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(v2);
        *v9 = 0;
      }
      if ( hMutex[0] )
      {
        if ( !ReleaseMutex(hMutex[0]) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9E7,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v10);
      }
    }
  }
  std::wstring::~wstring(SourceString);
  return a1;
}

```

## disassembly

```asm
0x18006be00  mov     [rsp-8+arg_10], rbx
0x18006be05  push    rbp
0x18006be06  push    rsi
0x18006be07  push    rdi
0x18006be08  push    r14
0x18006be0a  push    r15
0x18006be0c  lea     rbp, [rsp-37h]
0x18006be11  sub     rsp, 0E0h
0x18006be18  mov     rax, cs:__security_cookie
0x18006be1f  xor     rax, rsp
0x18006be22  mov     [rbp+57h+var_30], rax
0x18006be26  mov     rdi, rdx
0x18006be29  mov     rbx, rcx
0x18006be2c  mov     [rbp+57h+var_78], rcx
0x18006be30  xor     r15d, r15d
0x18006be33  mov     [rbp+57h+var_D0], r15d
0x18006be37  mov     [rcx], r15
0x18006be3a  lea     rsi, [rcx+8]
0x18006be3e  mov     [rsi], r15
0x18006be41  xorps   xmm0, xmm0
0x18006be44  movups  [rbp+57h+Src], xmm0
0x18006be48  xorps   xmm1, xmm1
0x18006be4b  movdqu  [rbp+57h+var_40], xmm1
0x18006be50  lea     r8d, [r15+0Ah]
0x18006be54  lea     rdx, aDaxmutex; "\\DaxMutex_"
0x18006be5b  lea     rcx, [rbp+57h+Src]
0x18006be5f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006be64  nop
0x18006be65  mov     r8, [rdi+10h]
0x18006be69  cmp     qword ptr [rdi+18h], 7
0x18006be6e  jbe     short loc_18006BE73
0x18006be70  mov     rdi, [rdi]
0x18006be73  mov     rdx, rdi
0x18006be76  lea     rcx, [rbp+57h+Src]; Src
0x18006be7a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18006be7f  xorps   xmm0, xmm0
0x18006be82  movups  xmmword ptr [rbp+57h+SourceString], xmm0
0x18006be86  mov     qword ptr [rbp+57h+var_60], r15
0x18006be8a  mov     qword ptr [rbp+57h+var_60+8], r15
0x18006be8e  movups  xmm0, xmmword ptr [rax]
0x18006be91  movups  xmmword ptr [rbp+57h+SourceString], xmm0
0x18006be95  movups  xmm1, xmmword ptr [rax+10h]
0x18006be99  movups  [rbp+57h+var_60], xmm1
0x18006be9d  mov     [rax+10h], r15
0x18006bea1  mov     qword ptr [rax+18h], 7
0x18006bea9  mov     [rax], r15w
0x18006bead  mov     edi, 3
0x18006beb2  lea     rcx, [rbp+57h+Src]; void *
0x18006beb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006bebb  nop
0x18006bebc  cmp     [rsi], r15
0x18006bebf  jnz     loc_18006C0EC
0x18006bec5  mov     [rbp+57h+hObject], r15
0x18006bec9  or      edi, 4
0x18006becc  mov     [rbp+57h+var_D0], edi
0x18006becf  xorps   xmm0, xmm0
0x18006bed2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006bed6  lea     rdx, [rbp+57h+SourceString]
0x18006beda  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18006bedf  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x18006bee4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006bee8  call    cs:__imp_RtlInitUnicodeString
0x18006beef  nop     dword ptr [rax+rax+00h]
0x18006bef4  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006befc  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r15
0x18006bf00  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18006bf04  lea     rax, [rbp+57h+DestinationString]
0x18006bf08  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006bf0c  xorps   xmm0, xmm0
0x18006bf0f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006bf14  lea     rcx, [rbp+57h+hObject]
0x18006bf18  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18006bf1d  mov     rcx, rax; MutantHandle
0x18006bf20  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006bf24  mov     edx, 100000h; DesiredAccess
0x18006bf29  call    cs:__imp_NtOpenMutant
0x18006bf30  nop     dword ptr [rax+rax+00h]
0x18006bf35  cmp     eax, 0C0000034h
0x18006bf3a  jz      short loc_18006BF48
0x18006bf3c  mov     rcx, [rbp+5Fh]; this
0x18006bf40  test    eax, eax
0x18006bf42  js      loc_18006C15C
0x18006bf48  lea     rdx, [rbp+57h+hObject]
0x18006bf4c  mov     rcx, rbx
0x18006bf4f  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006bf54  and     edi, 0FFFFFFFBh
0x18006bf57  mov     rcx, [rbp+57h+hObject]; hObject
0x18006bf5b  lea     rax, [rcx-1]
0x18006bf5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006bf63  ja      short loc_18006BF71
0x18006bf65  call    cs:__imp_CloseHandle
0x18006bf6c  nop     dword ptr [rax+rax+00h]
0x18006bf71  mov     rdx, [rbx]
0x18006bf74  lea     rax, [rdx-1]
0x18006bf78  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006bf7c  ja      short loc_18006BFCB
0x18006bf7e  or      r8d, 0FFFFFFFFh
0x18006bf82  lea     rcx, [rbp+57h+hMutex]
0x18006bf86  call    ?AcquireContainerMutex@details@helium@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXK@Z
0x18006bf8b  mov     r14, rax
0x18006bf8e  cmp     rsi, rax
0x18006bf91  jz      short loc_18006BFA1
0x18006bf93  mov     rdx, [rax]
0x18006bf96  mov     rcx, rsi
0x18006bf99  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006bf9e  mov     [r14], r15
0x18006bfa1  mov     rcx, [rbp+57h+hMutex]; hMutex
0x18006bfa5  test    rcx, rcx
0x18006bfa8  jz      loc_18006BEBC
0x18006bfae  mov     r14, [rbp+5Fh]
0x18006bfb2  call    cs:__imp_ReleaseMutex
0x18006bfb9  nop     dword ptr [rax+rax+00h]
0x18006bfbe  test    eax, eax
0x18006bfc0  jz      loc_18006C132
0x18006bfc6  jmp     loc_18006BEBC
0x18006bfcb  xorps   xmm0, xmm0
0x18006bfce  movdqu  xmmword ptr [rsp+100h+var_E0], xmm0; int
0x18006bfd4  mov     [rsp+100h+var_E0+8], r15
0x18006bfd9  or      edi, 8
0x18006bfdc  mov     [rbp+57h+var_D0], edi
0x18006bfdf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006bfe3  lea     rdx, [rbp+57h+SourceString]
0x18006bfe7  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18006bfec  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x18006bff1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006bff5  call    cs:__imp_RtlInitUnicodeString
0x18006bffc  nop     dword ptr [rax+rax+00h]
0x18006c001  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006c009  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r15
0x18006c00d  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18006c011  lea     rax, [rbp+57h+DestinationString]
0x18006c015  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006c019  xorps   xmm0, xmm0
0x18006c01c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006c021  lea     rcx, [rsp+100h+var_E0+8]
0x18006c026  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18006c02b  mov     rcx, rax; MutantHandle
0x18006c02e  mov     r9b, 1; InitialOwner
0x18006c031  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006c035  mov     edx, 1F0001h; DesiredAccess
0x18006c03a  call    cs:__imp_NtCreateMutant
0x18006c041  nop     dword ptr [rax+rax+00h]
0x18006c046  cmp     eax, 0C0000035h
0x18006c04b  jz      short loc_18006C071
0x18006c04d  mov     rcx, [rbp+5Fh]; this
0x18006c051  test    eax, eax
0x18006c053  js      loc_18006C11D
0x18006c059  mov     rdx, [rsp+100h+var_E0+8]
0x18006c05e  test    rdx, rdx
0x18006c061  jz      loc_18006C171
0x18006c067  lea     rcx, [rsp+100h+var_E0]
0x18006c06c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006c071  lea     rdx, [rsp+100h+var_E0+8]
0x18006c076  mov     rcx, rbx
0x18006c079  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006c07e  lea     rax, [rsp+100h+var_E0]
0x18006c083  cmp     rsi, rax
0x18006c086  jz      short loc_18006C09F
0x18006c088  mov     rdx, [rsp+100h+var_E0]
0x18006c08d  mov     rcx, rsi
0x18006c090  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006c095  mov     rcx, r15
0x18006c098  mov     [rsp+100h+var_E0], rcx
0x18006c09d  jmp     short loc_18006C0A4
0x18006c09f  mov     rcx, [rsp+100h+var_E0]
0x18006c0a4  and     edi, 0FFFFFFF7h
0x18006c0a7  mov     rdx, [rsp+100h+var_E0+8]
0x18006c0ac  lea     rax, [rdx-1]
0x18006c0b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c0b4  ja      short loc_18006C0CA
0x18006c0b6  mov     rcx, rdx; hObject
0x18006c0b9  call    cs:__imp_CloseHandle
0x18006c0c0  nop     dword ptr [rax+rax+00h]
0x18006c0c5  mov     rcx, [rsp+100h+var_E0]; hMutex
0x18006c0ca  test    rcx, rcx
0x18006c0cd  jz      loc_18006BEBC
0x18006c0d3  mov     r14, [rbp+5Fh]
0x18006c0d7  call    cs:__imp_ReleaseMutex
0x18006c0de  nop     dword ptr [rax+rax+00h]
0x18006c0e3  test    eax, eax
0x18006c0e5  jz      short loc_18006C147
0x18006c0e7  jmp     loc_18006BEBC
0x18006c0ec  lea     rcx, [rbp+57h+SourceString]; void *
0x18006c0f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006c0f5  nop
0x18006c0f6  mov     rax, rbx
0x18006c0f9  mov     rcx, [rbp+57h+var_30]
0x18006c0fd  xor     rcx, rsp; StackCookie
0x18006c100  call    __security_check_cookie
0x18006c105  mov     rbx, [rsp+100h+arg_10]
0x18006c10d  add     rsp, 0E0h
0x18006c114  pop     r15
0x18006c116  pop     r14
0x18006c118  pop     rdi
0x18006c119  pop     rsi
0x18006c11a  pop     rbp
0x18006c11b  retn
0x18006c11d  mov     r9d, eax; char *
0x18006c120  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006c127  mov     edx, 51h ; 'Q'; void *
0x18006c12c  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18006c132  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006c139  mov     edx, 9E7h; void *
0x18006c13e  mov     rcx, r14; this
0x18006c141  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006c147  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006c14e  mov     edx, 9E7h; void *
0x18006c153  mov     rcx, r14; this
0x18006c156  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006c15c  mov     r9d, eax; char *
0x18006c15f  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006c166  mov     edx, 2Bh ; '+'; void *
0x18006c16b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18006c171  mov     rcx, [rbp+5Fh]; this
0x18006c175  mov     edx, 0C0Ch; void *
0x18006c17a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
