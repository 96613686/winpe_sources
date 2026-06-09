# NgcStatusStorage::Load(HKEY__ *,ushort const *)

- ea: `0x180009050`
- end: `0x180009509`
- name: `?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `1209`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008f74`

## callees

- `0x1800073c0`
- `0x180009050`
- `0x18000c160`
- `0x18000ced0`
- `0x18000d240`
- `0x18000d2f0`
- `0x18000e414`
- `0x180027448`
- `0x1800274cc`
- `0x18002b998`
- `0x18002bc58`
- `0x18002cd24`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000927e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000927e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800091d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800091d5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000937e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000937e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094b1`
- `RPCRT4!UuidFromStringW` at `0x18000939d`
- `RPCRT4!UuidFromStringW` at `0x18000939d`

## string_xrefs

- `0x180009115`: `hUserRegistry`
- `0x1800093aa`: `%s: The registry key "%s" is not a valid NGC key ID. Error code: 0x%08x.`
- `0x1800091f4`: `%s: The registry key "%s\%s" does not exist. Noting to read.`
- `0x18000944f`: `%s: Cannot enumerate keys under registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180009193`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000918c`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180009220`: `RegOpenKeyExW`
- `0x1800092aa`: `%s: Cannot query values of registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180009484`: `%s: There is no valid key registry.`
- `0x180009236`: `%s: Cannot open registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180009421`: `%s: Failed to read registry key "%s\%s\%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Load(NgcStatusStorage *this, HKEY hKey, const unsigned __int16 *a3)
{
  WCHAR *v4; // rsi
  unsigned __int64 v6; // rdi
  __int64 v7; // r15
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  signed int v13; // edi
  __int64 v14; // r8
  unsigned int v15; // eax
  LSTATUS v16; // eax
  int v17; // r12d
  const unsigned __int16 *v18; // rcx
  LSTATUS v19; // eax
  const unsigned __int16 *v20; // r8
  DWORD v21; // eax
  size_t v22; // r14
  _BYTE *v23; // rax
  __int64 v24; // rcx
  DWORD v25; // r15d
  LSTATUS v26; // eax
  const unsigned __int16 *v27; // r8
  unsigned int v28; // eax
  struct STRUCT_NGC_REG_KEY *v29; // r9
  unsigned int v30; // eax
  HANDLE v31; // rax
  PHKEY phkResult; // [rsp+28h] [rbp-99h]
  const unsigned __int16 *phkResulta; // [rsp+28h] [rbp-99h]
  const unsigned __int16 *phkResultb; // [rsp+28h] [rbp-99h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+30h] [rbp-91h]
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-55h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp-51h] BYREF
  DWORD cchName[4]; // [rsp+78h] [rbp-49h] BYREF
  struct _GUID v41; // [rsp+88h] [rbp-39h] BYREF
  UUID Uuid; // [rsp+98h] [rbp-29h] BYREF
  _BYTE v43[16]; // [rsp+A8h] [rbp-19h] BYREF
  const wchar_t *v44; // [rsp+B8h] [rbp-9h]
  __int64 v45; // [rsp+C0h] [rbp-1h]
  const wchar_t *v46; // [rsp+C8h] [rbp+7h]
  __int64 v47; // [rsp+D0h] [rbp+Fh]

  v4 = 0;
  v6 = 0;
  hKeya = 0;
  cSubKeys = 0;
  for ( cbMaxSubKeyLen = 0; v6 < *((_QWORD *)this + 1); ++v6 )
  {
    v7 = *(_QWORD *)this + (v6 << 6);
    if ( v7 )
    {
      SafeFree(*(void **)(v7 + 16));
      v8 = *(void **)(v7 + 40);
      *(_QWORD *)(v7 + 16) = 0;
      SafeFree(v8);
      v9 = *(void **)(v7 + 48);
      *(_QWORD *)(v7 + 40) = 0;
      SafeFree(v9);
      v10 = *(void **)(v7 + 56);
      *(_QWORD *)(v7 + 48) = 0;
      SafeFree(v10);
      *(_QWORD *)(v7 + 56) = 0;
    }
  }
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( !hKey )
  {
    v13 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcStatusStorage::Load", L"hUserRegistry");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v44 = L"NgcStatusStorage::Load";
      v45 = 46;
      v46 = L"hUserRegistry";
      v47 = 28;
      v15 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v14,
              3,
              v43);
      if ( v15 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v15);
    }
    goto LABEL_41;
  }
  v13 = 0;
  v16 = RegOpenKeyExW(
          hKey,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
          0,
          0x20019u,
          &hKeya);
  v17 = v16;
  if ( v16 == 2 )
  {
    Logger::TraceVerbose(
      L"%s: The registry key \"%s\\%s\" does not exist. Noting to read.",
      L"NgcStatusStorage::Load",
      L"HKEY_CURRENT_USER",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    goto LABEL_41;
  }
  if ( v16 )
  {
    Logger::WriteRegistryFailureEventEx(
      v16,
      L"RegOpenKeyExW",
      L"%s\\%s",
      L"HKEY_CURRENT_USER",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    v18 = L"%s: Cannot open registry key \"%s\\%s\". Win32 error code: 0x%08x.";
    goto LABEL_36;
  }
  v19 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v17 = v19;
  if ( v19 )
  {
    Logger::WriteRegistryFailureEvent(v19, L"RegQueryInfoKeyW", v20, L"HKEY_CURRENT_USER", phkResulta);
    v18 = L"%s: Cannot query values of registry key \"%s\\%s\". Win32 error code: 0x%08x.";
LABEL_36:
    LODWORD(phkResult) = v17;
    Logger::TraceError(
      v18,
      L"NgcStatusStorage::Load",
      L"HKEY_CURRENT_USER",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
      phkResult);
LABEL_37:
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    else
      v13 = v17;
    goto LABEL_41;
  }
  v21 = cSubKeys;
  if ( cSubKeys && cbMaxSubKeyLen )
  {
    if ( cSubKeys > 0x400 )
      v21 = 1024;
    v22 = (unsigned __int64)v21 << 6;
    v23 = MIDL_user_allocate(v22);
    *(_QWORD *)this = v23;
    if ( !v23 )
      goto LABEL_25;
    for ( ; v22; --v22 )
      *v23++ = 0;
    v24 = cbMaxSubKeyLen + 1;
    *((_QWORD *)this + 1) = 0;
    v4 = (WCHAR *)MIDL_user_allocate(2 * v24);
    if ( v4 )
    {
      v25 = 0;
      while ( v25 < cSubKeys && *((_QWORD *)this + 1) < 0x400u )
      {
        cchName[0] = cbMaxSubKeyLen + 1;
        v26 = RegEnumKeyExW(hKeya, v25, v4, cchName, 0, 0, 0, 0);
        v17 = v26;
        if ( v26 )
        {
          Logger::WriteRegistryFailureEvent(v26, L"RegEnumKeyExW", v27, L"HKEY_CURRENT_USER", phkResultb);
          v18 = L"%s: Cannot enumerate keys under registry key \"%s\\%s\". Win32 error code: 0x%08x.";
          goto LABEL_36;
        }
        Uuid = 0;
        v28 = UuidFromStringW(v4, &Uuid);
        if ( v28 )
        {
          Logger::TraceInformation(
            L"%s: The registry key \"%s\" is not a valid NGC key ID. Error code: 0x%08x.",
            L"NgcStatusStorage::Load",
            v4,
            v28);
          ++v25;
        }
        else
        {
          v29 = (struct STRUCT_NGC_REG_KEY *)(*(_QWORD *)this + (*((_QWORD *)this + 1) << 6));
          v41 = Uuid;
          v30 = NgcStatusStorage::ReadKey(hKeya, v4, &v41, v29);
          v17 = v30;
          if ( v30 )
          {
            LODWORD(lpcbMaxSubKeyLen) = v30;
            Logger::TraceError(
              L"%s: Failed to read registry key \"%s\\%s\\%s\". Error code: 0x%08x.",
              L"NgcStatusStorage::Load",
              L"HKEY_CURRENT_USER",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
              v4,
              lpcbMaxSubKeyLen);
            goto LABEL_37;
          }
          ++*((_QWORD *)this + 1);
          ++v25;
        }
      }
    }
    else
    {
LABEL_25:
      v13 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"NgcStatusStorage::Load");
    }
  }
  else
  {
    Logger::TraceVerbose(L"%s: There is no valid key registry.", L"NgcStatusStorage::Load");
  }
LABEL_41:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( v4 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v4);
  }
  if ( v13 < 0 )
    NgcStatusStorage::Cleanup(this);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180009050  mov     r11, rsp
0x180009053  push    rbp
0x180009054  push    rbx
0x180009055  push    rdi
0x180009056  lea     rbp, [r11-5Fh]
0x18000905a  sub     rsp, 100h
0x180009061  mov     rax, cs:__security_cookie
0x180009068  xor     rax, rsp
0x18000906b  mov     [rbp+57h+var_40], rax
0x18000906f  mov     [r11+18h], rsi
0x180009073  mov     rbx, rcx
0x180009076  mov     [r11-28h], r13
0x18000907a  xor     r13d, r13d
0x18000907d  mov     esi, r13d
0x180009080  mov     [r11-30h], r14
0x180009084  mov     r14, rdx
0x180009087  mov     [r11-38h], r15
0x18000908b  mov     edi, r13d
0x18000908e  mov     [rbp+57h+hKey], r13
0x180009092  mov     [rbp+57h+cSubKeys], r13d
0x180009096  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18000909a  cmp     [rcx+8], r13
0x18000909e  jbe     short loc_1800090E9
0x1800090a0  mov     r15, rdi
0x1800090a3  shl     r15, 6
0x1800090a7  add     r15, [rbx]
0x1800090aa  jz      short loc_1800090E0
0x1800090ac  mov     rcx, [r15+10h]; lpMem
0x1800090b0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800090b5  mov     rcx, [r15+28h]; lpMem
0x1800090b9  mov     [r15+10h], r13
0x1800090bd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800090c2  mov     rcx, [r15+30h]; lpMem
0x1800090c6  mov     [r15+28h], r13
0x1800090ca  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800090cf  mov     rcx, [r15+38h]; lpMem
0x1800090d3  mov     [r15+30h], r13
0x1800090d7  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800090dc  mov     [r15+38h], r13
0x1800090e0  inc     rdi
0x1800090e3  cmp     rdi, [rbx+8]
0x1800090e7  jb      short loc_1800090A0
0x1800090e9  mov     rdi, [rbx]
0x1800090ec  test    rdi, rdi
0x1800090ef  jz      short loc_180009105
0x1800090f1  call    cs:__imp_GetProcessHeap
0x1800090f7  mov     r8, rdi; lpMem
0x1800090fa  xor     edx, edx; dwFlags
0x1800090fc  mov     rcx, rax; hHeap
0x1800090ff  call    cs:__imp_HeapFree
0x180009105  mov     [rbx], r13
0x180009108  mov     [rbx+8], r13
0x18000910c  test    r14, r14
0x18000910f  jnz     loc_1800091AB
0x180009115  lea     r15, aHuserregistry; "hUserRegistry"
0x18000911c  mov     edi, 80070057h
0x180009121  lea     r14, aNgcstatusstora; "NgcStatusStorage::Load"
0x180009128  mov     r8, r15
0x18000912b  mov     rdx, r14
0x18000912e  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180009135  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000913a  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180009141  jz      loc_180009498
0x180009147  lea     rax, [rbp+57h+var_70]
0x18000914b  mov     [rbp+57h+var_60], r14
0x18000914f  mov     r9d, 3
0x180009155  mov     [rsp+110h+phkResult], rax
0x18000915a  lea     rdx, NullOrEmptyParameterFailureEvent
0x180009161  mov     [rbp+57h+var_58], 2Eh ; '.'
0x180009169  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180009170  mov     [rbp+57h+var_50], r15
0x180009174  mov     [rbp+57h+var_48], 1Ch
0x18000917c  call    McGenEventWrite_EventWriteTransfer
0x180009181  test    eax, eax
0x180009183  jz      loc_180009498
0x180009189  mov     r9d, eax
0x18000918c  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180009193  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000919a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800091a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800091a6  jmp     loc_180009498
0x1800091ab  lea     rax, [rbp+57h+hKey]
0x1800091af  mov     [rsp+0F8h], r12
0x1800091b7  lea     r15, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800091be  mov     [rsp+110h+phkResult], rax; phkResult
0x1800091c3  mov     rdx, r15; lpSubKey
0x1800091c6  mov     r9d, 20019h; samDesired
0x1800091cc  xor     r8d, r8d; ulOptions
0x1800091cf  mov     rcx, r14; hKey
0x1800091d2  mov     edi, r13d
0x1800091d5  call    cs:__imp_RegOpenKeyExW
0x1800091db  mov     r12d, eax
0x1800091de  cmp     eax, 2
0x1800091e1  jnz     short loc_180009205
0x1800091e3  mov     r9, r15
0x1800091e6  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800091ed  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800091f4  lea     rcx, aSTheRegistryKe_5; "%s: The registry key \"%s\\%s\" does no"...
0x1800091fb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180009200  jmp     loc_180009490
0x180009205  test    r12d, r12d
0x180009208  jz      short loc_180009242
0x18000920a  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180009211  mov     [rsp+110h+phkResult], r15
0x180009216  lea     r8, aSS_0; "%s\\%s"
0x18000921d  mov     ecx, r12d; unsigned int
0x180009220  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180009227  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x18000922c  mov     r9, r15
0x18000922f  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180009236  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key \"%s\\%s\""...
0x18000923d  jmp     loc_180009456
0x180009242  mov     rcx, [rbp+57h+hKey]; hKey
0x180009246  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000924a  mov     [rsp+58h], r13; lpftLastWriteTime
0x18000924f  xor     r9d, r9d; lpReserved
0x180009252  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180009257  xor     r8d, r8d; lpcchClass
0x18000925a  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000925f  xor     edx, edx; lpClass
0x180009261  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180009266  mov     [rsp+110h+lpcValues], r13; lpcValues
0x18000926b  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180009270  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180009275  lea     rax, [rbp+57h+cSubKeys]
0x180009279  mov     [rsp+110h+phkResult], rax; unsigned __int16 *
0x18000927e  call    cs:__imp_RegQueryInfoKeyW
0x180009284  mov     r12d, eax
0x180009287  test    eax, eax
0x180009289  jz      short loc_1800092B6
0x18000928b  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180009292  mov     ecx, eax; unsigned int
0x180009294  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x18000929b  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800092a0  mov     r9, r15
0x1800092a3  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800092aa  lea     rcx, aSCannotQueryVa; "%s: Cannot query values of registry key"...
0x1800092b1  jmp     loc_180009456
0x1800092b6  mov     eax, [rbp+57h+cSubKeys]
0x1800092b9  test    eax, eax
0x1800092bb  jz      loc_18000947D
0x1800092c1  cmp     [rbp+57h+cbMaxSubKeyLen], esi
0x1800092c4  jz      loc_18000947D
0x1800092ca  mov     r12d, 400h
0x1800092d0  cmp     eax, r12d
0x1800092d3  cmova   eax, r12d
0x1800092d7  mov     r14d, eax
0x1800092da  shl     r14, 6
0x1800092de  mov     rcx, r14; size
0x1800092e1  call    MIDL_user_allocate
0x1800092e6  mov     [rbx], rax
0x1800092e9  test    rax, rax
0x1800092ec  jz      short loc_180009319
0x1800092ee  test    r14, r14
0x1800092f1  jz      short loc_180009300
0x1800092f3  mov     [rax], sil
0x1800092f6  lea     rax, [rax+1]
0x1800092fa  sub     r14, 1
0x1800092fe  jnz     short loc_1800092F3
0x180009300  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x180009303  inc     ecx
0x180009305  mov     [rbx+8], r13
0x180009309  add     rcx, rcx; size
0x18000930c  call    MIDL_user_allocate
0x180009311  mov     rsi, rax
0x180009314  test    rax, rax
0x180009317  jnz     short loc_180009336
0x180009319  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180009320  mov     edi, 8007000Eh
0x180009325  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000932c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180009331  jmp     loc_180009490
0x180009336  mov     r15d, r13d
0x180009339  lea     r14, aNgcstatusstora; "NgcStatusStorage::Load"
0x180009340  cmp     r15d, [rbp+57h+cSubKeys]
0x180009344  jnb     loc_180009490
0x18000934a  cmp     [rbx+8], r12
0x18000934e  jnb     loc_180009490
0x180009354  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180009357  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000935b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000935f  inc     eax
0x180009361  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x180009366  mov     r8, rsi; lpName
0x180009369  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x18000936e  mov     edx, r15d; dwIndex
0x180009371  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpClass
0x180009376  mov     [rbp+57h+cchName], eax
0x180009379  mov     [rsp+110h+phkResult], r13; unsigned __int16 *
0x18000937e  call    cs:__imp_RegEnumKeyExW
0x180009384  mov     r12d, eax
0x180009387  test    eax, eax
0x180009389  jnz     loc_18000942F
0x18000938f  xorps   xmm0, xmm0
0x180009392  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180009396  mov     rcx, rsi; StringUuid
0x180009399  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18000939d  call    cs:__imp_UuidFromStringW
0x1800093a3  test    eax, eax
0x1800093a5  jz      short loc_1800093CA
0x1800093a7  mov     r9d, eax
0x1800093aa  lea     rcx, aSTheRegistryKe_0; "%s: The registry key \"%s\" is not a va"...
0x1800093b1  mov     r8, rsi
0x1800093b4  mov     rdx, r14
0x1800093b7  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800093bc  inc     r15d
0x1800093bf  mov     r12d, 400h
0x1800093c5  jmp     loc_180009340
0x1800093ca  mov     r9, [rbx+8]
0x1800093ce  lea     r8, [rbp+57h+var_90]; struct _GUID
0x1800093d2  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x1800093d6  mov     rdx, rsi; unsigned __int16 *
0x1800093d9  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800093dd  shl     r9, 6
0x1800093e1  add     r9, [rbx]; struct STRUCT_NGC_REG_KEY *
0x1800093e4  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800093e9  call    ?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)
0x1800093ee  mov     r12d, eax
0x1800093f1  test    eax, eax
0x1800093f3  jnz     short loc_180009407
0x1800093f5  inc     qword ptr [rbx+8]
0x1800093f9  mov     r12d, 400h
0x1800093ff  inc     r15d
0x180009402  jmp     loc_180009340
0x180009407  mov     dword ptr [rsp+110h+lpcbMaxSubKeyLen], eax
0x18000940b  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180009412  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180009419  mov     [rsp+110h+phkResult], rsi
0x18000941e  mov     rdx, r14
0x180009421  lea     rcx, aSFailedToReadR; "%s: Failed to read registry key \"%s\\%"...
0x180009428  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000942d  jmp     short loc_180009467
0x18000942f  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180009436  mov     ecx, r12d; unsigned int
0x180009439  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x180009440  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180009445  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000944c  mov     rdx, r14
0x18000944f  lea     rcx, aSCannotEnumera; "%s: Cannot enumerate keys under registr"...
0x180009456  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18000945d  mov     dword ptr [rsp+110h+phkResult], r12d
0x180009462  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009467  test    r12d, r12d
0x18000946a  jg      short loc_180009471
0x18000946c  mov     edi, r12d
0x18000946f  jmp     short loc_180009490
0x180009471  movzx   edi, r12w
0x180009475  or      edi, 80070000h
0x18000947b  jmp     short loc_180009490
0x18000947d  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180009484  lea     rcx, aSThereIsNoVali; "%s: There is no valid key registry."
0x18000948b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180009490  mov     r12, [rsp+0F8h]
0x180009498  mov     rcx, [rbp+57h+hKey]; hKey
0x18000949c  mov     r15, [rsp+110h+var_30]
0x1800094a4  mov     r14, [rsp+110h+var_28]
0x1800094ac  test    rcx, rcx
0x1800094af  jz      short loc_1800094BB
0x1800094b1  call    cs:__imp_RegCloseKey
0x1800094b7  mov     [rbp+57h+hKey], r13
0x1800094bb  mov     r13, [rsp+110h+var_20]
0x1800094c3  test    rsi, rsi
0x1800094c6  jz      short loc_1800094DC
0x1800094c8  call    cs:__imp_GetProcessHeap
0x1800094ce  mov     r8, rsi; lpMem
0x1800094d1  xor     edx, edx; dwFlags
0x1800094d3  mov     rcx, rax; hHeap
0x1800094d6  call    cs:__imp_HeapFree
0x1800094dc  mov     rsi, [rsp+110h+arg_10]
0x1800094e4  test    edi, edi
0x1800094e6  jns     short loc_1800094F0
0x1800094e8  mov     rcx, rbx; this
0x1800094eb  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x1800094f0  mov     eax, edi
0x1800094f2  mov     rcx, [rbp+57h+var_40]
0x1800094f6  xor     rcx, rsp; StackCookie
0x1800094f9  call    __security_check_cookie
0x1800094fe  add     rsp, 100h
0x180009505  pop     rdi
0x180009506  pop     rbx
0x180009507  pop     rbp
0x180009508  retn
```
