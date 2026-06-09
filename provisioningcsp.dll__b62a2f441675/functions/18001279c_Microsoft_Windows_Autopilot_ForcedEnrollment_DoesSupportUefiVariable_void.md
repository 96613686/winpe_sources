# Microsoft::Windows::Autopilot::ForcedEnrollment::DoesSupportUefiVariable(void)

- ea: `0x18001279c`
- end: `0x1800128c7`
- name: `?DoesSupportUefiVariable@ForcedEnrollment@Autopilot@Windows@Microsoft@@SA_NXZ`
- size: `299`
- prototype: `static bool(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b750`
- `0x18000bd70`
- `0x18000c7d0`

## callees

- `0x180006974`
- `0x18001279c`
- `0x180012a7c`
- `0x180012b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001282b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001282b`
- `ntdll!RtlReleasePrivilege` at `0x1800127e9`
- `ntdll!RtlReleasePrivilege` at `0x180012880`
- `ntdll!RtlReleasePrivilege` at `0x1800128ac`
- `ntdll!RtlReleasePrivilege` at `0x1800127e9`
- `ntdll!RtlReleasePrivilege` at `0x180012880`
- `ntdll!RtlReleasePrivilege` at `0x1800128ac`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18001281b`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18001281b`

## pseudocode

```c
char Microsoft::Windows::Autopilot::ForcedEnrollment::DoesSupportUefiVariable(void)
{
  int v0; // eax
  signed int LastError; // ebx
  char v2; // di
  void *v3; // rdx
  unsigned int v4; // r8d
  bool v5; // sf
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int pBuffer; // [rsp+30h] [rbp+8h] BYREF
  PVOID ReturnedState; // [rsp+38h] [rbp+10h] BYREF

  ReturnedState = 0;
  v0 = ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(&ReturnedState);
  LastError = v0;
  v2 = 1;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
      (const char *)(unsigned int)v0,
      v7);
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
LABEL_15:
    wil::details::in1diag3::Log_Hr(retaddr, v3, v4, (const char *)(unsigned int)LastError, v7);
    return v2;
  }
  pBuffer = 0;
  if ( GetFirmwareEnvironmentVariableW(&Name, L"{00000000-0000-0000-0000-000000000000}", &pBuffer, 4u) )
    goto LABEL_17;
  LastError = GetLastError();
  if ( LastError == 1 )
  {
    v2 = 0;
    goto LABEL_17;
  }
  if ( LastError == 203 || LastError == 998 )
  {
LABEL_17:
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
    return v2;
  }
  v5 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = LastError < 0;
  }
  if ( v5 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
      (const char *)(unsigned int)LastError,
      v7);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  if ( LastError < 0 )
    goto LABEL_15;
  return v2;
}

```

## disassembly

```asm
0x18001279c  mov     [rsp+arg_10], rbx
0x1800127a1  push    rdi; int
0x1800127a2  sub     rsp, 20h
0x1800127a6  lea     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x1800127ab  mov     [rsp+28h+ReturnedState], 0
0x1800127b4  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x1800127b9  mov     ebx, eax
0x1800127bb  mov     dil, 1
0x1800127be  test    eax, eax
0x1800127c0  jns     short loc_1800127FA
0x1800127c2  mov     rcx, [rsp+28h]; this
0x1800127c7  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800127ce  mov     r9d, eax; char *
0x1800127d1  mov     edx, 44h ; 'D'; void *
0x1800127d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127db  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x1800127e0  test    rcx, rcx
0x1800127e3  jz      loc_180012890
0x1800127e9  call    cs:__imp_RtlReleasePrivilege
0x1800127f0  nop     dword ptr [rax+rax+00h]
0x1800127f5  jmp     loc_180012890
0x1800127fa  mov     r9d, 4; nSize
0x180012800  mov     [rsp+28h+pBuffer], 0
0x180012808  lea     r8, [rsp+28h+pBuffer]; pBuffer
0x18001280d  lea     rdx, Guid; "{00000000-0000-0000-0000-000000000000}"
0x180012814  lea     rcx, Name; lpName
0x18001281b  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180012822  nop     dword ptr [rax+rax+00h]
0x180012827  test    eax, eax
0x180012829  jnz     short loc_1800128A2
0x18001282b  call    cs:__imp_GetLastError
0x180012832  nop     dword ptr [rax+rax+00h]
0x180012837  mov     ebx, eax
0x180012839  sub     eax, 1
0x18001283c  jz      short loc_18001289F
0x18001283e  sub     eax, 0CAh
0x180012843  jz      short loc_1800128A2
0x180012845  cmp     eax, 31Bh
0x18001284a  jz      short loc_1800128A2
0x18001284c  test    ebx, ebx
0x18001284e  jle     short loc_18001285B
0x180012850  movzx   ebx, bx
0x180012853  or      ebx, 80070000h
0x180012859  test    ebx, ebx
0x18001285b  jns     short loc_180012876
0x18001285d  mov     rcx, [rsp+28h]; this
0x180012862  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012869  mov     r9d, ebx; char *
0x18001286c  mov     edx, 5Ch ; '\'; void *
0x180012871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012876  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x18001287b  test    rcx, rcx
0x18001287e  jz      short loc_18001288C
0x180012880  call    cs:__imp_RtlReleasePrivilege
0x180012887  nop     dword ptr [rax+rax+00h]
0x18001288c  test    ebx, ebx
0x18001288e  jns     short loc_1800128B8
0x180012890  mov     rcx, [rsp+28h]; this
0x180012895  mov     r9d, ebx; char *
0x180012898  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001289d  jmp     short loc_1800128B8
0x18001289f  xor     dil, dil
0x1800128a2  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x1800128a7  test    rcx, rcx
0x1800128aa  jz      short loc_1800128B8
0x1800128ac  call    cs:__imp_RtlReleasePrivilege
0x1800128b3  nop     dword ptr [rax+rax+00h]
0x1800128b8  mov     rbx, [rsp+28h+arg_10]
0x1800128bd  mov     al, dil
0x1800128c0  add     rsp, 20h
0x1800128c4  pop     rdi
0x1800128c5  retn
```
