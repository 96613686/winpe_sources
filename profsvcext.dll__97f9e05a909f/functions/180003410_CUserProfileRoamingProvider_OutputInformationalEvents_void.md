# CUserProfileRoamingProvider::OutputInformationalEvents(void)

- ea: `0x180003410`
- end: `0x1800038d6`
- name: `?OutputInformationalEvents@CUserProfileRoamingProvider@@UEAAJXZ`
- size: `1222`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003410`
- `0x180005234`
- `0x180005424`
- `0x180005960`
- `0x180006a9c`
- `0x18000a520`
- `0x18000aef8`
- `0x18000f530`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003470`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180003458`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180003458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003790`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003790`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800034b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800034b4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000368e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800037f2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000368e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800037f2`

## string_xrefs

- `0x1800036ea`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180003746`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18000384c`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800038b9`: `Temporary`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::OutputInformationalEvents(CUserProfileRoamingProvider *this)
{
  const wchar_t *v2; // rbx
  signed int LastError; // eax
  unsigned int v4; // edi
  bool v5; // r14
  const wchar_t *v6; // rdi
  const wchar_t *v7; // rdx
  int v8; // r8d
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  int v14; // eax
  unsigned int v15; // ebx
  void *v16; // rdi
  HANDLE ProcessHeap; // rax
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[3]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v27[3]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+90h] [rbp-70h] BYREF
  __int16 v30; // [rsp+1A8h] [rbp+A8h]
  _BYTE v31[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  const wchar_t *v32; // [rsp+1C0h] [rbp+C0h]
  int v33; // [rsp+1C8h] [rbp+C8h]
  int v34; // [rsp+1CCh] [rbp+CCh]
  const wchar_t *v35; // [rsp+1D0h] [rbp+D0h]
  int v36; // [rsp+1D8h] [rbp+D8h]
  int v37; // [rsp+1DCh] [rbp+DCh]
  const wchar_t *v38; // [rsp+1E0h] [rbp+E0h]
  int v39; // [rsp+1E8h] [rbp+E8h]
  int v40; // [rsp+1ECh] [rbp+ECh]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  v2 = L"Regular";
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( (v30 & 0x10) != 0 && (v30 & 0x100) == 0 )
    {
      v6 = L"RDS";
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)v4,
        phkResult);
      return v4;
    }
  }
  hKey[0] = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server",
          0,
          0x20019u,
          hKey) )
  {
    FileTime.dwLowDateTime = 0;
    cbData = 4;
    v5 = RegQueryValueExW(hKey[0], L"RDVirtualizationPool", 0, 0, (LPBYTE)&FileTime, &cbData) != 2;
    RegCloseKey(hKey[0]);
  }
  v6 = L"Regular";
  if ( v5 )
    v6 = L"VDI";
LABEL_9:
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x40000) != 0 )
  {
    v2 = L"Super-Mandatory";
    goto LABEL_13;
  }
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 1) != 0 )
  {
    v2 = L"Mandatory";
LABEL_13:
    if ( (*(char (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) < 0
      || ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x800) != 0 )
    {
      v2 = L"Temporary";
    }
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    {
      v7 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( v6[v10] );
      v32 = v6;
      v33 = 2 * v10 + 2;
      v34 = 0;
      if ( v7 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v7[v11] );
        v12 = 2 * v11 + 2;
      }
      else
      {
        v12 = 10;
        v7 = L"NULL";
      }
      v35 = v7;
      v36 = v12;
      v37 = 0;
      do
        ++v9;
      while ( v2[v9] );
      v38 = v2;
      v39 = 2 * v9 + 2;
      v40 = 0;
      McGenEventWrite_EtwEventWriteTransfer(v39, (unsigned int)"C", v8, 4, (__int64)v31);
    }
    return 0;
  }
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x10) == 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 8) == 0 )
  {
    goto LABEL_13;
  }
  FileTime = 0;
  (*(void (__fastcall **)(_QWORD, FILETIME *))(**((_QWORD **)this + 1) + 136LL))(*((_QWORD *)this + 1), &FileTime);
  *(_OWORD *)hKey = 0;
  FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)hKey);
  memset(lpMem, 0, sizeof(lpMem));
  phkResulta = HIWORD(hKey[0]);
  v14 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          lpMem,
          L"Year: %d, Month %d, Day %d, Hour %d, Minute %d",
          LOWORD(hKey[0]),
          WORD1(hKey[0]));
  v15 = v14;
  if ( v14 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, FILETIME *))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), &FileTime);
    FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)hKey);
    memset(v27, 0, sizeof(v27));
    phkResultb = HIWORD(hKey[0]);
    v18 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v27,
            L"Year: %d, Month %d, Day %d, Hour %d, Minute %d",
            LOWORD(hKey[0]),
            WORD1(hKey[0]));
    v20 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x192,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v18,
        phkResultb);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v27);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpMem);
      return v20;
    }
    v2 = L"Roaming";
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v19, EVENT_ROAMING_PROFILE_INFO, lpMem[0], v27[0]);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v27);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpMem);
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x187,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (const char *)(unsigned int)v14,
    phkResulta);
  v16 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  return v15;
}

```

## disassembly

```asm
0x180003410  push    rbp
0x180003412  push    rbx
0x180003413  push    rsi
0x180003414  push    rdi
0x180003415  push    r14
0x180003417  push    r15
0x180003419  lea     rbp, [rsp-108h]
0x180003421  sub     rsp, 208h
0x180003428  mov     rax, cs:__security_cookie
0x18000342f  xor     rax, rsp
0x180003432  mov     [rbp+130h+var_40], rax
0x180003439  mov     rsi, rcx
0x18000343c  xor     edx, edx; Val
0x18000343e  mov     r8d, 118h; Size
0x180003444  lea     rcx, [rbp+130h+VersionInformation.dwMajorVersion]; void *
0x180003448  call    memset_0
0x18000344d  mov     [rbp+130h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180003454  lea     rcx, [rbp+130h+VersionInformation]; lpVersionInformation
0x180003458  call    cs:__imp_GetVersionExW
0x18000345e  xor     r15d, r15d
0x180003461  lea     rbx, aRegular; "Regular"
0x180003468  test    eax, eax
0x18000346a  jnz     loc_180003711
0x180003470  call    cs:__imp_GetLastError
0x180003476  mov     edi, eax
0x180003478  test    eax, eax
0x18000347a  jle     short loc_180003485
0x18000347c  movzx   edi, ax
0x18000347f  or      edi, 80070000h
0x180003485  test    edi, edi
0x180003487  js      loc_18000373C
0x18000348d  mov     [rbp+130h+hKey], r15
0x180003491  xor     r14b, r14b
0x180003494  lea     rax, [rbp+130h+hKey]
0x180003498  mov     [rsp+230h+phkResult], rax; phkResult
0x18000349d  mov     r9d, 20019h; samDesired
0x1800034a3  xor     r8d, r8d; ulOptions
0x1800034a6  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800034ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800034b4  call    cs:__imp_RegOpenKeyExW
0x1800034ba  test    eax, eax
0x1800034bc  jz      loc_18000375E
0x1800034c2  lea     rax, aVdi; "VDI"
0x1800034c9  mov     rdi, rbx
0x1800034cc  test    r14b, r14b
0x1800034cf  cmovnz  rdi, rax
0x1800034d3  mov     rcx, [rsi+8]
0x1800034d7  mov     rax, [rcx]
0x1800034da  mov     rax, [rax+10h]
0x1800034de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e3  bt      eax, 12h
0x1800034e7  jb      loc_180003655
0x1800034ed  mov     rcx, [rsi+8]
0x1800034f1  mov     rax, [rcx]
0x1800034f4  mov     rax, [rax+10h]
0x1800034f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034fd  test    al, 1
0x1800034ff  jnz     loc_1800037AC
0x180003505  mov     rcx, [rsi+8]
0x180003509  mov     rax, [rcx]
0x18000350c  mov     rax, [rax+10h]
0x180003510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003515  test    al, 10h
0x180003517  jnz     loc_180003661
0x18000351d  mov     rcx, [rsi+8]
0x180003521  mov     rax, [rcx]
0x180003524  mov     rax, [rax+10h]
0x180003528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352d  test    al, 8
0x18000352f  jnz     loc_180003661
0x180003535  mov     rcx, [rsi+8]
0x180003539  mov     rax, [rcx]
0x18000353c  mov     rax, [rax+10h]
0x180003540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003545  test    al, al
0x180003547  js      loc_1800038B9
0x18000354d  mov     rcx, [rsi+8]
0x180003551  mov     rax, [rcx]
0x180003554  mov     rax, [rax+10h]
0x180003558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000355d  bt      eax, 0Bh
0x180003561  jb      loc_1800038B9
0x180003567  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x18000356e  jz      loc_180003634
0x180003574  mov     rcx, [rsi+8]
0x180003578  mov     rax, [rcx]
0x18000357b  mov     rax, [rax+48h]
0x18000357f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003584  mov     rdx, rax
0x180003587  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000358e  mov     rax, rcx
0x180003591  lea     rax, [rax+1]
0x180003595  cmp     word ptr [rdi+rax*2], 0
0x18000359a  jnz     short loc_180003591
0x18000359c  lea     eax, ds:2[rax*2]
0x1800035a3  mov     [rbp+130h+var_70], rdi
0x1800035aa  mov     [rbp+130h+var_68], eax
0x1800035b0  mov     [rbp+130h+var_64], r15d
0x1800035b7  test    rdx, rdx
0x1800035ba  jz      loc_1800038C5
0x1800035c0  mov     rax, rcx
0x1800035c3  lea     rax, [rax+1]
0x1800035c7  cmp     word ptr [rdx+rax*2], 0
0x1800035cc  jnz     short loc_1800035C3
0x1800035ce  lea     eax, ds:2[rax*2]
0x1800035d5  mov     [rbp+130h+var_60], rdx
0x1800035dc  mov     [rbp+130h+var_58], eax
0x1800035e2  mov     [rbp+130h+var_54], r15d
0x1800035e9  nop     dword ptr [rax+00000000h]
0x1800035f0  lea     rcx, [rcx+1]
0x1800035f4  cmp     word ptr [rbx+rcx*2], 0
0x1800035f9  jnz     short loc_1800035F0
0x1800035fb  lea     ecx, ds:2[rcx*2]
0x180003602  mov     [rbp+130h+var_50], rbx
0x180003609  mov     [rbp+130h+var_48], ecx
0x18000360f  mov     [rbp+130h+var_44], r15d
0x180003616  lea     rax, [rbp+130h+var_80]
0x18000361d  mov     [rsp+230h+phkResult], rax
0x180003622  mov     r9d, 4
0x180003628  lea     rdx, EVENT_PROFILE_INFO; "C"
0x18000362f  call    McGenEventWrite_EtwEventWriteTransfer
0x180003634  xor     eax, eax
0x180003636  mov     rcx, [rbp+130h+var_40]
0x18000363d  xor     rcx, rsp; StackCookie
0x180003640  call    __security_check_cookie
0x180003645  add     rsp, 208h
0x18000364c  pop     r15
0x18000364e  pop     r14
0x180003650  pop     rdi
0x180003651  pop     rsi
0x180003652  pop     rbx
0x180003653  pop     rbp
0x180003654  retn
0x180003655  lea     rbx, aSuperMandatory; "Super-Mandatory"
0x18000365c  jmp     loc_180003535
0x180003661  mov     qword ptr [rsp+230h+FileTime.dwLowDateTime], r15
0x180003666  mov     rcx, [rsi+8]
0x18000366a  mov     rax, [rcx]
0x18000366d  lea     rdx, [rsp+230h+FileTime]
0x180003672  mov     rax, [rax+88h]
0x180003679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000367e  xorps   xmm0, xmm0
0x180003681  movups  xmmword ptr [rbp+130h+hKey], xmm0
0x180003685  lea     rdx, [rbp+130h+hKey]; lpSystemTime
0x180003689  lea     rcx, [rsp+230h+FileTime]; lpFileTime
0x18000368e  call    cs:__imp_FileTimeToSystemTime
0x180003694  mov     [rsp+230h+lpMem], r15
0x180003699  mov     [rsp+230h+var_1D8], r15
0x18000369e  mov     [rsp+230h+var_1D0], r15
0x1800036a3  movzx   eax, word ptr [rbp+130h+hKey+0Ah]
0x1800036a7  movzx   ecx, word ptr [rbp+130h+hKey+8]
0x1800036ab  movzx   edx, word ptr [rbp+130h+hKey+6]
0x1800036af  movzx   r9d, word ptr [rbp+130h+hKey+2]
0x1800036b4  movzx   r8d, word ptr [rbp+130h+hKey]
0x1800036b9  mov     [rsp+230h+var_200], eax
0x1800036bd  mov     dword ptr [rsp+230h+lpcbData], ecx
0x1800036c1  mov     dword ptr [rsp+230h+phkResult], edx; int
0x1800036c5  lea     rdx, aYearDMonthDDay; "Year: %d, Month %d, Day %d, Hour %d, Mi"...
0x1800036cc  lea     rcx, [rsp+230h+lpMem]
0x1800036d1  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800036d6  mov     ebx, eax
0x1800036d8  test    eax, eax
0x1800036da  jns     loc_1800037D1
0x1800036e0  mov     rcx, [rbp+138h]; this
0x1800036e7  mov     r9d, eax; char *
0x1800036ea  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800036f1  mov     edx, 187h; void *
0x1800036f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036fb  nop
0x1800036fc  mov     rdi, [rsp+230h+lpMem]
0x180003701  test    rdi, rdi
0x180003704  jnz     loc_1800037B8
0x18000370a  mov     eax, ebx
0x18000370c  jmp     loc_180003636
0x180003711  test    byte ptr [rbp+130h+var_88], 10h
0x180003718  jz      loc_18000348D
0x18000371e  mov     eax, 100h
0x180003723  test    [rbp+130h+var_88], ax
0x18000372a  jnz     loc_18000348D
0x180003730  lea     rdi, aRds; "RDS"
0x180003737  jmp     loc_1800034D3
0x18000373c  mov     rcx, [rbp+138h]; this
0x180003743  mov     r9d, edi; char *
0x180003746  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18000374d  mov     edx, 15Bh; void *
0x180003752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003757  mov     eax, edi
0x180003759  jmp     loc_180003636
0x18000375e  mov     [rsp+230h+FileTime.dwLowDateTime], r15d
0x180003763  mov     [rsp+230h+cbData], 4
0x18000376b  lea     rax, [rsp+230h+cbData]
0x180003770  mov     [rsp+230h+lpcbData], rax; lpcbData
0x180003775  lea     rax, [rsp+230h+FileTime]
0x18000377a  mov     [rsp+230h+phkResult], rax; lpData
0x18000377f  xor     r9d, r9d; lpType
0x180003782  xor     r8d, r8d; lpReserved
0x180003785  lea     rdx, aRdvirtualizati; "RDVirtualizationPool"
0x18000378c  mov     rcx, [rbp+130h+hKey]; hKey
0x180003790  call    cs:__imp_RegQueryValueExW
0x180003796  cmp     eax, 2
0x180003799  setnz   r14b
0x18000379d  mov     rcx, [rbp+130h+hKey]; hKey
0x1800037a1  call    cs:__imp_RegCloseKey
0x1800037a7  jmp     loc_1800034C2
0x1800037ac  lea     rbx, aMandatory; "Mandatory"
0x1800037b3  jmp     loc_180003535
0x1800037b8  call    cs:__imp_GetProcessHeap
0x1800037be  mov     rcx, rax; hHeap
0x1800037c1  mov     r8, rdi; lpMem
0x1800037c4  xor     edx, edx; dwFlags
0x1800037c6  call    cs:__imp_HeapFree
0x1800037cc  jmp     loc_18000370A
0x1800037d1  mov     rcx, [rsi+8]
0x1800037d5  mov     rax, [rcx]
0x1800037d8  lea     rdx, [rsp+230h+FileTime]
0x1800037dd  mov     rax, [rax+98h]
0x1800037e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e9  lea     rdx, [rbp+130h+hKey]; lpSystemTime
0x1800037ed  lea     rcx, [rsp+230h+FileTime]; lpFileTime
0x1800037f2  call    cs:__imp_FileTimeToSystemTime
0x1800037f8  mov     [rsp+230h+var_1C8], r15
0x1800037fd  mov     [rsp+230h+var_1C0], r15
0x180003802  mov     [rsp+230h+var_1B8], r15
0x180003807  movzx   eax, word ptr [rbp+130h+hKey+0Ah]
0x18000380b  movzx   ecx, word ptr [rbp+130h+hKey+8]
0x18000380f  movzx   r10d, word ptr [rbp+130h+hKey+6]
0x180003814  movzx   r9d, word ptr [rbp+130h+hKey+2]
0x180003819  movzx   r8d, word ptr [rbp+130h+hKey]
0x18000381e  mov     [rsp+230h+var_200], eax
0x180003822  mov     dword ptr [rsp+230h+lpcbData], ecx
0x180003826  mov     dword ptr [rsp+230h+phkResult], r10d; int
0x18000382b  lea     rdx, aYearDMonthDDay; "Year: %d, Month %d, Day %d, Hour %d, Mi"...
0x180003832  lea     rcx, [rsp+230h+var_1C8]
0x180003837  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000383c  mov     ebx, eax
0x18000383e  test    eax, eax
0x180003840  jns     short loc_180003879
0x180003842  mov     rcx, [rbp+138h]; this
0x180003849  mov     r9d, eax; char *
0x18000384c  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180003853  mov     edx, 192h; void *
0x180003858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000385d  lea     rcx, [rsp+230h+var_1C8]
0x180003862  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003867  nop
0x180003868  lea     rcx, [rsp+230h+lpMem]
0x18000386d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003872  mov     eax, ebx
0x180003874  jmp     loc_180003636
0x180003879  lea     rbx, aRoaming; "Roaming"
0x180003880  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180003887  jz      short loc_18000389F
0x180003889  mov     r9, [rsp+230h+var_1C8]
0x18000388e  mov     r8, [rsp+230h+lpMem]
0x180003893  lea     rdx, EVENT_ROAMING_PROFILE_INFO
0x18000389a  call    McTemplateU0zz_EtwEventWriteTransfer
0x18000389f  lea     rcx, [rsp+230h+var_1C8]
0x1800038a4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800038a9  nop
0x1800038aa  lea     rcx, [rsp+230h+lpMem]
0x1800038af  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800038b4  jmp     loc_180003535
0x1800038b9  lea     rbx, aTemporary; "Temporary"
0x1800038c0  jmp     loc_180003567
0x1800038c5  mov     eax, 0Ah
0x1800038ca  lea     rdx, aNull; "NULL"
0x1800038d1  jmp     loc_1800035D5
```
