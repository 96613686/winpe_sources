# ForceCryptServiceToStart

- ea: `0x18002dacc`
- end: `0x18002dc69`
- name: `ForceCryptServiceToStart`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwStartType)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002de54`

## callees

- `0x18002dacc`
- `0x18002e1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002db82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002db82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dbbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dbbe`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002db33`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002db33`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002dc16`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002dc16`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc36`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc3f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc36`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc3f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002db01`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002db01`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002dbf7`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002dbf7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002db69`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002dba6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002db69`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002dba6`

## pseudocode

```c
__int64 __fastcall ForceCryptServiceToStart(LPCWSTR lpServiceName, DWORD dwStartType)
{
  unsigned int v4; // r14d
  SC_HANDLE v5; // rax
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // r9d
  SC_HANDLE v9; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v11; // rax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r9d
  SC_HANDLE v15; // rdi
  struct _QUERY_SERVICE_CONFIGW *v16; // rax
  struct _QUERY_SERVICE_CONFIGW *v17; // rbp
  BOOL v18; // ebx
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  int lpBinaryPathName; // [rsp+20h] [rbp-68h]
  int lpLoadOrderGroup; // [rsp+28h] [rbp-60h]
  DWORD pcbBytesNeeded; // [rsp+A0h] [rbp+18h] BYREF

  pcbBytesNeeded = 0;
  v4 = 0;
  v5 = OpenSCManagerW(0, 0, 0xE0000000);
  v9 = v5;
  if ( v5 )
  {
    v11 = OpenServiceW(v5, lpServiceName, 0x13u);
    v15 = v11;
    if ( !v11 )
    {
      ErrLog_LogError(v13, v12, 0xC0u, v14, lpBinaryPathName, lpLoadOrderGroup);
      LastError = GetLastError();
LABEL_17:
      CloseServiceHandle(v9);
      goto LABEL_18;
    }
    if ( QueryServiceConfigW(v11, 0, 0, &pcbBytesNeeded) )
    {
      v16 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
      v17 = v16;
      if ( v16 )
      {
        v18 = !QueryServiceConfigW(v15, v16, pcbBytesNeeded, &pcbBytesNeeded);
        if ( v17->dwStartType == 4 )
          v18 = 1;
        LocalFree(v17);
        if ( !v18 )
          goto LABEL_21;
      }
    }
    if ( ChangeServiceConfigW(v15, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
LABEL_21:
      if ( StartServiceW(v15, 0, 0) )
      {
        v4 = 1;
        goto LABEL_16;
      }
      v22 = 259;
    }
    else
    {
      v22 = 250;
    }
    ErrLog_LogError(v20, v19, v22, v21, lpBinaryPathName, lpLoadOrderGroup);
LABEL_16:
    LastError = GetLastError();
    CloseServiceHandle(v15);
    goto LABEL_17;
  }
  ErrLog_LogError(v7, v6, 0xB6u, v8, lpBinaryPathName, lpLoadOrderGroup);
  LastError = GetLastError();
LABEL_18:
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x18002dacc  mov     rax, rsp
0x18002dacf  mov     [rax+8], rbx
0x18002dad3  mov     [rax+10h], rbp
0x18002dad7  mov     [rax+18h], r8d
0x18002dadb  push    rsi
0x18002dadc  push    rdi
0x18002dadd  push    r13
0x18002dadf  push    r14
0x18002dae1  push    r15
0x18002dae3  sub     rsp, 60h
0x18002dae7  mov     r15d, edx
0x18002daea  mov     dword ptr [rax+18h], 0
0x18002daf1  mov     rbx, rcx
0x18002daf4  xor     edx, edx; lpDatabaseName
0x18002daf6  xor     ecx, ecx; lpMachineName
0x18002daf8  mov     r8d, 0E0000000h; dwDesiredAccess
0x18002dafe  xor     r14d, r14d
0x18002db01  call    cs:__imp_OpenSCManagerW
0x18002db07  mov     rsi, rax
0x18002db0a  test    rax, rax
0x18002db0d  jnz     short loc_18002DB27
0x18002db0f  mov     r8d, 0B6h; unsigned int
0x18002db15  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002db1a  call    cs:__imp_GetLastError
0x18002db20  mov     ebx, eax
0x18002db22  jmp     loc_18002DC45
0x18002db27  mov     r8d, 13h; dwDesiredAccess
0x18002db2d  mov     rdx, rbx; lpServiceName
0x18002db30  mov     rcx, rsi; hSCManager
0x18002db33  call    cs:__imp_OpenServiceW
0x18002db39  mov     rdi, rax
0x18002db3c  test    rax, rax
0x18002db3f  jnz     short loc_18002DB59
0x18002db41  mov     r8d, 0C0h; unsigned int
0x18002db47  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002db4c  call    cs:__imp_GetLastError
0x18002db52  mov     ebx, eax
0x18002db54  jmp     loc_18002DC3C
0x18002db59  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18002db61  xor     r8d, r8d; cbBufSize
0x18002db64  xor     edx, edx; lpServiceConfig
0x18002db66  mov     rcx, rdi; hService
0x18002db69  call    cs:__imp_QueryServiceConfigW
0x18002db6f  mov     r13d, 1
0x18002db75  test    eax, eax
0x18002db77  jz      short loc_18002DBC8
0x18002db79  mov     edx, [rsp+88h+pcbBytesNeeded]; uBytes
0x18002db80  xor     ecx, ecx; uFlags
0x18002db82  call    cs:__imp_LocalAlloc
0x18002db88  mov     rbp, rax
0x18002db8b  test    rax, rax
0x18002db8e  jz      short loc_18002DBC8
0x18002db90  mov     r8d, [rsp+88h+pcbBytesNeeded]; cbBufSize
0x18002db98  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18002dba0  mov     rdx, rax; lpServiceConfig
0x18002dba3  mov     rcx, rdi; hService
0x18002dba6  call    cs:__imp_QueryServiceConfigW
0x18002dbac  xor     ebx, ebx
0x18002dbae  mov     rcx, rbp; hMem
0x18002dbb1  test    eax, eax
0x18002dbb3  setz    bl
0x18002dbb6  cmp     dword ptr [rbp+4], 4
0x18002dbba  cmovz   ebx, r13d
0x18002dbbe  call    cs:__imp_LocalFree
0x18002dbc4  test    ebx, ebx
0x18002dbc6  jz      short loc_18002DC0E
0x18002dbc8  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x18002dbcd  or      edx, 0FFFFFFFFh; dwServiceType
0x18002dbd0  mov     [rsp+88h+lpPassword], r14; lpPassword
0x18002dbd5  mov     r9d, edx; dwErrorControl
0x18002dbd8  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x18002dbdd  mov     r8d, r15d; dwStartType
0x18002dbe0  mov     [rsp+88h+lpDependencies], r14; lpDependencies
0x18002dbe5  mov     rcx, rdi; hService
0x18002dbe8  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x18002dbed  mov     [rsp+88h+lpLoadOrderGroup], r14; int
0x18002dbf2  mov     [rsp+88h+lpBinaryPathName], r14; int
0x18002dbf7  call    cs:__imp_ChangeServiceConfigW
0x18002dbfd  test    eax, eax
0x18002dbff  jnz     short loc_18002DC0E
0x18002dc01  mov     r8d, 0FAh; unsigned int
0x18002dc07  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002dc0c  jmp     short loc_18002DC2B
0x18002dc0e  xor     r8d, r8d; lpServiceArgVectors
0x18002dc11  xor     edx, edx; dwNumServiceArgs
0x18002dc13  mov     rcx, rdi; hService
0x18002dc16  call    cs:__imp_StartServiceW
0x18002dc1c  test    eax, eax
0x18002dc1e  jnz     short loc_18002DC28
0x18002dc20  mov     r8d, 103h
0x18002dc26  jmp     short loc_18002DC07
0x18002dc28  mov     r14d, r13d
0x18002dc2b  call    cs:__imp_GetLastError
0x18002dc31  mov     rcx, rdi; hSCObject
0x18002dc34  mov     ebx, eax
0x18002dc36  call    cs:__imp_CloseServiceHandle
0x18002dc3c  mov     rcx, rsi; hSCObject
0x18002dc3f  call    cs:__imp_CloseServiceHandle
0x18002dc45  mov     ecx, ebx; dwErrCode
0x18002dc47  call    cs:__imp_SetLastError
0x18002dc4d  lea     r11, [rsp+88h+var_28]
0x18002dc52  mov     eax, r14d
0x18002dc55  mov     rbx, [r11+30h]
0x18002dc59  mov     rbp, [r11+38h]
0x18002dc5d  mov     rsp, r11
0x18002dc60  pop     r15
0x18002dc62  pop     r14
0x18002dc64  pop     r13
0x18002dc66  pop     rdi
0x18002dc67  pop     rsi
0x18002dc68  retn
```
