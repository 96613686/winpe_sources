# KnownUicc::SetUIStatus(__MIDL___MIDL_itf_mvengine_0000_0000_0002)

- ea: `0x1800355a4`
- end: `0x180035756`
- name: `?SetUIStatus@KnownUicc@@QEAAXW4__MIDL___MIDL_itf_mvengine_0000_0000_0002@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180029e90`

## callees

- `0x18000e0b0`
- `0x18000e308`
- `0x180012390`
- `0x180012e30`
- `0x1800355a4`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180035705`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035705`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800356f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800356f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800356dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800356dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800356a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800356a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall KnownUicc::SetUIStatus(_QWORD *a1)
{
  unsigned __int64 v2; // r8
  LPCWSTR *v3; // rcx
  char *v4; // rdx
  LPCWSTR *v5; // rax
  __int64 v6; // rdx
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  BYTE Data[8]; // [rsp+50h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+1Fh] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp+27h] BYREF
  __int64 v15; // [rsp+70h] [rbp+37h]
  unsigned __int64 v16; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  *(_DWORD *)Data = 4;
  v16 = 7;
  v15 = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( *gc_wszRegUicc )
  {
    v2 = -1;
    do
      ++v2;
    while ( gc_wszRegUicc[v2] );
  }
  else
  {
    v2 = 0;
  }
  std::wstring::assign(lpSubKey, (char *)gc_wszRegUicc, v2);
  v3 = lpSubKey;
  if ( v16 >= 8 )
    v3 = (LPCWSTR *)lpSubKey[0];
  v4 = (char *)v3 + 2 * v15;
  v5 = lpSubKey;
  if ( v16 >= 8 )
    v5 = (LPCWSTR *)lpSubKey[0];
  if ( v4 )
    v6 = (v4 - (char *)v5) >> 1;
  else
    v6 = 0;
  std::wstring::insert(lpSubKey, v6, 1);
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  std::wstring::append(lpSubKey, a1);
  hKey = 0;
  v7 = (const WCHAR *)lpSubKey;
  if ( v16 >= 8 )
    v7 = lpSubKey[0];
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v8,
      dwOptions);
  v9 = RegSetValueExW(hKey, L"UIRequired", 0, 4u, Data, 4u);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v9,
      dwOptionsa);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v16 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x1800355a4  mov     [rsp-8+arg_8], rbx
0x1800355a9  mov     [rsp-8+arg_10], rdi
0x1800355ae  push    rbp
0x1800355af  lea     rbp, [rsp-57h]
0x1800355b4  sub     rsp, 90h
0x1800355bb  mov     rax, cs:__security_cookie
0x1800355c2  xor     rax, rsp
0x1800355c5  mov     [rbp+57h+var_10], rax
0x1800355c9  mov     rbx, rcx
0x1800355cc  mov     dword ptr [rbp+57h+Data], 4
0x1800355d3  mov     rdx, cs:?gc_wszRegUicc@@3PEBGEB; Src
0x1800355da  mov     [rbp+57h+var_18], 7
0x1800355e2  xor     edi, edi
0x1800355e4  mov     [rbp+57h+var_20], rdi
0x1800355e8  mov     word ptr [rbp+57h+lpSubKey], di
0x1800355ec  cmp     [rdx], di
0x1800355ef  jnz     short loc_1800355F6
0x1800355f1  mov     r8d, edi
0x1800355f4  jmp     short loc_180035604
0x1800355f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800355fa  inc     r8
0x1800355fd  cmp     [rdx+r8*2], di
0x180035602  jnz     short loc_1800355FA
0x180035604  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180035608  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003560d  nop
0x18003560e  lea     rcx, [rbp+57h+lpSubKey]
0x180035612  cmp     [rbp+57h+var_18], 8
0x180035617  cmovnb  rcx, [rbp+57h+lpSubKey]
0x18003561c  mov     rax, [rbp+57h+var_20]
0x180035620  lea     rdx, [rcx+rax*2]
0x180035624  lea     rax, [rbp+57h+lpSubKey]
0x180035628  cmovnb  rax, [rbp+57h+lpSubKey]
0x18003562d  test    rdx, rdx
0x180035630  jnz     short loc_180035637
0x180035632  mov     rdx, rdi
0x180035635  jmp     short loc_18003563D
0x180035637  sub     rdx, rax
0x18003563a  sar     rdx, 1
0x18003563d  mov     r9d, 5Ch ; '\'
0x180035643  lea     r8d, [r9-5Bh]
0x180035647  lea     rcx, [rbp+57h+lpSubKey]
0x18003564b  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0G@Z; std::wstring::insert(unsigned __int64,unsigned __int64,ushort)
0x180035650  cmp     qword ptr [rbx+18h], 8
0x180035655  jb      short loc_18003565A
0x180035657  mov     rbx, [rbx]
0x18003565a  mov     rdx, rbx; void *
0x18003565d  lea     rcx, [rbp+57h+lpSubKey]; Src
0x180035661  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180035666  nop
0x180035667  mov     [rbp+57h+hKey], rdi
0x18003566b  lea     rdx, [rbp+57h+lpSubKey]
0x18003566f  cmp     [rbp+57h+var_18], 8
0x180035674  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180035679  mov     [rsp+90h+lpdwDisposition], rdi; lpdwDisposition
0x18003567e  lea     rax, [rbp+57h+hKey]
0x180035682  mov     [rsp+90h+phkResult], rax; phkResult
0x180035687  mov     [rsp+90h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003568c  mov     [rsp+90h+samDesired], 2; samDesired
0x180035694  mov     [rsp+90h+dwOptions], edi; unsigned int
0x180035698  xor     r9d, r9d; lpClass
0x18003569b  xor     r8d, r8d; Reserved
0x18003569e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800356a5  call    cs:__imp_RegCreateKeyExW
0x1800356ab  mov     rcx, [rbp+5Fh]; this
0x1800356af  test    eax, eax
0x1800356b1  jnz     loc_180035741
0x1800356b7  mov     [rsp+90h+samDesired], 4; cbData
0x1800356bf  lea     rax, [rbp+57h+Data]
0x1800356c3  mov     qword ptr [rsp+90h+dwOptions], rax; unsigned int
0x1800356c8  mov     r9d, 4; dwType
0x1800356ce  xor     r8d, r8d; Reserved
0x1800356d1  lea     rdx, ?gc_wszUIRequired@@3QBGB; "UIRequired"
0x1800356d8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800356dc  call    cs:__imp_RegSetValueExW
0x1800356e2  mov     rcx, [rbp+5Fh]; this
0x1800356e6  test    eax, eax
0x1800356e8  jnz     short loc_18003572C
0x1800356ea  mov     rcx, [rbp+57h+hKey]; hKey
0x1800356ee  test    rcx, rcx
0x1800356f1  jz      short loc_1800356FA
0x1800356f3  call    cs:__imp_RegCloseKey
0x1800356f9  nop
0x1800356fa  cmp     [rbp+57h+var_18], 8
0x1800356ff  jb      short loc_18003570B
0x180035701  mov     rcx, [rbp+57h+lpSubKey]
0x180035705  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003570b  mov     rcx, [rbp+57h+var_10]
0x18003570f  xor     rcx, rsp; StackCookie
0x180035712  call    __security_check_cookie
0x180035717  lea     r11, [rsp+90h+var_s0]
0x18003571f  mov     rbx, [r11+18h]
0x180035723  mov     rdi, [r11+20h]
0x180035727  mov     rsp, r11
0x18003572a  pop     rbp
0x18003572b  retn
0x18003572c  mov     r9d, eax; char *
0x18003572f  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035736  mov     edx, 90h; void *
0x18003573b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035741  mov     r9d, eax; char *
0x180035744  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003574b  mov     edx, 8Ch; void *
0x180035750  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
