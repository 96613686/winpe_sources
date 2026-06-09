# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x1800da990`
- end: `0x1800dab4e`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `446`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800de394`
- `0x1800de864`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x18002201c`
- `0x180025ac0`
- `0x18002aed0`
- `0x18002dcc8`
- `0x1800da990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800daace`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800daace`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800daa56`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800daa56`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800daa2c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800daa2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetDeviceEnrollerKey(PCWSTR pszMore, HKEY *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  HKEY v9; // rax
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

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
  v7 = (const WCHAR *)DMGetKnownRegPath(2);
  v5 = PathCchCombine(pszPathOut, 0x104u, v7, pszMore);
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
  phkResult = 0;
  dwDisposition = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
  if ( v8 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1002,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
           (const char *)v8,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    return (unsigned int)v5;
  }
  v9 = phkResult;
  phkResult = 0;
  *a2 = v9;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return 0;
}

```

## disassembly

```asm
0x1800da990  mov     [rsp-8+arg_10], rbx
0x1800da995  mov     [rsp-8+arg_18], rdi
0x1800da99a  push    rbp
0x1800da99b  lea     rbp, [rsp-180h]
0x1800da9a3  sub     rsp, 280h
0x1800da9aa  mov     rax, cs:__security_cookie
0x1800da9b1  xor     rax, rsp
0x1800da9b4  mov     [rbp+180h+var_10], rax
0x1800da9bb  mov     rdi, rdx
0x1800da9be  mov     rbx, rcx
0x1800da9c1  test    rcx, rcx
0x1800da9c4  jnz     short loc_1800DA9ED
0x1800da9c6  mov     edx, 0FF5h; void *
0x1800da9cb  mov     ebx, 80070057h
0x1800da9d0  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800da9d7  mov     r9d, ebx; char *
0x1800da9da  mov     rcx, [rbp+188h]; this
0x1800da9e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da9e6  mov     eax, ebx
0x1800da9e8  jmp     loc_1800DAB29
0x1800da9ed  test    rdi, rdi
0x1800da9f0  jnz     short loc_1800DA9F9
0x1800da9f2  mov     edx, 0FF6h
0x1800da9f7  jmp     short loc_1800DA9CB
0x1800da9f9  mov     qword ptr [rdx], 0
0x1800daa00  xor     edx, edx; Val
0x1800daa02  mov     r8d, 208h; Size
0x1800daa08  lea     rcx, [rsp+280h+pszPathOut]; void *
0x1800daa0d  call    memset_0
0x1800daa12  mov     ecx, 2
0x1800daa17  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800daa1c  mov     r8, rax; pszPathIn
0x1800daa1f  mov     r9, rbx; pszMore
0x1800daa22  mov     edx, 104h; cchPathOut
0x1800daa27  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x1800daa2c  call    cs:__imp_PathCchCombine
0x1800daa33  nop     dword ptr [rax+rax+00h]
0x1800daa38  mov     ebx, eax
0x1800daa3a  test    eax, eax
0x1800daa3c  jns     short loc_1800DAA45
0x1800daa3e  mov     edx, 0FFBh
0x1800daa43  jmp     short loc_1800DA9D0
0x1800daa45  lea     r8, aDeviceenroller; "DeviceEnroller"
0x1800daa4c  mov     edx, 104h; cchPath
0x1800daa51  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x1800daa56  call    cs:__imp_PathCchAppend
0x1800daa5d  nop     dword ptr [rax+rax+00h]
0x1800daa62  mov     ebx, eax
0x1800daa64  test    eax, eax
0x1800daa66  jns     short loc_1800DAA72
0x1800daa68  mov     edx, 0FFCh
0x1800daa6d  jmp     loc_1800DA9D0
0x1800daa72  mov     [rsp+280h+var_230], 0
0x1800daa7b  mov     [rsp+280h+dwDisposition], 0
0x1800daa83  xor     edx, edx
0x1800daa85  lea     rcx, [rsp+280h+var_230]
0x1800daa8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800daa8f  lea     rax, [rsp+280h+dwDisposition]
0x1800daa94  mov     [rsp+280h+lpdwDisposition], rax; lpdwDisposition
0x1800daa99  lea     rax, [rsp+280h+var_230]
0x1800daa9e  mov     [rsp+280h+phkResult], rax; phkResult
0x1800daaa3  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800daaac  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x1800daab4  mov     [rsp+280h+dwOptions], 0; unsigned int
0x1800daabc  xor     r9d, r9d; lpClass
0x1800daabf  xor     r8d, r8d; Reserved
0x1800daac2  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x1800daac7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800daace  call    cs:__imp_RegCreateKeyExW
0x1800daad5  nop     dword ptr [rax+rax+00h]
0x1800daada  test    eax, eax
0x1800daadc  jz      short loc_1800DAB0B
0x1800daade  mov     rcx, [rbp+188h]; this
0x1800daae5  mov     r9d, eax; char *
0x1800daae8  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800daaef  mov     edx, 1002h; void *
0x1800daaf4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800daaf9  mov     ebx, eax
0x1800daafb  lea     rcx, [rsp+280h+var_230]
0x1800dab00  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dab05  nop
0x1800dab06  jmp     loc_1800DA9E6
0x1800dab0b  mov     rax, [rsp+280h+var_230]
0x1800dab10  mov     [rsp+280h+var_230], 0
0x1800dab19  mov     [rdi], rax
0x1800dab1c  lea     rcx, [rsp+280h+var_230]
0x1800dab21  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dab26  nop
0x1800dab27  xor     eax, eax
0x1800dab29  mov     rcx, [rbp+180h+var_10]
0x1800dab30  xor     rcx, rsp; StackCookie
0x1800dab33  call    __security_check_cookie
0x1800dab38  lea     r11, [rsp+280h+var_s0]
0x1800dab40  mov     rbx, [r11+20h]
0x1800dab44  mov     rdi, [r11+28h]
0x1800dab48  mov     rsp, r11
0x1800dab4b  pop     rbp
0x1800dab4c  retn
```
