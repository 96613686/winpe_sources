# EEDBManager::GetEnrollmentEntDmId(_GUID,ushort * *)

- ea: `0x18001e4c4`
- end: `0x18001e767`
- name: `?GetEnrollmentEntDmId@EEDBManager@@SAJU_GUID@@PEAPEAG@Z`
- size: `675`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180012e60`
- `0x1800141d0`
- `0x180040820`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18000de50`
- `0x18001e4c4`
- `0x18001e770`
- `0x18002e1a0`
- `0x18002ec8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e64b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e64b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e65c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e65c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e5c8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e5c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e57b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e57b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e627`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e6ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e627`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e6ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e53e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e683`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e738`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e53e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e683`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e738`

## pseudocode

```c
__int64 __fastcall EEDBManager::GetEnrollmentEntDmId(struct _GUID *a1, unsigned __int16 **a2)
{
  LSTATUS v4; // eax
  HKEY v5; // rcx
  signed int v6; // ebx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  LSTATUS ValueW; // eax
  DWORD v11; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // rbx
  LSTATUS v14; // eax
  signed int v15; // edi
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName[3]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v21; // [rsp+70h] [rbp-90h]
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  *(struct _GUID *)phkResult = *a1;
  v4 = EEDBManager::OpenEnrollmentKey((struct _GUID *)phkResult, 131097, 0, &hKey);
  v5 = hKey;
  v6 = v4;
  if ( v4 < 0 )
  {
LABEL_2:
    if ( v5 )
      RegCloseKey(v5);
    return (unsigned int)v6;
  }
  hkey = 0;
  phkResult[0] = (HKEY)&hkey;
  phkResult[1] = 0;
  v21 = 1;
  RegOpenKeyExW(hKey, L"DMClient", 0, 0x20019u, &phkResult[1]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
  memset_0(Name, 0, 0x208u);
  cchName[0] = 260;
  v8 = RegEnumKeyExW(hkey, 0, Name, cchName, 0, 0, 0, 0);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  v9 = hkey;
  if ( v6 < 0 )
  {
LABEL_8:
    if ( v9 )
      RegCloseKey(v9);
    v5 = hKey;
    goto LABEL_2;
  }
  pcbData = 0;
  ValueW = RegGetValueW(hkey, Name, L"EntDMID", 2u, 0, 0, &pcbData);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( v6 < 0 )
  {
    v9 = hkey;
    goto LABEL_8;
  }
  v11 = pcbData;
  ProcessHeap = GetProcessHeap();
  phkResult[0] = (HKEY)HeapAlloc(ProcessHeap, 8u, v11);
  v13 = (unsigned __int16 *)phkResult[0];
  if ( phkResult[0] )
  {
    v14 = RegGetValueW(hkey, Name, L"EntDMID", 2u, 0, phkResult[0], &pcbData);
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v15 >= 0 )
    {
      phkResult[0] = 0;
      *a2 = v13;
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)phkResult);
      if ( hkey )
        RegCloseKey(hkey);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    else
    {
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)phkResult);
      if ( hkey )
        RegCloseKey(hkey);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v15;
    }
  }
  else
  {
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)phkResult);
    if ( hkey )
      RegCloseKey(hkey);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001e4c4  mov     [rsp-8+arg_10], rbx
0x18001e4c9  mov     [rsp-8+arg_18], rsi
0x18001e4ce  push    rbp
0x18001e4cf  push    rdi
0x18001e4d0  push    r14
0x18001e4d2  lea     rbp, [rsp-1A0h]
0x18001e4da  sub     rsp, 2A0h
0x18001e4e1  mov     rax, cs:__security_cookie
0x18001e4e8  xor     rax, rsp
0x18001e4eb  mov     [rbp+1B0h+var_20], rax
0x18001e4f2  mov     rsi, rdx
0x18001e4f5  mov     rbx, rcx
0x18001e4f8  xor     r14d, r14d
0x18001e4fb  lea     rcx, [rsp+2B0h+hKey]
0x18001e500  xor     edx, edx
0x18001e502  mov     [rsp+2B0h+hKey], r14
0x18001e507  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001e50c  movaps  xmm0, xmmword ptr [rbx]
0x18001e50f  lea     r9, [rsp+2B0h+hKey]; HKEY *
0x18001e514  mov     edi, 20019h
0x18001e519  movdqa  xmmword ptr [rsp+2B0h+var_250], xmm0
0x18001e51f  mov     edx, edi; unsigned int
0x18001e521  lea     rcx, [rsp+2B0h+var_250]; struct _GUID
0x18001e526  xor     r8d, r8d; unsigned __int16 *
0x18001e529  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18001e52e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001e533  mov     ebx, eax
0x18001e535  test    eax, eax
0x18001e537  jns     short loc_18001E54B
0x18001e539  test    rcx, rcx
0x18001e53c  jz      short loc_18001E544
0x18001e53e  call    cs:__imp_RegCloseKey
0x18001e544  mov     eax, ebx
0x18001e546  jmp     loc_18001E740
0x18001e54b  lea     rax, [rsp+2B0h+hkey]
0x18001e550  mov     [rsp+2B0h+hkey], r14
0x18001e555  mov     [rsp+2B0h+var_250], rax
0x18001e55a  lea     rdx, aDmclient; "DMClient"
0x18001e561  lea     rax, [rsp+2B0h+var_250+8]
0x18001e566  mov     [rsp+2B0h+var_250+8], r14
0x18001e56b  mov     r9d, edi; samDesired
0x18001e56e  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001e573  xor     r8d, r8d; ulOptions
0x18001e576  mov     [rsp+2B0h+var_240], 1
0x18001e57b  call    cs:__imp_RegOpenKeyExW
0x18001e581  lea     rcx, [rsp+2B0h+var_250]
0x18001e586  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001e58b  xor     edx, edx; Val
0x18001e58d  lea     rcx, [rbp+1B0h+Name]; void *
0x18001e591  mov     r8d, 208h; Size
0x18001e597  call    memset_0
0x18001e59c  mov     rcx, [rsp+2B0h+hkey]; hKey
0x18001e5a1  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18001e5a6  mov     [rsp+2B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001e5ab  lea     r8, [rbp+1B0h+Name]; lpName
0x18001e5af  mov     [rsp+2B0h+lpcchClass], r14; lpcchClass
0x18001e5b4  xor     edx, edx; dwIndex
0x18001e5b6  mov     [rsp+2B0h+lpClass], r14; lpClass
0x18001e5bb  mov     [rsp+2B0h+phkResult], r14; lpReserved
0x18001e5c0  mov     [rsp+2B0h+cchName], 104h
0x18001e5c8  call    cs:__imp_RegEnumKeyExW
0x18001e5ce  mov     ebx, eax
0x18001e5d0  test    eax, eax
0x18001e5d2  jle     short loc_18001E5DD
0x18001e5d4  movzx   ebx, ax
0x18001e5d7  or      ebx, 80070000h
0x18001e5dd  mov     rcx, [rsp+2B0h+hkey]; hkey
0x18001e5e2  test    ebx, ebx
0x18001e5e4  jns     short loc_18001E5FB
0x18001e5e6  test    rcx, rcx
0x18001e5e9  jz      short loc_18001E5F1
0x18001e5eb  call    cs:__imp_RegCloseKey
0x18001e5f1  mov     rcx, [rsp+2B0h+hKey]
0x18001e5f6  jmp     loc_18001E539
0x18001e5fb  lea     rax, [rsp+2B0h+pcbData]
0x18001e600  mov     [rsp+2B0h+pcbData], r14d
0x18001e605  mov     [rsp+2B0h+lpcchClass], rax; pcbData
0x18001e60a  lea     r8, aEntdmid; "EntDMID"
0x18001e611  mov     edi, 2
0x18001e616  mov     [rsp+2B0h+lpClass], r14; pvData
0x18001e61b  mov     r9d, edi; dwFlags
0x18001e61e  mov     [rsp+2B0h+phkResult], r14; pdwType
0x18001e623  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18001e627  call    cs:__imp_RegGetValueW
0x18001e62d  mov     ebx, eax
0x18001e62f  test    eax, eax
0x18001e631  jle     short loc_18001E63C
0x18001e633  movzx   ebx, ax
0x18001e636  or      ebx, 80070000h
0x18001e63c  test    ebx, ebx
0x18001e63e  jns     short loc_18001E647
0x18001e640  mov     rcx, [rsp+2B0h+hkey]
0x18001e645  jmp     short loc_18001E5E6
0x18001e647  mov     ebx, [rsp+2B0h+pcbData]
0x18001e64b  call    cs:__imp_GetProcessHeap
0x18001e651  mov     r8d, ebx; dwBytes
0x18001e654  mov     edx, 8; dwFlags
0x18001e659  mov     rcx, rax; hHeap
0x18001e65c  call    cs:__imp_HeapAlloc
0x18001e662  mov     [rsp+2B0h+var_250], rax
0x18001e667  mov     rbx, rax
0x18001e66a  test    rax, rax
0x18001e66d  jnz     short loc_18001E6A3
0x18001e66f  lea     rcx, [rsp+2B0h+var_250]
0x18001e674  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001e679  mov     rcx, [rsp+2B0h+hkey]; hKey
0x18001e67e  test    rcx, rcx
0x18001e681  jz      short loc_18001E689
0x18001e683  call    cs:__imp_RegCloseKey
0x18001e689  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001e68e  test    rcx, rcx
0x18001e691  jz      short loc_18001E699
0x18001e693  call    cs:__imp_RegCloseKey
0x18001e699  mov     eax, 8007000Eh
0x18001e69e  jmp     loc_18001E740
0x18001e6a3  mov     rcx, [rsp+2B0h+hkey]; hkey
0x18001e6a8  lea     rax, [rsp+2B0h+pcbData]
0x18001e6ad  mov     [rsp+2B0h+lpcchClass], rax; pcbData
0x18001e6b2  lea     r8, aEntdmid; "EntDMID"
0x18001e6b9  mov     [rsp+2B0h+lpClass], rbx; pvData
0x18001e6be  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18001e6c2  mov     r9d, edi; dwFlags
0x18001e6c5  mov     [rsp+2B0h+phkResult], r14; pdwType
0x18001e6ca  call    cs:__imp_RegGetValueW
0x18001e6d0  mov     edi, eax
0x18001e6d2  test    eax, eax
0x18001e6d4  jle     short loc_18001E6DF
0x18001e6d6  movzx   edi, ax
0x18001e6d9  or      edi, 80070000h
0x18001e6df  lea     rcx, [rsp+2B0h+var_250]
0x18001e6e4  test    edi, edi
0x18001e6e6  jns     short loc_18001E711
0x18001e6e8  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001e6ed  mov     rcx, [rsp+2B0h+hkey]; hKey
0x18001e6f2  test    rcx, rcx
0x18001e6f5  jz      short loc_18001E6FD
0x18001e6f7  call    cs:__imp_RegCloseKey
0x18001e6fd  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001e702  test    rcx, rcx
0x18001e705  jz      short loc_18001E70D
0x18001e707  call    cs:__imp_RegCloseKey
0x18001e70d  mov     eax, edi
0x18001e70f  jmp     short loc_18001E740
0x18001e711  mov     [rsp+2B0h+var_250], r14
0x18001e716  mov     [rsi], rbx
0x18001e719  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001e71e  mov     rcx, [rsp+2B0h+hkey]; hKey
0x18001e723  test    rcx, rcx
0x18001e726  jz      short loc_18001E72E
0x18001e728  call    cs:__imp_RegCloseKey
0x18001e72e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001e733  test    rcx, rcx
0x18001e736  jz      short loc_18001E73E
0x18001e738  call    cs:__imp_RegCloseKey
0x18001e73e  xor     eax, eax
0x18001e740  mov     rcx, [rbp+1B0h+var_20]
0x18001e747  xor     rcx, rsp; StackCookie
0x18001e74a  call    __security_check_cookie
0x18001e74f  lea     r11, [rsp+2B0h+var_10]
0x18001e757  mov     rbx, [r11+30h]
0x18001e75b  mov     rsi, [r11+38h]
0x18001e75f  mov     rsp, r11
0x18001e762  pop     r14
0x18001e764  pop     rdi
0x18001e765  pop     rbp
0x18001e766  retn
```
