# DmDiagnosticsCollector::RecordDiagnosticsError(ushort const *,ushort const *,long,ushort const *,ushort const *)

- ea: `0x180008448`
- end: `0x1800087d7`
- name: `?RecordDiagnosticsError@DmDiagnosticsCollector@@SAJPEBG0J00@Z`
- size: `911`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005690`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180003b88`
- `0x180005a14`
- `0x180005a38`
- `0x180006a30`
- `0x1800073bc`
- `0x180008448`
- `0x180008818`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800085d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008639`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000869d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008796`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800085d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008639`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000869d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008796`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008582`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008582`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800086be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800086be`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800084a0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800084a0`

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
0x180008448  push    rbp
0x18000844a  push    rbx
0x18000844b  push    rsi
0x18000844c  push    rdi
0x18000844d  push    r12
0x18000844f  push    r14
0x180008451  lea     rbp, [rsp-3B8h]
0x180008459  sub     rsp, 4B8h
0x180008460  mov     rax, cs:__security_cookie
0x180008467  xor     rax, rsp
0x18000846a  mov     [rbp+3E0h+var_40], rax
0x180008471  mov     rsi, [rbp+3E0h+lpData]
0x180008478  mov     rbx, rdx
0x18000847b  mov     r14, rcx
0x18000847e  mov     dword ptr [rsp+4E0h+Data], r8d
0x180008483  xor     edx, edx; Val
0x180008485  mov     [rsp+4E0h+hKey], 0
0x18000848e  mov     r8d, 208h; Size
0x180008494  lea     rcx, [rbp+3E0h+SubKey]; void *
0x180008498  mov     rdi, r9
0x18000849b  call    memset_0
0x1800084a0  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800084a6  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Provisioning\\Diag"...
0x1800084ad  lea     r9, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800084b4  test    rbx, rbx
0x1800084b7  jz      short loc_1800084EF
0x1800084b9  test    al, al
0x1800084bb  mov     qword ptr [rsp+4E0h+samDesired], rbx
0x1800084c0  mov     qword ptr [rsp+4E0h+dwOptions], r14
0x1800084c5  lea     r8, aSSS; "%s\\%s\\%s"
0x1800084cc  cmovz   r9, rcx
0x1800084d0  mov     r14d, 104h
0x1800084d6  mov     edx, r14d; unsigned __int64
0x1800084d9  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x1800084dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800084e2  mov     ebx, eax
0x1800084e4  test    eax, eax
0x1800084e6  jns     short loc_180008539
0x1800084e8  mov     edx, 5Dh ; ']'
0x1800084ed  jmp     short loc_18000851E
0x1800084ef  test    al, al
0x1800084f1  mov     qword ptr [rsp+4E0h+dwOptions], r14; int
0x1800084f6  mov     r14d, 104h
0x1800084fc  lea     r8, aSS; "%s\\%s"
0x180008503  cmovz   r9, rcx
0x180008507  mov     edx, r14d; unsigned __int64
0x18000850a  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x18000850e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008513  mov     ebx, eax
0x180008515  test    eax, eax
0x180008517  jns     short loc_180008539
0x180008519  mov     edx, 61h ; 'a'; void *
0x18000851e  mov     rcx, [rbp+3E8h]; this
0x180008525  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000852c  mov     r9d, eax; char *
0x18000852f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008534  jmp     loc_1800087AC
0x180008539  xor     edx, edx
0x18000853b  lea     rcx, [rsp+4E0h+hKey]
0x180008540  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180008545  mov     [rsp+4E0h+lpdwDisposition], 0; lpdwDisposition
0x18000854e  lea     rax, [rsp+4E0h+hKey]
0x180008553  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180008558  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x18000855c  mov     [rsp+4E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180008565  xor     r9d, r9d; lpClass
0x180008568  mov     [rsp+4E0h+samDesired], 0F003Fh; samDesired
0x180008570  xor     r8d, r8d; Reserved
0x180008573  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000857a  mov     [rsp+4E0h+dwOptions], 0; unsigned int
0x180008582  call    cs:__imp_RegCreateKeyExW
0x180008588  test    eax, eax
0x18000858a  jz      short loc_1800085AE
0x18000858c  mov     edx, 6Eh ; 'n'; void *
0x180008591  mov     rcx, [rbp+3E8h]; this
0x180008598  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000859f  mov     r9d, eax; char *
0x1800085a2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800085a7  mov     ebx, eax
0x1800085a9  jmp     loc_1800087AC
0x1800085ae  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800085b3  lea     rax, [rsp+4E0h+Data]
0x1800085b8  mov     r9d, 4; dwType
0x1800085be  lea     rdx, ValueName; "Error"
0x1800085c5  mov     [rsp+4E0h+samDesired], r9d; cbData
0x1800085ca  xor     r8d, r8d; Reserved
0x1800085cd  mov     qword ptr [rsp+4E0h+dwOptions], rax; lpData
0x1800085d2  call    cs:__imp_RegSetValueExW
0x1800085d8  test    eax, eax
0x1800085da  jz      short loc_1800085E3
0x1800085dc  mov     edx, 71h ; 'q'
0x1800085e1  jmp     short loc_180008591
0x1800085e3  mov     r12d, 0FFFFFFFEh
0x1800085e9  test    rdi, rdi
0x1800085ec  jz      short loc_18000864D
0x1800085ee  lea     r8, [rsp+4E0h+cbData]; unsigned __int64 *
0x1800085f3  mov     qword ptr [rsp+4E0h+cbData], 0
0x1800085fc  mov     edx, r12d; unsigned __int64
0x1800085ff  mov     rcx, rdi; unsigned __int16 *
0x180008602  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180008607  mov     ebx, eax
0x180008609  test    eax, eax
0x18000860b  jns     short loc_180008617
0x18000860d  mov     edx, 77h ; 'w'
0x180008612  jmp     loc_18000851E
0x180008617  mov     eax, [rsp+4E0h+cbData]
0x18000861b  lea     rdx, aMetadata1; "Metadata1"
0x180008622  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180008627  mov     r9d, 1; dwType
0x18000862d  mov     [rsp+4E0h+samDesired], eax; cbData
0x180008631  xor     r8d, r8d; Reserved
0x180008634  mov     qword ptr [rsp+4E0h+dwOptions], rdi; lpData
0x180008639  call    cs:__imp_RegSetValueExW
0x18000863f  test    eax, eax
0x180008641  jz      short loc_18000864D
0x180008643  mov     edx, 78h ; 'x'
0x180008648  jmp     loc_180008591
0x18000864d  test    rsi, rsi
0x180008650  jz      short loc_1800086B1
0x180008652  lea     r8, [rsp+4E0h+cbData]; unsigned __int64 *
0x180008657  mov     qword ptr [rsp+4E0h+cbData], 0
0x180008660  mov     rdx, r12; unsigned __int64
0x180008663  mov     rcx, rsi; unsigned __int16 *
0x180008666  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000866b  mov     ebx, eax
0x18000866d  test    eax, eax
0x18000866f  jns     short loc_18000867B
0x180008671  mov     edx, 7Fh
0x180008676  jmp     loc_18000851E
0x18000867b  mov     eax, [rsp+4E0h+cbData]
0x18000867f  lea     rdx, aMetadata2; "Metadata2"
0x180008686  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18000868b  mov     r9d, 1; dwType
0x180008691  mov     [rsp+4E0h+samDesired], eax; cbData
0x180008695  xor     r8d, r8d; Reserved
0x180008698  mov     qword ptr [rsp+4E0h+dwOptions], rsi; lpData
0x18000869d  call    cs:__imp_RegSetValueExW
0x1800086a3  test    eax, eax
0x1800086a5  jz      short loc_1800086B1
0x1800086a7  mov     edx, 80h
0x1800086ac  jmp     loc_180008591
0x1800086b1  xorps   xmm0, xmm0
0x1800086b4  lea     rcx, [rsp+4E0h+SystemTime]; lpSystemTime
0x1800086b9  movups  xmmword ptr [rsp+4E0h+SystemTime.wYear], xmm0
0x1800086be  call    cs:__imp_GetSystemTime
0x1800086c4  xor     edx, edx; Val
0x1800086c6  lea     rcx, [rbp+3E0h+var_250]; void *
0x1800086cd  mov     r8d, 208h; Size
0x1800086d3  call    memset_0
0x1800086d8  movzx   ecx, [rsp+4E0h+SystemTime.wSecond]
0x1800086dd  mov     rdx, r14; unsigned __int64
0x1800086e0  movzx   r8d, [rsp+4E0h+SystemTime.wMinute]
0x1800086e6  movzx   eax, [rsp+4E0h+SystemTime.wMilliseconds]
0x1800086eb  movzx   r10d, [rsp+4E0h+SystemTime.wHour]
0x1800086f1  movzx   r11d, [rsp+4E0h+SystemTime.wDay]
0x1800086f7  movzx   ebx, [rsp+4E0h+SystemTime.wMonth]
0x1800086fc  movzx   r9d, [rsp+4E0h+SystemTime.wYear]
0x180008702  mov     [rsp+4E0h+var_498], eax
0x180008706  mov     dword ptr [rsp+4E0h+lpdwDisposition], ecx
0x18000870a  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180008711  mov     dword ptr [rsp+4E0h+phkResult], r8d
0x180008716  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d.%03d"
0x18000871d  mov     dword ptr [rsp+4E0h+lpSecurityAttributes], r10d
0x180008722  mov     [rsp+4E0h+samDesired], r11d
0x180008727  mov     [rsp+4E0h+dwOptions], ebx
0x18000872b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008730  mov     ebx, eax
0x180008732  test    eax, eax
0x180008734  jns     short loc_180008740
0x180008736  mov     edx, 90h
0x18000873b  jmp     loc_18000851E
0x180008740  lea     r8, [rsp+4E0h+cbData]; unsigned __int64 *
0x180008745  mov     qword ptr [rsp+4E0h+cbData], 0
0x18000874e  mov     rdx, r12; unsigned __int64
0x180008751  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180008758  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000875d  mov     ebx, eax
0x18000875f  test    eax, eax
0x180008761  jns     short loc_18000876D
0x180008763  mov     edx, 93h
0x180008768  jmp     loc_18000851E
0x18000876d  mov     eax, [rsp+4E0h+cbData]
0x180008771  lea     rdx, aTime; "Time"
0x180008778  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18000877d  mov     r9d, 1; dwType
0x180008783  mov     [rsp+4E0h+samDesired], eax; cbData
0x180008787  xor     r8d, r8d; Reserved
0x18000878a  lea     rax, [rbp+3E0h+var_250]
0x180008791  mov     qword ptr [rsp+4E0h+dwOptions], rax; lpData
0x180008796  call    cs:__imp_RegSetValueExW
0x18000879c  test    eax, eax
0x18000879e  jz      short loc_1800087AA
0x1800087a0  mov     edx, 94h
0x1800087a5  jmp     loc_180008591
0x1800087aa  xor     ebx, ebx
0x1800087ac  lea     rcx, [rsp+4E0h+hKey]
0x1800087b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800087b6  mov     eax, ebx
0x1800087b8  mov     rcx, [rbp+3E0h+var_40]
0x1800087bf  xor     rcx, rsp; StackCookie
0x1800087c2  call    __security_check_cookie
0x1800087c7  add     rsp, 4B8h
0x1800087ce  pop     r14
0x1800087d0  pop     r12
0x1800087d2  pop     rdi
0x1800087d3  pop     rsi
0x1800087d4  pop     rbx
0x1800087d5  pop     rbp
0x1800087d6  retn
```
