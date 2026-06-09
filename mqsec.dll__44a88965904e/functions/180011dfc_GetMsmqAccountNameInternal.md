# _GetMsmqAccountNameInternal

- ea: `0x180011dfc`
- end: `0x180012090`
- name: `_GetMsmqAccountNameInternal`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180011bd8`

## callees

- `0x1800049ac`
- `0x18000eb48`
- `0x18000edd8`
- `0x18000ee9c`
- `0x180011638`
- `0x180011dfc`
- `0x18001722c`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011fa9`
- `msvcrt!_wcsicmp` at `0x180011fa9`
- `msvcrt!free` at `0x180012012`
- `msvcrt!free` at `0x180012012`
- `ADVAPI32!QueryServiceConfigW` at `0x180011f05`
- `ADVAPI32!QueryServiceConfigW` at `0x180011f48`
- `ADVAPI32!QueryServiceConfigW` at `0x180011f05`
- `ADVAPI32!QueryServiceConfigW` at `0x180011f48`
- `ADVAPI32!OpenServiceW` at `0x180011e8e`
- `ADVAPI32!OpenServiceW` at `0x180011e8e`
- `ADVAPI32!OpenSCManagerW` at `0x180011e20`
- `ADVAPI32!OpenSCManagerW` at `0x180011e20`
- `ADVAPI32!CloseServiceHandle` at `0x180011ee7`
- `ADVAPI32!CloseServiceHandle` at `0x18001201c`
- `ADVAPI32!CloseServiceHandle` at `0x180012026`
- `ADVAPI32!CloseServiceHandle` at `0x180012067`
- `ADVAPI32!CloseServiceHandle` at `0x180012071`
- `ADVAPI32!CloseServiceHandle` at `0x180011ee7`
- `ADVAPI32!CloseServiceHandle` at `0x18001201c`
- `ADVAPI32!CloseServiceHandle` at `0x180012026`
- `ADVAPI32!CloseServiceHandle` at `0x180012067`
- `ADVAPI32!CloseServiceHandle` at `0x180012071`
- `KERNEL32!GetLastError` at `0x180011e52`
- `KERNEL32!GetLastError` at `0x180011ebd`
- `KERNEL32!GetLastError` at `0x180011f0d`
- `KERNEL32!GetLastError` at `0x180011f6e`
- `KERNEL32!GetLastError` at `0x180011e52`
- `KERNEL32!GetLastError` at `0x180011ebd`
- `KERNEL32!GetLastError` at `0x180011f0d`
- `KERNEL32!GetLastError` at `0x180011f6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
int GetMsmqAccountNameInternal()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  PVOID *v2; // rax
  DWORD v3; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  DWORD v6; // eax
  BOOL v7; // esi
  DWORD LastError; // eax
  struct _QUERY_SERVICE_CONFIGW *v9; // rsi
  DWORD v10; // eax
  LPWSTR lpServiceStartName; // rbp
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-78h] BYREF
  SC_HANDLE v17; // [rsp+28h] [rbp-70h]
  SC_HANDLE v18; // [rsp+30h] [rbp-68h]
  struct _QUERY_SERVICE_CONFIGW *v19; // [rsp+38h] [rbp-60h]
  _BYTE v20[40]; // [rsp+40h] [rbp-58h] BYREF

  v0 = OpenSCManagerW(0, 0, 0x80000000);
  v1 = v0;
  v17 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"MSMQ", 1u);
    v5 = v4;
    v18 = v4;
    if ( v4 )
    {
      pcbBytesNeeded = 0;
      v7 = QueryServiceConfigW(v4, 0, 0, &pcbBytesNeeded);
      LastError = GetLastError();
      if ( v7 || LastError != 122 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            50,
            &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids,
            LastError);
        CloseServiceHandle(v5);
        LODWORD(v2) = CloseServiceHandle(v1);
      }
      else
      {
        v9 = (struct _QUERY_SERVICE_CONFIGW *)MmAllocate(pcbBytesNeeded);
        v19 = v9;
        if ( !QueryServiceConfigW(v5, v9, pcbBytesNeeded, &pcbBytesNeeded)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        {
          v10 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 51, &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids, v10);
        }
        lpServiceStartName = v9->lpServiceStartName;
        if ( lpServiceStartName && _wcsicmp(v9->lpServiceStartName, L"LocalSystem") )
        {
          v12 = -1;
          do
            ++v12;
          while ( lpServiceStartName[v12] );
          std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(
            &g_pwzLocalMsmqAccount,
            lpServiceStartName,
            v12);
        }
        else
        {
          v13 = _BuildAccountNameForSid(v20, g_pSystemSid);
          std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(
            &g_pwzLocalMsmqAccount,
            v13,
            0,
            -1);
          LOBYTE(v14) = 1;
          std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v20, v14, 0);
        }
        free(v9);
        CloseServiceHandle(v5);
        LODWORD(v2) = CloseServiceHandle(v1);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      {
        v6 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 49, &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids, v6);
      }
      LODWORD(v2) = CloseServiceHandle(v1);
    }
  }
  else
  {
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
    {
      v3 = GetLastError();
      LODWORD(v2) = WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 22),
                      48,
                      &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids,
                      v3);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x180011dfc  push    rbx
0x180011dfe  push    rbp
0x180011dff  push    rsi
0x180011e00  push    rdi
0x180011e01  push    r14
0x180011e03  sub     rsp, 70h
0x180011e07  mov     rax, cs:__security_cookie
0x180011e0e  xor     rax, rsp
0x180011e11  mov     [rsp+98h+var_30], rax
0x180011e16  xor     edx, edx; lpDatabaseName
0x180011e18  xor     ecx, ecx; lpMachineName
0x180011e1a  mov     r8d, 80000000h; dwDesiredAccess
0x180011e20  call    cs:__imp_OpenSCManagerW
0x180011e26  mov     rbx, rax
0x180011e29  mov     [rsp+98h+var_70], rax
0x180011e2e  xor     r14d, r14d
0x180011e31  test    rax, rax
0x180011e34  jnz     short loc_180011E7E
0x180011e36  lea     rax, WPP_GLOBAL_Control
0x180011e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e44  cmp     rcx, rax
0x180011e47  jz      short loc_180011E79
0x180011e49  test    byte ptr [rcx+0BCh], 1
0x180011e50  jz      short loc_180011E79
0x180011e52  call    cs:__imp_GetLastError
0x180011e58  lea     edx, [rbx+30h]
0x180011e5b  mov     r9d, eax
0x180011e5e  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e6c  mov     rcx, [rcx+0B0h]
0x180011e73  call    WPP_SF_d
0x180011e78  nop
0x180011e79  jmp     loc_180012078
0x180011e7e  mov     r8d, 1; dwDesiredAccess
0x180011e84  lea     rdx, SubsystemName; "MSMQ"
0x180011e8b  mov     rcx, rbx; hSCManager
0x180011e8e  call    cs:__imp_OpenServiceW
0x180011e94  mov     rdi, rax
0x180011e97  mov     [rsp+98h+var_68], rax
0x180011e9c  test    rax, rax
0x180011e9f  jnz     short loc_180011EF3
0x180011ea1  lea     rax, WPP_GLOBAL_Control
0x180011ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180011eaf  cmp     rcx, rax
0x180011eb2  jz      short loc_180011EE4
0x180011eb4  test    byte ptr [rcx+0BCh], 1
0x180011ebb  jz      short loc_180011EE4
0x180011ebd  call    cs:__imp_GetLastError
0x180011ec3  lea     edx, [rdi+31h]
0x180011ec6  mov     r9d, eax
0x180011ec9  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ed7  mov     rcx, [rcx+0B0h]
0x180011ede  call    WPP_SF_d
0x180011ee3  nop
0x180011ee4  mov     rcx, rbx; hSCObject
0x180011ee7  call    cs:__imp_CloseServiceHandle
0x180011eed  nop
0x180011eee  jmp     loc_180012078
0x180011ef3  mov     [rsp+98h+pcbBytesNeeded], r14d
0x180011ef8  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x180011efd  xor     r8d, r8d; cbBufSize
0x180011f00  xor     edx, edx; lpServiceConfig
0x180011f02  mov     rcx, rdi; hService
0x180011f05  call    cs:__imp_QueryServiceConfigW
0x180011f0b  mov     esi, eax
0x180011f0d  call    cs:__imp_GetLastError
0x180011f13  mov     r9d, eax
0x180011f16  test    esi, esi
0x180011f18  jnz     loc_18001202F
0x180011f1e  cmp     eax, 7Ah ; 'z'
0x180011f21  jnz     loc_18001202F
0x180011f27  mov     ecx, [rsp+98h+pcbBytesNeeded]; unsigned __int64
0x180011f2b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011f30  mov     rsi, rax
0x180011f33  mov     [rsp+98h+var_60], rax
0x180011f38  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x180011f3d  mov     r8d, [rsp+98h+pcbBytesNeeded]; cbBufSize
0x180011f42  mov     rdx, rax; lpServiceConfig
0x180011f45  mov     rcx, rdi; hService
0x180011f48  call    cs:__imp_QueryServiceConfigW
0x180011f4e  test    eax, eax
0x180011f50  jnz     short loc_180011F96
0x180011f52  lea     rax, WPP_GLOBAL_Control
0x180011f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f60  cmp     rcx, rax
0x180011f63  jz      short loc_180011F96
0x180011f65  test    byte ptr [rcx+0BCh], 1
0x180011f6c  jz      short loc_180011F96
0x180011f6e  call    cs:__imp_GetLastError
0x180011f74  mov     edx, 33h ; '3'
0x180011f79  mov     r9d, eax
0x180011f7c  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f8a  mov     rcx, [rcx+0B0h]
0x180011f91  call    WPP_SF_d
0x180011f96  mov     rbp, [rsi+30h]
0x180011f9a  test    rbp, rbp
0x180011f9d  jz      short loc_180011FD6
0x180011f9f  lea     rdx, aLocalsystem; "LocalSystem"
0x180011fa6  mov     rcx, rbp; String1
0x180011fa9  call    cs:__imp__wcsicmp
0x180011faf  test    eax, eax
0x180011fb1  jz      short loc_180011FD6
0x180011fb3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011fb7  inc     r9
0x180011fba  cmp     [rbp+r9*2+0], r14w
0x180011fc0  jnz     short loc_180011FB7
0x180011fc2  mov     r8, r9
0x180011fc5  mov     rdx, rbp
0x180011fc8  lea     rcx, ?g_pwzLocalMsmqAccount@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@A; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> g_pwzLocalMsmqAccount
0x180011fcf  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(wchar_t const *,unsigned __int64)
0x180011fd4  jmp     short loc_18001200F
0x180011fd6  mov     rdx, cs:?g_pSystemSid@@3PEAXEA; void * g_pSystemSid
0x180011fdd  lea     rcx, [rsp+98h+var_58]
0x180011fe2  call    ?_BuildAccountNameForSid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAX@Z; _BuildAccountNameForSid(void *)
0x180011fe7  nop
0x180011fe8  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011fec  xor     r8d, r8d
0x180011fef  mov     rdx, rax
0x180011ff2  lea     rcx, ?g_pwzLocalMsmqAccount@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@A; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> g_pwzLocalMsmqAccount
0x180011ff9  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)
0x180011ffe  nop
0x180011fff  xor     r8d, r8d
0x180012002  mov     dl, 1
0x180012004  lea     rcx, [rsp+98h+var_58]
0x180012009  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18001200e  nop
0x18001200f  mov     rcx, rsi; Block
0x180012012  call    cs:__imp_free
0x180012018  nop
0x180012019  mov     rcx, rdi; hSCObject
0x18001201c  call    cs:__imp_CloseServiceHandle
0x180012022  nop
0x180012023  mov     rcx, rbx; hSCObject
0x180012026  call    cs:__imp_CloseServiceHandle
0x18001202c  nop
0x18001202d  jmp     short loc_180012078
0x18001202f  lea     rax, WPP_GLOBAL_Control
0x180012036  mov     rcx, cs:WPP_GLOBAL_Control
0x18001203d  cmp     rcx, rax
0x180012040  jz      short loc_180012064
0x180012042  test    byte ptr [rcx+0BCh], 1
0x180012049  jz      short loc_180012064
0x18001204b  mov     edx, 32h ; '2'
0x180012050  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180012057  mov     rcx, [rcx+0B0h]
0x18001205e  call    WPP_SF_d
0x180012063  nop
0x180012064  mov     rcx, rdi; hSCObject
0x180012067  call    cs:__imp_CloseServiceHandle
0x18001206d  nop
0x18001206e  mov     rcx, rbx; hSCObject
0x180012071  call    cs:__imp_CloseServiceHandle
0x180012077  nop
0x180012078  mov     rcx, [rsp+98h+var_30]
0x18001207d  xor     rcx, rsp; StackCookie
0x180012080  call    __security_check_cookie
0x180012085  add     rsp, 70h
0x180012089  pop     r14
0x18001208b  pop     rdi
0x18001208c  pop     rsi
0x18001208d  pop     rbp
0x18001208e  pop     rbx
0x18001208f  retn
```
