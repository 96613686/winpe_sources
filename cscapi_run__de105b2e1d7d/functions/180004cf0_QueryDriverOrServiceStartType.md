# _QueryDriverOrServiceStartType

- ea: `0x180004cf0`
- end: `0x180004f07`
- name: `_QueryDriverOrServiceStartType`
- size: `535`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800073f0`

## callees

- `0x180004cf0`
- `0x180007dd4`
- `0x180007e54`
- `0x180007ee8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004ddb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004dfc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004ddb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004dfc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180004da3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180004da3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004d17`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004d17`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004d3b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004d3b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004d57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004de9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004d57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004de9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180004d7a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180004dc1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180004d7a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180004dc1`

## pseudocode

```c
__int64 __fastcall QueryDriverOrServiceStartType(LPCWSTR lpServiceName, DWORD *a2)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  DWORD v6; // edi
  SC_HANDLE v7; // rbp
  struct _QUERY_SERVICE_CONFIGW *v8; // rdi
  DWORD v9; // ebx
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  struct _QUERY_SERVICE_CONFIGW *v11; // rsi
  DWORD LastError; // eax
  int v14; // edx
  int v15; // r8d
  DWORD v16; // eax
  __int64 v17; // r8
  DWORD v18; // eax
  int v19; // r8d
  DWORD pcbBytesNeeded; // [rsp+70h] [rbp+18h] BYREF

  v4 = OpenSCManagerW(0, 0, 0x80000000);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    v7 = OpenServiceW(v4, lpServiceName, 0x80000000);
    if ( !v7 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 22), v14, v15, (_DWORD)lpServiceName, 0, LastError);
    }
    CloseServiceHandle(v5);
  }
  else
  {
    v7 = 0;
    v16 = GetLastError();
    v6 = v16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, v17, 0x80000000LL, v16);
  }
  if ( v6 )
    return v6;
  pcbBytesNeeded = 0;
  v8 = 0;
  if ( QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded) )
  {
    v9 = 1;
  }
  else
  {
    v9 = GetLastError();
    if ( v9 == 122 )
    {
      v10 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
      v11 = v10;
      if ( v10 )
      {
        if ( QueryServiceConfigW(v7, v10, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          v8 = v11;
          v9 = 0;
          v11 = 0;
        }
        else
        {
          v18 = GetLastError();
          v9 = v18;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 13, v19, (_DWORD)lpServiceName, v18);
        }
        LocalFree(v11);
      }
      else
      {
        v9 = 8;
      }
    }
  }
  CloseServiceHandle(v7);
  if ( !v9 )
  {
    *a2 = v8->dwStartType;
    LocalFree(v8);
  }
  return v9;
}

```

## disassembly

```asm
0x180004cf0  mov     [rsp+arg_8], rbx
0x180004cf5  mov     [rsp+arg_18], rbp
0x180004cfa  push    rdi
0x180004cfb  push    r12
0x180004cfd  push    r13
0x180004cff  push    r14
0x180004d01  push    r15
0x180004d03  sub     rsp, 30h
0x180004d07  mov     r15, rdx
0x180004d0a  mov     r12, rcx
0x180004d0d  xor     edx, edx; lpDatabaseName
0x180004d0f  xor     ecx, ecx; lpMachineName
0x180004d11  mov     r8d, 80000000h; dwDesiredAccess
0x180004d17  call    cs:__imp_OpenSCManagerW
0x180004d1d  xor     r14d, r14d
0x180004d20  mov     rbx, rax
0x180004d23  test    rax, rax
0x180004d26  jz      loc_180004E6C
0x180004d2c  mov     r8d, 80000000h; dwDesiredAccess
0x180004d32  mov     rdx, r12; lpServiceName
0x180004d35  mov     rcx, rax; hSCManager
0x180004d38  mov     edi, r14d
0x180004d3b  call    cs:__imp_OpenServiceW
0x180004d41  lea     r13, WPP_GLOBAL_Control
0x180004d48  mov     rbp, rax
0x180004d4b  test    rax, rax
0x180004d4e  jz      loc_180004E23
0x180004d54  mov     rcx, rbx; hSCObject
0x180004d57  call    cs:__imp_CloseServiceHandle
0x180004d5d  test    edi, edi
0x180004d5f  jnz     loc_180004E68
0x180004d65  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180004d6a  mov     [rsp+58h+pcbBytesNeeded], r14d
0x180004d6f  xor     r8d, r8d; cbBufSize
0x180004d72  xor     edx, edx; lpServiceConfig
0x180004d74  mov     rcx, rbp; hService
0x180004d77  mov     rdi, r14
0x180004d7a  call    cs:__imp_QueryServiceConfigW
0x180004d80  test    eax, eax
0x180004d82  jnz     loc_180004EBB
0x180004d88  call    cs:__imp_GetLastError
0x180004d8e  mov     ebx, eax
0x180004d90  cmp     eax, 7Ah ; 'z'
0x180004d93  jnz     short loc_180004DE6
0x180004d95  mov     edx, [rsp+58h+pcbBytesNeeded]; uBytes
0x180004d99  mov     ecx, 40h ; '@'; uFlags
0x180004d9e  mov     [rsp+58h+arg_0], rsi
0x180004da3  call    cs:__imp_LocalAlloc
0x180004da9  mov     rsi, rax
0x180004dac  test    rax, rax
0x180004daf  jz      short loc_180004E1C
0x180004db1  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180004db6  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180004dbb  mov     rdx, rax; lpServiceConfig
0x180004dbe  mov     rcx, rbp; hService
0x180004dc1  call    cs:__imp_QueryServiceConfigW
0x180004dc7  test    eax, eax
0x180004dc9  jz      loc_180004EC5
0x180004dcf  mov     rdi, rsi
0x180004dd2  mov     ebx, r14d
0x180004dd5  mov     rsi, r14
0x180004dd8  mov     rcx, rsi; hMem
0x180004ddb  call    cs:__imp_LocalFree
0x180004de1  mov     rsi, [rsp+58h+arg_0]
0x180004de6  mov     rcx, rbp; hSCObject
0x180004de9  call    cs:__imp_CloseServiceHandle
0x180004def  test    ebx, ebx
0x180004df1  jnz     short loc_180004E02
0x180004df3  mov     eax, [rdi+4]
0x180004df6  mov     rcx, rdi; hMem
0x180004df9  mov     [r15], eax
0x180004dfc  call    cs:__imp_LocalFree
0x180004e02  mov     eax, ebx
0x180004e04  mov     rbx, [rsp+58h+arg_8]
0x180004e09  mov     rbp, [rsp+58h+arg_18]
0x180004e0e  add     rsp, 30h
0x180004e12  pop     r15
0x180004e14  pop     r14
0x180004e16  pop     r13
0x180004e18  pop     r12
0x180004e1a  pop     rdi
0x180004e1b  retn
0x180004e1c  mov     ebx, 8
0x180004e21  jmp     short loc_180004DE1
0x180004e23  call    cs:__imp_GetLastError
0x180004e29  mov     edi, eax
0x180004e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e32  cmp     rcx, r13
0x180004e35  jz      loc_180004D54
0x180004e3b  test    byte ptr [rcx+0BCh], 1
0x180004e42  jz      loc_180004D54
0x180004e48  mov     rcx, [rcx+0B0h]
0x180004e4f  mov     r9, r12
0x180004e52  mov     [rsp+58h+var_30], eax
0x180004e56  mov     [rsp+58h+var_38], 80000000h
0x180004e5e  call    WPP_SF_Sdd
0x180004e63  jmp     loc_180004D54
0x180004e68  mov     eax, edi
0x180004e6a  jmp     short loc_180004E04
0x180004e6c  mov     rbp, r14
0x180004e6f  call    cs:__imp_GetLastError
0x180004e75  mov     edi, eax
0x180004e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e7e  lea     r13, WPP_GLOBAL_Control
0x180004e85  cmp     rcx, r13
0x180004e88  jz      loc_180004D5D
0x180004e8e  test    byte ptr [rcx+0BCh], 1
0x180004e95  jz      loc_180004D5D
0x180004e9b  mov     rcx, [rcx+0B0h]
0x180004ea2  mov     edx, 0Ah
0x180004ea7  mov     r9d, 80000000h
0x180004ead  mov     [rsp+58h+var_38], eax
0x180004eb1  call    WPP_SF_dd
0x180004eb6  jmp     loc_180004D5D
0x180004ebb  mov     ebx, 1
0x180004ec0  jmp     loc_180004DE6
0x180004ec5  call    cs:__imp_GetLastError
0x180004ecb  mov     ebx, eax
0x180004ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ed4  cmp     rcx, r13
0x180004ed7  jz      loc_180004DD8
0x180004edd  test    byte ptr [rcx+0BCh], 1
0x180004ee4  jz      loc_180004DD8
0x180004eea  mov     rcx, [rcx+0B0h]
0x180004ef1  mov     edx, 0Dh
0x180004ef6  mov     r9, r12
0x180004ef9  mov     [rsp+58h+var_38], eax
0x180004efd  call    WPP_SF_Sd
0x180004f02  jmp     loc_180004DD8
```
