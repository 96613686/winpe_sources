# InstallHidserv

- ea: `0x1800020b0`
- end: `0x18000222f`
- name: `InstallHidserv`
- size: `383`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800020b0`
- `0x1800025b8`
- `0x18000841e`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180002206`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180002206`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800020e8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800021f0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800020e8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800021f0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800020c9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800021d2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800020c9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800021d2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002190`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000220f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002218`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002190`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000220f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002218`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180002160`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180002160`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180002183`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180002183`

## string_xrefs

- `0x18000210a`: `HID Input Service`

## pseudocode

```c
int InstallHidserv()
{
  SC_HANDLE v0; // rax
  __int64 v1; // r9
  SC_HANDLE v2; // rbx
  bool i; // zf
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  DWORD pcbBytesNeeded[4]; // [rsp+60h] [rbp-58h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+70h] [rbp-48h] BYREF

  v0 = OpenSCManagerW(0, 0, 2u);
  if ( v0 )
  {
    v2 = OpenServiceW(v0, HidservServiceName, 0xF01FFu);
    if ( v2 )
    {
      memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
      pcbBytesNeeded[0] = 0;
      for ( i = !ChangeServiceConfigW(v2, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, HidservDisplayName);
            !i && QueryServiceConfigW(v2, &ServiceConfig, 0x40u, pcbBytesNeeded);
            i = ServiceConfig.dwStartType == 2 )
      {
        ;
      }
      CloseServiceHandle(v2);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids, v1);
  }
  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    v6 = OpenServiceW(v4, HidservServiceName, 0x10u);
    v7 = v6;
    if ( v6 )
    {
      StartServiceW(v6, 0, 0);
      CloseServiceHandle(v7);
    }
    LODWORD(v4) = CloseServiceHandle(v5);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x1800020b0  mov     [rsp+arg_0], rbx
0x1800020b5  push    rdi
0x1800020b6  sub     rsp, 0B0h
0x1800020bd  mov     edi, 2
0x1800020c2  xor     edx, edx; lpDatabaseName
0x1800020c4  mov     r8d, edi; dwDesiredAccess
0x1800020c7  xor     ecx, ecx; lpMachineName
0x1800020c9  call    cs:__imp_OpenSCManagerW
0x1800020cf  test    rax, rax
0x1800020d2  jz      loc_180002196
0x1800020d8  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800020de  lea     rdx, HidservServiceName; "HidServ"
0x1800020e5  mov     rcx, rax; hSCManager
0x1800020e8  call    cs:__imp_OpenServiceW
0x1800020ee  mov     rbx, rax
0x1800020f1  test    rax, rax
0x1800020f4  jz      loc_180002196
0x1800020fa  xor     edx, edx; Val
0x1800020fc  lea     r8d, [rdi+3Eh]; Size
0x180002100  lea     rcx, [rsp+0B8h+ServiceConfig]; void *
0x180002105  call    memset_0
0x18000210a  lea     rax, HidservDisplayName; "HID Input Service"
0x180002111  mov     [rsp+0B8h+pcbBytesNeeded], 0
0x180002119  mov     [rsp+0B8h+lpDisplayName], rax; lpDisplayName
0x18000211e  or      edx, 0FFFFFFFFh; dwServiceType
0x180002121  mov     [rsp+0B8h+lpPassword], 0; lpPassword
0x18000212a  mov     r9d, edx; dwErrorControl
0x18000212d  mov     [rsp+0B8h+lpServiceStartName], 0; lpServiceStartName
0x180002136  mov     r8d, edi; dwStartType
0x180002139  mov     [rsp+0B8h+lpDependencies], 0; lpDependencies
0x180002142  mov     rcx, rbx; hService
0x180002145  mov     [rsp+0B8h+lpdwTagId], 0; lpdwTagId
0x18000214e  mov     [rsp+0B8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180002157  mov     [rsp+0B8h+lpBinaryPathName], 0; lpBinaryPathName
0x180002160  call    cs:__imp_ChangeServiceConfigW
0x180002166  test    eax, eax
0x180002168  jmp     short loc_18000216E
0x18000216a  cmp     [rsp+0B8h+ServiceConfig.dwStartType], edi
0x18000216e  jz      short loc_18000218D
0x180002170  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x180002175  mov     r8d, 40h ; '@'; cbBufSize
0x18000217b  lea     rdx, [rsp+0B8h+ServiceConfig]; lpServiceConfig
0x180002180  mov     rcx, rbx; hService
0x180002183  call    cs:__imp_QueryServiceConfigW
0x180002189  test    eax, eax
0x18000218b  jnz     short loc_18000216A
0x18000218d  mov     rcx, rbx; hSCObject
0x180002190  call    cs:__imp_CloseServiceHandle
0x180002196  mov     rcx, cs:WPP_GLOBAL_Control
0x18000219d  lea     rax, WPP_GLOBAL_Control
0x1800021a4  cmp     rcx, rax
0x1800021a7  jz      short loc_1800021CA
0x1800021a9  test    byte ptr [rcx+1Ch], 1
0x1800021ad  jz      short loc_1800021CA
0x1800021af  cmp     byte ptr [rcx+19h], 5
0x1800021b3  jb      short loc_1800021CA
0x1800021b5  mov     rcx, [rcx+10h]
0x1800021b9  lea     r8, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids
0x1800021c0  mov     edx, 0Ah
0x1800021c5  call    WPP_SF_
0x1800021ca  xor     edx, edx; lpDatabaseName
0x1800021cc  xor     ecx, ecx; lpMachineName
0x1800021ce  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800021d2  call    cs:__imp_OpenSCManagerW
0x1800021d8  mov     rbx, rax
0x1800021db  test    rax, rax
0x1800021de  jz      short loc_18000221E
0x1800021e0  mov     r8d, 10h; dwDesiredAccess
0x1800021e6  lea     rdx, HidservServiceName; "HidServ"
0x1800021ed  mov     rcx, rax; hSCManager
0x1800021f0  call    cs:__imp_OpenServiceW
0x1800021f6  mov     rdi, rax
0x1800021f9  test    rax, rax
0x1800021fc  jz      short loc_180002215
0x1800021fe  xor     r8d, r8d; lpServiceArgVectors
0x180002201  xor     edx, edx; dwNumServiceArgs
0x180002203  mov     rcx, rax; hService
0x180002206  call    cs:__imp_StartServiceW
0x18000220c  mov     rcx, rdi; hSCObject
0x18000220f  call    cs:__imp_CloseServiceHandle
0x180002215  mov     rcx, rbx; hSCObject
0x180002218  call    cs:__imp_CloseServiceHandle
0x18000221e  mov     rbx, [rsp+0B8h+arg_0]
0x180002226  add     rsp, 0B0h
0x18000222d  pop     rdi
0x18000222e  retn
```
