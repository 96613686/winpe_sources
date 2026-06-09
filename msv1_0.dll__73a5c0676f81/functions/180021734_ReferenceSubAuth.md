# ReferenceSubAuth

- ea: `0x180021734`
- end: `0x180021ac3`
- name: `ReferenceSubAuth`
- size: `911`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180022220`
- `0x180036960`
- `0x180036b00`
- `0x180036c10`
- `0x180036c38`

## callees

- `0x180021734`
- `0x18002fb50`
- `0x180036d0c`
- `0x180036d68`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002191e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002191e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021950`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021963`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021976`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021989`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021950`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021963`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021976`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021989`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021a93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021a93`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800218fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800218fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800218a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800218a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021a80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021a80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002182f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002182f`
- `ntdll!RtlIntegerToChar` at `0x1800217f5`
- `ntdll!RtlIntegerToChar` at `0x1800217f5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800219f2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800219f2`
- `ntdll!RtlReleaseResource` at `0x1800217c4`
- `ntdll!RtlReleaseResource` at `0x180021a2c`
- `ntdll!RtlReleaseResource` at `0x1800217c4`
- `ntdll!RtlReleaseResource` at `0x180021a2c`
- `ntdll!RtlAcquireResourceShared` at `0x180021793`
- `ntdll!RtlAcquireResourceShared` at `0x180021793`

## pseudocode

```c
_QWORD *__fastcall ReferenceSubAuth(int a1, NTSTATUS *a2)
{
  _QWORD *v4; // rdi
  HMODULE v5; // r14
  __int64 v6; // rax
  NTSTATUS v7; // eax
  const CHAR *v8; // rdx
  LSTATUS v9; // eax
  int v10; // r8d
  _QWORD *v11; // rbx
  HMODULE Library; // rax
  __int64 v13; // rbx
  char v14; // al
  int v15; // r8d
  const CHAR *v16; // rdx
  FARPROC ProcAddress; // rbx
  FARPROC v18; // r12
  FARPROC v19; // r13
  FARPROC v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  char LastError; // al
  int v25; // r8d
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  FARPROC v30; // [rsp+40h] [rbp-C0h]
  CHAR ValueName[8]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[272]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  hKey = 0;
  cbData = 0;
  v4 = 0;
  Type = 0;
  Data[0] = 0;
  v5 = 0;
  RtlAcquireResourceShared(&SubAuthenticationCritSect, 1u);
  v6 = SubAuthenticationDlls;
  while ( (__int64 *)v6 != &SubAuthenticationDlls )
  {
    v4 = (_QWORD *)v6;
    if ( *(_DWORD *)(v6 + 16) == a1 )
      break;
    v6 = *(_QWORD *)v6;
    v4 = 0;
  }
  RtlReleaseResource(&SubAuthenticationCritSect);
  if ( !v4 )
  {
    strcpy(ValueName, "Auth");
    v7 = RtlIntegerToChar(a1 & 0x7FFFFFFF, 0xAu, 4u, &ValueName[4]);
    *a2 = v7;
    if ( v7 >= 0 )
    {
      v8 = "SYSTEM\\CurrentControlSet\\Control\\Lsa\\MSV1_0";
      if ( a1 < 0 )
        v8 = "SYSTEM\\CurrentControlSet\\Control\\Lsa\\Kerberos";
      v9 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, v8, 0, 1u, &hKey);
      if ( v9 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
LABEL_38:
          *a2 = -1073741702;
          goto LABEL_39;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
LABEL_35:
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
          {
            v23 = v11[2];
            LastError = GetLastError();
            WPP_SF_sl(v23, 13, v25, (unsigned int)Data, LastError);
          }
          goto LABEL_38;
        }
        WPP_SF_sl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          v10,
          (unsigned int)"SYSTEM\\CurrentControlSet\\Control\\Lsa\\MSV1_0",
          v9);
LABEL_34:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_35;
      }
      cbData = 257;
      if ( RegQueryValueExA(hKey, ValueName, 0, &Type, Data, &cbData) )
        goto LABEL_34;
      if ( Type != 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4dfae3304c4a345cf2ea5346cdf1ae07_Traceguids, ValueName);
LABEL_18:
        *a2 = -1073741515;
        goto LABEL_39;
      }
      Library = LoadLibraryExA((LPCSTR)Data, 0, 0);
      v5 = Library;
      if ( !Library )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v14 = GetLastError();
          WPP_SF_sl(v13, 12, v15, (unsigned int)Data, v14);
        }
        goto LABEL_18;
      }
      v16 = "Msv1_0SubAuthenticationFilter";
      if ( (a1 & 0x7FFFFFFF) != 0 )
        v16 = "Msv1_0SubAuthenticationRoutine";
      ProcAddress = GetProcAddress(Library, v16);
      v18 = GetProcAddress(v5, "Msv1_0SubAuthenticationRoutineEx");
      v19 = GetProcAddress(v5, "Msv1_0SubAuthenticationFilterEx");
      v20 = GetProcAddress(v5, "Msv1_0SubAuthenticationRoutineGeneric");
      v30 = v20;
      if ( !ProcAddress && !v19 && !v18 && !v20 )
        goto LABEL_34;
      v21 = ((__int64 (__fastcall *)(__int64))qword_180088390)(56);
      v4 = (_QWORD *)v21;
      if ( v21 )
      {
        *(_DWORD *)(v21 + 16) = a1;
        *(_QWORD *)(v21 + 24) = ProcAddress;
        *(_QWORD *)(v21 + 32) = v18;
        *(_QWORD *)(v21 + 48) = v30;
        *(_QWORD *)(v21 + 40) = v19;
        RtlAcquireResourceExclusive(&SubAuthenticationCritSect, 1u);
        v22 = SubAuthenticationDlls;
        if ( *(__int64 **)(SubAuthenticationDlls + 8) != &SubAuthenticationDlls )
          __fastfail(3u);
        v4[1] = &SubAuthenticationDlls;
        *v4 = v22;
        *(_QWORD *)(v22 + 8) = v4;
        SubAuthenticationDlls = (__int64)v4;
        RtlReleaseResource(&SubAuthenticationCritSect);
        v5 = 0;
      }
      else
      {
        *a2 = -1073741801;
      }
    }
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  if ( *a2 < 0 && v5 )
    FreeLibrary(v5);
  return v4;
}

```

## disassembly

```asm
0x180021734  mov     [rsp-8+arg_10], rbx
0x180021739  push    rbp
0x18002173a  push    rsi
0x18002173b  push    rdi
0x18002173c  push    r12
0x18002173e  push    r13
0x180021740  push    r14
0x180021742  push    r15
0x180021744  lea     rbp, [rsp-70h]
0x180021749  sub     rsp, 170h
0x180021750  mov     rax, cs:__security_cookie
0x180021757  xor     rax, rsp
0x18002175a  mov     [rbp+0A0h+var_40], rax
0x18002175e  xor     r12d, r12d
0x180021761  mov     rsi, rdx
0x180021764  mov     r15d, ecx
0x180021767  mov     [rdx], r12d
0x18002176a  lea     rcx, SubAuthenticationCritSect; Resource
0x180021771  mov     [rsp+1A0h+hKey], r12
0x180021776  mov     [rsp+1A0h+cbData], r12d
0x18002177b  mov     edi, r12d
0x18002177e  lea     r13d, [r12+1]
0x180021783  mov     [rsp+1A0h+Type], r12d
0x180021788  mov     dl, r13b; Wait
0x18002178b  mov     [rsp+1A0h+Data], r12b
0x180021790  mov     r14d, r12d
0x180021793  call    cs:__imp_RtlAcquireResourceShared
0x180021799  mov     rax, cs:SubAuthenticationDlls
0x1800217a0  lea     rcx, SubAuthenticationDlls
0x1800217a7  jmp     short loc_1800217B8
0x1800217a9  mov     rdi, rax
0x1800217ac  cmp     [rax+10h], r15d
0x1800217b0  jz      short loc_1800217BD
0x1800217b2  mov     rax, [rax]
0x1800217b5  mov     rdi, r12
0x1800217b8  cmp     rax, rcx
0x1800217bb  jnz     short loc_1800217A9
0x1800217bd  lea     rcx, SubAuthenticationCritSect; Resource
0x1800217c4  call    cs:__imp_RtlReleaseResource
0x1800217ca  test    rdi, rdi
0x1800217cd  jnz     loc_180021A76
0x1800217d3  mov     ebx, r15d
0x1800217d6  mov     dword ptr [rsp+1A0h+ValueName], 68747541h
0x1800217de  btr     ebx, 1Fh
0x1800217e2  mov     [rsp+1A0h+String], r12b
0x1800217e7  mov     ecx, ebx; Value
0x1800217e9  lea     r9, [rsp+1A0h+String]; String
0x1800217ee  lea     edx, [rdi+0Ah]; Base
0x1800217f1  lea     r8d, [rdi+4]; Length
0x1800217f5  call    cs:__imp_RtlIntegerToChar
0x1800217fb  mov     [rsi], eax
0x1800217fd  test    eax, eax
0x1800217ff  js      loc_180021A76
0x180021805  xor     r8d, r8d; ulOptions
0x180021808  lea     rax, [rsp+1A0h+hKey]
0x18002180d  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180021812  mov     r9d, r13d; samDesired
0x180021815  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18002181c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021823  test    r15d, r15d
0x180021826  jns     short loc_18002182F
0x180021828  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18002182f  call    cs:__imp_RegOpenKeyExA
0x180021835  lea     r13, WPP_GLOBAL_Control
0x18002183c  test    eax, eax
0x18002183e  jz      short loc_180021878
0x180021840  mov     rbx, cs:WPP_GLOBAL_Control
0x180021847  cmp     rbx, r13
0x18002184a  jz      loc_180021A70
0x180021850  test    byte ptr [rbx+1Ch], 8
0x180021854  jz      loc_180021A45
0x18002185a  mov     rcx, [rbx+10h]
0x18002185e  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180021865  mov     edx, 0Ah
0x18002186a  mov     dword ptr [rsp+1A0h+phkResult], eax
0x18002186e  call    WPP_SF_sl
0x180021873  jmp     loc_180021A3E
0x180021878  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18002187d  lea     rax, [rsp+1A0h+cbData]
0x180021882  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180021887  lea     r9, [rsp+1A0h+Type]; lpType
0x18002188c  lea     rax, [rsp+1A0h+Data]
0x180021891  mov     [rsp+1A0h+cbData], 101h
0x180021899  xor     r8d, r8d; lpReserved
0x18002189c  mov     [rsp+1A0h+phkResult], rax; lpData
0x1800218a1  lea     rdx, [rsp+1A0h+ValueName]; lpValueName
0x1800218a6  call    cs:__imp_RegQueryValueExA
0x1800218ac  test    eax, eax
0x1800218ae  jnz     loc_180021A3E
0x1800218b4  cmp     [rsp+1A0h+Type], 1
0x1800218b9  jz      short loc_1800218F0
0x1800218bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218c2  cmp     rcx, r13
0x1800218c5  jz      short loc_1800218E5
0x1800218c7  test    byte ptr [rcx+1Ch], 8
0x1800218cb  jz      short loc_1800218E5
0x1800218cd  mov     rcx, [rcx+10h]
0x1800218d1  lea     edx, [rax+0Bh]
0x1800218d4  lea     r9, [rsp+1A0h+ValueName]
0x1800218d9  lea     r8, WPP_4dfae3304c4a345cf2ea5346cdf1ae07_Traceguids
0x1800218e0  call    WPP_SF_s
0x1800218e5  mov     dword ptr [rsi], 0C0000135h
0x1800218eb  jmp     loc_180021A76
0x1800218f0  xor     r8d, r8d; dwFlags
0x1800218f3  lea     rcx, [rsp+1A0h+Data]; lpLibFileName
0x1800218f8  xor     edx, edx; hFile
0x1800218fa  call    cs:__imp_LoadLibraryExA
0x180021900  mov     r14, rax
0x180021903  test    rax, rax
0x180021906  jnz     short loc_18002193B
0x180021908  mov     rbx, cs:WPP_GLOBAL_Control
0x18002190f  cmp     rbx, r13
0x180021912  jz      short loc_1800218E5
0x180021914  test    byte ptr [rbx+1Ch], 8
0x180021918  jz      short loc_1800218E5
0x18002191a  mov     rbx, [rbx+10h]
0x18002191e  call    cs:__imp_GetLastError
0x180021924  lea     edx, [r14+0Ch]
0x180021928  mov     rcx, rbx
0x18002192b  lea     r9, [rsp+1A0h+Data]
0x180021930  mov     dword ptr [rsp+1A0h+phkResult], eax
0x180021934  call    WPP_SF_sl
0x180021939  jmp     short loc_1800218E5
0x18002193b  lea     rdx, aMsv10subauthen_2; "Msv1_0SubAuthenticationFilter"
0x180021942  mov     rcx, r14; hModule
0x180021945  test    ebx, ebx
0x180021947  jz      short loc_180021950
0x180021949  lea     rdx, ProcName; "Msv1_0SubAuthenticationRoutine"
0x180021950  call    cs:__imp_GetProcAddress
0x180021956  lea     rdx, aMsv10subauthen_3; "Msv1_0SubAuthenticationRoutineEx"
0x18002195d  mov     rcx, r14; hModule
0x180021960  mov     rbx, rax
0x180021963  call    cs:__imp_GetProcAddress
0x180021969  lea     rdx, aMsv10subauthen_0; "Msv1_0SubAuthenticationFilterEx"
0x180021970  mov     rcx, r14; hModule
0x180021973  mov     r12, rax
0x180021976  call    cs:__imp_GetProcAddress
0x18002197c  lea     rdx, aMsv10subauthen_4; "Msv1_0SubAuthenticationRoutineGeneric"
0x180021983  mov     rcx, r14; hModule
0x180021986  mov     r13, rax
0x180021989  call    cs:__imp_GetProcAddress
0x18002198f  mov     [rsp+1A0h+var_160], rax
0x180021994  test    rbx, rbx
0x180021997  jnz     short loc_1800219AC
0x180021999  test    r13, r13
0x18002199c  jnz     short loc_1800219AC
0x18002199e  test    r12, r12
0x1800219a1  jnz     short loc_1800219AC
0x1800219a3  test    rax, rax
0x1800219a6  jz      loc_180021A37
0x1800219ac  mov     rax, cs:qword_180088390
0x1800219b3  mov     ecx, 38h ; '8'
0x1800219b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219bd  mov     rdi, rax
0x1800219c0  test    rax, rax
0x1800219c3  jnz     short loc_1800219D0
0x1800219c5  mov     dword ptr [rsi], 0C0000017h
0x1800219cb  jmp     loc_180021A76
0x1800219d0  mov     [rax+10h], r15d
0x1800219d4  lea     rcx, SubAuthenticationCritSect; Resource
0x1800219db  mov     [rax+18h], rbx
0x1800219df  mov     dl, 1; Wait
0x1800219e1  mov     [rax+20h], r12
0x1800219e5  mov     rax, [rsp+1A0h+var_160]
0x1800219ea  mov     [rdi+30h], rax
0x1800219ee  mov     [rdi+28h], r13
0x1800219f2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800219f8  mov     rax, cs:SubAuthenticationDlls
0x1800219ff  lea     rcx, SubAuthenticationDlls
0x180021a06  cmp     [rax+8], rcx
0x180021a0a  jz      short loc_180021A13
0x180021a0c  mov     ecx, 3
0x180021a11  int     29h; Win8: RtlFailFast(ecx)
0x180021a13  mov     [rdi+8], rcx
0x180021a17  lea     rcx, SubAuthenticationCritSect; Resource
0x180021a1e  mov     [rdi], rax
0x180021a21  mov     [rax+8], rdi
0x180021a25  mov     cs:SubAuthenticationDlls, rdi
0x180021a2c  call    cs:__imp_RtlReleaseResource
0x180021a32  xor     r14d, r14d
0x180021a35  jmp     short loc_180021A76
0x180021a37  lea     r13, WPP_GLOBAL_Control
0x180021a3e  mov     rbx, cs:WPP_GLOBAL_Control
0x180021a45  cmp     rbx, r13
0x180021a48  jz      short loc_180021A70
0x180021a4a  test    byte ptr [rbx+1Ch], 8
0x180021a4e  jz      short loc_180021A70
0x180021a50  mov     rbx, [rbx+10h]
0x180021a54  call    cs:__imp_GetLastError
0x180021a5a  mov     edx, 0Dh
0x180021a5f  lea     r9, [rsp+1A0h+Data]
0x180021a64  mov     rcx, rbx
0x180021a67  mov     dword ptr [rsp+1A0h+phkResult], eax
0x180021a6b  call    WPP_SF_sl
0x180021a70  mov     dword ptr [rsi], 0C000007Ah
0x180021a76  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180021a7b  test    rcx, rcx
0x180021a7e  jz      short loc_180021A86
0x180021a80  call    cs:__imp_RegCloseKey
0x180021a86  cmp     dword ptr [rsi], 0
0x180021a89  jge     short loc_180021A99
0x180021a8b  test    r14, r14
0x180021a8e  jz      short loc_180021A99
0x180021a90  mov     rcx, r14; hLibModule
0x180021a93  call    cs:__imp_FreeLibrary
0x180021a99  mov     rax, rdi
0x180021a9c  mov     rcx, [rbp+0A0h+var_40]
0x180021aa0  xor     rcx, rsp; StackCookie
0x180021aa3  call    __security_check_cookie
0x180021aa8  mov     rbx, [rsp+1A0h+arg_10]
0x180021ab0  add     rsp, 170h
0x180021ab7  pop     r15
0x180021ab9  pop     r14
0x180021abb  pop     r13
0x180021abd  pop     r12
0x180021abf  pop     rdi
0x180021ac0  pop     rsi
0x180021ac1  pop     rbp
0x180021ac2  retn
```
