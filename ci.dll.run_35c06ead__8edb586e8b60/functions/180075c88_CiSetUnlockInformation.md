# CiSetUnlockInformation

- ea: `0x180075c88`
- end: `0x180075e9c`
- name: `CiSetUnlockInformation`
- size: `532`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005eac0`

## callees

- `0x18000e16c`
- `0x1800150ec`
- `0x18002c1b0`
- `0x180058b68`
- `0x18006c568`
- `0x180071d98`
- `0x180075c88`
- `0x180076164`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180075d5e`
- `ntoskrnl!ExAllocatePool2` at `0x180075d5e`
- `ntoskrnl!PsGetCurrentProcess` at `0x180075d01`
- `ntoskrnl!PsGetCurrentProcess` at `0x180075d01`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075e80`
- `ntoskrnl!ExGetPreviousMode` at `0x180075cb2`
- `ntoskrnl!ExGetPreviousMode` at `0x180075cb2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180075e60`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180075e60`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075df5`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075e11`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075df5`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075e11`

## string_xrefs

- `0x180075dec`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180075e08`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180075e01`: `ManufacturingMode`

## pseudocode

```c
__int64 __fastcall CiSetUnlockInformation(PVOID Buffer, ULONG Length)
{
  size_t v2; // r15
  void *v4; // rsi
  KPROCESSOR_MODE PreviousMode; // r12
  __int64 v6; // rcx
  int WindowsLockdownMode; // ebx
  __int64 CurrentProcess; // rax
  void *Pool2; // rax
  __int64 v10; // r8
  _DWORD v12[18]; // [rsp+50h] [rbp-48h] BYREF
  char v13; // [rsp+B0h] [rbp+18h] BYREF
  int v14; // [rsp+B8h] [rbp+20h] BYREF

  v2 = Length;
  v13 = 0;
  v4 = 0;
  memset(v12, 0, 32);
  PreviousMode = ExGetPreviousMode();
  WindowsLockdownMode = SIPolicyQueryWindowsLockdownMode(v12);
  if ( WindowsLockdownMode >= 0 )
  {
    if ( (v12[0] & 0x4000000) != 0 )
    {
LABEL_3:
      WindowsLockdownMode = -1073741790;
      goto LABEL_15;
    }
    if ( !(_DWORD)v2 )
    {
      WindowsLockdownMode = -1073741820;
      goto LABEL_15;
    }
    if ( PreviousMode )
    {
      CurrentProcess = PsGetCurrentProcess();
      WindowsLockdownMode = (*((__int64 (__fastcall **)(__int64, char *))&xmmword_18004A630 + 1))(CurrentProcess, &v13);
      if ( WindowsLockdownMode < 0 )
        goto LABEL_15;
      v6 = *((unsigned int *)g_CipWhichLevelComparisons + 12);
      if ( !_bittest((const int *)&v6, v13 & 0xF) )
        goto LABEL_3;
      LOBYTE(v14) = PreviousMode;
      Pool2 = (void *)ExAllocatePool2(259, v2, 1668499779);
      v4 = Pool2;
      if ( !Pool2 )
      {
        WindowsLockdownMode = -1073741801;
        goto LABEL_15;
      }
      RtlCopyFromUser(Pool2, Buffer, v2);
      Buffer = v4;
    }
    v10 = (unsigned int)g_CiOptions;
    LOBYTE(v10) = g_CiOptions & 8;
    WindowsLockdownMode = SbValidateSkuUnlockToken(Buffer, (unsigned int)v2, v10);
    if ( WindowsLockdownMode >= 0 )
    {
      WindowsLockdownMode = CipWriteUnlockTokenToSystemPartition(Buffer, v2);
      if ( WindowsLockdownMode >= 0 )
      {
        RtlDeleteRegistryValue(
          0,
          L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
          L"SkuPolicyRequired");
        RtlDeleteRegistryValue(
          0,
          L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
          L"ManufacturingMode");
        WindowsLockdownMode = CiUpdatePolicies(0);
        v14 = 0;
        ZwUpdateWnfStateData(&WNF_CI_SMODE_CHANGE, &v14, 4);
      }
    }
  }
LABEL_15:
  CiInstrumentWindowsLockdownModeChange(v6, (unsigned int)WindowsLockdownMode);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x63734943u);
  return (unsigned int)WindowsLockdownMode;
}

```

## disassembly

```asm
0x180075c88  mov     rax, rsp
0x180075c8b  push    rbx
0x180075c8c  push    rsi
0x180075c8d  push    r12
0x180075c8f  push    r14
0x180075c91  push    r15
0x180075c93  sub     rsp, 70h
0x180075c97  mov     r15d, edx
0x180075c9a  mov     r14, rcx
0x180075c9d  mov     byte ptr [rax+18h], 0
0x180075ca1  xor     esi, esi
0x180075ca3  mov     [rax-50h], rsi
0x180075ca7  xorps   xmm0, xmm0
0x180075caa  movups  xmmword ptr [rax-48h], xmm0
0x180075cae  movups  xmmword ptr [rax-38h], xmm0
0x180075cb2  call    cs:__imp_ExGetPreviousMode
0x180075cb9  nop     dword ptr [rax+rax+00h]
0x180075cbe  mov     r12b, al
0x180075cc1  lea     rcx, [rsp+98h+var_48]
0x180075cc6  call    SIPolicyQueryWindowsLockdownMode
0x180075ccb  mov     ebx, eax
0x180075ccd  test    eax, eax
0x180075ccf  js      loc_180075E6C
0x180075cd5  test    [rsp+98h+var_48], 4000000h
0x180075cdd  jz      short loc_180075CE9
0x180075cdf  mov     ebx, 0C0000022h
0x180075ce4  jmp     loc_180075E6C
0x180075ce9  test    r15d, r15d
0x180075cec  jnz     short loc_180075CF8
0x180075cee  mov     ebx, 0C0000004h
0x180075cf3  jmp     loc_180075E6C
0x180075cf8  test    r12b, r12b
0x180075cfb  jz      loc_180075DB0
0x180075d01  call    cs:__imp_PsGetCurrentProcess
0x180075d08  nop     dword ptr [rax+rax+00h]
0x180075d0d  mov     rcx, rax
0x180075d10  mov     rax, qword ptr cs:xmmword_18004A630+8
0x180075d17  lea     rdx, [rsp+98h+arg_10]
0x180075d1f  call    _guard_dispatch_icall
0x180075d24  mov     ebx, eax
0x180075d26  test    eax, eax
0x180075d28  js      loc_180075E6C
0x180075d2e  movzx   edx, [rsp+98h+arg_10]
0x180075d36  and     edx, 0Fh
0x180075d39  mov     rax, cs:g_CipWhichLevelComparisons
0x180075d40  mov     ecx, [rax+30h]
0x180075d43  bt      ecx, edx
0x180075d46  jnb     short loc_180075CDF
0x180075d48  mov     byte ptr [rsp+98h+arg_18], r12b
0x180075d50  mov     r8d, 63734943h
0x180075d56  mov     rdx, r15
0x180075d59  mov     ecx, 103h
0x180075d5e  call    cs:__imp_ExAllocatePool2
0x180075d65  nop     dword ptr [rax+rax+00h]
0x180075d6a  mov     rsi, rax
0x180075d6d  mov     [rsp+98h+var_50], rax
0x180075d72  test    rax, rax
0x180075d75  jnz     short loc_180075D85
0x180075d77  mov     ebx, 0C0000017h
0x180075d7c  mov     [rsp+98h+var_54], ebx
0x180075d80  jmp     loc_180075E6C
0x180075d85  mov     r8, r15; Size
0x180075d88  mov     rdx, r14; Src
0x180075d8b  mov     rcx, rsi; void *
0x180075d8e  call    RtlCopyFromUser
0x180075d93  mov     r14, rsi
0x180075d96  mov     [rsp+98h+arg_0], rsi
0x180075d9e  jmp     short loc_180075DB0
0x180075da0  mov     ebx, eax
0x180075da2  mov     [rsp+98h+var_54], eax
0x180075da6  mov     rsi, [rsp+98h+var_50]
0x180075dab  jmp     loc_180075E6C
0x180075db0  mov     r8d, cs:g_CiOptions
0x180075db7  and     r8b, 8
0x180075dbb  mov     edx, r15d
0x180075dbe  mov     rcx, r14
0x180075dc1  call    SbValidateSkuUnlockToken
0x180075dc6  mov     ebx, eax
0x180075dc8  test    eax, eax
0x180075dca  js      loc_180075E6C
0x180075dd0  mov     edx, r15d; Length
0x180075dd3  mov     rcx, r14; Buffer
0x180075dd6  call    CipWriteUnlockTokenToSystemPartition
0x180075ddb  mov     ebx, eax
0x180075ddd  test    eax, eax
0x180075ddf  js      loc_180075E6C
0x180075de5  lea     r8, aSkupolicyrequi; "SkuPolicyRequired"
0x180075dec  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180075df3  xor     ecx, ecx; RelativeTo
0x180075df5  call    cs:__imp_RtlDeleteRegistryValue
0x180075dfc  nop     dword ptr [rax+rax+00h]
0x180075e01  lea     r8, aManufacturingm; "ManufacturingMode"
0x180075e08  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180075e0f  xor     ecx, ecx; RelativeTo
0x180075e11  call    cs:__imp_RtlDeleteRegistryValue
0x180075e18  nop     dword ptr [rax+rax+00h]
0x180075e1d  xor     ecx, ecx
0x180075e1f  call    CiUpdatePolicies
0x180075e24  mov     ebx, eax
0x180075e26  mov     [rsp+98h+arg_18], 0
0x180075e31  mov     [rsp+98h+var_68], 0
0x180075e39  mov     [rsp+98h+var_70], 0
0x180075e41  mov     [rsp+98h+var_78], 0
0x180075e4a  xor     r9d, r9d
0x180075e4d  lea     r8d, [r9+4]
0x180075e51  lea     rdx, [rsp+98h+arg_18]
0x180075e59  lea     rcx, WNF_CI_SMODE_CHANGE
0x180075e60  call    cs:__imp_ZwUpdateWnfStateData
0x180075e67  nop     dword ptr [rax+rax+00h]
0x180075e6c  mov     edx, ebx
0x180075e6e  call    CiInstrumentWindowsLockdownModeChange
0x180075e73  test    rsi, rsi
0x180075e76  jz      short loc_180075E8C
0x180075e78  mov     edx, 63734943h; Tag
0x180075e7d  mov     rcx, rsi; P
0x180075e80  call    cs:__imp_ExFreePoolWithTag
0x180075e87  nop     dword ptr [rax+rax+00h]
0x180075e8c  mov     eax, ebx
0x180075e8e  add     rsp, 70h
0x180075e92  pop     r15
0x180075e94  pop     r14
0x180075e96  pop     r12
0x180075e98  pop     rsi
0x180075e99  pop     rbx
0x180075e9a  retn
0x1800ea5db  push    rbp
0x1800ea5dd  sub     rsp, 40h
0x1800ea5e1  mov     rbp, rdx
0x1800ea5e4  xor     eax, eax
0x1800ea5e6  cmp     [rbp+0B8h], al
0x1800ea5ec  setnz   al
0x1800ea5ef  mov     [rbp+40h], eax
0x1800ea5f2  mov     eax, [rbp+40h]
0x1800ea5f5  add     rsp, 40h
0x1800ea5f9  pop     rbp
0x1800ea5fa  retn
```
