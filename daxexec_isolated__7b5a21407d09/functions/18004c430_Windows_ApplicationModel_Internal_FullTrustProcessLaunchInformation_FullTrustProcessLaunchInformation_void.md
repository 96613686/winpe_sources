# Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation::FullTrustProcessLaunchInformation(void)

- ea: `0x18004c430`
- end: `0x18004c6ff`
- name: `??0FullTrustProcessLaunchInformation@Internal@ApplicationModel@Windows@@QEAA@XZ`
- size: `719`
- prototype: `Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *__fastcall(Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d580`
- `0x18004d8d0`

## callees

- `0x180004f70`
- `0x18000ff24`
- `0x1800125f4`
- `0x180013510`
- `0x1800136dc`
- `0x180014e74`
- `0x1800165bc`
- `0x18004c430`
- `0x1800ae4d4`
- `0x1800ae644`
- `0x1800aeb4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c543`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c4c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c51f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c697`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c4c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c51f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c654`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004c5a0`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004c607`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004c5a0`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004c607`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *__fastcall Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation::FullTrustProcessLaunchInformation(
        Windows::ApplicationModel::Internal::FullTrustProcessLaunchInformation *this)
{
  char *v2; // r15
  WCHAR *v3; // rbx
  unsigned __int16 **v4; // rdx
  int CallingProcessHandle; // edi
  unsigned __int16 **v6; // r8
  char *v7; // rcx
  int ProcessAppId; // eax
  HANDLE v9; // rcx
  bool v10; // cc
  void *v11; // r14
  DWORD LastError; // edi
  int CallingProcessPackageFullName; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // r9
  WCHAR *v19; // rax
  WCHAR *v20; // r8
  unsigned int v21; // eax
  char *v23; // rcx
  int packageRelativeApplicationId; // [rsp+20h] [rbp-79h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-79h]
  unsigned int packageRelativeApplicationIdb; // [rsp+20h] [rbp-79h]
  HANDLE hObject; // [rsp+30h] [rbp-69h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+38h] [rbp-61h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+3Ch] [rbp-5Dh] BYREF
  _QWORD v30[4]; // [rsp+40h] [rbp-59h] BYREF
  PWSTR v31[4]; // [rsp+60h] [rbp-39h] BYREF
  PWSTR packageFamilyName[4]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v30[2] = this;
  *(_QWORD *)this = 0;
  v2 = (char *)this + 8;
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 7;
  *((_WORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 7;
  *((_WORD *)this + 20) = 0;
  v3 = 0;
  v30[0] = 0;
  hObject = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(7, 1, &hObject);
  v7 = (char *)hObject;
  if ( CallingProcessHandle >= 0 )
  {
    ProcessAppId = CallerIdentity::GetProcessAppId(hObject, v30, v6);
    CallingProcessHandle = ProcessAppId;
    if ( ProcessAppId != -2147023728 && ProcessAppId != -2147024891 )
    {
      if ( ProcessAppId >= 0 )
      {
        v23 = (char *)hObject;
        hObject = 0;
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v23);
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
    v9 = hObject;
    v10 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    hObject = 0;
    if ( v10 )
      CloseHandle(v9);
LABEL_10:
    v3 = (WCHAR *)v30[0];
    goto LABEL_11;
  }
  hObject = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
LABEL_11:
  if ( CallingProcessHandle < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      packageRelativeApplicationId);
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  CallingProcessPackageFullName = CallerIdentity::GetCallingProcessPackageFullName(this, v4);
  if ( CallingProcessPackageFullName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      packageRelativeApplicationId);
  packageFamilyNameLength = 0;
  packageRelativeApplicationIdLength = 0;
  v14 = ParseApplicationUserModelId(v3, &packageFamilyNameLength, 0, &packageRelativeApplicationIdLength, 0);
  if ( v14 != 122 && v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)v14,
      packageRelativeApplicationIda);
  std::wstring::wstring(packageFamilyName, packageFamilyNameLength - 1, v15, v16);
  std::wstring::wstring(v31, packageRelativeApplicationIdLength - 1, v17, v18);
  v19 = (WCHAR *)v31;
  if ( v31[3] > (PWSTR)7 )
    v19 = v31[0];
  v20 = (WCHAR *)packageFamilyName;
  if ( packageFamilyName[3] > (PWSTR)7 )
    v20 = packageFamilyName[0];
  v21 = ParseApplicationUserModelId(v3, &packageFamilyNameLength, v20, &packageRelativeApplicationIdLength, v19);
  if ( v21 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)v21,
      packageRelativeApplicationIdb);
  std::wstring::operator=(v2, packageFamilyName);
  std::wstring::operator=((char *)this + 40, v31);
  std::wstring::~wstring(v31);
  std::wstring::~wstring(packageFamilyName);
  if ( v3 )
    CoTaskMemFree(v3);
  return this;
}

```

## disassembly

```asm
0x18004c430  push    rbp
0x18004c432  push    rbx
0x18004c433  push    rsi
0x18004c434  push    rdi
0x18004c435  push    r12
0x18004c437  push    r13
0x18004c439  push    r14
0x18004c43b  push    r15
0x18004c43d  lea     rbp, [rsp-1Fh]
0x18004c442  sub     rsp, 0B8h
0x18004c449  mov     rax, cs:__security_cookie
0x18004c450  xor     rax, rsp
0x18004c453  mov     [rbp+57h+var_50], rax
0x18004c457  mov     rsi, rcx
0x18004c45a  mov     [rbp+57h+var_A0], rcx
0x18004c45e  xor     r13d, r13d
0x18004c461  mov     [rcx], r13
0x18004c464  lea     r15, [rcx+8]
0x18004c468  xorps   xmm0, xmm0
0x18004c46b  movups  xmmword ptr [r15], xmm0
0x18004c46f  mov     [r15+10h], r13
0x18004c473  lea     ecx, [r13+7]
0x18004c477  mov     [r15+18h], rcx
0x18004c47b  mov     [r15], r13w
0x18004c47f  lea     r12, [rsi+28h]
0x18004c483  movups  xmmword ptr [r12], xmm0
0x18004c488  mov     [r12+10h], r13
0x18004c48d  mov     [r12+18h], rcx
0x18004c492  mov     [r12], r13w
0x18004c497  mov     ebx, r13d
0x18004c49a  mov     [rbp+57h+var_B0], rbx
0x18004c49e  mov     [rbp+57h+hObject], r13
0x18004c4a2  lea     r8, [rbp+57h+hObject]
0x18004c4a6  lea     edx, [rcx-6]
0x18004c4a9  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18004c4ae  mov     edi, eax
0x18004c4b0  mov     rcx, [rbp+57h+hObject]; ProcessHandle
0x18004c4b4  test    eax, eax
0x18004c4b6  jns     short loc_18004C4D4
0x18004c4b8  mov     [rbp+57h+hObject], r13
0x18004c4bc  lea     rax, [rcx-1]
0x18004c4c0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004c4c4  ja      short loc_18004C52F
0x18004c4c6  call    cs:__imp_CloseHandle
0x18004c4cd  nop     dword ptr [rax+rax+00h]
0x18004c4d2  jmp     short loc_18004C52F
0x18004c4d4  lea     rdx, [rbp+57h+var_B0]; void *
0x18004c4d8  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18004c4dd  mov     edi, eax
0x18004c4df  cmp     eax, 80070490h
0x18004c4e4  jz      short loc_18004C50D
0x18004c4e6  cmp     eax, 80070005h
0x18004c4eb  jz      short loc_18004C50D
0x18004c4ed  test    eax, eax
0x18004c4ef  jns     loc_18004C685
0x18004c4f5  mov     rcx, [rbp+5Fh]; this
0x18004c4f9  mov     r9d, eax; char *
0x18004c4fc  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18004c503  mov     edx, 0E8h; void *
0x18004c508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c50d  mov     rcx, [rbp+57h+hObject]; hObject
0x18004c511  lea     rax, [rcx-1]
0x18004c515  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004c519  mov     [rbp+57h+hObject], r13
0x18004c51d  ja      short loc_18004C52B
0x18004c51f  call    cs:__imp_CloseHandle
0x18004c526  nop     dword ptr [rax+rax+00h]
0x18004c52b  mov     rbx, [rbp+57h+var_B0]
0x18004c52f  mov     rcx, [rbp+5Fh]; this
0x18004c533  test    edi, edi
0x18004c535  js      loc_18004C6C0
0x18004c53b  mov     r14, [rsi]
0x18004c53e  test    r14, r14
0x18004c541  jz      short loc_18004C56E
0x18004c543  call    cs:__imp_GetLastError
0x18004c54a  nop     dword ptr [rax+rax+00h]
0x18004c54f  mov     edi, eax
0x18004c551  mov     rcx, r14; pv
0x18004c554  call    cs:__imp_CoTaskMemFree
0x18004c55b  nop     dword ptr [rax+rax+00h]
0x18004c560  mov     ecx, edi; dwErrCode
0x18004c562  call    cs:__imp_SetLastError
0x18004c569  nop     dword ptr [rax+rax+00h]
0x18004c56e  mov     [rsi], r13
0x18004c571  mov     rcx, rsi; this
0x18004c574  call    ?GetCallingProcessPackageFullName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x18004c579  mov     rcx, [rbp+5Fh]; this
0x18004c57d  test    eax, eax
0x18004c57f  js      loc_18004C6D5
0x18004c585  mov     [rbp+57h+packageFamilyNameLength], r13d
0x18004c589  mov     [rbp+57h+packageRelativeApplicationIdLength], r13d
0x18004c58d  mov     qword ptr [rsp+0F0h+packageRelativeApplicationId], r13; unsigned int
0x18004c592  lea     r9, [rbp+57h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004c596  xor     r8d, r8d; packageFamilyName
0x18004c599  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18004c59d  mov     rcx, rbx; applicationUserModelId
0x18004c5a0  call    cs:__imp_ParseApplicationUserModelId
0x18004c5a7  nop     dword ptr [rax+rax+00h]
0x18004c5ac  cmp     eax, 7Ah ; 'z'
0x18004c5af  jz      short loc_18004C5BD
0x18004c5b1  mov     rcx, [rbp+5Fh]; this
0x18004c5b5  test    eax, eax
0x18004c5b7  jnz     loc_18004C6EA
0x18004c5bd  mov     edx, [rbp+57h+packageFamilyNameLength]
0x18004c5c0  dec     edx
0x18004c5c2  lea     rcx, [rbp+57h+packageFamilyName]
0x18004c5c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18004c5cb  nop
0x18004c5cc  mov     edx, [rbp+57h+packageRelativeApplicationIdLength]
0x18004c5cf  dec     edx
0x18004c5d1  lea     rcx, [rbp+57h+var_90]
0x18004c5d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18004c5da  nop
0x18004c5db  lea     rax, [rbp+57h+var_90]
0x18004c5df  cmp     [rbp+57h+var_78], 7
0x18004c5e4  cmova   rax, [rbp+57h+var_90]
0x18004c5e9  lea     r8, [rbp+57h+packageFamilyName]
0x18004c5ed  cmp     [rbp+57h+var_58], 7
0x18004c5f2  cmova   r8, [rbp+57h+packageFamilyName]; packageFamilyName
0x18004c5f7  mov     qword ptr [rsp+0F0h+packageRelativeApplicationId], rax; unsigned int
0x18004c5fc  lea     r9, [rbp+57h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004c600  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18004c604  mov     rcx, rbx; applicationUserModelId
0x18004c607  call    cs:__imp_ParseApplicationUserModelId
0x18004c60e  nop     dword ptr [rax+rax+00h]
0x18004c613  mov     rcx, [rbp+5Fh]; this
0x18004c617  test    eax, eax
0x18004c619  jnz     loc_18004C6AB
0x18004c61f  lea     rdx, [rbp+57h+packageFamilyName]
0x18004c623  mov     rcx, r15
0x18004c626  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004c62b  lea     rdx, [rbp+57h+var_90]
0x18004c62f  mov     rcx, r12
0x18004c632  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004c637  nop
0x18004c638  lea     rcx, [rbp+57h+var_90]; void *
0x18004c63c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c641  nop
0x18004c642  lea     rcx, [rbp+57h+packageFamilyName]; void *
0x18004c646  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c64b  nop
0x18004c64c  test    rbx, rbx
0x18004c64f  jz      short loc_18004C661
0x18004c651  mov     rcx, rbx; pv
0x18004c654  call    cs:__imp_CoTaskMemFree
0x18004c65b  nop     dword ptr [rax+rax+00h]
0x18004c660  nop
0x18004c661  mov     rax, rsi
0x18004c664  mov     rcx, [rbp+57h+var_50]
0x18004c668  xor     rcx, rsp; StackCookie
0x18004c66b  call    __security_check_cookie
0x18004c670  add     rsp, 0B8h
0x18004c677  pop     r15
0x18004c679  pop     r14
0x18004c67b  pop     r13
0x18004c67d  pop     r12
0x18004c67f  pop     rdi
0x18004c680  pop     rsi
0x18004c681  pop     rbx
0x18004c682  pop     rbp
0x18004c683  retn
0x18004c685  mov     rcx, [rbp+57h+hObject]; hObject
0x18004c689  mov     [rbp+57h+hObject], r13
0x18004c68d  lea     rax, [rcx-1]
0x18004c691  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004c695  ja      short loc_18004C6A3
0x18004c697  call    cs:__imp_CloseHandle
0x18004c69e  nop     dword ptr [rax+rax+00h]
0x18004c6a3  mov     edi, r13d
0x18004c6a6  jmp     loc_18004C52B
0x18004c6ab  mov     r9d, eax; char *
0x18004c6ae  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c6b5  mov     edx, 34h ; '4'; void *
0x18004c6ba  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004c6c0  mov     r9d, edi; char *
0x18004c6c3  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c6ca  mov     edx, 1Dh; void *
0x18004c6cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c6d5  mov     r9d, eax; char *
0x18004c6d8  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c6df  mov     edx, 1Eh; void *
0x18004c6e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c6ea  mov     r9d, eax; char *
0x18004c6ed  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c6f4  mov     edx, 2Bh ; '+'; void *
0x18004c6f9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
