# _lambda_3a2f8dcf839b3b35c164e95d8960a240_::operator()

- ea: `0x180028cbc`
- end: `0x180028e9f`
- name: `_lambda_3a2f8dcf839b3b35c164e95d8960a240_::operator()`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a490`

## callees

- `0x180002690`
- `0x1800084b4`
- `0x180008fac`
- `0x180009a38`
- `0x1800127bc`
- `0x180012818`
- `0x180028cbc`
- `0x18002994c`
- `0x18002a608`
- `0x18002a8b0`
- `0x18002ac4c`
- `0x18002aef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ddf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ddf`

## string_xrefs

- `0x180028e36`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180028e59`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180028e71`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180028e8d`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall lambda_3a2f8dcf839b3b35c164e95d8960a240_::operator()(_QWORD *a1)
{
  __int64 DiskVolumePath; // rax
  HKEY v3; // rdx
  const unsigned __int16 *v4; // r8
  __int64 v5; // rax
  DWORD v6; // esi
  DWORD v7; // r14d
  char v8; // al
  DWORD v9; // edi
  __int64 v10; // rdx
  const char *v11; // r9
  unsigned int v12; // eax
  REGSAM samDesired; // [rsp+20h] [rbp-40h]
  HKEY hKey[4]; // [rsp+30h] [rbp-30h] BYREF
  DWORD dwMilliseconds; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  DiskVolumePath = TryGetDiskVolumePath(hKey, *(_QWORD *)a1[1]);
  std::wstring::operator=(*a1, DiskVolumePath);
  std::wstring::~wstring((char **)hKey);
  v5 = *a1;
  if ( !*(_QWORD *)(*a1 + 16LL) )
  {
    v6 = 10000;
    v7 = 60000;
    hKey[1] = 0;
    hKey[0] = (HKEY)&ComputeService::ComputeSystemSettingsStore::`vftable';
    if ( !ComputeService::MachineLocalSettingsStore::OpenImpl(
            (ComputeService::MachineLocalSettingsStore *)hKey,
            v3,
            v4,
            0,
            0x20019u) )
      goto LABEL_9;
    dwMilliseconds = 0;
    if ( ComputeService::MachineLocalSettingsStore::QueryValue(
           (ComputeService::MachineLocalSettingsStore *)hKey,
           L"VolumeArrivalForceOnlineInterval",
           &dwMilliseconds) )
    {
      v6 = dwMilliseconds;
    }
    if ( ComputeService::MachineLocalSettingsStore::QueryValue(
           (ComputeService::MachineLocalSettingsStore *)hKey,
           L"VolumeArrivalTimeout",
           &dwMilliseconds) )
    {
      v7 = dwMilliseconds;
    }
    if ( v7 < v6 )
      v8 = 1;
    else
LABEL_9:
      v8 = 0;
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        (const char *)0x80070057LL,
        samDesired);
    v9 = 0;
    while ( 1 )
    {
      ForceOnlineHardDisk(*(void **)a1[1]);
      if ( (unsigned int)Vml::VmSlimEvent::Wait((PSRWLOCK)a1[2], v6) )
        break;
      v9 += v6;
      if ( v9 >= v7 )
        goto LABEL_14;
    }
    v10 = a1[2];
    v11 = (const char *)*(unsigned int *)(v10 + 32);
    if ( (int)v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v11,
        samDesired);
    std::wstring::operator=(*a1, v10 + 48);
    if ( !*(_QWORD *)(*a1 + 16LL) )
    {
      v12 = wil::verify_hresult<long>(0x8000FFFF);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        (const char *)v12,
        samDesired);
    }
LABEL_14:
    v5 = *a1;
    if ( !*(_QWORD *)(*a1 + 16LL) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        (const char *)0x5B4,
        samDesired);
    if ( hKey[1] )
      LODWORD(v5) = RegCloseKey(hKey[1]);
  }
  return v5;
}

```

## disassembly

```asm
0x180028cbc  mov     [rsp-18h+arg_8], rbx
0x180028cc1  mov     [rsp-18h+arg_10], rsi
0x180028cc6  push    rbp
0x180028cc7  push    rdi
0x180028cc8  push    r14
0x180028cca  mov     rbp, rsp
0x180028ccd  sub     rsp, 60h
0x180028cd1  mov     rax, cs:__security_cookie
0x180028cd8  xor     rax, rsp
0x180028cdb  mov     [rbp+var_8], rax
0x180028cdf  mov     rbx, rcx
0x180028ce2  mov     rdx, [rcx+8]
0x180028ce6  mov     rdx, [rdx]
0x180028ce9  lea     rcx, [rbp+hKey]
0x180028ced  call    ?TryGetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; TryGetDiskVolumePath(void *)
0x180028cf2  mov     rdx, rax
0x180028cf5  mov     rcx, [rbx]
0x180028cf8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028cfd  lea     rcx, [rbp+hKey]
0x180028d01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028d06  mov     rax, [rbx]
0x180028d09  cmp     qword ptr [rax+10h], 0
0x180028d0e  jnz     loc_180028DEB
0x180028d14  mov     esi, 2710h
0x180028d19  mov     r14d, 0EA60h
0x180028d1f  xorps   xmm0, xmm0
0x180028d22  movups  xmmword ptr [rbp+hKey], xmm0
0x180028d26  mov     [rbp+hKey+8], 0
0x180028d2e  lea     rax, ??_7ComputeSystemSettingsStore@ComputeService@@6B@; const ComputeService::ComputeSystemSettingsStore::`vftable'
0x180028d35  mov     [rbp+hKey], rax
0x180028d39  mov     [rsp+60h+samDesired], 20019h; unsigned int
0x180028d41  xor     r9d, r9d; unsigned __int16 *
0x180028d44  lea     rcx, [rbp+hKey]; this
0x180028d48  call    ?OpenImpl@MachineLocalSettingsStore@ComputeService@@IEAA_NPEAUHKEY__@@PEBG1K@Z; ComputeService::MachineLocalSettingsStore::OpenImpl(HKEY__ *,ushort const *,ushort const *,ulong)
0x180028d4d  test    al, al
0x180028d4f  jz      short loc_180028D96
0x180028d51  mov     [rbp+dwMilliseconds], 0
0x180028d58  lea     r8, [rbp+dwMilliseconds]; unsigned int *
0x180028d5c  lea     rdx, aVolumearrivalf; "VolumeArrivalForceOnlineInterval"
0x180028d63  lea     rcx, [rbp+hKey]; this
0x180028d67  call    ?QueryValue@MachineLocalSettingsStore@ComputeService@@UEBA_NPEBGAEAI@Z; ComputeService::MachineLocalSettingsStore::QueryValue(ushort const *,uint &)
0x180028d6c  test    al, al
0x180028d6e  cmovnz  esi, [rbp+dwMilliseconds]
0x180028d72  lea     r8, [rbp+dwMilliseconds]; unsigned int *
0x180028d76  lea     rdx, aVolumearrivalt; "VolumeArrivalTimeout"
0x180028d7d  lea     rcx, [rbp+hKey]; this
0x180028d81  call    ?QueryValue@MachineLocalSettingsStore@ComputeService@@UEBA_NPEBGAEAI@Z; ComputeService::MachineLocalSettingsStore::QueryValue(ushort const *,uint &)
0x180028d86  test    al, al
0x180028d88  cmovnz  r14d, [rbp+dwMilliseconds]
0x180028d8d  cmp     r14d, esi
0x180028d90  jnb     short loc_180028D96
0x180028d92  mov     al, 1
0x180028d94  jmp     short loc_180028D98
0x180028d96  xor     al, al
0x180028d98  mov     rcx, [rbp+18h]; this
0x180028d9c  test    al, al
0x180028d9e  jnz     loc_180028E6B
0x180028da4  xor     edi, edi
0x180028da6  mov     rcx, [rbx+8]
0x180028daa  mov     rcx, [rcx]; void *
0x180028dad  call    ?ForceOnlineHardDisk@@YAXPEAX@Z; ForceOnlineHardDisk(void *)
0x180028db2  mov     edx, esi; dwMilliseconds
0x180028db4  mov     rcx, [rbx+10h]; SRWLock
0x180028db8  call    ?Wait@VmSlimEvent@Vml@@QEAAHK@Z; Vml::VmSlimEvent::Wait(ulong)
0x180028dbd  test    eax, eax
0x180028dbf  jnz     short loc_180028E0D
0x180028dc1  add     edi, esi
0x180028dc3  cmp     edi, r14d
0x180028dc6  jb      short loc_180028DA6
0x180028dc8  mov     rax, [rbx]
0x180028dcb  cmp     qword ptr [rax+10h], 0
0x180028dd0  jz      loc_180028E83
0x180028dd6  mov     rcx, [rbp+hKey+8]; hKey
0x180028dda  test    rcx, rcx
0x180028ddd  jz      short loc_180028DEB
0x180028ddf  call    cs:__imp_RegCloseKey
0x180028de6  nop     dword ptr [rax+rax+00h]
0x180028deb  mov     rcx, [rbp+var_8]
0x180028def  xor     rcx, rsp; StackCookie
0x180028df2  call    __security_check_cookie
0x180028df7  lea     r11, [rsp+60h+var_s0]
0x180028dfc  mov     rbx, [r11+28h]
0x180028e00  mov     rsi, [r11+30h]
0x180028e04  mov     rsp, r11
0x180028e07  pop     r14
0x180028e09  pop     rdi
0x180028e0a  pop     rbp
0x180028e0b  retn
0x180028e0d  mov     rdx, [rbx+10h]
0x180028e11  mov     r9d, [rdx+20h]; char *
0x180028e15  mov     rcx, [rbp+18h]; this
0x180028e19  test    r9d, r9d
0x180028e1c  js      short loc_180028E36
0x180028e1e  add     rdx, 30h ; '0'
0x180028e22  mov     rcx, [rbx]
0x180028e25  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028e2a  mov     rax, [rbx]
0x180028e2d  cmp     qword ptr [rax+10h], 0
0x180028e32  jz      short loc_180028E48
0x180028e34  jmp     short loc_180028DC8
0x180028e36  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028e3d  mov     edx, 19Fh; void *
0x180028e42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028e48  mov     ecx, 8000FFFFh
0x180028e4d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180028e52  mov     r9d, eax; char *
0x180028e55  mov     rcx, [rbp+18h]; this
0x180028e59  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028e60  mov     edx, 1A3h; void *
0x180028e65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028e6b  mov     r9d, 80070057h; char *
0x180028e71  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028e78  mov     edx, 182h; void *
0x180028e7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028e83  mov     rcx, [rbp+18h]; this
0x180028e87  mov     r9d, 5B4h; char *
0x180028e8d  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028e94  mov     edx, 1AFh; void *
0x180028e99  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
