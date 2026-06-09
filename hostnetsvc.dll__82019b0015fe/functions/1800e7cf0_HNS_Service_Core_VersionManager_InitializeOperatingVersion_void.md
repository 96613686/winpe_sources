# HNS::Service::Core::VersionManager::InitializeOperatingVersion(void)

- ea: `0x1800e7cf0`
- end: `0x1800e7fbf`
- name: `?InitializeOperatingVersion@VersionManager@Core@Service@HNS@@IEAAXXZ`
- size: `719`
- prototype: `void __fastcall(HNS::Service::Core::VersionManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e7c50`

## callees

- `0x1800759d8`
- `0x180075aac`
- `0x18007c420`
- `0x18007dd40`
- `0x1800805c4`
- `0x1800cfdc4`
- `0x1800e7c40`
- `0x1800e7cf0`
- `0x1800e7fc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7e98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e7e98`

## string_xrefs

- `0x1800e7d10`: `HNS::Service::Core::VersionManager::InitializeOperatingVersion`
- `0x1800e7f05`: `HNS::Service::Core::VersionManager::InitializeOperatingVersion`
- `0x1800e7fa1`: `Failed to get HNSCompatibleMajorVersion.`
- `0x1800e7f26`: `Failed to get HNSCompatibleMinorVersion.`
- `0x1800e7f58`: `HNSCurrentVersion(%d.%d) is less than HNSCompatibleVersion(%d.%d).`
- `0x1800e7da9`: `Missing HNSCurrentMajorVersion from HNS service key path. Falling back to default version: %d`
- `0x1800e7dcd`: `Missing HNSCurrentMajorVersion from HNS service key path. Falling back to default version: %d`
- `0x1800e7e2c`: `Missing HNSCurrentMinorVersion from HNS service key path. Falling back to default version: %d`
- `0x1800e7f32`: `onecore\vm\dv\net\hns\service\core\versionmanager.cpp`
- `0x1800e7f6a`: `onecore\vm\dv\net\hns\service\core\versionmanager.cpp`
- `0x1800e7f8b`: `onecore\vm\dv\net\hns\service\core\versionmanager.cpp`
- `0x1800e7fad`: `onecore\vm\dv\net\hns\service\core\versionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HNS::Service::Core::VersionManager::InitializeOperatingVersion(
        HNS::Service::Core::VersionManager *this)
{
  HKEY *HnsServiceKey; // rax
  __int64 v3; // rsi
  __int64 v4; // rax
  unsigned int v5; // ecx
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // edi
  __int64 v9; // rax
  unsigned int LastStatus; // eax
  char *v11; // [rsp+28h] [rbp-31h]
  unsigned int v12; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  const unsigned __int16 *v14; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+68h] [rbp+Fh]
  HKEY v16[2]; // [rsp+70h] [rbp+17h] BYREF
  int v17; // [rsp+80h] [rbp+27h]
  char v18; // [rsp+84h] [rbp+2Bh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned int v20; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+77h] BYREF
  unsigned int v22; // [rsp+D8h] [rbp+7Fh] BYREF

  HNSTraceProvider::TraceEnter("HNS::Service::Core::VersionManager::InitializeOperatingVersion", 0x50u);
  v20 = 0;
  v21 = 0;
  v12 = 0;
  v22 = 0;
  HnsServiceKey = (HKEY *)HNS::GetHnsServiceKey(&hKey, 0, 131097);
  v16[0] = *HnsServiceKey;
  *HnsServiceKey = 0;
  v17 = 0;
  v18 = 1;
  if ( hKey )
    RegCloseKey(hKey);
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( HNS::Service::Core::HNSCurrentMajorVersion[v4] );
  v14 = HNS::Service::Core::HNSCurrentMajorVersion;
  v15 = v4;
  if ( (unsigned __int8)HNS::RegKey::GetValueDw(v16, &v14, &v20) )
  {
    LODWORD(v6) = v20;
  }
  else
  {
    v5 = v17;
    if ( v17 == 2 )
    {
      v6 = HIDWORD(*((_QWORD *)this + 13));
      LogError(
        -2147024894,
        L"Missing HNSCurrentMajorVersion from HNS service key path. Falling back to default version: %d",
        (unsigned int)v6);
    }
    else
    {
      if ( v17 > 0 )
        v5 = (unsigned __int16)v17 | 0x80070000;
      LogError(
        v5,
        L"Missing HNSCurrentMajorVersion from HNS service key path. Falling back to default version: %d",
        v20);
      v6 = HIDWORD(*((_QWORD *)this + 13));
    }
  }
  v7 = -1;
  do
    ++v7;
  while ( HNS::Service::Core::HNSCurrentMinorVersion[v7] );
  v14 = HNS::Service::Core::HNSCurrentMinorVersion;
  v15 = v7;
  if ( (unsigned __int8)HNS::RegKey::GetValueDw(v16, &v14, &v21) )
  {
    v8 = v21;
  }
  else
  {
    if ( v17 != 2 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\versionmanager.cpp",
        (const char *)(unsigned int)v17,
        (unsigned int)"Failed to get HNSCurrentVersion.",
        v11);
    v8 = *((_DWORD *)this + 26);
    LogError(
      -2147024894,
      L"Missing HNSCurrentMinorVersion from HNS service key path. Falling back to default version: %d",
      v8);
  }
  v9 = -1;
  do
    ++v9;
  while ( HNS::Service::Core::HNSCompatibleMajorVersion[v9] );
  v14 = HNS::Service::Core::HNSCompatibleMajorVersion;
  v15 = v9;
  if ( (unsigned __int8)HNS::RegKey::GetValueDw(v16, &v14, &v12) )
  {
    do
      ++v3;
    while ( HNS::Service::Core::HNSCompatibleMinorVersion[v3] );
    v14 = HNS::Service::Core::HNSCompatibleMinorVersion;
    v15 = v3;
    if ( !(unsigned __int8)HNS::RegKey::GetValueDw(v16, &v14, &v22) )
    {
      LastStatus = HNS::RegKey::GetLastStatus((HNS::RegKey *)v16);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\versionmanager.cpp",
        (const char *)LastStatus,
        (unsigned int)"Failed to get HNSCompatibleMinorVersion.",
        v11);
    }
    if ( v12 > (unsigned int)v6 || v12 == (_DWORD)v6 && v22 > v8 )
    {
      LODWORD(v11) = v6;
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\versionmanager.cpp",
        (const char *)0x32,
        (unsigned int)"HNSCurrentVersion(%d.%d) is less than HNSCompatibleVersion(%d.%d).",
        v11,
        v8,
        v12,
        v22);
    }
    HNS::Service::Core::VersionManager::SetCurrentOperatingVersion(this, v12, v22);
    HNSTraceProvider::TraceSuccess("HNS::Service::Core::VersionManager::InitializeOperatingVersion", 0x9Fu);
  }
  else
  {
    if ( v17 != 2 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\versionmanager.cpp",
        (const char *)(unsigned int)v17,
        (unsigned int)"Failed to get HNSCompatibleMajorVersion.",
        v11);
    HNS::Service::Core::VersionManager::SetCurrentOperatingVersion(this, v6, v8);
  }
  if ( v16[0] )
    RegCloseKey(v16[0]);
}

```

## disassembly

```asm
0x1800e7cf0  mov     [rsp-8+arg_0], rbx
0x1800e7cf5  push    rbp
0x1800e7cf6  push    rsi
0x1800e7cf7  push    rdi
0x1800e7cf8  push    r14
0x1800e7cfa  push    r15
0x1800e7cfc  lea     rbp, [rsp-37h]
0x1800e7d01  sub     rsp, 90h
0x1800e7d08  mov     r14, rcx
0x1800e7d0b  mov     edx, 50h ; 'P'; unsigned int
0x1800e7d10  lea     rcx, aHnsServiceCore_68; "HNS::Service::Core::VersionManager::Ini"...
0x1800e7d17  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800e7d1c  xor     r15d, r15d
0x1800e7d1f  mov     [rbp+57h+arg_8], r15d
0x1800e7d23  mov     [rbp+57h+arg_10], r15d
0x1800e7d27  mov     [rbp+57h+var_60], r15d
0x1800e7d2b  mov     [rbp+57h+arg_18], r15d
0x1800e7d2f  xor     edx, edx
0x1800e7d31  mov     r8d, 20019h
0x1800e7d37  lea     rcx, [rbp+57h+hKey]
0x1800e7d3b  call    ?GetHnsServiceKey@HNS@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4SERVICE_REGISTRY_STATE_TYPE@@K@Z; HNS::GetHnsServiceKey(SERVICE_REGISTRY_STATE_TYPE,ulong)
0x1800e7d40  mov     rcx, [rax]
0x1800e7d43  mov     [rbp+57h+var_40], rcx
0x1800e7d47  mov     [rax], r15
0x1800e7d4a  mov     dword ptr [rbp+57h+var_30], r15d
0x1800e7d4e  mov     byte ptr [rbp+57h+var_30+4], 1
0x1800e7d52  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e7d56  test    rcx, rcx
0x1800e7d59  jz      short loc_1800E7D61
0x1800e7d5b  call    cs:__imp_RegCloseKey
0x1800e7d61  mov     rcx, cs:?HNSCurrentMajorVersion@Core@Service@HNS@@3PEBGEB; ushort const * const HNS::Service::Core::HNSCurrentMajorVersion
0x1800e7d68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e7d6c  mov     rax, rsi
0x1800e7d6f  inc     rax
0x1800e7d72  cmp     [rcx+rax*2], r15w
0x1800e7d77  jnz     short loc_1800E7D6F
0x1800e7d79  mov     [rbp+57h+var_50], rcx
0x1800e7d7d  mov     [rbp+57h+var_48], rax
0x1800e7d81  lea     r8, [rbp+57h+arg_8]
0x1800e7d85  lea     rdx, [rbp+57h+var_50]
0x1800e7d89  lea     rcx, [rbp+57h+var_40]
0x1800e7d8d  call    ?GetValueDw@RegKey@HNS@@QEAA_NV?$basic_zstring_view@G@wil@@AEAK@Z; HNS::RegKey::GetValueDw(wil::basic_zstring_view<ushort>,ulong &)
0x1800e7d92  test    al, al
0x1800e7d94  jnz     short loc_1800E7DE3
0x1800e7d96  mov     ecx, dword ptr [rbp+57h+var_30]
0x1800e7d99  cmp     ecx, 2
0x1800e7d9c  jnz     short loc_1800E7DBC
0x1800e7d9e  mov     rbx, [r14+68h]
0x1800e7da2  shr     rbx, 20h
0x1800e7da6  mov     r8d, ebx
0x1800e7da9  lea     rdx, aMissingHnscurr; "Missing HNSCurrentMajorVersion from HNS"...
0x1800e7db0  mov     ecx, 80070002h; int
0x1800e7db5  call    ?LogError@@YAXJPEBGZZ; LogError(long,ushort const *,...)
0x1800e7dba  jmp     short loc_1800E7DE6
0x1800e7dbc  test    ecx, ecx
0x1800e7dbe  jle     short loc_1800E7DC9
0x1800e7dc0  movzx   ecx, cx
0x1800e7dc3  or      ecx, 80070000h; int
0x1800e7dc9  mov     r8d, [rbp+57h+arg_8]
0x1800e7dcd  lea     rdx, aMissingHnscurr; "Missing HNSCurrentMajorVersion from HNS"...
0x1800e7dd4  call    ?LogError@@YAXJPEBGZZ; LogError(long,ushort const *,...)
0x1800e7dd9  mov     rbx, [r14+68h]
0x1800e7ddd  shr     rbx, 20h
0x1800e7de1  jmp     short loc_1800E7DE6
0x1800e7de3  mov     ebx, [rbp+57h+arg_8]
0x1800e7de6  mov     rcx, cs:?HNSCurrentMinorVersion@Core@Service@HNS@@3PEBGEB; ushort const * const HNS::Service::Core::HNSCurrentMinorVersion
0x1800e7ded  mov     rax, rsi
0x1800e7df0  inc     rax
0x1800e7df3  cmp     [rcx+rax*2], r15w
0x1800e7df8  jnz     short loc_1800E7DF0
0x1800e7dfa  mov     [rbp+57h+var_50], rcx
0x1800e7dfe  mov     [rbp+57h+var_48], rax
0x1800e7e02  lea     r8, [rbp+57h+arg_10]
0x1800e7e06  lea     rdx, [rbp+57h+var_50]
0x1800e7e0a  lea     rcx, [rbp+57h+var_40]
0x1800e7e0e  call    ?GetValueDw@RegKey@HNS@@QEAA_NV?$basic_zstring_view@G@wil@@AEAK@Z; HNS::RegKey::GetValueDw(wil::basic_zstring_view<ushort>,ulong &)
0x1800e7e13  test    al, al
0x1800e7e15  jnz     short loc_1800E7E3F
0x1800e7e17  mov     r9d, dword ptr [rbp+57h+var_30]; char *
0x1800e7e1b  cmp     r9d, 2
0x1800e7e1f  jnz     loc_1800E7F7B
0x1800e7e25  mov     edi, [r14+68h]
0x1800e7e29  mov     r8d, edi
0x1800e7e2c  lea     rdx, aMissingHnscurr_0; "Missing HNSCurrentMinorVersion from HNS"...
0x1800e7e33  mov     ecx, 80070002h; int
0x1800e7e38  call    ?LogError@@YAXJPEBGZZ; LogError(long,ushort const *,...)
0x1800e7e3d  jmp     short loc_1800E7E42
0x1800e7e3f  mov     edi, [rbp+57h+arg_10]
0x1800e7e42  mov     rcx, cs:?HNSCompatibleMajorVersion@Core@Service@HNS@@3PEBGEB; ushort const * const HNS::Service::Core::HNSCompatibleMajorVersion
0x1800e7e49  mov     rax, rsi
0x1800e7e4c  inc     rax
0x1800e7e4f  cmp     [rcx+rax*2], r15w
0x1800e7e54  jnz     short loc_1800E7E4C
0x1800e7e56  mov     [rbp+57h+var_50], rcx
0x1800e7e5a  mov     [rbp+57h+var_48], rax
0x1800e7e5e  lea     r8, [rbp+57h+var_60]
0x1800e7e62  lea     rdx, [rbp+57h+var_50]
0x1800e7e66  lea     rcx, [rbp+57h+var_40]
0x1800e7e6a  call    ?GetValueDw@RegKey@HNS@@QEAA_NV?$basic_zstring_view@G@wil@@AEAK@Z; HNS::RegKey::GetValueDw(wil::basic_zstring_view<ushort>,ulong &)
0x1800e7e6f  test    al, al
0x1800e7e71  jnz     short loc_1800E7EB5
0x1800e7e73  mov     r9d, dword ptr [rbp+57h+var_30]; char *
0x1800e7e77  cmp     r9d, 2
0x1800e7e7b  jnz     loc_1800E7F9D
0x1800e7e81  mov     r8d, edi; unsigned int
0x1800e7e84  mov     edx, ebx; unsigned int
0x1800e7e86  mov     rcx, r14; this
0x1800e7e89  call    ?SetCurrentOperatingVersion@VersionManager@Core@Service@HNS@@QEAAXKK@Z; HNS::Service::Core::VersionManager::SetCurrentOperatingVersion(ulong,ulong)
0x1800e7e8e  nop
0x1800e7e8f  mov     rcx, [rbp+57h+var_40]; hKey
0x1800e7e93  test    rcx, rcx
0x1800e7e96  jz      short loc_1800E7E9E
0x1800e7e98  call    cs:__imp_RegCloseKey
0x1800e7e9e  mov     rbx, [rsp+0B0h+arg_0]
0x1800e7ea6  add     rsp, 90h
0x1800e7ead  pop     r15
0x1800e7eaf  pop     r14
0x1800e7eb1  pop     rdi
0x1800e7eb2  pop     rsi
0x1800e7eb3  pop     rbp
0x1800e7eb4  retn
0x1800e7eb5  mov     rax, cs:?HNSCompatibleMinorVersion@Core@Service@HNS@@3PEBGEB; ushort const * const HNS::Service::Core::HNSCompatibleMinorVersion
0x1800e7ebc  inc     rsi
0x1800e7ebf  cmp     [rax+rsi*2], r15w
0x1800e7ec4  jnz     short loc_1800E7EBC
0x1800e7ec6  mov     [rbp+57h+var_50], rax
0x1800e7eca  mov     [rbp+57h+var_48], rsi
0x1800e7ece  lea     r8, [rbp+57h+arg_18]
0x1800e7ed2  lea     rdx, [rbp+57h+var_50]
0x1800e7ed6  lea     rcx, [rbp+57h+var_40]
0x1800e7eda  call    ?GetValueDw@RegKey@HNS@@QEAA_NV?$basic_zstring_view@G@wil@@AEAK@Z; HNS::RegKey::GetValueDw(wil::basic_zstring_view<ushort>,ulong &)
0x1800e7edf  test    al, al
0x1800e7ee1  jz      short loc_1800E7F16
0x1800e7ee3  mov     edx, [rbp+57h+arg_18]
0x1800e7ee6  mov     eax, [rbp+57h+var_60]
0x1800e7ee9  cmp     eax, ebx
0x1800e7eeb  ja      short loc_1800E7F44
0x1800e7eed  jnz     short loc_1800E7EF3
0x1800e7eef  cmp     edx, edi
0x1800e7ef1  ja      short loc_1800E7F44
0x1800e7ef3  mov     r8d, edx; unsigned int
0x1800e7ef6  mov     edx, eax; unsigned int
0x1800e7ef8  mov     rcx, r14; this
0x1800e7efb  call    ?SetCurrentOperatingVersion@VersionManager@Core@Service@HNS@@QEAAXKK@Z; HNS::Service::Core::VersionManager::SetCurrentOperatingVersion(ulong,ulong)
0x1800e7f00  mov     edx, 9Fh; unsigned int
0x1800e7f05  lea     rcx, aHnsServiceCore_68; "HNS::Service::Core::VersionManager::Ini"...
0x1800e7f0c  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800e7f11  jmp     loc_1800E7E8F
0x1800e7f16  lea     rcx, [rbp+57h+var_40]; this
0x1800e7f1a  call    ?GetLastStatus@RegKey@HNS@@QEBAJXZ; HNS::RegKey::GetLastStatus(void)
0x1800e7f1f  mov     r9d, eax; char *
0x1800e7f22  mov     rcx, [rbp+5Fh]; this
0x1800e7f26  lea     rax, aFailedToGetHns_0; "Failed to get HNSCompatibleMinorVersion"...
0x1800e7f2d  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x1800e7f32  lea     r8, aOnecoreVmDvNet_73; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800e7f39  mov     edx, 8Dh; void *
0x1800e7f3e  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800e7f44  mov     rcx, [rbp+5Fh]; this
0x1800e7f48  mov     [rsp+0B0h+var_70], edx
0x1800e7f4c  mov     [rsp+0B0h+var_78], eax
0x1800e7f50  mov     [rsp+0B0h+var_80], edi
0x1800e7f54  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x1800e7f58  lea     rax, aHnscurrentvers; "HNSCurrentVersion(%d.%d) is less than H"...
0x1800e7f5f  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x1800e7f64  mov     r9d, 32h ; '2'; char *
0x1800e7f6a  lea     r8, aOnecoreVmDvNet_73; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800e7f71  lea     edx, [r9+69h]; void *
0x1800e7f75  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800e7f7b  mov     rcx, [rbp+5Fh]; this
0x1800e7f7f  lea     rax, aFailedToGetHns_1; "Failed to get HNSCurrentVersion."
0x1800e7f86  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x1800e7f8b  lea     r8, aOnecoreVmDvNet_73; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800e7f92  mov     edx, 75h ; 'u'; void *
0x1800e7f97  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800e7f9d  mov     rcx, [rbp+5Fh]; this
0x1800e7fa1  lea     rax, aFailedToGetHns; "Failed to get HNSCompatibleMajorVersion"...
0x1800e7fa8  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x1800e7fad  lea     r8, aOnecoreVmDvNet_73; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800e7fb4  mov     edx, 86h; void *
0x1800e7fb9  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
