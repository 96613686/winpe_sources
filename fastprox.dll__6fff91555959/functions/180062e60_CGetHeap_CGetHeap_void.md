# CGetHeap::CGetHeap(void)

- ea: `0x180062e60`
- end: `0x18006304b`
- name: `??0CGetHeap@@QEAA@XZ`
- size: `491`
- prototype: `CGetHeap *__fastcall(CGetHeap *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180062e40`

## callees

- `0x180062e60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062eeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062eeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063016`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180063004`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180063004`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062ee5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062f24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062f54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062f84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062fb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062ee5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062f24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062f54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062f84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062fb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062ea7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062ea7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062fc6`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x180062fd2`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x180062fd2`

## string_xrefs

- `0x180062ec6`: `ProcessID`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CGetHeap *__fastcall CGetHeap::CGetHeap(CGetHeap *this)
{
  HANDLE ArenaHeap; // rax
  unsigned int v3; // eax
  BYTE v4[8]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  CGetHeap *cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF
  int v8; // [rsp+70h] [rbp+28h] BYREF
  int Data; // [rsp+78h] [rbp+30h] BYREF

  cbData = this;
  dword_1800D7F48 = 0;
  v8 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    Data = 0;
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"ProcessID", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData);
    if ( Data == GetCurrentProcessId() )
      v8 = 1;
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"EnablePrivateObjectHeap", 0, &Type, (LPBYTE)&v8, (LPDWORD)&cbData);
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"ContextLimit", 0, &Type, &g_ContextLimit, (LPDWORD)&cbData);
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"ObjectLimit", 0, &Type, &g_ObjectLimit, (LPDWORD)&cbData);
    LODWORD(cbData) = 4;
    *(_DWORD *)v4 = 0;
    if ( !RegQueryValueExW(hKey, L"IdentifierLimit", 0, &Type, v4, (LPDWORD)&cbData) && Type == 4 )
    {
      v3 = *(_DWORD *)v4;
      if ( *(_DWORD *)v4 < 0x40u )
        v3 = 64;
      g_IdentifierLimit = v3;
    }
    RegCloseKey(hKey);
  }
  if ( v8 )
  {
    CBasicBlobControl::m_Heap = 0;
    ArenaHeap = HeapCreate(0, 0, 0);
    CBasicBlobControl::m_Heap = ArenaHeap;
    if ( !ArenaHeap )
      goto LABEL_11;
    dword_1800D7F48 = 1;
  }
  else
  {
    ArenaHeap = (HANDLE)CWin32DefaultArena::GetArenaHeap();
    CBasicBlobControl::m_Heap = ArenaHeap;
  }
  if ( !ArenaHeap )
LABEL_11:
    CBasicBlobControl::m_Heap = GetProcessHeap();
  return (CGetHeap *)&CBasicBlobControl::m_Heap;
}

```

## disassembly

```asm
0x180062e60  mov     [rsp-10h+cbData], rcx
0x180062e65  push    rbp
0x180062e66  push    rdi
0x180062e67  mov     rbp, rsp
0x180062e6a  sub     rsp, 48h
0x180062e6e  lea     rax, [rbp+hKey]
0x180062e72  mov     cs:dword_1800D7F48, 0
0x180062e7c  mov     r9d, 20019h; samDesired
0x180062e82  mov     [rsp+48h+phkResult], rax; phkResult
0x180062e87  xor     r8d, r8d; ulOptions
0x180062e8a  mov     [rbp+arg_10], 0
0x180062e91  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180062e98  mov     [rbp+hKey], 0
0x180062ea0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062ea7  call    cs:__imp_RegOpenKeyExW
0x180062ead  test    eax, eax
0x180062eaf  jnz     loc_180062FCC
0x180062eb5  mov     rcx, [rbp+hKey]; hKey
0x180062eb9  lea     edi, [rax+4]
0x180062ebc  mov     [rbp+Type], eax
0x180062ebf  lea     r9, [rbp+Type]; lpType
0x180062ec3  mov     [rbp+Data], eax
0x180062ec6  lea     rdx, ValueName; "ProcessID"
0x180062ecd  lea     rax, [rbp+cbData]
0x180062ed1  mov     dword ptr [rbp+cbData], edi
0x180062ed4  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180062ed9  xor     r8d, r8d; lpReserved
0x180062edc  lea     rax, [rbp+Data]
0x180062ee0  mov     [rsp+48h+phkResult], rax; lpData
0x180062ee5  call    cs:__imp_RegQueryValueExW
0x180062eeb  call    cs:__imp_GetCurrentProcessId
0x180062ef1  cmp     [rbp+Data], eax
0x180062ef4  jnz     short loc_180062EFD
0x180062ef6  mov     [rbp+arg_10], 1
0x180062efd  mov     rcx, [rbp+hKey]; hKey
0x180062f01  lea     rax, [rbp+cbData]
0x180062f05  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180062f0a  lea     r9, [rbp+Type]; lpType
0x180062f0e  lea     rax, [rbp+arg_10]
0x180062f12  mov     dword ptr [rbp+cbData], edi
0x180062f15  xor     r8d, r8d; lpReserved
0x180062f18  mov     [rsp+48h+phkResult], rax; lpData
0x180062f1d  lea     rdx, aEnableprivateo; "EnablePrivateObjectHeap"
0x180062f24  call    cs:__imp_RegQueryValueExW
0x180062f2a  mov     rcx, [rbp+hKey]; hKey
0x180062f2e  lea     rax, [rbp+cbData]
0x180062f32  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180062f37  lea     r9, [rbp+Type]; lpType
0x180062f3b  lea     rax, ?g_ContextLimit@@3KA; ulong g_ContextLimit
0x180062f42  mov     dword ptr [rbp+cbData], edi
0x180062f45  xor     r8d, r8d; lpReserved
0x180062f48  mov     [rsp+48h+phkResult], rax; lpData
0x180062f4d  lea     rdx, aContextlimit; "ContextLimit"
0x180062f54  call    cs:__imp_RegQueryValueExW
0x180062f5a  mov     rcx, [rbp+hKey]; hKey
0x180062f5e  lea     rax, [rbp+cbData]
0x180062f62  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180062f67  lea     r9, [rbp+Type]; lpType
0x180062f6b  lea     rax, ?g_ObjectLimit@@3KA; ulong g_ObjectLimit
0x180062f72  mov     dword ptr [rbp+cbData], edi
0x180062f75  xor     r8d, r8d; lpReserved
0x180062f78  mov     [rsp+48h+phkResult], rax; lpData
0x180062f7d  lea     rdx, aObjectlimit; "ObjectLimit"
0x180062f84  call    cs:__imp_RegQueryValueExW
0x180062f8a  mov     rcx, [rbp+hKey]; hKey
0x180062f8e  lea     rax, [rbp+cbData]
0x180062f92  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180062f97  lea     r9, [rbp+Type]; lpType
0x180062f9b  lea     rax, [rbp+var_18]
0x180062f9f  mov     dword ptr [rbp+cbData], edi
0x180062fa2  xor     r8d, r8d; lpReserved
0x180062fa5  mov     [rsp+48h+phkResult], rax; lpData
0x180062faa  lea     rdx, aIdentifierlimi; "IdentifierLimit"
0x180062fb1  mov     dword ptr [rbp+var_18], 0
0x180062fb8  call    cs:__imp_RegQueryValueExW
0x180062fbe  test    eax, eax
0x180062fc0  jz      short loc_180063025
0x180062fc2  mov     rcx, [rbp+hKey]; hKey
0x180062fc6  call    cs:__imp_RegCloseKey
0x180062fcc  cmp     [rbp+arg_10], 0
0x180062fd0  jnz     short loc_180062FF2
0x180062fd2  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x180062fd8  mov     cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A, rax; CGetHeap CBasicBlobControl::m_Heap
0x180062fdf  test    rax, rax
0x180062fe2  jz      short loc_180063016
0x180062fe4  lea     rax, ?m_Heap@CBasicBlobControl@@2VCGetHeap@@A; CGetHeap CBasicBlobControl::m_Heap
0x180062feb  add     rsp, 48h
0x180062fef  pop     rdi
0x180062ff0  pop     rbp
0x180062ff1  retn
0x180062ff2  xor     r8d, r8d; dwMaximumSize
0x180062ff5  mov     cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A, 0; CGetHeap CBasicBlobControl::m_Heap
0x180063000  xor     edx, edx; dwInitialSize
0x180063002  xor     ecx, ecx; flOptions
0x180063004  call    cs:__imp_HeapCreate
0x18006300a  mov     cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A, rax; CGetHeap CBasicBlobControl::m_Heap
0x180063011  test    rax, rax
0x180063014  jnz     short loc_18006303F
0x180063016  call    cs:__imp_GetProcessHeap
0x18006301c  mov     cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A, rax; CGetHeap CBasicBlobControl::m_Heap
0x180063023  jmp     short loc_180062FE4
0x180063025  cmp     [rbp+Type], edi
0x180063028  jnz     short loc_180062FC2
0x18006302a  mov     eax, dword ptr [rbp+var_18]
0x18006302d  mov     ecx, 40h ; '@'
0x180063032  cmp     eax, ecx
0x180063034  cmovb   eax, ecx
0x180063037  mov     cs:?g_IdentifierLimit@@3KA, eax; ulong g_IdentifierLimit
0x18006303d  jmp     short loc_180062FC2
0x18006303f  mov     cs:dword_1800D7F48, 1
0x180063049  jmp     short loc_180062FDF
```
