# CLogonTaskFramework::NotifyShellCompletionIfNecessary(void)

- ea: `0x1400e1870`
- end: `0x1400e1a6d`
- name: `?NotifyShellCompletionIfNecessary@CLogonTaskFramework@@QEAAXXZ`
- size: `509`
- prototype: `void __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009e64`
- `0x14015a5c8`
- `0x1401a1e0c`

## callees

- `0x140005e14`
- `0x140012594`
- `0x14001b2c8`
- `0x14001c330`
- `0x140023418`
- `0x140082ab4`
- `0x140085cc4`
- `0x1400e1870`
- `0x1401d9010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1400e19f7`
- `ntdll!RtlPublishWnfStateData` at `0x1400e1a1b`
- `ntdll!RtlPublishWnfStateData` at `0x1400e19f7`
- `ntdll!RtlPublishWnfStateData` at `0x1400e1a1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e18ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e18ab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400e19ca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400e19ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e1889`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e1889`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400e1924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400e1924`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400e1913`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400e1913`
- `SHELL32!__imp_SHCreateSessionKey` at `0x1400e18d3`
- `SHELL32!__imp_SHCreateSessionKey` at `0x1400e18d3`
- `api-ms-win-core-biplmapi-l1-1-4!BiNotifyNewSessionComplete` at `0x1400e1a27`
- `api-ms-win-core-biplmapi-l1-1-4!BiNotifyNewSessionComplete` at `0x1400e1a27`

## string_xrefs

- `0x1400e18e4`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLogonTaskFramework::NotifyShellCompletionIfNecessary(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  char Ptr; // si
  int v4; // eax
  int v5; // eax
  PVOID v6; // rbx
  unsigned int Error; // eax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v11; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v2 = this + 4;
  AcquireSRWLockExclusive(this + 4);
  Ptr = (char)this[29].Ptr;
  LOBYTE(this[29].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  if ( !Ptr )
  {
    hKey = 0;
    v4 = SHCreateSessionKey(131078, &hKey);
    if ( v4 >= 0 )
    {
      RegDeleteKeyExW(hKey, L"FSIAInProgress", 0, 0);
      RegCloseKey(hKey);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x327B,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v4,
        v9);
    }
    v11 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
    if ( (int)CLogonTaskFramework::s_QueryServiceImmersiveShell(
                (const struct _GUID *)&SID_ImmersiveLauncher,
                &GUID_d8d60399_a0f1_f987_5551_321fd1b49864,
                &v11) >= 0
      && IsOnUserDesktop() )
    {
      v5 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v11 + 96LL))(v11);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3288,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v5,
          v9);
    }
    CLogonTaskFramework::s_PostTrayMessage(0x5BDu, 0, 0);
    v6 = this[6].Ptr;
    Error = ResultFromKnownLastError();
    if ( v6 )
      SetEvent(this[6].Ptr);
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3291,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)Error,
        v9);
    if ( !BYTE4(this[29].Ptr) )
    {
      RtlPublishWnfStateData(WNF_SHEL_LOGON_COMPLETE, 0, 0, 0);
      v9 = 0;
      RtlPublishWnfStateData(WNF_SHEL_SESSION_LOGON_COMPLETE, 0, 0, 0);
    }
    v8 = BiNotifyNewSessionComplete();
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x32A7,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v8,
        v9);
    Windows::Shell::CImmersiveCursor::DisableCursorSuppression();
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  }
}

```

## disassembly

```asm
0x1400e1870  mov     [rsp+arg_10], rbx
0x1400e1875  mov     [rsp+arg_18], rsi
0x1400e187a  push    rdi
0x1400e187b  sub     rsp, 30h
0x1400e187f  mov     rdi, rcx
0x1400e1882  lea     rbx, [rcx+20h]
0x1400e1886  mov     rcx, rbx; SRWLock
0x1400e1889  call    cs:__imp_AcquireSRWLockExclusive
0x1400e1890  nop     dword ptr [rax+rax+00h]
0x1400e1895  mov     sil, [rdi+0E8h]
0x1400e189c  mov     byte ptr [rdi+0E8h], 1
0x1400e18a3  test    rbx, rbx
0x1400e18a6  jz      short loc_1400E18B7
0x1400e18a8  mov     rcx, rbx; SRWLock
0x1400e18ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1400e18b2  nop     dword ptr [rax+rax+00h]
0x1400e18b7  test    sil, sil
0x1400e18ba  jnz     loc_1400E1A5C
0x1400e18c0  mov     [rsp+38h+hKey], 0
0x1400e18c9  lea     rdx, [rsp+38h+hKey]
0x1400e18ce  mov     ecx, 20006h
0x1400e18d3  call    cs:__imp_SHCreateSessionKey
0x1400e18da  nop     dword ptr [rax+rax+00h]
0x1400e18df  mov     rcx, [rsp+38h]; this
0x1400e18e4  lea     rsi, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400e18eb  test    eax, eax
0x1400e18ed  jns     short loc_1400E1901
0x1400e18ef  mov     r9d, eax; char *
0x1400e18f2  mov     r8, rsi; unsigned int
0x1400e18f5  mov     edx, 327Bh; void *
0x1400e18fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400e18ff  jmp     short loc_1400E1930
0x1400e1901  xor     r9d, r9d; Reserved
0x1400e1904  xor     r8d, r8d; samDesired
0x1400e1907  lea     rdx, aFsiainprogress; "FSIAInProgress"
0x1400e190e  mov     rcx, [rsp+38h+hKey]; hKey
0x1400e1913  call    cs:__imp_RegDeleteKeyExW
0x1400e191a  nop     dword ptr [rax+rax+00h]
0x1400e191f  mov     rcx, [rsp+38h+hKey]; hKey
0x1400e1924  call    cs:__imp_RegCloseKey
0x1400e192b  nop     dword ptr [rax+rax+00h]
0x1400e1930  mov     [rsp+38h+arg_0], 0
0x1400e1939  lea     rcx, [rsp+38h+arg_0]
0x1400e193e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400e1943  lea     r8, [rsp+38h+arg_0]; void **
0x1400e1948  lea     rdx, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864; struct _GUID *
0x1400e194f  lea     rcx, SID_ImmersiveLauncher; struct _GUID *
0x1400e1956  call    ?s_QueryServiceImmersiveShell@CLogonTaskFramework@@CAJAEBU_GUID@@0PEAPEAX@Z; CLogonTaskFramework::s_QueryServiceImmersiveShell(_GUID const &,_GUID const &,void * *)
0x1400e195b  test    eax, eax
0x1400e195d  js      short loc_1400E1992
0x1400e195f  call    ?IsOnUserDesktop@@YA_NXZ; IsOnUserDesktop(void)
0x1400e1964  test    al, al
0x1400e1966  jz      short loc_1400E1992
0x1400e1968  mov     rcx, [rsp+38h+arg_0]
0x1400e196d  mov     rax, [rcx]
0x1400e1970  mov     rax, [rax+60h]
0x1400e1974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e1979  mov     rcx, [rsp+38h]; this
0x1400e197e  test    eax, eax
0x1400e1980  jns     short loc_1400E1992
0x1400e1982  mov     r9d, eax; char *
0x1400e1985  mov     r8, rsi; unsigned int
0x1400e1988  mov     edx, 3288h; void *
0x1400e198d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400e1992  xor     r8d, r8d; lParam
0x1400e1995  xor     edx, edx; wParam
0x1400e1997  mov     ecx, 5BDh; Msg
0x1400e199c  call    ?s_PostTrayMessage@CLogonTaskFramework@@CAXI_K_J@Z; CLogonTaskFramework::s_PostTrayMessage(uint,unsigned __int64,__int64)
0x1400e19a1  mov     rbx, [rdi+30h]
0x1400e19a5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400e19aa  mov     rcx, [rsp+38h]; this
0x1400e19af  test    rbx, rbx
0x1400e19b2  jnz     short loc_1400E19C6
0x1400e19b4  mov     r9d, eax; char *
0x1400e19b7  mov     r8, rsi; unsigned int
0x1400e19ba  mov     edx, 3291h; void *
0x1400e19bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400e19c4  jmp     short loc_1400E19D6
0x1400e19c6  mov     rcx, [rdi+30h]; hEvent
0x1400e19ca  call    cs:__imp_SetEvent
0x1400e19d1  nop     dword ptr [rax+rax+00h]
0x1400e19d6  cmp     byte ptr [rdi+0ECh], 0
0x1400e19dd  jnz     short loc_1400E1A27
0x1400e19df  mov     qword ptr [rsp+38h+var_18], 0
0x1400e19e8  xor     r9d, r9d
0x1400e19eb  xor     r8d, r8d
0x1400e19ee  xor     edx, edx
0x1400e19f0  mov     rcx, cs:WNF_SHEL_LOGON_COMPLETE
0x1400e19f7  call    cs:__imp_RtlPublishWnfStateData
0x1400e19fe  nop     dword ptr [rax+rax+00h]
0x1400e1a03  mov     qword ptr [rsp+38h+var_18], 0; int
0x1400e1a0c  xor     r9d, r9d
0x1400e1a0f  xor     r8d, r8d
0x1400e1a12  xor     edx, edx
0x1400e1a14  mov     rcx, cs:WNF_SHEL_SESSION_LOGON_COMPLETE
0x1400e1a1b  call    cs:__imp_RtlPublishWnfStateData
0x1400e1a22  nop     dword ptr [rax+rax+00h]
0x1400e1a27  call    cs:__imp_BiNotifyNewSessionComplete
0x1400e1a2e  nop     dword ptr [rax+rax+00h]
0x1400e1a33  mov     rcx, [rsp+38h]; this
0x1400e1a38  test    eax, eax
0x1400e1a3a  jns     short loc_1400E1A4C
0x1400e1a3c  mov     r9d, eax; char *
0x1400e1a3f  mov     r8, rsi; unsigned int
0x1400e1a42  mov     edx, 32A7h; void *
0x1400e1a47  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400e1a4c  call    ?DisableCursorSuppression@CImmersiveCursor@Shell@Windows@@SAXXZ; Windows::Shell::CImmersiveCursor::DisableCursorSuppression(void)
0x1400e1a51  nop
0x1400e1a52  lea     rcx, [rsp+38h+arg_0]
0x1400e1a57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400e1a5c  mov     rbx, [rsp+38h+arg_10]
0x1400e1a61  mov     rsi, [rsp+38h+arg_18]
0x1400e1a66  add     rsp, 30h
0x1400e1a6a  pop     rdi
0x1400e1a6b  retn
```
