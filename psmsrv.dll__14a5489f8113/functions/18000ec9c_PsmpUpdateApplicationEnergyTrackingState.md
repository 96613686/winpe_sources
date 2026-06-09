# PsmpUpdateApplicationEnergyTrackingState

- ea: `0x18000ec9c`
- end: `0x18000ed2c`
- name: `PsmpUpdateApplicationEnergyTrackingState`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d378`
- `0x18000eb48`
- `0x1800114d0`

## callees

- `0x18000ec9c`

## import_xrefs

- `ntdll!NtSetInformationJobObject` at `0x18000ece7`
- `ntdll!NtSetInformationJobObject` at `0x18000ed0e`
- `ntdll!NtSetInformationJobObject` at `0x18000ece7`
- `ntdll!NtSetInformationJobObject` at `0x18000ed0e`

## pseudocode

```c
NTSTATUS __fastcall PsmpUpdateApplicationEnergyTrackingState(__int64 a1)
{
  int v1; // edx
  NTSTATUS result; // eax
  void *v4; // rcx
  __int64 JobInformation; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 344);
  JobInformation = 12;
  if ( v1 != 4 )
  {
    if ( (unsigned int)(v1 - 1) > 1 )
    {
      if ( v1 != 6 )
        HIDWORD(JobInformation) = 4;
    }
    else
    {
      HIDWORD(JobInformation) = 8;
    }
  }
  result = NtSetInformationJobObject(
             *(HANDLE *)(a1 + 184),
             MaxJobObjectInfoClass|JobObjectBasicLimitInformation|0x20,
             &JobInformation,
             8u);
  v4 = *(void **)(a1 + 200);
  if ( v4 )
    return NtSetInformationJobObject(v4, MaxJobObjectInfoClass|JobObjectBasicLimitInformation|0x20, &JobInformation, 8u);
  return result;
}

```

## disassembly

```asm
0x18000ec9c  push    rbx
0x18000ec9e  sub     rsp, 20h
0x18000eca2  mov     edx, [rcx+158h]
0x18000eca8  mov     rbx, rcx
0x18000ecab  mov     [rsp+28h+JobInformation], 0
0x18000ecb4  mov     dword ptr [rsp+28h+JobInformation], 0Ch
0x18000ecbc  cmp     edx, 4
0x18000ecbf  jz      short loc_18000ED25
0x18000ecc1  lea     eax, [rdx-1]
0x18000ecc4  cmp     eax, 1
0x18000ecc7  ja      short loc_18000ED16
0x18000ecc9  mov     dword ptr [rsp+28h+JobInformation+4], 8
0x18000ecd1  mov     rcx, [rcx+0B8h]; JobHandle
0x18000ecd8  lea     r8, [rsp+28h+JobInformation]; JobInformation
0x18000ecdd  mov     r9d, 8; JobInformationLength
0x18000ece3  lea     edx, [r9+26h]; JobInformationClass
0x18000ece7  call    cs:__imp_NtSetInformationJobObject
0x18000eced  mov     rcx, [rbx+0C8h]; JobHandle
0x18000ecf4  test    rcx, rcx
0x18000ecf7  jnz     short loc_18000ECFF
0x18000ecf9  add     rsp, 20h
0x18000ecfd  pop     rbx
0x18000ecfe  retn
0x18000ecff  mov     r9d, 8; JobInformationLength
0x18000ed05  lea     r8, [rsp+28h+JobInformation]; JobInformation
0x18000ed0a  lea     edx, [r9+26h]; JobInformationClass
0x18000ed0e  call    cs:__imp_NtSetInformationJobObject
0x18000ed14  jmp     short loc_18000ECF9
0x18000ed16  cmp     edx, 6
0x18000ed19  jz      short loc_18000ECD1
0x18000ed1b  mov     dword ptr [rsp+28h+JobInformation+4], 4
0x18000ed23  jmp     short loc_18000ECD1
0x18000ed25  cmp     edx, 2
0x18000ed28  jnz     short loc_18000ECD1
0x18000ed2a  jmp     short loc_18000ECC9
```
