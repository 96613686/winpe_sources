# CWPPLoggerGuidConfig::ReadTraceConfig(void)

- ea: `0x180027dd4`
- end: `0x18002824e`
- name: `?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ`
- size: `1146`
- prototype: `__int64 __fastcall(CWPPLoggerGuidConfig *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fb74`
- `0x180083e28`
- `0x18008405c`

## callees

- `0x1800077a0`
- `0x180027dd4`
- `0x180028254`
- `0x1800282e0`
- `0x18004e850`
- `0x18004f354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027ee7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027f33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027f84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002803a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028090`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800280f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028138`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027ee7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027f33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027f84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002803a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028090`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800280f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028138`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028217`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028217`

## string_xrefs

- `0x180027e77`: `error %#x: RegOpenKeyEx(%S) failed`

## pseudocode

```c
__int64 __fastcall CWPPLoggerGuidConfig::ReadTraceConfig(CWPPLoggerGuidConfig *this)
{
  LSTATUS v2; // eax
  signed int v3; // edi
  bool v4; // zf
  int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // eax
  HKEY v8; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  memset_0(ValueName, 0, 0x208u);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    _DbgPrintMessage(1, "error %#x: RegOpenKeyEx(%S) failed", v2, ValueName);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v3 = 0;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%s", *((_QWORD *)this + 2));
    cbData = 4;
    if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4
      || (cbData = 4, !RegQueryValueExW(hKey, L"Debug", 0, &Type, Data, &cbData)) && Type == 4 )
    {
      v4 = *(_DWORD *)Data == 0;
    }
    else
    {
      v4 = (unsigned int)CUtils::IsKernelDebuggerAttached() == 0;
    }
    *((_BYTE *)this + 32) = !v4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"CaptureStackTrace", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v5 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v5 = *(_DWORD *)Data;
    }
    v6 = *((_QWORD *)this + 2);
    g_bCaptureObjectStackTrace = v5;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sFlags", v6);
    cbData = 4;
    if ( RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) || Type != 4 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"DebugFlags", 0, &Type, Data, &cbData) || (v7 = *(_DWORD *)Data, Type != 4) )
        v7 = -2;
    }
    else
    {
      v7 = *(_DWORD *)Data;
    }
    v8 = hKey;
    *((_DWORD *)this + 6) = v7;
    g_DebugTraceComponent = v7;
    cbData = 4;
    if ( !RegQueryValueExW(v8, L"DebugFlagsEx", 0, &Type, Data, &cbData) && Type == 4 )
      g_DebugFlagsEx = *(_DWORD *)Data;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sLevel", *((_QWORD *)this + 2));
    cbData = 4;
    if ( (RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) || Type != 4)
      && ((cbData = 4, RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, Data, &cbData)) || Type != 4) )
    {
      *((_DWORD *)this + 7) = 16574;
    }
    else
    {
      *((_DWORD *)this + 7) = *(_DWORD *)Data;
    }
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sToDebugger", *((_QWORD *)this + 2));
    cbData = 4;
    *((_BYTE *)this + 33) = (!RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4
                          || (cbData = 4, !RegQueryValueExW(hKey, L"DebugToDebugger", 0, &Type, Data, &cbData))
                          && Type == 4)
                         && *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180027dd4  mov     [rsp-8+arg_8], rbx
0x180027dd9  mov     [rsp-8+arg_10], rdi
0x180027dde  push    rbp
0x180027ddf  push    r14
0x180027de1  push    r15
0x180027de3  lea     rbp, [rsp-170h]
0x180027deb  sub     rsp, 270h
0x180027df2  mov     rax, cs:__security_cookie
0x180027df9  xor     rax, rsp
0x180027dfc  mov     [rbp+180h+var_20], rax
0x180027e03  mov     rbx, rcx
0x180027e06  mov     [rsp+280h+Type], 0
0x180027e0e  mov     r15d, 208h
0x180027e14  mov     dword ptr [rsp+280h+Data], 0
0x180027e1c  mov     r8d, r15d; Size
0x180027e1f  mov     [rsp+280h+cbData], 0
0x180027e27  xor     edx, edx; Val
0x180027e29  mov     [rsp+280h+hKey], 0
0x180027e32  lea     rcx, [rsp+280h+ValueName]; void *
0x180027e37  call    memset_0
0x180027e3c  lea     rax, [rsp+280h+hKey]
0x180027e41  mov     r9d, 20019h; samDesired
0x180027e47  xor     r8d, r8d; ulOptions
0x180027e4a  mov     [rsp+280h+phkResult], rax; phkResult
0x180027e4f  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180027e56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027e5d  call    cs:__imp_RegOpenKeyExW
0x180027e64  nop     dword ptr [rax+rax+00h]
0x180027e69  mov     edi, eax
0x180027e6b  test    eax, eax
0x180027e6d  jz      short loc_180027E9E
0x180027e6f  lea     r9, [rsp+280h+ValueName]
0x180027e74  mov     r8d, eax
0x180027e77  lea     rdx, aErrorXRegopenk; "error %#x: RegOpenKeyEx(%S) failed"
0x180027e7e  mov     ecx, 1; int
0x180027e83  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027e88  test    edi, edi
0x180027e8a  jle     loc_18002820D
0x180027e90  movzx   edi, di
0x180027e93  or      edi, 80070000h
0x180027e99  jmp     loc_18002820D
0x180027e9e  mov     r9, [rbx+10h]
0x180027ea2  lea     r8, aDebugS; "Debug%s"
0x180027ea9  mov     rdx, r15; unsigned __int64
0x180027eac  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180027eb1  xor     edi, edi
0x180027eb3  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027eb8  mov     rcx, [rsp+280h+hKey]; hKey
0x180027ebd  lea     rax, [rsp+280h+cbData]
0x180027ec2  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180027ec7  lea     r14d, [rdi+4]
0x180027ecb  lea     rax, [rsp+280h+Data]
0x180027ed0  mov     [rsp+280h+cbData], r14d
0x180027ed5  lea     r9, [rsp+280h+Type]; lpType
0x180027eda  mov     [rsp+280h+phkResult], rax; lpData
0x180027edf  xor     r8d, r8d; lpReserved
0x180027ee2  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180027ee7  call    cs:__imp_RegQueryValueExW
0x180027eee  nop     dword ptr [rax+rax+00h]
0x180027ef3  test    eax, eax
0x180027ef5  jnz     short loc_180027F06
0x180027ef7  cmp     [rsp+280h+Type], r14d
0x180027efc  jnz     short loc_180027F06
0x180027efe  xor     ecx, ecx
0x180027f00  cmp     dword ptr [rsp+280h+Data], ecx
0x180027f04  jmp     short loc_180027F51
0x180027f06  mov     rcx, [rsp+280h+hKey]; hKey
0x180027f0b  lea     rax, [rsp+280h+cbData]
0x180027f10  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180027f15  lea     r9, [rsp+280h+Type]; lpType
0x180027f1a  lea     rax, [rsp+280h+Data]
0x180027f1f  mov     [rsp+280h+cbData], r14d
0x180027f24  xor     r8d, r8d; lpReserved
0x180027f27  mov     [rsp+280h+phkResult], rax; lpData
0x180027f2c  lea     rdx, aDebug; "Debug"
0x180027f33  call    cs:__imp_RegQueryValueExW
0x180027f3a  nop     dword ptr [rax+rax+00h]
0x180027f3f  test    eax, eax
0x180027f41  jnz     short loc_180027F4A
0x180027f43  cmp     [rsp+280h+Type], r14d
0x180027f48  jz      short loc_180027EFE
0x180027f4a  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x180027f4f  test    eax, eax
0x180027f51  setnz   cl
0x180027f54  lea     rax, [rsp+280h+cbData]
0x180027f59  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180027f5e  lea     r9, [rsp+280h+Type]; lpType
0x180027f63  mov     [rbx+20h], cl
0x180027f66  lea     rax, [rsp+280h+Data]
0x180027f6b  mov     rcx, [rsp+280h+hKey]; hKey
0x180027f70  lea     rdx, aCapturestacktr; "CaptureStackTrace"
0x180027f77  xor     r8d, r8d; lpReserved
0x180027f7a  mov     [rsp+280h+phkResult], rax; lpData
0x180027f7f  mov     [rsp+280h+cbData], r14d
0x180027f84  call    cs:__imp_RegQueryValueExW
0x180027f8b  nop     dword ptr [rax+rax+00h]
0x180027f90  test    eax, eax
0x180027f92  jnz     short loc_180027FA1
0x180027f94  cmp     [rsp+280h+Type], r14d
0x180027f99  jnz     short loc_180027FA1
0x180027f9b  mov     eax, dword ptr [rsp+280h+Data]
0x180027f9f  jmp     short loc_180027FA7
0x180027fa1  xor     eax, eax
0x180027fa3  mov     dword ptr [rsp+280h+Data], eax
0x180027fa7  mov     r9, [rbx+10h]
0x180027fab  lea     r8, aDebugSflags; "Debug%sFlags"
0x180027fb2  mov     rdx, r15; unsigned __int64
0x180027fb5  mov     cs:?g_bCaptureObjectStackTrace@@3HA, eax; int g_bCaptureObjectStackTrace
0x180027fbb  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180027fc0  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027fc5  mov     rcx, [rsp+280h+hKey]; hKey
0x180027fca  lea     rax, [rsp+280h+cbData]
0x180027fcf  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180027fd4  lea     r9, [rsp+280h+Type]; lpType
0x180027fd9  lea     rax, [rsp+280h+Data]
0x180027fde  mov     [rsp+280h+cbData], r14d
0x180027fe3  xor     r8d, r8d; lpReserved
0x180027fe6  mov     [rsp+280h+phkResult], rax; lpData
0x180027feb  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180027ff0  call    cs:__imp_RegQueryValueExW
0x180027ff7  nop     dword ptr [rax+rax+00h]
0x180027ffc  test    eax, eax
0x180027ffe  jnz     short loc_18002800D
0x180028000  cmp     [rsp+280h+Type], r14d
0x180028005  jnz     short loc_18002800D
0x180028007  mov     eax, dword ptr [rsp+280h+Data]
0x18002800b  jmp     short loc_18002805A
0x18002800d  mov     rcx, [rsp+280h+hKey]; hKey
0x180028012  lea     rax, [rsp+280h+cbData]
0x180028017  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002801c  lea     r9, [rsp+280h+Type]; lpType
0x180028021  lea     rax, [rsp+280h+Data]
0x180028026  mov     [rsp+280h+cbData], r14d
0x18002802b  xor     r8d, r8d; lpReserved
0x18002802e  mov     [rsp+280h+phkResult], rax; lpData
0x180028033  lea     rdx, aDebugflags; "DebugFlags"
0x18002803a  call    cs:__imp_RegQueryValueExW
0x180028041  nop     dword ptr [rax+rax+00h]
0x180028046  test    eax, eax
0x180028048  jnz     short loc_180028055
0x18002804a  mov     eax, dword ptr [rsp+280h+Data]
0x18002804e  cmp     [rsp+280h+Type], r14d
0x180028053  jz      short loc_18002805A
0x180028055  mov     eax, 0FFFFFFFEh
0x18002805a  mov     rcx, [rsp+280h+hKey]; hKey
0x18002805f  lea     r9, [rsp+280h+Type]; lpType
0x180028064  mov     [rbx+18h], eax
0x180028067  lea     rdx, aDebugflagsex; "DebugFlagsEx"
0x18002806e  mov     cs:?g_DebugTraceComponent@@3KA, eax; ulong g_DebugTraceComponent
0x180028074  xor     r8d, r8d; lpReserved
0x180028077  lea     rax, [rsp+280h+cbData]
0x18002807c  mov     [rsp+280h+cbData], r14d
0x180028081  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180028086  lea     rax, [rsp+280h+Data]
0x18002808b  mov     [rsp+280h+phkResult], rax; lpData
0x180028090  call    cs:__imp_RegQueryValueExW
0x180028097  nop     dword ptr [rax+rax+00h]
0x18002809c  test    eax, eax
0x18002809e  jnz     short loc_1800280B1
0x1800280a0  cmp     [rsp+280h+Type], r14d
0x1800280a5  jnz     short loc_1800280B1
0x1800280a7  mov     eax, dword ptr [rsp+280h+Data]
0x1800280ab  mov     cs:?g_DebugFlagsEx@@3KA, eax; ulong g_DebugFlagsEx
0x1800280b1  mov     r9, [rbx+10h]
0x1800280b5  lea     r8, aDebugSlevel; "Debug%sLevel"
0x1800280bc  mov     rdx, r15; unsigned __int64
0x1800280bf  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x1800280c4  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800280c9  mov     rcx, [rsp+280h+hKey]; hKey
0x1800280ce  lea     rax, [rsp+280h+cbData]
0x1800280d3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800280d8  lea     r9, [rsp+280h+Type]; lpType
0x1800280dd  lea     rax, [rsp+280h+Data]
0x1800280e2  mov     [rsp+280h+cbData], r14d
0x1800280e7  xor     r8d, r8d; lpReserved
0x1800280ea  mov     [rsp+280h+phkResult], rax; lpData
0x1800280ef  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x1800280f4  call    cs:__imp_RegQueryValueExW
0x1800280fb  nop     dword ptr [rax+rax+00h]
0x180028100  test    eax, eax
0x180028102  jnz     short loc_18002810B
0x180028104  cmp     [rsp+280h+Type], r14d
0x180028109  jz      short loc_18002814F
0x18002810b  mov     rcx, [rsp+280h+hKey]; hKey
0x180028110  lea     rax, [rsp+280h+cbData]
0x180028115  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002811a  lea     r9, [rsp+280h+Type]; lpType
0x18002811f  lea     rax, [rsp+280h+Data]
0x180028124  mov     [rsp+280h+cbData], r14d
0x180028129  xor     r8d, r8d; lpReserved
0x18002812c  mov     [rsp+280h+phkResult], rax; lpData
0x180028131  lea     rdx, aDebuglevel; "DebugLevel"
0x180028138  call    cs:__imp_RegQueryValueExW
0x18002813f  nop     dword ptr [rax+rax+00h]
0x180028144  test    eax, eax
0x180028146  jnz     short loc_180028158
0x180028148  cmp     [rsp+280h+Type], r14d
0x18002814d  jnz     short loc_180028158
0x18002814f  mov     eax, dword ptr [rsp+280h+Data]
0x180028153  mov     [rbx+1Ch], eax
0x180028156  jmp     short loc_18002815F
0x180028158  mov     dword ptr [rbx+1Ch], 40BEh
0x18002815f  mov     r9, [rbx+10h]
0x180028163  lea     r8, aDebugStodebugg; "Debug%sToDebugger"
0x18002816a  mov     rdx, r15; unsigned __int64
0x18002816d  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180028172  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028177  mov     rcx, [rsp+280h+hKey]; hKey
0x18002817c  lea     rax, [rsp+280h+cbData]
0x180028181  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180028186  lea     r9, [rsp+280h+Type]; lpType
0x18002818b  lea     rax, [rsp+280h+Data]
0x180028190  mov     [rsp+280h+cbData], r14d
0x180028195  xor     r8d, r8d; lpReserved
0x180028198  mov     [rsp+280h+phkResult], rax; lpData
0x18002819d  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x1800281a2  call    cs:__imp_RegQueryValueExW
0x1800281a9  nop     dword ptr [rax+rax+00h]
0x1800281ae  test    eax, eax
0x1800281b0  jnz     short loc_1800281B9
0x1800281b2  cmp     [rsp+280h+Type], r14d
0x1800281b7  jz      short loc_1800281FD
0x1800281b9  mov     rcx, [rsp+280h+hKey]; hKey
0x1800281be  lea     rax, [rsp+280h+cbData]
0x1800281c3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800281c8  lea     r9, [rsp+280h+Type]; lpType
0x1800281cd  lea     rax, [rsp+280h+Data]
0x1800281d2  mov     [rsp+280h+cbData], r14d
0x1800281d7  xor     r8d, r8d; lpReserved
0x1800281da  mov     [rsp+280h+phkResult], rax; lpData
0x1800281df  lea     rdx, aDebugtodebugge; "DebugToDebugger"
0x1800281e6  call    cs:__imp_RegQueryValueExW
0x1800281ed  nop     dword ptr [rax+rax+00h]
0x1800281f2  test    eax, eax
0x1800281f4  jnz     short loc_180028209
0x1800281f6  cmp     [rsp+280h+Type], r14d
0x1800281fb  jnz     short loc_180028209
0x1800281fd  cmp     dword ptr [rsp+280h+Data], edi
0x180028201  setnz   al
0x180028204  mov     [rbx+21h], al
0x180028207  jmp     short loc_18002820D
0x180028209  mov     [rbx+21h], dil
0x18002820d  mov     rcx, [rsp+280h+hKey]; hKey
0x180028212  test    rcx, rcx
0x180028215  jz      short loc_180028223
0x180028217  call    cs:__imp_RegCloseKey
0x18002821e  nop     dword ptr [rax+rax+00h]
0x180028223  mov     eax, edi
0x180028225  mov     rcx, [rbp+180h+var_20]
0x18002822c  xor     rcx, rsp; StackCookie
0x18002822f  call    __security_check_cookie
0x180028234  lea     r11, [rsp+280h+var_10]
0x18002823c  mov     rbx, [r11+28h]
0x180028240  mov     rdi, [r11+30h]
0x180028244  mov     rsp, r11
0x180028247  pop     r15
0x180028249  pop     r14
0x18002824b  pop     rbp
0x18002824c  retn
```
