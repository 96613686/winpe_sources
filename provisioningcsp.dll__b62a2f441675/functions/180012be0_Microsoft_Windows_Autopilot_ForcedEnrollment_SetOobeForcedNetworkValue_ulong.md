# Microsoft::Windows::Autopilot::ForcedEnrollment::SetOobeForcedNetworkValue(ulong)

- ea: `0x180012be0`
- end: `0x180012cca`
- name: `?SetOobeForcedNetworkValue@ForcedEnrollment@Autopilot@Windows@Microsoft@@SAJK@Z`
- size: `234`
- prototype: `static int(unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b750`
- `0x18000c7d0`

## callees

- `0x180006954`
- `0x180006974`
- `0x180012a7c`
- `0x180012be0`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x180012c25`
- `ntdll!RtlReleasePrivilege` at `0x180012c7e`
- `ntdll!RtlReleasePrivilege` at `0x180012cb5`
- `ntdll!RtlReleasePrivilege` at `0x180012c25`
- `ntdll!RtlReleasePrivilege` at `0x180012c7e`
- `ntdll!RtlReleasePrivilege` at `0x180012cb5`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x180012c4c`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x180012c4c`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ForcedEnrollment::SetOobeForcedNetworkValue(int a1)
{
  int v1; // eax
  int LastError; // ebx
  const char *v3; // r9
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int pValue; // [rsp+30h] [rbp+8h] BYREF
  PVOID ReturnedState; // [rsp+38h] [rbp+10h] BYREF

  pValue = a1;
  ReturnedState = 0;
  v1 = ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(&ReturnedState);
  LastError = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
      (const char *)(unsigned int)v1,
      v5);
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\forcedenrollment.cpp",
      (const char *)(unsigned int)LastError,
      v5);
    return (unsigned int)LastError;
  }
  if ( SetFirmwareEnvironmentVariableW(L"FORCED_NETWORK_FLAG", L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}", &pValue, 4u) )
  {
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC0,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
                  v3);
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
    if ( LastError < 0 )
      goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x180012be0  mov     [rsp+pValue], ecx
0x180012be4  push    rbx; int
0x180012be5  sub     rsp, 20h
0x180012be9  lea     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012bee  mov     [rsp+28h+ReturnedState], 0
0x180012bf7  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x180012bfc  mov     ebx, eax
0x180012bfe  test    eax, eax
0x180012c00  jns     short loc_180012C33
0x180012c02  mov     rcx, [rsp+28h]; this
0x180012c07  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012c0e  mov     r9d, eax; char *
0x180012c11  mov     edx, 0BAh; void *
0x180012c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c1b  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012c20  test    rcx, rcx
0x180012c23  jz      short loc_180012C8E
0x180012c25  call    cs:__imp_RtlReleasePrivilege
0x180012c2c  nop     dword ptr [rax+rax+00h]
0x180012c31  jmp     short loc_180012C8E
0x180012c33  mov     r9d, 4; nSize
0x180012c39  lea     r8, [rsp+28h+pValue]; pValue
0x180012c3e  lea     rdx, a616e2ea6Af897e; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x180012c45  lea     rcx, aForcedNetworkF; "FORCED_NETWORK_FLAG"
0x180012c4c  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x180012c53  nop     dword ptr [rax+rax+00h]
0x180012c58  test    eax, eax
0x180012c5a  jnz     short loc_180012CAB
0x180012c5c  mov     rcx, [rsp+28h]; this
0x180012c61  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012c68  mov     edx, 0C0h; void *
0x180012c6d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012c72  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012c77  mov     ebx, eax
0x180012c79  test    rcx, rcx
0x180012c7c  jz      short loc_180012C8A
0x180012c7e  call    cs:__imp_RtlReleasePrivilege
0x180012c85  nop     dword ptr [rax+rax+00h]
0x180012c8a  test    ebx, ebx
0x180012c8c  jns     short loc_180012CC1
0x180012c8e  mov     rcx, [rsp+28h]; this
0x180012c93  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\provcsp\\force"...
0x180012c9a  mov     r9d, ebx; char *
0x180012c9d  mov     edx, 1Eh; void *
0x180012ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ca7  mov     eax, ebx
0x180012ca9  jmp     short loc_180012CC3
0x180012cab  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012cb0  test    rcx, rcx
0x180012cb3  jz      short loc_180012CC1
0x180012cb5  call    cs:__imp_RtlReleasePrivilege
0x180012cbc  nop     dword ptr [rax+rax+00h]
0x180012cc1  xor     eax, eax
0x180012cc3  add     rsp, 20h
0x180012cc7  pop     rbx
0x180012cc8  retn
```
