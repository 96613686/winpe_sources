# CiSetUnlockInformation

- ea: `0x1800743dc`
- end: `0x180074601`
- name: `CiSetUnlockInformation`
- size: `549`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005e420`

## callees

- `0x18000e15c`
- `0x18002bfd0`
- `0x18002c040`
- `0x180057f28`
- `0x18006b178`
- `0x180070808`
- `0x1800743dc`
- `0x1800748c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800744be`
- `ntoskrnl!ExAllocatePool2` at `0x1800744be`
- `ntoskrnl!PsGetCurrentProcess` at `0x180074451`
- `ntoskrnl!PsGetCurrentProcess` at `0x180074451`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800745e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800745e0`
- `ntoskrnl!ExGetPreviousMode` at `0x18007443d`
- `ntoskrnl!ExGetPreviousMode` at `0x18007443d`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1800e84d5`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1800e84d5`
- `ntoskrnl!ProbeForRead` at `0x1800744a4`
- `ntoskrnl!ProbeForRead` at `0x1800744a4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800745c0`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800745c0`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180074555`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180074571`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180074555`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x180074571`

## string_xrefs

- `0x18007454c`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074568`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074561`: `ManufacturingMode`

## pseudocode

```c
__int64 __fastcall CiSetUnlockInformation(PVOID Buffer, ULONG Length)
{
  SIZE_T v2; // r15
  void *v4; // rsi
  __int64 v5; // rcx
  int WindowsLockdownMode; // ebx
  __int64 CurrentProcess; // rax
  void *Pool2; // rax
  __int64 v9; // r8
  _DWORD v11[14]; // [rsp+50h] [rbp-38h] BYREF
  char v12; // [rsp+A0h] [rbp+18h] BYREF
  int v13; // [rsp+A8h] [rbp+20h] BYREF

  v2 = Length;
  v12 = 0;
  v4 = 0;
  memset(v11, 0, 32);
  WindowsLockdownMode = SIPolicyQueryWindowsLockdownMode(v11);
  if ( WindowsLockdownMode >= 0 )
  {
    if ( (v11[0] & 0x4000000) != 0 )
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
    if ( ExGetPreviousMode() == 1 )
    {
      CurrentProcess = PsGetCurrentProcess();
      WindowsLockdownMode = (*((__int64 (__fastcall **)(__int64, char *))&xmmword_180049630 + 1))(CurrentProcess, &v12);
      if ( WindowsLockdownMode < 0 )
        goto LABEL_15;
      v5 = *((unsigned int *)g_CipWhichLevelComparisons + 12);
      if ( !_bittest((const int *)&v5, v12 & 0xF) )
        goto LABEL_3;
      ProbeForRead(Buffer, v2, 1u);
      Pool2 = (void *)ExAllocatePool2(259, v2, 1668499779);
      v4 = Pool2;
      if ( !Pool2 )
      {
        WindowsLockdownMode = -1073741801;
        goto LABEL_15;
      }
      memmove(Pool2, Buffer, v2);
      Buffer = v4;
    }
    v9 = (unsigned int)g_CiOptions;
    LOBYTE(v9) = g_CiOptions & 8;
    WindowsLockdownMode = SbValidateSkuUnlockToken(Buffer, (unsigned int)v2, v9);
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
        v13 = 0;
        ZwUpdateWnfStateData(&WNF_CI_SMODE_CHANGE, &v13, 4);
      }
    }
  }
LABEL_15:
  CiInstrumentWindowsLockdownModeChange(v5, (unsigned int)WindowsLockdownMode);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x63734943u);
  return (unsigned int)WindowsLockdownMode;
}

```

## disassembly

```asm
0x1800743dc  mov     rax, rsp
0x1800743df  mov     [rax+10h], rbx
0x1800743e3  push    rsi
0x1800743e4  push    r14
0x1800743e6  push    r15
0x1800743e8  sub     rsp, 70h
0x1800743ec  mov     r15d, edx
0x1800743ef  mov     r14, rcx
0x1800743f2  mov     byte ptr [rax+18h], 0
0x1800743f6  xor     esi, esi
0x1800743f8  mov     [rax-40h], rsi
0x1800743fc  xorps   xmm0, xmm0
0x1800743ff  movups  xmmword ptr [rax-38h], xmm0
0x180074403  movups  xmmword ptr [rax-28h], xmm0
0x180074407  lea     rcx, [rax-38h]
0x18007440b  call    SIPolicyQueryWindowsLockdownMode
0x180074410  mov     ebx, eax
0x180074412  test    eax, eax
0x180074414  js      loc_1800745CC
0x18007441a  test    [rsp+88h+var_38], 4000000h
0x180074422  jz      short loc_18007442E
0x180074424  mov     ebx, 0C0000022h
0x180074429  jmp     loc_1800745CC
0x18007442e  test    r15d, r15d
0x180074431  jnz     short loc_18007443D
0x180074433  mov     ebx, 0C0000004h
0x180074438  jmp     loc_1800745CC
0x18007443d  call    cs:__imp_ExGetPreviousMode
0x180074444  nop     dword ptr [rax+rax+00h]
0x180074449  cmp     al, 1
0x18007444b  jnz     loc_180074510
0x180074451  call    cs:__imp_PsGetCurrentProcess
0x180074458  nop     dword ptr [rax+rax+00h]
0x18007445d  mov     rcx, rax
0x180074460  mov     rax, qword ptr cs:xmmword_180049630+8
0x180074467  lea     rdx, [rsp+88h+arg_10]
0x18007446f  call    _guard_dispatch_icall
0x180074474  mov     ebx, eax
0x180074476  test    eax, eax
0x180074478  js      loc_1800745CC
0x18007447e  movzx   edx, [rsp+88h+arg_10]
0x180074486  and     edx, 0Fh
0x180074489  mov     rax, cs:g_CipWhichLevelComparisons
0x180074490  mov     ecx, [rax+30h]
0x180074493  bt      ecx, edx
0x180074496  jnb     short loc_180074424
0x180074498  mov     r8d, 1; Alignment
0x18007449e  mov     rdx, r15; Length
0x1800744a1  mov     rcx, r14; Address
0x1800744a4  call    cs:__imp_ProbeForRead
0x1800744ab  nop     dword ptr [rax+rax+00h]
0x1800744b0  mov     r8d, 63734943h
0x1800744b6  mov     rdx, r15
0x1800744b9  mov     ecx, 103h
0x1800744be  call    cs:__imp_ExAllocatePool2
0x1800744c5  nop     dword ptr [rax+rax+00h]
0x1800744ca  mov     rsi, rax
0x1800744cd  mov     [rsp+88h+var_40], rax
0x1800744d2  test    rax, rax
0x1800744d5  jnz     short loc_1800744E5
0x1800744d7  mov     ebx, 0C0000017h
0x1800744dc  mov     [rsp+88h+var_48], ebx
0x1800744e0  jmp     loc_1800745CC
0x1800744e5  mov     r8, r15; Size
0x1800744e8  mov     rdx, r14; Src
0x1800744eb  mov     rcx, rsi; void *
0x1800744ee  call    memmove
0x1800744f3  mov     r14, rsi
0x1800744f6  mov     [rsp+88h+arg_0], rsi
0x1800744fe  jmp     short loc_180074510
0x180074500  mov     ebx, eax
0x180074502  mov     [rsp+88h+var_48], eax
0x180074506  mov     rsi, [rsp+88h+var_40]
0x18007450b  jmp     loc_1800745CC
0x180074510  mov     r8d, cs:g_CiOptions
0x180074517  and     r8b, 8
0x18007451b  mov     edx, r15d
0x18007451e  mov     rcx, r14
0x180074521  call    SbValidateSkuUnlockToken
0x180074526  mov     ebx, eax
0x180074528  test    eax, eax
0x18007452a  js      loc_1800745CC
0x180074530  mov     edx, r15d; Length
0x180074533  mov     rcx, r14; Buffer
0x180074536  call    CipWriteUnlockTokenToSystemPartition
0x18007453b  mov     ebx, eax
0x18007453d  test    eax, eax
0x18007453f  js      loc_1800745CC
0x180074545  lea     r8, aSkupolicyrequi; "SkuPolicyRequired"
0x18007454c  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074553  xor     ecx, ecx; RelativeTo
0x180074555  call    cs:__imp_RtlDeleteRegistryValue
0x18007455c  nop     dword ptr [rax+rax+00h]
0x180074561  lea     r8, aManufacturingm; "ManufacturingMode"
0x180074568  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007456f  xor     ecx, ecx; RelativeTo
0x180074571  call    cs:__imp_RtlDeleteRegistryValue
0x180074578  nop     dword ptr [rax+rax+00h]
0x18007457d  xor     ecx, ecx
0x18007457f  call    CiUpdatePolicies
0x180074584  mov     ebx, eax
0x180074586  mov     [rsp+88h+arg_18], 0
0x180074591  mov     [rsp+88h+var_58], 0
0x180074599  mov     [rsp+88h+var_60], 0
0x1800745a1  mov     [rsp+88h+var_68], 0
0x1800745aa  xor     r9d, r9d
0x1800745ad  lea     r8d, [r9+4]
0x1800745b1  lea     rdx, [rsp+88h+arg_18]
0x1800745b9  lea     rcx, WNF_CI_SMODE_CHANGE
0x1800745c0  call    cs:__imp_ZwUpdateWnfStateData
0x1800745c7  nop     dword ptr [rax+rax+00h]
0x1800745cc  mov     edx, ebx
0x1800745ce  call    CiInstrumentWindowsLockdownModeChange
0x1800745d3  test    rsi, rsi
0x1800745d6  jz      short loc_1800745EC
0x1800745d8  mov     edx, 63734943h; Tag
0x1800745dd  mov     rcx, rsi; P
0x1800745e0  call    cs:__imp_ExFreePoolWithTag
0x1800745e7  nop     dword ptr [rax+rax+00h]
0x1800745ec  mov     eax, ebx
0x1800745ee  mov     rbx, [rsp+88h+arg_8]
0x1800745f6  add     rsp, 70h
0x1800745fa  pop     r15
0x1800745fc  pop     r14
0x1800745fe  pop     rsi
0x1800745ff  retn
0x1800e84cc  push    rbp
0x1800e84ce  sub     rsp, 40h
0x1800e84d2  mov     rbp, rdx
0x1800e84d5  call    cs:__imp_ExSystemExceptionFilter
0x1800e84dc  nop     dword ptr [rax+rax+00h]
0x1800e84e1  nop
0x1800e84e2  add     rsp, 40h
0x1800e84e6  pop     rbp
0x1800e84e7  retn
```
