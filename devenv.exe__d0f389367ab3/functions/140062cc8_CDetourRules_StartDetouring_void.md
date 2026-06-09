# CDetourRules::StartDetouring(void)

- ea: `0x140062cc8`
- end: `0x14006348e`
- name: `?StartDetouring@CDetourRules@@QEAAJXZ`
- size: `1990`
- prototype: `__int64 __fastcall(CDetourRules *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140021450`

## callees

- `0x140001020`
- `0x140002190`
- `0x140017bec`
- `0x140017bf0`
- `0x1400195e8`
- `0x140029230`
- `0x140062b68`
- `0x140062cc8`
- `0x140067700`

## import_xrefs

- `KERNEL32!HeapLock` at `0x1400630cf`
- `KERNEL32!HeapLock` at `0x1400630cf`
- `KERNEL32!HeapUnlock` at `0x140063461`
- `KERNEL32!HeapUnlock` at `0x140063461`
- `KERNEL32!GetVersionExW` at `0x140062cfe`
- `KERNEL32!GetVersionExW` at `0x140062cfe`
- `KERNEL32!CloseHandle` at `0x1400633ec`
- `KERNEL32!CloseHandle` at `0x1400633ec`
- `KERNEL32!GetModuleHandleW` at `0x140062d24`
- `KERNEL32!GetModuleHandleW` at `0x140062d24`
- `KERNEL32!GetProcAddress` at `0x140062d57`
- `KERNEL32!GetProcAddress` at `0x140062d7c`
- `KERNEL32!GetProcAddress` at `0x140062da1`
- `KERNEL32!GetProcAddress` at `0x140062dc6`
- `KERNEL32!GetProcAddress` at `0x140062def`
- `KERNEL32!GetProcAddress` at `0x140062e18`
- `KERNEL32!GetProcAddress` at `0x140062e41`
- `KERNEL32!GetProcAddress` at `0x140062e6a`
- `KERNEL32!GetProcAddress` at `0x140062e93`
- `KERNEL32!GetProcAddress` at `0x140062ebc`
- `KERNEL32!GetProcAddress` at `0x140062ee5`
- `KERNEL32!GetProcAddress` at `0x140062f0e`
- `KERNEL32!GetProcAddress` at `0x140062f37`
- `KERNEL32!GetProcAddress` at `0x140062f60`
- `KERNEL32!GetProcAddress` at `0x140062f89`
- `KERNEL32!GetProcAddress` at `0x140062fb2`
- `KERNEL32!GetProcAddress` at `0x140062fdb`
- `KERNEL32!GetProcAddress` at `0x140063004`
- `KERNEL32!GetProcAddress` at `0x14006302d`
- `KERNEL32!GetProcAddress` at `0x140063056`
- `KERNEL32!GetProcAddress` at `0x14006307f`
- `KERNEL32!GetProcAddress` at `0x140062d57`
- `KERNEL32!GetProcAddress` at `0x140062d7c`
- `KERNEL32!GetProcAddress` at `0x140062da1`
- `KERNEL32!GetProcAddress` at `0x140062dc6`
- `KERNEL32!GetProcAddress` at `0x140062def`
- `KERNEL32!GetProcAddress` at `0x140062e18`
- `KERNEL32!GetProcAddress` at `0x140062e41`
- `KERNEL32!GetProcAddress` at `0x140062e6a`
- `KERNEL32!GetProcAddress` at `0x140062e93`
- `KERNEL32!GetProcAddress` at `0x140062ebc`
- `KERNEL32!GetProcAddress` at `0x140062ee5`
- `KERNEL32!GetProcAddress` at `0x140062f0e`
- `KERNEL32!GetProcAddress` at `0x140062f37`
- `KERNEL32!GetProcAddress` at `0x140062f60`
- `KERNEL32!GetProcAddress` at `0x140062f89`
- `KERNEL32!GetProcAddress` at `0x140062fb2`
- `KERNEL32!GetProcAddress` at `0x140062fdb`
- `KERNEL32!GetProcAddress` at `0x140063004`
- `KERNEL32!GetProcAddress` at `0x14006302d`
- `KERNEL32!GetProcAddress` at `0x140063056`
- `KERNEL32!GetProcAddress` at `0x14006307f`
- `KERNEL32!GetProcessHeap` at `0x1400630c6`
- `KERNEL32!GetProcessHeap` at `0x140063458`
- `KERNEL32!GetProcessHeap` at `0x1400630c6`
- `KERNEL32!GetProcessHeap` at `0x140063458`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14006343a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14006343a`

## string_xrefs

- `0x140062e89`: `RegDeleteKeyExW`
- `0x140062d4d`: `RegCreateKeyExA`
- `0x140062d72`: `RegCreateKeyExW`
- `0x140062dbc`: `RegOpenKeyExW`
- `0x140062d97`: `RegOpenKeyExA`
- `0x140062e60`: `RegDeleteKeyExA`
- `0x140062f2d`: `RegDeleteTreeW`
- `0x140062f04`: `RegDeleteTreeA`
- `0x140062f7f`: `RegDeleteValueW`
- `0x140062f56`: `RegDeleteValueA`
- `0x140062edb`: `RegDeleteKeyValueW`
- `0x140062eb2`: `RegDeleteKeyValueA`
- `0x140062d1d`: `advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDetourRules::StartDetouring(CDetourRules *this)
{
  bool v1; // cc
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rbx
  BOOL v4; // edi
  __int64 result; // rax
  int (*ProcAddress)(HKEY, const char *, unsigned int, char *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *); // rax
  int (*v7)(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *); // rax
  int (*v8)(HKEY, const char *, unsigned int, unsigned int, HKEY *); // rax
  int (*v9)(HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *); // rax
  int (*v10)(HKEY); // rax
  int (*v11)(HKEY, const char *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *); // rax
  int (*v12)(HKEY, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *); // rax
  int (*v13)(HKEY, const char *, unsigned int, unsigned int); // rax
  int (*v14)(HKEY, const unsigned __int16 *, unsigned int, unsigned int); // rax
  int (*v15)(HKEY, const char *, const char *); // rax
  int (*v16)(HKEY, const unsigned __int16 *, const unsigned __int16 *); // rax
  int (*v17)(HKEY, const char *); // rax
  int (*v18)(HKEY, const unsigned __int16 *); // rax
  int (*v19)(HKEY, const char *); // rax
  int (*v20)(HKEY, const unsigned __int16 *); // rax
  int (*v21)(HKEY, unsigned int, char *, unsigned int *, unsigned int *, char *, unsigned int *, struct _FILETIME *); // rax
  int (*v22)(HKEY, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int *, struct _FILETIME *); // rax
  int (*v23)(HKEY, unsigned int, char *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *); // rax
  int (*v24)(HKEY, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *); // rax
  int (*v25)(HKEY, char *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, struct _FILETIME *); // rax
  int (*v26)(HKEY, unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, struct _FILETIME *); // rax
  BOOL v27; // ebx
  unsigned int v28; // ebx
  int v29; // ecx
  HANDLE ProcessHeap; // rax
  int updated; // edi
  int v32; // eax
  int v33; // eax
  __int128 v34; // rdi
  const struct std::nothrow_t *v35; // rdx
  __int64 v36; // rax
  HANDLE v37; // rax
  __int64 v38; // [rsp+28h] [rbp-E0h] BYREF
  void *v39[2]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C8h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+48h] [rbp-C0h] BYREF

  VersionInformation.dwOSVersionInfoSize = 276;
  GetVersionExW(&VersionInformation);
  v1 = VersionInformation.dwMajorVersion <= 6;
  if ( VersionInformation.dwMajorVersion != 6 )
  {
LABEL_4:
    if ( v1 )
      goto LABEL_30;
    goto LABEL_5;
  }
  if ( !VersionInformation.dwMinorVersion )
  {
    v1 = VersionInformation.dwMajorVersion <= 6;
    goto LABEL_4;
  }
LABEL_5:
  ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
  v3 = ModuleHandleW;
  v4 = ModuleHandleW == 0;
  if ( !ModuleHandleW )
    goto LABEL_6;
  ProcAddress = (int (*)(HKEY, const char *, unsigned int, char *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *))GetProcAddress(ModuleHandleW, "RegCreateKeyExA");
  v4 = ProcAddress == 0;
  if ( !ProcAddress )
    goto LABEL_6;
  Real_RegCreateKeyExA = ProcAddress;
  v7 = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *))GetProcAddress(v3, "RegCreateKeyExW");
  v4 = v7 == 0;
  if ( !v7 )
    goto LABEL_6;
  Real_RegCreateKeyExW = v7;
  v8 = (int (*)(HKEY, const char *, unsigned int, unsigned int, HKEY *))GetProcAddress(v3, "RegOpenKeyExA");
  v4 = v8 == 0;
  if ( !v8 )
    goto LABEL_6;
  Real_RegOpenKeyExA = v8;
  v9 = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *))GetProcAddress(v3, "RegOpenKeyExW");
  v4 = v9 == 0;
  if ( !v9 )
    goto LABEL_6;
  Real_RegOpenKeyExW = v9;
  v10 = (int (*)(HKEY))GetProcAddress(v3, "RegCloseKey");
  v4 = v10 == 0;
  if ( !v10 )
    goto LABEL_6;
  Real_RegCloseKey = v10;
  v11 = (int (*)(HKEY, const char *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *))GetProcAddress(v3, "RegQueryValueExA");
  v4 = v11 == 0;
  if ( !v11 )
    goto LABEL_6;
  Real_RegQueryValueExA = v11;
  v12 = (int (*)(HKEY, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *))GetProcAddress(v3, "RegQueryValueExW");
  v4 = v12 == 0;
  if ( !v12 )
    goto LABEL_6;
  Real_RegQueryValueExW = v12;
  v13 = (int (*)(HKEY, const char *, unsigned int, unsigned int))GetProcAddress(v3, "RegDeleteKeyExA");
  v4 = v13 == 0;
  if ( !v13 )
    goto LABEL_6;
  Real_RegDeleteKeyExA = v13;
  v14 = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned int))GetProcAddress(v3, "RegDeleteKeyExW");
  v4 = v14 == 0;
  if ( !v14 )
    goto LABEL_6;
  Real_RegDeleteKeyExW = v14;
  v15 = (int (*)(HKEY, const char *, const char *))GetProcAddress(v3, "RegDeleteKeyValueA");
  v4 = v15 == 0;
  if ( !v15 )
    goto LABEL_6;
  Real_RegDeleteKeyValueA = v15;
  v16 = (int (*)(HKEY, const unsigned __int16 *, const unsigned __int16 *))GetProcAddress(v3, "RegDeleteKeyValueW");
  v4 = v16 == 0;
  if ( !v16 )
    goto LABEL_6;
  Real_RegDeleteKeyValueW = v16;
  v17 = (int (*)(HKEY, const char *))GetProcAddress(v3, "RegDeleteTreeA");
  v4 = v17 == 0;
  if ( !v17 )
    goto LABEL_6;
  Real_RegDeleteTreeA = v17;
  v18 = (int (*)(HKEY, const unsigned __int16 *))GetProcAddress(v3, "RegDeleteTreeW");
  v4 = v18 == 0;
  if ( !v18 )
    goto LABEL_6;
  Real_RegDeleteTreeW = v18;
  v19 = (int (*)(HKEY, const char *))GetProcAddress(v3, "RegDeleteValueA");
  v4 = v19 == 0;
  if ( !v19 )
    goto LABEL_6;
  Real_RegDeleteValueA = v19;
  v20 = (int (*)(HKEY, const unsigned __int16 *))GetProcAddress(v3, "RegDeleteValueW");
  v4 = v20 == 0;
  if ( !v20 )
    goto LABEL_6;
  Real_RegDeleteValueW = v20;
  v21 = (int (*)(HKEY, unsigned int, char *, unsigned int *, unsigned int *, char *, unsigned int *, struct _FILETIME *))GetProcAddress(v3, "RegEnumKeyExA");
  v4 = v21 == 0;
  if ( !v21 )
    goto LABEL_6;
  Real_RegEnumKeyExA = v21;
  v22 = (int (*)(HKEY, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int *, struct _FILETIME *))GetProcAddress(v3, "RegEnumKeyExW");
  v4 = v22 == 0;
  if ( !v22 )
    goto LABEL_6;
  Real_RegEnumKeyExW = v22;
  v23 = (int (*)(HKEY, unsigned int, char *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *))GetProcAddress(v3, "RegEnumValueA");
  v4 = v23 == 0;
  if ( !v23
    || (Real_RegEnumValueA = v23,
        v24 = (int (*)(HKEY, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *))GetProcAddress(v3, "RegEnumValueW"),
        v4 = v24 == 0,
        !v24)
    || (Real_RegEnumValueW = v24,
        v25 = (int (*)(HKEY, char *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, struct _FILETIME *))GetProcAddress(v3, "RegQueryInfoKeyA"),
        v4 = v25 == 0,
        !v25) )
  {
LABEL_6:
    DetourTransactionAbort();
    return v4 | 0x80070000;
  }
  Real_RegQueryInfoKeyA = v25;
  v26 = (int (*)(HKEY, unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, struct _FILETIME *))GetProcAddress(v3, "RegQueryInfoKeyW");
  v27 = v26 == 0;
  if ( !v26 )
  {
    DetourTransactionAbort();
    return v27 | 0x80070000;
  }
  Real_RegQueryInfoKeyW = v26;
LABEL_30:
  v29 = DetourTransactionBegin();
  if ( !v29 )
  {
    ProcessHeap = GetProcessHeap();
    HeapLock(ProcessHeap);
    v40 = 0;
    *(_OWORD *)v39 = 0;
    updated = DetourUpdateAllThreads((__int64)v39);
    if ( updated )
    {
      DetourTransactionAbort();
      v28 = (unsigned __int16)updated | 0x80070000;
      if ( updated <= 0 )
        v28 = updated;
    }
    else
    {
      v32 = DetourAttach(&Real_RegCreateKeyExA, CDetourRules::Mine_RegCreateKeyExA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegCreateKeyExW, CDetourRules::Mine_RegCreateKeyExW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegOpenKeyExA, CDetourRules::Mine_RegOpenKeyExA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegOpenKeyExW, CDetourRules::Mine_RegOpenKeyExW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegCloseKey, Mine_RegCloseKey);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegQueryValueExA, Mine_RegQueryValueExA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegQueryValueExW, Mine_RegQueryValueExW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteKeyA, CDetourRules::Mine_RegDeleteKeyA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteKeyW, CDetourRules::Mine_RegDeleteKeyW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteKeyExA, CDetourRules::Mine_RegDeleteKeyExA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteKeyExW, CDetourRules::Mine_RegDeleteKeyExW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteKeyValueA, CDetourRules::Mine_RegDeleteKeyValueA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteKeyValueW, CDetourRules::Mine_RegDeleteKeyValueW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteTreeA, CDetourRules::Mine_RegDeleteTreeA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteTreeW, CDetourRules::Mine_RegDeleteTreeW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteValueA, Mine_RegDeleteValueA);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegDeleteValueW, Mine_RegDeleteValueW);
      if ( v32 )
        goto LABEL_63;
      v32 = DetourAttach(&Real_RegEnumKeyExA, Mine_RegEnumKeyExA);
      if ( v32
        || (v32 = DetourAttach(&Real_RegEnumKeyExW, Mine_RegEnumKeyExW)) != 0
        || (v32 = DetourAttach(&Real_RegEnumValueA, Mine_RegEnumValueA)) != 0
        || (v32 = DetourAttach(&Real_RegEnumValueW, Mine_RegEnumValueW)) != 0
        || (v32 = DetourAttach(&Real_RegQueryInfoKeyA, Mine_RegQueryInfoKeyA)) != 0
        || (v32 = DetourAttach(&Real_RegQueryInfoKeyW, Mine_RegQueryInfoKeyW)) != 0
        || (v32 = DetourAttach(&Real_RegQueryValueExA, Mine_RegQueryValueExA)) != 0
        || (v32 = DetourAttach(&Real_RegQueryValueExW, Mine_RegQueryValueExW)) != 0 )
      {
LABEL_63:
        v28 = (unsigned __int16)v32 | 0x80070000;
        if ( v32 <= 0 )
          v28 = v32;
        DetourTransactionAbort();
      }
      else
      {
        v33 = DetourTransactionCommit();
        if ( v33 )
        {
          v38 = 0;
          v33 = DetourTransactionCommitEx(&v38);
        }
        v28 = (unsigned __int16)v33 | 0x80070000;
        if ( v33 <= 0 )
          v28 = v33;
      }
      v34 = *(_OWORD *)v39;
      if ( v39[0] == v39[1] )
        goto LABEL_73;
      do
      {
        CloseHandle(*(HANDLE *)v34);
        *(_QWORD *)&v34 = v34 + 8;
      }
      while ( (_QWORD)v34 != *((_QWORD *)&v34 + 1) );
    }
    *(void **)&v34 = v39[0];
LABEL_73:
    if ( (_QWORD)v34 )
    {
      v35 = (const struct std::nothrow_t *)(8 * ((v40 - (__int64)v34) >> 3));
      v36 = v34;
      if ( (unsigned __int64)v35 >= 0x1000 )
      {
        v35 = (const struct std::nothrow_t *)((char *)v35 + 39);
        *(_QWORD *)&v34 = *(_QWORD *)(v34 - 8);
        if ( (unsigned __int64)(v36 - v34 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete((void *)v34, v35);
      *(_OWORD *)v39 = 0;
      v40 = 0;
    }
    v37 = GetProcessHeap();
    HeapUnlock(v37);
    return v28;
  }
  result = (unsigned __int16)v29 | 0x80070000;
  if ( v29 <= 0 )
    return (unsigned int)v29;
  return result;
}

```

## disassembly

```asm
0x140062cc8  mov     rax, rsp
0x140062ccb  mov     [rax+8], rbx
0x140062ccf  mov     [rax+10h], rsi
0x140062cd3  mov     [rax+18h], rdi
0x140062cd7  push    rbp
0x140062cd8  lea     rbp, [rax-78h]
0x140062cdc  sub     rsp, 170h
0x140062ce3  mov     rax, cs:__security_cookie
0x140062cea  xor     rax, rsp
0x140062ced  mov     [rbp+70h+var_8], rax
0x140062cf1  mov     [rsp+170h+VersionInformation.dwOSVersionInfoSize], 114h
0x140062cf9  lea     rcx, [rsp+170h+VersionInformation]; lpVersionInformation
0x140062cfe  call    cs:__imp_GetVersionExW
0x140062d04  cmp     [rsp+170h+VersionInformation.dwMajorVersion], 6
0x140062d09  jnz     short loc_140062D17
0x140062d0b  cmp     [rsp+170h+VersionInformation.dwMinorVersion], 1
0x140062d10  jnb     short loc_140062D1D
0x140062d12  cmp     [rsp+170h+VersionInformation.dwMajorVersion], 6
0x140062d17  jbe     loc_1400630A9
0x140062d1d  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x140062d24  call    cs:__imp_GetModuleHandleW
0x140062d2a  mov     rbx, rax
0x140062d2d  xor     edi, edi
0x140062d2f  test    rax, rax
0x140062d32  setz    dil
0x140062d36  test    rax, rax
0x140062d39  jnz     short loc_140062D4D
0x140062d3b  call    DetourTransactionAbort
0x140062d40  or      edi, 80070000h
0x140062d46  mov     eax, edi
0x140062d48  jmp     loc_140063469
0x140062d4d  lea     rdx, aRegcreatekeyex; "RegCreateKeyExA"
0x140062d54  mov     rcx, rbx; hModule
0x140062d57  call    cs:__imp_GetProcAddress
0x140062d5d  xor     edi, edi
0x140062d5f  test    rax, rax
0x140062d62  setz    dil
0x140062d66  test    rax, rax
0x140062d69  jz      short loc_140062D3B
0x140062d6b  mov     cs:?Real_RegCreateKeyExA@@3P6AJPEAUHKEY__@@PEBDKPEADKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA, rax; long (*Real_RegCreateKeyExA)(HKEY__ *,char const *,ulong,char *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x140062d72  lea     rdx, aRegcreatekeyex_0; "RegCreateKeyExW"
0x140062d79  mov     rcx, rbx; hModule
0x140062d7c  call    cs:__imp_GetProcAddress
0x140062d82  xor     edi, edi
0x140062d84  test    rax, rax
0x140062d87  setz    dil
0x140062d8b  test    rax, rax
0x140062d8e  jz      short loc_140062D3B
0x140062d90  mov     cs:?Real_RegCreateKeyExW@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA, rax; long (*Real_RegCreateKeyExW)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x140062d97  lea     rdx, aRegopenkeyexa; "RegOpenKeyExA"
0x140062d9e  mov     rcx, rbx; hModule
0x140062da1  call    cs:__imp_GetProcAddress
0x140062da7  xor     edi, edi
0x140062da9  test    rax, rax
0x140062dac  setz    dil
0x140062db0  test    rax, rax
0x140062db3  jz      short loc_140062D3B
0x140062db5  mov     cs:?Real_RegOpenKeyExA@@3P6AJPEAUHKEY__@@PEBDKKPEAPEAU1@@ZEA, rax; long (*Real_RegOpenKeyExA)(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x140062dbc  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x140062dc3  mov     rcx, rbx; hModule
0x140062dc6  call    cs:__imp_GetProcAddress
0x140062dcc  xor     edi, edi
0x140062dce  test    rax, rax
0x140062dd1  setz    dil
0x140062dd5  test    rax, rax
0x140062dd8  jz      loc_140062D3B
0x140062dde  mov     cs:?Real_RegOpenKeyExW@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA, rax; long (*Real_RegOpenKeyExW)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140062de5  lea     rdx, aRegclosekey; "RegCloseKey"
0x140062dec  mov     rcx, rbx; hModule
0x140062def  call    cs:__imp_GetProcAddress
0x140062df5  xor     edi, edi
0x140062df7  test    rax, rax
0x140062dfa  setz    dil
0x140062dfe  test    rax, rax
0x140062e01  jz      loc_140062D3B
0x140062e07  mov     cs:?Real_RegCloseKey@@3P6AJPEAUHKEY__@@@ZEA, rax; long (*Real_RegCloseKey)(HKEY__ *)
0x140062e0e  lea     rdx, aRegqueryvaluee; "RegQueryValueExA"
0x140062e15  mov     rcx, rbx; hModule
0x140062e18  call    cs:__imp_GetProcAddress
0x140062e1e  xor     edi, edi
0x140062e20  test    rax, rax
0x140062e23  setz    dil
0x140062e27  test    rax, rax
0x140062e2a  jz      loc_140062D3B
0x140062e30  mov     cs:?Real_RegQueryValueExA@@3P6AJPEAUHKEY__@@PEBDPEAK2PEAE2@ZEA, rax; long (*Real_RegQueryValueExA)(HKEY__ *,char const *,ulong *,ulong *,uchar *,ulong *)
0x140062e37  lea     rdx, aRegqueryvaluee_0; "RegQueryValueExW"
0x140062e3e  mov     rcx, rbx; hModule
0x140062e41  call    cs:__imp_GetProcAddress
0x140062e47  xor     edi, edi
0x140062e49  test    rax, rax
0x140062e4c  setz    dil
0x140062e50  test    rax, rax
0x140062e53  jz      loc_140062D3B
0x140062e59  mov     cs:?Real_RegQueryValueExW@@3P6AJPEAUHKEY__@@PEBGPEAK2PEAE2@ZEA, rax; long (*Real_RegQueryValueExW)(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)
0x140062e60  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExA"
0x140062e67  mov     rcx, rbx; hModule
0x140062e6a  call    cs:__imp_GetProcAddress
0x140062e70  xor     edi, edi
0x140062e72  test    rax, rax
0x140062e75  setz    dil
0x140062e79  test    rax, rax
0x140062e7c  jz      loc_140062D3B
0x140062e82  mov     cs:?Real_RegDeleteKeyExA@@3P6AJPEAUHKEY__@@PEBDKK@ZEA, rax; long (*Real_RegDeleteKeyExA)(HKEY__ *,char const *,ulong,ulong)
0x140062e89  lea     rdx, aRegdeletekeyex_0; "RegDeleteKeyExW"
0x140062e90  mov     rcx, rbx; hModule
0x140062e93  call    cs:__imp_GetProcAddress
0x140062e99  xor     edi, edi
0x140062e9b  test    rax, rax
0x140062e9e  setz    dil
0x140062ea2  test    rax, rax
0x140062ea5  jz      loc_140062D3B
0x140062eab  mov     cs:?Real_RegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA, rax; long (*Real_RegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x140062eb2  lea     rdx, aRegdeletekeyva; "RegDeleteKeyValueA"
0x140062eb9  mov     rcx, rbx; hModule
0x140062ebc  call    cs:__imp_GetProcAddress
0x140062ec2  xor     edi, edi
0x140062ec4  test    rax, rax
0x140062ec7  setz    dil
0x140062ecb  test    rax, rax
0x140062ece  jz      loc_140062D3B
0x140062ed4  mov     cs:?Real_RegDeleteKeyValueA@@3P6AJPEAUHKEY__@@PEBD1@ZEA, rax; long (*Real_RegDeleteKeyValueA)(HKEY__ *,char const *,char const *)
0x140062edb  lea     rdx, aRegdeletekeyva_0; "RegDeleteKeyValueW"
0x140062ee2  mov     rcx, rbx; hModule
0x140062ee5  call    cs:__imp_GetProcAddress
0x140062eeb  xor     edi, edi
0x140062eed  test    rax, rax
0x140062ef0  setz    dil
0x140062ef4  test    rax, rax
0x140062ef7  jz      loc_140062D3B
0x140062efd  mov     cs:?Real_RegDeleteKeyValueW@@3P6AJPEAUHKEY__@@PEBG1@ZEA, rax; long (*Real_RegDeleteKeyValueW)(HKEY__ *,ushort const *,ushort const *)
0x140062f04  lea     rdx, aRegdeletetreea; "RegDeleteTreeA"
0x140062f0b  mov     rcx, rbx; hModule
0x140062f0e  call    cs:__imp_GetProcAddress
0x140062f14  xor     edi, edi
0x140062f16  test    rax, rax
0x140062f19  setz    dil
0x140062f1d  test    rax, rax
0x140062f20  jz      loc_140062D3B
0x140062f26  mov     cs:?Real_RegDeleteTreeA@@3P6AJPEAUHKEY__@@PEBD@ZEA, rax; long (*Real_RegDeleteTreeA)(HKEY__ *,char const *)
0x140062f2d  lea     rdx, aRegdeletetreew; "RegDeleteTreeW"
0x140062f34  mov     rcx, rbx; hModule
0x140062f37  call    cs:__imp_GetProcAddress
0x140062f3d  xor     edi, edi
0x140062f3f  test    rax, rax
0x140062f42  setz    dil
0x140062f46  test    rax, rax
0x140062f49  jz      loc_140062D3B
0x140062f4f  mov     cs:?Real_RegDeleteTreeW@@3P6AJPEAUHKEY__@@PEBG@ZEA, rax; long (*Real_RegDeleteTreeW)(HKEY__ *,ushort const *)
0x140062f56  lea     rdx, aRegdeletevalue; "RegDeleteValueA"
0x140062f5d  mov     rcx, rbx; hModule
0x140062f60  call    cs:__imp_GetProcAddress
0x140062f66  xor     edi, edi
0x140062f68  test    rax, rax
0x140062f6b  setz    dil
0x140062f6f  test    rax, rax
0x140062f72  jz      loc_140062D3B
0x140062f78  mov     cs:?Real_RegDeleteValueA@@3P6AJPEAUHKEY__@@PEBD@ZEA, rax; long (*Real_RegDeleteValueA)(HKEY__ *,char const *)
0x140062f7f  lea     rdx, aRegdeletevalue_0; "RegDeleteValueW"
0x140062f86  mov     rcx, rbx; hModule
0x140062f89  call    cs:__imp_GetProcAddress
0x140062f8f  xor     edi, edi
0x140062f91  test    rax, rax
0x140062f94  setz    dil
0x140062f98  test    rax, rax
0x140062f9b  jz      loc_140062D3B
0x140062fa1  mov     cs:?Real_RegDeleteValueW@@3P6AJPEAUHKEY__@@PEBG@ZEA, rax; long (*Real_RegDeleteValueW)(HKEY__ *,ushort const *)
0x140062fa8  lea     rdx, aRegenumkeyexa; "RegEnumKeyExA"
0x140062faf  mov     rcx, rbx; hModule
0x140062fb2  call    cs:__imp_GetProcAddress
0x140062fb8  xor     edi, edi
0x140062fba  test    rax, rax
0x140062fbd  setz    dil
0x140062fc1  test    rax, rax
0x140062fc4  jz      loc_140062D3B
0x140062fca  mov     cs:?Real_RegEnumKeyExA@@3P6AJPEAUHKEY__@@KPEADPEAK212PEAU_FILETIME@@@ZEA, rax; long (*Real_RegEnumKeyExA)(HKEY__ *,ulong,char *,ulong *,ulong *,char *,ulong *,_FILETIME *)
0x140062fd1  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x140062fd8  mov     rcx, rbx; hModule
0x140062fdb  call    cs:__imp_GetProcAddress
0x140062fe1  xor     edi, edi
0x140062fe3  test    rax, rax
0x140062fe6  setz    dil
0x140062fea  test    rax, rax
0x140062fed  jz      loc_140062D3B
0x140062ff3  mov     cs:?Real_RegEnumKeyExW@@3P6AJPEAUHKEY__@@KPEAGPEAK212PEAU_FILETIME@@@ZEA, rax; long (*Real_RegEnumKeyExW)(HKEY__ *,ulong,ushort *,ulong *,ulong *,ushort *,ulong *,_FILETIME *)
0x140062ffa  lea     rdx, aRegenumvaluea; "RegEnumValueA"
0x140063001  mov     rcx, rbx; hModule
0x140063004  call    cs:__imp_GetProcAddress
0x14006300a  xor     edi, edi
0x14006300c  test    rax, rax
0x14006300f  setz    dil
0x140063013  test    rax, rax
0x140063016  jz      loc_140062D3B
0x14006301c  mov     cs:?Real_RegEnumValueA@@3P6AJPEAUHKEY__@@KPEADPEAK22PEAE2@ZEA, rax; long (*Real_RegEnumValueA)(HKEY__ *,ulong,char *,ulong *,ulong *,ulong *,uchar *,ulong *)
0x140063023  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x14006302a  mov     rcx, rbx; hModule
0x14006302d  call    cs:__imp_GetProcAddress
0x140063033  xor     edi, edi
0x140063035  test    rax, rax
0x140063038  setz    dil
0x14006303c  test    rax, rax
0x14006303f  jz      loc_140062D3B
0x140063045  mov     cs:?Real_RegEnumValueW@@3P6AJPEAUHKEY__@@KPEAGPEAK22PEAE2@ZEA, rax; long (*Real_RegEnumValueW)(HKEY__ *,ulong,ushort *,ulong *,ulong *,ulong *,uchar *,ulong *)
0x14006304c  lea     rdx, aRegqueryinfoke_0; "RegQueryInfoKeyA"
0x140063053  mov     rcx, rbx; hModule
0x140063056  call    cs:__imp_GetProcAddress
0x14006305c  xor     edi, edi
0x14006305e  test    rax, rax
0x140063061  setz    dil
0x140063065  test    rax, rax
0x140063068  jz      loc_140062D3B
0x14006306e  mov     cs:?Real_RegQueryInfoKeyA@@3P6AJPEAUHKEY__@@PEADPEAK22222222PEAU_FILETIME@@@ZEA, rax; long (*Real_RegQueryInfoKeyA)(HKEY__ *,char *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *)
0x140063075  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x14006307c  mov     rcx, rbx; hModule
0x14006307f  call    cs:__imp_GetProcAddress
0x140063085  xor     ebx, ebx
0x140063087  test    rax, rax
0x14006308a  setz    bl
0x14006308d  test    rax, rax
0x140063090  jnz     short loc_1400630A2
0x140063092  call    DetourTransactionAbort
0x140063097  or      ebx, 80070000h
0x14006309d  jmp     loc_140063467
0x1400630a2  mov     cs:?Real_RegQueryInfoKeyW@@3P6AJPEAUHKEY__@@PEAGPEAK22222222PEAU_FILETIME@@@ZEA, rax; long (*Real_RegQueryInfoKeyW)(HKEY__ *,ushort *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *)
0x1400630a9  call    DetourTransactionBegin
0x1400630ae  mov     ecx, eax
0x1400630b0  test    eax, eax
0x1400630b2  jz      short loc_1400630C6
0x1400630b4  movzx   eax, cx
0x1400630b7  or      eax, 80070000h
0x1400630bc  test    ecx, ecx
0x1400630be  cmovle  eax, ecx
0x1400630c1  jmp     loc_140063469
0x1400630c6  call    cs:__imp_GetProcessHeap
0x1400630cc  mov     rcx, rax; hHeap
0x1400630cf  call    cs:__imp_HeapLock
0x1400630d5  xor     eax, eax
0x1400630d7  mov     [rsp+170h+var_138], rax
0x1400630dc  xorps   xmm1, xmm1
0x1400630df  movdqu  xmmword ptr [rsp+170h+var_150+8], xmm1
0x1400630e5  and     [rsp+170h+var_138], rax
0x1400630ea  lea     rcx, [rsp+170h+var_150+8]
0x1400630ef  nop
0x1400630f0  call    ?DetourUpdateAllThreads@@YAJAEAV?$vector@PEAXV?$allocator@PEAX@std@@@std@@@Z; DetourUpdateAllThreads(std::vector<void *> &)
0x1400630f5  mov     edi, eax
0x1400630f7  test    eax, eax
0x1400630f9  jz      short loc_140063113
0x1400630fb  call    DetourTransactionAbort
0x140063100  movzx   ebx, di
0x140063103  or      ebx, 80070000h
0x140063109  test    edi, edi
0x14006310b  cmovle  ebx, edi
0x14006310e  jmp     loc_1400633FB
0x140063113  lea     rdx, ?Mine_RegCreateKeyExA@CDetourRules@@CAJPEAUHKEY__@@PEBDKPEADKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; CDetourRules::Mine_RegCreateKeyExA(HKEY__ *,char const *,ulong,char *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x14006311a  lea     rcx, ?Real_RegCreateKeyExA@@3P6AJPEAUHKEY__@@PEBDKPEADKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA; long (*Real_RegCreateKeyExA)(HKEY__ *,char const *,ulong,char *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x140063121  call    DetourAttach
0x140063126  test    eax, eax
0x140063128  jnz     loc_14006339E
0x14006312e  lea     rdx, ?Mine_RegCreateKeyExW@CDetourRules@@CAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; CDetourRules::Mine_RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x140063135  lea     rcx, ?Real_RegCreateKeyExW@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA; long (*Real_RegCreateKeyExW)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x14006313c  call    DetourAttach
0x140063141  test    eax, eax
0x140063143  jnz     loc_14006339E
0x140063149  lea     rdx, ?Mine_RegOpenKeyExA@CDetourRules@@CAJPEAUHKEY__@@PEBDKKPEAPEAU2@@Z; CDetourRules::Mine_RegOpenKeyExA(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x140063150  lea     rcx, ?Real_RegOpenKeyExA@@3P6AJPEAUHKEY__@@PEBDKKPEAPEAU1@@ZEA; long (*Real_RegOpenKeyExA)(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x140063157  call    DetourAttach
0x14006315c  test    eax, eax
0x14006315e  jnz     loc_14006339E
0x140063164  lea     rdx, ?Mine_RegOpenKeyExW@CDetourRules@@CAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z; CDetourRules::Mine_RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x14006316b  lea     rcx, ?Real_RegOpenKeyExW@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*Real_RegOpenKeyExW)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140063172  call    DetourAttach
0x140063177  test    eax, eax
0x140063179  jnz     loc_14006339E
0x14006317f  lea     rdx, ?Mine_RegCloseKey@@YAJPEAUHKEY__@@@Z; Mine_RegCloseKey(HKEY__ *)
0x140063186  lea     rcx, ?Real_RegCloseKey@@3P6AJPEAUHKEY__@@@ZEA; long (*Real_RegCloseKey)(HKEY__ *)
0x14006318d  call    DetourAttach
0x140063192  test    eax, eax
0x140063194  jnz     loc_14006339E
0x14006319a  lea     rdx, ?Mine_RegQueryValueExA@@YAJPEAUHKEY__@@PEBDPEAK2PEAE2@Z; Mine_RegQueryValueExA(HKEY__ *,char const *,ulong *,ulong *,uchar *,ulong *)
0x1400631a1  lea     rcx, ?Real_RegQueryValueExA@@3P6AJPEAUHKEY__@@PEBDPEAK2PEAE2@ZEA; long (*Real_RegQueryValueExA)(HKEY__ *,char const *,ulong *,ulong *,uchar *,ulong *)
0x1400631a8  call    DetourAttach
0x1400631ad  test    eax, eax
0x1400631af  jnz     loc_14006339E
0x1400631b5  lea     rdx, ?Mine_RegQueryValueExW@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2@Z; Mine_RegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)
0x1400631bc  lea     rcx, ?Real_RegQueryValueExW@@3P6AJPEAUHKEY__@@PEBGPEAK2PEAE2@ZEA; long (*Real_RegQueryValueExW)(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)
0x1400631c3  call    DetourAttach
0x1400631c8  test    eax, eax
0x1400631ca  jnz     loc_14006339E
0x1400631d0  lea     rdx, ?Mine_RegDeleteKeyA@CDetourRules@@CAJPEAUHKEY__@@PEBD@Z; CDetourRules::Mine_RegDeleteKeyA(HKEY__ *,char const *)
0x1400631d7  lea     rcx, ?Real_RegDeleteKeyA@@3P6AJPEAUHKEY__@@PEBD@ZEA; long (*Real_RegDeleteKeyA)(HKEY__ *,char const *)
0x1400631de  call    DetourAttach
0x1400631e3  test    eax, eax
0x1400631e5  jnz     loc_14006339E
0x1400631eb  lea     rdx, ?Mine_RegDeleteKeyW@CDetourRules@@CAJPEAUHKEY__@@PEBG@Z; CDetourRules::Mine_RegDeleteKeyW(HKEY__ *,ushort const *)
0x1400631f2  lea     rcx, ?Real_RegDeleteKeyW@@3P6AJPEAUHKEY__@@PEBG@ZEA; long (*Real_RegDeleteKeyW)(HKEY__ *,ushort const *)
0x1400631f9  call    DetourAttach
0x1400631fe  test    eax, eax
0x140063200  jnz     loc_14006339E
0x140063206  lea     rdx, ?Mine_RegDeleteKeyExA@CDetourRules@@CAJPEAUHKEY__@@PEBDKK@Z; CDetourRules::Mine_RegDeleteKeyExA(HKEY__ *,char const *,ulong,ulong)
0x14006320d  lea     rcx, ?Real_RegDeleteKeyExA@@3P6AJPEAUHKEY__@@PEBDKK@ZEA; long (*Real_RegDeleteKeyExA)(HKEY__ *,char const *,ulong,ulong)
0x140063214  call    DetourAttach
  ... truncated ...
```
