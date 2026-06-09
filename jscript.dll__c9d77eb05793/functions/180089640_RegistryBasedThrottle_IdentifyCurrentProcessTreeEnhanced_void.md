# RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)

- ea: `0x180089640`
- end: `0x180089b45`
- name: `?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ`
- size: `1285`
- prototype: `void __fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007b4b8`
- `0x180089030`

## callees

- `0x1800576e0`
- `0x18005830c`
- `0x180089240`
- `0x180089640`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!_mbsnbcpy_s` at `0x1800899ee`
- `msvcrt!_mbsnbcpy_s` at `0x1800899ee`
- `msvcrt!_snprintf_s` at `0x180089a6e`
- `msvcrt!_snprintf_s` at `0x180089ac0`
- `msvcrt!_snprintf_s` at `0x180089a6e`
- `msvcrt!_snprintf_s` at `0x180089ac0`
- `msvcrt!strcat_s` at `0x1800897d1`
- `msvcrt!strcat_s` at `0x1800897e3`
- `msvcrt!strcat_s` at `0x180089b11`
- `msvcrt!strcat_s` at `0x180089b26`
- `msvcrt!strcat_s` at `0x1800897d1`
- `msvcrt!strcat_s` at `0x1800897e3`
- `msvcrt!strcat_s` at `0x180089b11`
- `msvcrt!strcat_s` at `0x180089b26`
- `msvcrt!_mbsicmp` at `0x18008983f`
- `msvcrt!_mbsicmp` at `0x18008983f`
- `KERNEL32!Process32Next` at `0x180089713`
- `KERNEL32!Process32Next` at `0x180089713`
- `KERNEL32!LoadLibraryA` at `0x18008986f`
- `KERNEL32!LoadLibraryA` at `0x18008986f`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800896e7`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800896e7`
- `KERNEL32!OpenProcess` at `0x18008980e`
- `KERNEL32!OpenProcess` at `0x18008980e`
- `KERNEL32!Process32First` at `0x1800896fd`
- `KERNEL32!Process32First` at `0x1800896fd`
- `KERNEL32!FreeLibrary` at `0x180089a0f`
- `KERNEL32!FreeLibrary` at `0x180089a0f`
- `KERNEL32!CloseHandle` at `0x180089720`
- `KERNEL32!CloseHandle` at `0x18008982e`
- `KERNEL32!CloseHandle` at `0x180089b32`
- `KERNEL32!CloseHandle` at `0x180089720`
- `KERNEL32!CloseHandle` at `0x18008982e`
- `KERNEL32!CloseHandle` at `0x180089b32`
- `KERNEL32!GetProcAddress` at `0x18008988b`
- `KERNEL32!GetProcAddress` at `0x18008989e`
- `KERNEL32!GetProcAddress` at `0x1800898b1`
- `KERNEL32!GetProcAddress` at `0x18008988b`
- `KERNEL32!GetProcAddress` at `0x18008989e`
- `KERNEL32!GetProcAddress` at `0x1800898b1`
- `KERNEL32!GetCurrentProcessId` at `0x18008966f`
- `KERNEL32!GetCurrentProcessId` at `0x18008966f`

## string_xrefs

- `0x180089861`: `advapi32.dll`
- `0x1800898a4`: `CloseServiceHandle`
- `0x180089881`: `OpenSCManagerA`
- `0x180089891`: `EnumServicesStatusExA`

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
0x180089640  push    rbp
0x180089642  push    rbx
0x180089643  push    rsi
0x180089644  push    rdi
0x180089645  push    r14
0x180089647  lea     rbp, [rsp-6C0h]
0x18008964f  sub     rsp, 7C0h
0x180089656  mov     rax, cs:__security_cookie
0x18008965d  xor     rax, rsp
0x180089660  mov     [rbp+6E0h+var_30], rax
0x180089667  mov     rbx, rcx
0x18008966a  mov     [rsp+7E0h+var_778], rcx
0x18008966f  call    cs:__imp_GetCurrentProcessId
0x180089675  xor     edx, edx; Val
0x180089677  lea     rcx, [rbp+6E0h+pe.cntUsage]; void *
0x18008967b  mov     r8d, 12Ch; Size
0x180089681  mov     esi, eax
0x180089683  call    memset_0
0x180089688  mov     [rbp+6E0h+pe.dwSize], 130h
0x18008968f  lea     r14, [rbx+238h]
0x180089696  mov     [rsp+7E0h+var_770], r14
0x18008969b  lea     rdi, [rbx+33Ch]
0x1800896a2  mov     byte ptr [r14], 0
0x1800896a6  mov     [rsp+7E0h+var_768], rdi
0x1800896ab  mov     byte ptr [rdi], 0
0x1800896ae  test    esi, esi
0x1800896b0  jz      loc_180089743
0x1800896b6  mov     [rsp+7E0h+arg_8], r12
0x1800896be  lea     r12, aS_0; "%s"
0x1800896c5  mov     [rsp+7E0h+arg_10], r13
0x1800896cd  mov     [rsp+7E0h+arg_18], r15
0x1800896d5  nop     word ptr [rax+rax+00000000h]
0x1800896e0  xor     edx, edx; th32ProcessID
0x1800896e2  mov     ecx, 2; dwFlags
0x1800896e7  call    cs:__imp_CreateToolhelp32Snapshot
0x1800896ed  mov     r13, rax
0x1800896f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800896f4  jz      short loc_180089726
0x1800896f6  lea     rdx, [rbp+6E0h+pe]; lppe
0x1800896fa  mov     rcx, rax; hSnapshot
0x1800896fd  call    cs:__imp_Process32First
0x180089703  test    eax, eax
0x180089705  jz      short loc_18008971D
0x180089707  cmp     [rbp+6E0h+pe.th32ProcessID], esi
0x18008970a  jz      short loc_180089782
0x18008970c  lea     rdx, [rbp+6E0h+pe]; lppe
0x180089710  mov     rcx, r13; hSnapshot
0x180089713  call    cs:__imp_Process32Next
0x180089719  test    eax, eax
0x18008971b  jnz     short loc_180089707
0x18008971d  mov     rcx, r13; hObject
0x180089720  call    cs:__imp_CloseHandle
0x180089726  mov     rbx, [rsp+7E0h+var_778]
0x18008972b  mov     r15, [rsp+7E0h+arg_18]
0x180089733  mov     r12, [rsp+7E0h+arg_8]
0x18008973b  mov     r13, [rsp+7E0h+arg_10]
0x180089743  mov     [rbx+1B48h], r14
0x18008974a  mov     [rbx+1B50h], rdi
0x180089751  mov     dword ptr [rbx+1B64h], 1
0x18008975b  mov     dword ptr [rbx+1B68h], 1
0x180089765  mov     rcx, [rbp+6E0h+var_30]
0x18008976c  xor     rcx, rsp; StackCookie
0x18008976f  call    __security_check_cookie
0x180089774  add     rsp, 7C0h
0x18008977b  pop     r14
0x18008977d  pop     rdi
0x18008977e  pop     rsi
0x18008977f  pop     rbx
0x180089780  pop     rbp
0x180089781  retn
0x180089782  lea     rax, [rbp+6E0h+pe.szExeFile]
0x180089786  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008978d  nop     dword ptr [rax]
0x180089790  inc     rcx
0x180089793  cmp     byte ptr [rax+rcx], 0
0x180089797  jnz     short loc_180089790
0x180089799  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800897a0  inc     rax
0x1800897a3  cmp     byte ptr [r14+rax], 0
0x1800897a8  jnz     short loc_1800897A0
0x1800897aa  inc     rax
0x1800897ad  add     rax, rcx
0x1800897b0  cmp     rax, 104h
0x1800897b6  jnb     loc_18008971D
0x1800897bc  cmp     byte ptr [r14], 0
0x1800897c0  jz      short loc_1800897D7
0x1800897c2  lea     r8, asc_1800A82AC; ";"
0x1800897c9  mov     edx, 104h; SizeInBytes
0x1800897ce  mov     rcx, r14; Destination
0x1800897d1  call    cs:__imp_strcat_s
0x1800897d7  lea     r8, [rbp+6E0h+pe.szExeFile]; Source
0x1800897db  mov     edx, 104h; SizeInBytes
0x1800897e0  mov     rcx, r14; Destination
0x1800897e3  call    cs:__imp_strcat_s
0x1800897e9  xor     edx, edx; Val
0x1800897eb  mov     [rbp+6E0h+Destination], 0
0x1800897f2  mov     r8d, 1FFh; Size
0x1800897f8  lea     rcx, [rbp+6E0h+var_52F]; void *
0x1800897ff  call    memset_0
0x180089804  mov     r8d, esi; dwProcessId
0x180089807  xor     edx, edx; bInheritHandle
0x180089809  mov     ecx, 410h; dwDesiredAccess
0x18008980e  call    cs:__imp_OpenProcess
0x180089814  mov     rbx, rax
0x180089817  test    rax, rax
0x18008981a  jz      short loc_180089834
0x18008981c  lea     rdx, [rbp+6E0h+Destination]; Destination
0x180089823  mov     rcx, rax; hProcess
0x180089826  call    GetProcessCommandLine
0x18008982b  mov     rcx, rbx; hObject
0x18008982e  call    cs:__imp_CloseHandle
0x180089834  lea     rdx, aSvchostExe; "svchost.exe"
0x18008983b  lea     rcx, [rbp+6E0h+pe.szExeFile]; Str1
0x18008983f  call    cs:__imp__mbsicmp
0x180089845  test    eax, eax
0x180089847  jnz     loc_180089A86
0x18008984d  xor     edx, edx; Val
0x18008984f  lea     rcx, [rbp+6E0h+var_62F]; void *
0x180089856  mov     r8d, 0FFh; Size
0x18008985c  call    memset_0
0x180089861  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180089868  mov     [rbp+6E0h+Dst], 0
0x18008986f  call    cs:__imp_LoadLibraryA
0x180089875  mov     r15, rax
0x180089878  test    rax, rax
0x18008987b  jz      loc_180089A21
0x180089881  lea     rdx, aOpenscmanagera; "OpenSCManagerA"
0x180089888  mov     rcx, rax; hModule
0x18008988b  call    cs:__imp_GetProcAddress
0x180089891  lea     rdx, aEnumservicesst; "EnumServicesStatusExA"
0x180089898  mov     rcx, r15; hModule
0x18008989b  mov     rbx, rax
0x18008989e  call    cs:__imp_GetProcAddress
0x1800898a4  lea     rdx, aCloseserviceha; "CloseServiceHandle"
0x1800898ab  mov     rcx, r15; hModule
0x1800898ae  mov     rdi, rax
0x1800898b1  call    cs:__imp_GetProcAddress
0x1800898b7  mov     r12, rax
0x1800898ba  test    rbx, rbx
0x1800898bd  jz      loc_180089A0C
0x1800898c3  test    rdi, rdi
0x1800898c6  jz      loc_180089A0C
0x1800898cc  test    rax, rax
0x1800898cf  jz      loc_180089A0C
0x1800898d5  xor     edx, edx
0x1800898d7  xor     ecx, ecx
0x1800898d9  mov     r8d, 4
0x1800898df  mov     rax, rbx
0x1800898e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800898e7  mov     r14, rax
0x1800898ea  test    rax, rax
0x1800898ed  jz      loc_180089A07
0x1800898f3  xor     ecx, ecx
0x1800898f5  lea     rax, [rsp+7E0h+var_780+4]
0x1800898fa  mov     [rsp+7E0h+var_798], rcx
0x1800898ff  xor     edx, edx
0x180089901  mov     [rsp+7E0h+var_7A0], rcx
0x180089906  mov     r9d, 3
0x18008990c  mov     [rsp+7E0h+var_7A8], rax
0x180089911  mov     r8d, 30h ; '0'
0x180089917  lea     rax, [rsp+7E0h+var_780]
0x18008991c  mov     dword ptr [rsp+7E0h+var_780], ecx
0x180089920  mov     [rsp+7E0h+var_7B0], rax
0x180089925  mov     rax, rdi
0x180089928  mov     dword ptr [rsp+7E0h+var_7B8], ecx
0x18008992c  mov     [rsp+7E0h+var_7C0], rcx
0x180089931  mov     dword ptr [rsp+7E0h+var_780+4], ecx
0x180089935  mov     rcx, r14
0x180089938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008993d  mov     eax, dword ptr [rsp+7E0h+var_780]
0x180089941  test    eax, eax
0x180089943  jz      loc_1800899FC
0x180089949  mov     ecx, eax; unsigned __int64
0x18008994b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180089952  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180089957  mov     rbx, rax
0x18008995a  test    rax, rax
0x18008995d  jz      loc_1800899FC
0x180089963  mov     ecx, dword ptr [rsp+7E0h+var_780]
0x180089967  xor     eax, eax
0x180089969  mov     [rsp+7E0h+var_798], rax
0x18008996e  xor     edx, edx
0x180089970  mov     [rsp+7E0h+var_7A0], rax
0x180089975  mov     r9d, 3
0x18008997b  lea     rax, [rsp+7E0h+var_780+4]
0x180089980  mov     r8d, 30h ; '0'
0x180089986  mov     [rsp+7E0h+var_7A8], rax
0x18008998b  lea     rax, [rsp+7E0h+var_780]
0x180089990  mov     [rsp+7E0h+var_7B0], rax
0x180089995  mov     rax, rdi
0x180089998  mov     dword ptr [rsp+7E0h+var_7B8], ecx
0x18008999c  mov     rcx, r14
0x18008999f  mov     [rsp+7E0h+var_7C0], rbx
0x1800899a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800899a9  test    eax, eax
0x1800899ab  jz      short loc_1800899F4
0x1800899ad  mov     r9d, dword ptr [rsp+7E0h+var_780+4]
0x1800899b2  xor     edx, edx
0x1800899b4  test    r9d, r9d
0x1800899b7  jz      short loc_1800899F4
0x1800899b9  nop     dword ptr [rax+00000000h]
0x1800899c0  mov     eax, edx
0x1800899c2  imul    r8, rax, 38h ; '8'
0x1800899c6  cmp     [r8+rbx+2Ch], esi
0x1800899cb  jz      short loc_1800899D6
0x1800899cd  inc     edx
0x1800899cf  cmp     edx, r9d
0x1800899d2  jb      short loc_1800899C0
0x1800899d4  jmp     short loc_1800899F4
0x1800899d6  mov     r8, [r8+rbx+8]; Src
0x1800899db  lea     rcx, [rbp+6E0h+Dst]; Dst
0x1800899e2  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800899e9  mov     edx, 100h; SizeInBytes
0x1800899ee  call    cs:__imp__mbsnbcpy_s
0x1800899f4  mov     rcx, rbx; Block
0x1800899f7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800899fc  mov     rcx, r14
0x1800899ff  mov     rax, r12
0x180089a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a07  mov     r14, [rsp+7E0h+var_770]
0x180089a0c  mov     rcx, r15; hLibModule
0x180089a0f  call    cs:__imp_FreeLibrary
0x180089a15  mov     rdi, [rsp+7E0h+var_768]
0x180089a1a  lea     r12, aS_0; "%s"
0x180089a21  cmp     [rbp+6E0h+Dst], 0
0x180089a28  jz      short loc_180089A86
0x180089a2a  cmp     [rbp+6E0h+Destination], 0
0x180089a31  lea     rcx, [rbp+6E0h+Buffer]; Buffer
0x180089a38  mov     edx, 300h; BufferCount
0x180089a3d  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180089a44  jz      short loc_180089A76
0x180089a46  lea     rax, [rbp+6E0h+Destination]
0x180089a4d  mov     [rsp+7E0h+var_7B0], rax
0x180089a52  lea     r9, aSSS; "%s(\"%s | %s\")"
0x180089a59  lea     rax, [rbp+6E0h+Dst]
0x180089a60  mov     [rsp+7E0h+var_7B8], rax
0x180089a65  lea     rax, [rbp+6E0h+pe.szExeFile]
0x180089a69  mov     [rsp+7E0h+var_7C0], rax
0x180089a6e  call    cs:__imp__snprintf_s
0x180089a74  jmp     short loc_180089AC6
0x180089a76  lea     rax, [rbp+6E0h+Dst]
0x180089a7d  lea     r9, aSS_2; "%s(\"%s\")"
0x180089a84  jmp     short loc_180089AB2
0x180089a86  cmp     [rbp+6E0h+Destination], 0
0x180089a8d  lea     r9, aSS_2; "%s(\"%s\")"
0x180089a94  lea     rcx, [rbp+6E0h+Buffer]; Buffer
0x180089a9b  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180089aa2  cmovz   r9, r12; Format
0x180089aa6  lea     rax, [rbp+6E0h+Destination]
0x180089aad  mov     edx, 300h; BufferCount
0x180089ab2  mov     [rsp+7E0h+var_7B8], rax
0x180089ab7  lea     rax, [rbp+6E0h+pe.szExeFile]
0x180089abb  mov     [rsp+7E0h+var_7C0], rax
0x180089ac0  call    cs:__imp__snprintf_s
0x180089ac6  lea     rax, [rbp+6E0h+Buffer]
0x180089acd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180089ad4  inc     rcx
0x180089ad7  cmp     byte ptr [rax+rcx], 0
0x180089adb  jnz     short loc_180089AD4
0x180089add  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180089ae4  inc     rax
0x180089ae7  cmp     byte ptr [rdi+rax], 0
0x180089aeb  jnz     short loc_180089AE4
0x180089aed  add     rcx, 2
0x180089af1  add     rcx, rax
0x180089af4  cmp     rcx, 1000h
0x180089afb  jnb     short loc_180089B2C
0x180089afd  cmp     byte ptr [rdi], 0
0x180089b00  jz      short loc_180089B17
0x180089b02  lea     r8, asc_1800A82AC; ";"
0x180089b09  mov     edx, 1000h; SizeInBytes
0x180089b0e  mov     rcx, rdi; Destination
0x180089b11  call    cs:__imp_strcat_s
0x180089b17  lea     r8, [rbp+6E0h+Buffer]; Source
0x180089b1e  mov     edx, 1000h; SizeInBytes
0x180089b23  mov     rcx, rdi; Destination
0x180089b26  call    cs:__imp_strcat_s
0x180089b2c  mov     esi, [rbp+6E0h+pe.th32ParentProcessID]
0x180089b2f  mov     rcx, r13; hObject
0x180089b32  call    cs:__imp_CloseHandle
0x180089b38  test    esi, esi
0x180089b3a  jnz     loc_1800896E0
0x180089b40  jmp     loc_180089726
```
