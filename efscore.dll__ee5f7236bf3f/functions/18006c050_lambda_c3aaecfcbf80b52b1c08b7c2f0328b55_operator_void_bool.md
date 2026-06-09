# _lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()(void *,bool *)

- ea: `0x18006c050`
- end: `0x18006c286`
- name: `??R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006ae80`

## callees

- `0x1800049f4`
- `0x180004e44`
- `0x180004eb4`
- `0x18000ef44`
- `0x1800467d0`
- `0x1800474b0`
- `0x1800476b0`
- `0x180048b58`
- `0x18004d12c`
- `0x180051858`
- `0x18006c050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18006c103`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18006c103`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006c124`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006c124`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006c083`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006c083`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006c16f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006c16f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c228`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c228`

## string_xrefs

- `0x18006c094`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006c1b3`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006c239`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()(__int64 a1, __int64 a2, _BYTE *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int ValueW; // eax
  const struct _FILETIME *v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  char v11; // r9
  const struct _FILETIME *v12; // rdx
  unsigned int v13; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-30h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-30h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-30h]
  RTL_SRWLOCK *v17; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v18; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY phkResult; // [rsp+70h] [rbp+20h] BYREF
  __int64 pcbData; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int64 Data; // [rsp+88h] [rbp+38h] BYREF

  pcbData = a2;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v4 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1C1,
           (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
           (const char *)v4,
           pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    return v5;
  }
  v18 = EfsUtcTimestamp();
  if ( __TSS0__1___R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55___QEBAJPEAXPEA_N_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                                  + (unsigned int)tls_index)
                                                                                                + 4LL) )
  {
    Init_thread_header(&__TSS0__1___R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55___QEBAJPEAXPEA_N_Z_4HA);
    if ( __TSS0__1___R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55___QEBAJPEAXPEA_N_Z_4HA == -1 )
    {
      InitializeSRWLock(&`_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()'::`2'::g_canFireCheckLock);
      atexit(`_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()'::`2'::`dynamic atexit destructor for 'g_canFireCheckLock'');
      Init_thread_footer(&__TSS0__1___R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55___QEBAJPEAXPEA_N_Z_4HA);
    }
  }
  AcquireSRWLockExclusive(&`_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()'::`2'::g_canFireCheckLock);
  v17 = &`_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()'::`2'::g_canFireCheckLock;
  Data = 0;
  LODWORD(pcbData) = 8;
  ValueW = RegGetValueW(
             phkResult,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\RMS",
             L"NextUserInteractionRequestMinTime",
             0x40u,
             0,
             &Data,
             (LPDWORD)&pcbData);
  if ( ValueW )
  {
    if ( ValueW - 2 > 1 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1DE,
             (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
             (const char *)ValueW,
             pdwTypea);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return v5;
    }
  }
  else
  {
    v10 = wil::FileTime::ToInt64((wil::FileTime *)&v18, v8);
    if ( v10 < Data )
    {
      *a3 = v11;
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return 0;
    }
  }
  Data = (unsigned __int64)wil::FileTime::Add((wil::FileTime *)&v18, (const struct _FILETIME *)0xC92A69C000LL, v9);
  Data = wil::FileTime::ToInt64((wil::FileTime *)&Data, v12);
  v13 = RegSetKeyValueW(
          phkResult,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\RMS",
          L"NextUserInteractionRequestMinTime",
          0xBu,
          &Data,
          8u);
  if ( v13 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1EA,
           (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
           (const char *)v13,
           pdwTypeb);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    return v5;
  }
  *a3 = 1;
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return 0;
}

```

## disassembly

```asm
0x18006c050  mov     [rsp-18h+arg_8], rdx
0x18006c055  mov     [rsp-18h+phkResult], rcx
0x18006c05a  push    rbp
0x18006c05b  push    rbx
0x18006c05c  push    rsi
0x18006c05d  mov     rbp, rsp
0x18006c060  sub     rsp, 50h
0x18006c064  mov     rbx, r8
0x18006c067  mov     [rbp+phkResult], 0
0x18006c06f  xor     edx, edx
0x18006c071  lea     rcx, [rbp+phkResult]
0x18006c075  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006c07a  lea     rdx, [rbp+phkResult]; phkResult
0x18006c07e  mov     ecx, 0F003Fh; samDesired
0x18006c083  call    cs:__imp_RegOpenCurrentUser
0x18006c089  test    eax, eax
0x18006c08b  jz      short loc_18006C0B8
0x18006c08d  mov     rcx, [rbp+18h]; this
0x18006c091  mov     r9d, eax; char *
0x18006c094  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006c09b  mov     edx, 1C1h; void *
0x18006c0a0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c0a5  mov     ebx, eax
0x18006c0a7  lea     rcx, [rbp+phkResult]
0x18006c0ab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c0b0  nop
0x18006c0b1  mov     eax, ebx
0x18006c0b3  jmp     loc_18006C27E
0x18006c0b8  call    ?EfsUtcTimestamp@@YA_KXZ; EfsUtcTimestamp(void)
0x18006c0bd  mov     [rbp+var_8], rax
0x18006c0c1  mov     ecx, cs:_tls_index
0x18006c0c7  mov     rax, gs:58h
0x18006c0d0  mov     edx, 4
0x18006c0d5  mov     rax, [rax+rcx*8]
0x18006c0d9  lea     rsi, ?g_canFireCheckLock@?1???R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z@4VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock `_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_::operator()(void *,bool *)'::`2'::g_canFireCheckLock
0x18006c0e0  mov     eax, [rdx+rax]
0x18006c0e3  cmp     cs:?$TSS0@?1???R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z@4HA, eax
0x18006c0e9  jle     short loc_18006C121
0x18006c0eb  lea     rcx, ?$TSS0@?1???R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z@4HA
0x18006c0f2  call    _Init_thread_header
0x18006c0f7  cmp     cs:?$TSS0@?1???R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z@4HA, 0FFFFFFFFh
0x18006c0fe  jnz     short loc_18006C121
0x18006c100  mov     rcx, rsi; SRWLock
0x18006c103  call    cs:__imp_InitializeSRWLock
0x18006c109  lea     rcx, ??__Fg_canFireCheckLock@?1???R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z@YAXXZ; void (__cdecl *)()
0x18006c110  call    atexit
0x18006c115  lea     rcx, ?$TSS0@?1???R_lambda_c3aaecfcbf80b52b1c08b7c2f0328b55_@@QEBAJPEAXPEA_N@Z@4HA
0x18006c11c  call    _Init_thread_footer
0x18006c121  mov     rcx, rsi; SRWLock
0x18006c124  call    cs:__imp_AcquireSRWLockExclusive
0x18006c12a  mov     [rbp+var_10], rsi
0x18006c12e  mov     [rbp+Data], 0
0x18006c136  mov     esi, 8
0x18006c13b  mov     dword ptr [rbp+arg_8], esi
0x18006c13e  lea     rax, [rbp+arg_8]
0x18006c142  mov     [rsp+50h+pcbData], rax; pcbData
0x18006c147  lea     rax, [rbp+Data]
0x18006c14b  mov     [rsp+50h+pvData], rax; pvData
0x18006c150  mov     [rsp+50h+pdwType], 0; unsigned int
0x18006c159  lea     r9d, [rsi+38h]; dwFlags
0x18006c15d  lea     r8, aNextuserintera; "NextUserInteractionRequestMinTime"
0x18006c164  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18006c16b  mov     rcx, [rbp+phkResult]; hkey
0x18006c16f  call    cs:__imp_RegGetValueW
0x18006c175  mov     r9d, eax; char *
0x18006c178  test    eax, eax
0x18006c17a  jnz     short loc_18006C1A7
0x18006c17c  lea     rcx, [rbp+var_8]; this
0x18006c180  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18006c185  cmp     rax, [rbp+Data]
0x18006c189  jnb     short loc_18006C1DF
0x18006c18b  mov     [rbx], r9b
0x18006c18e  lea     rcx, [rbp+var_10]; this
0x18006c192  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006c197  nop
0x18006c198  lea     rcx, [rbp+phkResult]
0x18006c19c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c1a1  nop
0x18006c1a2  jmp     loc_18006C27C
0x18006c1a7  add     eax, 0FFFFFFFEh
0x18006c1aa  cmp     eax, 1
0x18006c1ad  jbe     short loc_18006C1DF
0x18006c1af  mov     rcx, [rbp+18h]; this
0x18006c1b3  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006c1ba  mov     edx, 1DEh; void *
0x18006c1bf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c1c4  mov     ebx, eax
0x18006c1c6  lea     rcx, [rbp+var_10]; this
0x18006c1ca  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006c1cf  nop
0x18006c1d0  lea     rcx, [rbp+phkResult]
0x18006c1d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c1d9  nop
0x18006c1da  jmp     loc_18006C0B1
0x18006c1df  mov     rdx, 0C92A69C000h; struct _FILETIME *
0x18006c1e9  lea     rcx, [rbp+var_8]; this
0x18006c1ed  call    ?Add@FileTime@wil@@YA?AU_FILETIME@@AEBU3@_J@Z; wil::FileTime::Add(_FILETIME const &,__int64)
0x18006c1f2  mov     [rbp+Data], rax
0x18006c1f6  lea     rcx, [rbp+Data]; this
0x18006c1fa  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18006c1ff  mov     [rbp+Data], rax
0x18006c203  mov     dword ptr [rsp+50h+pvData], esi; cbData
0x18006c207  lea     rax, [rbp+Data]
0x18006c20b  mov     [rsp+50h+pdwType], rax; unsigned int
0x18006c210  mov     r9d, 0Bh; dwType
0x18006c216  lea     r8, aNextuserintera; "NextUserInteractionRequestMinTime"
0x18006c21d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18006c224  mov     rcx, [rbp+phkResult]; hKey
0x18006c228  call    cs:__imp_RegSetKeyValueW
0x18006c22e  test    eax, eax
0x18006c230  jz      short loc_18006C265
0x18006c232  mov     rcx, [rbp+18h]; this
0x18006c236  mov     r9d, eax; char *
0x18006c239  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006c240  mov     edx, 1EAh; void *
0x18006c245  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c24a  mov     ebx, eax
0x18006c24c  lea     rcx, [rbp+var_10]; this
0x18006c250  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006c255  nop
0x18006c256  lea     rcx, [rbp+phkResult]
0x18006c25a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c25f  nop
0x18006c260  jmp     loc_18006C0B1
0x18006c265  mov     byte ptr [rbx], 1
0x18006c268  lea     rcx, [rbp+var_10]; this
0x18006c26c  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006c271  nop
0x18006c272  lea     rcx, [rbp+phkResult]
0x18006c276  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c27b  nop
0x18006c27c  xor     eax, eax
0x18006c27e  add     rsp, 50h
0x18006c282  pop     rsi
0x18006c283  pop     rbx
0x18006c284  pop     rbp
0x18006c285  retn
```
