# Win32ShellUIHostRegistration::LaunchHost(void)

- ea: `0x18007f2a0`
- end: `0x18007f45f`
- name: `?LaunchHost@Win32ShellUIHostRegistration@@UEAA_NXZ`
- size: `447`
- prototype: `bool __fastcall(Win32ShellUIHostRegistration *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000c444`
- `0x180010880`
- `0x1800164dc`
- `0x18001c95c`
- `0x18002404c`
- `0x180029ce4`
- `0x180029d0c`
- `0x18002af50`
- `0x18007f2a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007f400`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007f400`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Win32ShellUIHostRegistration::LaunchHost(Win32ShellUIHostRegistration *this)
{
  WCHAR *v2; // rbx
  __int64 v3; // r8
  const unsigned __int16 **v4; // rsi
  const unsigned __int16 *v6; // r14
  char *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // r8
  bool v10; // bl
  struct _PROCESS_INFORMATION *v11; // rdx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-39h] BYREF
  LPCWSTR lpApplicationName; // [rsp+110h] [rbp+67h] BYREF
  WCHAR *v15; // [rsp+118h] [rbp+6Fh] BYREF
  char v16; // [rsp+120h] [rbp+77h] BYREF

  v2 = 0;
  v15 = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
    &lpApplicationName,
    *((_QWORD *)this + 21));
  v4 = (const unsigned __int16 **)((char *)this + 176);
  if ( *((_QWORD *)this + 22) )
  {
    if ( (int)wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v15,
                &lpApplicationName,
                v3,
                (char *)this + 176) < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpApplicationName);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v15);
      return 0;
    }
    v2 = v15;
  }
  v6 = &qword_180090A60;
  if ( *v4 )
    v6 = *v4;
  v7 = (char *)this + 152;
  v8 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::operator->(
                    v7,
                    &v16)
     + 352LL;
  v9 = -1;
  do
    ++v9;
  while ( v6[v9] );
  std::wstring::_Assign<unsigned short>(v8, v6);
  tip2::test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::~test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>(&v16);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::operator->(
                          v7,
                          &v16)
           + 305LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::~test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>(&v16);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  memset(&StartupInfo.lpReserved, 0, 40);
  StartupInfo.dwFlags = 128;
  *(_DWORD *)&StartupInfo.wShowWindow = 1;
  StartupInfo.lpReserved2 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v10 = CreateProcessW(lpApplicationName, v2, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::operator->(
                          v7,
                          &v16)
           + 312LL) = v10;
  tip2::test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::~test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>(&v16);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v11);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpApplicationName);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v15);
  return v10;
}

```

## disassembly

```asm
0x18007f2a0  mov     [rsp-8+arg_18], rbx
0x18007f2a5  push    rbp
0x18007f2a6  push    rsi
0x18007f2a7  push    rdi
0x18007f2a8  push    r14
0x18007f2aa  push    r15
0x18007f2ac  lea     rbp, [rsp-37h]
0x18007f2b1  sub     rsp, 0E0h
0x18007f2b8  mov     rdi, rcx
0x18007f2bb  xor     r15d, r15d
0x18007f2be  mov     ebx, r15d
0x18007f2c1  mov     [rbp+57h+arg_8], rbx
0x18007f2c5  mov     rdx, [rcx+0A8h]
0x18007f2cc  lea     rcx, [rbp+57h+lpApplicationName]
0x18007f2d0  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x18007f2d5  nop
0x18007f2d6  lea     rsi, [rdi+0B0h]
0x18007f2dd  cmp     [rsi], r15
0x18007f2e0  jz      short loc_18007F314
0x18007f2e2  mov     r9, rsi
0x18007f2e5  lea     rdx, [rbp+57h+lpApplicationName]
0x18007f2e9  lea     rcx, [rbp+57h+arg_8]
0x18007f2ed  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@AEAY01$$CBG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x18007f2f2  test    eax, eax
0x18007f2f4  jns     short loc_18007F310
0x18007f2f6  lea     rcx, [rbp+57h+lpApplicationName]
0x18007f2fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007f2ff  nop
0x18007f300  lea     rcx, [rbp+57h+arg_8]
0x18007f304  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007f309  xor     al, al
0x18007f30b  jmp     loc_18007F448
0x18007f310  mov     rbx, [rbp+57h+arg_8]
0x18007f314  lea     r14, qword_180090A60
0x18007f31b  cmp     [rsi], r15
0x18007f31e  cmovnz  r14, [rsi]
0x18007f322  add     rdi, 98h
0x18007f329  lea     rdx, [rbp+57h+arg_10]
0x18007f32d  mov     rcx, rdi
0x18007f330  call    ??C?$tip_test@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::operator->(void)
0x18007f335  nop
0x18007f336  mov     rcx, [rax]
0x18007f339  add     rcx, 160h
0x18007f340  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007f344  inc     r8
0x18007f347  cmp     [r14+r8*2], r15w
0x18007f34c  jnz     short loc_18007F344
0x18007f34e  mov     rdx, r14
0x18007f351  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007f356  nop
0x18007f357  lea     rcx, [rbp+57h+arg_10]
0x18007f35b  call    ??1?$test_data_control@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::~test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>(void)
0x18007f360  lea     rdx, [rbp+57h+arg_10]
0x18007f364  mov     rcx, rdi
0x18007f367  call    ??C?$tip_test@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::operator->(void)
0x18007f36c  mov     rcx, [rax]
0x18007f36f  mov     r14d, 1
0x18007f375  mov     [rcx+131h], r14b
0x18007f37c  lea     rcx, [rbp+57h+arg_10]
0x18007f380  call    ??1?$test_data_control@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::~test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>(void)
0x18007f385  lea     esi, [r14+67h]
0x18007f389  mov     r8d, esi; Size
0x18007f38c  xor     edx, edx; Val
0x18007f38e  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18007f392  call    memset_0
0x18007f397  mov     [rbp+57h+StartupInfo.cb], esi
0x18007f39a  mov     [rbp+57h+StartupInfo.lpReserved], r15
0x18007f39e  mov     [rbp+57h+StartupInfo.lpTitle], r15
0x18007f3a2  mov     [rbp+57h+StartupInfo.lpDesktop], r15
0x18007f3a6  mov     qword ptr [rbp+57h+StartupInfo.dwXSize], r15
0x18007f3aa  mov     qword ptr [rbp+57h+StartupInfo.dwX], r15
0x18007f3ae  mov     [rbp+57h+StartupInfo.dwFlags], 80h
0x18007f3b5  mov     dword ptr [rbp+57h+StartupInfo.wShowWindow], r14d
0x18007f3b9  mov     [rbp+57h+StartupInfo.lpReserved2], r15
0x18007f3bd  xorps   xmm0, xmm0
0x18007f3c0  xor     eax, eax
0x18007f3c2  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18007f3c6  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18007f3ca  lea     rax, [rbp+57h+ProcessInformation]
0x18007f3ce  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x18007f3d3  lea     rax, [rbp+57h+StartupInfo]
0x18007f3d7  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x18007f3dc  mov     [rsp+100h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18007f3e1  mov     [rsp+100h+lpEnvironment], r15; lpEnvironment
0x18007f3e6  mov     [rsp+100h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18007f3ee  mov     [rsp+100h+bInheritHandles], r15d; bInheritHandles
0x18007f3f3  xor     r9d, r9d; lpThreadAttributes
0x18007f3f6  xor     r8d, r8d; lpProcessAttributes
0x18007f3f9  mov     rdx, rbx; lpCommandLine
0x18007f3fc  mov     rcx, [rbp+57h+lpApplicationName]; lpApplicationName
0x18007f400  call    cs:__imp_CreateProcessW
0x18007f406  test    eax, eax
0x18007f408  setnz   bl
0x18007f40b  lea     rdx, [rbp+57h+arg_10]
0x18007f40f  mov     rcx, rdi
0x18007f412  call    ??C?$tip_test@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::operator->(void)
0x18007f417  mov     rcx, [rax]
0x18007f41a  mov     [rcx+138h], bl
0x18007f420  lea     rcx, [rbp+57h+arg_10]
0x18007f424  call    ??1?$test_data_control@V?$merged_data@U_tip_HostLaunchTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>::~test_data_control<tip2::details::merged_data<_tip_HostLaunchTest,_tip_HostLaunchTest>>(void)
0x18007f429  lea     rcx, [rbp+57h+ProcessInformation]; this
0x18007f42d  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18007f432  nop
0x18007f433  lea     rcx, [rbp+57h+lpApplicationName]
0x18007f437  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007f43c  nop
0x18007f43d  lea     rcx, [rbp+57h+arg_8]
0x18007f441  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007f446  mov     al, bl
0x18007f448  mov     rbx, [rsp+100h+arg_18]
0x18007f450  add     rsp, 0E0h
0x18007f457  pop     r15
0x18007f459  pop     r14
0x18007f45b  pop     rdi
0x18007f45c  pop     rsi
0x18007f45d  pop     rbp
0x18007f45e  retn
```
