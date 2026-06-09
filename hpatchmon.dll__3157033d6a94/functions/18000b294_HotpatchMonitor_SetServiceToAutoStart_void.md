# HotpatchMonitor::SetServiceToAutoStart(void)

- ea: `0x18000b294`
- end: `0x18000b610`
- name: `?SetServiceToAutoStart@HotpatchMonitor@@KAJXZ`
- size: `892`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180009a80`

## callees

- `0x180001008`
- `0x1800011cc`
- `0x180002270`
- `0x180002c8c`
- `0x180002c98`
- `0x18000b294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b527`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000b2ca`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000b2ca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000b34f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000b34f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b3c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b445`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b44f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b5d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b5e3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b3c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b445`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b44f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b5d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b5e3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000b51d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000b51d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000b3d9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000b477`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000b3d9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000b477`

## string_xrefs

- `0x18000b4cc`: `Service is already set to auto start`

## pseudocode

```c
__int64 HotpatchMonitor::SetServiceToAutoStart(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int LastError; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  signed int v6; // eax
  signed int v7; // eax
  unsigned int v8; // esi
  struct _QUERY_SERVICE_CONFIGW *v10; // r14
  int v11; // ecx
  int v12; // r9d
  signed int v13; // eax
  unsigned int v14; // esi
  char *v15; // rdx
  signed int v16; // eax
  unsigned __int64 v17; // rdx
  const char *v18; // [rsp+60h] [rbp-39h] BYREF
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp-31h] BYREF
  SC_HANDLE v20; // [rsp+70h] [rbp-29h]
  SC_HANDLE v21; // [rsp+78h] [rbp-21h]
  _BYTE v22[32]; // [rsp+80h] [rbp-19h] BYREF
  const char **v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]

  v18 = 0;
  pcbBytesNeeded = 0;
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  v20 = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v18) = v3;
      v23 = &v18;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, word_180018D62, 0, 0, 3, v22);
    }
    return v3;
  }
  v4 = OpenServiceW(v0, L"hpatchmon", 0xF01FFu);
  v5 = v4;
  v21 = v4;
  if ( !v4 )
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v18) = v3;
      v23 = &v18;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, word_180018C9A, 0, 0, 3, v22);
    }
    CloseServiceHandle(v1);
    return v3;
  }
  QueryServiceConfigW(v4, 0, 0, &pcbBytesNeeded);
  v7 = GetLastError();
  v8 = v7;
  if ( v7 != 122 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v18) = v8;
      v23 = &v18;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_1800188B9, 0, 0, 3, v22);
    }
    CloseServiceHandle(v5);
    CloseServiceHandle(v1);
    return v8;
  }
  v10 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded);
  if ( !QueryServiceConfigW(v5, v10, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( (unsigned int)dword_18001E048 <= 5 )
      goto LABEL_37;
    v15 = byte_180018905;
    goto LABEL_33;
  }
  if ( v10->dwStartType == 2 )
  {
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v18 = "Service is already set to auto start";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned int)word_1800192A2,
        2,
        v12,
        (__int64)&v18);
    }
LABEL_36:
    v14 = 0;
    goto LABEL_37;
  }
  if ( ChangeServiceConfigW(v5, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v18) = 0;
      v23 = &v18;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &byte_18001861F, 0, 0, 3, v22);
    }
    goto LABEL_36;
  }
  v16 = GetLastError();
  v14 = v16;
  if ( v16 > 0 )
    v14 = (unsigned __int16)v16 | 0x80070000;
  if ( (unsigned int)dword_18001E048 <= 5 )
    goto LABEL_37;
  v15 = byte_1800186FD;
LABEL_33:
  v23 = &v18;
  v24 = 4;
  LODWORD(v18) = v14;
  tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, v15, 0, 0, 3, v22);
LABEL_37:
  CloseServiceHandle(v5);
  CloseServiceHandle(v1);
  operator delete(v10, v17);
  return v14;
}

```

## disassembly

```asm
0x18000b294  push    rbp
0x18000b296  push    rbx
0x18000b297  push    rsi
0x18000b298  push    rdi
0x18000b299  push    r14
0x18000b29b  push    r15
0x18000b29d  lea     rbp, [rsp-2Fh]
0x18000b2a2  sub     rsp, 0C8h
0x18000b2a9  mov     rax, cs:__security_cookie
0x18000b2b0  xor     rax, rsp
0x18000b2b3  mov     [rbp+57h+var_40], rax
0x18000b2b7  xor     r15d, r15d
0x18000b2ba  mov     [rbp+57h+var_90], r15
0x18000b2be  mov     [rbp+57h+pcbBytesNeeded], r15d
0x18000b2c2  xor     edx, edx; lpDatabaseName
0x18000b2c4  xor     ecx, ecx; lpMachineName
0x18000b2c6  lea     r8d, [r15+1]; dwDesiredAccess
0x18000b2ca  call    cs:__imp_OpenSCManagerW
0x18000b2d0  mov     rdi, rax
0x18000b2d3  mov     [rbp+57h+var_80], rax
0x18000b2d7  test    rax, rax
0x18000b2da  jnz     short loc_18000B33F
0x18000b2dc  call    cs:__imp_GetLastError
0x18000b2e2  mov     ebx, eax
0x18000b2e4  test    eax, eax
0x18000b2e6  jle     short loc_18000B2F1
0x18000b2e8  movzx   ebx, ax
0x18000b2eb  or      ebx, 80070000h
0x18000b2f1  mov     eax, cs:dword_18001E048
0x18000b2f7  cmp     eax, 5
0x18000b2fa  jbe     short loc_18000B33A
0x18000b2fc  mov     dword ptr [rbp+57h+var_90], ebx
0x18000b2ff  lea     rax, [rbp+57h+var_90]
0x18000b303  mov     [rbp+57h+var_50], rax
0x18000b307  mov     [rbp+57h+var_48], 4
0x18000b30f  lea     rax, [rbp+57h+var_70]
0x18000b313  mov     [rsp+0F0h+lpLoadOrderGroup], rax
0x18000b318  mov     dword ptr [rsp+0F0h+lpBinaryPathName], 3
0x18000b320  xor     r9d, r9d
0x18000b323  xor     r8d, r8d
0x18000b326  lea     rdx, word_180018D62
0x18000b32d  lea     rcx, dword_18001E048
0x18000b334  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b339  nop
0x18000b33a  jmp     loc_18000B457
0x18000b33f  mov     r8d, 0F01FFh; dwDesiredAccess
0x18000b345  lea     rdx, ServiceName; "hpatchmon"
0x18000b34c  mov     rcx, rdi; hSCManager
0x18000b34f  call    cs:__imp_OpenServiceW
0x18000b355  mov     rbx, rax
0x18000b358  mov     [rbp+57h+var_78], rax
0x18000b35c  test    rax, rax
0x18000b35f  jnz     short loc_18000B3CD
0x18000b361  call    cs:__imp_GetLastError
0x18000b367  mov     ebx, eax
0x18000b369  test    eax, eax
0x18000b36b  jle     short loc_18000B376
0x18000b36d  movzx   ebx, ax
0x18000b370  or      ebx, 80070000h
0x18000b376  mov     eax, cs:dword_18001E048
0x18000b37c  cmp     eax, 5
0x18000b37f  jbe     short loc_18000B3BF
0x18000b381  mov     dword ptr [rbp+57h+var_90], ebx
0x18000b384  lea     rax, [rbp+57h+var_90]
0x18000b388  mov     [rbp+57h+var_50], rax
0x18000b38c  mov     [rbp+57h+var_48], 4
0x18000b394  lea     rax, [rbp+57h+var_70]
0x18000b398  mov     [rsp+0F0h+lpLoadOrderGroup], rax
0x18000b39d  mov     dword ptr [rsp+0F0h+lpBinaryPathName], 3
0x18000b3a5  xor     r9d, r9d
0x18000b3a8  xor     r8d, r8d
0x18000b3ab  lea     rdx, word_180018C9A
0x18000b3b2  lea     rcx, dword_18001E048
0x18000b3b9  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b3be  nop
0x18000b3bf  mov     rcx, rdi; hSCObject
0x18000b3c2  call    cs:__imp_CloseServiceHandle
0x18000b3c8  jmp     loc_18000B457
0x18000b3cd  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18000b3d1  xor     r8d, r8d; cbBufSize
0x18000b3d4  xor     edx, edx; lpServiceConfig
0x18000b3d6  mov     rcx, rbx; hService
0x18000b3d9  call    cs:__imp_QueryServiceConfigW
0x18000b3df  call    cs:__imp_GetLastError
0x18000b3e5  mov     esi, eax
0x18000b3e7  cmp     eax, 7Ah ; 'z'
0x18000b3ea  jz      short loc_18000B45E
0x18000b3ec  test    eax, eax
0x18000b3ee  jle     short loc_18000B3F9
0x18000b3f0  movzx   esi, ax
0x18000b3f3  or      esi, 80070000h
0x18000b3f9  mov     eax, cs:dword_18001E048
0x18000b3ff  cmp     eax, 5
0x18000b402  jbe     short loc_18000B442
0x18000b404  mov     dword ptr [rbp+57h+var_90], esi
0x18000b407  lea     rax, [rbp+57h+var_90]
0x18000b40b  mov     [rbp+57h+var_50], rax
0x18000b40f  mov     [rbp+57h+var_48], 4
0x18000b417  lea     rax, [rbp+57h+var_70]
0x18000b41b  mov     [rsp+0F0h+lpLoadOrderGroup], rax
0x18000b420  mov     dword ptr [rsp+0F0h+lpBinaryPathName], 3
0x18000b428  xor     r9d, r9d
0x18000b42b  xor     r8d, r8d
0x18000b42e  lea     rdx, byte_1800188B9
0x18000b435  lea     rcx, dword_18001E048
0x18000b43c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b441  nop
0x18000b442  mov     rcx, rbx; hSCObject
0x18000b445  call    cs:__imp_CloseServiceHandle
0x18000b44b  nop
0x18000b44c  mov     rcx, rdi; hSCObject
0x18000b44f  call    cs:__imp_CloseServiceHandle
0x18000b455  mov     ebx, esi
0x18000b457  mov     eax, ebx
0x18000b459  jmp     loc_18000B5F4
0x18000b45e  mov     ecx, [rbp+57h+pcbBytesNeeded]; unsigned __int64
0x18000b461  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b466  mov     r14, rax
0x18000b469  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18000b46d  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x18000b471  mov     rdx, rax; lpServiceConfig
0x18000b474  mov     rcx, rbx; hService
0x18000b477  call    cs:__imp_QueryServiceConfigW
0x18000b47d  test    eax, eax
0x18000b47f  jnz     short loc_18000B4B1
0x18000b481  call    cs:__imp_GetLastError
0x18000b487  mov     esi, eax
0x18000b489  test    eax, eax
0x18000b48b  jle     short loc_18000B496
0x18000b48d  movzx   esi, ax
0x18000b490  or      esi, 80070000h
0x18000b496  mov     eax, cs:dword_18001E048
0x18000b49c  cmp     eax, 5
0x18000b49f  jbe     loc_18000B5D6
0x18000b4a5  lea     rdx, byte_180018905
0x18000b4ac  jmp     loc_18000B552
0x18000b4b1  mov     r8d, 2; dwStartType
0x18000b4b7  cmp     [r14+4], r8d
0x18000b4bb  jnz     short loc_18000B4F1
0x18000b4bd  mov     eax, cs:dword_18001E048
0x18000b4c3  cmp     eax, 5
0x18000b4c6  jbe     loc_18000B5D3
0x18000b4cc  lea     rax, aServiceIsAlrea; "Service is already set to auto start"
0x18000b4d3  mov     [rbp+57h+var_90], rax
0x18000b4d7  lea     rax, [rbp+57h+var_90]
0x18000b4db  mov     [rsp+0F0h+lpBinaryPathName], rax
0x18000b4e0  lea     rdx, word_1800192A2
0x18000b4e7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000b4ec  jmp     loc_18000B5D3
0x18000b4f1  mov     [rsp+0F0h+lpDisplayName], r15; lpDisplayName
0x18000b4f6  mov     [rsp+0F0h+lpPassword], r15; lpPassword
0x18000b4fb  mov     [rsp+0F0h+lpServiceStartName], r15; lpServiceStartName
0x18000b500  mov     [rsp+0F0h+lpDependencies], r15; lpDependencies
0x18000b505  mov     [rsp+0F0h+lpdwTagId], r15; lpdwTagId
0x18000b50a  mov     [rsp+0F0h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x18000b50f  mov     [rsp+0F0h+lpBinaryPathName], r15; lpBinaryPathName
0x18000b514  or      edx, 0FFFFFFFFh; dwServiceType
0x18000b517  mov     r9d, edx; dwErrorControl
0x18000b51a  mov     rcx, rbx; hService
0x18000b51d  call    cs:__imp_ChangeServiceConfigW
0x18000b523  test    eax, eax
0x18000b525  jnz     short loc_18000B58A
0x18000b527  call    cs:__imp_GetLastError
0x18000b52d  mov     esi, eax
0x18000b52f  test    eax, eax
0x18000b531  jle     short loc_18000B53C
0x18000b533  movzx   esi, ax
0x18000b536  or      esi, 80070000h
0x18000b53c  mov     eax, cs:dword_18001E048
0x18000b542  cmp     eax, 5
0x18000b545  jbe     loc_18000B5D6
0x18000b54b  lea     rdx, byte_1800186FD
0x18000b552  lea     rax, [rbp+57h+var_90]
0x18000b556  mov     [rbp+57h+var_50], rax
0x18000b55a  lea     rax, [rbp+57h+var_70]
0x18000b55e  xor     r9d, r9d
0x18000b561  mov     [rsp+0F0h+lpLoadOrderGroup], rax
0x18000b566  xor     r8d, r8d
0x18000b569  mov     dword ptr [rsp+0F0h+lpBinaryPathName], 3
0x18000b571  mov     [rbp+57h+var_48], 4
0x18000b579  mov     dword ptr [rbp+57h+var_90], esi
0x18000b57c  lea     rcx, dword_18001E048
0x18000b583  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b588  jmp     short loc_18000B5D6
0x18000b58a  mov     eax, cs:dword_18001E048
0x18000b590  cmp     eax, 5
0x18000b593  jbe     short loc_18000B5D3
0x18000b595  mov     dword ptr [rbp+57h+var_90], r15d
0x18000b599  lea     rax, [rbp+57h+var_90]
0x18000b59d  mov     [rbp+57h+var_50], rax
0x18000b5a1  mov     [rbp+57h+var_48], 4
0x18000b5a9  lea     rax, [rbp+57h+var_70]
0x18000b5ad  mov     [rsp+0F0h+lpLoadOrderGroup], rax
0x18000b5b2  mov     dword ptr [rsp+0F0h+lpBinaryPathName], 3
0x18000b5ba  xor     r9d, r9d
0x18000b5bd  xor     r8d, r8d
0x18000b5c0  lea     rdx, byte_18001861F
0x18000b5c7  lea     rcx, dword_18001E048
0x18000b5ce  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b5d3  mov     esi, r15d
0x18000b5d6  mov     rcx, rbx; hSCObject
0x18000b5d9  call    cs:__imp_CloseServiceHandle
0x18000b5df  nop
0x18000b5e0  mov     rcx, rdi; hSCObject
0x18000b5e3  call    cs:__imp_CloseServiceHandle
0x18000b5e9  nop
0x18000b5ea  mov     rcx, r14; void *
0x18000b5ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b5f2  mov     eax, esi
0x18000b5f4  mov     rcx, [rbp+57h+var_40]
0x18000b5f8  xor     rcx, rsp; StackCookie
0x18000b5fb  call    __security_check_cookie
0x18000b600  add     rsp, 0C8h
0x18000b607  pop     r15
0x18000b609  pop     r14
0x18000b60b  pop     rdi
0x18000b60c  pop     rsi
0x18000b60d  pop     rbx
0x18000b60e  pop     rbp
0x18000b60f  retn
```
