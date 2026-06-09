# OmaDmEnumerateInitiationInfo

- ea: `0x180016c50`
- end: `0x1800170e4`
- name: `OmaDmEnumerateInitiationInfo`
- size: `1172`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fb50`
- `0x180016160`
- `0x18001fa38`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x1800075f0`
- `0x180007930`
- `0x18000c920`
- `0x18000f47c`
- `0x180014514`
- `0x180014570`
- `0x180014698`
- `0x180016c50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017076`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017076`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016eb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016efa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016eb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016efa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017086`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016e5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016e5d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016f58`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016f58`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180016da0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180016f6c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180016da0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180016f6c`
- `DMCmnUtils!BigStrcat` at `0x180016dcf`
- `DMCmnUtils!BigStrcat` at `0x180016fac`
- `DMCmnUtils!BigStrcat` at `0x180016dcf`
- `DMCmnUtils!BigStrcat` at `0x180016fac`
- `DMCmnUtils!CopyString` at `0x180016d59`
- `DMCmnUtils!CopyString` at `0x180016d59`

## pseudocode

```c
__int64 __fastcall OmaDmEnumerateInitiationInfo(unsigned __int16 *a1, int a2, HLOCAL **a3, DWORD *a4)
{
  WCHAR *v8; // r14
  int AccountIDFromLookupID; // edi
  __int64 v10; // rdx
  HLOCAL v11; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v13; // rdx
  HLOCAL *v14; // rsi
  LSTATUS v15; // eax
  unsigned __int64 v16; // rax
  size_t v17; // rbx
  HLOCAL *v18; // rax
  signed int v19; // r15d
  WCHAR *v20; // rcx
  DWORD v21; // eax
  __int64 v22; // r14
  LSTATUS v23; // eax
  HLOCAL v24; // rbx
  char v25; // al
  const wchar_t *v26; // rdx
  unsigned __int16 *v27; // rax
  __int64 i; // r14
  __int64 v29; // rcx
  DWORD cSubKeys; // [rsp+60h] [rbp-49h] BYREF
  WCHAR *v32; // [rsp+68h] [rbp-41h]
  HLOCAL v33; // [rsp+70h] [rbp-39h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-31h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-2Dh] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-29h]
  HKEY phkResult; // [rsp+88h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-19h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-11h] BYREF
  char v40[16]; // [rsp+A0h] [rbp-9h] BYREF
  const wchar_t *v41; // [rsp+B0h] [rbp+7h]
  __int64 v42; // [rsp+B8h] [rbp+Fh]

  hObject = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v8 = 0;
  cchName = 0;
  hMem = 0;
  v33 = 0;
  hKey = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v41 = L"OmaDmEnumerateInitiationInfo";
    v42 = 58;
    McGenEventWrite_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, FunctionEntryPointEvent, a3, 2, v40);
  }
  if ( !a1 || !*a1 || !a3 || !a4 )
    goto LABEL_56;
  AccountIDFromLookupID = AcquireOmaDmMutex(&hObject);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_57;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, OmaDmEnumerateInitiationInfoEvent, a1);
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&v33);
      if ( AccountIDFromLookupID >= 0 )
        goto LABEL_16;
      goto LABEL_15;
    }
LABEL_56:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_57;
  }
  AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID((__int16 *)a1, 0, (unsigned __int16 **)&v33);
LABEL_15:
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_57;
LABEL_16:
  AccountIDFromLookupID = GetAccountRootKey(v33, v10, &hKey);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_57;
  v11 = v33;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v13 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v13 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v32 = BigStrcat(3u, v13, L"\\", v11);
  v8 = v32;
  if ( !v32 )
  {
    AccountIDFromLookupID = -2147024882;
    goto LABEL_57;
  }
  v14 = 0;
  if ( RegOpenKeyExW(hKey, v32, 0, 0x20119u, &phkResult) )
  {
    v21 = cSubKeys;
  }
  else
  {
    v15 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v15 )
    {
      if ( v15 > 0 )
        AccountIDFromLookupID = (unsigned __int16)v15 | 0x80070000;
      else
        AccountIDFromLookupID = v15;
      goto LABEL_57;
    }
    if ( !cSubKeys )
    {
      *a4 = 0;
      *a3 = 0;
      goto LABEL_57;
    }
    v16 = 8LL * cSubKeys;
    if ( v16 > 0xFFFFFFFF )
    {
      AccountIDFromLookupID = -2147024362;
      goto LABEL_57;
    }
    v17 = (unsigned int)v16;
    v18 = (HLOCAL *)LocalAlloc(0, (unsigned int)v16);
    v14 = v18;
    if ( !v18 )
    {
      AccountIDFromLookupID = -2147024882;
      goto LABEL_57;
    }
    memset_0(v18, 0, v17);
    v19 = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      AccountIDFromLookupID = -2147024362;
      goto LABEL_49;
    }
    if ( v19 < 0 )
    {
      AccountIDFromLookupID = -2102788093;
      goto LABEL_49;
    }
    hMem = LocalAlloc(0, (unsigned int)(2 * v19));
    v20 = (WCHAR *)hMem;
    if ( !hMem )
    {
LABEL_34:
      AccountIDFromLookupID = -2147024882;
LABEL_49:
      for ( i = 0; (unsigned int)i < cSubKeys; i = (unsigned int)(i + 1) )
        LocalFree(v14[i]);
      LocalFree(v14);
      v8 = v32;
      goto LABEL_57;
    }
    v21 = cSubKeys;
    AccountIDFromLookupID = 0;
    v22 = 0;
    if ( cSubKeys )
    {
      while ( 1 )
      {
        cchName = v19;
        v23 = RegEnumKeyExW(phkResult, v22, v20, &cchName, 0, 0, 0, 0);
        if ( v23 )
          break;
        v24 = v33;
        v25 = RtlIsStateSeparationEnabled();
        v26 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
        if ( !v25 )
          v26 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
        v27 = BigStrcat(5u, v26, L"\\", v24, L"\\", hMem);
        v14[v22] = v27;
        if ( !v27 )
          goto LABEL_34;
        v21 = cSubKeys;
        v22 = (unsigned int)(v22 + 1);
        if ( (unsigned int)v22 >= cSubKeys )
          goto LABEL_54;
        v20 = (WCHAR *)hMem;
      }
      if ( v23 > 0 )
        AccountIDFromLookupID = (unsigned __int16)v23 | 0x80070000;
      else
        AccountIDFromLookupID = v23;
      goto LABEL_49;
    }
  }
LABEL_54:
  v8 = v32;
  *a4 = v21;
  *a3 = v14;
  if ( !v21 )
    AccountIDFromLookupID = -2147023728;
LABEL_57:
  LocalFree(hMem);
  LocalFree(v8);
  LocalFree(v33);
  RegCloseKey(phkResult);
  ReleaseOmaDmMutex(hObject);
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v29,
      FunctionReturnValueEvent,
      L"OmaDmEnumerateInitiationInfo",
      (unsigned int)AccountIDFromLookupID);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x180016c50  mov     [rsp-8+arg_8], rbx
0x180016c55  push    rbp
0x180016c56  push    rsi
0x180016c57  push    rdi
0x180016c58  push    r12
0x180016c5a  push    r13
0x180016c5c  push    r14
0x180016c5e  push    r15
0x180016c60  lea     rbp, [rsp-27h]
0x180016c65  sub     rsp, 0D0h
0x180016c6c  mov     rax, cs:__security_cookie
0x180016c73  xor     rax, rsp
0x180016c76  mov     [rbp+57h+var_40], rax
0x180016c7a  xor     r15d, r15d
0x180016c7d  lea     rax, aOmadmenumerate_2; "OmaDmEnumerateInitiationInfo"
0x180016c84  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180016c8b  mov     r13, r9
0x180016c8e  mov     r12, r8
0x180016c91  mov     [rbp+57h+hObject], r15
0x180016c95  mov     esi, edx
0x180016c97  mov     [rbp+57h+var_78], r15
0x180016c9b  mov     rbx, rcx
0x180016c9e  mov     [rbp+57h+cSubKeys], r15d
0x180016ca2  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x180016ca6  mov     r14d, r15d
0x180016ca9  mov     [rbp+57h+cchName], r15d
0x180016cad  mov     [rbp+57h+hMem], r15
0x180016cb1  mov     [rbp+57h+var_90], r15
0x180016cb5  mov     [rbp+57h+hKey], r15
0x180016cb9  jz      short loc_180016CE7
0x180016cbb  mov     [rbp+57h+var_50], rax
0x180016cbf  lea     r9d, [r15+2]
0x180016cc3  lea     rax, [rbp+57h+var_60]
0x180016cc7  mov     [rbp+57h+var_48], 3Ah ; ':'
0x180016ccf  lea     rdx, FunctionEntryPointEvent
0x180016cd6  mov     [rsp+100h+phkResult], rax
0x180016cdb  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180016ce2  call    McGenEventWrite_EventWriteTransfer
0x180016ce7  test    rbx, rbx
0x180016cea  jz      loc_18001704E
0x180016cf0  cmp     r15w, [rbx]
0x180016cf4  jz      loc_18001704E
0x180016cfa  test    r12, r12
0x180016cfd  jz      loc_18001704E
0x180016d03  test    r13, r13
0x180016d06  jz      loc_18001704E
0x180016d0c  lea     rcx, [rbp+57h+hObject]; void **
0x180016d10  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x180016d15  mov     edi, eax
0x180016d17  test    eax, eax
0x180016d19  js      loc_180017053
0x180016d1f  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x180016d26  jz      short loc_180016D3E
0x180016d28  mov     r8, rbx
0x180016d2b  lea     rdx, OmaDmEnumerateInitiationInfoEvent
0x180016d32  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180016d39  call    McTemplateU0z_EventWriteTransfer
0x180016d3e  mov     eax, 0FFFFFFFFh
0x180016d43  test    esi, esi
0x180016d45  jz      short loc_180016D6D
0x180016d47  cmp     esi, 1
0x180016d4a  jnz     loc_18001704E
0x180016d50  lea     r8, [rbp+57h+var_90]
0x180016d54  mov     edx, eax
0x180016d56  mov     rcx, rbx
0x180016d59  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180016d60  nop     dword ptr [rax+rax+00h]
0x180016d65  mov     edi, eax
0x180016d67  test    eax, eax
0x180016d69  js      short loc_180016D7D
0x180016d6b  jmp     short loc_180016D85
0x180016d6d  lea     r8, [rbp+57h+var_90]
0x180016d71  xor     edx, edx
0x180016d73  mov     rcx, rbx
0x180016d76  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x180016d7b  mov     edi, eax
0x180016d7d  test    edi, edi
0x180016d7f  js      loc_180017053
0x180016d85  mov     rcx, [rbp+57h+var_90]
0x180016d89  lea     r8, [rbp+57h+hKey]
0x180016d8d  call    GetAccountRootKey
0x180016d92  mov     edi, eax
0x180016d94  test    eax, eax
0x180016d96  js      loc_180017053
0x180016d9c  mov     rbx, [rbp+57h+var_90]
0x180016da0  call    cs:__imp_RtlIsStateSeparationEnabled
0x180016da7  nop     dword ptr [rax+rax+00h]
0x180016dac  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180016db3  mov     r9, rbx
0x180016db6  test    al, al
0x180016db8  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180016dbf  lea     r8, asc_1800273F4; "\\"
0x180016dc6  cmovz   rdx, rcx
0x180016dca  mov     ecx, 3
0x180016dcf  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x180016dd6  nop     dword ptr [rax+rax+00h]
0x180016ddb  mov     [rbp+57h+var_98], rax
0x180016ddf  mov     r14, rax
0x180016de2  test    rax, rax
0x180016de5  jnz     short loc_180016DF1
0x180016de7  mov     edi, 8007000Eh
0x180016dec  jmp     loc_180017053
0x180016df1  mov     rcx, [rbp+57h+hKey]; hKey
0x180016df5  lea     rax, [rbp+57h+var_78]
0x180016df9  mov     r9d, 20119h; samDesired
0x180016dff  mov     [rsp+100h+phkResult], rax; phkResult
0x180016e04  xor     r8d, r8d; ulOptions
0x180016e07  mov     rdx, r14; lpSubKey
0x180016e0a  mov     rsi, r15
0x180016e0d  call    cs:__imp_RegOpenKeyExW
0x180016e14  nop     dword ptr [rax+rax+00h]
0x180016e19  test    eax, eax
0x180016e1b  jnz     loc_180017034
0x180016e21  mov     rcx, [rbp+57h+var_78]; hKey
0x180016e25  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180016e29  mov     [rsp+100h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180016e2e  xor     r9d, r9d; lpReserved
0x180016e31  mov     [rsp+100h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180016e36  xor     r8d, r8d; lpcchClass
0x180016e39  mov     [rsp+100h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180016e3e  xor     edx, edx; lpClass
0x180016e40  mov     [rsp+100h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180016e45  mov     [rsp+100h+lpcValues], r15; lpcValues
0x180016e4a  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016e4f  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180016e54  lea     rax, [rbp+57h+cSubKeys]
0x180016e58  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x180016e5d  call    cs:__imp_RegQueryInfoKeyW
0x180016e64  nop     dword ptr [rax+rax+00h]
0x180016e69  test    eax, eax
0x180016e6b  jz      short loc_180016E84
0x180016e6d  jg      short loc_180016E76
0x180016e6f  mov     edi, eax
0x180016e71  jmp     loc_180017053
0x180016e76  movzx   edi, ax
0x180016e79  or      edi, 80070000h
0x180016e7f  jmp     loc_180017053
0x180016e84  mov     eax, [rbp+57h+cSubKeys]
0x180016e87  test    eax, eax
0x180016e89  jnz     short loc_180016E98
0x180016e8b  mov     [r13+0], r15d
0x180016e8f  mov     [r12], r15
0x180016e93  jmp     loc_180017053
0x180016e98  shl     rax, 3
0x180016e9c  mov     ecx, 0FFFFFFFFh
0x180016ea1  cmp     rax, rcx
0x180016ea4  ja      loc_18001702D
0x180016eaa  mov     edx, eax; uBytes
0x180016eac  xor     ecx, ecx; uFlags
0x180016eae  mov     ebx, eax
0x180016eb0  call    cs:__imp_LocalAlloc
0x180016eb7  nop     dword ptr [rax+rax+00h]
0x180016ebc  mov     rsi, rax
0x180016ebf  test    rax, rax
0x180016ec2  jnz     short loc_180016ECE
0x180016ec4  mov     edi, 8007000Eh
0x180016ec9  jmp     loc_180017053
0x180016ece  mov     r8, rbx; Size
0x180016ed1  xor     edx, edx; Val
0x180016ed3  mov     rcx, rsi; void *
0x180016ed6  call    memset_0
0x180016edb  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180016ede  lea     r15d, [rax+1]
0x180016ee2  cmp     r15d, eax
0x180016ee5  jb      loc_180016FEE
0x180016eeb  test    r15d, r15d
0x180016eee  js      loc_180016FE7
0x180016ef4  lea     edx, [r15+r15]; uBytes
0x180016ef8  xor     ecx, ecx; uFlags
0x180016efa  call    cs:__imp_LocalAlloc
0x180016f01  nop     dword ptr [rax+rax+00h]
0x180016f06  mov     [rbp+57h+hMem], rax
0x180016f0a  mov     rcx, rax
0x180016f0d  test    rax, rax
0x180016f10  jnz     short loc_180016F1C
0x180016f12  mov     edi, 8007000Eh
0x180016f17  jmp     loc_180016FF3
0x180016f1c  mov     eax, [rbp+57h+cSubKeys]
0x180016f1f  xor     edi, edi
0x180016f21  xor     r14d, r14d
0x180016f24  test    eax, eax
0x180016f26  jz      loc_180017037
0x180016f2c  jmp     short loc_180016F32
0x180016f2e  mov     rcx, [rbp+57h+hMem]
0x180016f32  mov     [rsp+100h+lpcValues], rdi; lpftLastWriteTime
0x180016f37  lea     r9, [rbp+57h+cchName]; lpcchName
0x180016f3b  mov     [rsp+100h+lpcbMaxClassLen], rdi; lpcchClass
0x180016f40  mov     r8, rcx; lpName
0x180016f43  mov     rcx, [rbp+57h+var_78]; hKey
0x180016f47  mov     edx, r14d; dwIndex
0x180016f4a  mov     [rsp+100h+lpcbMaxSubKeyLen], rdi; lpClass
0x180016f4f  mov     [rsp+100h+phkResult], rdi; lpReserved
0x180016f54  mov     [rbp+57h+cchName], r15d
0x180016f58  call    cs:__imp_RegEnumKeyExW
0x180016f5f  nop     dword ptr [rax+rax+00h]
0x180016f64  test    eax, eax
0x180016f66  jnz     short loc_180016FD6
0x180016f68  mov     rbx, [rbp+57h+var_90]
0x180016f6c  call    cs:__imp_RtlIsStateSeparationEnabled
0x180016f73  nop     dword ptr [rax+rax+00h]
0x180016f78  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180016f7f  mov     r9, rbx
0x180016f82  test    al, al
0x180016f84  mov     ecx, 5
0x180016f89  lea     rax, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180016f90  cmovz   rdx, rax
0x180016f94  mov     rax, [rbp+57h+hMem]
0x180016f98  mov     [rsp+100h+lpcbMaxSubKeyLen], rax
0x180016f9d  lea     rax, asc_1800273F4; "\\"
0x180016fa4  mov     r8, rax
0x180016fa7  mov     [rsp+100h+phkResult], rax
0x180016fac  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x180016fb3  nop     dword ptr [rax+rax+00h]
0x180016fb8  mov     [rsi+r14*8], rax
0x180016fbc  test    rax, rax
0x180016fbf  jz      loc_180016F12
0x180016fc5  mov     eax, [rbp+57h+cSubKeys]
0x180016fc8  inc     r14d
0x180016fcb  cmp     r14d, eax
0x180016fce  jb      loc_180016F2E
0x180016fd4  jmp     short loc_180017037
0x180016fd6  jg      short loc_180016FDC
0x180016fd8  mov     edi, eax
0x180016fda  jmp     short loc_180016FF3
0x180016fdc  movzx   edi, ax
0x180016fdf  or      edi, 80070000h
0x180016fe5  jmp     short loc_180016FF3
0x180016fe7  mov     edi, 82AA0003h
0x180016fec  jmp     short loc_180016FF3
0x180016fee  mov     edi, 80070216h
0x180016ff3  xor     r14d, r14d
0x180016ff6  mov     rbx, rsi
0x180016ff9  cmp     [rbp+57h+cSubKeys], r14d
0x180016ffd  jbe     short loc_180017018
0x180016fff  mov     rcx, [rbx+r14*8]; hMem
0x180017003  call    cs:__imp_LocalFree
0x18001700a  nop     dword ptr [rax+rax+00h]
0x18001700f  inc     r14d
0x180017012  cmp     r14d, [rbp+57h+cSubKeys]
0x180017016  jb      short loc_180016FFF
0x180017018  mov     rcx, rsi; hMem
0x18001701b  call    cs:__imp_LocalFree
0x180017022  nop     dword ptr [rax+rax+00h]
0x180017027  mov     r14, [rbp+57h+var_98]
0x18001702b  jmp     short loc_180017053
0x18001702d  mov     edi, 80070216h
0x180017032  jmp     short loc_180017053
0x180017034  mov     eax, [rbp+57h+cSubKeys]
0x180017037  mov     r14, [rbp+57h+var_98]
0x18001703b  mov     [r13+0], eax
0x18001703f  mov     [r12], rsi
0x180017043  test    eax, eax
0x180017045  jnz     short loc_180017053
0x180017047  mov     edi, 80070490h
0x18001704c  jmp     short loc_180017053
0x18001704e  mov     edi, 80070057h
0x180017053  mov     rcx, [rbp+57h+hMem]; hMem
0x180017057  call    cs:__imp_LocalFree
0x18001705e  nop     dword ptr [rax+rax+00h]
0x180017063  mov     rcx, r14; hMem
0x180017066  call    cs:__imp_LocalFree
0x18001706d  nop     dword ptr [rax+rax+00h]
0x180017072  mov     rcx, [rbp+57h+var_90]; hMem
0x180017076  call    cs:__imp_LocalFree
0x18001707d  nop     dword ptr [rax+rax+00h]
0x180017082  mov     rcx, [rbp+57h+var_78]; hKey
0x180017086  call    cs:__imp_RegCloseKey
0x18001708d  nop     dword ptr [rax+rax+00h]
0x180017092  mov     rcx, [rbp+57h+hObject]; hObject
0x180017096  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18001709b  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x1800170a2  jz      short loc_1800170BA
0x1800170a4  mov     r9d, edi
0x1800170a7  lea     r8, aOmadmenumerate_2; "OmaDmEnumerateInitiationInfo"
0x1800170ae  lea     rdx, FunctionReturnValueEvent
0x1800170b5  call    McTemplateU0zq_EventWriteTransfer
0x1800170ba  mov     eax, edi
0x1800170bc  mov     rcx, [rbp+57h+var_40]
0x1800170c0  xor     rcx, rsp; StackCookie
0x1800170c3  call    __security_check_cookie
0x1800170c8  mov     rbx, [rsp+100h+arg_8]
0x1800170d0  add     rsp, 0D0h
0x1800170d7  pop     r15
0x1800170d9  pop     r14
0x1800170db  pop     r13
0x1800170dd  pop     r12
0x1800170df  pop     rdi
0x1800170e0  pop     rsi
0x1800170e1  pop     rbp
0x1800170e2  retn
```
