# CRdlsDBManager::Initialize(void)

- ea: `0x18007e4d8`
- end: `0x18007e715`
- name: `?Initialize@CRdlsDBManager@@QEAAKXZ`
- size: `573`
- prototype: `DWORD __fastcall(CRdlsDBManager *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180020790`
- `0x18007e360`

## callees

- `0x18000205c`
- `0x180005665`
- `0x180022910`
- `0x18007e4d8`
- `0x18007eaa0`
- `0x18007ed10`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18007e559`
- `ADVAPI32!RegCreateKeyExW` at `0x18007e559`
- `ADVAPI32!RegQueryValueExW` at `0x18007e5d8`
- `ADVAPI32!RegQueryValueExW` at `0x18007e625`
- `ADVAPI32!RegQueryValueExW` at `0x18007e5d8`
- `ADVAPI32!RegQueryValueExW` at `0x18007e625`
- `KERNEL32!LoadLibraryW` at `0x18007e67b`
- `KERNEL32!LoadLibraryW` at `0x18007e67b`
- `KERNEL32!GetLastError` at `0x18007e68c`
- `KERNEL32!GetLastError` at `0x18007e68c`
- `KERNEL32!GetProcAddress` at `0x18007e6a4`
- `KERNEL32!GetProcAddress` at `0x18007e6a4`

## string_xrefs

- `0x18007e54b`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x18007e69a`: `CreateRdlsDbPluginFactory`
- `0x18007e61e`: `RdlsDBPlugin`

## pseudocode

```c
DWORD __fastcall CRdlsDBManager::Initialize(CRdlsDBManager *this)
{
  unsigned int v2; // eax
  CRdlsDBManager *v3; // rcx
  LSTATUS v4; // ebx
  CRdlsDBManager *v5; // rcx
  LSTATUS v6; // eax
  struct IRdlsDBFactory *v7; // rcx
  HMODULE LibraryW; // rax
  __int64 (*ProcAddress)(void); // rax
  DWORD v11; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DESCRIPTOR v15; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Data[256]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(Data, 0, sizeof(Data));
  Type[0] = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         0);
  if ( !v2 )
  {
    CRdlsDBManager::ReadDatabasePaths(v3, hKey);
    CRdlsDBManager::ReadMaxDBHandleCount(v5, hKey);
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"UseMultipleDBConnections", 0, Type, &g_bUseMultipleConnections, &cbData);
    cbData = 256;
    v11 = 0;
    if ( hKey && (v11 = 254, v6 = RegQueryValueExW(hKey, L"RdlsDBPlugin", 0, 0, (LPBYTE)Data, &v11), cbData = v11, v6) )
    {
      v7 = MsRdlsDBFactory::m_DBFactoryInstance;
      if ( MsRdlsDBFactory::m_DBFactoryInstance )
      {
LABEL_16:
        *((_QWORD *)this + 328) = (**(__int64 (__fastcall ***)(struct IRdlsDBFactory *, char *, char *, char *))v7)(
                                    v7,
                                    (char *)this + 1028,
                                    (char *)this + 2072,
                                    (char *)this + 1550);
        return v4;
      }
      v7 = (struct IRdlsDBFactory *)operator new(8u);
      *(_QWORD *)&v15.Id = v7;
      if ( v7 )
        *(_QWORD *)v7 = &MsRdlsDBFactory::`vftable';
      else
        v7 = 0;
      MsRdlsDBFactory::m_DBFactoryInstance = v7;
    }
    else
    {
      LibraryW = LoadLibraryW(Data);
      if ( !LibraryW )
        return GetLastError();
      ProcAddress = GetProcAddress(LibraryW, "CreateRdlsDbPluginFactory");
      if ( !ProcAddress )
        return GetLastError();
      v7 = (struct IRdlsDBFactory *)ProcAddress();
    }
    if ( !v7 )
      return 14;
    goto LABEL_16;
  }
  v15 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
  TLSLogEvent(&v15, 0xC0010014, v2);
  return 4115;
}

```

## disassembly

```asm
0x18007e4d8  mov     [rsp-8+arg_8], rbx
0x18007e4dd  mov     [rsp-8+arg_10], rdi
0x18007e4e2  push    rbp
0x18007e4e3  lea     rbp, [rsp-190h]
0x18007e4eb  sub     rsp, 290h
0x18007e4f2  mov     rax, cs:__security_cookie
0x18007e4f9  xor     rax, rsp
0x18007e4fc  mov     [rbp+190h+var_10], rax
0x18007e503  mov     rdi, rcx
0x18007e506  xor     edx, edx; Val
0x18007e508  mov     r8d, 200h; Size
0x18007e50e  lea     rcx, [rbp+190h+Data]; void *
0x18007e512  call    memset_0
0x18007e517  and     [rsp+290h+Type], 0
0x18007e51c  and     [rsp+290h+hKey], 0
0x18007e522  and     [rsp+290h+var_250], 0
0x18007e528  lea     rax, [rsp+290h+hKey]
0x18007e52d  mov     [rsp+290h+phkResult], rax; phkResult
0x18007e532  and     [rsp+290h+var_260], 0
0x18007e538  mov     [rsp+290h+samDesired], 20019h; samDesired
0x18007e540  and     dword ptr [rsp+290h+lpData], 0
0x18007e545  xor     r9d, r9d; lpClass
0x18007e548  xor     r8d, r8d; Reserved
0x18007e54b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18007e552  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e559  call    cs:__imp_RegCreateKeyExW
0x18007e560  nop     dword ptr [rax+rax+00h]
0x18007e565  test    eax, eax
0x18007e567  jz      short loc_18007E592
0x18007e569  movups  xmm0, cs:TLS_E_SERVICEINIT
0x18007e570  movdqu  xmmword ptr [rsp+290h+var_220.Id], xmm0
0x18007e576  mov     r8d, eax
0x18007e579  mov     edx, 0C0010014h; unsigned int
0x18007e57e  lea     rcx, [rsp+290h+var_220]; struct _EVENT_DESCRIPTOR
0x18007e583  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18007e588  mov     ebx, 1013h
0x18007e58d  jmp     loc_18007E6EE
0x18007e592  mov     rdx, [rsp+290h+hKey]; HKEY
0x18007e597  call    ?ReadDatabasePaths@CRdlsDBManager@@QEAAKPEAUHKEY__@@@Z; CRdlsDBManager::ReadDatabasePaths(HKEY__ *)
0x18007e59c  mov     rdx, [rsp+290h+hKey]; HKEY
0x18007e5a1  call    ?ReadMaxDBHandleCount@CRdlsDBManager@@QEAAKPEAUHKEY__@@@Z; CRdlsDBManager::ReadMaxDBHandleCount(HKEY__ *)
0x18007e5a6  mov     [rsp+290h+cbData], 4
0x18007e5ae  lea     rax, [rsp+290h+cbData]
0x18007e5b3  mov     qword ptr [rsp+290h+samDesired], rax; lpcbData
0x18007e5b8  lea     rax, ?g_bUseMultipleConnections@@3KA; ulong g_bUseMultipleConnections
0x18007e5bf  mov     [rsp+290h+lpData], rax; lpData
0x18007e5c4  lea     r9, [rsp+290h+Type]; lpType
0x18007e5c9  xor     r8d, r8d; lpReserved
0x18007e5cc  lea     rdx, aUsemultipledbc; "UseMultipleDBConnections"
0x18007e5d3  mov     rcx, [rsp+290h+hKey]; hKey
0x18007e5d8  call    cs:__imp_RegQueryValueExW
0x18007e5df  nop     dword ptr [rax+rax+00h]
0x18007e5e4  mov     ebx, eax
0x18007e5e6  mov     [rsp+290h+cbData], 100h
0x18007e5ee  and     [rsp+290h+var_240], 0
0x18007e5f3  mov     rcx, [rsp+290h+hKey]; hKey
0x18007e5f8  test    rcx, rcx
0x18007e5fb  jz      short loc_18007E677
0x18007e5fd  mov     [rsp+290h+var_240], 0FEh
0x18007e605  lea     rax, [rsp+290h+var_240]
0x18007e60a  mov     qword ptr [rsp+290h+samDesired], rax; lpcbData
0x18007e60f  lea     rax, [rbp+190h+Data]
0x18007e613  mov     [rsp+290h+lpData], rax; lpData
0x18007e618  xor     r9d, r9d; lpType
0x18007e61b  xor     r8d, r8d; lpReserved
0x18007e61e  lea     rdx, aRdlsdbplugin; "RdlsDBPlugin"
0x18007e625  call    cs:__imp_RegQueryValueExW
0x18007e62c  nop     dword ptr [rax+rax+00h]
0x18007e631  mov     ecx, [rsp+290h+var_240]
0x18007e635  mov     [rsp+290h+cbData], ecx
0x18007e639  test    eax, eax
0x18007e63b  jz      short loc_18007E677
0x18007e63d  mov     rcx, cs:?m_DBFactoryInstance@MsRdlsDBFactory@@0PEAVIRdlsDBFactory@@EA; IRdlsDBFactory * MsRdlsDBFactory::m_DBFactoryInstance
0x18007e644  test    rcx, rcx
0x18007e647  jnz     short loc_18007E6C7
0x18007e649  mov     ecx, 8; Size
0x18007e64e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e653  mov     rcx, rax
0x18007e656  mov     qword ptr [rsp+290h+var_220.Id], rax
0x18007e65b  test    rax, rax
0x18007e65e  jz      short loc_18007E66C
0x18007e660  lea     rax, ??_7MsRdlsDBFactory@@6B@; const MsRdlsDBFactory::`vftable'
0x18007e667  mov     [rcx], rax
0x18007e66a  jmp     short loc_18007E66E
0x18007e66c  xor     ecx, ecx
0x18007e66e  mov     cs:?m_DBFactoryInstance@MsRdlsDBFactory@@0PEAVIRdlsDBFactory@@EA, rcx; IRdlsDBFactory * MsRdlsDBFactory::m_DBFactoryInstance
0x18007e675  jmp     short loc_18007E6BD
0x18007e677  lea     rcx, [rbp+190h+Data]; lpLibFileName
0x18007e67b  call    cs:__imp_LoadLibraryW
0x18007e682  nop     dword ptr [rax+rax+00h]
0x18007e687  test    rax, rax
0x18007e68a  jnz     short loc_18007E69A
0x18007e68c  call    cs:__imp_GetLastError
0x18007e693  nop     dword ptr [rax+rax+00h]
0x18007e698  jmp     short loc_18007E6F0
0x18007e69a  lea     rdx, aCreaterdlsdbpl; "CreateRdlsDbPluginFactory"
0x18007e6a1  mov     rcx, rax; hModule
0x18007e6a4  call    cs:__imp_GetProcAddress
0x18007e6ab  nop     dword ptr [rax+rax+00h]
0x18007e6b0  test    rax, rax
0x18007e6b3  jz      short loc_18007E68C
0x18007e6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6ba  mov     rcx, rax
0x18007e6bd  test    rcx, rcx
0x18007e6c0  jnz     short loc_18007E6C7
0x18007e6c2  lea     eax, [rcx+0Eh]
0x18007e6c5  jmp     short loc_18007E6F0
0x18007e6c7  mov     rax, [rcx]
0x18007e6ca  lea     r9, [rdi+60Eh]
0x18007e6d1  lea     r8, [rdi+818h]
0x18007e6d8  lea     rdx, [rdi+404h]
0x18007e6df  mov     rax, [rax]
0x18007e6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6e7  mov     [rdi+0A40h], rax
0x18007e6ee  mov     eax, ebx
0x18007e6f0  mov     rcx, [rbp+190h+var_10]
0x18007e6f7  xor     rcx, rsp; StackCookie
0x18007e6fa  call    __security_check_cookie
0x18007e6ff  lea     r11, [rsp+290h+var_s0]
0x18007e707  mov     rbx, [r11+18h]
0x18007e70b  mov     rdi, [r11+20h]
0x18007e70f  mov     rsp, r11
0x18007e712  pop     rbp
0x18007e713  retn
```
