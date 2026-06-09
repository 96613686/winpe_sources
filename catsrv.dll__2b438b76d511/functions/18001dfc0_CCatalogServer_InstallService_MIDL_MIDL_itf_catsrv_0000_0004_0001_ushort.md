# CCatalogServer::InstallService(__MIDL___MIDL_itf_catsrv_0000_0004_0001,ushort *)

- ea: `0x18001dfc0`
- end: `0x18001e435`
- name: `?InstallService@CCatalogServer@@UEAAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@PEAG@Z`
- size: `1141`
- prototype: `int __high(enum __MIDL___MIDL_itf_catsrv_0000_0004_0001, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000a01c`
- `0x18001dfc0`
- `0x18001e744`
- `0x18001ec1c`
- `0x18001f0b4`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e078`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e31a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e31a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e228`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e228`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e200`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e20e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e200`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e20e`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18001e2fa`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18001e2fa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e16e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e16e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e358`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e358`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001e3fb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001e3fb`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001e3d9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001e3d9`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001e3a2`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001e3a2`

## pseudocode

```c
__int64 __fastcall CCatalogServer::InstallService(__int64 *a1, int a2, __int64 a3)
{
  __int64 v3; // r14
  unsigned __int64 v4; // rax
  unsigned int LoadBalancingIfNeeded; // ebx
  __int64 v7; // rsi
  UINT v8; // edx
  unsigned __int16 **v10; // r11
  int v11; // r12d
  __int64 v12; // rax
  SC_HANDLE v13; // rax
  signed int LastError; // eax
  SC_HANDLE ServiceW; // rdi
  int v16; // eax
  WCHAR *lpLoadOrderGroup; // r11
  SC_HANDLE v18; // r15
  __int64 (*v19)(void); // rax
  int v20; // eax
  signed int v21; // eax
  DWORD v22; // r14d
  SC_HANDLE hSCObject; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwStartType; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 *v26; // [rsp+80h] [rbp-80h]
  LPCWSTR lpServiceName; // [rsp+88h] [rbp-78h]
  _SERVICE_STATUS ServiceStatus; // [rsp+90h] [rbp-70h] BYREF
  WCHAR BinaryPathName[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = a2;
  LODWORD(hSCObject) = 0;
  v4 = -1;
  v25 = 4;
  do
    ++v4;
  while ( *(_WORD *)(a3 + 2 * v4) );
  if ( v4 < 0x104 && a2 == 1 )
  {
    LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(1);
    if ( (LoadBalancingIfNeeded & 0x80000000) == 0 )
    {
      v7 = 10 * v3;
      v8 = *((_DWORD *)&csServices + 20 * v3 - 18);
      lpServiceName = (&csServices)[10 * v3 - 5];
      if ( v8 )
      {
        if ( !LoadStringW(hInstance, v8, Buffer, 260) )
          return 2147549183LL;
        v10 = &csServices;
      }
      else
      {
        LoadBalancingIfNeeded = StringCchCopyW(Buffer, 0x104u, (&csServices)[10 * v3 - 4]);
        if ( (LoadBalancingIfNeeded & 0x80000000) != 0 )
          return LoadBalancingIfNeeded;
      }
      v26 = v10[10 * v3 - 7];
      dwStartType = (DWORD)v10[10 * v3 - 4];
      if ( (int)utIsServiceInstalled(1, &hSCObject, &v25) >= 0 )
      {
        v11 = (int)hSCObject;
        if ( (_DWORD)hSCObject && v25 == dwStartType )
        {
          v12 = *a1;
          LoadBalancingIfNeeded = 0;
          LODWORD(hSCObject) = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64, SC_HANDLE *))(v12 + 64))(a1, 1, &hSCObject) >= 0
            && ((unsigned int)hSCObject & 0xFFFFFFFD) != 0 )
          {
            if ( *((_DWORD *)&csServices + 20 * v3 - 9) )
              (*(void (__fastcall **)(__int64 *, __int64))(*a1 + 72))(a1, 1);
          }
          else if ( *((_DWORD *)&csServices + 20 * v3 - 2) )
          {
            (*(void (__fastcall **)(__int64 *, __int64))(*a1 + 24))(a1, 1);
          }
          return LoadBalancingIfNeeded;
        }
        v13 = OpenSCManagerW(0, 0, 0xF003Fu);
        hSCObject = v13;
        if ( !v13 )
        {
          LastError = GetLastError();
          LoadBalancingIfNeeded = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return LoadBalancingIfNeeded;
        }
        ServiceW = 0;
        if ( !v11 )
        {
          v16 = StringCchCopyW(BinaryPathName, 0x104u, v26);
          LoadBalancingIfNeeded = v16;
          if ( v16 < 0
            || (v19 = (__int64 (*)(void))*(&csServices + 10 * v3 - 3)) != 0
            && (v20 = v19(), lpLoadOrderGroup = 0, LoadBalancingIfNeeded = v20, v20 < 0) )
          {
            v18 = hSCObject;
            goto LABEL_27;
          }
          v18 = hSCObject;
          ServiceW = CreateServiceW(
                       hSCObject,
                       lpServiceName,
                       Buffer,
                       0xF01FFu,
                       *((_DWORD *)&csServices + 20 * v3 - 11),
                       dwStartType,
                       1u,
                       BinaryPathName,
                       lpLoadOrderGroup,
                       (LPDWORD)lpLoadOrderGroup,
                       lpLoadOrderGroup,
                       lpLoadOrderGroup,
                       lpLoadOrderGroup);
          if ( ServiceW )
          {
            if ( !*((_DWORD *)&csServices + 20 * v3 - 2) )
              goto LABEL_27;
            goto LABEL_44;
          }
LABEL_36:
          v21 = GetLastError();
          LoadBalancingIfNeeded = v21;
          if ( v21 > 0 )
            LoadBalancingIfNeeded = (unsigned __int16)v21 | 0x80070000;
          goto LABEL_27;
        }
        v22 = dwStartType;
        v18 = v13;
        if ( v25 != dwStartType )
        {
          ServiceW = OpenServiceW(v13, lpServiceName, 0xF01FFu);
          if ( ServiceW )
          {
            if ( !ChangeServiceConfigW(ServiceW, 0xFFFFFFFF, v22, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, Buffer) )
              goto LABEL_36;
            if ( *((_DWORD *)&csServices + 2 * v7 - 2) )
            {
              memset(&ServiceStatus, 0, sizeof(ServiceStatus));
              if ( !ControlService(ServiceW, 4u, &ServiceStatus)
                || ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) == 0 )
              {
LABEL_44:
                StartServiceW(ServiceW, 0, 0);
              }
            }
          }
        }
LABEL_27:
        CloseServiceHandle(v18);
        if ( ServiceW )
          CloseServiceHandle(ServiceW);
      }
    }
    return LoadBalancingIfNeeded;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001dfc0  mov     [rsp-8+arg_18], rbx
0x18001dfc5  push    rbp
0x18001dfc6  push    rsi
0x18001dfc7  push    rdi
0x18001dfc8  push    r12
0x18001dfca  push    r13
0x18001dfcc  push    r14
0x18001dfce  push    r15
0x18001dfd0  lea     rbp, [rsp-3E0h]
0x18001dfd8  sub     rsp, 4E0h
0x18001dfdf  mov     rax, cs:__security_cookie
0x18001dfe6  xor     rax, rsp
0x18001dfe9  mov     [rbp+410h+var_40], rax
0x18001dff0  xor     r12d, r12d
0x18001dff3  movsxd  r14, edx
0x18001dff6  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001dffa  mov     dword ptr [rsp+510h+hSCObject], r12d
0x18001dfff  mov     rax, r15
0x18001e002  mov     [rsp+510h+var_494], 4
0x18001e00a  mov     r13, r8
0x18001e00d  mov     rdi, rcx
0x18001e010  inc     rax
0x18001e013  cmp     [r8+rax*2], r12w
0x18001e018  jnz     short loc_18001E010
0x18001e01a  cmp     rax, 104h
0x18001e020  jnb     loc_18001E406
0x18001e026  lea     eax, [r14-1]
0x18001e02a  test    eax, eax
0x18001e02c  jnz     loc_18001E406
0x18001e032  mov     ecx, r14d
0x18001e035  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001e03a  mov     ebx, eax
0x18001e03c  test    eax, eax
0x18001e03e  js      loc_18001E214
0x18001e044  lea     r11, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e04b  lea     rsi, [r14+r14*4]
0x18001e04f  add     rsi, rsi
0x18001e052  mov     rax, [r11+rsi*8-50h]
0x18001e057  mov     edx, [r11+rsi*8-48h]; uID
0x18001e05c  mov     [rbp+410h+lpServiceName], rax
0x18001e060  test    edx, edx
0x18001e062  jz      short loc_18001E08C
0x18001e064  mov     rcx, cs:hInstance; hInstance
0x18001e06b  lea     r8, [rbp+410h+Buffer]; lpBuffer
0x18001e072  mov     r9d, 104h; cchBufferMax
0x18001e078  call    cs:__imp_LoadStringW
0x18001e07e  test    eax, eax
0x18001e080  jnz     short loc_18001E0AE
0x18001e082  mov     eax, 8000FFFFh
0x18001e087  jmp     loc_18001E40B
0x18001e08c  mov     r8, [r11+rsi*8-40h]; unsigned __int16 *
0x18001e091  lea     rcx, [rbp+410h+Buffer]; unsigned __int16 *
0x18001e098  mov     edx, 104h; unsigned __int64
0x18001e09d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e0a2  mov     ebx, eax
0x18001e0a4  test    eax, eax
0x18001e0a6  js      loc_18001E214
0x18001e0ac  jmp     short loc_18001E0B5
0x18001e0ae  lea     r11, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e0b5  mov     rax, [r11+rsi*8-38h]
0x18001e0ba  lea     r8, [rsp+510h+var_494]
0x18001e0bf  mov     [rbp+410h+var_490], rax
0x18001e0c3  lea     rdx, [rsp+510h+hSCObject]
0x18001e0c8  mov     eax, [r11+rsi*8-20h]
0x18001e0cd  mov     ecx, r14d
0x18001e0d0  mov     [rsp+510h+var_498], eax
0x18001e0d4  call    ?utIsServiceInstalled@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@PEAK1@Z; utIsServiceInstalled(__MIDL___MIDL_itf_catsrv_0000_0004_0001,ulong *,ulong *)
0x18001e0d9  test    eax, eax
0x18001e0db  js      loc_18001E214
0x18001e0e1  mov     r12d, dword ptr [rsp+510h+hSCObject]
0x18001e0e6  test    r12d, r12d
0x18001e0e9  jz      short loc_18001E164
0x18001e0eb  mov     eax, [rsp+510h+var_498]
0x18001e0ef  cmp     [rsp+510h+var_494], eax
0x18001e0f3  jnz     short loc_18001E164
0x18001e0f5  mov     rax, [rdi]
0x18001e0f8  lea     r8, [rsp+510h+hSCObject]
0x18001e0fd  xor     ebx, ebx
0x18001e0ff  mov     edx, r14d
0x18001e102  mov     rcx, rdi
0x18001e105  mov     dword ptr [rsp+510h+hSCObject], ebx
0x18001e109  mov     rax, [rax+40h]
0x18001e10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e112  test    eax, eax
0x18001e114  js      short loc_18001E13B
0x18001e116  test    dword ptr [rsp+510h+hSCObject], 0FFFFFFFDh
0x18001e11e  jz      short loc_18001E13B
0x18001e120  lea     r12, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e127  cmp     [r12+rsi*8-24h], ebx
0x18001e12c  jz      loc_18001E214
0x18001e132  mov     rax, [rdi]
0x18001e135  mov     rax, [rax+48h]
0x18001e139  jmp     short loc_18001E154
0x18001e13b  lea     r12, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e142  cmp     [r12+rsi*8-8], ebx
0x18001e147  jz      loc_18001E214
0x18001e14d  mov     rax, [rdi]
0x18001e150  mov     rax, [rax+18h]
0x18001e154  mov     edx, r14d
0x18001e157  mov     rcx, rdi
0x18001e15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e15f  jmp     loc_18001E214
0x18001e164  xor     edx, edx; lpDatabaseName
0x18001e166  xor     ecx, ecx; lpMachineName
0x18001e168  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001e16e  call    cs:__imp_OpenSCManagerW
0x18001e174  xor     r11d, r11d
0x18001e177  mov     [rsp+510h+hSCObject], rax
0x18001e17c  test    rax, rax
0x18001e17f  jnz     short loc_18001E19C
0x18001e181  call    cs:__imp_GetLastError
0x18001e187  mov     ebx, eax
0x18001e189  test    eax, eax
0x18001e18b  jle     loc_18001E214
0x18001e191  movzx   ebx, ax
0x18001e194  or      ebx, 80070000h
0x18001e19a  jmp     short loc_18001E214
0x18001e19c  mov     rdi, r11
0x18001e19f  test    r12d, r12d
0x18001e1a2  jnz     loc_18001E338
0x18001e1a8  cmp     r14d, 1
0x18001e1ac  jnz     short loc_18001E1C5
0x18001e1ae  mov     r8, [rbp+410h+var_490]; unsigned __int16 *
0x18001e1b2  lea     rcx, [rbp+410h+BinaryPathName]; unsigned __int16 *
0x18001e1b6  mov     edx, 104h; unsigned __int64
0x18001e1bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e1c0  jmp     loc_18001E279
0x18001e1c5  test    r13, r13
0x18001e1c8  jz      short loc_18001E21B
0x18001e1ca  mov     rax, r15
0x18001e1cd  inc     rax
0x18001e1d0  cmp     [r13+rax*2+0], r11w
0x18001e1d6  jnz     short loc_18001E1CD
0x18001e1d8  test    rax, rax
0x18001e1db  jz      short loc_18001E21B
0x18001e1dd  mov     r14d, 104h
0x18001e1e3  lea     rcx, [rbp+410h+BinaryPathName]; unsigned __int16 *
0x18001e1e7  mov     edx, r14d; unsigned __int64
0x18001e1ea  mov     r8, r13; unsigned __int16 *
0x18001e1ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e1f2  mov     ebx, eax
0x18001e1f4  test    eax, eax
0x18001e1f6  jns     short loc_18001E231
0x18001e1f8  mov     r15, [rsp+510h+hSCObject]
0x18001e1fd  mov     rcx, r15; hSCObject
0x18001e200  call    cs:__imp_CloseServiceHandle
0x18001e206  test    rdi, rdi
0x18001e209  jz      short loc_18001E214
0x18001e20b  mov     rcx, rdi; hSCObject
0x18001e20e  call    cs:__imp_CloseServiceHandle
0x18001e214  mov     eax, ebx
0x18001e216  jmp     loc_18001E40B
0x18001e21b  mov     r14d, 104h
0x18001e221  lea     rcx, [rbp+410h+BinaryPathName]; lpBuffer
0x18001e225  mov     edx, r14d; uSize
0x18001e228  call    cs:__imp_GetSystemDirectoryW
0x18001e22e  xor     r11d, r11d
0x18001e231  lea     rax, [rbp+410h+BinaryPathName]
0x18001e235  inc     r15
0x18001e238  cmp     [rax+r15*2], r11w
0x18001e23d  jnz     short loc_18001E235
0x18001e23f  test    r15, r15
0x18001e242  jz      short loc_18001E283
0x18001e244  cmp     [rbp+r15*2+410h+var_462], 5Ch ; '\'
0x18001e24b  jz      short loc_18001E283
0x18001e24d  lea     r8, asc_18005D30C; "\\"
0x18001e254  mov     rdx, r14; unsigned __int64
0x18001e257  lea     rcx, [rbp+410h+BinaryPathName]; unsigned __int16 *
0x18001e25b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e260  mov     ebx, eax
0x18001e262  test    eax, eax
0x18001e264  js      short loc_18001E1F8
0x18001e266  mov     r8, [rbp+410h+var_490]; unsigned __int16 *
0x18001e26a  lea     rcx, [rbp+410h+BinaryPathName]; unsigned __int16 *
0x18001e26e  mov     rdx, r14; unsigned __int64
0x18001e271  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e276  xor     r11d, r11d
0x18001e279  mov     ebx, eax
0x18001e27b  test    eax, eax
0x18001e27d  js      loc_18001E1F8
0x18001e283  lea     r12, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e28a  mov     rax, [r12+rsi*8-18h]
0x18001e28f  test    rax, rax
0x18001e292  jz      short loc_18001E2A6
0x18001e294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e299  xor     r11d, r11d
0x18001e29c  mov     ebx, eax
0x18001e29e  test    eax, eax
0x18001e2a0  js      loc_18001E1F8
0x18001e2a6  mov     r15, [rsp+510h+hSCObject]
0x18001e2ab  lea     rax, [rbp+410h+BinaryPathName]
0x18001e2af  mov     rdx, [rbp+410h+lpServiceName]; lpServiceName
0x18001e2b3  lea     r8, [rbp+410h+Buffer]; lpDisplayName
0x18001e2ba  mov     [rsp+510h+lpPassword], r11; lpPassword
0x18001e2bf  mov     r9d, 0F01FFh; dwDesiredAccess
0x18001e2c5  mov     [rsp+510h+lpServiceStartName], r11; lpServiceStartName
0x18001e2ca  mov     rcx, r15; hSCManager
0x18001e2cd  mov     [rsp+510h+lpDependencies], r11; lpDependencies
0x18001e2d2  mov     [rsp+510h+lpdwTagId], r11; lpdwTagId
0x18001e2d7  mov     [rsp+510h+lpLoadOrderGroup], r11; lpLoadOrderGroup
0x18001e2dc  mov     [rsp+510h+lpBinaryPathName], rax; lpBinaryPathName
0x18001e2e1  mov     eax, [rsp+510h+var_498]
0x18001e2e5  mov     [rsp+510h+dwErrorControl], 1; dwErrorControl
0x18001e2ed  mov     [rsp+510h+dwStartType], eax; dwStartType
0x18001e2f1  mov     eax, [r12+rsi*8-2Ch]
0x18001e2f6  mov     [rsp+510h+dwServiceType], eax; dwServiceType
0x18001e2fa  call    cs:__imp_CreateServiceW
0x18001e300  mov     rdi, rax
0x18001e303  xor     eax, eax
0x18001e305  test    rdi, rdi
0x18001e308  jz      short loc_18001E31A
0x18001e30a  cmp     [r12+rsi*8-8], eax
0x18001e30f  jz      loc_18001E1FD
0x18001e315  jmp     loc_18001E3F3
0x18001e31a  call    cs:__imp_GetLastError
0x18001e320  mov     ebx, eax
0x18001e322  test    eax, eax
0x18001e324  jle     loc_18001E1FD
0x18001e32a  movzx   ebx, ax
0x18001e32d  or      ebx, 80070000h
0x18001e333  jmp     loc_18001E1FD
0x18001e338  mov     r14d, [rsp+510h+var_498]
0x18001e33d  mov     r15, rax
0x18001e340  cmp     [rsp+510h+var_494], r14d
0x18001e345  jz      loc_18001E1FD
0x18001e34b  mov     rdx, [rbp+410h+lpServiceName]; lpServiceName
0x18001e34f  mov     r8d, 0F01FFh; dwDesiredAccess
0x18001e355  mov     rcx, rax; hSCManager
0x18001e358  call    cs:__imp_OpenServiceW
0x18001e35e  xor     ecx, ecx
0x18001e360  mov     rdi, rax
0x18001e363  test    rax, rax
0x18001e366  jz      loc_18001E1FD
0x18001e36c  lea     rax, [rbp+410h+Buffer]
0x18001e373  or      edx, 0FFFFFFFFh; dwServiceType
0x18001e376  mov     [rsp+510h+lpDependencies], rax; lpDisplayName
0x18001e37b  mov     r9d, edx; dwErrorControl
0x18001e37e  mov     [rsp+510h+lpdwTagId], rcx; lpPassword
0x18001e383  mov     r8d, r14d; dwStartType
0x18001e386  mov     [rsp+510h+lpLoadOrderGroup], rcx; lpServiceStartName
0x18001e38b  mov     [rsp+510h+lpBinaryPathName], rcx; lpDependencies
0x18001e390  mov     qword ptr [rsp+510h+dwErrorControl], rcx; lpdwTagId
0x18001e395  mov     qword ptr [rsp+510h+dwStartType], rcx; lpLoadOrderGroup
0x18001e39a  mov     qword ptr [rsp+510h+dwServiceType], rcx; lpBinaryPathName
0x18001e39f  mov     rcx, rdi; hService
0x18001e3a2  call    cs:__imp_ChangeServiceConfigW
0x18001e3a8  xor     ecx, ecx
0x18001e3aa  test    eax, eax
0x18001e3ac  jz      loc_18001E31A
0x18001e3b2  lea     r12, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e3b9  cmp     [r12+rsi*8-8], ecx
0x18001e3be  jz      loc_18001E1FD
0x18001e3c4  xorps   xmm0, xmm0
0x18001e3c7  lea     edx, [rcx+4]; dwControl
0x18001e3ca  movups  xmmword ptr [rbp+410h+ServiceStatus.dwServiceType], xmm0
0x18001e3ce  lea     r8, [rbp+410h+ServiceStatus]; lpServiceStatus
0x18001e3d2  mov     rcx, rdi; hService
0x18001e3d5  movups  xmmword ptr [rbp+410h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001e3d9  call    cs:__imp_ControlService
0x18001e3df  test    eax, eax
0x18001e3e1  jz      short loc_18001E3F3
0x18001e3e3  mov     eax, [rbp+410h+ServiceStatus.dwCurrentState]
0x18001e3e6  dec     eax
0x18001e3e8  test    eax, 0FFFFFFFDh
0x18001e3ed  jnz     loc_18001E1FD
0x18001e3f3  xor     r8d, r8d; lpServiceArgVectors
0x18001e3f6  xor     edx, edx; dwNumServiceArgs
0x18001e3f8  mov     rcx, rdi; hService
0x18001e3fb  call    cs:__imp_StartServiceW
0x18001e401  jmp     loc_18001E1FD
0x18001e406  mov     eax, 80070057h
0x18001e40b  mov     rcx, [rbp+410h+var_40]
0x18001e412  xor     rcx, rsp; StackCookie
0x18001e415  call    __security_check_cookie
0x18001e41a  mov     rbx, [rsp+510h+arg_18]
0x18001e422  add     rsp, 4E0h
0x18001e429  pop     r15
0x18001e42b  pop     r14
0x18001e42d  pop     r13
0x18001e42f  pop     r12
0x18001e431  pop     rdi
0x18001e432  pop     rsi
0x18001e433  pop     rbp
0x18001e434  retn
```
