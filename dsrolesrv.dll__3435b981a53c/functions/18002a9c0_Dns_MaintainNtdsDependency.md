# Dns_MaintainNtdsDependency

- ea: `0x18002a9c0`
- end: `0x18002abec`
- name: `Dns_MaintainNtdsDependency`
- size: `556`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800295c0`

## callees

- `0x18002a9c0`
- `0x18002abf4`
- `0x18002ac1c`
- `0x18002b79c`
- `0x18002b810`
- `0x18002c012`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa12`
- `ntdll!_stricmp` at `0x18002aa94`
- `ntdll!_stricmp` at `0x18002ab4a`
- `ntdll!_stricmp` at `0x18002aa94`
- `ntdll!_stricmp` at `0x18002ab4a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ab09`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ab17`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ab09`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ab17`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18002aa04`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18002aa04`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x18002abd9`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x18002abd9`

## pseudocode

```c
__int64 Dns_MaintainNtdsDependency()
{
  const char *v0; // r13
  SC_HANDLE v1; // rbx
  CHAR *lpDependencies; // r14
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r12
  DWORD LastError; // esi
  DWORD ServiceConfig; // eax
  __int64 v7; // r15
  const char *v8; // rbx
  __int64 v9; // rdi
  int v10; // eax
  const char *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  _BYTE *v15; // rbx
  CHAR *v16; // rdi
  size_t v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  SC_HANDLE v20; // rcx
  int v21; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+50h] BYREF
  SC_HANDLE hService; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+60h] BYREF

  v0 = 0;
  v1 = 0;
  v22 = 0;
  hService = 0;
  v24 = 0;
  v21 = 0;
  lpDependencies = 0;
  v3 = OpenSCManagerA(0, 0, 0xC0000000);
  v4 = v3;
  if ( !v3 )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_19;
  }
  LastError = getServiceConfig((_DWORD)v3, (unsigned int)"DNS", (unsigned int)&hService, (unsigned int)&v22, 0);
  if ( LastError )
    goto LABEL_18;
  ServiceConfig = getServiceConfig((_DWORD)v4, (unsigned int)"NTDS", 0, (unsigned int)&v24, (__int64)&v21);
  LastError = ServiceConfig;
  if ( ServiceConfig != 1060 )
  {
    if ( ServiceConfig )
      goto LABEL_18;
  }
  v7 = v22;
  if ( !v22 )
    goto LABEL_18;
  v8 = *(const char **)(v22 + 40);
  if ( !v8 )
    goto LABEL_18;
  v9 = 0;
  if ( !*v8 )
    goto LABEL_18;
  do
  {
    v10 = _stricmp(v8, "NTDS");
    v11 = v8;
    if ( v10 )
      v11 = v0;
    v12 = -1;
    v0 = v11;
    do
      ++v12;
    while ( v8[v12] );
    v8 += v12 + 1;
    v9 += v12 + 1;
  }
  while ( *v8 );
  if ( !v11 || !v9 )
    goto LABEL_18;
  v13 = Dns_AllocZero((unsigned int)v9);
  lpDependencies = (CHAR *)v13;
  if ( !v13 )
  {
    LastError = 14;
LABEL_18:
    v1 = hService;
    goto LABEL_19;
  }
  v15 = *(_BYTE **)(v7 + 40);
  v16 = (CHAR *)v13;
  if ( !*v15 )
    goto LABEL_35;
  do
  {
    if ( _stricmp(v15, "NTDS") )
    {
      v17 = -1;
      do
        ++v17;
      while ( v15[v17] );
      memcpy_0(v16, v15, v17);
      v18 = -1;
      do
        ++v18;
      while ( v15[v18] );
      v16[v18] = 0;
      v16 += v18 + 1;
    }
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
    v15 += v19 + 1;
  }
  while ( *v15 );
  if ( v16 == lpDependencies )
LABEL_35:
    *v16++ = 0;
  v1 = hService;
  v20 = hService;
  *v16 = 0;
  if ( !ChangeServiceConfigA(v20, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 0, lpDependencies, 0, 0, 0) )
    goto LABEL_2;
LABEL_19:
  Dns_Free(lpDependencies);
  freeServiceConfig(&v22);
  freeServiceConfig(&v24);
  if ( v1 )
    CloseServiceHandle(v1);
  if ( v4 )
    CloseServiceHandle(v4);
  return LastError;
}

```

## disassembly

```asm
0x18002a9c0  mov     [rsp-40h+hService], r8
0x18002a9c5  mov     [rsp-40h+arg_8], rdx
0x18002a9ca  mov     [rsp-40h+arg_0], ecx
0x18002a9ce  push    rbp
0x18002a9cf  push    rbx
0x18002a9d0  push    rsi
0x18002a9d1  push    rdi
0x18002a9d2  push    r12
0x18002a9d4  push    r13
0x18002a9d6  push    r14
0x18002a9d8  push    r15
0x18002a9da  mov     rbp, rsp
0x18002a9dd  sub     rsp, 68h
0x18002a9e1  xor     r13d, r13d
0x18002a9e4  xor     edx, edx; lpDatabaseName
0x18002a9e6  mov     ebx, r13d
0x18002a9e9  mov     [rbp+arg_8], r13
0x18002a9ed  xor     ecx, ecx; lpMachineName
0x18002a9ef  mov     [rbp+hService], rbx
0x18002a9f3  mov     r8d, 0C0000000h; dwDesiredAccess
0x18002a9f9  mov     [rbp+arg_18], r13
0x18002a9fd  mov     [rbp+arg_0], r13d
0x18002aa01  mov     r14d, r13d
0x18002aa04  call    cs:__imp_OpenSCManagerA
0x18002aa0a  mov     r12, rax
0x18002aa0d  test    rax, rax
0x18002aa10  jnz     short loc_18002AA1F
0x18002aa12  call    cs:__imp_GetLastError
0x18002aa18  mov     esi, eax
0x18002aa1a  jmp     loc_18002AAE7
0x18002aa1f  lea     r9, [rbp+arg_8]
0x18002aa23  mov     [rsp+68h+lpBinaryPathName], r13
0x18002aa28  lea     r8, [rbp+hService]
0x18002aa2c  mov     rcx, r12
0x18002aa2f  lea     rdx, aDns; "DNS"
0x18002aa36  call    getServiceConfig
0x18002aa3b  mov     esi, eax
0x18002aa3d  test    eax, eax
0x18002aa3f  jnz     loc_18002AAE3
0x18002aa45  lea     rax, [rbp+arg_0]
0x18002aa49  xor     r8d, r8d
0x18002aa4c  lea     r9, [rbp+arg_18]
0x18002aa50  mov     [rsp+68h+lpBinaryPathName], rax
0x18002aa55  lea     rdx, aNtds_0; "NTDS"
0x18002aa5c  mov     rcx, r12
0x18002aa5f  call    getServiceConfig
0x18002aa64  mov     esi, eax
0x18002aa66  cmp     eax, 424h
0x18002aa6b  jz      short loc_18002AA71
0x18002aa6d  test    eax, eax
0x18002aa6f  jnz     short loc_18002AAE3
0x18002aa71  mov     r15, [rbp+arg_8]
0x18002aa75  test    r15, r15
0x18002aa78  jz      short loc_18002AAE3
0x18002aa7a  mov     rbx, [r15+28h]
0x18002aa7e  test    rbx, rbx
0x18002aa81  jz      short loc_18002AAE3
0x18002aa83  xor     edi, edi
0x18002aa85  cmp     [rbx], dil
0x18002aa88  jz      short loc_18002AAE3
0x18002aa8a  lea     rdx, aNtds_0; "NTDS"
0x18002aa91  mov     rcx, rbx; String1
0x18002aa94  call    cs:__imp__stricmp
0x18002aa9a  test    eax, eax
0x18002aa9c  mov     rcx, rbx
0x18002aa9f  cmovnz  rcx, r13
0x18002aaa3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aaa7  mov     r13, rcx
0x18002aaaa  inc     rax
0x18002aaad  cmp     [rbx+rax], r14b
0x18002aab1  jnz     short loc_18002AAAA
0x18002aab3  inc     rbx
0x18002aab6  inc     rdi
0x18002aab9  add     rbx, rax
0x18002aabc  add     rdi, rax
0x18002aabf  cmp     [rbx], r14b
0x18002aac2  jnz     short loc_18002AA8A
0x18002aac4  test    rcx, rcx
0x18002aac7  jz      short loc_18002AAE3
0x18002aac9  xor     r13d, r13d
0x18002aacc  test    rdi, rdi
0x18002aacf  jz      short loc_18002AAE3
0x18002aad1  mov     ecx, edi; Size
0x18002aad3  call    Dns_AllocZero
0x18002aad8  mov     r14, rax
0x18002aadb  test    rax, rax
0x18002aade  jnz     short loc_18002AB30
0x18002aae0  lea     esi, [rax+0Eh]
0x18002aae3  mov     rbx, [rbp+hService]
0x18002aae7  mov     rcx, r14; lpMem
0x18002aaea  call    Dns_Free
0x18002aaef  lea     rcx, [rbp+arg_8]
0x18002aaf3  call    freeServiceConfig
0x18002aaf8  lea     rcx, [rbp+arg_18]
0x18002aafc  call    freeServiceConfig
0x18002ab01  test    rbx, rbx
0x18002ab04  jz      short loc_18002AB0F
0x18002ab06  mov     rcx, rbx; hSCObject
0x18002ab09  call    cs:__imp_CloseServiceHandle
0x18002ab0f  test    r12, r12
0x18002ab12  jz      short loc_18002AB1D
0x18002ab14  mov     rcx, r12; hSCObject
0x18002ab17  call    cs:__imp_CloseServiceHandle
0x18002ab1d  mov     eax, esi
0x18002ab1f  add     rsp, 68h
0x18002ab23  pop     r15
0x18002ab25  pop     r14
0x18002ab27  pop     r13
0x18002ab29  pop     r12
0x18002ab2b  pop     rdi
0x18002ab2c  pop     rsi
0x18002ab2d  pop     rbx
0x18002ab2e  pop     rbp
0x18002ab2f  retn
0x18002ab30  mov     rbx, [r15+28h]
0x18002ab34  mov     rdi, r14
0x18002ab37  cmp     [rbx], r13b
0x18002ab3a  jz      short loc_18002AB9D
0x18002ab3c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002ab40  lea     rdx, aNtds_0; "NTDS"
0x18002ab47  mov     rcx, rbx; String1
0x18002ab4a  call    cs:__imp__stricmp
0x18002ab50  test    eax, eax
0x18002ab52  jz      short loc_18002AB81
0x18002ab54  mov     r8, r15
0x18002ab57  inc     r8; Size
0x18002ab5a  cmp     [rbx+r8], r13b
0x18002ab5e  jnz     short loc_18002AB57
0x18002ab60  mov     rdx, rbx; Src
0x18002ab63  mov     rcx, rdi; void *
0x18002ab66  call    memcpy_0
0x18002ab6b  mov     rax, r15
0x18002ab6e  inc     rax
0x18002ab71  cmp     [rbx+rax], r13b
0x18002ab75  jnz     short loc_18002AB6E
0x18002ab77  mov     [rax+rdi], r13b
0x18002ab7b  inc     rdi
0x18002ab7e  add     rdi, rax
0x18002ab81  mov     rax, r15
0x18002ab84  inc     rax
0x18002ab87  cmp     [rbx+rax], r13b
0x18002ab8b  jnz     short loc_18002AB84
0x18002ab8d  inc     rbx
0x18002ab90  add     rbx, rax
0x18002ab93  cmp     [rbx], r13b
0x18002ab96  jnz     short loc_18002AB40
0x18002ab98  cmp     rdi, r14
0x18002ab9b  jnz     short loc_18002ABA3
0x18002ab9d  mov     [rdi], r13b
0x18002aba0  inc     rdi
0x18002aba3  mov     rbx, [rbp+hService]
0x18002aba7  or      edx, 0FFFFFFFFh; dwServiceType
0x18002abaa  mov     [rsp+68h+lpDisplayName], r13; lpDisplayName
0x18002abaf  mov     r9d, edx; dwErrorControl
0x18002abb2  mov     [rsp+68h+lpPassword], r13; lpPassword
0x18002abb7  mov     r8d, edx; dwStartType
0x18002abba  mov     [rsp+68h+lpServiceStartName], r13; lpServiceStartName
0x18002abbf  mov     rcx, rbx; hService
0x18002abc2  mov     [rsp+68h+lpDependencies], r14; lpDependencies
0x18002abc7  mov     [rsp+68h+lpdwTagId], r13; lpdwTagId
0x18002abcc  mov     [rsp+68h+lpLoadOrderGroup], r13; lpLoadOrderGroup
0x18002abd1  mov     [rsp+68h+lpBinaryPathName], r13; lpBinaryPathName
0x18002abd6  mov     [rdi], r13b
0x18002abd9  call    cs:__imp_ChangeServiceConfigA
0x18002abdf  test    eax, eax
0x18002abe1  jnz     loc_18002AAE7
0x18002abe7  jmp     loc_18002AA12
```
