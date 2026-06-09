# CLTApp::SetApplicationIdentities(void)

- ea: `0x180006d50`
- end: `0x180006edc`
- name: `?SetApplicationIdentities@CLTApp@@AEAAJXZ`
- size: `396`
- prototype: `__int64 __fastcall(CLTApp *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x180006d50`
- `0x18001933c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ec5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180006db6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180006db6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006e3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006e70`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006e7e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006e3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006e70`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006e7e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180006dd5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180006dd5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180006e2f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180006e2f`

## pseudocode

```c
__int64 __fastcall CLTApp::SetApplicationIdentities(CLTApp *this)
{
  __int64 v1; // rdi
  signed int SecurityAdmin; // ebx
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rsi
  struct ISecurityAdmin2 *v5; // r14
  SC_HANDLE v6; // rax
  signed int LastError; // eax
  signed int v9; // eax
  struct ISecurityAdmin2 *v10; // [rsp+80h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 7);
  SecurityAdmin = 0;
  v10 = 0;
  if ( !v1 )
    return (unsigned int)SecurityAdmin;
  v3 = 0;
  v4 = 0;
  SecurityAdmin = MyGetSecurityAdmin(&v10);
  if ( SecurityAdmin < 0 )
    return (unsigned int)SecurityAdmin;
  v5 = v10;
  while ( 1 )
  {
    if ( !v1 )
      goto LABEL_14;
    if ( !*(_DWORD *)v1 )
    {
      SecurityAdmin = (*(__int64 (__fastcall **)(struct ISecurityAdmin2 *, __int64, _QWORD, _QWORD))(*(_QWORD *)v5 + 56LL))(
                        v5,
                        v1 + 8,
                        *(_QWORD *)(v1 + 24),
                        *(_QWORD *)(v1 + 32));
      if ( SecurityAdmin < 0 )
        goto LABEL_14;
      goto LABEL_20;
    }
    if ( !v3 )
    {
      v3 = OpenSCManagerW(0, 0, 0x80000000);
      if ( !v3 )
        break;
    }
    v6 = OpenServiceW(v3, *(LPCWSTR *)(v1 + 8), 2u);
    v4 = v6;
    if ( v6 )
    {
      if ( !ChangeServiceConfigW(
              v6,
              0xFFFFFFFF,
              0xFFFFFFFF,
              0xFFFFFFFF,
              0,
              0,
              0,
              0,
              *(LPCWSTR *)(v1 + 24),
              *(LPCWSTR *)(v1 + 32),
              0) )
        goto LABEL_12;
      CloseServiceHandle(v4);
      v4 = 0;
    }
    else if ( GetLastError() != 1060 )
    {
LABEL_12:
      LastError = GetLastError();
      SecurityAdmin = LastError;
      if ( LastError > 0 )
        SecurityAdmin = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
      if ( v3 )
        CloseServiceHandle(v3);
      goto LABEL_16;
    }
LABEL_20:
    v1 = *(_QWORD *)(v1 + 40);
  }
  v9 = GetLastError();
  SecurityAdmin = v9;
  if ( v9 > 0 )
    SecurityAdmin = (unsigned __int16)v9 | 0x80070000;
LABEL_16:
  if ( v4 )
    CloseServiceHandle(v4);
  return (unsigned int)SecurityAdmin;
}

```

## disassembly

```asm
0x180006d50  mov     rax, rsp
0x180006d53  mov     [rax+10h], rbx
0x180006d57  mov     [rax+18h], rbp
0x180006d5b  push    rsi
0x180006d5c  push    rdi
0x180006d5d  push    r14
0x180006d5f  sub     rsp, 60h
0x180006d63  mov     rdi, [rcx+38h]
0x180006d67  xor     ebx, ebx
0x180006d69  mov     [rax+8], rbx
0x180006d6d  test    rdi, rdi
0x180006d70  jz      loc_180006E84
0x180006d76  lea     rcx, [rax+8]; struct ISecurityAdmin2 **
0x180006d7a  xor     ebp, ebp
0x180006d7c  xor     esi, esi
0x180006d7e  call    ?MyGetSecurityAdmin@@YAJPEAPEAUISecurityAdmin2@@@Z; MyGetSecurityAdmin(ISecurityAdmin2 * *)
0x180006d83  mov     ebx, eax
0x180006d85  test    eax, eax
0x180006d87  js      loc_180006E84
0x180006d8d  mov     r14, [rsp+78h+arg_0]
0x180006d95  test    rdi, rdi
0x180006d98  jz      loc_180006E68
0x180006d9e  cmp     dword ptr [rdi], 0
0x180006da1  jz      loc_180006E9B
0x180006da7  test    rbp, rbp
0x180006daa  jnz     short loc_180006DC8
0x180006dac  xor     edx, edx; lpDatabaseName
0x180006dae  xor     ecx, ecx; lpMachineName
0x180006db0  mov     r8d, 80000000h; dwDesiredAccess
0x180006db6  call    cs:__imp_OpenSCManagerW
0x180006dbc  mov     rbp, rax
0x180006dbf  test    rax, rax
0x180006dc2  jz      loc_180006EC5
0x180006dc8  mov     rdx, [rdi+8]; lpServiceName
0x180006dcc  mov     r8d, 2; dwDesiredAccess
0x180006dd2  mov     rcx, rbp; hSCManager
0x180006dd5  call    cs:__imp_OpenServiceW
0x180006ddb  mov     rsi, rax
0x180006dde  test    rax, rax
0x180006de1  jz      short loc_180006E46
0x180006de3  mov     rcx, [rdi+20h]
0x180006de7  or      r9d, 0FFFFFFFFh; dwErrorControl
0x180006deb  mov     [rsp+78h+lpDisplayName], 0; lpDisplayName
0x180006df4  or      r8d, r9d; dwStartType
0x180006df7  mov     [rsp+78h+lpPassword], rcx; lpPassword
0x180006dfc  or      edx, r9d; dwServiceType
0x180006dff  mov     rcx, [rdi+18h]
0x180006e03  mov     [rsp+78h+lpServiceStartName], rcx; lpServiceStartName
0x180006e08  mov     rcx, rax; hService
0x180006e0b  mov     [rsp+78h+lpDependencies], 0; lpDependencies
0x180006e14  mov     [rsp+78h+lpdwTagId], 0; lpdwTagId
0x180006e1d  mov     [rsp+78h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180006e26  mov     [rsp+78h+lpBinaryPathName], 0; lpBinaryPathName
0x180006e2f  call    cs:__imp_ChangeServiceConfigW
0x180006e35  test    eax, eax
0x180006e37  jz      short loc_180006E53
0x180006e39  mov     rcx, rsi; hSCObject
0x180006e3c  call    cs:__imp_CloseServiceHandle
0x180006e42  xor     esi, esi
0x180006e44  jmp     short loc_180006EBC
0x180006e46  call    cs:__imp_GetLastError
0x180006e4c  cmp     eax, 424h
0x180006e51  jz      short loc_180006EBC
0x180006e53  call    cs:__imp_GetLastError
0x180006e59  mov     ebx, eax
0x180006e5b  test    eax, eax
0x180006e5d  jle     short loc_180006E68
0x180006e5f  movzx   ebx, ax
0x180006e62  or      ebx, 80070000h
0x180006e68  test    rbp, rbp
0x180006e6b  jz      short loc_180006E76
0x180006e6d  mov     rcx, rbp; hSCObject
0x180006e70  call    cs:__imp_CloseServiceHandle
0x180006e76  test    rsi, rsi
0x180006e79  jz      short loc_180006E84
0x180006e7b  mov     rcx, rsi; hSCObject
0x180006e7e  call    cs:__imp_CloseServiceHandle
0x180006e84  lea     r11, [rsp+78h+var_18]
0x180006e89  mov     eax, ebx
0x180006e8b  mov     rbx, [r11+28h]
0x180006e8f  mov     rbp, [r11+30h]
0x180006e93  mov     rsp, r11
0x180006e96  pop     r14
0x180006e98  pop     rdi
0x180006e99  pop     rsi
0x180006e9a  retn
0x180006e9b  mov     rax, [r14]
0x180006e9e  lea     rdx, [rdi+8]
0x180006ea2  mov     r9, [rdi+20h]
0x180006ea6  mov     rcx, r14
0x180006ea9  mov     r8, [rdi+18h]
0x180006ead  mov     rax, [rax+38h]
0x180006eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb6  mov     ebx, eax
0x180006eb8  test    eax, eax
0x180006eba  js      short loc_180006E68
0x180006ebc  mov     rdi, [rdi+28h]
0x180006ec0  jmp     loc_180006D95
0x180006ec5  call    cs:__imp_GetLastError
0x180006ecb  mov     ebx, eax
0x180006ecd  test    eax, eax
0x180006ecf  jle     short loc_180006E76
0x180006ed1  movzx   ebx, ax
0x180006ed4  or      ebx, 80070000h
0x180006eda  jmp     short loc_180006E76
```
