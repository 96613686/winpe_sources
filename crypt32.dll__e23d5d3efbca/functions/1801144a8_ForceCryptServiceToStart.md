# ForceCryptServiceToStart

- ea: `0x1801144a8`
- end: `0x180114645`
- name: `ForceCryptServiceToStart`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwStartType)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180057150`

## callees

- `0x1800bbe5c`
- `0x1801144a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801144f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801144f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180114623`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180114623`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011459a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011459a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011455e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011455e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801144dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801144dd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1801145f2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1801145f2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18011450f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18011450f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180114612`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18011461b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180114612`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18011461b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1801145d3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1801145d3`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180114545`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180114582`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180114545`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180114582`

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
0x1801144a8  mov     rax, rsp
0x1801144ab  mov     [rax+8], rbx
0x1801144af  mov     [rax+10h], rbp
0x1801144b3  mov     [rax+18h], r8d
0x1801144b7  push    rsi
0x1801144b8  push    rdi
0x1801144b9  push    r13
0x1801144bb  push    r14
0x1801144bd  push    r15
0x1801144bf  sub     rsp, 60h
0x1801144c3  mov     r15d, edx
0x1801144c6  mov     dword ptr [rax+18h], 0
0x1801144cd  mov     rbx, rcx
0x1801144d0  xor     edx, edx; lpDatabaseName
0x1801144d2  xor     ecx, ecx; lpMachineName
0x1801144d4  mov     r8d, 0E0000000h; dwDesiredAccess
0x1801144da  xor     r14d, r14d
0x1801144dd  call    cs:__imp_OpenSCManagerW
0x1801144e3  mov     rsi, rax
0x1801144e6  test    rax, rax
0x1801144e9  jnz     short loc_180114503
0x1801144eb  mov     r8d, 0B6h; unsigned int
0x1801144f1  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1801144f6  call    cs:__imp_GetLastError
0x1801144fc  mov     ebx, eax
0x1801144fe  jmp     loc_180114621
0x180114503  mov     r8d, 13h; dwDesiredAccess
0x180114509  mov     rdx, rbx; lpServiceName
0x18011450c  mov     rcx, rsi; hSCManager
0x18011450f  call    cs:__imp_OpenServiceW
0x180114515  mov     rdi, rax
0x180114518  test    rax, rax
0x18011451b  jnz     short loc_180114535
0x18011451d  mov     r8d, 0C0h; unsigned int
0x180114523  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180114528  call    cs:__imp_GetLastError
0x18011452e  mov     ebx, eax
0x180114530  jmp     loc_180114618
0x180114535  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18011453d  xor     r8d, r8d; cbBufSize
0x180114540  xor     edx, edx; lpServiceConfig
0x180114542  mov     rcx, rdi; hService
0x180114545  call    cs:__imp_QueryServiceConfigW
0x18011454b  mov     r13d, 1
0x180114551  test    eax, eax
0x180114553  jz      short loc_1801145A4
0x180114555  mov     edx, [rsp+88h+pcbBytesNeeded]; uBytes
0x18011455c  xor     ecx, ecx; uFlags
0x18011455e  call    cs:__imp_LocalAlloc
0x180114564  mov     rbp, rax
0x180114567  test    rax, rax
0x18011456a  jz      short loc_1801145A4
0x18011456c  mov     r8d, [rsp+88h+pcbBytesNeeded]; cbBufSize
0x180114574  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18011457c  mov     rdx, rax; lpServiceConfig
0x18011457f  mov     rcx, rdi; hService
0x180114582  call    cs:__imp_QueryServiceConfigW
0x180114588  xor     ebx, ebx
0x18011458a  mov     rcx, rbp; hMem
0x18011458d  test    eax, eax
0x18011458f  setz    bl
0x180114592  cmp     dword ptr [rbp+4], 4
0x180114596  cmovz   ebx, r13d
0x18011459a  call    cs:__imp_LocalFree
0x1801145a0  test    ebx, ebx
0x1801145a2  jz      short loc_1801145EA
0x1801145a4  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x1801145a9  or      edx, 0FFFFFFFFh; dwServiceType
0x1801145ac  mov     [rsp+88h+lpPassword], r14; lpPassword
0x1801145b1  mov     r9d, edx; dwErrorControl
0x1801145b4  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x1801145b9  mov     r8d, r15d; dwStartType
0x1801145bc  mov     [rsp+88h+lpDependencies], r14; lpDependencies
0x1801145c1  mov     rcx, rdi; hService
0x1801145c4  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x1801145c9  mov     [rsp+88h+lpLoadOrderGroup], r14; int
0x1801145ce  mov     [rsp+88h+lpBinaryPathName], r14; int
0x1801145d3  call    cs:__imp_ChangeServiceConfigW
0x1801145d9  test    eax, eax
0x1801145db  jnz     short loc_1801145EA
0x1801145dd  mov     r8d, 0FAh; unsigned int
0x1801145e3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1801145e8  jmp     short loc_180114607
0x1801145ea  xor     r8d, r8d; lpServiceArgVectors
0x1801145ed  xor     edx, edx; dwNumServiceArgs
0x1801145ef  mov     rcx, rdi; hService
0x1801145f2  call    cs:__imp_StartServiceW
0x1801145f8  test    eax, eax
0x1801145fa  jnz     short loc_180114604
0x1801145fc  mov     r8d, 103h
0x180114602  jmp     short loc_1801145E3
0x180114604  mov     r14d, r13d
0x180114607  call    cs:__imp_GetLastError
0x18011460d  mov     rcx, rdi; hSCObject
0x180114610  mov     ebx, eax
0x180114612  call    cs:__imp_CloseServiceHandle
0x180114618  mov     rcx, rsi; hSCObject
0x18011461b  call    cs:__imp_CloseServiceHandle
0x180114621  mov     ecx, ebx; dwErrCode
0x180114623  call    cs:__imp_SetLastError
0x180114629  lea     r11, [rsp+88h+var_28]
0x18011462e  mov     eax, r14d
0x180114631  mov     rbx, [r11+30h]
0x180114635  mov     rbp, [r11+38h]
0x180114639  mov     rsp, r11
0x18011463c  pop     r15
0x18011463e  pop     r14
0x180114640  pop     r13
0x180114642  pop     rdi
0x180114643  pop     rsi
0x180114644  retn
```
