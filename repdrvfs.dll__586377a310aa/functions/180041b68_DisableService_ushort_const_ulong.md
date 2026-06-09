# DisableService(ushort const *,ulong &)

- ea: `0x180041b68`
- end: `0x180041d21`
- name: `?DisableService@@YAJPEBGAEAK@Z`
- size: `441`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800411c0`
- `0x180041610`

## callees

- `0x180041b68`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180041bf9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180041bf9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180041caa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180041caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d01`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041b86`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041b86`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041cd9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041cf9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041cd9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041cf9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041ba8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041ba8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180041c84`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180041c84`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180041bd5`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180041c21`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180041bd5`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180041c21`

## pseudocode

```c
__int64 __fastcall DisableService(const unsigned __int16 *a1, unsigned int *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbp
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  struct _QUERY_SERVICE_CONFIGW *v8; // rdi
  unsigned int dwStartType; // ecx
  unsigned int v10; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  const unsigned __int16 *pcbBytesNeeded; // [rsp+90h] [rbp+8h] BYREF

  pcbBytesNeeded = a1;
  *a2 = -1;
  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"WinMgmt", 3u);
    v6 = v5;
    if ( v5 )
    {
      LODWORD(pcbBytesNeeded) = 0;
      if ( QueryServiceConfigW(v5, 0, 0, (LPDWORD)&pcbBytesNeeded) )
      {
        v10 = -2147217379;
      }
      else if ( GetLastError() == 122 )
      {
        v7 = (struct _QUERY_SERVICE_CONFIGW *)CWin32DefaultArena::WbemMemAlloc((unsigned int)pcbBytesNeeded);
        v8 = v7;
        if ( v7 )
        {
          if ( QueryServiceConfigW(v6, v7, (DWORD)pcbBytesNeeded, (LPDWORD)&pcbBytesNeeded)
            && ((dwStartType = v8->dwStartType, *a2 = dwStartType, dwStartType == -1)
             || ChangeServiceConfigW(v6, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)) )
          {
            v10 = 0;
          }
          else
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
          }
          CWin32DefaultArena::WbemMemFree(v8);
        }
        else
        {
          v10 = -2147217402;
        }
      }
      else
      {
        v12 = GetLastError();
        v10 = v12;
        if ( v12 > 0 )
          v10 = (unsigned __int16)v12 | 0x80070000;
      }
      CloseServiceHandle(v6);
    }
    else
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v14 = GetLastError();
    v10 = v14;
    if ( v14 > 0 )
      return (unsigned __int16)v14 | 0x80070000;
  }
  return v10;
}

```

## disassembly

```asm
0x180041b68  mov     [rsp+pcbBytesNeeded], rcx
0x180041b6d  push    rbx
0x180041b6e  push    rbp
0x180041b6f  push    rsi
0x180041b70  push    rdi
0x180041b71  sub     rsp, 68h
0x180041b75  mov     rbx, rdx
0x180041b78  mov     dword ptr [rdx], 0FFFFFFFFh
0x180041b7e  xor     edx, edx; lpDatabaseName
0x180041b80  xor     ecx, ecx; lpMachineName
0x180041b82  lea     r8d, [rdx+1]; dwDesiredAccess
0x180041b86  call    cs:__imp_OpenSCManagerW
0x180041b8c  mov     rbp, rax
0x180041b8f  test    rax, rax
0x180041b92  jz      loc_180041D01
0x180041b98  mov     r8d, 3; dwDesiredAccess
0x180041b9e  lea     rdx, ServiceName; "WinMgmt"
0x180041ba5  mov     rcx, rax; hSCManager
0x180041ba8  call    cs:__imp_OpenServiceW
0x180041bae  mov     rsi, rax
0x180041bb1  test    rax, rax
0x180041bb4  jz      loc_180041CE1
0x180041bba  mov     dword ptr [rsp+88h+pcbBytesNeeded], 0
0x180041bc5  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x180041bcd  xor     r8d, r8d; cbBufSize
0x180041bd0  xor     edx, edx; lpServiceConfig
0x180041bd2  mov     rcx, rax; hService
0x180041bd5  call    cs:__imp_QueryServiceConfigW
0x180041bdb  test    eax, eax
0x180041bdd  jnz     loc_180041CD1
0x180041be3  call    cs:__imp_GetLastError
0x180041be9  cmp     eax, 7Ah ; 'z'
0x180041bec  jnz     loc_180041CBA
0x180041bf2  mov     ecx, dword ptr [rsp+88h+pcbBytesNeeded]
0x180041bf9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180041bff  mov     rdi, rax
0x180041c02  test    rax, rax
0x180041c05  jz      loc_180041CB3
0x180041c0b  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x180041c13  mov     r8d, dword ptr [rsp+88h+pcbBytesNeeded]; cbBufSize
0x180041c1b  mov     rdx, rax; lpServiceConfig
0x180041c1e  mov     rcx, rsi; hService
0x180041c21  call    cs:__imp_QueryServiceConfigW
0x180041c27  test    eax, eax
0x180041c29  jz      short loc_180041C92
0x180041c2b  mov     ecx, [rdi+4]
0x180041c2e  mov     [rbx], ecx
0x180041c30  cmp     ecx, 0FFFFFFFFh
0x180041c33  jz      short loc_180041C8E
0x180041c35  mov     [rsp+88h+lpDisplayName], 0; lpDisplayName
0x180041c3e  mov     [rsp+88h+lpPassword], 0; lpPassword
0x180041c47  mov     [rsp+88h+lpServiceStartName], 0; lpServiceStartName
0x180041c50  mov     [rsp+88h+lpDependencies], 0; lpDependencies
0x180041c59  mov     [rsp+88h+lpdwTagId], 0; lpdwTagId
0x180041c62  mov     [rsp+88h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180041c6b  mov     [rsp+88h+lpBinaryPathName], 0; lpBinaryPathName
0x180041c74  or      r9d, 0FFFFFFFFh; dwErrorControl
0x180041c78  mov     r8d, 4; dwStartType
0x180041c7e  or      edx, r9d; dwServiceType
0x180041c81  mov     rcx, rsi; hService
0x180041c84  call    cs:__imp_ChangeServiceConfigW
0x180041c8a  test    eax, eax
0x180041c8c  jz      short loc_180041C92
0x180041c8e  xor     ebx, ebx
0x180041c90  jmp     short loc_180041CA7
0x180041c92  call    cs:__imp_GetLastError
0x180041c98  test    eax, eax
0x180041c9a  mov     ebx, eax
0x180041c9c  jle     short loc_180041CA7
0x180041c9e  movzx   ebx, ax
0x180041ca1  or      ebx, 80070000h
0x180041ca7  mov     rcx, rdi
0x180041caa  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180041cb0  nop
0x180041cb1  jmp     short loc_180041CD6
0x180041cb3  mov     ebx, 80041006h
0x180041cb8  jmp     short loc_180041CD6
0x180041cba  call    cs:__imp_GetLastError
0x180041cc0  mov     ebx, eax
0x180041cc2  test    eax, eax
0x180041cc4  jle     short loc_180041CD6
0x180041cc6  movzx   ebx, ax
0x180041cc9  or      ebx, 80070000h
0x180041ccf  jmp     short loc_180041CD6
0x180041cd1  mov     ebx, 8004101Dh
0x180041cd6  mov     rcx, rsi; hSCObject
0x180041cd9  call    cs:__imp_CloseServiceHandle
0x180041cdf  jmp     short loc_180041CF6
0x180041ce1  call    cs:__imp_GetLastError
0x180041ce7  mov     ebx, eax
0x180041ce9  test    eax, eax
0x180041ceb  jle     short loc_180041CF6
0x180041ced  movzx   ebx, ax
0x180041cf0  or      ebx, 80070000h
0x180041cf6  mov     rcx, rbp; hSCObject
0x180041cf9  call    cs:__imp_CloseServiceHandle
0x180041cff  jmp     short loc_180041D16
0x180041d01  call    cs:__imp_GetLastError
0x180041d07  mov     ebx, eax
0x180041d09  test    eax, eax
0x180041d0b  jle     short loc_180041D16
0x180041d0d  movzx   ebx, ax
0x180041d10  or      ebx, 80070000h
0x180041d16  mov     eax, ebx
0x180041d18  add     rsp, 68h
0x180041d1c  pop     rdi
0x180041d1d  pop     rsi
0x180041d1e  pop     rbp
0x180041d1f  pop     rbx
0x180041d20  retn
```
