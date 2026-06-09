# CDimInterfaceTable::RegLoadInterfaces(ushort *,_GUID *,ulong,_DIM_COMPARTMENT_INTERFACE *)

- ea: `0x180001610`
- end: `0x180001d09`
- name: `?RegLoadInterfaces@CDimInterfaceTable@@QEAAKPEAGPEAU_GUID@@KPEAU_DIM_COMPARTMENT_INTERFACE@@@Z`
- size: `1785`
- prototype: `unsigned int __fastcall(CDimInterfaceTable *__hidden this, unsigned __int16 *, struct _GUID *, unsigned int, struct _DIM_COMPARTMENT_INTERFACE *)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005134`
- `0x180011eb0`
- `0x180013b80`
- `0x180014244`
- `0x180015490`

## callees

- `0x180001610`
- `0x180002598`
- `0x1800091dc`
- `0x18000def0`
- `0x18000df70`
- `0x180024214`
- `0x180026d54`
- `0x180036924`
- `0x180045d40`
- `0x180046e06`
- `0x180046e2a`
- `0x180046e70`
- `0x180046f00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000192e`
- `msvcrt!_wcsicmp` at `0x18000192e`
- `rtutils!RouterLogEventW` at `0x1800017a1`
- `rtutils!RouterLogEventW` at `0x1800017a1`
- `rtutils!RouterLogEventStringW` at `0x180001c06`
- `rtutils!RouterLogEventStringW` at `0x180001c06`
- `ADVAPI32!RegOpenKeyExW` at `0x1800018a3`
- `ADVAPI32!RegOpenKeyExW` at `0x180001977`
- `ADVAPI32!RegOpenKeyExW` at `0x1800018a3`
- `ADVAPI32!RegOpenKeyExW` at `0x180001977`
- `ADVAPI32!RegCloseKey` at `0x180001801`
- `ADVAPI32!RegCloseKey` at `0x180001909`
- `ADVAPI32!RegCloseKey` at `0x180001941`
- `ADVAPI32!RegCloseKey` at `0x180001c11`
- `ADVAPI32!RegCloseKey` at `0x180001c2d`
- `ADVAPI32!RegCloseKey` at `0x180001cd8`
- `ADVAPI32!RegCloseKey` at `0x180001801`
- `ADVAPI32!RegCloseKey` at `0x180001909`
- `ADVAPI32!RegCloseKey` at `0x180001941`
- `ADVAPI32!RegCloseKey` at `0x180001c11`
- `ADVAPI32!RegCloseKey` at `0x180001c2d`
- `ADVAPI32!RegCloseKey` at `0x180001cd8`
- `ADVAPI32!RegQueryValueExW` at `0x1800018d5`
- `ADVAPI32!RegQueryValueExW` at `0x1800018d5`
- `ADVAPI32!RegEnumKeyExW` at `0x18000187a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000187a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800019ce`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800019ce`

## string_xrefs

- `0x180001721`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x1800017be`: `Cannot access the Registry key %s.`
- `0x180001a6b`: `RegLoadInterfaces: Error reading routing domain from registry`

## pseudocode

```c
__int64 __fastcall CDimInterfaceTable::RegLoadInterfaces(
        CDimInterfaceTable *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int a4,
        struct _DIM_COMPARTMENT_INTERFACE *a5)
{
  DWORD v8; // esi
  __int64 v10; // rax
  LPWSTR v12; // rdi
  __int64 v13; // rax
  LSTATUS dwErrorCode; // ebx
  HKEY v15; // rdi
  LSTATUS v16; // ebx
  LSTATUS v17; // eax
  HKEY v18; // rax
  CDimInterfaceTable *v19; // rcx
  CDimInterfaceTable *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  DWORD v23; // ebx
  __int128 *v24; // r9
  unsigned int v25; // eax
  bool v26; // [rsp+60h] [rbp-A0h] BYREF
  bool v27; // [rsp+61h] [rbp-9Fh] BYREF
  bool v28; // [rsp+62h] [rbp-9Eh] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cSubKeys; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-7Ch] BYREF
  LPWSTR plpszSubStringArray; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR v36; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v37; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID Buf1; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h] BYREF
  int v40; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v41; // [rsp+CCh] [rbp-34h]
  __int128 v42; // [rsp+DCh] [rbp-24h]
  int v43; // [rsp+ECh] [rbp-14h]
  wchar_t Data[256]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v45; // [rsp+2F0h] [rbp+1F0h]
  WCHAR Name[2]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v47[2044]; // [rsp+304h] [rbp+204h] BYREF
  int v48; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v49[2044]; // [rsp+B04h] [rbp+A04h] BYREF

  *(_QWORD *)&v37.Data1 = a5;
  v8 = 0;
  phkResult = 0;
  v36 = 0;
  memset_0(Data, 0, 0x202u);
  v26 = 0;
  v28 = 0;
  v48 = 0;
  v39 = 0;
  memset_0(v49, 0, sizeof(v49));
  v40 = 0;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  if ( a3 && !*((_BYTE *)this + 116) )
  {
    v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v10 )
      return 87;
  }
  Type = 0;
  cchName = 0;
  cbData = 0;
  hKey = 0;
  cSubKeys = 0;
  *(_DWORD *)Name = 0;
  memset_0(v47, 0, sizeof(v47));
  v12 = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
  if ( !*((_BYTE *)this + 116) || !a3 )
    goto LABEL_33;
  v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v13 )
  {
    dwErrorCode = OpenInterfacesKey(a3, &hKey);
    if ( dwErrorCode )
      goto LABEL_13;
  }
  else
  {
LABEL_33:
    dwErrorCode = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces",
                    0,
                    0x20019u,
                    &hKey);
    if ( dwErrorCode )
      goto LABEL_13;
  }
  v17 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cchName, &Type, &cbData, 0, 0);
  ++Type;
  dwErrorCode = v17;
  if ( !v17 )
  {
    v15 = hKey;
    goto LABEL_21;
  }
LABEL_13:
  plpszSubStringArray = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
  if ( dword_180070F40 )
  {
    RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &plpszSubStringArray, dwErrorCode);
    v12 = plpszSubStringArray;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
  {
    Name[0] = 0;
    FormatRRASErrorString(Name, L"Cannot access the Registry key %s.", v12);
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, Name);
  }
  v15 = hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    v15 = 0;
    hKey = 0;
  }
  cSubKeys = 0;
  if ( dwErrorCode )
    goto LABEL_76;
LABEL_21:
  while ( v8 < cSubKeys )
  {
    memset_0(Name, 0, 0x202u);
    cchName = 257;
    Type = 0;
    cbData = 514;
    phkResult = 0;
    if ( RegEnumKeyExW(v15, v8, Name, &cchName, 0, 0, 0, 0) || RegOpenKeyExW(v15, Name, 0, 0x20019u, &phkResult) )
      goto LABEL_27;
    v16 = RegQueryValueExW(phkResult, L"InterfaceName", 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v16 && Type != 1 )
    {
      v45 = 0;
LABEL_27:
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      goto LABEL_67;
    }
    v45 = 0;
    if ( v16 )
      goto LABEL_27;
    v18 = phkResult;
    if ( a2 )
    {
      if ( !_wcsicmp(a2, Data) )
      {
        v18 = phkResult;
        goto LABEL_39;
      }
      RegCloseKey(phkResult);
      v15 = hKey;
      phkResult = 0;
      ++v8;
    }
    else
    {
LABEL_39:
      if ( a3 )
      {
        v19 = (CDimInterfaceTable *)(*(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1);
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
          v19 = (CDimInterfaceTable *)(*(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4);
        if ( v19 )
        {
          v27 = 0;
          Buf1 = 0;
          if ( CDimInterfaceTable::RegGetRoutingDomainId(v19, v18, &Buf1) )
          {
            LOBYTE(cchName) = Microsoft_Windows_RRASEnableBits & 4;
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              LOWORD(v40) = 0;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)L"RegLoadInterfaces: Error reading routing domain from registry",
                (_DWORD)a3,
                (__int64)Data,
                (__int64)&v40);
            }
          }
          if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
            goto LABEL_52;
          v21 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
            v21 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
          if ( v21 )
          {
LABEL_52:
            v22 = *(_QWORD *)&Buf1.Data1 - *(_QWORD *)&a3->Data1;
            if ( *(_QWORD *)&Buf1.Data1 == *(_QWORD *)&a3->Data1 )
              v22 = *(_QWORD *)Buf1.Data4 - *(_QWORD *)a3->Data4;
            if ( v22 )
              goto LABEL_66;
          }
          CDimInterfaceTable::DoStackInterfaceListLookup(
            v20,
            phkResult,
            a4,
            *(struct _DIM_COMPARTMENT_INTERFACE **)&v37.Data1,
            &v27);
          if ( !v27 )
          {
LABEL_66:
            RegCloseKey(phkResult);
            phkResult = 0;
            goto LABEL_67;
          }
          v18 = phkResult;
        }
      }
      v26 = 0;
      v28 = 0;
      v23 = CDimInterfaceTable::RegLoadInterface(this, Data, v18, a3, &v26, &v28);
      if ( v23 && !v26 )
      {
        v36 = Data;
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v48) = 0;
          LOWORD(v40) = 0;
          FormatRRASErrorString(&v48, L"Error %d occured while loading interface name %s.", v23, Data);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            v24 = &v39;
            if ( a3 )
              LODWORD(v24) = (_DWORD)a3;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)&v48,
              (_DWORD)v24,
              (__int64)Data,
              (__int64)&v40);
          }
        }
        if ( dword_180070F40 )
          RouterLogEventStringW(hLogHandle, 1u, 0x4E89u, 1u, &v36, v23, 1u);
      }
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( a2 )
        goto LABEL_75;
LABEL_67:
      v15 = hKey;
      ++v8;
    }
  }
  if ( a2 )
    goto LABEL_76;
  v37 = GUID_NULL;
  if ( *((_BYTE *)this + 116) )
    v37 = *a3;
  v25 = CDimInterfaceTable::PlumbIkev2PskPolicy(this, &v37, 0);
  if ( v25 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v48) = 0;
      FormatRRASErrorString(&v48, L"RegLoadInterfaces: PlumbIkev2PskPolicy failed with error %d", v25);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v48);
    }
  }
LABEL_75:
  v15 = hKey;
LABEL_76:
  if ( v15 )
    RegCloseKey(v15);
  return 0;
}

```

## disassembly

```asm
0x180001610  push    rbp
0x180001612  push    rsi
0x180001613  push    r12
0x180001615  push    r13
0x180001617  push    r14
0x180001619  push    r15
0x18000161b  lea     rbp, [rsp-1218h]
0x180001623  mov     eax, 1318h
0x180001628  call    _alloca_probe
0x18000162d  sub     rsp, rax
0x180001630  mov     rax, cs:__security_cookie
0x180001637  xor     rax, rsp
0x18000163a  mov     [rbp+1240h+var_40], rax
0x180001641  mov     rax, [rbp+1240h+arg_20]
0x180001648  mov     r15, r8
0x18000164b  mov     r14, rdx
0x18000164e  mov     qword ptr [rbp+1240h+var_12A8.Data1], rax
0x180001652  mov     r12, rcx
0x180001655  xor     esi, esi
0x180001657  xor     edx, edx; Val
0x180001659  mov     [rsp+1340h+phkResult], rsi
0x18000165e  mov     r8d, 202h; Size
0x180001664  mov     [rbp+1240h+var_12B0], rsi
0x180001668  lea     rcx, [rbp+1240h+Data]; void *
0x18000166c  mov     r13d, r9d
0x18000166f  call    memset_0
0x180001674  xorps   xmm0, xmm0
0x180001677  mov     [rsp+1340h+var_12E0], sil
0x18000167c  xor     edx, edx; Val
0x18000167e  mov     [rsp+1340h+var_12DE], sil
0x180001683  mov     r8d, 7FCh; Size
0x180001689  mov     [rbp+1240h+var_840], esi
0x18000168f  lea     rcx, [rbp+1240h+var_83C]; void *
0x180001696  movups  [rbp+1240h+var_1288], xmm0
0x18000169a  call    memset_0
0x18000169f  xor     eax, eax
0x1800016a1  mov     [rbp+1240h+var_1278], esi
0x1800016a4  mov     [rbp+1240h+var_1254], eax
0x1800016a7  xorps   xmm0, xmm0
0x1800016aa  movups  [rbp+1240h+var_1274], xmm0
0x1800016ae  movups  [rbp+1240h+var_1264], xmm0
0x1800016b2  test    r15, r15
0x1800016b5  jz      short loc_1800016E4
0x1800016b7  cmp     [r12+74h], al
0x1800016bc  jnz     short loc_1800016E4
0x1800016be  mov     rax, [r15]
0x1800016c1  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800016c8  jnz     short loc_1800016D5
0x1800016ca  mov     rax, [r15+8]
0x1800016ce  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800016d5  test    rax, rax
0x1800016d8  jz      short loc_1800016E4
0x1800016da  mov     eax, 57h ; 'W'
0x1800016df  jmp     loc_180001CE8
0x1800016e4  mov     [rsp+1340h+arg_18], rbx
0x1800016ec  lea     rcx, [rbp+1240h+var_103C]; void *
0x1800016f3  xor     edx, edx; Val
0x1800016f5  mov     [rsp+1340h+var_30], rdi
0x1800016fd  mov     r8d, 7FCh; Size
0x180001703  mov     [rsp+1340h+Type], esi
0x180001707  mov     [rsp+1340h+cchName], esi
0x18000170b  mov     [rbp+1240h+cbData], esi
0x18000170e  mov     [rsp+1340h+hKey], rsi
0x180001713  mov     [rbp+1240h+cSubKeys], esi
0x180001716  mov     dword ptr [rbp+1240h+Name], esi
0x18000171c  call    memset_0
0x180001721  lea     rdi, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x180001728  cmp     [r12+74h], sil
0x18000172d  jz      loc_18000195A
0x180001733  test    r15, r15
0x180001736  jz      loc_18000195A
0x18000173c  mov     rax, [r15]
0x18000173f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180001746  jnz     short loc_180001753
0x180001748  mov     rax, [r15+8]
0x18000174c  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180001753  test    rax, rax
0x180001756  jz      loc_18000195A
0x18000175c  lea     rdx, [rsp+1340h+hKey]; HKEY *
0x180001761  mov     rcx, r15; struct _GUID *
0x180001764  call    OpenInterfacesKey
0x180001769  mov     ebx, eax
0x18000176b  test    eax, eax
0x18000176d  jz      loc_180001987
0x180001773  cmp     cs:dword_180070F40, esi
0x180001779  mov     [rbp+1240h+var_12B8], rdi
0x18000177d  jbe     short loc_1800017AB
0x18000177f  mov     rcx, cs:hLogHandle; hLogHandle
0x180001786  lea     rax, [rbp+1240h+var_12B8]
0x18000178a  mov     edx, 1; dwEventType
0x18000178f  mov     [rsp+1340h+dwErrorCode], ebx; dwErrorCode
0x180001793  mov     r9d, edx; dwSubStringCount
0x180001796  mov     [rsp+1340h+plpszSubStringArray], rax; plpszSubStringArray
0x18000179b  mov     r8d, 4E84h; dwMessageId
0x1800017a1  call    cs:__imp_RouterLogEventW
0x1800017a7  mov     rdi, [rbp+1240h+var_12B8]
0x1800017ab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800017b2  jz      short loc_1800017F4
0x1800017b4  mov     r8, rdi
0x1800017b7  mov     [rbp+1240h+Name], si
0x1800017be  lea     rdx, aCannotAccessTh_1; "Cannot access the Registry key %s."
0x1800017c5  lea     rcx, [rbp+1240h+Name]
0x1800017cc  call    FormatRRASErrorString
0x1800017d1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800017d8  jz      short loc_1800017F4
0x1800017da  lea     r8, [rbp+1240h+Name]
0x1800017e1  lea     rdx, RasDimTraceAdminError
0x1800017e8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800017ef  call    McTemplateU0z_EventWriteTransfer
0x1800017f4  mov     rdi, [rsp+1340h+hKey]
0x1800017f9  test    rdi, rdi
0x1800017fc  jz      short loc_18000180F
0x1800017fe  mov     rcx, rdi; hKey
0x180001801  call    cs:__imp_RegCloseKey
0x180001807  mov     rdi, rsi
0x18000180a  mov     [rsp+1340h+hKey], rsi
0x18000180f  mov     [rbp+1240h+cSubKeys], esi
0x180001812  test    ebx, ebx
0x180001814  jnz     loc_180001CC8
0x18000181a  xor     ebx, ebx
0x18000181c  nop     dword ptr [rax+00h]
0x180001820  cmp     esi, [rbp+1240h+cSubKeys]
0x180001823  jnb     loc_180001C48
0x180001829  xor     edx, edx; Val
0x18000182b  lea     rcx, [rbp+1240h+Name]; void *
0x180001832  mov     r8d, 202h; Size
0x180001838  call    memset_0
0x18000183d  mov     [rsp+1340h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180001842  lea     r9, [rsp+1340h+cchName]; lpcchName
0x180001847  mov     [rsp+1340h+lpcchClass], rbx; lpcchClass
0x18000184c  lea     r8, [rbp+1240h+Name]; lpName
0x180001853  mov     qword ptr [rsp+1340h+dwErrorCode], rbx; lpClass
0x180001858  mov     edx, esi; dwIndex
0x18000185a  mov     rcx, rdi; hKey
0x18000185d  mov     [rsp+1340h+plpszSubStringArray], rbx; lpReserved
0x180001862  mov     [rsp+1340h+cchName], 101h
0x18000186a  mov     [rsp+1340h+Type], ebx
0x18000186e  mov     [rbp+1240h+cbData], 202h
0x180001875  mov     [rsp+1340h+phkResult], rbx
0x18000187a  call    cs:__imp_RegEnumKeyExW
0x180001880  mov     ebx, eax
0x180001882  test    eax, eax
0x180001884  jnz     short loc_1800018FC
0x180001886  lea     rax, [rsp+1340h+phkResult]
0x18000188b  mov     r9d, 20019h; samDesired
0x180001891  xor     r8d, r8d; ulOptions
0x180001894  mov     [rsp+1340h+plpszSubStringArray], rax; phkResult
0x180001899  lea     rdx, [rbp+1240h+Name]; lpSubKey
0x1800018a0  mov     rcx, rdi; hKey
0x1800018a3  call    cs:__imp_RegOpenKeyExW
0x1800018a9  mov     ebx, eax
0x1800018ab  test    eax, eax
0x1800018ad  jnz     short loc_1800018FC
0x1800018af  mov     rcx, [rsp+1340h+phkResult]; hKey
0x1800018b4  lea     rax, [rbp+1240h+cbData]
0x1800018b8  mov     qword ptr [rsp+1340h+dwErrorCode], rax; lpcbData
0x1800018bd  lea     r9, [rsp+1340h+Type]; lpType
0x1800018c2  lea     rax, [rbp+1240h+Data]
0x1800018c6  xor     r8d, r8d; lpReserved
0x1800018c9  lea     rdx, ValueName; "InterfaceName"
0x1800018d0  mov     [rsp+1340h+plpszSubStringArray], rax; lpData
0x1800018d5  call    cs:__imp_RegQueryValueExW
0x1800018db  mov     ebx, eax
0x1800018dd  test    eax, eax
0x1800018df  jnz     loc_1800019EC
0x1800018e5  cmp     [rsp+1340h+Type], 1
0x1800018ea  jz      loc_1800019EC
0x1800018f0  mov     ebx, 3F7h
0x1800018f5  mov     [rbp+1240h+var_1050], ax
0x1800018fc  mov     rax, [rsp+1340h+phkResult]
0x180001901  test    rax, rax
0x180001904  jz      short loc_180001916
0x180001906  mov     rcx, rax; hKey
0x180001909  call    cs:__imp_RegCloseKey
0x18000190f  xor     eax, eax
0x180001911  mov     [rsp+1340h+phkResult], rax
0x180001916  test    ebx, ebx
0x180001918  jnz     loc_180001C3A
0x18000191e  test    r14, r14
0x180001921  jz      loc_180001A0C
0x180001927  lea     rdx, [rbp+1240h+Data]; String2
0x18000192b  mov     rcx, r14; String1
0x18000192e  call    cs:__imp__wcsicmp
0x180001934  test    eax, eax
0x180001936  jz      loc_180001A07
0x18000193c  mov     rcx, [rsp+1340h+phkResult]; hKey
0x180001941  call    cs:__imp_RegCloseKey
0x180001947  mov     rdi, [rsp+1340h+hKey]
0x18000194c  xor     ebx, ebx
0x18000194e  mov     [rsp+1340h+phkResult], rbx
0x180001953  inc     esi
0x180001955  jmp     loc_180001820
0x18000195a  lea     rax, [rsp+1340h+hKey]
0x18000195f  mov     r9d, 20019h; samDesired
0x180001965  xor     r8d, r8d; ulOptions
0x180001968  mov     [rsp+1340h+plpszSubStringArray], rax; phkResult
0x18000196d  mov     rdx, rdi; lpSubKey
0x180001970  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001977  call    cs:__imp_RegOpenKeyExW
0x18000197d  mov     ebx, eax
0x18000197f  test    eax, eax
0x180001981  jnz     loc_180001773
0x180001987  mov     rcx, [rsp+1340h+hKey]; hKey
0x18000198c  lea     rax, [rbp+1240h+cbData]
0x180001990  mov     [rsp+1340h+var_12E8], rsi; lpftLastWriteTime
0x180001995  xor     r9d, r9d; lpReserved
0x180001998  mov     [rsp+1340h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000199d  xor     r8d, r8d; lpcchClass
0x1800019a0  mov     [rsp+1340h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800019a5  xor     edx, edx; lpClass
0x1800019a7  lea     rax, [rsp+1340h+Type]
0x1800019ac  mov     [rsp+1340h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800019b1  lea     rax, [rsp+1340h+cchName]
0x1800019b6  mov     [rsp+1340h+lpftLastWriteTime], rax; lpcValues
0x1800019bb  lea     rax, [rbp+1240h+cSubKeys]
0x1800019bf  mov     [rsp+1340h+lpcchClass], rsi; lpcbMaxClassLen
0x1800019c4  mov     qword ptr [rsp+1340h+dwErrorCode], rsi; lpcbMaxSubKeyLen
0x1800019c9  mov     [rsp+1340h+plpszSubStringArray], rax; lpcSubKeys
0x1800019ce  call    cs:__imp_RegQueryInfoKeyW
0x1800019d4  inc     [rsp+1340h+Type]
0x1800019d8  mov     ebx, eax
0x1800019da  test    eax, eax
0x1800019dc  jnz     loc_180001773
0x1800019e2  mov     rdi, [rsp+1340h+hKey]
0x1800019e7  jmp     loc_18000181A
0x1800019ec  xor     eax, eax
0x1800019ee  mov     [rbp+1240h+var_1050], ax
0x1800019f5  test    ebx, ebx
0x1800019f7  jnz     loc_1800018FC
0x1800019fd  mov     rax, [rsp+1340h+phkResult]
0x180001a02  jmp     loc_18000191E
0x180001a07  mov     rax, [rsp+1340h+phkResult]
0x180001a0c  test    r15, r15
0x180001a0f  jz      loc_180001B14
0x180001a15  mov     rcx, [r15]
0x180001a18  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x180001a1f  jnz     short loc_180001A2C
0x180001a21  mov     rcx, [r15+8]
0x180001a25  sub     rcx, qword ptr cs:GUID_NULL.Data4; this
0x180001a2c  test    rcx, rcx
0x180001a2f  jz      loc_180001B14
0x180001a35  xorps   xmm0, xmm0
0x180001a38  mov     [rsp+1340h+var_12DF], 0
0x180001a3d  lea     r8, [rbp+1240h+Buf1]; struct _GUID *
0x180001a41  mov     rdx, rax; HKEY
0x180001a44  movups  [rbp+1240h+Buf1], xmm0
0x180001a48  call    ?RegGetRoutingDomainId@CDimInterfaceTable@@AEAAKPEAUHKEY__@@AEAU_GUID@@@Z; CDimInterfaceTable::RegGetRoutingDomainId(HKEY__ *,_GUID &)
0x180001a4d  test    eax, eax
0x180001a4f  jz      short loc_180001A97
0x180001a51  movzx   eax, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180001a58  and     al, 4
0x180001a5a  mov     byte ptr [rsp+1340h+cchName], al
0x180001a5e  jz      short loc_180001A97
0x180001a60  lea     rax, [rbp+1240h+var_1278]
0x180001a64  xor     ebx, ebx
0x180001a66  mov     qword ptr [rsp+1340h+dwErrorCode], rax
0x180001a6b  lea     r8, aRegloadinterfa; "RegLoadInterfaces: Error reading routin"...
0x180001a72  lea     rax, [rbp+1240h+Data]
0x180001a76  mov     word ptr [rbp+1240h+var_1278], bx
0x180001a7a  mov     r9, r15
0x180001a7d  mov     [rsp+1340h+plpszSubStringArray], rax
0x180001a82  lea     rdx, RasDimParamTraceError
0x180001a89  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001a90  call    McTemplateU0zjzz_EventWriteTransfer
0x180001a95  jmp     short loc_180001A99
0x180001a97  xor     ebx, ebx
0x180001a99  mov     r8d, 10h; Size
0x180001a9f  lea     rdx, GUID_NULL; Buf2
0x180001aa6  lea     rcx, [rbp+1240h+Buf1]; Buf1
0x180001aaa  call    memcmp_0
0x180001aaf  test    eax, eax
0x180001ab1  jnz     short loc_180001ACF
0x180001ab3  mov     rax, [r15]
0x180001ab6  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180001abd  jnz     short loc_180001ACA
0x180001abf  mov     rax, [r15+8]
0x180001ac3  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180001aca  test    rax, rax
0x180001acd  jz      short loc_180001AE9
0x180001acf  mov     rax, qword ptr [rbp+1240h+Buf1]
0x180001ad3  sub     rax, [r15]
0x180001ad6  jnz     short loc_180001AE0
0x180001ad8  mov     rax, qword ptr [rbp+1240h+Buf1+8]
0x180001adc  sub     rax, [r15+8]
0x180001ae0  test    rax, rax
0x180001ae3  jnz     loc_180001C28
0x180001ae9  mov     r9, qword ptr [rbp+1240h+var_12A8.Data1]; struct _DIM_COMPARTMENT_INTERFACE *
0x180001aed  lea     rax, [rsp+1340h+var_12DF]
0x180001af2  mov     rdx, [rsp+1340h+phkResult]; HKEY
0x180001af7  mov     r8d, r13d; unsigned int
0x180001afa  mov     [rsp+1340h+plpszSubStringArray], rax; bool *
0x180001aff  call    ?DoStackInterfaceListLookup@CDimInterfaceTable@@AEAAKPEAUHKEY__@@KPEAU_DIM_COMPARTMENT_INTERFACE@@AEA_N@Z; CDimInterfaceTable::DoStackInterfaceListLookup(HKEY__ *,ulong,_DIM_COMPARTMENT_INTERFACE *,bool &)
0x180001b04  cmp     [rsp+1340h+var_12DF], 0
0x180001b09  jz      loc_180001C28
0x180001b0f  mov     rax, [rsp+1340h+phkResult]
0x180001b14  lea     rcx, [rsp+1340h+var_12DE]
0x180001b19  mov     [rsp+1340h+var_12E0], 0
0x180001b1e  mov     qword ptr [rsp+1340h+dwErrorCode], rcx; bool *
0x180001b23  lea     rdx, [rbp+1240h+Data]; unsigned __int16 *
0x180001b27  lea     rcx, [rsp+1340h+var_12E0]
  ... truncated ...
```
