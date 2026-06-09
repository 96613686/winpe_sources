# PpfSystemCcsKey::Open(void)

- ea: `0x18002d1a8`
- end: `0x18002d5e4`
- name: `?Open@PpfSystemCcsKey@@QEAAJXZ`
- size: `1084`
- prototype: `__int64 __fastcall(PpfSystemCcsKey *__hidden this)`
- caller_count: `15`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callers

- `0x18000d1e8`
- `0x1800334d0`
- `0x18003375c`
- `0x180033ae4`
- `0x180033c98`
- `0x180037720`
- `0x18003796c`
- `0x180038f70`
- `0x180039354`
- `0x1800395d4`
- `0x1800398b4`
- `0x18003b0fc`
- `0x18003b418`
- `0x180052134`
- `0x180053280`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c64`
- `0x18000a66c`
- `0x18000b5c8`
- `0x18000c9a4`
- `0x18000dfe0`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180030944`
- `0x180033670`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d2df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d2df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d594`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d2f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d39b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d50d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d2f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d39b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d50d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5a8`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002d44b`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002d44b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d26f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d370`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d26f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d370`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d238`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d544`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d238`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d544`

## string_xrefs

- `0x18002d3d7`: `%s\Windows\System32\Config\SYSTEM`
- `0x18002d429`: `PpfSystemCcsKey::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfSystemCcsKey::Open(PpfSystemCcsKey *this)
{
  int IsOSWinPEBased; // eax
  int AssociatedOSPathInWinPEBasedOS; // ebx
  unsigned int v5; // eax
  unsigned __int16 **v6; // rax
  __int64 v7; // rdx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v10; // eax
  int v11; // eax
  HKEY v12; // rcx
  unsigned int v13; // edi
  void *v14; // rbx
  HANDLE v15; // rax
  HKEY v16; // rax
  const char *v17; // r9
  unsigned int v18; // eax
  unsigned int KeyW; // eax
  int v20; // eax
  unsigned int v21; // esi
  void *v22; // rbx
  HANDLE v23; // rax
  unsigned int v24; // eax
  void *v25; // rbx
  HANDLE v26; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  bool v31; // [rsp+30h] [rbp-D0h] BYREF
  bool v32; // [rsp+31h] [rbp-CFh] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v35; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A0h]
  _BYTE v38[22]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR File[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v31 = 0;
  IsOSWinPEBased = PpfhIsOSWinPEBased(&v31);
  AssociatedOSPathInWinPEBasedOS = IsOSWinPEBased;
  if ( IsOSWinPEBased < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E1,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)IsOSWinPEBased,
      (int)phkResult);
    return (unsigned int)AssociatedOSPathInWinPEBasedOS;
  }
  if ( !v31 )
  {
    hKey = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet", 0, 0x20019u, &hKey);
    if ( v5 )
    {
      AssociatedOSPathInWinPEBasedOS = wil::details::in1diag3::Return_Win32(
                                         retaddr,
                                         (void *)0x2E6,
                                         (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
                                         (const char *)v5,
                                         phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)AssociatedOSPathInWinPEBasedOS;
    }
    *(_QWORD *)this = hKey;
    return 0;
  }
  lpMem = 0;
  v32 = 0;
  v6 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&lpMem);
  AssociatedOSPathInWinPEBasedOS = PpfhGetAssociatedOSPathInWinPEBasedOS(&v32, v6);
  if ( AssociatedOSPathInWinPEBasedOS < 0 )
  {
    v7 = 750;
    goto LABEL_11;
  }
  if ( !v32 )
  {
    hKey = 0;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet", 0, 0x20019u, &hKey);
    if ( v10 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2F3,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
              (const char *)v10,
              phkResultb);
      v12 = hKey;
      goto LABEL_16;
    }
    v16 = hKey;
    hKey = 0;
    goto LABEL_36;
  }
  memset_0(File, 0, 0x208u);
  AssociatedOSPathInWinPEBasedOS = StringCchPrintfW(File, 0x104u, L"%s\\Windows\\System32\\Config\\SYSTEM", lpMem);
  if ( AssociatedOSPathInWinPEBasedOS < 0 )
  {
    v7 = 764;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)AssociatedOSPathInWinPEBasedOS,
      (int)phkResult);
    v8 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    return (unsigned int)AssociatedOSPathInWinPEBasedOS;
  }
  v18 = PpfSystemCcsKey::m_targetOSSystemHiveLoadCount;
  if ( !PpfSystemCcsKey::m_targetOSSystemHiveLoadCount )
  {
    phkResult = (PHKEY)L"PcrpfRootKey";
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x301u,
      "PpfSystemCcsKey::Open",
      "Loading HKLM\\%ws --> %ws");
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"PcrpfRootKey", File);
    if ( KeyW )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x302,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
              (const char *)KeyW,
              (unsigned int)L"PcrpfRootKey");
LABEL_18:
      v14 = lpMem;
      if ( lpMem )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v14);
      }
      return v13;
    }
    v18 = PpfSystemCcsKey::m_targetOSSystemHiveLoadCount;
  }
  PpfSystemCcsKey::m_targetOSSystemHiveLoadCount = v18 + 1;
  if ( v18 + 1 > 0x3E8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      v17);
  *(_OWORD *)SubKey = 0;
  v37 = 0;
  memset(v38, 0, sizeof(v38));
  v20 = StringCchPrintfW(SubKey, 0x1Bu, L"%s\\ControlSet001", L"PcrpfRootKey");
  v21 = v20;
  if ( v20 >= 0 )
  {
    v35 = 0;
    v24 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v35);
    if ( v24 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x310,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
              (const char *)v24,
              phkResultc);
      v12 = v35;
LABEL_16:
      v13 = v11;
      if ( v12 )
        RegCloseKey(v12);
      goto LABEL_18;
    }
    v16 = v35;
    v35 = 0;
LABEL_36:
    *(_QWORD *)this = v16;
    v25 = lpMem;
    if ( lpMem )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v25);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x30D,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    (const char *)(unsigned int)v20,
    (int)phkResult);
  v22 = lpMem;
  if ( lpMem )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  return v21;
}

```

## disassembly

```asm
0x18002d1a8  push    rbp
0x18002d1aa  push    rbx
0x18002d1ab  push    rsi
0x18002d1ac  push    rdi
0x18002d1ad  lea     rbp, [rsp-1B8h]
0x18002d1b5  sub     rsp, 2B8h
0x18002d1bc  mov     rax, cs:__security_cookie
0x18002d1c3  xor     rax, rsp
0x18002d1c6  mov     [rbp+1D0h+var_30], rax
0x18002d1cd  mov     rdi, rcx
0x18002d1d0  mov     [rsp+2D0h+var_2A0], 0
0x18002d1d5  lea     rcx, [rsp+2D0h+var_2A0]; bool *
0x18002d1da  call    ?PpfhIsOSWinPEBased@@YAJPEA_N@Z; PpfhIsOSWinPEBased(bool *)
0x18002d1df  mov     ebx, eax
0x18002d1e1  test    eax, eax
0x18002d1e3  jns     short loc_18002D207
0x18002d1e5  mov     rcx, [rbp+1D8h]; this
0x18002d1ec  mov     r9d, eax; char *
0x18002d1ef  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d1f6  mov     edx, 2E1h; void *
0x18002d1fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d200  mov     eax, ebx
0x18002d202  jmp     loc_18002D5B6
0x18002d207  cmp     [rsp+2D0h+var_2A0], 0
0x18002d20c  jnz     short loc_18002D28A
0x18002d20e  mov     [rsp+2D0h+hKey], 0
0x18002d217  lea     rax, [rsp+2D0h+hKey]
0x18002d21c  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x18002d221  mov     r9d, 20019h; samDesired
0x18002d227  xor     r8d, r8d; ulOptions
0x18002d22a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet"
0x18002d231  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d238  call    cs:__imp_RegOpenKeyExW
0x18002d23f  nop     dword ptr [rax+rax+00h]
0x18002d244  test    eax, eax
0x18002d246  jz      short loc_18002D27D
0x18002d248  mov     rcx, [rbp+1D8h]; this
0x18002d24f  mov     r9d, eax; char *
0x18002d252  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d259  mov     edx, 2E6h; void *
0x18002d25e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d263  mov     ebx, eax
0x18002d265  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002d26a  test    rcx, rcx
0x18002d26d  jz      short loc_18002D200
0x18002d26f  call    cs:__imp_RegCloseKey
0x18002d276  nop     dword ptr [rax+rax+00h]
0x18002d27b  jmp     short loc_18002D200
0x18002d27d  mov     rax, [rsp+2D0h+hKey]
0x18002d282  mov     [rdi], rax
0x18002d285  jmp     loc_18002D5B4
0x18002d28a  mov     [rsp+2D0h+lpMem], 0
0x18002d293  mov     [rsp+2D0h+var_29F], 0
0x18002d298  lea     rcx, [rsp+2D0h+lpMem]
0x18002d29d  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x18002d2a2  mov     rdx, rax; unsigned __int16 **
0x18002d2a5  lea     rcx, [rsp+2D0h+var_29F]; bool *
0x18002d2aa  call    ?PpfhGetAssociatedOSPathInWinPEBasedOS@@YAJPEA_NPEAPEAG@Z; PpfhGetAssociatedOSPathInWinPEBasedOS(bool *,ushort * *)
0x18002d2af  mov     ebx, eax
0x18002d2b1  test    eax, eax
0x18002d2b3  jns     short loc_18002D304
0x18002d2b5  mov     edx, 2EEh; void *
0x18002d2ba  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d2c1  mov     r9d, ebx; char *
0x18002d2c4  mov     rcx, [rbp+1D8h]; this
0x18002d2cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d2d0  nop
0x18002d2d1  mov     rdi, [rsp+2D0h+lpMem]
0x18002d2d6  test    rdi, rdi
0x18002d2d9  jz      loc_18002D200
0x18002d2df  call    cs:__imp_GetProcessHeap
0x18002d2e6  nop     dword ptr [rax+rax+00h]
0x18002d2eb  mov     rcx, rax; hHeap
0x18002d2ee  mov     r8, rdi; lpMem
0x18002d2f1  xor     edx, edx; dwFlags
0x18002d2f3  call    cs:__imp_HeapFree
0x18002d2fa  nop     dword ptr [rax+rax+00h]
0x18002d2ff  jmp     loc_18002D200
0x18002d304  cmp     [rsp+2D0h+var_29F], 0
0x18002d309  jnz     loc_18002D3C1
0x18002d30f  mov     [rsp+2D0h+hKey], 0
0x18002d318  lea     rax, [rsp+2D0h+hKey]
0x18002d31d  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x18002d322  mov     r9d, 20019h; samDesired
0x18002d328  xor     r8d, r8d; ulOptions
0x18002d32b  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet"
0x18002d332  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d339  call    cs:__imp_RegOpenKeyExW
0x18002d340  nop     dword ptr [rax+rax+00h]
0x18002d345  test    eax, eax
0x18002d347  jz      short loc_18002D3AE
0x18002d349  mov     rcx, [rbp+1D8h]; this
0x18002d350  mov     r9d, eax; char *
0x18002d353  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d35a  mov     edx, 2F3h; void *
0x18002d35f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d364  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002d369  test    rcx, rcx
0x18002d36c  mov     edi, eax
0x18002d36e  jz      short loc_18002D37D
0x18002d370  call    cs:__imp_RegCloseKey
0x18002d377  nop     dword ptr [rax+rax+00h]
0x18002d37c  nop
0x18002d37d  mov     rbx, [rsp+2D0h+lpMem]
0x18002d382  test    rbx, rbx
0x18002d385  jz      short loc_18002D3A7
0x18002d387  call    cs:__imp_GetProcessHeap
0x18002d38e  nop     dword ptr [rax+rax+00h]
0x18002d393  mov     rcx, rax; hHeap
0x18002d396  mov     r8, rbx; lpMem
0x18002d399  xor     edx, edx; dwFlags
0x18002d39b  call    cs:__imp_HeapFree
0x18002d3a2  nop     dword ptr [rax+rax+00h]
0x18002d3a7  mov     eax, edi
0x18002d3a9  jmp     loc_18002D5B6
0x18002d3ae  mov     rax, [rsp+2D0h+hKey]
0x18002d3b3  mov     [rsp+2D0h+hKey], 0
0x18002d3bc  jmp     loc_18002D587
0x18002d3c1  xor     edx, edx; Val
0x18002d3c3  mov     r8d, 208h; Size
0x18002d3c9  lea     rcx, [rbp+1D0h+File]; void *
0x18002d3cd  call    memset_0
0x18002d3d2  mov     r9, [rsp+2D0h+lpMem]
0x18002d3d7  lea     r8, aSWindowsSystem; "%s\\Windows\\System32\\Config\\SYSTEM"
0x18002d3de  mov     edx, 104h; unsigned __int64
0x18002d3e3  lea     rcx, [rbp+1D0h+File]; unsigned __int16 *
0x18002d3e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d3ec  mov     ebx, eax
0x18002d3ee  test    eax, eax
0x18002d3f0  jns     short loc_18002D3FC
0x18002d3f2  mov     edx, 2FCh
0x18002d3f7  jmp     loc_18002D2BA
0x18002d3fc  mov     rbx, 0FFFFFFFF80000002h
0x18002d403  lea     rsi, aPcrpfrootkey; "PcrpfRootKey"
0x18002d40a  mov     eax, cs:?m_targetOSSystemHiveLoadCount@PpfSystemCcsKey@@0IA; uint PpfSystemCcsKey::m_targetOSSystemHiveLoadCount
0x18002d410  test    eax, eax
0x18002d412  jnz     short loc_18002D483
0x18002d414  lea     rax, [rbp+1D0h+File]
0x18002d418  mov     [rsp+2D0h+var_2A8], rax
0x18002d41d  mov     [rsp+2D0h+phkResult], rsi; int
0x18002d422  lea     r9, aLoadingHklmWsW; "Loading HKLM\\%ws --> %ws"
0x18002d429  lea     r8, aPpfsystemccske_0; "PpfSystemCcsKey::Open"
0x18002d430  mov     edx, 301h; unsigned int
0x18002d435  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d43c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002d441  lea     r8, [rbp+1D0h+File]; lpFile
0x18002d445  mov     rdx, rsi; lpSubKey
0x18002d448  mov     rcx, rbx; hKey
0x18002d44b  call    cs:__imp_RegLoadKeyW
0x18002d452  nop     dword ptr [rax+rax+00h]
0x18002d457  test    eax, eax
0x18002d459  jz      short loc_18002D47D
0x18002d45b  mov     rcx, [rbp+1D8h]; this
0x18002d462  mov     r9d, eax; char *
0x18002d465  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d46c  mov     edx, 302h; void *
0x18002d471  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d476  mov     edi, eax
0x18002d478  jmp     loc_18002D37D
0x18002d47d  mov     eax, cs:?m_targetOSSystemHiveLoadCount@PpfSystemCcsKey@@0IA; uint PpfSystemCcsKey::m_targetOSSystemHiveLoadCount
0x18002d483  inc     eax
0x18002d485  mov     cs:?m_targetOSSystemHiveLoadCount@PpfSystemCcsKey@@0IA, eax; uint PpfSystemCcsKey::m_targetOSSystemHiveLoadCount
0x18002d48b  mov     rcx, [rbp+1D8h]; this
0x18002d492  cmp     eax, 3E8h
0x18002d497  ja      loc_18002D5D2
0x18002d49d  xorps   xmm0, xmm0
0x18002d4a0  xor     eax, eax
0x18002d4a2  movups  xmmword ptr [rsp+2D0h+SubKey], xmm0
0x18002d4a7  movups  [rsp+2D0h+var_270], xmm0
0x18002d4ac  movups  xmmword ptr [rsp+2D0h+var_260], xmm0
0x18002d4b1  mov     qword ptr [rsp+2D0h+var_260+0Eh], rax
0x18002d4b6  mov     r9, rsi
0x18002d4b9  lea     r8, aSControlset001; "%s\\ControlSet001"
0x18002d4c0  lea     edx, [rax+1Bh]; unsigned __int64
0x18002d4c3  lea     rcx, [rsp+2D0h+SubKey]; unsigned __int16 *
0x18002d4c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d4cd  mov     esi, eax
0x18002d4cf  test    eax, eax
0x18002d4d1  jns     short loc_18002D520
0x18002d4d3  mov     rcx, [rbp+1D8h]; this
0x18002d4da  mov     r9d, eax; char *
0x18002d4dd  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d4e4  mov     edx, 30Dh; void *
0x18002d4e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d4ee  nop
0x18002d4ef  mov     rbx, [rsp+2D0h+lpMem]
0x18002d4f4  test    rbx, rbx
0x18002d4f7  jz      short loc_18002D519
0x18002d4f9  call    cs:__imp_GetProcessHeap
0x18002d500  nop     dword ptr [rax+rax+00h]
0x18002d505  mov     rcx, rax; hHeap
0x18002d508  mov     r8, rbx; lpMem
0x18002d50b  xor     edx, edx; dwFlags
0x18002d50d  call    cs:__imp_HeapFree
0x18002d514  nop     dword ptr [rax+rax+00h]
0x18002d519  mov     eax, esi
0x18002d51b  jmp     loc_18002D5B6
0x18002d520  mov     [rsp+2D0h+var_288], 0
0x18002d529  lea     rax, [rsp+2D0h+var_288]
0x18002d52e  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x18002d533  mov     r9d, 20019h; samDesired
0x18002d539  xor     r8d, r8d; ulOptions
0x18002d53c  lea     rdx, [rsp+2D0h+SubKey]; lpSubKey
0x18002d541  mov     rcx, rbx; hKey
0x18002d544  call    cs:__imp_RegOpenKeyExW
0x18002d54b  nop     dword ptr [rax+rax+00h]
0x18002d550  test    eax, eax
0x18002d552  jz      short loc_18002D579
0x18002d554  mov     rcx, [rbp+1D8h]; this
0x18002d55b  mov     r9d, eax; char *
0x18002d55e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d565  mov     edx, 310h; void *
0x18002d56a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d56f  mov     rcx, [rsp+2D0h+var_288]
0x18002d574  jmp     loc_18002D369
0x18002d579  mov     rax, [rsp+2D0h+var_288]
0x18002d57e  mov     [rsp+2D0h+var_288], 0
0x18002d587  mov     [rdi], rax
0x18002d58a  mov     rbx, [rsp+2D0h+lpMem]
0x18002d58f  test    rbx, rbx
0x18002d592  jz      short loc_18002D5B4
0x18002d594  call    cs:__imp_GetProcessHeap
0x18002d59b  nop     dword ptr [rax+rax+00h]
0x18002d5a0  mov     r8, rbx; lpMem
0x18002d5a3  xor     edx, edx; dwFlags
0x18002d5a5  mov     rcx, rax; hHeap
0x18002d5a8  call    cs:__imp_HeapFree
0x18002d5af  nop     dword ptr [rax+rax+00h]
0x18002d5b4  xor     eax, eax
0x18002d5b6  mov     rcx, [rbp+1D0h+var_30]
0x18002d5bd  xor     rcx, rsp; StackCookie
0x18002d5c0  call    __security_check_cookie
0x18002d5c5  add     rsp, 2B8h
0x18002d5cc  pop     rdi
0x18002d5cd  pop     rsi
0x18002d5ce  pop     rbx
0x18002d5cf  pop     rbp
0x18002d5d0  retn
0x18002d5d2  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002d5d9  mov     edx, 307h; void *
0x18002d5de  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
