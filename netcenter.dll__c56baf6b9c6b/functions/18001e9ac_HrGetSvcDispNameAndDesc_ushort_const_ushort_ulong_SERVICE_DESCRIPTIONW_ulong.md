# HrGetSvcDispNameAndDesc(ushort * const,ushort * *,ulong *,_SERVICE_DESCRIPTIONW * *,ulong *)

- ea: `0x18001e9ac`
- end: `0x18001ebf5`
- name: `?HrGetSvcDispNameAndDesc@@YAJQEAGPEAPEAGPEAKPEAPEAU_SERVICE_DESCRIPTIONW@@2@Z`
- size: `585`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 **, unsigned int *, struct _SERVICE_DESCRIPTIONW **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e7c4`

## callees

- `0x180010e9c`
- `0x18001e9ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ebc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ebcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ebc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ebcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ea7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eb3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ea7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb11`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001eb94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ebb0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001eb94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ebb0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea0b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea0b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001eacf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001eacf`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001eafd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001eb60`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001eafd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001eb60`
- `api-ms-win-service-core-l1-1-2!GetServiceDisplayNameW` at `0x18001ea33`
- `api-ms-win-service-core-l1-1-2!GetServiceDisplayNameW` at `0x18001eaa2`
- `api-ms-win-service-core-l1-1-2!GetServiceDisplayNameW` at `0x18001ea33`
- `api-ms-win-service-core-l1-1-2!GetServiceDisplayNameW` at `0x18001eaa2`

## string_xrefs

- `0x18001e9ff`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall HrGetSvcDispNameAndDesc(
        unsigned __int16 *const a1,
        LPVOID *a2,
        unsigned int *a3,
        LPVOID *a4,
        unsigned int *a5)
{
  unsigned int *v8; // r13
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // r12
  signed int Error; // ebx
  signed int LastError; // eax
  unsigned __int16 *v13; // rax
  signed int v14; // esi
  SC_HANDLE v15; // r15
  signed int v16; // eax
  struct _SERVICE_DESCRIPTIONW *v17; // rax
  __int64 v18; // rax
  DWORD cchBuffer; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbBufSize[5]; // [rsp+34h] [rbp-14h] BYREF
  unsigned __int16 *DisplayName; // [rsp+90h] [rbp+48h] BYREF

  DisplayName = a1;
  if ( !a2 )
    return 2147500035LL;
  if ( !a4 )
    return 2147500035LL;
  if ( !a3 )
    return 2147500035LL;
  v8 = a5;
  if ( !a5 )
    return 2147500035LL;
  *a2 = 0;
  *a4 = 0;
  v9 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v10 = v9;
  if ( !v9 )
  {
    Error = ResultFromKnownLastError();
    goto LABEL_39;
  }
  cchBuffer = 0;
  if ( !GetServiceDisplayNameW(v9, L"netprofm", (LPWSTR)&DisplayName, &cchBuffer) )
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError == 122 )
    {
      Error = 0;
      *a3 = cchBuffer + 1;
    }
    else
    {
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      if ( Error < 0 )
        goto LABEL_37;
    }
    v13 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *a3);
    *a2 = v13;
    if ( !v13 )
    {
      Error = -2147024882;
      goto LABEL_37;
    }
    cchBuffer = *a3;
    if ( !GetServiceDisplayNameW(v10, L"netprofm", v13, &cchBuffer) )
      Error = ResultFromKnownLastError();
    v14 = Error;
    if ( Error < 0 )
      goto LABEL_37;
    v15 = OpenServiceW(v10, L"netprofm", 1u);
    if ( !v15 )
    {
      Error = ResultFromKnownLastError();
      goto LABEL_37;
    }
    cbBufSize[0] = 0;
    if ( QueryServiceConfig2W(v15, 1u, (LPBYTE)&DisplayName, 0, cbBufSize) )
    {
      Error = -2147418113;
    }
    else
    {
      v16 = GetLastError();
      Error = v16;
      if ( v16 == 122 )
      {
        Error = v14;
      }
      else
      {
        if ( v16 > 0 )
          Error = (unsigned __int16)v16 | 0x80070000;
        if ( Error < 0 )
          goto LABEL_33;
      }
      v17 = (struct _SERVICE_DESCRIPTIONW *)CoTaskMemAlloc(cbBufSize[0]);
      *a4 = v17;
      if ( v17 )
      {
        if ( QueryServiceConfig2W(v15, 1u, (LPBYTE)v17, cbBufSize[0], cbBufSize) )
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(*(_QWORD *)*a4 + 2 * v18) );
          *v8 = v18;
        }
        else
        {
          Error = ResultFromKnownLastError();
        }
      }
      else
      {
        Error = -2147024882;
      }
    }
LABEL_33:
    CloseServiceHandle(v15);
    goto LABEL_37;
  }
  Error = -2147418113;
LABEL_37:
  CloseServiceHandle(v10);
LABEL_39:
  if ( Error < 0 )
  {
    CoTaskMemFree(*a2);
    CoTaskMemFree(*a4);
    *a2 = 0;
    *a4 = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001e9ac  mov     [rsp-40h+DisplayName], rcx
0x18001e9b1  push    rbp
0x18001e9b2  push    rbx
0x18001e9b3  push    rsi
0x18001e9b4  push    rdi
0x18001e9b5  push    r12
0x18001e9b7  push    r13
0x18001e9b9  push    r14
0x18001e9bb  push    r15
0x18001e9bd  mov     rbp, rsp
0x18001e9c0  sub     rsp, 48h
0x18001e9c4  xor     r15d, r15d
0x18001e9c7  mov     rdi, r9
0x18001e9ca  mov     rsi, r8
0x18001e9cd  mov     r14, rdx
0x18001e9d0  test    rdx, rdx
0x18001e9d3  jz      loc_18001EBDF
0x18001e9d9  test    r9, r9
0x18001e9dc  jz      loc_18001EBDF
0x18001e9e2  test    r8, r8
0x18001e9e5  jz      loc_18001EBDF
0x18001e9eb  mov     r13, [rbp+arg_20]
0x18001e9ef  test    r13, r13
0x18001e9f2  jz      loc_18001EBDF
0x18001e9f8  mov     [rdx], r15
0x18001e9fb  lea     r8d, [r15+1]; dwDesiredAccess
0x18001e9ff  lea     rdx, DatabaseName; "ServicesActive"
0x18001ea06  mov     [r9], r15
0x18001ea09  xor     ecx, ecx; lpMachineName
0x18001ea0b  call    cs:__imp_OpenSCManagerW
0x18001ea11  mov     r12, rax
0x18001ea14  test    rax, rax
0x18001ea17  jz      loc_18001EBB8
0x18001ea1d  lea     r9, [rbp+cchBuffer]; lpcchBuffer
0x18001ea21  mov     [rbp+cchBuffer], r15d
0x18001ea25  lea     r8, [rbp+DisplayName]; lpDisplayName
0x18001ea29  mov     rcx, rax; hSCManager
0x18001ea2c  lea     rdx, ServiceName; "netprofm"
0x18001ea33  call    cs:__imp_GetServiceDisplayNameW
0x18001ea39  test    eax, eax
0x18001ea3b  jz      short loc_18001EA47
0x18001ea3d  mov     ebx, 8000FFFFh
0x18001ea42  jmp     loc_18001EBAD
0x18001ea47  call    cs:__imp_GetLastError
0x18001ea4d  mov     ebx, eax
0x18001ea4f  cmp     eax, 7Ah ; 'z'
0x18001ea52  jnz     short loc_18001EA60
0x18001ea54  mov     eax, [rbp+cchBuffer]
0x18001ea57  mov     ebx, r15d
0x18001ea5a  inc     eax
0x18001ea5c  mov     [rsi], eax
0x18001ea5e  jmp     short loc_18001EA75
0x18001ea60  test    eax, eax
0x18001ea62  jle     short loc_18001EA6D
0x18001ea64  movzx   ebx, ax
0x18001ea67  or      ebx, 80070000h
0x18001ea6d  test    ebx, ebx
0x18001ea6f  js      loc_18001EBAD
0x18001ea75  mov     ecx, [rsi]
0x18001ea77  add     rcx, rcx; cb
0x18001ea7a  call    cs:__imp_CoTaskMemAlloc
0x18001ea80  mov     [r14], rax
0x18001ea83  test    rax, rax
0x18001ea86  jz      loc_18001EBA8
0x18001ea8c  mov     ecx, [rsi]
0x18001ea8e  lea     r9, [rbp+cchBuffer]; lpcchBuffer
0x18001ea92  mov     [rbp+cchBuffer], ecx
0x18001ea95  lea     rdx, ServiceName; "netprofm"
0x18001ea9c  mov     rcx, r12; hSCManager
0x18001ea9f  mov     r8, rax; lpDisplayName
0x18001eaa2  call    cs:__imp_GetServiceDisplayNameW
0x18001eaa8  test    eax, eax
0x18001eaaa  jnz     short loc_18001EAB3
0x18001eaac  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001eab1  mov     ebx, eax
0x18001eab3  mov     esi, ebx
0x18001eab5  test    ebx, ebx
0x18001eab7  js      loc_18001EBAD
0x18001eabd  mov     ebx, 1
0x18001eac2  lea     rdx, ServiceName; "netprofm"
0x18001eac9  mov     r8d, ebx; dwDesiredAccess
0x18001eacc  mov     rcx, r12; hSCManager
0x18001eacf  call    cs:__imp_OpenServiceW
0x18001ead5  mov     r15, rax
0x18001ead8  test    rax, rax
0x18001eadb  jz      loc_18001EB9F
0x18001eae1  lea     rax, [rbp+cbBufSize]
0x18001eae5  mov     [rbp+cbBufSize], 0
0x18001eaec  xor     r9d, r9d; cbBufSize
0x18001eaef  mov     [rsp+48h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001eaf4  lea     r8, [rbp+DisplayName]; lpBuffer
0x18001eaf8  mov     edx, ebx; dwInfoLevel
0x18001eafa  mov     rcx, r15; hService
0x18001eafd  call    cs:__imp_QueryServiceConfig2W
0x18001eb03  test    eax, eax
0x18001eb05  jz      short loc_18001EB11
0x18001eb07  mov     ebx, 8000FFFFh
0x18001eb0c  jmp     loc_18001EB91
0x18001eb11  call    cs:__imp_GetLastError
0x18001eb17  mov     ebx, eax
0x18001eb19  cmp     eax, 7Ah ; 'z'
0x18001eb1c  jz      short loc_18001EB33
0x18001eb1e  xor     esi, esi
0x18001eb20  test    eax, eax
0x18001eb22  jle     short loc_18001EB2D
0x18001eb24  movzx   ebx, ax
0x18001eb27  or      ebx, 80070000h
0x18001eb2d  test    ebx, ebx
0x18001eb2f  js      short loc_18001EB91
0x18001eb31  jmp     short loc_18001EB37
0x18001eb33  mov     ebx, esi
0x18001eb35  xor     esi, esi
0x18001eb37  mov     ecx, [rbp+cbBufSize]; cb
0x18001eb3a  call    cs:__imp_CoTaskMemAlloc
0x18001eb40  mov     [rdi], rax
0x18001eb43  test    rax, rax
0x18001eb46  jz      short loc_18001EB8C
0x18001eb48  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x18001eb4c  lea     rcx, [rbp+cbBufSize]
0x18001eb50  mov     [rsp+48h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x18001eb55  mov     r8, rax; lpBuffer
0x18001eb58  mov     rcx, r15; hService
0x18001eb5b  mov     edx, 1; dwInfoLevel
0x18001eb60  call    cs:__imp_QueryServiceConfig2W
0x18001eb66  test    eax, eax
0x18001eb68  jz      short loc_18001EB83
0x18001eb6a  mov     rax, [rdi]
0x18001eb6d  mov     rcx, [rax]
0x18001eb70  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eb74  inc     rax
0x18001eb77  cmp     [rcx+rax*2], si
0x18001eb7b  jnz     short loc_18001EB74
0x18001eb7d  mov     [r13+0], eax
0x18001eb81  jmp     short loc_18001EB91
0x18001eb83  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001eb88  mov     ebx, eax
0x18001eb8a  jmp     short loc_18001EB91
0x18001eb8c  mov     ebx, 8007000Eh
0x18001eb91  mov     rcx, r15; hSCObject
0x18001eb94  call    cs:__imp_CloseServiceHandle
0x18001eb9a  xor     r15d, r15d
0x18001eb9d  jmp     short loc_18001EBAD
0x18001eb9f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001eba4  mov     ebx, eax
0x18001eba6  jmp     short loc_18001EB9A
0x18001eba8  mov     ebx, 8007000Eh
0x18001ebad  mov     rcx, r12; hSCObject
0x18001ebb0  call    cs:__imp_CloseServiceHandle
0x18001ebb6  jmp     short loc_18001EBBF
0x18001ebb8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ebbd  mov     ebx, eax
0x18001ebbf  test    ebx, ebx
0x18001ebc1  jns     short loc_18001EBDB
0x18001ebc3  mov     rcx, [r14]; pv
0x18001ebc6  call    cs:__imp_CoTaskMemFree
0x18001ebcc  mov     rcx, [rdi]; pv
0x18001ebcf  call    cs:__imp_CoTaskMemFree
0x18001ebd5  mov     [r14], r15
0x18001ebd8  mov     [rdi], r15
0x18001ebdb  mov     eax, ebx
0x18001ebdd  jmp     short loc_18001EBE4
0x18001ebdf  mov     eax, 80004003h
0x18001ebe4  add     rsp, 48h
0x18001ebe8  pop     r15
0x18001ebea  pop     r14
0x18001ebec  pop     r13
0x18001ebee  pop     r12
0x18001ebf0  pop     rdi
0x18001ebf1  pop     rsi
0x18001ebf2  pop     rbx
0x18001ebf3  pop     rbp
0x18001ebf4  retn
```
