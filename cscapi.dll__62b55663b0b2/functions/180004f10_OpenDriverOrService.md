# _OpenDriverOrService

- ea: `0x180004f10`
- end: `0x180004ff6`
- name: `_OpenDriverOrService`
- size: `230`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwDesiredAccess)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007950`
- `0x180007ff4`
- `0x180008118`

## callees

- `0x180004f10`
- `0x180007e54`
- `0x180007ee8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004f30`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004f30`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004f4e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004f4e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004f5f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004f5f`

## pseudocode

```c
DWORD __fastcall OpenDriverOrService(LPCWSTR lpServiceName, DWORD dwDesiredAccess, SC_HANDLE *a3)
{
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbx
  DWORD v8; // edi
  SC_HANDLE v9; // rax
  DWORD result; // eax
  DWORD LastError; // eax
  int v12; // r8d
  __int64 v13; // r8
  DWORD v14; // ebx

  *a3 = 0;
  v6 = OpenSCManagerW(0, 0, dwDesiredAccess);
  v7 = v6;
  if ( v6 )
  {
    v8 = 0;
    v9 = OpenServiceW(v6, lpServiceName, dwDesiredAccess);
    *a3 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          (unsigned int)&WPP_GLOBAL_Control,
          v12,
          (_DWORD)lpServiceName,
          dwDesiredAccess,
          LastError);
    }
    CloseServiceHandle(v7);
    return v8;
  }
  else
  {
    result = GetLastError();
    v14 = result;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, v13, dwDesiredAccess, result);
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004f10  push    rbx
0x180004f12  push    rbp
0x180004f13  push    rsi
0x180004f14  push    r14
0x180004f16  sub     rsp, 38h
0x180004f1a  mov     rsi, r8
0x180004f1d  mov     qword ptr [r8], 0
0x180004f24  mov     r8d, edx; dwDesiredAccess
0x180004f27  mov     ebp, edx
0x180004f29  mov     r14, rcx
0x180004f2c  xor     edx, edx; lpDatabaseName
0x180004f2e  xor     ecx, ecx; lpMachineName
0x180004f30  call    cs:__imp_OpenSCManagerW
0x180004f36  mov     rbx, rax
0x180004f39  test    rax, rax
0x180004f3c  jz      short loc_180004FB3
0x180004f3e  mov     [rsp+58h+arg_0], rdi
0x180004f43  mov     r8d, ebp; dwDesiredAccess
0x180004f46  mov     rdx, r14; lpServiceName
0x180004f49  mov     rcx, rax; hSCManager
0x180004f4c  xor     edi, edi
0x180004f4e  call    cs:__imp_OpenServiceW
0x180004f54  mov     [rsi], rax
0x180004f57  test    rax, rax
0x180004f5a  jz      short loc_180004F76
0x180004f5c  mov     rcx, rbx; hSCObject
0x180004f5f  call    cs:__imp_CloseServiceHandle
0x180004f65  mov     eax, edi
0x180004f67  mov     rdi, [rsp+58h+arg_0]
0x180004f6c  add     rsp, 38h
0x180004f70  pop     r14
0x180004f72  pop     rsi
0x180004f73  pop     rbp
0x180004f74  pop     rbx
0x180004f75  retn
0x180004f76  call    cs:__imp_GetLastError
0x180004f7c  mov     edi, eax
0x180004f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f85  lea     rdx, WPP_GLOBAL_Control
0x180004f8c  cmp     rcx, rdx
0x180004f8f  jz      short loc_180004F5C
0x180004f91  test    byte ptr [rcx+0BCh], 1
0x180004f98  jz      short loc_180004F5C
0x180004f9a  mov     rcx, [rcx+0B0h]
0x180004fa1  mov     r9, r14
0x180004fa4  mov     [rsp+58h+var_30], eax
0x180004fa8  mov     [rsp+58h+var_38], ebp
0x180004fac  call    WPP_SF_Sdd
0x180004fb1  jmp     short loc_180004F5C
0x180004fb3  call    cs:__imp_GetLastError
0x180004fb9  mov     ebx, eax
0x180004fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fc2  lea     rdx, WPP_GLOBAL_Control
0x180004fc9  cmp     rcx, rdx
0x180004fcc  jz      short loc_180004F6C
0x180004fce  test    byte ptr [rcx+0BCh], 1
0x180004fd5  jz      short loc_180004F6C
0x180004fd7  mov     rcx, [rcx+0B0h]
0x180004fde  mov     edx, 0Ah
0x180004fe3  mov     r9d, ebp
0x180004fe6  mov     [rsp+58h+var_38], eax
0x180004fea  call    WPP_SF_dd
0x180004fef  mov     eax, ebx
0x180004ff1  jmp     loc_180004F6C
```
