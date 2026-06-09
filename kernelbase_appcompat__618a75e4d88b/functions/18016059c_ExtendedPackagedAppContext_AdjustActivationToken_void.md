# ExtendedPackagedAppContext::AdjustActivationToken(void *)

- ea: `0x18016059c`
- end: `0x1801607f7`
- name: `?AdjustActivationToken@ExtendedPackagedAppContext@@AEAAJPEAX@Z`
- size: `603`
- prototype: `__int64 __fastcall(ExtendedPackagedAppContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180004458`

## callees

- `0x18000669c`
- `0x1800183d4`
- `0x180019350`
- `0x180057738`
- `0x18005b2c4`
- `0x180081fc0`
- `0x1800cedb0`
- `0x180110b9c`
- `0x18012c6b8`
- `0x1801369c9`
- `0x18016059c`
- `0x180194f10`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18016075f`
- `ntdll!_wcsicmp` at `0x18016075f`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x1801606b3`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180160706`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x1801607aa`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x1801607ba`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x1801606b3`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180160706`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x1801607aa`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x1801607ba`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x180160634`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x1801606d5`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x180160634`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x1801606d5`

## string_xrefs

- `0x180160600`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180160682`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18016069a`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x1801606f3`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`

## pseudocode

```c
__int64 __fastcall ExtendedPackagedAppContext::AdjustActivationToken(ExtendedPackagedAppContext *this, void *a2)
{
  bool v2; // zf
  HANDLE v3; // rdi
  const char *v5; // r9
  unsigned int LastError; // ebx
  __int64 v7; // rcx
  unsigned int PackageActivationTokenForFilePath2; // esi
  const unsigned __int16 *v9; // r8
  int PackagedDataForFileInternal; // eax
  unsigned int v11; // esi
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int PackageFullNameFromToken; // eax
  __int128 v15; // xmm1
  HANDLE token[2]; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR packageFullName[128]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v2 = *((_DWORD *)this + 137) == 4;
  v3 = a2;
  TokenHandle = 0;
  if ( !v2 && !a2 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&TokenHandle);
    if ( !OpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xAFu, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3A9,
                    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                    v5);
      goto LABEL_19;
    }
    v3 = TokenHandle;
  }
  v7 = *((_QWORD *)this + 65);
  *(_OWORD *)token = 0;
  PackageActivationTokenForFilePath2 = BasepGetPackageActivationTokenForFilePath2(v7, v3, token);
  if ( PackageActivationTokenForFilePath2 - 2 <= 1 && !PathFileExistsW(*((LPCWSTR *)this + 65)) )
  {
    v9 = (const unsigned __int16 *)*((_QWORD *)this + 79);
    *(_BYTE *)this = 0;
    PackagedDataForFileInternal = PackagedCreateProcess::GetPackagedDataForFileInternal(0, v3, v9, this);
    v11 = PackagedDataForFileInternal;
    if ( PackagedDataForFileInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)PackagedDataForFileInternal,
        (int)token[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)v11,
        (int)token[0]);
      BasepFreeActivationTokenInfo(token);
      LastError = v11;
      goto LABEL_19;
    }
    PackageActivationTokenForFilePath2 = BasepGetPackageActivationTokenForFilePath2(*((_QWORD *)this + 65), v3, token);
  }
  if ( PackageActivationTokenForFilePath2 )
  {
    v12 = PackageActivationTokenForFilePath2;
    v13 = 953;
LABEL_13:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                  (const char *)v12,
                  (unsigned int)token[0]);
    BasepFreeActivationTokenInfo(token);
    goto LABEL_19;
  }
  memset_0(packageFullName, 0, sizeof(packageFullName));
  packageFullNameLength = 128;
  PackageFullNameFromToken = GetPackageFullNameFromToken(token[0], &packageFullNameLength, packageFullName);
  if ( PackageFullNameFromToken )
  {
    v12 = PackageFullNameFromToken;
    v13 = 957;
    goto LABEL_13;
  }
  if ( _wcsicmp(packageFullName, (const wchar_t *)this + 131) )
  {
    BasepFreeActivationTokenInfo(token);
    LastError = -2147023728;
  }
  else
  {
    v15 = *((_OWORD *)this + 40);
    *((_OWORD *)this + 40) = *(_OWORD *)token;
    *((_QWORD *)this + 69) = *((_QWORD *)this + 80);
    *((_QWORD *)this + 70) = *((_QWORD *)this + 81);
    *(_OWORD *)token = v15;
    BasepFreeActivationTokenInfo(token);
    LastError = 0;
  }
LABEL_19:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18016059c  mov     [rsp-8+arg_10], rbx
0x1801605a1  push    rbp
0x1801605a2  push    rsi
0x1801605a3  push    rdi
0x1801605a4  lea     rbp, [rsp-50h]
0x1801605a9  sub     rsp, 150h
0x1801605b0  mov     rax, cs:__security_cookie
0x1801605b7  xor     rax, rsp
0x1801605ba  mov     [rbp+60h+var_20], rax
0x1801605be  cmp     dword ptr [rcx+224h], 4
0x1801605c5  mov     rdi, rdx
0x1801605c8  mov     rbx, rcx
0x1801605cb  mov     [rsp+160h+TokenHandle], 0
0x1801605d4  jz      short loc_18016061D
0x1801605d6  test    rdx, rdx
0x1801605d9  jnz     short loc_18016061D
0x1801605db  lea     rcx, [rsp+160h+TokenHandle]
0x1801605e0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801605e5  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x1801605ea  mov     edx, 0AFh; DesiredAccess
0x1801605ef  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1801605f3  call    OpenProcessToken
0x1801605f8  test    eax, eax
0x1801605fa  jnz     short loc_180160618
0x1801605fc  mov     rcx, [rbp+68h]; this
0x180160600  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180160607  mov     edx, 3A9h; void *
0x18016060c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180160611  mov     ebx, eax
0x180160613  jmp     loc_1801607CB
0x180160618  mov     rdi, [rsp+160h+TokenHandle]
0x18016061d  mov     rcx, [rbx+208h]
0x180160624  lea     r8, [rsp+160h+token]
0x180160629  xorps   xmm0, xmm0
0x18016062c  mov     rdx, rdi
0x18016062f  movups  xmmword ptr [rsp+160h+token], xmm0; unsigned int
0x180160634  call    cs:__imp_BasepGetPackageActivationTokenForFilePath2
0x18016063b  nop     dword ptr [rax+rax+00h]
0x180160640  mov     esi, eax
0x180160642  lea     ecx, [rax-2]
0x180160645  cmp     ecx, 1
0x180160648  ja      loc_1801606E3
0x18016064e  mov     rcx, [rbx+208h]; pszPath
0x180160655  call    PathFileExistsW
0x18016065a  test    eax, eax
0x18016065c  jnz     loc_1801606E3
0x180160662  mov     r8, [rbx+278h]; unsigned __int16 *
0x180160669  mov     r9, rbx; struct ExtendedPackagedAppContext *
0x18016066c  mov     rdx, rdi; void *
0x18016066f  mov     [rbx], al
0x180160671  xor     ecx, ecx; Source
0x180160673  call    ?GetPackagedDataForFileInternal@PackagedCreateProcess@@CAJPEBGPEAX0PEAVExtendedPackagedAppContext@@@Z; PackagedCreateProcess::GetPackagedDataForFileInternal(ushort const *,void *,ushort const *,ExtendedPackagedAppContext *)
0x180160678  mov     esi, eax
0x18016067a  test    eax, eax
0x18016067c  jns     short loc_1801606C6
0x18016067e  mov     rcx, [rbp+68h]; this
0x180160682  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180160689  mov     r9d, eax; char *
0x18016068c  mov     edx, 170h; void *
0x180160691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160696  mov     rcx, [rbp+68h]; this
0x18016069a  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x1801606a1  mov     r9d, esi; char *
0x1801606a4  mov     edx, 3B4h; void *
0x1801606a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801606ae  lea     rcx, [rsp+160h+token]
0x1801606b3  call    cs:__imp_BasepFreeActivationTokenInfo
0x1801606ba  nop     dword ptr [rax+rax+00h]
0x1801606bf  mov     ebx, esi
0x1801606c1  jmp     loc_1801607CB
0x1801606c6  mov     rcx, [rbx+208h]
0x1801606cd  lea     r8, [rsp+160h+token]
0x1801606d2  mov     rdx, rdi
0x1801606d5  call    cs:__imp_BasepGetPackageActivationTokenForFilePath2
0x1801606dc  nop     dword ptr [rax+rax+00h]
0x1801606e1  mov     esi, eax
0x1801606e3  test    esi, esi
0x1801606e5  jz      short loc_180160717
0x1801606e7  mov     r9d, esi; char *
0x1801606ea  mov     edx, 3B9h; void *
0x1801606ef  mov     rcx, [rbp+68h]; this
0x1801606f3  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x1801606fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801606ff  lea     rcx, [rsp+160h+token]
0x180160704  mov     ebx, eax
0x180160706  call    cs:__imp_BasepFreeActivationTokenInfo
0x18016070d  nop     dword ptr [rax+rax+00h]
0x180160712  jmp     loc_1801607CB
0x180160717  xor     edx, edx; Val
0x180160719  lea     rcx, [rsp+160h+packageFullName]; void *
0x18016071e  mov     r8d, 100h; Size
0x180160724  call    memset_0
0x180160729  mov     rcx, [rsp+160h+token]; token
0x18016072e  lea     r8, [rsp+160h+packageFullName]; packageFullName
0x180160733  lea     rdx, [rsp+160h+packageFullNameLength]; packageFullNameLength
0x180160738  mov     [rsp+160h+packageFullNameLength], 80h
0x180160740  call    GetPackageFullNameFromToken
0x180160745  test    eax, eax
0x180160747  jz      short loc_180160753
0x180160749  mov     r9d, eax
0x18016074c  mov     edx, 3BDh
0x180160751  jmp     short loc_1801606EF
0x180160753  lea     rdx, [rbx+106h]; String2
0x18016075a  lea     rcx, [rsp+160h+packageFullName]; String1
0x18016075f  call    cs:__imp__wcsicmp
0x180160766  nop     dword ptr [rax+rax+00h]
0x18016076b  lea     rcx, [rsp+160h+token]
0x180160770  test    eax, eax
0x180160772  jnz     short loc_1801607BA
0x180160774  movups  xmm1, xmmword ptr [rbx+280h]
0x18016077b  movaps  xmm0, xmmword ptr [rsp+160h+token]
0x180160780  movdqu  xmmword ptr [rbx+280h], xmm0
0x180160788  mov     rax, [rbx+280h]
0x18016078f  mov     [rbx+228h], rax
0x180160796  mov     rax, [rbx+288h]
0x18016079d  mov     [rbx+230h], rax
0x1801607a4  movdqa  xmmword ptr [rsp+160h+token], xmm1
0x1801607aa  call    cs:__imp_BasepFreeActivationTokenInfo
0x1801607b1  nop     dword ptr [rax+rax+00h]
0x1801607b6  xor     ebx, ebx
0x1801607b8  jmp     short loc_1801607CB
0x1801607ba  call    cs:__imp_BasepFreeActivationTokenInfo
0x1801607c1  nop     dword ptr [rax+rax+00h]
0x1801607c6  mov     ebx, 80070490h
0x1801607cb  lea     rcx, [rsp+160h+TokenHandle]
0x1801607d0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801607d5  mov     eax, ebx
0x1801607d7  mov     rcx, [rbp+60h+var_20]
0x1801607db  xor     rcx, rsp; StackCookie
0x1801607de  call    __security_check_cookie
0x1801607e3  mov     rbx, [rsp+160h+arg_10]
0x1801607eb  add     rsp, 150h
0x1801607f2  pop     rdi
0x1801607f3  pop     rsi
0x1801607f4  pop     rbp
0x1801607f5  retn
```
