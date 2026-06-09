# DmDiagnosticsCollector::RecordDiagnosticsError(ushort const *,ushort const *,long,ushort const *,ushort const *)

- ea: `0x180008838`
- end: `0x180008bf2`
- name: `?RecordDiagnosticsError@DmDiagnosticsCollector@@SAJPEBG0J00@Z`
- size: `954`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005860`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180003b94`
- `0x180005c14`
- `0x180005c3c`
- `0x180006cb0`
- `0x18000768c`
- `0x180008838`
- `0x180008c38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800089ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008a3b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008aa5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008baa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800089ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008a3b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008aa5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008baa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008978`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008978`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008acc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008acc`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180008890`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180008890`

## pseudocode

```c
__int64 __fastcall DmDiagnosticsCollector::RecordDiagnosticsError(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        BYTE *lpData)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v9; // r9
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD cbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v22[264]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  *(_DWORD *)Data = a3;
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v9 = L"OSData\\Software\\Microsoft\\Provisioning\\Diagnostics";
  if ( !a2 )
  {
    if ( !IsStateSeparationEnabled )
      v9 = L"Software\\Microsoft\\Provisioning\\Diagnostics";
    v10 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v9, a1);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 97;
      goto LABEL_10;
    }
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v13 )
    {
      v14 = 110;
    }
    else
    {
      v13 = RegSetValueExW(hKey, L"Error", 0, 4u, Data, 4u);
      if ( v13 )
      {
        v14 = 113;
      }
      else
      {
        if ( !a4 )
          goto LABEL_36;
        *(_QWORD *)cbData = 0;
        v10 = StringCbLengthW(a4, 0xFFFFFFFE, (unsigned __int64 *)cbData);
        v11 = v10;
        if ( v10 < 0 )
        {
          v12 = 119;
          goto LABEL_10;
        }
        v13 = RegSetValueExW(hKey, L"Metadata1", 0, 1u, (const BYTE *)a4, cbData[0]);
        if ( v13 )
        {
          v14 = 120;
        }
        else
        {
LABEL_36:
          if ( !lpData )
            goto LABEL_26;
          *(_QWORD *)cbData = 0;
          v10 = StringCbLengthW((const unsigned __int16 *)lpData, 0xFFFFFFFE, (unsigned __int64 *)cbData);
          v11 = v10;
          if ( v10 < 0 )
          {
            v12 = 127;
            goto LABEL_10;
          }
          v13 = RegSetValueExW(hKey, L"Metadata2", 0, 1u, lpData, cbData[0]);
          if ( v13 )
          {
            v14 = 128;
          }
          else
          {
LABEL_26:
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            memset_0(v22, 0, 0x208u);
            dwOptions = SystemTime.wMonth;
            v10 = StringCchPrintfW(v22, 0x104u, L"%d-%02d-%02d %02d:%02d:%02d.%03d", SystemTime.wYear);
            v11 = v10;
            if ( v10 < 0 )
            {
              v12 = 144;
              goto LABEL_10;
            }
            *(_QWORD *)cbData = 0;
            v10 = StringCbLengthW(v22, 0xFFFFFFFE, (unsigned __int64 *)cbData);
            v11 = v10;
            if ( v10 < 0 )
            {
              v12 = 147;
              goto LABEL_10;
            }
            v13 = RegSetValueExW(hKey, L"Time", 0, 1u, (const BYTE *)v22, cbData[0]);
            if ( !v13 )
            {
              v11 = 0;
              goto LABEL_33;
            }
            v14 = 148;
          }
        }
      }
    }
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
            (const char *)v13,
            dwOptions);
    goto LABEL_33;
  }
  if ( !IsStateSeparationEnabled )
    v9 = L"Software\\Microsoft\\Provisioning\\Diagnostics";
  v10 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", v9, a1, a2);
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_11;
  v12 = 93;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
    (const char *)(unsigned int)v10,
    dwOptions);
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v11;
}

```

## disassembly

```asm
0x180008838  push    rbp
0x18000883a  push    rbx
0x18000883b  push    rsi
0x18000883c  push    rdi
0x18000883d  push    r12
0x18000883f  push    r14
0x180008841  lea     rbp, [rsp-3B8h]
0x180008849  sub     rsp, 4B8h
0x180008850  mov     rax, cs:__security_cookie
0x180008857  xor     rax, rsp
0x18000885a  mov     [rbp+3E0h+var_40], rax
0x180008861  mov     rsi, [rbp+3E0h+lpData]
0x180008868  mov     rbx, rdx
0x18000886b  mov     r14, rcx
0x18000886e  mov     dword ptr [rsp+4E0h+Data], r8d
0x180008873  xor     edx, edx; Val
0x180008875  mov     [rsp+4E0h+hKey], 0
0x18000887e  mov     r8d, 208h; Size
0x180008884  lea     rcx, [rbp+3E0h+SubKey]; void *
0x180008888  mov     rdi, r9
0x18000888b  call    memset_0
0x180008890  call    cs:__imp_RtlIsStateSeparationEnabled
0x180008897  nop     dword ptr [rax+rax+00h]
0x18000889c  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Provisioning\\Diag"...
0x1800088a3  lea     r9, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800088aa  test    rbx, rbx
0x1800088ad  jz      short loc_1800088E5
0x1800088af  test    al, al
0x1800088b1  mov     qword ptr [rsp+4E0h+samDesired], rbx
0x1800088b6  mov     qword ptr [rsp+4E0h+dwOptions], r14
0x1800088bb  lea     r8, aSSS; "%s\\%s\\%s"
0x1800088c2  cmovz   r9, rcx
0x1800088c6  mov     r14d, 104h
0x1800088cc  mov     edx, r14d; unsigned __int64
0x1800088cf  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x1800088d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088d8  mov     ebx, eax
0x1800088da  test    eax, eax
0x1800088dc  jns     short loc_18000892F
0x1800088de  mov     edx, 5Dh ; ']'
0x1800088e3  jmp     short loc_180008914
0x1800088e5  test    al, al
0x1800088e7  mov     qword ptr [rsp+4E0h+dwOptions], r14; int
0x1800088ec  mov     r14d, 104h
0x1800088f2  lea     r8, aSS; "%s\\%s"
0x1800088f9  cmovz   r9, rcx
0x1800088fd  mov     edx, r14d; unsigned __int64
0x180008900  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x180008904  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008909  mov     ebx, eax
0x18000890b  test    eax, eax
0x18000890d  jns     short loc_18000892F
0x18000890f  mov     edx, 61h ; 'a'; void *
0x180008914  mov     rcx, [rbp+3E8h]; this
0x18000891b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180008922  mov     r9d, eax; char *
0x180008925  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000892a  jmp     loc_180008BC6
0x18000892f  xor     edx, edx
0x180008931  lea     rcx, [rsp+4E0h+hKey]
0x180008936  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000893b  mov     [rsp+4E0h+lpdwDisposition], 0; lpdwDisposition
0x180008944  lea     rax, [rsp+4E0h+hKey]
0x180008949  mov     [rsp+4E0h+phkResult], rax; phkResult
0x18000894e  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x180008952  mov     [rsp+4E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000895b  xor     r9d, r9d; lpClass
0x18000895e  mov     [rsp+4E0h+samDesired], 0F003Fh; samDesired
0x180008966  xor     r8d, r8d; Reserved
0x180008969  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008970  mov     [rsp+4E0h+dwOptions], 0; unsigned int
0x180008978  call    cs:__imp_RegCreateKeyExW
0x18000897f  nop     dword ptr [rax+rax+00h]
0x180008984  test    eax, eax
0x180008986  jz      short loc_1800089AA
0x180008988  mov     edx, 6Eh ; 'n'; void *
0x18000898d  mov     rcx, [rbp+3E8h]; this
0x180008994  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000899b  mov     r9d, eax; char *
0x18000899e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800089a3  mov     ebx, eax
0x1800089a5  jmp     loc_180008BC6
0x1800089aa  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800089af  lea     rax, [rsp+4E0h+Data]
0x1800089b4  mov     r9d, 4; dwType
0x1800089ba  lea     rdx, ValueName; "Error"
0x1800089c1  mov     [rsp+4E0h+samDesired], r9d; cbData
0x1800089c6  xor     r8d, r8d; Reserved
0x1800089c9  mov     qword ptr [rsp+4E0h+dwOptions], rax; lpData
0x1800089ce  call    cs:__imp_RegSetValueExW
0x1800089d5  nop     dword ptr [rax+rax+00h]
0x1800089da  test    eax, eax
0x1800089dc  jz      short loc_1800089E5
0x1800089de  mov     edx, 71h ; 'q'
0x1800089e3  jmp     short loc_18000898D
0x1800089e5  mov     r12d, 0FFFFFFFEh
0x1800089eb  test    rdi, rdi
0x1800089ee  jz      short loc_180008A55
0x1800089f0  lea     r8, [rsp+4E0h+cbData]; unsigned __int64 *
0x1800089f5  mov     qword ptr [rsp+4E0h+cbData], 0
0x1800089fe  mov     edx, r12d; unsigned __int64
0x180008a01  mov     rcx, rdi; unsigned __int16 *
0x180008a04  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180008a09  mov     ebx, eax
0x180008a0b  test    eax, eax
0x180008a0d  jns     short loc_180008A19
0x180008a0f  mov     edx, 77h ; 'w'
0x180008a14  jmp     loc_180008914
0x180008a19  mov     eax, [rsp+4E0h+cbData]
0x180008a1d  lea     rdx, aMetadata1; "Metadata1"
0x180008a24  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180008a29  mov     r9d, 1; dwType
0x180008a2f  mov     [rsp+4E0h+samDesired], eax; cbData
0x180008a33  xor     r8d, r8d; Reserved
0x180008a36  mov     qword ptr [rsp+4E0h+dwOptions], rdi; lpData
0x180008a3b  call    cs:__imp_RegSetValueExW
0x180008a42  nop     dword ptr [rax+rax+00h]
0x180008a47  test    eax, eax
0x180008a49  jz      short loc_180008A55
0x180008a4b  mov     edx, 78h ; 'x'
0x180008a50  jmp     loc_18000898D
0x180008a55  test    rsi, rsi
0x180008a58  jz      short loc_180008ABF
0x180008a5a  lea     r8, [rsp+4E0h+cbData]; unsigned __int64 *
0x180008a5f  mov     qword ptr [rsp+4E0h+cbData], 0
0x180008a68  mov     rdx, r12; unsigned __int64
0x180008a6b  mov     rcx, rsi; unsigned __int16 *
0x180008a6e  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180008a73  mov     ebx, eax
0x180008a75  test    eax, eax
0x180008a77  jns     short loc_180008A83
0x180008a79  mov     edx, 7Fh
0x180008a7e  jmp     loc_180008914
0x180008a83  mov     eax, [rsp+4E0h+cbData]
0x180008a87  lea     rdx, aMetadata2; "Metadata2"
0x180008a8e  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180008a93  mov     r9d, 1; dwType
0x180008a99  mov     [rsp+4E0h+samDesired], eax; cbData
0x180008a9d  xor     r8d, r8d; Reserved
0x180008aa0  mov     qword ptr [rsp+4E0h+dwOptions], rsi; lpData
0x180008aa5  call    cs:__imp_RegSetValueExW
0x180008aac  nop     dword ptr [rax+rax+00h]
0x180008ab1  test    eax, eax
0x180008ab3  jz      short loc_180008ABF
0x180008ab5  mov     edx, 80h
0x180008aba  jmp     loc_18000898D
0x180008abf  xorps   xmm0, xmm0
0x180008ac2  lea     rcx, [rsp+4E0h+SystemTime]; lpSystemTime
0x180008ac7  movups  xmmword ptr [rsp+4E0h+SystemTime.wYear], xmm0
0x180008acc  call    cs:__imp_GetSystemTime
0x180008ad3  nop     dword ptr [rax+rax+00h]
0x180008ad8  xor     edx, edx; Val
0x180008ada  lea     rcx, [rbp+3E0h+var_250]; void *
0x180008ae1  mov     r8d, 208h; Size
0x180008ae7  call    memset_0
0x180008aec  movzx   ecx, [rsp+4E0h+SystemTime.wSecond]
0x180008af1  mov     rdx, r14; unsigned __int64
0x180008af4  movzx   r8d, [rsp+4E0h+SystemTime.wMinute]
0x180008afa  movzx   eax, [rsp+4E0h+SystemTime.wMilliseconds]
0x180008aff  movzx   r10d, [rsp+4E0h+SystemTime.wHour]
0x180008b05  movzx   r11d, [rsp+4E0h+SystemTime.wDay]
0x180008b0b  movzx   ebx, [rsp+4E0h+SystemTime.wMonth]
0x180008b10  movzx   r9d, [rsp+4E0h+SystemTime.wYear]
0x180008b16  mov     [rsp+4E0h+var_498], eax
0x180008b1a  mov     dword ptr [rsp+4E0h+lpdwDisposition], ecx
0x180008b1e  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180008b25  mov     dword ptr [rsp+4E0h+phkResult], r8d
0x180008b2a  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d.%03d"
0x180008b31  mov     dword ptr [rsp+4E0h+lpSecurityAttributes], r10d
0x180008b36  mov     [rsp+4E0h+samDesired], r11d
0x180008b3b  mov     [rsp+4E0h+dwOptions], ebx
0x180008b3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008b44  mov     ebx, eax
0x180008b46  test    eax, eax
0x180008b48  jns     short loc_180008B54
0x180008b4a  mov     edx, 90h
0x180008b4f  jmp     loc_180008914
0x180008b54  lea     r8, [rsp+4E0h+cbData]; unsigned __int64 *
0x180008b59  mov     qword ptr [rsp+4E0h+cbData], 0
0x180008b62  mov     rdx, r12; unsigned __int64
0x180008b65  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180008b6c  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180008b71  mov     ebx, eax
0x180008b73  test    eax, eax
0x180008b75  jns     short loc_180008B81
0x180008b77  mov     edx, 93h
0x180008b7c  jmp     loc_180008914
0x180008b81  mov     eax, [rsp+4E0h+cbData]
0x180008b85  lea     rdx, aTime; "Time"
0x180008b8c  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180008b91  mov     r9d, 1; dwType
0x180008b97  mov     [rsp+4E0h+samDesired], eax; cbData
0x180008b9b  xor     r8d, r8d; Reserved
0x180008b9e  lea     rax, [rbp+3E0h+var_250]
0x180008ba5  mov     qword ptr [rsp+4E0h+dwOptions], rax; lpData
0x180008baa  call    cs:__imp_RegSetValueExW
0x180008bb1  nop     dword ptr [rax+rax+00h]
0x180008bb6  test    eax, eax
0x180008bb8  jz      short loc_180008BC4
0x180008bba  mov     edx, 94h
0x180008bbf  jmp     loc_18000898D
0x180008bc4  xor     ebx, ebx
0x180008bc6  lea     rcx, [rsp+4E0h+hKey]
0x180008bcb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180008bd0  mov     eax, ebx
0x180008bd2  mov     rcx, [rbp+3E0h+var_40]
0x180008bd9  xor     rcx, rsp; StackCookie
0x180008bdc  call    __security_check_cookie
0x180008be1  add     rsp, 4B8h
0x180008be8  pop     r14
0x180008bea  pop     r12
0x180008bec  pop     rdi
0x180008bed  pop     rsi
0x180008bee  pop     rbx
0x180008bef  pop     rbp
0x180008bf0  retn
```
