# EnableServiceAutoStart(void)

- ea: `0x180007b34`
- end: `0x180007c2c`
- name: `?EnableServiceAutoStart@@YAXXZ`
- size: `248`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180007eb0`

## callees

- `0x180007b34`
- `0x180007c34`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180007c20`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180007c20`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180007bfa`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180007bfa`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180007bc4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180007bc4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180007b42`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180007b42`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180007b61`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180007b61`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void EnableServiceAutoStart(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  int Buffer; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcbBytesNeeded; // [rsp+78h] [rbp+10h] BYREF

  v0 = OpenSCManagerW(0, 0, 1u);
  if ( v0 )
  {
    v1 = OpenServiceW(v0, ServiceName, 7u);
    if ( IsServiceAutoStart(v1) || ChangeServiceConfigW(v1, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      Buffer = 0;
      pcbBytesNeeded = 0;
      if ( QueryServiceConfig2W(v1, 3u, (LPBYTE)&Buffer, 4u, &pcbBytesNeeded) )
      {
        if ( Buffer )
        {
          Buffer = 0;
          ChangeServiceConfig2W(v1, 3u, &Buffer);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180007b34  push    rbx
0x180007b36  sub     rsp, 60h
0x180007b3a  xor     edx, edx; lpDatabaseName
0x180007b3c  xor     ecx, ecx; lpMachineName
0x180007b3e  lea     r8d, [rdx+1]; dwDesiredAccess
0x180007b42  call    cs:__imp_OpenSCManagerW
0x180007b48  test    rax, rax
0x180007b4b  jz      loc_180007C26
0x180007b51  mov     r8d, 7; dwDesiredAccess
0x180007b57  lea     rdx, ServiceName; "EmbeddedMode"
0x180007b5e  mov     rcx, rax; hSCManager
0x180007b61  call    cs:__imp_OpenServiceW
0x180007b67  mov     rcx, rax; hService
0x180007b6a  mov     rbx, rax
0x180007b6d  call    ?IsServiceAutoStart@@YA_NPEAUSC_HANDLE__@@@Z; IsServiceAutoStart(SC_HANDLE__ *)
0x180007b72  test    al, al
0x180007b74  jnz     short loc_180007BCE
0x180007b76  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x180007b7f  or      edx, 0FFFFFFFFh; dwServiceType
0x180007b82  mov     [rsp+68h+lpPassword], 0; lpPassword
0x180007b8b  mov     r9d, edx; dwErrorControl
0x180007b8e  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x180007b97  mov     r8d, 2; dwStartType
0x180007b9d  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x180007ba6  mov     rcx, rbx; hService
0x180007ba9  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x180007bb2  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180007bbb  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x180007bc4  call    cs:__imp_ChangeServiceConfigW
0x180007bca  test    eax, eax
0x180007bcc  jz      short loc_180007C26
0x180007bce  mov     r9d, 4; cbBufSize
0x180007bd4  mov     [rsp+68h+Buffer], 0
0x180007bdc  lea     rax, [rsp+68h+pcbBytesNeeded]
0x180007be1  mov     [rsp+68h+pcbBytesNeeded], 0
0x180007be9  lea     r8, [rsp+68h+Buffer]; lpBuffer
0x180007bee  mov     [rsp+68h+lpBinaryPathName], rax; pcbBytesNeeded
0x180007bf3  mov     rcx, rbx; hService
0x180007bf6  lea     edx, [r9-1]; dwInfoLevel
0x180007bfa  call    cs:__imp_QueryServiceConfig2W
0x180007c00  test    eax, eax
0x180007c02  jz      short loc_180007C26
0x180007c04  cmp     [rsp+68h+Buffer], 0
0x180007c09  jz      short loc_180007C26
0x180007c0b  lea     r8, [rsp+68h+Buffer]; lpInfo
0x180007c10  mov     [rsp+68h+Buffer], 0
0x180007c18  mov     edx, 3; dwInfoLevel
0x180007c1d  mov     rcx, rbx; hService
0x180007c20  call    cs:__imp_ChangeServiceConfig2W
0x180007c26  add     rsp, 60h
0x180007c2a  pop     rbx
0x180007c2b  retn
```
