# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x180062988`
- end: `0x180062b3f`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `439`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001208c`
- `0x180012370`

## callees

- `0x1800071c0`
- `0x1800118f8`
- `0x180011938`
- `0x18002d998`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180062988`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180062aba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180062aba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062b12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062b12`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180062a48`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180062a48`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180062a24`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180062a24`

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
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
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
  hKey = 0;
  dwDisposition = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( v8 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1002,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
           (const char *)v8,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
  v9 = hKey;
  hKey = 0;
  *a2 = v9;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180062988  mov     [rsp-8+arg_10], rbx
0x18006298d  mov     [rsp-8+arg_18], rdi
0x180062992  push    rbp
0x180062993  lea     rbp, [rsp-180h]
0x18006299b  sub     rsp, 280h
0x1800629a2  mov     rax, cs:__security_cookie
0x1800629a9  xor     rax, rsp
0x1800629ac  mov     [rbp+180h+var_10], rax
0x1800629b3  mov     rdi, rdx
0x1800629b6  mov     rbx, rcx
0x1800629b9  test    rcx, rcx
0x1800629bc  jnz     short loc_1800629E5
0x1800629be  mov     edx, 0FF5h; void *
0x1800629c3  mov     ebx, 80070057h
0x1800629c8  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800629cf  mov     r9d, ebx; char *
0x1800629d2  mov     rcx, [rbp+188h]; this
0x1800629d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800629de  mov     eax, ebx
0x1800629e0  jmp     loc_180062B1B
0x1800629e5  test    rdi, rdi
0x1800629e8  jnz     short loc_1800629F1
0x1800629ea  mov     edx, 0FF6h
0x1800629ef  jmp     short loc_1800629C3
0x1800629f1  mov     qword ptr [rdx], 0
0x1800629f8  xor     edx, edx; Val
0x1800629fa  mov     r8d, 208h; Size
0x180062a00  lea     rcx, [rsp+280h+pszPathOut]; void *
0x180062a05  call    memset_0
0x180062a0a  mov     ecx, 2
0x180062a0f  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180062a14  mov     r8, rax; pszPathIn
0x180062a17  mov     r9, rbx; pszMore
0x180062a1a  mov     edx, 104h; cchPathOut
0x180062a1f  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x180062a24  call    cs:__imp_PathCchCombine
0x180062a2a  mov     ebx, eax
0x180062a2c  test    eax, eax
0x180062a2e  jns     short loc_180062A37
0x180062a30  mov     edx, 0FFBh
0x180062a35  jmp     short loc_1800629C8
0x180062a37  lea     r8, aDeviceenroller; "DeviceEnroller"
0x180062a3e  mov     edx, 104h; cchPath
0x180062a43  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x180062a48  call    cs:__imp_PathCchAppend
0x180062a4e  mov     ebx, eax
0x180062a50  test    eax, eax
0x180062a52  jns     short loc_180062A5E
0x180062a54  mov     edx, 0FFCh
0x180062a59  jmp     loc_1800629C8
0x180062a5e  mov     [rsp+280h+hKey], 0
0x180062a67  mov     [rsp+280h+dwDisposition], 0
0x180062a6f  xor     edx, edx
0x180062a71  lea     rcx, [rsp+280h+hKey]
0x180062a76  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180062a7b  lea     rax, [rsp+280h+dwDisposition]
0x180062a80  mov     [rsp+280h+lpdwDisposition], rax; lpdwDisposition
0x180062a85  lea     rax, [rsp+280h+hKey]
0x180062a8a  mov     [rsp+280h+phkResult], rax; phkResult
0x180062a8f  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180062a98  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x180062aa0  mov     [rsp+280h+dwOptions], 0; unsigned int
0x180062aa8  xor     r9d, r9d; lpClass
0x180062aab  xor     r8d, r8d; Reserved
0x180062aae  lea     rdx, [rsp+280h+pszPathOut]; lpSubKey
0x180062ab3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062aba  call    cs:__imp_RegCreateKeyExW
0x180062ac0  test    eax, eax
0x180062ac2  jz      short loc_180062AF7
0x180062ac4  mov     rcx, [rbp+188h]; this
0x180062acb  mov     r9d, eax; char *
0x180062ace  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180062ad5  mov     edx, 1002h; void *
0x180062ada  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180062adf  mov     ebx, eax
0x180062ae1  mov     rcx, [rsp+280h+hKey]; hKey
0x180062ae6  test    rcx, rcx
0x180062ae9  jz      short loc_180062AF2
0x180062aeb  call    cs:__imp_RegCloseKey
0x180062af1  nop
0x180062af2  jmp     loc_1800629DE
0x180062af7  mov     rax, [rsp+280h+hKey]
0x180062afc  mov     [rsp+280h+hKey], 0
0x180062b05  mov     [rdi], rax
0x180062b08  mov     rcx, [rsp+280h+hKey]; hKey
0x180062b0d  test    rcx, rcx
0x180062b10  jz      short loc_180062B19
0x180062b12  call    cs:__imp_RegCloseKey
0x180062b18  nop
0x180062b19  xor     eax, eax
0x180062b1b  mov     rcx, [rbp+180h+var_10]
0x180062b22  xor     rcx, rsp; StackCookie
0x180062b25  call    __security_check_cookie
0x180062b2a  lea     r11, [rsp+280h+var_s0]
0x180062b32  mov     rbx, [r11+20h]
0x180062b36  mov     rdi, [r11+28h]
0x180062b3a  mov     rsp, r11
0x180062b3d  pop     rbp
0x180062b3e  retn
```
