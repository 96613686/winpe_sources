# RegisterLocalServer(_GUID,_GUID)

- ea: `0x14000c498`
- end: `0x14000c95e`
- name: `?RegisterLocalServer@@YAJU_GUID@@U1@@Z`
- size: `1222`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ca10`

## callees

- `0x140001af3`
- `0x140003da4`
- `0x140003ea4`
- `0x140004314`
- `0x14000c498`
- `0x14000d094`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x14000c751`
- `ADVAPI32!RegDeleteValueW` at `0x14000c751`
- `ADVAPI32!RegSetValueExW` at `0x14000c6e0`
- `ADVAPI32!RegSetValueExW` at `0x14000c7a3`
- `ADVAPI32!RegSetValueExW` at `0x14000c7e9`
- `ADVAPI32!RegSetValueExW` at `0x14000c6e0`
- `ADVAPI32!RegSetValueExW` at `0x14000c7a3`
- `ADVAPI32!RegSetValueExW` at `0x14000c7e9`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c625`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c6a1`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c72f`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c87d`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c8ca`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c625`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c6a1`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c72f`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c87d`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c8ca`
- `ADVAPI32!RegCloseKey` at `0x14000c7fc`
- `ADVAPI32!RegCloseKey` at `0x14000c821`
- `ADVAPI32!RegCloseKey` at `0x14000c832`
- `ADVAPI32!RegCloseKey` at `0x14000c8ed`
- `ADVAPI32!RegCloseKey` at `0x14000c8fe`
- `ADVAPI32!RegCloseKey` at `0x14000c7fc`
- `ADVAPI32!RegCloseKey` at `0x14000c821`
- `ADVAPI32!RegCloseKey` at `0x14000c832`
- `ADVAPI32!RegCloseKey` at `0x14000c8ed`
- `ADVAPI32!RegCloseKey` at `0x14000c8fe`
- `KERNEL32!GetCurrentProcess` at `0x14000c54e`
- `KERNEL32!GetCurrentProcess` at `0x14000c54e`
- `KERNEL32!GetModuleHandleW` at `0x14000c53f`
- `KERNEL32!GetModuleHandleW` at `0x14000c53f`
- `KERNEL32!K32GetModuleBaseNameW` at `0x14000c570`
- `KERNEL32!K32GetModuleBaseNameW` at `0x14000c570`
- `KERNEL32!GetLastError` at `0x14000c90c`
- `KERNEL32!GetLastError` at `0x14000c90c`
- `ole32!StringFromGUID2` at `0x14000c64d`
- `ole32!StringFromGUID2` at `0x14000c663`
- `ole32!StringFromGUID2` at `0x14000c64d`
- `ole32!StringFromGUID2` at `0x14000c663`

## string_xrefs

- `0x14000c5fc`: `CLSID`
- `0x14000c74a`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall RegisterLocalServer(GUID *rguid, GUID *a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE CurrentProcess; // rax
  int LastError; // ebx
  __int64 v7; // rdi
  __int64 v8; // rax
  bool v9; // cc
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v13; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v15; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR SubKey[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE v18[16]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v19; // [rsp+130h] [rbp+30h]
  __int128 v20; // [rsp+140h] [rbp+40h]
  __int128 v21; // [rsp+150h] [rbp+50h]
  int v22; // [rsp+160h] [rbp+60h]
  _BYTE v23[460]; // [rsp+164h] [rbp+64h] BYREF
  BYTE Data[2]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v25[526]; // [rsp+332h] [rbp+232h] BYREF
  WCHAR BaseName; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v27[526]; // [rsp+542h] [rbp+442h] BYREF

  *(_OWORD *)v18 = *(_OWORD *)L"%ProgramFiles%\\Internet Explorer\\";
  v19 = *(_OWORD *)L"Files%\\Internet Explorer\\";
  v20 = *(_OWORD *)L"nternet Explorer\\";
  v21 = *(_OWORD *)L"Explorer\\";
  v22 = *(_DWORD *)L"\\";
  memset_0(v23, 0, 0x1C4u);
  BaseName = 0;
  memset_0(v27, 0, 0x206u);
  dwDisposition = 0;
  ModuleHandleW = GetModuleHandleW(0);
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetModuleBaseNameW(CurrentProcess, ModuleHandleW, &BaseName, 0x104u) )
  {
    LastError = GetLastError();
    goto LABEL_22;
  }
  LastError = StringCchCatW((unsigned __int16 *)v18, 0x104u, &BaseName);
  if ( LastError < 0 )
    return (unsigned int)LastError;
  *(_WORD *)Data = 0;
  memset_0(v25, 0, 0x206u);
  LastError = QuotePath((const unsigned __int16 *)v18, 0x104u, (unsigned __int16 *)Data);
  if ( LastError < 0 )
    return (unsigned int)LastError;
  v15 = 0;
  hKey = 0;
  LastError = RegCreateKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( !LastError )
  {
    phkResult = 0;
    StringFromGUID2(rguid, sz, 39);
    StringFromGUID2(a2, SubKey, 39);
    LastError = RegCreateKeyExW(hKey, sz, 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
    if ( !LastError )
    {
      v13 = 0;
      LastError = RegSetValueExW(phkResult, L"AppID", 0, 1u, (const BYTE *)SubKey, 0x4Eu);
      if ( !LastError )
      {
        LastError = RegCreateKeyExW(
                      phkResult,
                      L"LocalServer32",
                      0,
                      (LPWSTR)L"REG_EXPAND_SZ",
                      0,
                      0xF003Fu,
                      0,
                      &v13,
                      &dwDisposition);
        if ( !LastError )
        {
          RegDeleteValueW(v13, L"ThreadingModel");
          v7 = -1;
          v8 = -1;
          do
            ++v8;
          while ( *(_WORD *)&Data[2 * v8] );
          LastError = RegSetValueExW(v13, &::Data, 0, 2u, Data, 2 * v8 + 2);
          if ( !LastError )
          {
            do
              ++v7;
            while ( *(_WORD *)&v18[2 * v7] );
            LastError = RegSetValueExW(v13, L"ServerExecutable", 0, 2u, v18, 2 * v7 + 2);
          }
          RegCloseKey(v13);
          if ( !LastError )
            LastError = RegisterCLSID(phkResult, (const unsigned __int16 *)v18);
        }
      }
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
    v9 = LastError <= 0;
    if ( LastError )
      goto LABEL_25;
    LastError = RegCreateKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &v15, &dwDisposition);
    if ( !LastError )
    {
      phkResult = 0;
      LastError = RegCreateKeyExW(v15, SubKey, 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
      if ( !LastError )
      {
        LastError = RegisterAppID(phkResult);
        RegCloseKey(phkResult);
      }
      RegCloseKey(v15);
LABEL_22:
      v9 = LastError <= 0;
      if ( !LastError )
        return 0;
      goto LABEL_25;
    }
  }
  v9 = LastError <= 0;
LABEL_25:
  if ( !v9 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000c498  mov     [rsp-8+arg_10], rbx
0x14000c49d  mov     [rsp-8+arg_18], rsi
0x14000c4a2  push    rbp
0x14000c4a3  push    rdi
0x14000c4a4  push    r12
0x14000c4a6  push    r14
0x14000c4a8  push    r15
0x14000c4aa  lea     rbp, [rsp-660h]
0x14000c4b2  sub     rsp, 760h
0x14000c4b9  mov     rax, cs:__security_cookie
0x14000c4c0  xor     rax, rsp
0x14000c4c3  mov     [rbp+680h+var_30], rax
0x14000c4ca  movaps  xmm0, xmmword ptr cs:aProgramfilesIn; "%ProgramFiles%\\Internet Explorer\\"
0x14000c4d1  mov     rsi, rdx
0x14000c4d4  movaps  xmm1, xmmword ptr cs:aProgramfilesIn+10h; "Files%\\Internet Explorer\\"
0x14000c4db  mov     rdi, rcx
0x14000c4de  mov     eax, dword ptr cs:aProgramfilesIn+40h; "\\"
0x14000c4e4  lea     rcx, [rbp+680h+var_61C]; void *
0x14000c4e8  movaps  xmmword ptr [rbp+680h+var_660], xmm0
0x14000c4ec  xor     edx, edx; Val
0x14000c4ee  movaps  xmm0, xmmword ptr cs:aProgramfilesIn+20h; "nternet Explorer\\"
0x14000c4f5  mov     r8d, 1C4h; Size
0x14000c4fb  movaps  [rbp+680h+var_650], xmm1
0x14000c4ff  movaps  xmm1, xmmword ptr cs:aProgramfilesIn+30h; "Explorer\\"
0x14000c506  movaps  [rbp+680h+var_640], xmm0
0x14000c50a  movaps  [rbp+680h+var_630], xmm1
0x14000c50e  mov     [rbp+680h+var_620], eax
0x14000c511  call    memset_0
0x14000c516  mov     r12d, 206h
0x14000c51c  lea     rcx, [rbp+680h+var_23E]; void *
0x14000c523  xor     r14d, r14d
0x14000c526  mov     r8d, r12d; Size
0x14000c529  xor     edx, edx; Val
0x14000c52b  mov     [rbp+680h+BaseName], r14w
0x14000c533  call    memset_0
0x14000c538  xor     ecx, ecx; lpModuleName
0x14000c53a  mov     [rsp+780h+dwDisposition], r14d
0x14000c53f  call    cs:__imp_GetModuleHandleW
0x14000c546  nop     dword ptr [rax+rax+00h]
0x14000c54b  mov     rbx, rax
0x14000c54e  call    cs:__imp_GetCurrentProcess
0x14000c555  nop     dword ptr [rax+rax+00h]
0x14000c55a  mov     r15d, 104h
0x14000c560  lea     r8, [rbp+680h+BaseName]; lpBaseName
0x14000c567  mov     r9d, r15d; nSize
0x14000c56a  mov     rcx, rax; hProcess
0x14000c56d  mov     rdx, rbx; hModule
0x14000c570  call    cs:__imp_K32GetModuleBaseNameW
0x14000c577  nop     dword ptr [rax+rax+00h]
0x14000c57c  test    eax, eax
0x14000c57e  jz      loc_14000C90C
0x14000c584  lea     r8, [rbp+680h+BaseName]; unsigned __int16 *
0x14000c58b  mov     edx, r15d; unsigned __int64
0x14000c58e  lea     rcx, [rbp+680h+var_660]; unsigned __int16 *
0x14000c592  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c597  mov     ebx, eax
0x14000c599  test    eax, eax
0x14000c59b  js      loc_14000C930
0x14000c5a1  mov     r8d, r12d; Size
0x14000c5a4  mov     word ptr [rbp+680h+Data], r14w
0x14000c5ac  xor     edx, edx; Val
0x14000c5ae  lea     rcx, [rbp+680h+var_44E]; void *
0x14000c5b5  call    memset_0
0x14000c5ba  lea     r8, [rbp+680h+Data]; unsigned __int16 *
0x14000c5c1  mov     edx, r15d; unsigned int
0x14000c5c4  lea     rcx, [rbp+680h+var_660]; unsigned __int16 *
0x14000c5c8  call    ?QuotePath@@YAJPEBGKPEAG@Z; QuotePath(ushort const *,ulong,ushort *)
0x14000c5cd  mov     ebx, eax
0x14000c5cf  test    eax, eax
0x14000c5d1  js      loc_14000C930
0x14000c5d7  lea     rax, [rsp+780h+dwDisposition]
0x14000c5dc  mov     [rsp+780h+var_710], r14
0x14000c5e1  mov     [rsp+780h+lpdwDisposition], rax; lpdwDisposition
0x14000c5e6  lea     r12, Class; "REG_SZ"
0x14000c5ed  lea     rax, [rsp+780h+hKey]
0x14000c5f2  mov     [rsp+780h+hKey], r14
0x14000c5f7  mov     [rsp+780h+phkResult], rax; phkResult
0x14000c5fc  lea     rdx, aClsid_0; "CLSID"
0x14000c603  mov     [rsp+780h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000c608  mov     r15d, 0F003Fh
0x14000c60e  mov     [rsp+780h+samDesired], r15d; samDesired
0x14000c613  mov     r9, r12; lpClass
0x14000c616  xor     r8d, r8d; Reserved
0x14000c619  mov     [rsp+780h+dwOptions], r14d; dwOptions
0x14000c61e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000c625  call    cs:__imp_RegCreateKeyExW
0x14000c62c  nop     dword ptr [rax+rax+00h]
0x14000c631  mov     ebx, eax
0x14000c633  test    eax, eax
0x14000c635  jnz     loc_14000C923
0x14000c63b  lea     ebx, [rax+27h]
0x14000c63e  mov     [rsp+780h+var_728], r14
0x14000c643  mov     r8d, ebx; cchMax
0x14000c646  lea     rdx, [rbp+680h+sz]; lpsz
0x14000c64a  mov     rcx, rdi; rguid
0x14000c64d  call    cs:__imp_StringFromGUID2
0x14000c654  nop     dword ptr [rax+rax+00h]
0x14000c659  mov     r8d, ebx; cchMax
0x14000c65c  lea     rdx, [rbp+680h+SubKey]; lpsz
0x14000c660  mov     rcx, rsi; rguid
0x14000c663  call    cs:__imp_StringFromGUID2
0x14000c66a  nop     dword ptr [rax+rax+00h]
0x14000c66f  mov     rcx, [rsp+780h+hKey]; hKey
0x14000c674  lea     rax, [rsp+780h+dwDisposition]
0x14000c679  mov     [rsp+780h+lpdwDisposition], rax; lpdwDisposition
0x14000c67e  lea     rdx, [rbp+680h+sz]; lpSubKey
0x14000c682  lea     rax, [rsp+780h+var_728]
0x14000c687  mov     r9, r12; lpClass
0x14000c68a  mov     [rsp+780h+phkResult], rax; phkResult
0x14000c68f  xor     r8d, r8d; Reserved
0x14000c692  mov     [rsp+780h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000c697  mov     [rsp+780h+samDesired], r15d; samDesired
0x14000c69c  mov     [rsp+780h+dwOptions], r14d; dwOptions
0x14000c6a1  call    cs:__imp_RegCreateKeyExW
0x14000c6a8  nop     dword ptr [rax+rax+00h]
0x14000c6ad  mov     ebx, eax
0x14000c6af  test    eax, eax
0x14000c6b1  jnz     loc_14000C82D
0x14000c6b7  mov     rcx, [rsp+780h+var_728]; hKey
0x14000c6bc  lea     rax, [rbp+680h+SubKey]
0x14000c6c0  mov     [rsp+780h+samDesired], 4Eh ; 'N'; cbData
0x14000c6c8  lea     r9d, [r14+1]; dwType
0x14000c6cc  xor     r8d, r8d; Reserved
0x14000c6cf  mov     qword ptr [rsp+780h+dwOptions], rax; lpData
0x14000c6d4  lea     rdx, aAppid; "AppID"
0x14000c6db  mov     [rsp+780h+var_720], r14
0x14000c6e0  call    cs:__imp_RegSetValueExW
0x14000c6e7  nop     dword ptr [rax+rax+00h]
0x14000c6ec  mov     ebx, eax
0x14000c6ee  test    eax, eax
0x14000c6f0  jnz     loc_14000C81C
0x14000c6f6  mov     rcx, [rsp+780h+var_728]; hKey
0x14000c6fb  lea     rax, [rsp+780h+dwDisposition]
0x14000c700  mov     [rsp+780h+lpdwDisposition], rax; lpdwDisposition
0x14000c705  lea     r9, aRegExpandSz; "REG_EXPAND_SZ"
0x14000c70c  lea     rax, [rsp+780h+var_720]
0x14000c711  xor     r8d, r8d; Reserved
0x14000c714  mov     [rsp+780h+phkResult], rax; phkResult
0x14000c719  lea     rdx, aLocalserver32; "LocalServer32"
0x14000c720  mov     [rsp+780h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000c725  mov     [rsp+780h+samDesired], r15d; samDesired
0x14000c72a  mov     [rsp+780h+dwOptions], r14d; dwOptions
0x14000c72f  call    cs:__imp_RegCreateKeyExW
0x14000c736  nop     dword ptr [rax+rax+00h]
0x14000c73b  mov     ebx, eax
0x14000c73d  test    eax, eax
0x14000c73f  jnz     loc_14000C81C
0x14000c745  mov     rcx, [rsp+780h+var_720]; hKey
0x14000c74a  lea     rdx, aThreadingmodel; "ThreadingModel"
0x14000c751  call    cs:__imp_RegDeleteValueW
0x14000c758  nop     dword ptr [rax+rax+00h]
0x14000c75d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c761  lea     rcx, [rbp+680h+Data]
0x14000c768  mov     rax, rdi
0x14000c76b  inc     rax
0x14000c76e  cmp     [rcx+rax*2], r14w
0x14000c773  jnz     short loc_14000C76B
0x14000c775  mov     rcx, [rsp+780h+var_720]; hKey
0x14000c77a  lea     eax, ds:2[rax*2]
0x14000c781  mov     [rsp+780h+samDesired], eax; cbData
0x14000c785  lea     rdx, Data; lpValueName
0x14000c78c  lea     rax, [rbp+680h+Data]
0x14000c793  mov     esi, 2
0x14000c798  mov     r9d, esi; dwType
0x14000c79b  mov     qword ptr [rsp+780h+dwOptions], rax; lpData
0x14000c7a0  xor     r8d, r8d; Reserved
0x14000c7a3  call    cs:__imp_RegSetValueExW
0x14000c7aa  nop     dword ptr [rax+rax+00h]
0x14000c7af  mov     ebx, eax
0x14000c7b1  test    eax, eax
0x14000c7b3  jnz     short loc_14000C7F7
0x14000c7b5  lea     rax, [rbp+680h+var_660]
0x14000c7b9  inc     rdi
0x14000c7bc  cmp     [rax+rdi*2], r14w
0x14000c7c1  jnz     short loc_14000C7B9
0x14000c7c3  mov     rcx, [rsp+780h+var_720]; hKey
0x14000c7c8  lea     eax, ds:2[rdi*2]
0x14000c7cf  mov     [rsp+780h+samDesired], eax; cbData
0x14000c7d3  lea     rdx, aServerexecutab; "ServerExecutable"
0x14000c7da  lea     rax, [rbp+680h+var_660]
0x14000c7de  mov     r9d, esi; dwType
0x14000c7e1  xor     r8d, r8d; Reserved
0x14000c7e4  mov     qword ptr [rsp+780h+dwOptions], rax; lpData
0x14000c7e9  call    cs:__imp_RegSetValueExW
0x14000c7f0  nop     dword ptr [rax+rax+00h]
0x14000c7f5  mov     ebx, eax
0x14000c7f7  mov     rcx, [rsp+780h+var_720]; hKey
0x14000c7fc  call    cs:__imp_RegCloseKey
0x14000c803  nop     dword ptr [rax+rax+00h]
0x14000c808  test    ebx, ebx
0x14000c80a  jnz     short loc_14000C81C
0x14000c80c  mov     rcx, [rsp+780h+var_728]; hKey
0x14000c811  lea     rdx, [rbp+680h+var_660]; unsigned __int16 *
0x14000c815  call    ?RegisterCLSID@@YAKPEAUHKEY__@@PEBG@Z; RegisterCLSID(HKEY__ *,ushort const *)
0x14000c81a  mov     ebx, eax
0x14000c81c  mov     rcx, [rsp+780h+var_728]; hKey
0x14000c821  call    cs:__imp_RegCloseKey
0x14000c828  nop     dword ptr [rax+rax+00h]
0x14000c82d  mov     rcx, [rsp+780h+hKey]; hKey
0x14000c832  call    cs:__imp_RegCloseKey
0x14000c839  nop     dword ptr [rax+rax+00h]
0x14000c83e  test    ebx, ebx
0x14000c840  jnz     loc_14000C925
0x14000c846  lea     rax, [rsp+780h+dwDisposition]
0x14000c84b  mov     r9, r12; lpClass
0x14000c84e  mov     [rsp+780h+lpdwDisposition], rax; lpdwDisposition
0x14000c853  lea     rdx, aAppid; "AppID"
0x14000c85a  lea     rax, [rsp+780h+var_710]
0x14000c85f  xor     r8d, r8d; Reserved
0x14000c862  mov     [rsp+780h+phkResult], rax; phkResult
0x14000c867  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000c86e  mov     [rsp+780h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000c873  mov     [rsp+780h+samDesired], r15d; samDesired
0x14000c878  mov     [rsp+780h+dwOptions], r14d; dwOptions
0x14000c87d  call    cs:__imp_RegCreateKeyExW
0x14000c884  nop     dword ptr [rax+rax+00h]
0x14000c889  mov     ebx, eax
0x14000c88b  test    eax, eax
0x14000c88d  jnz     loc_14000C923
0x14000c893  mov     rcx, [rsp+780h+var_710]; hKey
0x14000c898  lea     rax, [rsp+780h+dwDisposition]
0x14000c89d  mov     [rsp+780h+lpdwDisposition], rax; lpdwDisposition
0x14000c8a2  lea     rdx, [rbp+680h+SubKey]; lpSubKey
0x14000c8a6  lea     rax, [rsp+780h+var_728]
0x14000c8ab  mov     [rsp+780h+var_728], r14
0x14000c8b0  mov     [rsp+780h+phkResult], rax; phkResult
0x14000c8b5  mov     r9, r12; lpClass
0x14000c8b8  mov     [rsp+780h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000c8bd  xor     r8d, r8d; Reserved
0x14000c8c0  mov     [rsp+780h+samDesired], r15d; samDesired
0x14000c8c5  mov     [rsp+780h+dwOptions], r14d; dwOptions
0x14000c8ca  call    cs:__imp_RegCreateKeyExW
0x14000c8d1  nop     dword ptr [rax+rax+00h]
0x14000c8d6  mov     ebx, eax
0x14000c8d8  test    eax, eax
0x14000c8da  jnz     short loc_14000C8F9
0x14000c8dc  mov     rcx, [rsp+780h+var_728]; hKey
0x14000c8e1  call    ?RegisterAppID@@YAKPEAUHKEY__@@@Z; RegisterAppID(HKEY__ *)
0x14000c8e6  mov     rcx, [rsp+780h+var_728]; hKey
0x14000c8eb  mov     ebx, eax
0x14000c8ed  call    cs:__imp_RegCloseKey
0x14000c8f4  nop     dword ptr [rax+rax+00h]
0x14000c8f9  mov     rcx, [rsp+780h+var_710]; hKey
0x14000c8fe  call    cs:__imp_RegCloseKey
0x14000c905  nop     dword ptr [rax+rax+00h]
0x14000c90a  jmp     short loc_14000C91A
0x14000c90c  call    cs:__imp_GetLastError
0x14000c913  nop     dword ptr [rax+rax+00h]
0x14000c918  mov     ebx, eax
0x14000c91a  test    ebx, ebx
0x14000c91c  jnz     short loc_14000C925
0x14000c91e  mov     ebx, r14d
0x14000c921  jmp     short loc_14000C930
0x14000c923  test    ebx, ebx
0x14000c925  jle     short loc_14000C930
0x14000c927  movzx   ebx, bx
0x14000c92a  or      ebx, 80070000h
0x14000c930  mov     eax, ebx
0x14000c932  mov     rcx, [rbp+680h+var_30]
0x14000c939  xor     rcx, rsp; StackCookie
0x14000c93c  call    __security_check_cookie
0x14000c941  lea     r11, [rsp+780h+var_20]
0x14000c949  mov     rbx, [r11+40h]
0x14000c94d  mov     rsi, [r11+48h]
0x14000c951  mov     rsp, r11
0x14000c954  pop     r15
0x14000c956  pop     r14
0x14000c958  pop     r12
0x14000c95a  pop     rdi
0x14000c95b  pop     rbp
0x14000c95c  retn
```
