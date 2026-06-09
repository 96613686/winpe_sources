# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x180017558`
- end: `0x18001772c`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `468`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c054`
- `0x18001c61c`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x180006294`
- `0x180017558`
- `0x180018c48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017653`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017666`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001765e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800176da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001765e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800176da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017701`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800176b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800176b5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800175d7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800175d7`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180017600`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180017600`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180017622`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180017622`

## pseudocode

```c
__int64 __fastcall GetDeviceEnrollerKey(PCWSTR pszMore, HKEY *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  char IsStateSeparationEnabled; // al
  unsigned int v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  HKEY v13; // rax
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !pszMore )
  {
    v4 = 4085;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      dwOptions);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v4 = 4086;
    goto LABEL_3;
  }
  *a2 = 0;
  memset_0(pszPathOut, 0, 0x208u);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v8, v7);
  v5 = PathCchCombine(
         pszPathOut,
         0x104u,
         *(wchar_t **)((char *)off_180021170 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         pszMore);
  if ( v5 < 0 )
  {
    v4 = 4091;
    goto LABEL_4;
  }
  v5 = PathCchAppend(pszPathOut, 0x104u, L"DeviceEnroller");
  if ( v5 < 0 )
  {
    v4 = 4092;
    goto LABEL_4;
  }
  dwDisposition = 0;
  hKey = 0;
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( v10 )
  {
    v5 = wil::details::in1diag3::Return_Win32(retaddr, v11, v12, (const char *)v10, dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
  v13 = hKey;
  hKey = 0;
  *a2 = v13;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180017558  mov     [rsp-8+arg_10], rbx
0x18001755d  push    rbp
0x18001755e  push    rsi
0x18001755f  push    rdi
0x180017560  lea     rbp, [rsp-180h]
0x180017568  sub     rsp, 280h
0x18001756f  mov     rax, cs:__security_cookie
0x180017576  xor     rax, rsp
0x180017579  mov     [rbp+190h+var_20], rax
0x180017580  mov     rsi, rdx
0x180017583  mov     rbx, rcx
0x180017586  test    rcx, rcx
0x180017589  jnz     short loc_1800175B2
0x18001758b  mov     edx, 0FF5h; void *
0x180017590  mov     ebx, 80070057h
0x180017595  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001759c  mov     r9d, ebx; char *
0x18001759f  mov     rcx, [rbp+198h]; this
0x1800175a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800175ab  mov     eax, ebx
0x1800175ad  jmp     loc_18001770A
0x1800175b2  test    rsi, rsi
0x1800175b5  jnz     short loc_1800175BE
0x1800175b7  mov     edx, 0FF6h
0x1800175bc  jmp     short loc_180017590
0x1800175be  mov     qword ptr [rdx], 0
0x1800175c5  xor     edx, edx; Val
0x1800175c7  mov     r8d, 208h; Size
0x1800175cd  lea     rcx, [rsp+290h+pszPathOut]; void *
0x1800175d2  call    memset_0
0x1800175d7  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800175dd  neg     al
0x1800175df  sbb     r8, r8
0x1800175e2  and     r8d, 8
0x1800175e6  lea     rax, off_180021170; "Software\\Microsoft\\Enrollments\\"
0x1800175ed  mov     r9, rbx; pszMore
0x1800175f0  mov     r8, [r8+rax]; pszPathIn
0x1800175f4  mov     edi, 104h
0x1800175f9  mov     edx, edi; cchPathOut
0x1800175fb  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180017600  call    cs:__imp_PathCchCombine
0x180017606  mov     ebx, eax
0x180017608  test    eax, eax
0x18001760a  jns     short loc_180017613
0x18001760c  mov     edx, 0FFBh
0x180017611  jmp     short loc_180017595
0x180017613  lea     r8, pszMore; "DeviceEnroller"
0x18001761a  mov     rdx, rdi; cchPath
0x18001761d  lea     rcx, [rsp+290h+pszPathOut]; pszPath
0x180017622  call    cs:__imp_PathCchAppend
0x180017628  mov     ebx, eax
0x18001762a  test    eax, eax
0x18001762c  jns     short loc_180017638
0x18001762e  mov     edx, 0FFCh
0x180017633  jmp     loc_180017595
0x180017638  mov     [rsp+290h+hKey], 0
0x180017641  mov     [rsp+290h+dwDisposition], 0
0x180017649  mov     rdi, [rsp+290h+hKey]
0x18001764e  test    rdi, rdi
0x180017651  jz      short loc_18001766D
0x180017653  call    cs:__imp_GetLastError
0x180017659  mov     ebx, eax
0x18001765b  mov     rcx, rdi; hKey
0x18001765e  call    cs:__imp_RegCloseKey
0x180017664  mov     ecx, ebx; dwErrCode
0x180017666  call    cs:__imp_SetLastError
0x18001766c  nop
0x18001766d  mov     [rsp+290h+hKey], 0
0x180017676  lea     rax, [rsp+290h+dwDisposition]
0x18001767b  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x180017680  lea     rax, [rsp+290h+hKey]
0x180017685  mov     [rsp+290h+phkResult], rax; phkResult
0x18001768a  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180017693  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18001769b  mov     [rsp+290h+dwOptions], 0; unsigned int
0x1800176a3  xor     r9d, r9d; lpClass
0x1800176a6  xor     r8d, r8d; Reserved
0x1800176a9  lea     rdx, [rsp+290h+pszPathOut]; lpSubKey
0x1800176ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800176b5  call    cs:__imp_RegCreateKeyExW
0x1800176bb  test    eax, eax
0x1800176bd  jz      short loc_1800176E6
0x1800176bf  mov     rcx, [rbp+198h]; this
0x1800176c6  mov     r9d, eax; char *
0x1800176c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800176ce  mov     ebx, eax
0x1800176d0  mov     rcx, [rsp+290h+hKey]; hKey
0x1800176d5  test    rcx, rcx
0x1800176d8  jz      short loc_1800176E1
0x1800176da  call    cs:__imp_RegCloseKey
0x1800176e0  nop
0x1800176e1  jmp     loc_1800175AB
0x1800176e6  mov     rax, [rsp+290h+hKey]
0x1800176eb  mov     [rsp+290h+hKey], 0
0x1800176f4  mov     [rsi], rax
0x1800176f7  mov     rcx, [rsp+290h+hKey]; hKey
0x1800176fc  test    rcx, rcx
0x1800176ff  jz      short loc_180017708
0x180017701  call    cs:__imp_RegCloseKey
0x180017707  nop
0x180017708  xor     eax, eax
0x18001770a  mov     rcx, [rbp+190h+var_20]
0x180017711  xor     rcx, rsp; StackCookie
0x180017714  call    __security_check_cookie
0x180017719  mov     rbx, [rsp+290h+arg_10]
0x180017721  add     rsp, 280h
0x180017728  pop     rdi
0x180017729  pop     rsi
0x18001772a  pop     rbp
0x18001772b  retn
```
