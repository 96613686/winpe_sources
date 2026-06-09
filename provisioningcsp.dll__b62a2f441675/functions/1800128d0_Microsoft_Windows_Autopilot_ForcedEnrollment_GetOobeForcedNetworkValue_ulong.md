# Microsoft::Windows::Autopilot::ForcedEnrollment::GetOobeForcedNetworkValue(ulong *)

- ea: `0x1800128d0`
- end: `0x180012a76`
- name: `?GetOobeForcedNetworkValue@ForcedEnrollment@Autopilot@Windows@Microsoft@@SAJPEAK@Z`
- size: `422`
- prototype: `static int(unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b750`
- `0x18000bd70`

## callees

- `0x180006974`
- `0x1800128d0`
- `0x180012a7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012971`
- `ntdll!RtlReleasePrivilege` at `0x18001292d`
- `ntdll!RtlReleasePrivilege` at `0x18001299e`
- `ntdll!RtlReleasePrivilege` at `0x1800129d6`
- `ntdll!RtlReleasePrivilege` at `0x180012a11`
- `ntdll!RtlReleasePrivilege` at `0x18001292d`
- `ntdll!RtlReleasePrivilege` at `0x18001299e`
- `ntdll!RtlReleasePrivilege` at `0x1800129d6`
- `ntdll!RtlReleasePrivilege` at `0x180012a11`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18001295b`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18001295b`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ForcedEnrollment::GetOobeForcedNetworkValue(unsigned int *a1)
{
  int v2; // eax
  signed int v3; // ebx
  unsigned int v4; // edi
  DWORD FirmwareEnvironmentVariableW; // ebx
  signed int LastError; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int pBuffer; // [rsp+38h] [rbp+10h] BYREF
  PVOID ReturnedState; // [rsp+40h] [rbp+18h] BYREF

  pBuffer = 0;
  ReturnedState = 0;
  v2 = ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(&ReturnedState);
  v3 = v2;
  v4 = -2147024693;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
      (const char *)(unsigned int)v2,
      v8);
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
LABEL_15:
    if ( v3 != -2147024693 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
        (const char *)(unsigned int)v3,
        v8);
      v4 = v3;
    }
    goto LABEL_21;
  }
  pBuffer = 0;
  FirmwareEnvironmentVariableW = GetFirmwareEnvironmentVariableW(
                                   L"FORCED_NETWORK_FLAG",
                                   L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}",
                                   &pBuffer,
                                   4u);
  if ( FirmwareEnvironmentVariableW )
  {
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
    if ( FirmwareEnvironmentVariableW > 4 )
    {
      v4 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
        (const char *)0x8007000DLL,
        v8);
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\forcedenrollment.cpp",
        (const char *)v4,
        v8);
      return v4;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 == -2147024693 )
    {
      if ( ReturnedState )
        RtlReleasePrivilege(ReturnedState);
      goto LABEL_21;
    }
    if ( v3 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
        (const char *)(unsigned int)v3,
        v8);
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
    if ( v3 < 0 )
      goto LABEL_15;
  }
  *a1 = pBuffer;
  return 0;
}

```

## disassembly

```asm
0x1800128d0  mov     rax, rsp
0x1800128d3  mov     [rax+8], rbx
0x1800128d7  mov     [rax+20h], rsi
0x1800128db  push    rdi; int
0x1800128dc  sub     rsp, 20h
0x1800128e0  mov     rsi, rcx
0x1800128e3  mov     dword ptr [rax+10h], 0
0x1800128ea  lea     rcx, [rax+18h]; ReturnedState
0x1800128ee  mov     qword ptr [rax+18h], 0
0x1800128f6  call    ?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)
0x1800128fb  mov     ebx, eax
0x1800128fd  mov     edi, 800700CBh
0x180012902  test    eax, eax
0x180012904  jns     short loc_18001293E
0x180012906  mov     rcx, [rsp+28h]; this
0x18001290b  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012912  mov     r9d, eax; char *
0x180012915  mov     edx, 7Ch ; '|'; void *
0x18001291a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001291f  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012924  test    rcx, rcx
0x180012927  jz      loc_1800129E6
0x18001292d  call    cs:__imp_RtlReleasePrivilege
0x180012934  nop     dword ptr [rax+rax+00h]
0x180012939  jmp     loc_1800129E6
0x18001293e  xor     eax, eax
0x180012940  lea     r8, [rsp+28h+pBuffer]; pBuffer
0x180012945  lea     rdx, a616e2ea6Af897e; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18001294c  mov     [rsp+28h+pBuffer], eax
0x180012950  lea     rcx, aForcedNetworkF; "FORCED_NETWORK_FLAG"
0x180012957  lea     r9d, [rax+4]; nSize
0x18001295b  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180012962  nop     dword ptr [rax+rax+00h]
0x180012967  mov     ebx, eax
0x180012969  test    eax, eax
0x18001296b  jnz     loc_180012A07
0x180012971  call    cs:__imp_GetLastError
0x180012978  nop     dword ptr [rax+rax+00h]
0x18001297d  mov     ebx, eax
0x18001297f  test    eax, eax
0x180012981  jle     short loc_18001298C
0x180012983  movzx   ebx, ax
0x180012986  or      ebx, 80070000h
0x18001298c  cmp     ebx, edi
0x18001298e  jnz     short loc_1800129AF
0x180012990  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012995  test    rcx, rcx
0x180012998  jz      loc_180012A40
0x18001299e  call    cs:__imp_RtlReleasePrivilege
0x1800129a5  nop     dword ptr [rax+rax+00h]
0x1800129aa  jmp     loc_180012A40
0x1800129af  test    ebx, ebx
0x1800129b1  jns     short loc_1800129CC
0x1800129b3  mov     rcx, [rsp+28h]; this
0x1800129b8  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800129bf  mov     r9d, ebx; char *
0x1800129c2  mov     edx, 84h; void *
0x1800129c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129cc  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x1800129d1  test    rcx, rcx
0x1800129d4  jz      short loc_1800129E2
0x1800129d6  call    cs:__imp_RtlReleasePrivilege
0x1800129dd  nop     dword ptr [rax+rax+00h]
0x1800129e2  test    ebx, ebx
0x1800129e4  jns     short loc_180012A5D
0x1800129e6  cmp     ebx, edi
0x1800129e8  jz      short loc_180012A40
0x1800129ea  mov     rcx, [rsp+28h]; this
0x1800129ef  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800129f6  mov     r9d, ebx; char *
0x1800129f9  mov     edx, 0AEh; void *
0x1800129fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a03  mov     edi, ebx
0x180012a05  jmp     short loc_180012A40
0x180012a07  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x180012a0c  test    rcx, rcx
0x180012a0f  jz      short loc_180012A1D
0x180012a11  call    cs:__imp_RtlReleasePrivilege
0x180012a18  nop     dword ptr [rax+rax+00h]
0x180012a1d  cmp     ebx, 4
0x180012a20  jbe     short loc_180012A5D
0x180012a22  mov     rcx, [rsp+28h]; this
0x180012a27  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012a2e  mov     edi, 8007000Dh
0x180012a33  mov     edx, 0B0h; void *
0x180012a38  mov     r9d, edi; char *
0x180012a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a40  mov     rcx, [rsp+28h]; this
0x180012a45  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\provcsp\\force"...
0x180012a4c  mov     r9d, edi; char *
0x180012a4f  mov     edx, 28h ; '('; void *
0x180012a54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a59  mov     eax, edi
0x180012a5b  jmp     short loc_180012A65
0x180012a5d  mov     eax, [rsp+28h+pBuffer]
0x180012a61  mov     [rsi], eax
0x180012a63  xor     eax, eax
0x180012a65  mov     rbx, [rsp+28h+arg_0]
0x180012a6a  mov     rsi, [rsp+28h+arg_18]
0x180012a6f  add     rsp, 20h
0x180012a73  pop     rdi
0x180012a74  retn
```
