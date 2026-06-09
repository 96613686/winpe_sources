# HotpatchMonitor::ConfigureServiceStartType(ulong const &)

- ea: `0x1800051d8`
- end: `0x18000556a`
- name: `?ConfigureServiceStartType@HotpatchMonitor@@KAJAEBK@Z`
- size: `914`
- prototype: `__int64 __fastcall(DWORD *)`
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
- `0x1800051d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000522d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000522d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005475`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000521b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000521b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800052a0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800052a0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005313`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005396`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800053a0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005527`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005531`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005313`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005396`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800053a0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005527`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005531`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000546b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000546b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000532a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800053c8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000532a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800053c8`

## string_xrefs

- `0x18000541a`: `Service is already set to the requested start type`

## pseudocode

```c
__int64 __fastcall HotpatchMonitor::ConfigureServiceStartType(DWORD *a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbx
  signed int v8; // eax
  signed int v9; // eax
  unsigned int v10; // esi
  struct _QUERY_SERVICE_CONFIGW *v12; // r15
  int v13; // ecx
  int v14; // r9d
  signed int v15; // eax
  unsigned int v16; // esi
  int *v17; // rdx
  DWORD v18; // r8d
  signed int v19; // eax
  unsigned __int64 v20; // rdx
  const char *v21; // [rsp+60h] [rbp-29h] BYREF
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp-21h] BYREF
  SC_HANDLE v23; // [rsp+70h] [rbp-19h]
  SC_HANDLE v24; // [rsp+78h] [rbp-11h]
  _BYTE v25[32]; // [rsp+80h] [rbp-9h] BYREF
  const char **v26; // [rsp+A0h] [rbp+17h]
  __int64 v27; // [rsp+A8h] [rbp+1Fh]

  v21 = 0;
  pcbBytesNeeded = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  v23 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v21) = v5;
      v26 = &v21;
      v27 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_180018D23, 0, 0, 3, v25);
    }
    return v5;
  }
  v6 = OpenServiceW(v2, L"hpatchmon", 0xF01FFu);
  v7 = v6;
  v24 = v6;
  if ( !v6 )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v21) = v5;
      v26 = &v21;
      v27 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &word_18001873E, 0, 0, 3, v25);
    }
    CloseServiceHandle(v3);
    return v5;
  }
  QueryServiceConfigW(v6, 0, 0, &pcbBytesNeeded);
  v9 = GetLastError();
  v10 = v9;
  if ( v9 != 122 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v21) = v10;
      v26 = &v21;
      v27 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_180018CD3, 0, 0, 3, v25);
    }
    CloseServiceHandle(v7);
    CloseServiceHandle(v3);
    return v10;
  }
  v12 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded);
  if ( !QueryServiceConfigW(v7, v12, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    if ( (unsigned int)dword_18001E048 <= 5 )
      goto LABEL_37;
    v17 = &dword_1800193CC;
    goto LABEL_33;
  }
  v18 = *a1;
  if ( v12->dwStartType == *a1 )
  {
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v21 = "Service is already set to the requested start type";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v13,
        (unsigned int)&dword_180018B14,
        v18,
        v14,
        (__int64)&v21);
    }
LABEL_36:
    v16 = 0;
    goto LABEL_37;
  }
  if ( ChangeServiceConfigW(v7, 0xFFFFFFFF, v18, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      LODWORD(v21) = 0;
      v26 = &v21;
      v27 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_180018DEB, 0, 0, 3, v25);
    }
    goto LABEL_36;
  }
  v19 = GetLastError();
  v16 = v19;
  if ( v19 > 0 )
    v16 = (unsigned __int16)v19 | 0x80070000;
  if ( (unsigned int)dword_18001E048 <= 5 )
    goto LABEL_37;
  v17 = (int *)byte_1800190F1;
LABEL_33:
  v26 = &v21;
  v27 = 4;
  LODWORD(v21) = v16;
  tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, v17, 0, 0, 3, v25);
LABEL_37:
  CloseServiceHandle(v7);
  CloseServiceHandle(v3);
  operator delete(v12, v20);
  return v16;
}

```

## disassembly

```asm
0x1800051d8  mov     [rsp-8+arg_8], rbx
0x1800051dd  mov     [rsp-8+arg_10], rsi
0x1800051e2  push    rbp
0x1800051e3  push    rdi
0x1800051e4  push    r12
0x1800051e6  push    r14
0x1800051e8  push    r15
0x1800051ea  lea     rbp, [rsp-37h]
0x1800051ef  sub     rsp, 0C0h
0x1800051f6  mov     rax, cs:__security_cookie
0x1800051fd  xor     rax, rsp
0x180005200  mov     [rbp+57h+var_30], rax
0x180005204  mov     r14, rcx
0x180005207  xor     r12d, r12d
0x18000520a  mov     [rbp+57h+var_80], r12
0x18000520e  mov     [rbp+57h+pcbBytesNeeded], r12d
0x180005212  xor     edx, edx; lpDatabaseName
0x180005214  xor     ecx, ecx; lpMachineName
0x180005216  lea     r8d, [r12+1]; dwDesiredAccess
0x18000521b  call    cs:__imp_OpenSCManagerW
0x180005221  mov     rdi, rax
0x180005224  mov     [rbp+57h+var_70], rax
0x180005228  test    rax, rax
0x18000522b  jnz     short loc_180005290
0x18000522d  call    cs:__imp_GetLastError
0x180005233  mov     ebx, eax
0x180005235  test    eax, eax
0x180005237  jle     short loc_180005242
0x180005239  movzx   ebx, ax
0x18000523c  or      ebx, 80070000h
0x180005242  mov     eax, cs:dword_18001E048
0x180005248  cmp     eax, 5
0x18000524b  jbe     short loc_18000528B
0x18000524d  mov     dword ptr [rbp+57h+var_80], ebx
0x180005250  lea     rax, [rbp+57h+var_80]
0x180005254  mov     [rbp+57h+var_40], rax
0x180005258  mov     [rbp+57h+var_38], 4
0x180005260  lea     rax, [rbp+57h+var_60]
0x180005264  mov     [rsp+0E0h+lpLoadOrderGroup], rax
0x180005269  mov     dword ptr [rsp+0E0h+lpBinaryPathName], 3
0x180005271  xor     r9d, r9d
0x180005274  xor     r8d, r8d
0x180005277  lea     rdx, byte_180018D23
0x18000527e  lea     rcx, dword_18001E048
0x180005285  call    _tlgWriteTransfer_EventWriteTransfer
0x18000528a  nop
0x18000528b  jmp     loc_1800053A8
0x180005290  mov     r8d, 0F01FFh; dwDesiredAccess
0x180005296  lea     rdx, ServiceName; "hpatchmon"
0x18000529d  mov     rcx, rdi; hSCManager
0x1800052a0  call    cs:__imp_OpenServiceW
0x1800052a6  mov     rbx, rax
0x1800052a9  mov     [rbp+57h+var_68], rax
0x1800052ad  test    rax, rax
0x1800052b0  jnz     short loc_18000531E
0x1800052b2  call    cs:__imp_GetLastError
0x1800052b8  mov     ebx, eax
0x1800052ba  test    eax, eax
0x1800052bc  jle     short loc_1800052C7
0x1800052be  movzx   ebx, ax
0x1800052c1  or      ebx, 80070000h
0x1800052c7  mov     eax, cs:dword_18001E048
0x1800052cd  cmp     eax, 5
0x1800052d0  jbe     short loc_180005310
0x1800052d2  mov     dword ptr [rbp+57h+var_80], ebx
0x1800052d5  lea     rax, [rbp+57h+var_80]
0x1800052d9  mov     [rbp+57h+var_40], rax
0x1800052dd  mov     [rbp+57h+var_38], 4
0x1800052e5  lea     rax, [rbp+57h+var_60]
0x1800052e9  mov     [rsp+0E0h+lpLoadOrderGroup], rax
0x1800052ee  mov     dword ptr [rsp+0E0h+lpBinaryPathName], 3
0x1800052f6  xor     r9d, r9d
0x1800052f9  xor     r8d, r8d
0x1800052fc  lea     rdx, word_18001873E
0x180005303  lea     rcx, dword_18001E048
0x18000530a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000530f  nop
0x180005310  mov     rcx, rdi; hSCObject
0x180005313  call    cs:__imp_CloseServiceHandle
0x180005319  jmp     loc_1800053A8
0x18000531e  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180005322  xor     r8d, r8d; cbBufSize
0x180005325  xor     edx, edx; lpServiceConfig
0x180005327  mov     rcx, rbx; hService
0x18000532a  call    cs:__imp_QueryServiceConfigW
0x180005330  call    cs:__imp_GetLastError
0x180005336  mov     esi, eax
0x180005338  cmp     eax, 7Ah ; 'z'
0x18000533b  jz      short loc_1800053AF
0x18000533d  test    eax, eax
0x18000533f  jle     short loc_18000534A
0x180005341  movzx   esi, ax
0x180005344  or      esi, 80070000h
0x18000534a  mov     eax, cs:dword_18001E048
0x180005350  cmp     eax, 5
0x180005353  jbe     short loc_180005393
0x180005355  mov     dword ptr [rbp+57h+var_80], esi
0x180005358  lea     rax, [rbp+57h+var_80]
0x18000535c  mov     [rbp+57h+var_40], rax
0x180005360  mov     [rbp+57h+var_38], 4
0x180005368  lea     rax, [rbp+57h+var_60]
0x18000536c  mov     [rsp+0E0h+lpLoadOrderGroup], rax
0x180005371  mov     dword ptr [rsp+0E0h+lpBinaryPathName], 3
0x180005379  xor     r9d, r9d
0x18000537c  xor     r8d, r8d
0x18000537f  lea     rdx, byte_180018CD3
0x180005386  lea     rcx, dword_18001E048
0x18000538d  call    _tlgWriteTransfer_EventWriteTransfer
0x180005392  nop
0x180005393  mov     rcx, rbx; hSCObject
0x180005396  call    cs:__imp_CloseServiceHandle
0x18000539c  nop
0x18000539d  mov     rcx, rdi; hSCObject
0x1800053a0  call    cs:__imp_CloseServiceHandle
0x1800053a6  mov     ebx, esi
0x1800053a8  mov     eax, ebx
0x1800053aa  jmp     loc_180005542
0x1800053af  mov     ecx, [rbp+57h+pcbBytesNeeded]; unsigned __int64
0x1800053b2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800053b7  mov     r15, rax
0x1800053ba  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x1800053be  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x1800053c2  mov     rdx, rax; lpServiceConfig
0x1800053c5  mov     rcx, rbx; hService
0x1800053c8  call    cs:__imp_QueryServiceConfigW
0x1800053ce  test    eax, eax
0x1800053d0  jnz     short loc_180005402
0x1800053d2  call    cs:__imp_GetLastError
0x1800053d8  mov     esi, eax
0x1800053da  test    eax, eax
0x1800053dc  jle     short loc_1800053E7
0x1800053de  movzx   esi, ax
0x1800053e1  or      esi, 80070000h
0x1800053e7  mov     eax, cs:dword_18001E048
0x1800053ed  cmp     eax, 5
0x1800053f0  jbe     loc_180005524
0x1800053f6  lea     rdx, dword_1800193CC
0x1800053fd  jmp     loc_1800054A0
0x180005402  mov     r8d, [r14]; dwStartType
0x180005405  cmp     [r15+4], r8d
0x180005409  jnz     short loc_18000543F
0x18000540b  mov     eax, cs:dword_18001E048
0x180005411  cmp     eax, 5
0x180005414  jbe     loc_180005521
0x18000541a  lea     rax, aServiceIsAlrea_0; "Service is already set to the requested"...
0x180005421  mov     [rbp+57h+var_80], rax
0x180005425  lea     rax, [rbp+57h+var_80]
0x180005429  mov     [rsp+0E0h+lpBinaryPathName], rax
0x18000542e  lea     rdx, dword_180018B14
0x180005435  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000543a  jmp     loc_180005521
0x18000543f  mov     [rsp+0E0h+lpDisplayName], r12; lpDisplayName
0x180005444  mov     [rsp+0E0h+lpPassword], r12; lpPassword
0x180005449  mov     [rsp+0E0h+lpServiceStartName], r12; lpServiceStartName
0x18000544e  mov     [rsp+0E0h+lpDependencies], r12; lpDependencies
0x180005453  mov     [rsp+0E0h+lpdwTagId], r12; lpdwTagId
0x180005458  mov     [rsp+0E0h+lpLoadOrderGroup], r12; lpLoadOrderGroup
0x18000545d  mov     [rsp+0E0h+lpBinaryPathName], r12; lpBinaryPathName
0x180005462  or      edx, 0FFFFFFFFh; dwServiceType
0x180005465  mov     r9d, edx; dwErrorControl
0x180005468  mov     rcx, rbx; hService
0x18000546b  call    cs:__imp_ChangeServiceConfigW
0x180005471  test    eax, eax
0x180005473  jnz     short loc_1800054D8
0x180005475  call    cs:__imp_GetLastError
0x18000547b  mov     esi, eax
0x18000547d  test    eax, eax
0x18000547f  jle     short loc_18000548A
0x180005481  movzx   esi, ax
0x180005484  or      esi, 80070000h
0x18000548a  mov     eax, cs:dword_18001E048
0x180005490  cmp     eax, 5
0x180005493  jbe     loc_180005524
0x180005499  lea     rdx, byte_1800190F1
0x1800054a0  lea     rax, [rbp+57h+var_80]
0x1800054a4  mov     [rbp+57h+var_40], rax
0x1800054a8  lea     rax, [rbp+57h+var_60]
0x1800054ac  xor     r9d, r9d
0x1800054af  mov     [rsp+0E0h+lpLoadOrderGroup], rax
0x1800054b4  xor     r8d, r8d
0x1800054b7  mov     dword ptr [rsp+0E0h+lpBinaryPathName], 3
0x1800054bf  mov     [rbp+57h+var_38], 4
0x1800054c7  mov     dword ptr [rbp+57h+var_80], esi
0x1800054ca  lea     rcx, dword_18001E048
0x1800054d1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800054d6  jmp     short loc_180005524
0x1800054d8  mov     eax, cs:dword_18001E048
0x1800054de  cmp     eax, 5
0x1800054e1  jbe     short loc_180005521
0x1800054e3  mov     dword ptr [rbp+57h+var_80], r12d
0x1800054e7  lea     rax, [rbp+57h+var_80]
0x1800054eb  mov     [rbp+57h+var_40], rax
0x1800054ef  mov     [rbp+57h+var_38], 4
0x1800054f7  lea     rax, [rbp+57h+var_60]
0x1800054fb  mov     [rsp+0E0h+lpLoadOrderGroup], rax
0x180005500  mov     dword ptr [rsp+0E0h+lpBinaryPathName], 3
0x180005508  xor     r9d, r9d
0x18000550b  xor     r8d, r8d
0x18000550e  lea     rdx, byte_180018DEB
0x180005515  lea     rcx, dword_18001E048
0x18000551c  call    _tlgWriteTransfer_EventWriteTransfer
0x180005521  mov     esi, r12d
0x180005524  mov     rcx, rbx; hSCObject
0x180005527  call    cs:__imp_CloseServiceHandle
0x18000552d  nop
0x18000552e  mov     rcx, rdi; hSCObject
0x180005531  call    cs:__imp_CloseServiceHandle
0x180005537  nop
0x180005538  mov     rcx, r15; void *
0x18000553b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005540  mov     eax, esi
0x180005542  mov     rcx, [rbp+57h+var_30]
0x180005546  xor     rcx, rsp; StackCookie
0x180005549  call    __security_check_cookie
0x18000554e  lea     r11, [rsp+0E0h+var_20]
0x180005556  mov     rbx, [r11+38h]
0x18000555a  mov     rsi, [r11+40h]
0x18000555e  mov     rsp, r11
0x180005561  pop     r15
0x180005563  pop     r14
0x180005565  pop     r12
0x180005567  pop     rdi
0x180005568  pop     rbp
0x180005569  retn
```
