# InitializeCVMapForDmSession(ushort const *)

- ea: `0x1800111a8`
- end: `0x180011357`
- name: `?InitializeCVMapForDmSession@@YAJPEBG@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800382e8`

## callees

- `0x1800071c0`
- `0x18000dd20`
- `0x1800111a8`
- `0x1800118f8`
- `0x180011938`
- `0x18002d998`
- `0x1800404a8`
- `0x180075458`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011301`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011301`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800111ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011252`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800111ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011252`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011219`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001127f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011337`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011347`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011219`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001127f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011337`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011347`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitializeCVMapForDmSession(const unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  unsigned int v3; // eax
  int v4; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  unsigned __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  HKEY v15; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)DMGetKnownRegPath(0);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x2001Fu, &hKey);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xA5,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
           (const char *)v3,
           phkResult);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v4;
  }
  v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v15,
    0);
  v6 = RegOpenKeyExW(hKey, a1, 0, 0x20019u, &v15);
  if ( v6 )
  {
    v7 = 175;
LABEL_8:
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
           (const char *)v6,
           phkResulta);
    goto LABEL_9;
  }
  v11 = 0;
  cbData = 0;
  v4 = StringCbLengthW(a1, 0xFFFFFFFE, &v11);
  if ( v4 < 0 )
  {
    v8 = 180;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)(unsigned int)v4,
      phkResulta);
LABEL_9:
    if ( v15 )
      RegCloseKey(v15);
    goto LABEL_3;
  }
  v4 = ULongLongToULong(v11, &cbData);
  if ( v4 < 0 )
  {
    v8 = 182;
    goto LABEL_13;
  }
  v6 = RegSetValueExW(hKey, L"CurrentEnrollmentId", 0, 1u, (const BYTE *)a1, cbData);
  if ( v6 )
  {
    v7 = 191;
    goto LABEL_8;
  }
  v4 = InitializeCVForDmComponents(a1, hKey);
  if ( v4 < 0 )
  {
    v8 = 194;
    goto LABEL_13;
  }
  if ( v15 )
    RegCloseKey(v15);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800111a8  push    rbp
0x1800111aa  push    rbx
0x1800111ab  push    rdi
0x1800111ac  mov     rbp, rsp
0x1800111af  sub     rsp, 40h
0x1800111b3  mov     rdi, rcx
0x1800111b6  mov     [rbp+hKey], 0
0x1800111be  xor     edx, edx
0x1800111c0  lea     rcx, [rbp+hKey]
0x1800111c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800111c9  xor     ecx, ecx
0x1800111cb  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800111d0  lea     rcx, [rbp+hKey]
0x1800111d4  mov     [rsp+40h+phkResult], rcx; unsigned int
0x1800111d9  mov     r9d, 2001Fh; samDesired
0x1800111df  xor     r8d, r8d; ulOptions
0x1800111e2  mov     rdx, rax; lpSubKey
0x1800111e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800111ec  call    cs:__imp_RegOpenKeyExW
0x1800111f2  test    eax, eax
0x1800111f4  jz      short loc_180011226
0x1800111f6  mov     rcx, [rbp+18h]; this
0x1800111fa  mov     r9d, eax; char *
0x1800111fd  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x180011204  mov     edx, 0A5h; void *
0x180011209  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001120e  mov     ebx, eax
0x180011210  mov     rcx, [rbp+hKey]; hKey
0x180011214  test    rcx, rcx
0x180011217  jz      short loc_18001121F
0x180011219  call    cs:__imp_RegCloseKey
0x18001121f  mov     eax, ebx
0x180011221  jmp     loc_18001134F
0x180011226  mov     [rbp+arg_18], 0
0x18001122e  xor     edx, edx
0x180011230  lea     rcx, [rbp+arg_18]
0x180011234  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180011239  lea     rax, [rbp+arg_18]
0x18001123d  mov     [rsp+40h+phkResult], rax; int
0x180011242  mov     r9d, 20019h; samDesired
0x180011248  xor     r8d, r8d; ulOptions
0x18001124b  mov     rdx, rdi; lpSubKey
0x18001124e  mov     rcx, [rbp+hKey]; hKey
0x180011252  call    cs:__imp_RegOpenKeyExW
0x180011258  test    eax, eax
0x18001125a  jz      short loc_180011287
0x18001125c  mov     edx, 0AFh; void *
0x180011261  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x180011268  mov     r9d, eax; char *
0x18001126b  mov     rcx, [rbp+18h]; this
0x18001126f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011274  mov     ebx, eax
0x180011276  mov     rcx, [rbp+arg_18]; hKey
0x18001127a  test    rcx, rcx
0x18001127d  jz      short loc_180011210
0x18001127f  call    cs:__imp_RegCloseKey
0x180011285  jmp     short loc_180011210
0x180011287  mov     [rbp+var_10], 0
0x18001128f  mov     [rbp+arg_8], 0
0x180011296  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18001129a  mov     edx, 0FFFFFFFEh; unsigned __int64
0x18001129f  mov     rcx, rdi; unsigned __int16 *
0x1800112a2  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800112a7  mov     ebx, eax
0x1800112a9  test    eax, eax
0x1800112ab  jns     short loc_1800112C7
0x1800112ad  mov     edx, 0B4h; void *
0x1800112b2  mov     rcx, [rbp+18h]; this
0x1800112b6  mov     r9d, ebx; char *
0x1800112b9  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x1800112c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112c5  jmp     short loc_180011276
0x1800112c7  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800112cb  mov     rcx, [rbp+var_10]; unsigned __int64
0x1800112cf  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800112d4  mov     ebx, eax
0x1800112d6  test    eax, eax
0x1800112d8  jns     short loc_1800112E1
0x1800112da  mov     edx, 0B6h
0x1800112df  jmp     short loc_1800112B2
0x1800112e1  mov     eax, [rbp+arg_8]
0x1800112e4  mov     [rsp+40h+cbData], eax; cbData
0x1800112e8  mov     [rsp+40h+phkResult], rdi; lpData
0x1800112ed  mov     r9d, 1; dwType
0x1800112f3  xor     r8d, r8d; Reserved
0x1800112f6  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1800112fd  mov     rcx, [rbp+hKey]; hKey
0x180011301  call    cs:__imp_RegSetValueExW
0x180011307  test    eax, eax
0x180011309  jz      short loc_180011315
0x18001130b  mov     edx, 0BFh
0x180011310  jmp     loc_180011261
0x180011315  mov     rdx, [rbp+hKey]; HKEY
0x180011319  mov     rcx, rdi; unsigned __int16 *
0x18001131c  call    ?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z; InitializeCVForDmComponents(ushort const *,HKEY__ *)
0x180011321  mov     ebx, eax
0x180011323  test    eax, eax
0x180011325  jns     short loc_18001132E
0x180011327  mov     edx, 0C2h
0x18001132c  jmp     short loc_1800112B2
0x18001132e  mov     rcx, [rbp+arg_18]; hKey
0x180011332  test    rcx, rcx
0x180011335  jz      short loc_18001133E
0x180011337  call    cs:__imp_RegCloseKey
0x18001133d  nop
0x18001133e  mov     rcx, [rbp+hKey]; hKey
0x180011342  test    rcx, rcx
0x180011345  jz      short loc_18001134D
0x180011347  call    cs:__imp_RegCloseKey
0x18001134d  xor     eax, eax
0x18001134f  add     rsp, 40h
0x180011353  pop     rdi
0x180011354  pop     rbx
0x180011355  pop     rbp
0x180011356  retn
```
