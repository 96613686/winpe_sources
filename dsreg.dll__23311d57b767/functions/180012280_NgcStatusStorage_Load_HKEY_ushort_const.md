# NgcStatusStorage::Load(HKEY__ *,ushort const *)

- ea: `0x180012280`
- end: `0x180012885`
- name: `?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `1541`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800121a8`
- `0x180029e68`

## callees

- `0x1800049f0`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000cbd8`
- `0x18000fba0`
- `0x1800107f0`
- `0x180012280`
- `0x18001288c`
- `0x180012948`
- `0x180012cf0`
- `0x18003334c`
- `0x18004255c`
- `0x180044300`
- `0x18008cf20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012396`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001245f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012396`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001245f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012475`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001246d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001246d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012483`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012362`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012362`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012589`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012589`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001230a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001230a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012869`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012869`
- `RPCRT4!UuidFromStringW` at `0x1800125a7`
- `RPCRT4!UuidFromStringW` at `0x1800125a7`

## string_xrefs

- `0x1800127b5`: `RegOpenKeyExW`
- `0x1800125b4`: `%s: The registry key "%s" is not a valid NGC key ID. Error code: 0x%08x.`
- `0x180012408`: `%s: The registry key "%s\%s" does not exist. Noting to read.`
- `0x18001248b`: `hUserRegistry`
- `0x180012528`: `%s: There is no valid key registry.`
- `0x180012619`: `%s: Failed to read registry key "%s\%s\%s". Error code: 0x%08x.`
- `0x180012509`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180012502`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x1800127ca`: `%s: Cannot open registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x1800127fe`: `%s: Cannot query values of registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180012840`: `%s: Cannot enumerate keys under registry key "%s\%s". Win32 error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Load(NgcStatusStorage *this, HKEY hKey, const unsigned __int16 *a3)
{
  WCHAR *v4; // rsi
  _WORD *v5; // r15
  signed int v8; // ebx
  const unsigned __int16 *v9; // r13
  LSTATUS v10; // eax
  int v11; // edi
  LSTATUS v12; // eax
  DWORD v13; // eax
  SIZE_T v14; // rdi
  HANDLE ProcessHeap; // rax
  _BYTE *v16; // rax
  __int64 v17; // rcx
  HANDLE v19; // rax
  HANDLE v20; // rax
  __int64 v21; // r8
  unsigned int v22; // eax
  DWORD i; // ecx
  LSTATUS v24; // eax
  unsigned int v25; // eax
  struct STRUCT_NGC_REG_KEY *v26; // r9
  int v27; // eax
  const unsigned __int16 *v28; // rax
  __int64 v29; // rcx
  int v30; // r13d
  unsigned __int64 v31; // rbx
  bool v32; // zf
  unsigned __int64 v33; // rbx
  int v34; // eax
  int v35; // eax
  __int64 v36; // r10
  __int64 v37; // r9
  int v38; // eax
  const wchar_t *v39; // r8
  const unsigned __int16 *v40; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-99h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-91h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-55h] BYREF
  DWORD cchName[2]; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp-49h] BYREF
  __int64 v47; // [rsp+78h] [rbp-41h]
  struct _GUID v48; // [rsp+80h] [rbp-39h] BYREF
  UUID Uuid; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v50[16]; // [rsp+A0h] [rbp-19h] BYREF
  const wchar_t *v51; // [rsp+B0h] [rbp-9h]
  __int64 v52; // [rsp+B8h] [rbp-1h]
  const unsigned __int16 *v53; // [rsp+C0h] [rbp+7h]
  __int64 v54; // [rsp+C8h] [rbp+Fh]

  hKeya = 0;
  v4 = 0;
  cSubKeys = 0;
  v5 = 0;
  cbMaxSubKeyLen = 0;
  NgcStatusStorage::Cleanup(this);
  if ( !hKey )
  {
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcStatusStorage::Load", L"hUserRegistry");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v51 = L"NgcStatusStorage::Load";
      v52 = 46;
      v53 = L"hUserRegistry";
      v54 = 28;
      v22 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v21,
              3,
              v50);
      if ( v22 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v22);
    }
    goto LABEL_17;
  }
  if ( !a3 || !*a3 )
  {
    v8 = 0;
    v9 = L"HKEY_CURRENT_USER";
    goto LABEL_5;
  }
  *(_QWORD *)cchName = 0;
  v35 = StringCchLengthW(L"HKEY_USERS\\", 0x7FFFFFFFu, (unsigned __int64 *)cchName);
  v30 = v35;
  if ( v35 < 0 )
  {
    v37 = (unsigned int)v35;
LABEL_60:
    v39 = L"StringCchLengthW";
    goto LABEL_61;
  }
  v29 = v36;
  v28 = a3;
  do
  {
    if ( !*v28 )
      break;
    ++v28;
    --v29;
  }
  while ( v29 );
  v30 = -2147024809;
  if ( !v29 )
  {
    v37 = 2147942487LL;
    goto LABEL_60;
  }
  v30 = 0;
  v31 = *(_QWORD *)cchName;
  v47 = v36 - v29;
  *(_QWORD *)cchName += v36 - v29 + 1;
  v5 = SafeAlloc(2LL * *(_QWORD *)cchName);
  if ( !v5 )
  {
    v30 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"StringCat");
LABEL_62:
    SafeFree(v5);
    v5 = 0;
    v8 = v30;
    goto LABEL_50;
  }
  v32 = v31 == 0;
  *v5 = 0;
  v33 = *(_QWORD *)cchName;
  if ( !v32 )
  {
    v38 = StringCchCatW(v5, *(unsigned __int64 *)cchName, L"HKEY_USERS\\");
    v30 = v38;
    if ( v38 < 0 )
    {
      v37 = (unsigned int)v38;
      v39 = L"StringCchCatW";
LABEL_61:
      Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"StringCat", v39, v37);
      goto LABEL_62;
    }
  }
  if ( v47 )
  {
    v34 = StringCchCatW(v5, v33, a3);
    v30 = v34;
    if ( v34 < 0 )
    {
      v37 = (unsigned int)v34;
      v39 = L"StringCchCatW";
      goto LABEL_61;
    }
  }
  v8 = v30;
  if ( v30 < 0 )
  {
LABEL_50:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"NgcStatusStorage::Load",
      L"StringCat",
      (unsigned int)v30);
    goto LABEL_17;
  }
  v9 = v5;
LABEL_5:
  v10 = RegOpenKeyExW(
          hKey,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
          0,
          0x20019u,
          &hKeya);
  v11 = v10;
  if ( v10 == 2 )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: The registry key \"%s\\%s\" does not exist. Noting to read.",
      L"NgcStatusStorage::Load",
      v9,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    goto LABEL_17;
  }
  if ( v10 )
  {
    Logger::WriteRegistryFailureEventEx(
      v10,
      L"RegOpenKeyExW",
      L"%s\\%s",
      v9,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    v40 = L"%s: Cannot open registry key \"%s\\%s\". Win32 error code: 0x%08x.";
    goto LABEL_68;
  }
  v12 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v11 = v12;
  if ( v12 )
  {
    Logger::WriteRegistryFailureEvent(
      v12,
      L"RegQueryInfoKeyW",
      L"%s\\%s",
      v9,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    v40 = L"%s: Cannot query values of registry key \"%s\\%s\". Win32 error code: 0x%08x.";
LABEL_68:
    LODWORD(phkResult) = v11;
    Logger::TraceError(
      v40,
      L"NgcStatusStorage::Load",
      v9,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
      phkResult);
LABEL_40:
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    else
      v8 = v11;
    goto LABEL_17;
  }
  v13 = cSubKeys;
  if ( cSubKeys && cbMaxSubKeyLen )
  {
    if ( cSubKeys > 0x400 )
      v13 = 1024;
    v14 = (unsigned __int64)v13 << 6;
    ProcessHeap = GetProcessHeap();
    v16 = HeapAlloc(ProcessHeap, 8u, v14);
    *(_QWORD *)this = v16;
    if ( !v16 )
      goto LABEL_15;
    for ( ; v14; --v14 )
      *v16++ = 0;
    v17 = cbMaxSubKeyLen + 1;
    *((_QWORD *)this + 1) = 0;
    v4 = (WCHAR *)SafeAlloc(2 * v17);
    if ( v4 )
    {
      for ( i = 0; ; i = v47 + 1 )
      {
        LODWORD(v47) = i;
        if ( i >= cSubKeys || *((_QWORD *)this + 1) >= 0x400u )
          break;
        cchName[0] = cbMaxSubKeyLen + 1;
        v24 = RegEnumKeyExW(hKeya, i, v4, cchName, 0, 0, 0, 0);
        v11 = v24;
        if ( v24 )
        {
          Logger::WriteRegistryFailureEvent(
            v24,
            L"RegEnumKeyExW",
            L"%s\\%s",
            v9,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
          v40 = L"%s: Cannot enumerate keys under registry key \"%s\\%s\". Win32 error code: 0x%08x.";
          goto LABEL_68;
        }
        Uuid = 0;
        v25 = UuidFromStringW(v4, &Uuid);
        if ( v25 )
        {
          Logger::TraceInformation(
            L"%s: The registry key \"%s\" is not a valid NGC key ID. Error code: 0x%08x.",
            L"NgcStatusStorage::Load",
            v4,
            v25);
        }
        else
        {
          v26 = (struct STRUCT_NGC_REG_KEY *)(*(_QWORD *)this + (*((_QWORD *)this + 1) << 6));
          v48 = Uuid;
          v27 = NgcStatusStorage::ReadKey(hKeya, v4, &v48, v26);
          v11 = v27;
          if ( v27 )
          {
            LODWORD(lpcbMaxSubKeyLen) = v27;
            Logger::TraceError(
              L"%s: Failed to read registry key \"%s\\%s\\%s\". Error code: 0x%08x.",
              L"NgcStatusStorage::Load",
              v9,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
              v4,
              lpcbMaxSubKeyLen);
            goto LABEL_40;
          }
          ++*((_QWORD *)this + 1);
        }
      }
    }
    else
    {
LABEL_15:
      v8 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"NgcStatusStorage::Load");
    }
  }
  else
  {
    Logger::TraceVerbose((wchar_t *)L"%s: There is no valid key registry.", L"NgcStatusStorage::Load");
  }
LABEL_17:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( v4 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v4);
  }
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  if ( v8 < 0 )
    NgcStatusStorage::Cleanup(this);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012280  mov     [rsp-8+arg_18], rbx
0x180012285  push    rbp
0x180012286  push    rsi
0x180012287  push    rdi
0x180012288  push    r12
0x18001228a  push    r13
0x18001228c  push    r14
0x18001228e  push    r15
0x180012290  lea     rbp, [rsp-27h]
0x180012295  sub     rsp, 0E0h
0x18001229c  mov     rax, cs:__security_cookie
0x1800122a3  xor     rax, rsp
0x1800122a6  mov     [rbp+57h+var_40], rax
0x1800122aa  xor     r13d, r13d
0x1800122ad  mov     rdi, r8
0x1800122b0  mov     [rbp+57h+hKey], r13
0x1800122b4  mov     esi, r13d
0x1800122b7  mov     [rbp+57h+cSubKeys], r13d
0x1800122bb  mov     r15d, r13d
0x1800122be  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x1800122c2  mov     r14, rdx
0x1800122c5  mov     r12, rcx
0x1800122c8  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x1800122cd  test    r14, r14
0x1800122d0  jz      loc_18001248B
0x1800122d6  test    rdi, rdi
0x1800122d9  jz      short loc_1800122E4
0x1800122db  cmp     [rdi], si
0x1800122de  jnz     loc_1800126E3
0x1800122e4  mov     ebx, r13d
0x1800122e7  lea     r13, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800122ee  lea     rax, [rbp+57h+hKey]
0x1800122f2  mov     r9d, 20019h; samDesired
0x1800122f8  xor     r8d, r8d; ulOptions
0x1800122fb  mov     [rsp+110h+phkResult], rax; phkResult
0x180012300  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180012307  mov     rcx, r14; hKey
0x18001230a  call    cs:__imp_RegOpenKeyExW
0x180012310  mov     edi, eax
0x180012312  cmp     eax, 2
0x180012315  jz      loc_1800123F7
0x18001231b  test    eax, eax
0x18001231d  jnz     loc_18001279F
0x180012323  mov     rcx, [rbp+57h+hKey]; hKey
0x180012327  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18001232b  xor     r14d, r14d
0x18001232e  xor     r9d, r9d; lpReserved
0x180012331  mov     [rsp+110h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180012336  xor     r8d, r8d; lpcchClass
0x180012339  mov     [rsp+110h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18001233e  xor     edx, edx; lpClass
0x180012340  mov     [rsp+110h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180012345  mov     [rsp+110h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18001234a  mov     [rsp+110h+lpcValues], r14; lpcValues
0x18001234f  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180012354  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180012359  lea     rax, [rbp+57h+cSubKeys]
0x18001235d  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x180012362  call    cs:__imp_RegQueryInfoKeyW
0x180012368  mov     edi, eax
0x18001236a  test    eax, eax
0x18001236c  jnz     loc_1800127D3
0x180012372  mov     eax, [rbp+57h+cSubKeys]
0x180012375  test    eax, eax
0x180012377  jz      loc_180012521
0x18001237d  cmp     [rbp+57h+cbMaxSubKeyLen], esi
0x180012380  jz      loc_180012521
0x180012386  mov     ecx, 400h
0x18001238b  cmp     eax, ecx
0x18001238d  cmova   eax, ecx
0x180012390  mov     edi, eax
0x180012392  shl     rdi, 6
0x180012396  call    cs:__imp_GetProcessHeap
0x18001239c  mov     r8, rdi; dwBytes
0x18001239f  mov     edx, 8; dwFlags
0x1800123a4  mov     rcx, rax; hHeap
0x1800123a7  call    cs:__imp_HeapAlloc
0x1800123ad  mov     [r12], rax
0x1800123b1  test    rax, rax
0x1800123b4  jz      short loc_1800123DD
0x1800123b6  test    rdi, rdi
0x1800123b9  jnz     loc_180012807
0x1800123bf  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1800123c2  inc     ecx
0x1800123c4  mov     [r12+8], r14
0x1800123c9  add     rcx, rcx; unsigned __int64
0x1800123cc  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800123d1  mov     rsi, rax
0x1800123d4  test    rax, rax
0x1800123d7  jnz     loc_180012539
0x1800123dd  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x1800123e4  mov     ebx, 8007000Eh
0x1800123e9  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800123f0  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800123f5  jmp     short loc_180012414
0x1800123f7  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800123fe  mov     r8, r13
0x180012401  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x180012408  lea     rcx, aSTheRegistryKe_9; "%s: The registry key \"%s\\%s\" does no"...
0x18001240f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180012414  xor     r13d, r13d
0x180012417  mov     rcx, [rbp+57h+hKey]; hKey
0x18001241b  test    rcx, rcx
0x18001241e  jnz     loc_180012869
0x180012424  test    rsi, rsi
0x180012427  jnz     short loc_18001245F
0x180012429  test    r15, r15
0x18001242c  jnz     short loc_180012475
0x18001242e  test    ebx, ebx
0x180012430  js      loc_180012878
0x180012436  mov     eax, ebx
0x180012438  mov     rcx, [rbp+57h+var_40]
0x18001243c  xor     rcx, rsp; StackCookie
0x18001243f  call    __security_check_cookie
0x180012444  mov     rbx, [rsp+110h+arg_18]
0x18001244c  add     rsp, 0E0h
0x180012453  pop     r15
0x180012455  pop     r14
0x180012457  pop     r13
0x180012459  pop     r12
0x18001245b  pop     rdi
0x18001245c  pop     rsi
0x18001245d  pop     rbp
0x18001245e  retn
0x18001245f  call    cs:__imp_GetProcessHeap
0x180012465  mov     r8, rsi; lpMem
0x180012468  xor     edx, edx; dwFlags
0x18001246a  mov     rcx, rax; hHeap
0x18001246d  call    cs:__imp_HeapFree
0x180012473  jmp     short loc_180012429
0x180012475  call    cs:__imp_GetProcessHeap
0x18001247b  mov     r8, r15; lpMem
0x18001247e  xor     edx, edx; dwFlags
0x180012480  mov     rcx, rax; hHeap
0x180012483  call    cs:__imp_HeapFree
0x180012489  jmp     short loc_18001242E
0x18001248b  lea     rdi, aHuserregistry; "hUserRegistry"
0x180012492  mov     ebx, 80070057h
0x180012497  lea     r14, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x18001249e  mov     r8, rdi
0x1800124a1  mov     rdx, r14
0x1800124a4  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800124ab  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800124b0  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800124b7  jz      loc_180012417
0x1800124bd  lea     rax, [rbp+57h+var_70]
0x1800124c1  mov     [rbp+57h+var_60], r14
0x1800124c5  mov     r9d, 3
0x1800124cb  mov     [rsp+110h+phkResult], rax
0x1800124d0  lea     rdx, NullOrEmptyParameterFailureEvent
0x1800124d7  mov     [rbp+57h+var_58], 2Eh ; '.'
0x1800124df  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x1800124e6  mov     [rbp+57h+var_50], rdi
0x1800124ea  mov     [rbp+57h+var_48], 1Ch
0x1800124f2  call    McGenEventWrite_EventWriteTransfer
0x1800124f7  test    eax, eax
0x1800124f9  jz      loc_180012417
0x1800124ff  mov     r9d, eax
0x180012502  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180012509  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180012510  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180012517  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001251c  jmp     loc_180012417
0x180012521  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x180012528  lea     rcx, aSThereIsNoVali; "%s: There is no valid key registry."
0x18001252f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180012534  jmp     loc_180012414
0x180012539  mov     ecx, r14d
0x18001253c  lea     r14, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x180012543  mov     dword ptr [rbp+57h+var_98], ecx
0x180012546  cmp     ecx, [rbp+57h+cSubKeys]
0x180012549  jnb     loc_180012414
0x18001254f  cmp     qword ptr [r12+8], 400h
0x180012558  jnb     loc_180012414
0x18001255e  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180012561  lea     r9, [rbp+57h+cchName]; lpcchName
0x180012565  inc     eax
0x180012567  mov     edx, ecx; dwIndex
0x180012569  mov     rcx, [rbp+57h+hKey]; hKey
0x18001256d  mov     r8, rsi; lpName
0x180012570  mov     [rbp+57h+cchName], eax
0x180012573  xor     eax, eax
0x180012575  mov     [rsp+110h+lpcValues], rax; lpftLastWriteTime
0x18001257a  mov     [rsp+110h+lpcbMaxClassLen], rax; lpcchClass
0x18001257f  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpClass
0x180012584  mov     [rsp+110h+phkResult], rax; lpReserved
0x180012589  call    cs:__imp_RegEnumKeyExW
0x18001258f  mov     edi, eax
0x180012591  test    eax, eax
0x180012593  jnz     loc_180012819
0x180012599  xorps   xmm0, xmm0
0x18001259c  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800125a0  mov     rcx, rsi; StringUuid
0x1800125a3  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800125a7  call    cs:__imp_UuidFromStringW
0x1800125ad  test    eax, eax
0x1800125af  jz      short loc_1800125D0
0x1800125b1  mov     r9d, eax
0x1800125b4  lea     rcx, aSTheRegistryKe_0; "%s: The registry key \"%s\" is not a va"...
0x1800125bb  mov     r8, rsi
0x1800125be  mov     rdx, r14
0x1800125c1  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800125c6  mov     ecx, dword ptr [rbp+57h+var_98]
0x1800125c9  inc     ecx
0x1800125cb  jmp     loc_180012543
0x1800125d0  mov     r9, [r12+8]
0x1800125d5  lea     r8, [rbp+57h+var_90]; struct _GUID
0x1800125d9  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x1800125dd  mov     rdx, rsi; unsigned __int16 *
0x1800125e0  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800125e4  shl     r9, 6
0x1800125e8  add     r9, [r12]; struct STRUCT_NGC_REG_KEY *
0x1800125ec  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800125f1  call    ?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)
0x1800125f6  mov     edi, eax
0x1800125f8  test    eax, eax
0x1800125fa  jnz     short loc_180012603
0x1800125fc  inc     qword ptr [r12+8]
0x180012601  jmp     short loc_1800125C6
0x180012603  mov     dword ptr [rsp+110h+lpcbMaxSubKeyLen], eax
0x180012607  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001260e  mov     r8, r13
0x180012611  mov     [rsp+110h+phkResult], rsi
0x180012616  mov     rdx, r14
0x180012619  lea     rcx, aSFailedToReadR_0; "%s: Failed to read registry key \"%s\\%"...
0x180012620  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180012625  test    edi, edi
0x180012627  jg      loc_18001285B
0x18001262d  mov     ebx, edi
0x18001262f  jmp     loc_180012414
0x180012634  cmp     [rax], si
0x180012637  jz      short loc_180012643
0x180012639  add     rax, 2
0x18001263d  sub     rcx, 1
0x180012641  jnz     short loc_180012634
0x180012643  xor     eax, eax
0x180012645  mov     r13d, 80070057h
0x18001264b  test    rcx, rcx
0x18001264e  cmovnz  r13d, eax
0x180012652  jz      loc_18001276F
0x180012658  mov     rbx, qword ptr [rbp+57h+cchName]
0x18001265c  sub     r10, rcx
0x18001265f  mov     [rbp+57h+var_98], r10
0x180012663  lea     rax, [rbx+1]
0x180012667  add     rax, r10
0x18001266a  mov     qword ptr [rbp+57h+cchName], rax
0x18001266e  lea     rcx, [rax+rax]; unsigned __int64
0x180012672  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180012677  mov     r15, rax
0x18001267a  test    rax, rax
0x18001267d  jz      loc_180012717
0x180012683  xor     eax, eax
0x180012685  test    rbx, rbx
0x180012688  mov     [r15], ax
0x18001268c  mov     rbx, qword ptr [rbp+57h+cchName]
0x180012690  jnz     loc_180012732
0x180012696  cmp     [rbp+57h+var_98], rsi
0x18001269a  jbe     short loc_1800126B5
0x18001269c  mov     r8, rdi; unsigned __int16 *
0x18001269f  mov     rdx, rbx; unsigned __int64
0x1800126a2  mov     rcx, r15; unsigned __int16 *
0x1800126a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800126aa  mov     r13d, eax
0x1800126ad  test    eax, eax
0x1800126af  js      loc_18001275B
0x1800126b5  mov     ebx, r13d
0x1800126b8  test    r13d, r13d
0x1800126bb  jns     loc_180012767
0x1800126c1  mov     r9d, r13d
0x1800126c4  lea     r8, aStringcat; "StringCat"
0x1800126cb  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x1800126d2  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800126d9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800126de  jmp     loc_180012414
0x1800126e3  mov     r10d, 7FFFFFFFh
0x1800126e9  mov     qword ptr [rbp+57h+cchName], r13
0x1800126ed  mov     edx, r10d; unsigned __int64
0x1800126f0  lea     r8, [rbp+57h+cchName]; unsigned __int64 *
0x1800126f4  lea     rcx, aHkeyUsers_0; "HKEY_USERS\\"
0x1800126fb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012700  mov     r13d, eax
0x180012703  test    eax, eax
0x180012705  jns     short loc_18001270C
0x180012707  mov     r9d, eax
0x18001270a  jmp     short loc_180012772
0x18001270c  mov     rcx, r10
0x18001270f  mov     rax, rdi
0x180012712  jmp     loc_180012634
0x180012717  lea     rdx, aStringcat; "StringCat"
0x18001271e  mov     r13d, 8007000Eh
0x180012724  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18001272b  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180012730  jmp     short loc_18001278C
0x180012732  lea     r8, aHkeyUsers_0; "HKEY_USERS\\"
0x180012739  mov     rdx, rbx; unsigned __int64
0x18001273c  mov     rcx, r15; unsigned __int16 *
0x18001273f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012744  mov     r13d, eax
0x180012747  test    eax, eax
0x180012749  jns     loc_180012696
  ... truncated ...
```
