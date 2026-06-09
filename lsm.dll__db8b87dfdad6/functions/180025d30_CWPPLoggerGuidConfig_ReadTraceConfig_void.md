# CWPPLoggerGuidConfig::ReadTraceConfig(void)

- ea: `0x180025d30`
- end: `0x180026161`
- name: `?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ`
- size: `1073`
- prototype: `__int64 __fastcall(CWPPLoggerGuidConfig *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d454`
- `0x18007f274`
- `0x18007f4a0`

## callees

- `0x1800074c0`
- `0x180025d30`
- `0x180026168`
- `0x1800261f4`
- `0x18004b460`
- `0x18004bf44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025db9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025db9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025ece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025fc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026026`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026064`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026106`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025ece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025fc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026026`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026064`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026106`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026131`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026131`

## string_xrefs

- `0x180025dcd`: `error %#x: RegOpenKeyEx(%S) failed`

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
0x180025d30  mov     [rsp-8+arg_8], rbx
0x180025d35  mov     [rsp-8+arg_10], rdi
0x180025d3a  push    rbp
0x180025d3b  push    r14
0x180025d3d  push    r15
0x180025d3f  lea     rbp, [rsp-170h]
0x180025d47  sub     rsp, 270h
0x180025d4e  mov     rax, cs:__security_cookie
0x180025d55  xor     rax, rsp
0x180025d58  mov     [rbp+180h+var_20], rax
0x180025d5f  mov     rbx, rcx
0x180025d62  mov     [rsp+280h+Type], 0
0x180025d6a  mov     r15d, 208h
0x180025d70  mov     dword ptr [rsp+280h+Data], 0
0x180025d78  mov     r8d, r15d; Size
0x180025d7b  mov     [rsp+280h+cbData], 0
0x180025d83  xor     edx, edx; Val
0x180025d85  mov     [rsp+280h+hKey], 0
0x180025d8e  lea     rcx, [rsp+280h+ValueName]; void *
0x180025d93  call    memset_0
0x180025d98  lea     rax, [rsp+280h+hKey]
0x180025d9d  mov     r9d, 20019h; samDesired
0x180025da3  xor     r8d, r8d; ulOptions
0x180025da6  mov     [rsp+280h+phkResult], rax; phkResult
0x180025dab  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180025db2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025db9  call    cs:__imp_RegOpenKeyExW
0x180025dbf  mov     edi, eax
0x180025dc1  test    eax, eax
0x180025dc3  jz      short loc_180025DF4
0x180025dc5  lea     r9, [rsp+280h+ValueName]
0x180025dca  mov     r8d, eax
0x180025dcd  lea     rdx, aErrorXRegopenk; "error %#x: RegOpenKeyEx(%S) failed"
0x180025dd4  mov     ecx, 1; int
0x180025dd9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180025dde  test    edi, edi
0x180025de0  jle     loc_180026127
0x180025de6  movzx   edi, di
0x180025de9  or      edi, 80070000h
0x180025def  jmp     loc_180026127
0x180025df4  mov     r9, [rbx+10h]
0x180025df8  lea     r8, aDebugS; "Debug%s"
0x180025dff  mov     rdx, r15; unsigned __int64
0x180025e02  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180025e07  xor     edi, edi
0x180025e09  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025e0e  mov     rcx, [rsp+280h+hKey]; hKey
0x180025e13  lea     rax, [rsp+280h+cbData]
0x180025e18  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180025e1d  lea     r14d, [rdi+4]
0x180025e21  lea     rax, [rsp+280h+Data]
0x180025e26  mov     [rsp+280h+cbData], r14d
0x180025e2b  lea     r9, [rsp+280h+Type]; lpType
0x180025e30  mov     [rsp+280h+phkResult], rax; lpData
0x180025e35  xor     r8d, r8d; lpReserved
0x180025e38  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180025e3d  call    cs:__imp_RegQueryValueExW
0x180025e43  test    eax, eax
0x180025e45  jnz     short loc_180025E56
0x180025e47  cmp     [rsp+280h+Type], r14d
0x180025e4c  jnz     short loc_180025E56
0x180025e4e  xor     ecx, ecx
0x180025e50  cmp     dword ptr [rsp+280h+Data], ecx
0x180025e54  jmp     short loc_180025E9B
0x180025e56  mov     rcx, [rsp+280h+hKey]; hKey
0x180025e5b  lea     rax, [rsp+280h+cbData]
0x180025e60  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180025e65  lea     r9, [rsp+280h+Type]; lpType
0x180025e6a  lea     rax, [rsp+280h+Data]
0x180025e6f  mov     [rsp+280h+cbData], r14d
0x180025e74  xor     r8d, r8d; lpReserved
0x180025e77  mov     [rsp+280h+phkResult], rax; lpData
0x180025e7c  lea     rdx, aDebug; "Debug"
0x180025e83  call    cs:__imp_RegQueryValueExW
0x180025e89  test    eax, eax
0x180025e8b  jnz     short loc_180025E94
0x180025e8d  cmp     [rsp+280h+Type], r14d
0x180025e92  jz      short loc_180025E4E
0x180025e94  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x180025e99  test    eax, eax
0x180025e9b  setnz   cl
0x180025e9e  lea     rax, [rsp+280h+cbData]
0x180025ea3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180025ea8  lea     r9, [rsp+280h+Type]; lpType
0x180025ead  mov     [rbx+20h], cl
0x180025eb0  lea     rax, [rsp+280h+Data]
0x180025eb5  mov     rcx, [rsp+280h+hKey]; hKey
0x180025eba  lea     rdx, aCapturestacktr; "CaptureStackTrace"
0x180025ec1  xor     r8d, r8d; lpReserved
0x180025ec4  mov     [rsp+280h+phkResult], rax; lpData
0x180025ec9  mov     [rsp+280h+cbData], r14d
0x180025ece  call    cs:__imp_RegQueryValueExW
0x180025ed4  test    eax, eax
0x180025ed6  jnz     short loc_180025EE5
0x180025ed8  cmp     [rsp+280h+Type], r14d
0x180025edd  jnz     short loc_180025EE5
0x180025edf  mov     eax, dword ptr [rsp+280h+Data]
0x180025ee3  jmp     short loc_180025EEB
0x180025ee5  xor     eax, eax
0x180025ee7  mov     dword ptr [rsp+280h+Data], eax
0x180025eeb  mov     r9, [rbx+10h]
0x180025eef  lea     r8, aDebugSflags; "Debug%sFlags"
0x180025ef6  mov     rdx, r15; unsigned __int64
0x180025ef9  mov     cs:?g_bCaptureObjectStackTrace@@3HA, eax; int g_bCaptureObjectStackTrace
0x180025eff  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180025f04  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025f09  mov     rcx, [rsp+280h+hKey]; hKey
0x180025f0e  lea     rax, [rsp+280h+cbData]
0x180025f13  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180025f18  lea     r9, [rsp+280h+Type]; lpType
0x180025f1d  lea     rax, [rsp+280h+Data]
0x180025f22  mov     [rsp+280h+cbData], r14d
0x180025f27  xor     r8d, r8d; lpReserved
0x180025f2a  mov     [rsp+280h+phkResult], rax; lpData
0x180025f2f  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180025f34  call    cs:__imp_RegQueryValueExW
0x180025f3a  test    eax, eax
0x180025f3c  jnz     short loc_180025F4B
0x180025f3e  cmp     [rsp+280h+Type], r14d
0x180025f43  jnz     short loc_180025F4B
0x180025f45  mov     eax, dword ptr [rsp+280h+Data]
0x180025f49  jmp     short loc_180025F92
0x180025f4b  mov     rcx, [rsp+280h+hKey]; hKey
0x180025f50  lea     rax, [rsp+280h+cbData]
0x180025f55  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180025f5a  lea     r9, [rsp+280h+Type]; lpType
0x180025f5f  lea     rax, [rsp+280h+Data]
0x180025f64  mov     [rsp+280h+cbData], r14d
0x180025f69  xor     r8d, r8d; lpReserved
0x180025f6c  mov     [rsp+280h+phkResult], rax; lpData
0x180025f71  lea     rdx, aDebugflags; "DebugFlags"
0x180025f78  call    cs:__imp_RegQueryValueExW
0x180025f7e  test    eax, eax
0x180025f80  jnz     short loc_180025F8D
0x180025f82  mov     eax, dword ptr [rsp+280h+Data]
0x180025f86  cmp     [rsp+280h+Type], r14d
0x180025f8b  jz      short loc_180025F92
0x180025f8d  mov     eax, 0FFFFFFFEh
0x180025f92  mov     rcx, [rsp+280h+hKey]; hKey
0x180025f97  lea     r9, [rsp+280h+Type]; lpType
0x180025f9c  mov     [rbx+18h], eax
0x180025f9f  lea     rdx, aDebugflagsex; "DebugFlagsEx"
0x180025fa6  mov     cs:?g_DebugTraceComponent@@3KA, eax; ulong g_DebugTraceComponent
0x180025fac  xor     r8d, r8d; lpReserved
0x180025faf  lea     rax, [rsp+280h+cbData]
0x180025fb4  mov     [rsp+280h+cbData], r14d
0x180025fb9  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180025fbe  lea     rax, [rsp+280h+Data]
0x180025fc3  mov     [rsp+280h+phkResult], rax; lpData
0x180025fc8  call    cs:__imp_RegQueryValueExW
0x180025fce  test    eax, eax
0x180025fd0  jnz     short loc_180025FE3
0x180025fd2  cmp     [rsp+280h+Type], r14d
0x180025fd7  jnz     short loc_180025FE3
0x180025fd9  mov     eax, dword ptr [rsp+280h+Data]
0x180025fdd  mov     cs:?g_DebugFlagsEx@@3KA, eax; ulong g_DebugFlagsEx
0x180025fe3  mov     r9, [rbx+10h]
0x180025fe7  lea     r8, aDebugSlevel; "Debug%sLevel"
0x180025fee  mov     rdx, r15; unsigned __int64
0x180025ff1  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180025ff6  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025ffb  mov     rcx, [rsp+280h+hKey]; hKey
0x180026000  lea     rax, [rsp+280h+cbData]
0x180026005  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002600a  lea     r9, [rsp+280h+Type]; lpType
0x18002600f  lea     rax, [rsp+280h+Data]
0x180026014  mov     [rsp+280h+cbData], r14d
0x180026019  xor     r8d, r8d; lpReserved
0x18002601c  mov     [rsp+280h+phkResult], rax; lpData
0x180026021  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180026026  call    cs:__imp_RegQueryValueExW
0x18002602c  test    eax, eax
0x18002602e  jnz     short loc_180026037
0x180026030  cmp     [rsp+280h+Type], r14d
0x180026035  jz      short loc_180026075
0x180026037  mov     rcx, [rsp+280h+hKey]; hKey
0x18002603c  lea     rax, [rsp+280h+cbData]
0x180026041  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180026046  lea     r9, [rsp+280h+Type]; lpType
0x18002604b  lea     rax, [rsp+280h+Data]
0x180026050  mov     [rsp+280h+cbData], r14d
0x180026055  xor     r8d, r8d; lpReserved
0x180026058  mov     [rsp+280h+phkResult], rax; lpData
0x18002605d  lea     rdx, aDebuglevel; "DebugLevel"
0x180026064  call    cs:__imp_RegQueryValueExW
0x18002606a  test    eax, eax
0x18002606c  jnz     short loc_18002607E
0x18002606e  cmp     [rsp+280h+Type], r14d
0x180026073  jnz     short loc_18002607E
0x180026075  mov     eax, dword ptr [rsp+280h+Data]
0x180026079  mov     [rbx+1Ch], eax
0x18002607c  jmp     short loc_180026085
0x18002607e  mov     dword ptr [rbx+1Ch], 40BEh
0x180026085  mov     r9, [rbx+10h]
0x180026089  lea     r8, aDebugStodebugg; "Debug%sToDebugger"
0x180026090  mov     rdx, r15; unsigned __int64
0x180026093  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180026098  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002609d  mov     rcx, [rsp+280h+hKey]; hKey
0x1800260a2  lea     rax, [rsp+280h+cbData]
0x1800260a7  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800260ac  lea     r9, [rsp+280h+Type]; lpType
0x1800260b1  lea     rax, [rsp+280h+Data]
0x1800260b6  mov     [rsp+280h+cbData], r14d
0x1800260bb  xor     r8d, r8d; lpReserved
0x1800260be  mov     [rsp+280h+phkResult], rax; lpData
0x1800260c3  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x1800260c8  call    cs:__imp_RegQueryValueExW
0x1800260ce  test    eax, eax
0x1800260d0  jnz     short loc_1800260D9
0x1800260d2  cmp     [rsp+280h+Type], r14d
0x1800260d7  jz      short loc_180026117
0x1800260d9  mov     rcx, [rsp+280h+hKey]; hKey
0x1800260de  lea     rax, [rsp+280h+cbData]
0x1800260e3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800260e8  lea     r9, [rsp+280h+Type]; lpType
0x1800260ed  lea     rax, [rsp+280h+Data]
0x1800260f2  mov     [rsp+280h+cbData], r14d
0x1800260f7  xor     r8d, r8d; lpReserved
0x1800260fa  mov     [rsp+280h+phkResult], rax; lpData
0x1800260ff  lea     rdx, aDebugtodebugge; "DebugToDebugger"
0x180026106  call    cs:__imp_RegQueryValueExW
0x18002610c  test    eax, eax
0x18002610e  jnz     short loc_180026123
0x180026110  cmp     [rsp+280h+Type], r14d
0x180026115  jnz     short loc_180026123
0x180026117  cmp     dword ptr [rsp+280h+Data], edi
0x18002611b  setnz   al
0x18002611e  mov     [rbx+21h], al
0x180026121  jmp     short loc_180026127
0x180026123  mov     [rbx+21h], dil
0x180026127  mov     rcx, [rsp+280h+hKey]; hKey
0x18002612c  test    rcx, rcx
0x18002612f  jz      short loc_180026137
0x180026131  call    cs:__imp_RegCloseKey
0x180026137  mov     eax, edi
0x180026139  mov     rcx, [rbp+180h+var_20]
0x180026140  xor     rcx, rsp; StackCookie
0x180026143  call    __security_check_cookie
0x180026148  lea     r11, [rsp+280h+var_10]
0x180026150  mov     rbx, [r11+28h]
0x180026154  mov     rdi, [r11+30h]
0x180026158  mov     rsp, r11
0x18002615b  pop     r15
0x18002615d  pop     r14
0x18002615f  pop     rbp
0x180026160  retn
```
