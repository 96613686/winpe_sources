# Sm::LoadInstapiIfNeeded(void)

- ea: `0x100437ac4`
- end: `0x100437f4e`
- name: `?LoadInstapiIfNeeded@Sm@@SAKXZ`
- size: `1162`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1004381cc`

## callees

- `0x1004134a0`
- `0x100437ac4`
- `0x1004383e0`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x100546aa8`
- `0x100548210`
- `0x100548a18`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x100437d38`
- `KERNEL32!LoadLibraryA` at `0x100437d38`
- `KERNEL32!GetLastError` at `0x100437d46`
- `KERNEL32!GetLastError` at `0x100437d98`
- `KERNEL32!GetLastError` at `0x100437de2`
- `KERNEL32!GetLastError` at `0x100437d46`
- `KERNEL32!GetLastError` at `0x100437d98`
- `KERNEL32!GetLastError` at `0x100437de2`
- `KERNEL32!GetProcAddress` at `0x100437d89`
- `KERNEL32!GetProcAddress` at `0x100437dd3`
- `KERNEL32!GetProcAddress` at `0x100437d89`
- `KERNEL32!GetProcAddress` at `0x100437dd3`
- `KERNEL32!FreeLibrary` at `0x100437e2c`
- `KERNEL32!FreeLibrary` at `0x100437e2c`
- `ADVAPI32!RegQueryValueExA` at `0x100437c66`
- `ADVAPI32!RegQueryValueExA` at `0x100437c66`
- `ADVAPI32!RegOpenKeyExA` at `0x100437bf3`
- `ADVAPI32!RegOpenKeyExA` at `0x100437bf3`
- `ADVAPI32!RegCloseKey` at `0x100437c73`
- `ADVAPI32!RegCloseKey` at `0x100437c73`

## string_xrefs

- `0x100437cd1`: `instapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Sm::LoadInstapiIfNeeded(void)
{
  DWORD Value; // ebx
  _QWORD *v1; // rax
  signed __int64 v2; // rdi
  unsigned int v3; // eax
  __int64 v4; // r9
  wchar_t *v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  struct __crt_locale_pointers *v9; // rax
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  FARPROC v12; // rax
  DWORD Type[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey[2]; // [rsp+58h] [rbp-B0h] BYREF
  _DWORD v17[4]; // [rsp+68h] [rbp-A0h] BYREF
  _OWORD SubKey_8[3]; // [rsp+78h] [rbp-90h] BYREF
  BYTE Data[272]; // [rsp+A8h] [rbp-60h] BYREF
  CHAR LibFileName[288]; // [rsp+1B8h] [rbp+B0h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  Value = 0;
  v15 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7D98[0] && bidID != -1 )
    off_1005D39F0();
  if ( _InterlockedCompareExchange64(&qword_1005D8400, 0, 0) )
    goto LABEL_42;
  v1 = (_QWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 24);
  v2 = (signed __int64)v1;
  if ( !v1 )
  {
    Value = 14;
LABEL_38:
    if ( (bidGblFlags & 2) != 0 && off_1005E5AF8[0] )
    {
      SniErrorIdFromStringId(0xC3D8u);
      bidTraceW(0, 318464, off_1005E5AF8[0], 4);
    }
    SNISetLastError(4, Value, 50136);
LABEL_42:
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_1005E5B00[0] )
        bidTraceW(0, 321536, off_1005E5B00[0], Value);
    }
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
    return Value;
  }
  *v1 = 0;
  strcpy((char *)SubKey_8, "Software\\Microsoft\\Microsoft SQL Server\\90");
  v3 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, (LPCSTR)SubKey_8, 0, 1u, hKey);
  Value = v3;
  if ( v3 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E5AC8[0] )
    {
      v4 = v3;
      v5 = off_1005E5AC8[0];
      v6 = 206848;
LABEL_12:
      bidTraceW(0, v6, v5, v4);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  Type[0] = 260;
  Value = RegQueryValueExA(hKey[0], "SharedCode", 0, &Type[1], Data, Type);
  RegCloseKey(hKey[0]);
  if ( Value )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E5AD0[0] )
    {
      v4 = Value;
      v5 = off_1005E5AD0[0];
      v6 = 225280;
      goto LABEL_12;
    }
LABEL_35:
    if ( *(_QWORD *)v2 )
      FreeLibrary(*(HMODULE *)v2);
    ((void (__fastcall *)(struct IMalloc *, signed __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v2);
    if ( !Value )
      goto LABEL_42;
    goto LABEL_38;
  }
  if ( Type[1] != 1 )
  {
    Value = 13;
    goto LABEL_35;
  }
  if ( Type[0] >= 0x105uLL )
    _report_rangecheckfailure(v8, v7);
  Data[Type[0]] = 0;
  strcpy((char *)v17, "instapi.dll");
  v9 = (struct __crt_locale_pointers *)ImplBidTouch();
  if ( (int)StringCchPrintf_lA(LibFileName, 0x111u, "%s%s", v9, Data, v17) < 0 )
  {
    Value = 87;
    goto LABEL_35;
  }
  LibFileName[272] = 0;
  LibraryA = LoadLibraryA(LibFileName);
  *(_QWORD *)v2 = LibraryA;
  if ( !LibraryA )
  {
    Value = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E5AD8[0] )
    {
      v4 = Value;
      v5 = off_1005E5AD8[0];
      v6 = 259072;
      goto LABEL_12;
    }
    goto LABEL_35;
  }
  ProcAddress = GetProcAddress(LibraryA, "GetSvcInstanceIDFromName");
  *(_QWORD *)(v2 + 8) = ProcAddress;
  if ( !ProcAddress )
  {
    Value = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E5AE0[0] )
    {
      v4 = Value;
      v5 = off_1005E5AE0[0];
      v6 = 272384;
      goto LABEL_12;
    }
    goto LABEL_35;
  }
  v12 = GetProcAddress(*(HMODULE *)v2, "GetSQLInstanceRegStringByID");
  *(_QWORD *)(v2 + 16) = v12;
  if ( !v12 )
  {
    Value = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E5AE8[0] )
    {
      v4 = Value;
      v5 = off_1005E5AE8[0];
      v6 = 286720;
      goto LABEL_12;
    }
    goto LABEL_35;
  }
  if ( _InterlockedCompareExchange64(&qword_1005D8400, v2, 0) )
    goto LABEL_35;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5AF0[0] )
    bidTraceW(0, 301056, off_1005E5AF0[0], 0);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
  return 0;
}

```

## disassembly

```asm
0x100437ac4  mov     rax, rsp
0x100437ac7  push    rbp
0x100437ac8  lea     rbp, [rax-1E8h]
0x100437acf  sub     rsp, 2E0h
0x100437ad6  mov     [rsp+2E0h+var_288], 0FFFFFFFFFFFFFFFEh
0x100437adf  mov     [rax+8], rbx
0x100437ae3  mov     [rax+10h], rsi
0x100437ae7  mov     [rax+18h], rdi
0x100437aeb  mov     rax, cs:__security_cookie
0x100437af2  xor     rax, rsp
0x100437af5  mov     [rbp+1E0h+var_10], rax
0x100437afc  xor     esi, esi
0x100437afe  mov     ebx, esi
0x100437b00  or      [rsp+2E0h+var_298], 0FFFFFFFFFFFFFFFFh
0x100437b06  mov     eax, cs:_bidGblFlags
0x100437b0c  mov     ecx, 20004h
0x100437b11  and     eax, ecx
0x100437b13  cmp     eax, ecx
0x100437b15  jnz     short loc_100437B5F
0x100437b17  mov     rax, cs:off_1005E7D98; "<Sm::LoadInstapiIfNeeded|API|SNI> \n"
0x100437b1e  test    rax, rax
0x100437b21  jz      short loc_100437B5F
0x100437b23  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100437b2b  jz      short loc_100437B5F
0x100437b2d  mov     r10, cs:off_1005D39F0
0x100437b34  mov     [rsp+2E0h+lpcbData], rsi
0x100437b39  mov     rax, cs:off_1005E7D98; "<Sm::LoadInstapiIfNeeded|API|SNI> \n"
0x100437b40  mov     [rsp+2E0h+phkResult], rax
0x100437b45  lea     r9, [rsp+2E0h+var_298]
0x100437b4a  xor     r8d, r8d
0x100437b4d  xor     edx, edx
0x100437b4f  mov     rcx, cs:_bidID
0x100437b56  mov     rax, r10
0x100437b59  call    cs:__guard_dispatch_icall_fptr
0x100437b5f  xor     eax, eax
0x100437b61  lock cmpxchg cs:qword_1005D8400, rsi
0x100437b6a  jnz     loc_100437E9E
0x100437b70  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x100437b77  mov     rax, [rcx]
0x100437b7a  mov     edx, 18h
0x100437b7f  mov     rax, [rax+58h]
0x100437b83  call    cs:__guard_dispatch_icall_fptr
0x100437b89  mov     rdi, rax
0x100437b8c  test    rax, rax
0x100437b8f  jnz     short loc_100437B99
0x100437b91  lea     ebx, [rax+0Eh]
0x100437b94  jmp     loc_100437E4D
0x100437b99  mov     [rax], rsi
0x100437b9c  movups  xmm0, xmmword ptr cs:aSoftwareMicros_10; "Software\\Microsoft\\Microsoft SQL Serv"...
0x100437ba3  movups  xmmword ptr [rsp+2E0h+SubKey+8], xmm0
0x100437ba8  movups  xmm1, xmmword ptr cs:aSoftwareMicros_10+10h; "ft\\Microsoft SQL Server\\90"
0x100437baf  movups  [rbp+1E0h+var_260], xmm1
0x100437bb3  movsd   xmm0, qword ptr cs:aSoftwareMicros_10+20h; " Server\\90"
0x100437bbb  movsd   [rbp+1E0h+var_250], xmm0
0x100437bc0  movzx   eax, word ptr cs:aSoftwareMicros_10+28h; "90"
0x100437bc7  mov     [rbp+1E0h+var_248], ax
0x100437bcb  mov     al, byte ptr cs:aSoftwareMicros_10+2Ah; ""
0x100437bd1  mov     [rbp+1E0h+var_246], al
0x100437bd4  lea     rax, [rsp+2E0h+hKey]
0x100437bd9  mov     [rsp+2E0h+phkResult], rax; phkResult
0x100437bde  mov     r9d, 1; samDesired
0x100437be4  xor     r8d, r8d; ulOptions
0x100437be7  lea     rdx, [rsp+2E0h+SubKey+8]; lpSubKey
0x100437bec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100437bf3  call    cs:__imp_RegOpenKeyExA
0x100437bf9  mov     ebx, eax
0x100437bfb  test    eax, eax
0x100437bfd  jz      short loc_100437C37
0x100437bff  test    byte ptr cs:_bidGblFlags, 2
0x100437c06  jz      loc_100437E24
0x100437c0c  mov     rcx, cs:off_1005E5AC8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x100437c13  test    rcx, rcx
0x100437c16  jz      loc_100437E24
0x100437c1c  mov     r9d, eax
0x100437c1f  mov     r8, cs:off_1005E5AC8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x100437c26  mov     edx, 32800h
0x100437c2b  xor     ecx, ecx
0x100437c2d  call    _bidTraceW
0x100437c32  jmp     loc_100437E24
0x100437c37  mov     [rsp+2E0h+Type], 104h
0x100437c3f  lea     rax, [rsp+2E0h+Type]
0x100437c44  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x100437c49  lea     rax, [rbp+1E0h+Data]
0x100437c4d  mov     [rsp+2E0h+phkResult], rax; lpData
0x100437c52  lea     r9, [rsp+2E0h+Type+4]; lpType
0x100437c57  xor     r8d, r8d; lpReserved
0x100437c5a  lea     rdx, ValueName; "SharedCode"
0x100437c61  mov     rcx, [rsp+2E0h+hKey]; hKey
0x100437c66  call    cs:__imp_RegQueryValueExA
0x100437c6c  mov     ebx, eax
0x100437c6e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x100437c73  call    cs:__imp_RegCloseKey
0x100437c79  test    ebx, ebx
0x100437c7b  jz      short loc_100437CAB
0x100437c7d  test    byte ptr cs:_bidGblFlags, 2
0x100437c84  jz      loc_100437E24
0x100437c8a  mov     rax, cs:off_1005E5AD0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x100437c91  test    rax, rax
0x100437c94  jz      loc_100437E24
0x100437c9a  mov     r9d, ebx
0x100437c9d  mov     r8, cs:off_1005E5AD0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x100437ca4  mov     edx, 37000h
0x100437ca9  jmp     short loc_100437C2B
0x100437cab  cmp     [rsp+2E0h+Type+4], 1
0x100437cb0  jz      short loc_100437CBC
0x100437cb2  mov     ebx, 0Dh
0x100437cb7  jmp     loc_100437E24
0x100437cbc  mov     eax, [rsp+2E0h+Type]
0x100437cc0  cmp     rax, 105h
0x100437cc6  jnb     loc_100437F48
0x100437ccc  mov     [rbp+rax+1E0h+Data], sil
0x100437cd1  movsd   xmm0, qword ptr cs:aInstapiDll; "instapi.dll"
0x100437cd9  movsd   qword ptr [rsp+2E0h+var_280], xmm0
0x100437cdf  mov     eax, dword ptr cs:aInstapiDll+8; "dll"
0x100437ce5  mov     dword ptr [rsp+2E0h+SubKey], eax
0x100437ce9  call    ImplBidTouch
0x100437cee  mov     r9, rax; struct __crt_locale_pointers *
0x100437cf1  lea     rax, [rsp+2E0h+var_280]
0x100437cf6  mov     [rsp+2E0h+lpcbData], rax
0x100437cfb  lea     rax, [rbp+1E0h+Data]
0x100437cff  mov     [rsp+2E0h+phkResult], rax
0x100437d04  lea     r8, aSS_6; "%s%s"
0x100437d0b  mov     edx, 111h; unsigned __int64
0x100437d10  lea     rcx, [rbp+1E0h+LibFileName]; char *
0x100437d17  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100437d1c  test    eax, eax
0x100437d1e  jns     short loc_100437D2A
0x100437d20  mov     ebx, 57h ; 'W'
0x100437d25  jmp     loc_100437E24
0x100437d2a  mov     [rbp+1E0h+var_20], sil
0x100437d31  lea     rcx, [rbp+1E0h+LibFileName]; lpLibFileName
0x100437d38  call    cs:__imp_LoadLibraryA
0x100437d3e  mov     [rdi], rax
0x100437d41  test    rax, rax
0x100437d44  jnz     short loc_100437D7F
0x100437d46  call    cs:__imp_GetLastError
0x100437d4c  mov     ebx, eax
0x100437d4e  test    byte ptr cs:_bidGblFlags, 2
0x100437d55  jz      loc_100437E24
0x100437d5b  mov     rax, cs:off_1005E5AD8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x100437d62  test    rax, rax
0x100437d65  jz      loc_100437E24
0x100437d6b  mov     r9d, ebx
0x100437d6e  mov     r8, cs:off_1005E5AD8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x100437d75  mov     edx, 3F400h
0x100437d7a  jmp     loc_100437C2B
0x100437d7f  lea     rdx, aGetsvcinstance; "GetSvcInstanceIDFromName"
0x100437d86  mov     rcx, rax; hModule
0x100437d89  call    cs:__imp_GetProcAddress
0x100437d8f  mov     [rdi+8], rax
0x100437d93  test    rax, rax
0x100437d96  jnz     short loc_100437DC9
0x100437d98  call    cs:__imp_GetLastError
0x100437d9e  mov     ebx, eax
0x100437da0  test    byte ptr cs:_bidGblFlags, 2
0x100437da7  jz      short loc_100437E24
0x100437da9  mov     rax, cs:off_1005E5AE0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x100437db0  test    rax, rax
0x100437db3  jz      short loc_100437E24
0x100437db5  mov     r9d, ebx
0x100437db8  mov     r8, cs:off_1005E5AE0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x100437dbf  mov     edx, 42800h
0x100437dc4  jmp     loc_100437C2B
0x100437dc9  lea     rdx, aGetsqlinstance; "GetSQLInstanceRegStringByID"
0x100437dd0  mov     rcx, [rdi]; hModule
0x100437dd3  call    cs:__imp_GetProcAddress
0x100437dd9  mov     [rdi+10h], rax
0x100437ddd  test    rax, rax
0x100437de0  jnz     short loc_100437E13
0x100437de2  call    cs:__imp_GetLastError
0x100437de8  mov     ebx, eax
0x100437dea  test    byte ptr cs:_bidGblFlags, 2
0x100437df1  jz      short loc_100437E24
0x100437df3  mov     rax, cs:off_1005E5AE8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x100437dfa  test    rax, rax
0x100437dfd  jz      short loc_100437E24
0x100437dff  mov     r9d, ebx
0x100437e02  mov     r8, cs:off_1005E5AE8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x100437e09  mov     edx, 46000h
0x100437e0e  jmp     loc_100437C2B
0x100437e13  xor     eax, eax
0x100437e15  lock cmpxchg cs:qword_1005D8400, rdi
0x100437e1e  jz      loc_100437F06
0x100437e24  mov     rcx, [rdi]; hLibModule
0x100437e27  test    rcx, rcx
0x100437e2a  jz      short loc_100437E32
0x100437e2c  call    cs:__imp_FreeLibrary
0x100437e32  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100437e39  mov     rax, [rcx]
0x100437e3c  mov     rdx, rdi
0x100437e3f  mov     rax, [rax+68h]
0x100437e43  call    cs:__guard_dispatch_icall_fptr
0x100437e49  test    ebx, ebx
0x100437e4b  jz      short loc_100437E9E
0x100437e4d  mov     edi, 0C3D8h
0x100437e52  test    byte ptr cs:_bidGblFlags, 2
0x100437e59  jz      short loc_100437E8F
0x100437e5b  mov     rax, cs:off_1005E5AF8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Provi"...
0x100437e62  test    rax, rax
0x100437e65  jz      short loc_100437E8F
0x100437e67  mov     ecx, edi; unsigned int
0x100437e69  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100437e6e  mov     dword ptr [rsp+2E0h+lpcbData], ebx
0x100437e72  mov     dword ptr [rsp+2E0h+phkResult], eax
0x100437e76  mov     r9d, 4
0x100437e7c  mov     r8, cs:off_1005E5AF8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Provi"...
0x100437e83  mov     edx, 4DC00h
0x100437e88  xor     ecx, ecx
0x100437e8a  call    _bidTraceW
0x100437e8f  mov     r8d, edi
0x100437e92  mov     edx, ebx
0x100437e94  mov     ecx, 4
0x100437e99  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100437e9e  mov     eax, cs:_bidGblFlags
0x100437ea4  mov     ecx, 20002h
0x100437ea9  and     eax, ecx
0x100437eab  cmp     eax, ecx
0x100437ead  jnz     short loc_100437ED2
0x100437eaf  mov     rax, cs:off_1005E5B00; "<Sm::LoadInstapiIfNeeded|RET|SNI> %d{WI"...
0x100437eb6  test    rax, rax
0x100437eb9  jz      short loc_100437ED2
0x100437ebb  mov     r9d, ebx
0x100437ebe  mov     r8, cs:off_1005E5B00; "<Sm::LoadInstapiIfNeeded|RET|SNI> %d{WI"...
0x100437ec5  mov     edx, 4E800h
0x100437eca  xor     ecx, ecx
0x100437ecc  call    _bidTraceW
0x100437ed1  nop
0x100437ed2  lea     rcx, [rsp+2E0h+var_298]; this
0x100437ed7  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100437edc  mov     eax, ebx
0x100437ede  mov     rcx, [rbp+1E0h+var_10]
0x100437ee5  xor     rcx, rsp; StackCookie
0x100437ee8  call    __security_check_cookie
0x100437eed  lea     r11, [rsp+2E0h+var_s0]
0x100437ef5  mov     rbx, [r11+10h]
0x100437ef9  mov     rsi, [r11+18h]
0x100437efd  mov     rdi, [r11+20h]
0x100437f01  mov     rsp, r11
0x100437f04  pop     rbp
0x100437f05  retn
0x100437f06  mov     eax, cs:_bidGblFlags
0x100437f0c  mov     ecx, 20002h
0x100437f11  and     eax, ecx
0x100437f13  cmp     eax, ecx
0x100437f15  jnz     short loc_100437F3A
0x100437f17  mov     rax, cs:off_1005E5AF0; "<Sm::LoadInstapiIfNeeded|RET|SNI> Loade"...
0x100437f1e  test    rax, rax
0x100437f21  jz      short loc_100437F3A
0x100437f23  xor     r9d, r9d
0x100437f26  mov     r8, cs:off_1005E5AF0; "<Sm::LoadInstapiIfNeeded|RET|SNI> Loade"...
0x100437f2d  mov     edx, 49800h
0x100437f32  xor     ecx, ecx
0x100437f34  call    _bidTraceW
0x100437f39  nop
0x100437f3a  lea     rcx, [rsp+2E0h+var_298]; this
0x100437f3f  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100437f44  xor     eax, eax
0x100437f46  jmp     short loc_100437EDE
0x100437f48  call    __report_rangecheckfailure
```
