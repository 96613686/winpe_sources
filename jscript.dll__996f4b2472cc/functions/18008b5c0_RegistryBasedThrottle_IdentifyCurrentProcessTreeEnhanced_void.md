# RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)

- ea: `0x18008b5c0`
- end: `0x18008bb43`
- name: `?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ`
- size: `1411`
- prototype: `void __fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007cce0`
- `0x18008af00`

## callees

- `0x180058610`
- `0x18005925c`
- `0x18008b150`
- `0x18008b5c0`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!_mbsnbcpy_s` at `0x18008b9be`
- `msvcrt!_mbsnbcpy_s` at `0x18008b9be`
- `msvcrt!_snprintf_s` at `0x18008ba4a`
- `msvcrt!_snprintf_s` at `0x18008baa2`
- `msvcrt!_snprintf_s` at `0x18008ba4a`
- `msvcrt!_snprintf_s` at `0x18008baa2`
- `msvcrt!strcat_s` at `0x18008b771`
- `msvcrt!strcat_s` at `0x18008b789`
- `msvcrt!strcat_s` at `0x18008bafd`
- `msvcrt!strcat_s` at `0x18008bb18`
- `msvcrt!strcat_s` at `0x18008b771`
- `msvcrt!strcat_s` at `0x18008b789`
- `msvcrt!strcat_s` at `0x18008bafd`
- `msvcrt!strcat_s` at `0x18008bb18`
- `msvcrt!_mbsicmp` at `0x18008b7f7`
- `msvcrt!_mbsicmp` at `0x18008b7f7`
- `KERNEL32!Process32Next` at `0x18008b6a3`
- `KERNEL32!Process32Next` at `0x18008b6a3`
- `KERNEL32!LoadLibraryA` at `0x18008b82d`
- `KERNEL32!LoadLibraryA` at `0x18008b82d`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18008b667`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18008b667`
- `KERNEL32!OpenProcess` at `0x18008b7ba`
- `KERNEL32!OpenProcess` at `0x18008b7ba`
- `KERNEL32!Process32First` at `0x18008b683`
- `KERNEL32!Process32First` at `0x18008b683`
- `KERNEL32!FreeLibrary` at `0x18008b9e5`
- `KERNEL32!FreeLibrary` at `0x18008b9e5`
- `KERNEL32!CloseHandle` at `0x18008b6b6`
- `KERNEL32!CloseHandle` at `0x18008b7e0`
- `KERNEL32!CloseHandle` at `0x18008bb2a`
- `KERNEL32!CloseHandle` at `0x18008b6b6`
- `KERNEL32!CloseHandle` at `0x18008b7e0`
- `KERNEL32!CloseHandle` at `0x18008bb2a`
- `KERNEL32!GetProcAddress` at `0x18008b84f`
- `KERNEL32!GetProcAddress` at `0x18008b868`
- `KERNEL32!GetProcAddress` at `0x18008b881`
- `KERNEL32!GetProcAddress` at `0x18008b84f`
- `KERNEL32!GetProcAddress` at `0x18008b868`
- `KERNEL32!GetProcAddress` at `0x18008b881`
- `KERNEL32!GetCurrentProcessId` at `0x18008b5ef`
- `KERNEL32!GetCurrentProcessId` at `0x18008b5ef`

## string_xrefs

- `0x18008b81f`: `advapi32.dll`
- `0x18008b874`: `CloseServiceHandle`
- `0x18008b85b`: `EnumServicesStatusExA`
- `0x18008b845`: `OpenSCManagerA`

## pseudocode

```c
void __fastcall RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(RegistryBasedThrottle *this)
{
  RegistryBasedThrottle *v1; // rbx
  DWORD CurrentProcessId; // esi
  char *v3; // r14
  char *v4; // rdi
  HANDLE Toolhelp32Snapshot; // rax
  void *v6; // r13
  __int64 v7; // rcx
  __int64 v8; // rax
  HANDLE v9; // rax
  void *v10; // rbx
  HMODULE LibraryA; // rax
  HMODULE v12; // r15
  FARPROC ProcAddress; // rbx
  FARPROC v14; // rdi
  FARPROC v15; // rax
  void (__fastcall *v16)(__int64); // r12
  __int64 v17; // r14
  char *v18; // rbx
  unsigned int v19; // edx
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  RegistryBasedThrottle *v26; // [rsp+68h] [rbp-98h]
  char *v27; // [rsp+70h] [rbp-90h]
  char *v28; // [rsp+78h] [rbp-88h]
  PROCESSENTRY32 pe; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 Dst; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v31[255]; // [rsp+1B1h] [rbp+B1h] BYREF
  char Destination; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v33[511]; // [rsp+2B1h] [rbp+1B1h] BYREF
  char Buffer[768]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v1 = this;
  v26 = this;
  CurrentProcessId = GetCurrentProcessId();
  memset_0(&pe.cntUsage, 0, 0x12Cu);
  pe.dwSize = 304;
  v3 = (char *)v1 + 568;
  v27 = (char *)v1 + 568;
  v4 = (char *)v1 + 828;
  *((_BYTE *)v1 + 568) = 0;
  v28 = (char *)v1 + 828;
  *((_BYTE *)v1 + 828) = 0;
  if ( CurrentProcessId )
  {
    do
    {
      Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
      v6 = Toolhelp32Snapshot;
      if ( Toolhelp32Snapshot == (HANDLE)-1LL )
        break;
      if ( !Process32First(Toolhelp32Snapshot, &pe) )
        goto LABEL_6;
      while ( pe.th32ProcessID != CurrentProcessId )
      {
        if ( !Process32Next(v6, &pe) )
          goto LABEL_6;
      }
      v7 = -1;
      do
        ++v7;
      while ( pe.szExeFile[v7] );
      v8 = -1;
      do
        ++v8;
      while ( v3[v8] );
      if ( (unsigned __int64)(v7 + v8 + 1) >= 0x104 )
      {
LABEL_6:
        CloseHandle(v6);
        break;
      }
      if ( *v3 )
        strcat_s(v3, 0x104u, ";");
      strcat_s(v3, 0x104u, pe.szExeFile);
      Destination = 0;
      memset_0(v33, 0, sizeof(v33));
      v9 = OpenProcess(0x410u, 0, CurrentProcessId);
      v10 = v9;
      if ( v9 )
      {
        GetProcessCommandLine(v9, &Destination);
        CloseHandle(v10);
      }
      if ( _mbsicmp((const unsigned __int8 *)pe.szExeFile, "svchost.exe") )
        goto LABEL_40;
      memset_0(v31, 0, sizeof(v31));
      Dst = 0;
      LibraryA = LoadLibraryA("advapi32.dll");
      v12 = LibraryA;
      if ( LibraryA )
      {
        ProcAddress = GetProcAddress(LibraryA, "OpenSCManagerA");
        v14 = GetProcAddress(v12, "EnumServicesStatusExA");
        v15 = GetProcAddress(v12, "CloseServiceHandle");
        v16 = (void (__fastcall *)(__int64))v15;
        if ( ProcAddress && v14 && v15 )
        {
          v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, 0, 4);
          if ( v17 )
          {
            v25 = 0;
            LODWORD(v24) = 0;
            ((void (__fastcall *)(__int64, _QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64 *, char *, _QWORD, _QWORD))v14)(
              v17,
              0,
              48,
              3,
              0,
              v24,
              &v25,
              (char *)&v25 + 4,
              0,
              0);
            if ( (_DWORD)v25 )
            {
              v18 = (char *)operator new[]((unsigned int)v25, (const struct std::nothrow_t *)std::nothrow);
              if ( v18 )
              {
                if ( ((unsigned int (__fastcall *)(__int64, _QWORD, __int64, __int64, char *, _DWORD, unsigned __int64 *, char *, _QWORD, _QWORD))v14)(
                       v17,
                       0,
                       48,
                       3,
                       v18,
                       v25,
                       &v25,
                       (char *)&v25 + 4,
                       0,
                       0) )
                {
                  v19 = 0;
                  if ( HIDWORD(v25) )
                  {
                    while ( 1 )
                    {
                      v20 = 56LL * v19;
                      if ( *(_DWORD *)&v18[v20 + 44] == CurrentProcessId )
                        break;
                      if ( ++v19 >= HIDWORD(v25) )
                        goto LABEL_32;
                    }
                    _mbsnbcpy_s(&Dst, 0x100u, *(const unsigned __int8 **)&v18[v20 + 8], 0xFFFFFFFFFFFFFFFFuLL);
                  }
                }
LABEL_32:
                operator delete[](v18);
              }
            }
            v16(v17);
          }
          v3 = v27;
        }
        FreeLibrary(v12);
        v4 = v28;
      }
      if ( !Dst )
      {
LABEL_40:
        v21 = "%s(\"%s\")";
        if ( !Destination )
          v21 = "%s";
        _snprintf_s(Buffer, 0x300u, 0xFFFFFFFFFFFFFFFFuLL, v21, pe.szExeFile, &Destination);
      }
      else if ( Destination )
      {
        _snprintf_s(
          Buffer,
          0x300u,
          0xFFFFFFFFFFFFFFFFuLL,
          "%s(\"%s | %s\")",
          pe.szExeFile,
          (const char *)&Dst,
          &Destination);
      }
      else
      {
        _snprintf_s(Buffer, 0x300u, 0xFFFFFFFFFFFFFFFFuLL, "%s(\"%s\")", pe.szExeFile, &Dst);
      }
      v22 = -1;
      do
        ++v22;
      while ( Buffer[v22] );
      v23 = -1;
      do
        ++v23;
      while ( v4[v23] );
      if ( (unsigned __int64)(v23 + v22 + 2) < 0x1000 )
      {
        if ( *v4 )
          strcat_s(v4, 0x1000u, ";");
        strcat_s(v4, 0x1000u, Buffer);
      }
      CurrentProcessId = pe.th32ParentProcessID;
      CloseHandle(v6);
    }
    while ( CurrentProcessId );
    v1 = v26;
  }
  *((_QWORD *)v1 + 873) = v3;
  *((_QWORD *)v1 + 874) = v4;
  *((_DWORD *)v1 + 1753) = 1;
  *((_DWORD *)v1 + 1754) = 1;
}

```

## disassembly

```asm
0x18008b5c0  push    rbp
0x18008b5c2  push    rbx
0x18008b5c3  push    rsi
0x18008b5c4  push    rdi
0x18008b5c5  push    r14
0x18008b5c7  lea     rbp, [rsp-6C0h]
0x18008b5cf  sub     rsp, 7C0h
0x18008b5d6  mov     rax, cs:__security_cookie
0x18008b5dd  xor     rax, rsp
0x18008b5e0  mov     [rbp+6E0h+var_30], rax
0x18008b5e7  mov     rbx, rcx
0x18008b5ea  mov     [rsp+7E0h+var_778], rcx
0x18008b5ef  call    cs:__imp_GetCurrentProcessId
0x18008b5f6  nop     dword ptr [rax+rax+00h]
0x18008b5fb  xor     edx, edx; Val
0x18008b5fd  lea     rcx, [rbp+6E0h+pe.cntUsage]; void *
0x18008b601  mov     r8d, 12Ch; Size
0x18008b607  mov     esi, eax
0x18008b609  call    memset_0
0x18008b60e  mov     [rbp+6E0h+pe.dwSize], 130h
0x18008b615  lea     r14, [rbx+238h]
0x18008b61c  mov     [rsp+7E0h+var_770], r14
0x18008b621  lea     rdi, [rbx+33Ch]
0x18008b628  mov     byte ptr [r14], 0
0x18008b62c  mov     [rsp+7E0h+var_768], rdi
0x18008b631  mov     byte ptr [rdi], 0
0x18008b634  test    esi, esi
0x18008b636  jz      loc_18008B6DF
0x18008b63c  mov     [rsp+7E0h+arg_8], r12
0x18008b644  lea     r12, aS_0; "%s"
0x18008b64b  mov     [rsp+7E0h+arg_10], r13
0x18008b653  mov     [rsp+7E0h+arg_18], r15
0x18008b65b  nop     dword ptr [rax+rax+00h]
0x18008b660  xor     edx, edx; th32ProcessID
0x18008b662  mov     ecx, 2; dwFlags
0x18008b667  call    cs:__imp_CreateToolhelp32Snapshot
0x18008b66e  nop     dword ptr [rax+rax+00h]
0x18008b673  mov     r13, rax
0x18008b676  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008b67a  jz      short loc_18008B6C2
0x18008b67c  lea     rdx, [rbp+6E0h+pe]; lppe
0x18008b680  mov     rcx, rax; hSnapshot
0x18008b683  call    cs:__imp_Process32First
0x18008b68a  nop     dword ptr [rax+rax+00h]
0x18008b68f  test    eax, eax
0x18008b691  jz      short loc_18008B6B3
0x18008b693  cmp     [rbp+6E0h+pe.th32ProcessID], esi
0x18008b696  jz      loc_18008B71F
0x18008b69c  lea     rdx, [rbp+6E0h+pe]; lppe
0x18008b6a0  mov     rcx, r13; hSnapshot
0x18008b6a3  call    cs:__imp_Process32Next
0x18008b6aa  nop     dword ptr [rax+rax+00h]
0x18008b6af  test    eax, eax
0x18008b6b1  jnz     short loc_18008B693
0x18008b6b3  mov     rcx, r13; hObject
0x18008b6b6  call    cs:__imp_CloseHandle
0x18008b6bd  nop     dword ptr [rax+rax+00h]
0x18008b6c2  mov     rbx, [rsp+7E0h+var_778]
0x18008b6c7  mov     r15, [rsp+7E0h+arg_18]
0x18008b6cf  mov     r12, [rsp+7E0h+arg_8]
0x18008b6d7  mov     r13, [rsp+7E0h+arg_10]
0x18008b6df  mov     [rbx+1B48h], r14
0x18008b6e6  mov     [rbx+1B50h], rdi
0x18008b6ed  mov     dword ptr [rbx+1B64h], 1
0x18008b6f7  mov     dword ptr [rbx+1B68h], 1
0x18008b701  mov     rcx, [rbp+6E0h+var_30]
0x18008b708  xor     rcx, rsp; StackCookie
0x18008b70b  call    __security_check_cookie
0x18008b710  add     rsp, 7C0h
0x18008b717  pop     r14
0x18008b719  pop     rdi
0x18008b71a  pop     rsi
0x18008b71b  pop     rbx
0x18008b71c  pop     rbp
0x18008b71d  retn
0x18008b71f  lea     rax, [rbp+6E0h+pe.szExeFile]
0x18008b723  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b72a  nop     word ptr [rax+rax+00h]
0x18008b730  inc     rcx
0x18008b733  cmp     byte ptr [rax+rcx], 0
0x18008b737  jnz     short loc_18008B730
0x18008b739  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18008b740  inc     rax
0x18008b743  cmp     byte ptr [r14+rax], 0
0x18008b748  jnz     short loc_18008B740
0x18008b74a  inc     rax
0x18008b74d  add     rax, rcx
0x18008b750  cmp     rax, 104h
0x18008b756  jnb     loc_18008B6B3
0x18008b75c  cmp     byte ptr [r14], 0
0x18008b760  jz      short loc_18008B77D
0x18008b762  lea     r8, asc_1800AA210; ";"
0x18008b769  mov     edx, 104h; SizeInBytes
0x18008b76e  mov     rcx, r14; Destination
0x18008b771  call    cs:__imp_strcat_s
0x18008b778  nop     dword ptr [rax+rax+00h]
0x18008b77d  lea     r8, [rbp+6E0h+pe.szExeFile]; Source
0x18008b781  mov     edx, 104h; SizeInBytes
0x18008b786  mov     rcx, r14; Destination
0x18008b789  call    cs:__imp_strcat_s
0x18008b790  nop     dword ptr [rax+rax+00h]
0x18008b795  xor     edx, edx; Val
0x18008b797  mov     [rbp+6E0h+Destination], 0
0x18008b79e  mov     r8d, 1FFh; Size
0x18008b7a4  lea     rcx, [rbp+6E0h+var_52F]; void *
0x18008b7ab  call    memset_0
0x18008b7b0  mov     r8d, esi; dwProcessId
0x18008b7b3  xor     edx, edx; bInheritHandle
0x18008b7b5  mov     ecx, 410h; dwDesiredAccess
0x18008b7ba  call    cs:__imp_OpenProcess
0x18008b7c1  nop     dword ptr [rax+rax+00h]
0x18008b7c6  mov     rbx, rax
0x18008b7c9  test    rax, rax
0x18008b7cc  jz      short loc_18008B7EC
0x18008b7ce  lea     rdx, [rbp+6E0h+Destination]; Destination
0x18008b7d5  mov     rcx, rax; hProcess
0x18008b7d8  call    GetProcessCommandLine
0x18008b7dd  mov     rcx, rbx; hObject
0x18008b7e0  call    cs:__imp_CloseHandle
0x18008b7e7  nop     dword ptr [rax+rax+00h]
0x18008b7ec  lea     rdx, aSvchostExe; "svchost.exe"
0x18008b7f3  lea     rcx, [rbp+6E0h+pe.szExeFile]; Str1
0x18008b7f7  call    cs:__imp__mbsicmp
0x18008b7fe  nop     dword ptr [rax+rax+00h]
0x18008b803  test    eax, eax
0x18008b805  jnz     loc_18008BA68
0x18008b80b  xor     edx, edx; Val
0x18008b80d  lea     rcx, [rbp+6E0h+var_62F]; void *
0x18008b814  mov     r8d, 0FFh; Size
0x18008b81a  call    memset_0
0x18008b81f  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18008b826  mov     [rbp+6E0h+Dst], 0
0x18008b82d  call    cs:__imp_LoadLibraryA
0x18008b834  nop     dword ptr [rax+rax+00h]
0x18008b839  mov     r15, rax
0x18008b83c  test    rax, rax
0x18008b83f  jz      loc_18008B9FD
0x18008b845  lea     rdx, aOpenscmanagera; "OpenSCManagerA"
0x18008b84c  mov     rcx, rax; hModule
0x18008b84f  call    cs:__imp_GetProcAddress
0x18008b856  nop     dword ptr [rax+rax+00h]
0x18008b85b  lea     rdx, aEnumservicesst; "EnumServicesStatusExA"
0x18008b862  mov     rcx, r15; hModule
0x18008b865  mov     rbx, rax
0x18008b868  call    cs:__imp_GetProcAddress
0x18008b86f  nop     dword ptr [rax+rax+00h]
0x18008b874  lea     rdx, aCloseserviceha; "CloseServiceHandle"
0x18008b87b  mov     rcx, r15; hModule
0x18008b87e  mov     rdi, rax
0x18008b881  call    cs:__imp_GetProcAddress
0x18008b888  nop     dword ptr [rax+rax+00h]
0x18008b88d  mov     r12, rax
0x18008b890  test    rbx, rbx
0x18008b893  jz      loc_18008B9E2
0x18008b899  test    rdi, rdi
0x18008b89c  jz      loc_18008B9E2
0x18008b8a2  test    rax, rax
0x18008b8a5  jz      loc_18008B9E2
0x18008b8ab  xor     edx, edx
0x18008b8ad  xor     ecx, ecx
0x18008b8af  mov     r8d, 4
0x18008b8b5  mov     rax, rbx
0x18008b8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b8bd  mov     r14, rax
0x18008b8c0  test    rax, rax
0x18008b8c3  jz      loc_18008B9DD
0x18008b8c9  xor     ecx, ecx
0x18008b8cb  lea     rax, [rsp+7E0h+var_780+4]
0x18008b8d0  mov     [rsp+7E0h+var_798], rcx
0x18008b8d5  xor     edx, edx
0x18008b8d7  mov     [rsp+7E0h+var_7A0], rcx
0x18008b8dc  mov     r9d, 3
0x18008b8e2  mov     [rsp+7E0h+var_7A8], rax
0x18008b8e7  mov     r8d, 30h ; '0'
0x18008b8ed  lea     rax, [rsp+7E0h+var_780]
0x18008b8f2  mov     dword ptr [rsp+7E0h+var_780], ecx
0x18008b8f6  mov     [rsp+7E0h+var_7B0], rax
0x18008b8fb  mov     rax, rdi
0x18008b8fe  mov     dword ptr [rsp+7E0h+var_7B8], ecx
0x18008b902  mov     [rsp+7E0h+var_7C0], rcx
0x18008b907  mov     dword ptr [rsp+7E0h+var_780+4], ecx
0x18008b90b  mov     rcx, r14
0x18008b90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b913  mov     eax, dword ptr [rsp+7E0h+var_780]
0x18008b917  test    eax, eax
0x18008b919  jz      loc_18008B9D2
0x18008b91f  mov     ecx, eax; unsigned __int64
0x18008b921  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008b928  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008b92d  mov     rbx, rax
0x18008b930  test    rax, rax
0x18008b933  jz      loc_18008B9D2
0x18008b939  mov     ecx, dword ptr [rsp+7E0h+var_780]
0x18008b93d  xor     eax, eax
0x18008b93f  mov     [rsp+7E0h+var_798], rax
0x18008b944  xor     edx, edx
0x18008b946  mov     [rsp+7E0h+var_7A0], rax
0x18008b94b  mov     r9d, 3
0x18008b951  lea     rax, [rsp+7E0h+var_780+4]
0x18008b956  mov     r8d, 30h ; '0'
0x18008b95c  mov     [rsp+7E0h+var_7A8], rax
0x18008b961  lea     rax, [rsp+7E0h+var_780]
0x18008b966  mov     [rsp+7E0h+var_7B0], rax
0x18008b96b  mov     rax, rdi
0x18008b96e  mov     dword ptr [rsp+7E0h+var_7B8], ecx
0x18008b972  mov     rcx, r14
0x18008b975  mov     [rsp+7E0h+var_7C0], rbx
0x18008b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b97f  test    eax, eax
0x18008b981  jz      short loc_18008B9CA
0x18008b983  mov     r9d, dword ptr [rsp+7E0h+var_780+4]
0x18008b988  xor     edx, edx
0x18008b98a  test    r9d, r9d
0x18008b98d  jz      short loc_18008B9CA
0x18008b98f  nop
0x18008b990  mov     eax, edx
0x18008b992  imul    r8, rax, 38h ; '8'
0x18008b996  cmp     [r8+rbx+2Ch], esi
0x18008b99b  jz      short loc_18008B9A6
0x18008b99d  inc     edx
0x18008b99f  cmp     edx, r9d
0x18008b9a2  jb      short loc_18008B990
0x18008b9a4  jmp     short loc_18008B9CA
0x18008b9a6  mov     r8, [r8+rbx+8]; Src
0x18008b9ab  lea     rcx, [rbp+6E0h+Dst]; Dst
0x18008b9b2  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18008b9b9  mov     edx, 100h; SizeInBytes
0x18008b9be  call    cs:__imp__mbsnbcpy_s
0x18008b9c5  nop     dword ptr [rax+rax+00h]
0x18008b9ca  mov     rcx, rbx; Block
0x18008b9cd  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18008b9d2  mov     rcx, r14
0x18008b9d5  mov     rax, r12
0x18008b9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b9dd  mov     r14, [rsp+7E0h+var_770]
0x18008b9e2  mov     rcx, r15; hLibModule
0x18008b9e5  call    cs:__imp_FreeLibrary
0x18008b9ec  nop     dword ptr [rax+rax+00h]
0x18008b9f1  mov     rdi, [rsp+7E0h+var_768]
0x18008b9f6  lea     r12, aS_0; "%s"
0x18008b9fd  cmp     [rbp+6E0h+Dst], 0
0x18008ba04  jz      short loc_18008BA68
0x18008ba06  cmp     [rbp+6E0h+Destination], 0
0x18008ba0d  lea     rcx, [rbp+6E0h+Buffer]; Buffer
0x18008ba14  mov     edx, 300h; BufferCount
0x18008ba19  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18008ba20  jz      short loc_18008BA58
0x18008ba22  lea     rax, [rbp+6E0h+Destination]
0x18008ba29  mov     [rsp+7E0h+var_7B0], rax
0x18008ba2e  lea     r9, aSSS; "%s(\"%s | %s\")"
0x18008ba35  lea     rax, [rbp+6E0h+Dst]
0x18008ba3c  mov     [rsp+7E0h+var_7B8], rax
0x18008ba41  lea     rax, [rbp+6E0h+pe.szExeFile]
0x18008ba45  mov     [rsp+7E0h+var_7C0], rax
0x18008ba4a  call    cs:__imp__snprintf_s
0x18008ba51  nop     dword ptr [rax+rax+00h]
0x18008ba56  jmp     short loc_18008BAAE
0x18008ba58  lea     rax, [rbp+6E0h+Dst]
0x18008ba5f  lea     r9, aSS_2; "%s(\"%s\")"
0x18008ba66  jmp     short loc_18008BA94
0x18008ba68  cmp     [rbp+6E0h+Destination], 0
0x18008ba6f  lea     r9, aSS_2; "%s(\"%s\")"
0x18008ba76  lea     rcx, [rbp+6E0h+Buffer]; Buffer
0x18008ba7d  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18008ba84  cmovz   r9, r12; Format
0x18008ba88  lea     rax, [rbp+6E0h+Destination]
0x18008ba8f  mov     edx, 300h; BufferCount
0x18008ba94  mov     [rsp+7E0h+var_7B8], rax
0x18008ba99  lea     rax, [rbp+6E0h+pe.szExeFile]
0x18008ba9d  mov     [rsp+7E0h+var_7C0], rax
0x18008baa2  call    cs:__imp__snprintf_s
0x18008baa9  nop     dword ptr [rax+rax+00h]
0x18008baae  lea     rax, [rbp+6E0h+Buffer]
0x18008bab5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008babc  nop     dword ptr [rax+00h]
0x18008bac0  inc     rcx
0x18008bac3  cmp     byte ptr [rax+rcx], 0
0x18008bac7  jnz     short loc_18008BAC0
0x18008bac9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18008bad0  inc     rax
0x18008bad3  cmp     byte ptr [rdi+rax], 0
0x18008bad7  jnz     short loc_18008BAD0
0x18008bad9  add     rcx, 2
0x18008badd  add     rcx, rax
0x18008bae0  cmp     rcx, 1000h
0x18008bae7  jnb     short loc_18008BB24
0x18008bae9  cmp     byte ptr [rdi], 0
0x18008baec  jz      short loc_18008BB09
0x18008baee  lea     r8, asc_1800AA210; ";"
0x18008baf5  mov     edx, 1000h; SizeInBytes
0x18008bafa  mov     rcx, rdi; Destination
0x18008bafd  call    cs:__imp_strcat_s
0x18008bb04  nop     dword ptr [rax+rax+00h]
0x18008bb09  lea     r8, [rbp+6E0h+Buffer]; Source
0x18008bb10  mov     edx, 1000h; SizeInBytes
0x18008bb15  mov     rcx, rdi; Destination
0x18008bb18  call    cs:__imp_strcat_s
0x18008bb1f  nop     dword ptr [rax+rax+00h]
0x18008bb24  mov     esi, [rbp+6E0h+pe.th32ParentProcessID]
0x18008bb27  mov     rcx, r13; hObject
  ... truncated ...
```
