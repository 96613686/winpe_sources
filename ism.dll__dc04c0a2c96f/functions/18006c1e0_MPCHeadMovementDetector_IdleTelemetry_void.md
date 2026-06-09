# MPCHeadMovementDetector::IdleTelemetry(void)

- ea: `0x18006c1e0`
- end: `0x18006c2b8`
- name: `?IdleTelemetry@MPCHeadMovementDetector@@AEAAXXZ`
- size: `216`
- prototype: `void __fastcall(MPCHeadMovementDetector *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18006be10`

## callees

- `0x18006c1e0`
- `0x180116b04`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18006c226`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18006c226`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x18006c299`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x18006c299`
- `POWRPROF!PowerReadACValueIndex` at `0x18006c254`
- `POWRPROF!PowerReadACValueIndex` at `0x18006c254`
- `POWRPROF!PowerReadDCValueIndex` at `0x18006c27b`
- `POWRPROF!PowerReadDCValueIndex` at `0x18006c27b`

## pseudocode

```c
void __fastcall MPCHeadMovementDetector::IdleTelemetry(MPCHeadMovementDetector *this)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // rax
  DWORD ActiveScheme; // eax
  unsigned int OutputBuffer; // [rsp+40h] [rbp+10h] BYREF
  DWORD DcValueIndex; // [rsp+48h] [rbp+18h] BYREF
  DWORD AcValueIndex; // [rsp+50h] [rbp+20h] BYREF
  GUID *ActivePolicyGuid; // [rsp+58h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 5);
  if ( v1 >= *((_QWORD *)this + 21) )
  {
    v2 = v1 + *((unsigned int *)this + 44);
    AcValueIndex = 0;
    *((_QWORD *)this + 21) = v2;
    DcValueIndex = 0;
    ActivePolicyGuid = 0;
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
    OutputBuffer = 0;
    if ( !ActiveScheme
      && !PowerReadACValueIndex(0, ActivePolicyGuid, &GUID_VIDEO_SUBGROUP, &GUID_VIDEO_POWERDOWN_TIMEOUT, &AcValueIndex)
      && !PowerReadDCValueIndex(0, ActivePolicyGuid, &GUID_VIDEO_SUBGROUP, &GUID_VIDEO_POWERDOWN_TIMEOUT, &DcValueIndex)
      && !CallNtPowerInformation(SystemExecutionState, 0, 0, &OutputBuffer, 4u) )
    {
      ISMTracing::LogIdleTelemetry(AcValueIndex, DcValueIndex, OutputBuffer);
    }
  }
}

```

## disassembly

```asm
0x18006c1e0  push    rbp
0x18006c1e2  mov     rbp, rsp
0x18006c1e5  sub     rsp, 30h
0x18006c1e9  mov     rdx, [rcx+28h]
0x18006c1ed  cmp     rdx, [rcx+0A8h]
0x18006c1f4  jb      loc_18006C2B2
0x18006c1fa  mov     eax, [rcx+0B0h]
0x18006c200  add     rax, rdx
0x18006c203  mov     [rbp+arg_10], 0
0x18006c20a  mov     [rcx+0A8h], rax
0x18006c211  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x18006c215  xor     ecx, ecx; UserRootPowerKey
0x18006c217  mov     [rbp+DcValueIndex], 0
0x18006c21e  mov     [rbp+ActivePolicyGuid], 0
0x18006c226  call    cs:__imp_PowerGetActiveScheme
0x18006c22c  mov     [rbp+OutputBuffer], 0
0x18006c233  test    eax, eax
0x18006c235  jnz     short loc_18006C2B2
0x18006c237  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18006c23b  lea     rax, [rbp+arg_10]
0x18006c23f  lea     r9, GUID_VIDEO_POWERDOWN_TIMEOUT; PowerSettingGuid
0x18006c246  mov     [rsp+30h+AcValueIndex], rax; AcValueIndex
0x18006c24b  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18006c252  xor     ecx, ecx; RootPowerKey
0x18006c254  call    cs:__imp_PowerReadACValueIndex
0x18006c25a  test    eax, eax
0x18006c25c  jnz     short loc_18006C2B2
0x18006c25e  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18006c262  lea     rax, [rbp+DcValueIndex]
0x18006c266  lea     r9, GUID_VIDEO_POWERDOWN_TIMEOUT; PowerSettingGuid
0x18006c26d  mov     [rsp+30h+AcValueIndex], rax; DcValueIndex
0x18006c272  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18006c279  xor     ecx, ecx; RootPowerKey
0x18006c27b  call    cs:__imp_PowerReadDCValueIndex
0x18006c281  test    eax, eax
0x18006c283  jnz     short loc_18006C2B2
0x18006c285  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x18006c289  mov     dword ptr [rsp+30h+AcValueIndex], 4; OutputBufferLength
0x18006c291  xor     r8d, r8d; InputBufferLength
0x18006c294  lea     ecx, [rax+10h]; InformationLevel
0x18006c297  xor     edx, edx; InputBuffer
0x18006c299  call    cs:__imp_CallNtPowerInformation
0x18006c29f  test    eax, eax
0x18006c2a1  jnz     short loc_18006C2B2
0x18006c2a3  mov     r8d, [rbp+OutputBuffer]; unsigned int
0x18006c2a7  mov     edx, [rbp+DcValueIndex]; unsigned int
0x18006c2aa  mov     ecx, [rbp+arg_10]; unsigned int
0x18006c2ad  call    ?LogIdleTelemetry@ISMTracing@@SAXKKK@Z; ISMTracing::LogIdleTelemetry(ulong,ulong,ulong)
0x18006c2b2  add     rsp, 30h
0x18006c2b6  pop     rbp
0x18006c2b7  retn
```
