# Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation::FullTrustProcessLaunchInformation(void)

- ea: `0x18004a844`
- end: `0x18004ab2a`
- name: `??0FullTrustProcessLaunchInformation@Internal@ApplicationModel@Windows@@QEAA@XZ`
- size: `742`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ba10`
- `0x18004bd60`

## callees

- `0x1800053a0`
- `0x18000e234`
- `0x180010a84`
- `0x180011820`
- `0x180011a64`
- `0x180013100`
- `0x1800149a4`
- `0x18004a844`
- `0x1800ad050`
- `0x1800ad1ac`
- `0x1800ad688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a961`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a980`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a8e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a93d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aac2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a8e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a93d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa72`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004a9be`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004aa25`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004a9be`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004aa25`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *__fastcall Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation::FullTrustProcessLaunchInformation(
        Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *this)
{
  char *v2; // r15
  char *v3; // r12
  WCHAR *v4; // rbx
  unsigned __int16 **v5; // rdx
  int CallingProcessHandle; // edi
  unsigned __int16 **v7; // r8
  char *v8; // rcx
  int ProcessAppId; // eax
  HANDLE v10; // rcx
  bool v11; // cc
  void *v12; // r14
  DWORD LastError; // edi
  int CallingProcessPackageFullName; // eax
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  WCHAR *v20; // rax
  WCHAR *v21; // r8
  unsigned int v22; // eax
  char *v24; // rcx
  int packageRelativeApplicationId; // [rsp+28h] [rbp-59h]
  unsigned int packageRelativeApplicationIda; // [rsp+28h] [rbp-59h]
  unsigned int packageRelativeApplicationIdb; // [rsp+28h] [rbp-59h]
  HANDLE hObject; // [rsp+38h] [rbp-49h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+40h] [rbp-41h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+44h] [rbp-3Dh] BYREF
  _QWORD v31[4]; // [rsp+48h] [rbp-39h] BYREF
  PWSTR v32[4]; // [rsp+68h] [rbp-19h] BYREF
  PWSTR packageFamilyName[4]; // [rsp+88h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v31[2] = this;
  *(_QWORD *)this = 0;
  v2 = (char *)this + 8;
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 7;
  *((_WORD *)this + 4) = 0;
  v3 = (char *)this + 40;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 7;
  *((_WORD *)this + 20) = 0;
  v4 = 0;
  v31[0] = 0;
  hObject = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, 1, &hObject);
  v8 = (char *)hObject;
  if ( CallingProcessHandle >= 0 )
  {
    ProcessAppId = CallerIdentity::GetProcessAppId(hObject, v31, v7);
    CallingProcessHandle = ProcessAppId;
    if ( ProcessAppId != -2147023728 && ProcessAppId != -2147024891 )
    {
      if ( ProcessAppId >= 0 )
      {
        v24 = (char *)hObject;
        hObject = 0;
        if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v24);
        CallingProcessHandle = 0;
        goto LABEL_10;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)ProcessAppId,
        packageRelativeApplicationId);
    }
    v10 = hObject;
    v11 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    hObject = 0;
    if ( v11 )
      CloseHandle(v10);
LABEL_10:
    v4 = (WCHAR *)v31[0];
    goto LABEL_11;
  }
  hObject = 0;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
LABEL_11:
  if ( CallingProcessHandle < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      packageRelativeApplicationId);
  v12 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  CallingProcessPackageFullName = CallerIdentity::GetCallingProcessPackageFullName(this, v5);
  if ( CallingProcessPackageFullName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      packageRelativeApplicationId);
  packageFamilyNameLength = 0;
  packageRelativeApplicationIdLength = 0;
  v15 = ParseApplicationUserModelId(v4, &packageFamilyNameLength, 0, &packageRelativeApplicationIdLength, 0);
  if ( v15 != 122 && v15 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)v15,
      packageRelativeApplicationIda);
  std::wstring::wstring(packageFamilyName, packageFamilyNameLength - 1, v16, v17);
  std::wstring::wstring(v32, packageRelativeApplicationIdLength - 1, v18, v19);
  v20 = (WCHAR *)v32;
  if ( v32[3] > (PWSTR)7 )
    v20 = v32[0];
  v21 = (WCHAR *)packageFamilyName;
  if ( packageFamilyName[3] > (PWSTR)7 )
    v21 = packageFamilyName[0];
  v22 = ParseApplicationUserModelId(v4, &packageFamilyNameLength, v21, &packageRelativeApplicationIdLength, v20);
  if ( v22 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)v22,
      packageRelativeApplicationIdb);
  std::wstring::operator=(v2, packageFamilyName);
  std::wstring::operator=(v3, v32);
  std::wstring::~wstring(v32);
  std::wstring::~wstring(packageFamilyName);
  if ( v4 )
    CoTaskMemFree(v4);
  return this;
}

```

## disassembly

```asm
0x18004a844  mov     rax, rsp
0x18004a847  mov     [rax+10h], rbx
0x18004a84b  mov     [rax+18h], rsi
0x18004a84f  mov     [rax+20h], rdi
0x18004a853  push    rbp
0x18004a854  push    r12
0x18004a856  push    r13
0x18004a858  push    r14
0x18004a85a  push    r15
0x18004a85c  lea     rbp, [rax-5Fh]
0x18004a860  sub     rsp, 0B0h
0x18004a867  mov     rax, cs:__security_cookie
0x18004a86e  xor     rax, rsp
0x18004a871  mov     [rbp+57h+var_30], rax
0x18004a875  mov     rsi, rcx
0x18004a878  mov     [rbp+57h+var_80], rcx
0x18004a87c  xor     r13d, r13d
0x18004a87f  mov     [rcx], r13
0x18004a882  lea     r15, [rcx+8]
0x18004a886  xorps   xmm0, xmm0
0x18004a889  movups  xmmword ptr [r15], xmm0
0x18004a88d  mov     [r15+10h], r13
0x18004a891  lea     eax, [r13+7]
0x18004a895  mov     [r15+18h], rax
0x18004a899  mov     [r15], r13w
0x18004a89d  lea     r12, [rcx+28h]
0x18004a8a1  movups  xmmword ptr [r12], xmm0
0x18004a8a6  mov     [r12+10h], r13
0x18004a8ab  mov     [r12+18h], rax
0x18004a8b0  mov     [r12], r13w
0x18004a8b5  mov     ebx, r13d
0x18004a8b8  mov     [rbp+57h+var_90], rbx
0x18004a8bc  mov     [rbp+57h+hObject], r13
0x18004a8c0  lea     r8, [rbp+57h+hObject]
0x18004a8c4  lea     edx, [rax-6]
0x18004a8c7  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18004a8cc  mov     edi, eax
0x18004a8ce  mov     rcx, [rbp+57h+hObject]; ProcessHandle
0x18004a8d2  test    eax, eax
0x18004a8d4  jns     short loc_18004A8F2
0x18004a8d6  mov     [rbp+57h+hObject], r13
0x18004a8da  lea     rax, [rcx-1]
0x18004a8de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a8e2  ja      short loc_18004A94D
0x18004a8e4  call    cs:__imp_CloseHandle
0x18004a8eb  nop     dword ptr [rax+rax+00h]
0x18004a8f0  jmp     short loc_18004A94D
0x18004a8f2  lea     rdx, [rbp+57h+var_90]; void *
0x18004a8f6  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18004a8fb  mov     edi, eax
0x18004a8fd  cmp     eax, 80070490h
0x18004a902  jz      short loc_18004A92B
0x18004a904  cmp     eax, 80070005h
0x18004a909  jz      short loc_18004A92B
0x18004a90b  test    eax, eax
0x18004a90d  jns     loc_18004AAB0
0x18004a913  mov     rcx, [rbp+5Fh]; this
0x18004a917  mov     r9d, eax; char *
0x18004a91a  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18004a921  mov     edx, 0E8h; void *
0x18004a926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a92b  mov     rcx, [rbp+57h+hObject]; hObject
0x18004a92f  lea     rax, [rcx-1]
0x18004a933  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a937  mov     [rbp+57h+hObject], r13
0x18004a93b  ja      short loc_18004A949
0x18004a93d  call    cs:__imp_CloseHandle
0x18004a944  nop     dword ptr [rax+rax+00h]
0x18004a949  mov     rbx, [rbp+57h+var_90]
0x18004a94d  mov     rcx, [rbp+5Fh]; this
0x18004a951  test    edi, edi
0x18004a953  js      loc_18004AAEB
0x18004a959  mov     r14, [rsi]
0x18004a95c  test    r14, r14
0x18004a95f  jz      short loc_18004A98C
0x18004a961  call    cs:__imp_GetLastError
0x18004a968  nop     dword ptr [rax+rax+00h]
0x18004a96d  mov     edi, eax
0x18004a96f  mov     rcx, r14; pv
0x18004a972  call    cs:__imp_CoTaskMemFree
0x18004a979  nop     dword ptr [rax+rax+00h]
0x18004a97e  mov     ecx, edi; dwErrCode
0x18004a980  call    cs:__imp_SetLastError
0x18004a987  nop     dword ptr [rax+rax+00h]
0x18004a98c  mov     [rsi], r13
0x18004a98f  mov     rcx, rsi; this
0x18004a992  call    ?GetCallingProcessPackageFullName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x18004a997  mov     rcx, [rbp+5Fh]; this
0x18004a99b  test    eax, eax
0x18004a99d  js      loc_18004AB00
0x18004a9a3  mov     [rbp+57h+packageFamilyNameLength], r13d
0x18004a9a7  mov     [rbp+57h+packageRelativeApplicationIdLength], r13d
0x18004a9ab  mov     qword ptr [rsp+0D0h+packageRelativeApplicationId], r13; unsigned int
0x18004a9b0  lea     r9, [rbp+57h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004a9b4  xor     r8d, r8d; packageFamilyName
0x18004a9b7  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18004a9bb  mov     rcx, rbx; applicationUserModelId
0x18004a9be  call    cs:__imp_ParseApplicationUserModelId
0x18004a9c5  nop     dword ptr [rax+rax+00h]
0x18004a9ca  cmp     eax, 7Ah ; 'z'
0x18004a9cd  jz      short loc_18004A9DB
0x18004a9cf  mov     rcx, [rbp+5Fh]; this
0x18004a9d3  test    eax, eax
0x18004a9d5  jnz     loc_18004AB15
0x18004a9db  mov     edx, [rbp+57h+packageFamilyNameLength]
0x18004a9de  dec     edx
0x18004a9e0  lea     rcx, [rbp+57h+packageFamilyName]
0x18004a9e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18004a9e9  nop
0x18004a9ea  mov     edx, [rbp+57h+packageRelativeApplicationIdLength]
0x18004a9ed  dec     edx
0x18004a9ef  lea     rcx, [rbp+57h+var_70]
0x18004a9f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18004a9f8  nop
0x18004a9f9  lea     rax, [rbp+57h+var_70]
0x18004a9fd  cmp     [rbp+57h+var_58], 7
0x18004aa02  cmova   rax, [rbp+57h+var_70]
0x18004aa07  lea     r8, [rbp+57h+packageFamilyName]
0x18004aa0b  cmp     [rbp+57h+var_38], 7
0x18004aa10  cmova   r8, [rbp+57h+packageFamilyName]; packageFamilyName
0x18004aa15  mov     qword ptr [rsp+0D0h+packageRelativeApplicationId], rax; unsigned int
0x18004aa1a  lea     r9, [rbp+57h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004aa1e  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18004aa22  mov     rcx, rbx; applicationUserModelId
0x18004aa25  call    cs:__imp_ParseApplicationUserModelId
0x18004aa2c  nop     dword ptr [rax+rax+00h]
0x18004aa31  mov     rcx, [rbp+5Fh]; this
0x18004aa35  test    eax, eax
0x18004aa37  jnz     loc_18004AAD6
0x18004aa3d  lea     rdx, [rbp+57h+packageFamilyName]
0x18004aa41  mov     rcx, r15
0x18004aa44  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004aa49  lea     rdx, [rbp+57h+var_70]
0x18004aa4d  mov     rcx, r12
0x18004aa50  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004aa55  nop
0x18004aa56  lea     rcx, [rbp+57h+var_70]; void *
0x18004aa5a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004aa5f  nop
0x18004aa60  lea     rcx, [rbp+57h+packageFamilyName]; void *
0x18004aa64  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004aa69  nop
0x18004aa6a  test    rbx, rbx
0x18004aa6d  jz      short loc_18004AA7F
0x18004aa6f  mov     rcx, rbx; pv
0x18004aa72  call    cs:__imp_CoTaskMemFree
0x18004aa79  nop     dword ptr [rax+rax+00h]
0x18004aa7e  nop
0x18004aa7f  mov     rax, rsi
0x18004aa82  mov     rcx, [rbp+57h+var_30]
0x18004aa86  xor     rcx, rsp; StackCookie
0x18004aa89  call    __security_check_cookie
0x18004aa8e  lea     r11, [rsp+0D0h+var_20]
0x18004aa96  mov     rbx, [r11+38h]
0x18004aa9a  mov     rsi, [r11+40h]
0x18004aa9e  mov     rdi, [r11+48h]
0x18004aaa2  mov     rsp, r11
0x18004aaa5  pop     r15
0x18004aaa7  pop     r14
0x18004aaa9  pop     r13
0x18004aaab  pop     r12
0x18004aaad  pop     rbp
0x18004aaae  retn
0x18004aab0  mov     rcx, [rbp+57h+hObject]; hObject
0x18004aab4  mov     [rbp+57h+hObject], r13
0x18004aab8  lea     rax, [rcx-1]
0x18004aabc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004aac0  ja      short loc_18004AACE
0x18004aac2  call    cs:__imp_CloseHandle
0x18004aac9  nop     dword ptr [rax+rax+00h]
0x18004aace  mov     edi, r13d
0x18004aad1  jmp     loc_18004A949
0x18004aad6  mov     r9d, eax; char *
0x18004aad9  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004aae0  mov     edx, 34h ; '4'; void *
0x18004aae5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004aaeb  mov     r9d, edi; char *
0x18004aaee  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004aaf5  mov     edx, 1Dh; void *
0x18004aafa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ab00  mov     r9d, eax; char *
0x18004ab03  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004ab0a  mov     edx, 1Eh; void *
0x18004ab0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ab15  mov     r9d, eax; char *
0x18004ab18  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004ab1f  mov     edx, 2Bh ; '+'; void *
0x18004ab24  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
