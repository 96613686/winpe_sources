# CiSetUnlockInformation

- ea: `0x1800759a8`
- end: `0x180075bbc`
- name: `CiSetUnlockInformation`
- size: `532`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005eb20`

## callees

- `0x18000e15c`
- `0x18001508c`
- `0x18002c000`
- `0x180058c40`
- `0x18006c3f8`
- `0x180071ab8`
- `0x1800759a8`
- `0x180075e84`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180075a7e`
- `ntoskrnl!ExAllocatePool2` at `0x180075a7e`
- `ntoskrnl!PsGetCurrentProcess` at `0x180075a21`
- `ntoskrnl!PsGetCurrentProcess` at `0x180075a21`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075ba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075ba0`
- `ntoskrnl!ExGetPreviousMode` at `0x1800759d2`
- `ntoskrnl!ExGetPreviousMode` at `0x1800759d2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180075b80`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180075b80`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075b15`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075b31`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075b15`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180075b31`

## string_xrefs

- `0x180075b0c`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180075b28`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180075b21`: `ManufacturingMode`

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
      WindowsLockdownMode = (*((__int64 (__fastcall **)(__int64, char *))&xmmword_18004A590 + 1))(CurrentProcess, &v13);
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
0x1800759a8  mov     rax, rsp
0x1800759ab  push    rbx
0x1800759ac  push    rsi
0x1800759ad  push    r12
0x1800759af  push    r14
0x1800759b1  push    r15
0x1800759b3  sub     rsp, 70h
0x1800759b7  mov     r15d, edx
0x1800759ba  mov     r14, rcx
0x1800759bd  mov     byte ptr [rax+18h], 0
0x1800759c1  xor     esi, esi
0x1800759c3  mov     [rax-50h], rsi
0x1800759c7  xorps   xmm0, xmm0
0x1800759ca  movups  xmmword ptr [rax-48h], xmm0
0x1800759ce  movups  xmmword ptr [rax-38h], xmm0
0x1800759d2  call    cs:__imp_ExGetPreviousMode
0x1800759d9  nop     dword ptr [rax+rax+00h]
0x1800759de  mov     r12b, al
0x1800759e1  lea     rcx, [rsp+98h+var_48]
0x1800759e6  call    SIPolicyQueryWindowsLockdownMode
0x1800759eb  mov     ebx, eax
0x1800759ed  test    eax, eax
0x1800759ef  js      loc_180075B8C
0x1800759f5  test    [rsp+98h+var_48], 4000000h
0x1800759fd  jz      short loc_180075A09
0x1800759ff  mov     ebx, 0C0000022h
0x180075a04  jmp     loc_180075B8C
0x180075a09  test    r15d, r15d
0x180075a0c  jnz     short loc_180075A18
0x180075a0e  mov     ebx, 0C0000004h
0x180075a13  jmp     loc_180075B8C
0x180075a18  test    r12b, r12b
0x180075a1b  jz      loc_180075AD0
0x180075a21  call    cs:__imp_PsGetCurrentProcess
0x180075a28  nop     dword ptr [rax+rax+00h]
0x180075a2d  mov     rcx, rax
0x180075a30  mov     rax, qword ptr cs:xmmword_18004A590+8
0x180075a37  lea     rdx, [rsp+98h+arg_10]
0x180075a3f  call    _guard_dispatch_icall
0x180075a44  mov     ebx, eax
0x180075a46  test    eax, eax
0x180075a48  js      loc_180075B8C
0x180075a4e  movzx   edx, [rsp+98h+arg_10]
0x180075a56  and     edx, 0Fh
0x180075a59  mov     rax, cs:g_CipWhichLevelComparisons
0x180075a60  mov     ecx, [rax+30h]
0x180075a63  bt      ecx, edx
0x180075a66  jnb     short loc_1800759FF
0x180075a68  mov     byte ptr [rsp+98h+arg_18], r12b
0x180075a70  mov     r8d, 63734943h
0x180075a76  mov     rdx, r15
0x180075a79  mov     ecx, 103h
0x180075a7e  call    cs:__imp_ExAllocatePool2
0x180075a85  nop     dword ptr [rax+rax+00h]
0x180075a8a  mov     rsi, rax
0x180075a8d  mov     [rsp+98h+var_50], rax
0x180075a92  test    rax, rax
0x180075a95  jnz     short loc_180075AA5
0x180075a97  mov     ebx, 0C0000017h
0x180075a9c  mov     [rsp+98h+var_54], ebx
0x180075aa0  jmp     loc_180075B8C
0x180075aa5  mov     r8, r15; Size
0x180075aa8  mov     rdx, r14; Src
0x180075aab  mov     rcx, rsi; void *
0x180075aae  call    RtlCopyFromUser
0x180075ab3  mov     r14, rsi
0x180075ab6  mov     [rsp+98h+arg_0], rsi
0x180075abe  jmp     short loc_180075AD0
0x180075ac0  mov     ebx, eax
0x180075ac2  mov     [rsp+98h+var_54], eax
0x180075ac6  mov     rsi, [rsp+98h+var_50]
0x180075acb  jmp     loc_180075B8C
0x180075ad0  mov     r8d, cs:g_CiOptions
0x180075ad7  and     r8b, 8
0x180075adb  mov     edx, r15d
0x180075ade  mov     rcx, r14
0x180075ae1  call    SbValidateSkuUnlockToken
0x180075ae6  mov     ebx, eax
0x180075ae8  test    eax, eax
0x180075aea  js      loc_180075B8C
0x180075af0  mov     edx, r15d; Length
0x180075af3  mov     rcx, r14; Buffer
0x180075af6  call    CipWriteUnlockTokenToSystemPartition
0x180075afb  mov     ebx, eax
0x180075afd  test    eax, eax
0x180075aff  js      loc_180075B8C
0x180075b05  lea     r8, aSkupolicyrequi; "SkuPolicyRequired"
0x180075b0c  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180075b13  xor     ecx, ecx; RelativeTo
0x180075b15  call    cs:__imp_RtlDeleteRegistryValue
0x180075b1c  nop     dword ptr [rax+rax+00h]
0x180075b21  lea     r8, aManufacturingm; "ManufacturingMode"
0x180075b28  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180075b2f  xor     ecx, ecx; RelativeTo
0x180075b31  call    cs:__imp_RtlDeleteRegistryValue
0x180075b38  nop     dword ptr [rax+rax+00h]
0x180075b3d  xor     ecx, ecx
0x180075b3f  call    CiUpdatePolicies
0x180075b44  mov     ebx, eax
0x180075b46  mov     [rsp+98h+arg_18], 0
0x180075b51  mov     [rsp+98h+var_68], 0
0x180075b59  mov     [rsp+98h+var_70], 0
0x180075b61  mov     [rsp+98h+var_78], 0
0x180075b6a  xor     r9d, r9d
0x180075b6d  lea     r8d, [r9+4]
0x180075b71  lea     rdx, [rsp+98h+arg_18]
0x180075b79  lea     rcx, WNF_CI_SMODE_CHANGE
0x180075b80  call    cs:__imp_ZwUpdateWnfStateData
0x180075b87  nop     dword ptr [rax+rax+00h]
0x180075b8c  mov     edx, ebx
0x180075b8e  call    CiInstrumentWindowsLockdownModeChange
0x180075b93  test    rsi, rsi
0x180075b96  jz      short loc_180075BAC
0x180075b98  mov     edx, 63734943h; Tag
0x180075b9d  mov     rcx, rsi; P
0x180075ba0  call    cs:__imp_ExFreePoolWithTag
0x180075ba7  nop     dword ptr [rax+rax+00h]
0x180075bac  mov     eax, ebx
0x180075bae  add     rsp, 70h
0x180075bb2  pop     r15
0x180075bb4  pop     r14
0x180075bb6  pop     r12
0x180075bb8  pop     rsi
0x180075bb9  pop     rbx
0x180075bba  retn
0x1800e9d9b  push    rbp
0x1800e9d9d  sub     rsp, 40h
0x1800e9da1  mov     rbp, rdx
0x1800e9da4  xor     eax, eax
0x1800e9da6  cmp     [rbp+0B8h], al
0x1800e9dac  setnz   al
0x1800e9daf  mov     [rbp+40h], eax
0x1800e9db2  mov     eax, [rbp+40h]
0x1800e9db5  add     rsp, 40h
0x1800e9db9  pop     rbp
0x1800e9dba  retn
```
