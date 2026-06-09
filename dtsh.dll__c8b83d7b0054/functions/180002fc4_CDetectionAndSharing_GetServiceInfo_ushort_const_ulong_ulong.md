# CDetectionAndSharing::GetServiceInfo(ushort const *,ulong *,ulong *)

- ea: `0x180002fc4`
- end: `0x1800030c0`
- name: `?GetServiceInfo@CDetectionAndSharing@@AEAAJPEBGPEAK1@Z`
- size: `252`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002e2c`
- `0x180003128`
- `0x180003410`

## callees

- `0x180002fc4`
- `0x1800036f8`
- `0x180004920`

## import_xrefs

- `ADVAPI32!ControlService` at `0x18000301c`
- `ADVAPI32!ControlService` at `0x18000301c`
- `ADVAPI32!OpenServiceW` at `0x180002ff0`
- `ADVAPI32!OpenServiceW` at `0x180002ff0`
- `ADVAPI32!CloseServiceHandle` at `0x180003074`
- `ADVAPI32!CloseServiceHandle` at `0x180003074`
- `KERNEL32!GetLastError` at `0x18000302d`
- `KERNEL32!GetLastError` at `0x180003086`
- `KERNEL32!GetLastError` at `0x18000302d`
- `KERNEL32!GetLastError` at `0x180003086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000306b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000306b`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::GetServiceInfo(
        SC_HANDLE *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  unsigned int v8; // ebp
  DWORD dwCurrentState; // esi
  signed int v10; // ebx
  int ServiceConfigWithAlloc; // eax
  signed int LastError; // eax
  LPVOID pv; // [rsp+20h] [rbp-68h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-60h] BYREF

  v6 = OpenServiceW(this[8], a2, 0x81u);
  v7 = v6;
  if ( v6 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    v8 = 0;
    if ( ControlService(v6, 4u, &ServiceStatus) || (dwCurrentState = 0, v10 = -2147467259, GetLastError() == 1062) )
    {
      dwCurrentState = ServiceStatus.dwCurrentState;
      pv = 0;
      ServiceConfigWithAlloc = QueryServiceConfigWithAlloc(v7, (struct _QUERY_SERVICE_CONFIGW **)&pv);
      v10 = ServiceConfigWithAlloc;
      if ( ServiceConfigWithAlloc > 0 )
        v10 = (unsigned __int16)ServiceConfigWithAlloc | 0x80070000;
      if ( v10 >= 0 )
      {
        v8 = *((_DWORD *)pv + 1);
        CoTaskMemFree(pv);
      }
    }
    CloseServiceHandle(v7);
    if ( v10 >= 0 )
    {
      *a3 = v8;
      *a4 = dwCurrentState;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002fc4  push    rbx
0x180002fc6  push    rbp
0x180002fc7  push    rsi
0x180002fc8  push    rdi
0x180002fc9  push    r14
0x180002fcb  push    r15
0x180002fcd  sub     rsp, 58h
0x180002fd1  mov     rax, cs:__security_cookie
0x180002fd8  xor     rax, rsp
0x180002fdb  mov     [rsp+88h+var_40], rax
0x180002fe0  mov     rcx, [rcx+40h]; hSCManager
0x180002fe4  mov     r14, r8
0x180002fe7  mov     r8d, 81h; dwDesiredAccess
0x180002fed  mov     r15, r9
0x180002ff0  call    cs:__imp_OpenServiceW
0x180002ff6  mov     rdi, rax
0x180002ff9  test    rax, rax
0x180002ffc  jz      loc_180003086
0x180003002  xorps   xmm0, xmm0
0x180003005  lea     r8, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18000300a  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18000300f  xor     ebp, ebp
0x180003011  mov     rcx, rax; hService
0x180003014  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180003019  lea     edx, [rbp+4]; dwControl
0x18000301c  call    cs:__imp_ControlService
0x180003022  test    eax, eax
0x180003024  jnz     short loc_18000303A
0x180003026  xor     esi, esi
0x180003028  mov     ebx, 80004005h
0x18000302d  call    cs:__imp_GetLastError
0x180003033  cmp     eax, 426h
0x180003038  jnz     short loc_180003071
0x18000303a  mov     esi, [rsp+88h+ServiceStatus.dwCurrentState]
0x18000303e  lea     rdx, [rsp+88h+pv]
0x180003043  mov     rcx, rdi; hService
0x180003046  mov     [rsp+88h+pv], rbp
0x18000304b  call    QueryServiceConfigWithAlloc
0x180003050  mov     ebx, eax
0x180003052  test    eax, eax
0x180003054  jle     short loc_18000305F
0x180003056  movzx   ebx, ax
0x180003059  or      ebx, 80070000h
0x18000305f  test    ebx, ebx
0x180003061  js      short loc_180003071
0x180003063  mov     rcx, [rsp+88h+pv]; pv
0x180003068  mov     ebp, [rcx+4]
0x18000306b  call    cs:__imp_CoTaskMemFree
0x180003071  mov     rcx, rdi; hSCObject
0x180003074  call    cs:__imp_CloseServiceHandle
0x18000307a  test    ebx, ebx
0x18000307c  js      short loc_1800030A4
0x18000307e  mov     [r14], ebp
0x180003081  mov     [r15], esi
0x180003084  jmp     short loc_1800030A4
0x180003086  call    cs:__imp_GetLastError
0x18000308c  test    eax, eax
0x18000308e  jle     short loc_180003098
0x180003090  movzx   eax, ax
0x180003093  or      eax, 80070000h
0x180003098  mov     ebx, 80004005h
0x18000309d  test    eax, eax
0x18000309f  cmovns  eax, ebx
0x1800030a2  mov     ebx, eax
0x1800030a4  mov     eax, ebx
0x1800030a6  mov     rcx, [rsp+88h+var_40]
0x1800030ab  xor     rcx, rsp; StackCookie
0x1800030ae  call    __security_check_cookie
0x1800030b3  add     rsp, 58h
0x1800030b7  pop     r15
0x1800030b9  pop     r14
0x1800030bb  pop     rdi
0x1800030bc  pop     rsi
0x1800030bd  pop     rbp
0x1800030be  pop     rbx
0x1800030bf  retn
```
