# LookUpXaDllPath(char *,char *,ulong)

- ea: `0x180021688`
- end: `0x1800219a2`
- name: `?LookUpXaDllPath@@YAJPEAD0K@Z`
- size: `794`
- prototype: `__int64 __fastcall(char *lpValueName, char *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a828`
- `0x18001ae88`
- `0x18001b8f0`

## callees

- `0x1800063b0`
- `0x180007d08`
- `0x180013a84`
- `0x180021688`
- `0x1800298ac`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002192b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002192b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800217b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800217b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021825`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180021818`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180021818`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002174a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002174a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002178b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800217dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002178b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800217dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800218c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800218c8`

## string_xrefs

- `0x1800216e6`: `LookUpXaDllPath`
- `0x18002189d`: `LookUpXaDllPath`
- `0x180021951`: `LookUpXaDllPath`
- `0x1800216b8`: `Looking up XA DLL '%S'`
- `0x1800216c4`: `com\complus\dtc\dtc\xatm\src\xatmdll.cpp`
- `0x180021888`: `The registry value is not a string.`
- `0x180021936`: `Xa DLL Lookup completed, HR=%08x, Path='%S'`
- `0x180021721`: `Software\Microsoft\MSDTC\XADLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LookUpXaDllPath(char *lpValueName, char *a2)
{
  BYTE *v4; // rsi
  LSTATUS v5; // eax
  signed int v6; // ebx
  unsigned int v7; // edi
  LSTATUS v8; // eax
  const wchar_t *v9; // rax
  __int64 v10; // r9
  LSTATUS v11; // eax
  bool v12; // zf
  DWORD v13; // eax
  signed int LastError; // eax
  void *v15; // r9
  void *v17; // [rsp+40h] [rbp-21h]
  DWORD cbData; // [rsp+58h] [rbp-9h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-5h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-1h] BYREF
  char *v21[2]; // [rsp+68h] [rbp+7h] BYREF
  char v22[16]; // [rsp+78h] [rbp+17h] BYREF

  cbData = 0;
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmdll.cpp",
    175,
    L"LookUpXaDllPath",
    0,
    L"Looking up XA DLL '%S'",
    lpValueName);
  if ( !lpValueName || !a2 )
    return 2147942487LL;
  v21[0] = lpValueName;
  v21[1] = v22;
  v4 = 0;
  hKey = 0;
  Type = 0;
  v5 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\MSDTC\\XADLL", 0, 0x20119u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = -1073737380;
    goto LABEL_29;
  }
  v8 = RegQueryValueExA(hKey, lpValueName, 0, &Type, 0, &cbData);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v9 = L"RegQueryValueExA failed";
    v10 = 213;
    goto LABEL_28;
  }
  v4 = (BYTE *)CoTaskMemAlloc(cbData);
  v11 = RegQueryValueExA(hKey, lpValueName, 0, &Type, v4, &cbData);
  v6 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    v7 = -1073737379;
    goto LABEL_29;
  }
  v6 = 0;
  v12 = Type == 2;
  a2[260] = 0;
  if ( v12 )
  {
    v13 = ExpandEnvironmentStringsA((LPCSTR)v4, a2, 0x105u);
    cbData = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_20;
      goto LABEL_23;
    }
    if ( v13 > 0x105 )
    {
      v6 = -2147024662;
LABEL_23:
      v9 = L"ExpandEnvironmentStringsA failed";
      v10 = 254;
LABEL_28:
      v7 = -1073737379;
      TraceStringInline(11, 1, L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmdll.cpp", v10, L"LookUpXaDllPath", v6, v9);
      goto LABEL_29;
    }
  }
  else
  {
    if ( Type != 1 )
    {
      v9 = L"The registry value is not a string.";
      v10 = 272;
      goto LABEL_28;
    }
    v6 = StringCchCopyA(a2, 0x105u, (const char *)v4);
    if ( v6 < 0 )
    {
      v9 = L"StringCchPrintfA failed";
      v10 = 265;
      goto LABEL_28;
    }
  }
LABEL_20:
  v7 = 0;
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 < 0 )
  {
    StringCchPrintfA(v22, 0x10u, "0x%08x", v6);
    DtcWriteToEventLoggerExA(1u, 5u, v7, v15, 2u, 0, (const char **)v21, 0, 0);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  LODWORD(v17) = v6;
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmdll.cpp",
    294,
    L"LookUpXaDllPath",
    0,
    L"Xa DLL Lookup completed, HR=%08x, Path='%S'",
    v17,
    a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021688  mov     r11, rsp
0x18002168b  mov     [r11+18h], rbx
0x18002168f  mov     [r11+20h], rsi
0x180021693  push    rbp
0x180021694  push    rdi
0x180021695  push    r12
0x180021697  push    r13
0x180021699  push    r14
0x18002169b  lea     rbp, [r11-5Fh]
0x18002169f  sub     rsp, 90h
0x1800216a6  mov     rax, cs:__security_cookie
0x1800216ad  xor     rax, rsp
0x1800216b0  mov     [rbp+57h+var_30], rax
0x1800216b4  mov     [r11-80h], rcx
0x1800216b8  lea     rax, aLookingUpXaDll; "Looking up XA DLL '%S'"
0x1800216bf  mov     [rsp+0B0h+var_80], rax
0x1800216c4  lea     r13, aComComplusDtcD_26; "com\\complus\\dtc\\dtc\\xatm\\src\\xatm"...
0x1800216cb  mov     r14, rdx
0x1800216ce  mov     [rsp+0B0h+lpcbData], 0
0x1800216d7  mov     edx, 4
0x1800216dc  mov     [rbp+57h+cbData], 0
0x1800216e3  mov     rdi, rcx
0x1800216e6  lea     rax, aLookupxadllpat; "LookUpXaDllPath"
0x1800216ed  mov     r9d, 0AFh
0x1800216f3  mov     [rsp+0B0h+phkResult], rax
0x1800216f8  mov     r8, r13
0x1800216fb  lea     ecx, [rdx+7]
0x1800216fe  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180021703  test    rdi, rdi
0x180021706  jz      loc_180021975
0x18002170c  test    r14, r14
0x18002170f  jz      loc_180021975
0x180021715  lea     rax, [rbp+57h+var_40]
0x180021719  mov     [rbp+57h+var_50], rdi
0x18002171d  mov     [rbp+57h+var_48], rax
0x180021721  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\MSDTC\\XADLL"
0x180021728  lea     rax, [rbp+57h+hKey]
0x18002172c  xor     esi, esi
0x18002172e  mov     r9d, 20119h; samDesired
0x180021734  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180021739  xor     r8d, r8d; ulOptions
0x18002173c  mov     [rbp+57h+hKey], rsi
0x180021740  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021747  mov     [rbp+57h+Type], esi
0x18002174a  call    cs:__imp_RegOpenKeyExA
0x180021750  lea     r12d, [rsi+1]
0x180021754  mov     ebx, eax
0x180021756  test    eax, eax
0x180021758  jz      short loc_18002176F
0x18002175a  jle     short loc_180021765
0x18002175c  movzx   ebx, ax
0x18002175f  or      ebx, 80070000h
0x180021765  mov     edi, 0C000115Ch
0x18002176a  jmp     loc_1800218BF
0x18002176f  mov     rcx, [rbp+57h+hKey]; hKey
0x180021773  lea     rax, [rbp+57h+cbData]
0x180021777  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18002177c  lea     r9, [rbp+57h+Type]; lpType
0x180021780  xor     r8d, r8d; lpReserved
0x180021783  mov     [rsp+0B0h+phkResult], rsi; lpData
0x180021788  mov     rdx, rdi; lpValueName
0x18002178b  call    cs:__imp_RegQueryValueExA
0x180021791  mov     ebx, eax
0x180021793  test    eax, eax
0x180021795  jz      short loc_1800217B4
0x180021797  jle     short loc_1800217A2
0x180021799  movzx   ebx, ax
0x18002179c  or      ebx, 80070000h
0x1800217a2  lea     rax, aRegqueryvaluee; "RegQueryValueExA failed"
0x1800217a9  mov     r9d, 0D5h
0x1800217af  jmp     loc_180021895
0x1800217b4  mov     ecx, [rbp+57h+cbData]; cb
0x1800217b7  call    cs:__imp_CoTaskMemAlloc
0x1800217bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800217c1  lea     r9, [rbp+57h+Type]; lpType
0x1800217c5  mov     rsi, rax
0x1800217c8  xor     r8d, r8d; lpReserved
0x1800217cb  lea     rax, [rbp+57h+cbData]
0x1800217cf  mov     rdx, rdi; lpValueName
0x1800217d2  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800217d7  mov     [rsp+0B0h+phkResult], rsi; lpData
0x1800217dc  call    cs:__imp_RegQueryValueExA
0x1800217e2  mov     ebx, eax
0x1800217e4  test    eax, eax
0x1800217e6  jz      short loc_1800217FD
0x1800217e8  jle     short loc_1800217F3
0x1800217ea  movzx   ebx, ax
0x1800217ed  or      ebx, 80070000h
0x1800217f3  mov     edi, 0C000115Dh
0x1800217f8  jmp     loc_1800218BF
0x1800217fd  xor     ebx, ebx
0x1800217ff  cmp     [rbp+57h+Type], 2
0x180021803  mov     [r14+104h], bl
0x18002180a  jnz     short loc_18002185D
0x18002180c  mov     r8d, 105h; nSize
0x180021812  mov     rdx, r14; lpDst
0x180021815  mov     rcx, rsi; lpSrc
0x180021818  call    cs:__imp_ExpandEnvironmentStringsA
0x18002181e  mov     [rbp+57h+cbData], eax
0x180021821  test    eax, eax
0x180021823  jnz     short loc_180021842
0x180021825  call    cs:__imp_GetLastError
0x18002182b  mov     ebx, eax
0x18002182d  test    eax, eax
0x18002182f  jle     short loc_18002183A
0x180021831  movzx   ebx, ax
0x180021834  or      ebx, 80070000h
0x18002183a  test    ebx, ebx
0x18002183c  js      short loc_18002184E
0x18002183e  xor     edi, edi
0x180021840  jmp     short loc_1800218BF
0x180021842  cmp     eax, 105h
0x180021847  jbe     short loc_18002183E
0x180021849  mov     ebx, 800700EAh
0x18002184e  lea     rax, aExpandenvironm; "ExpandEnvironmentStringsA failed"
0x180021855  mov     r9d, 0FEh
0x18002185b  jmp     short loc_180021895
0x18002185d  cmp     [rbp+57h+Type], r12d
0x180021861  jnz     short loc_180021888
0x180021863  mov     r8, rsi; char *
0x180021866  mov     edx, 105h; unsigned __int64
0x18002186b  mov     rcx, r14; char *
0x18002186e  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180021873  mov     ebx, eax
0x180021875  test    eax, eax
0x180021877  jns     short loc_18002183E
0x180021879  lea     rax, aStringcchprint; "StringCchPrintfA failed"
0x180021880  mov     r9d, 109h
0x180021886  jmp     short loc_180021895
0x180021888  lea     rax, aTheRegistryVal; "The registry value is not a string."
0x18002188f  mov     r9d, 110h
0x180021895  mov     [rsp+0B0h+var_80], rax
0x18002189a  mov     r8, r13
0x18002189d  lea     rax, aLookupxadllpat; "LookUpXaDllPath"
0x1800218a4  mov     dword ptr [rsp+0B0h+lpcbData], ebx
0x1800218a8  mov     edx, r12d
0x1800218ab  mov     [rsp+0B0h+phkResult], rax
0x1800218b0  mov     ecx, 0Bh
0x1800218b5  mov     edi, 0C000115Dh
0x1800218ba  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800218bf  mov     rcx, [rbp+57h+hKey]; hKey
0x1800218c3  test    rcx, rcx
0x1800218c6  jz      short loc_1800218CE
0x1800218c8  call    cs:__imp_RegCloseKey
0x1800218ce  test    ebx, ebx
0x1800218d0  jns     short loc_180021923
0x1800218d2  mov     r9d, ebx
0x1800218d5  lea     r8, a0x08x_0; "0x%08x"
0x1800218dc  mov     edx, 10h; unsigned __int64
0x1800218e1  lea     rcx, [rbp+57h+var_40]; char *
0x1800218e5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800218ea  mov     [rsp+0B0h+var_70], 0; int
0x1800218f2  lea     rax, [rbp+57h+var_50]
0x1800218f6  mov     [rsp+0B0h+var_78], 0; void *
0x1800218ff  mov     edx, 5; unsigned __int16
0x180021904  mov     [rsp+0B0h+var_80], rax; char **
0x180021909  mov     ecx, r12d; unsigned __int16
0x18002190c  mov     dword ptr [rsp+0B0h+lpcbData], 0; unsigned int
0x180021914  mov     r8d, edi; unsigned int
0x180021917  mov     word ptr [rsp+0B0h+phkResult], 2; unsigned __int16
0x18002191e  call    ?DtcWriteToEventLoggerExA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x180021923  test    rsi, rsi
0x180021926  jz      short loc_180021931
0x180021928  mov     rcx, rsi; pv
0x18002192b  call    cs:__imp_CoTaskMemFree
0x180021931  mov     qword ptr [rsp+0B0h+var_70], r14
0x180021936  lea     rax, aXaDllLookupCom; "Xa DLL Lookup completed, HR=%08x, Path="...
0x18002193d  mov     dword ptr [rsp+0B0h+var_78], ebx
0x180021941  mov     edx, 4
0x180021946  mov     [rsp+0B0h+var_80], rax
0x18002194b  mov     r9d, 126h
0x180021951  lea     rax, aLookupxadllpat; "LookUpXaDllPath"
0x180021958  mov     [rsp+0B0h+lpcbData], 0
0x180021961  mov     r8, r13
0x180021964  mov     [rsp+0B0h+phkResult], rax
0x180021969  lea     ecx, [rdx+7]
0x18002196c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180021971  mov     eax, ebx
0x180021973  jmp     short loc_18002197A
0x180021975  mov     eax, 80070057h
0x18002197a  mov     rcx, [rbp+57h+var_30]
0x18002197e  xor     rcx, rsp; StackCookie
0x180021981  call    __security_check_cookie
0x180021986  lea     r11, [rsp+0B0h+var_20]
0x18002198e  mov     rbx, [r11+40h]
0x180021992  mov     rsi, [r11+48h]
0x180021996  mov     rsp, r11
0x180021999  pop     r14
0x18002199b  pop     r13
0x18002199d  pop     r12
0x18002199f  pop     rdi
0x1800219a0  pop     rbp
0x1800219a1  retn
```
