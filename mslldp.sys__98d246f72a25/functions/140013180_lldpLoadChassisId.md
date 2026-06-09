# lldpLoadChassisId

- ea: `0x140013180`
- end: `0x140013313`
- name: `lldpLoadChassisId`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013008`

## callees

- `0x140004b00`
- `0x140006670`
- `0x140013180`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013221`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013283`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013221`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013283`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140013255`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400132b6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140013232`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140013294`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140013232`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140013294`

## string_xrefs

- `0x1400131c1`: `RtlQueryRegistryValuesEx`
- `0x140013272`: `RtlQueryRegistryValuesEx`
- `0x1400131b1`: `ChassisId`
- `0x1400131c8`: `ComputerName`
- `0x1400132ac`: `ComputerName\ComputerName`

## pseudocode

```c
__int64 lldpLoadChassisId()
{
  PVOID SystemRoutineAddress; // rax
  unsigned int v1; // ebx
  PVOID v2; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  void *v5; // [rsp+40h] [rbp-C0h] BYREF
  int v6; // [rsp+48h] [rbp-B8h]
  const wchar_t *v7; // [rsp+50h] [rbp-B0h]
  __int64 v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+60h] [rbp-A0h]
  __int64 v10; // [rsp+68h] [rbp-98h]
  int v11; // [rsp+70h] [rbp-90h]
  __int64 v12; // [rsp+78h] [rbp-88h]
  __int128 v13; // [rsp+80h] [rbp-80h]
  __int128 v14; // [rsp+90h] [rbp-70h]
  __int128 v15; // [rsp+A0h] [rbp-60h]
  void *v16; // [rsp+B0h] [rbp-50h] BYREF
  int v17; // [rsp+B8h] [rbp-48h]
  const wchar_t *v18; // [rsp+C0h] [rbp-40h]
  __int64 v19; // [rsp+C8h] [rbp-38h]
  int v20; // [rsp+D0h] [rbp-30h]
  __int64 v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  __int128 v24; // [rsp+F0h] [rbp-10h]
  __int128 v25; // [rsp+100h] [rbp+0h]
  __int128 v26; // [rsp+110h] [rbp+10h]

  v5 = &lldpReadComputerName;
  v16 = &lldpReadComputerName;
  v6 = 20;
  v7 = L"ChassisId";
  v17 = 20;
  v18 = L"ComputerName";
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v19 = 0;
  v14 = 0;
  v20 = 0;
  v15 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v1 = ((__int64 (__fastcall *)(__int64, const wchar_t *, void **, _QWORD, _QWORD))SystemRoutineAddress)(
         1,
         L"Mslldp\\Parameters",
         &v5,
         0,
         0);
  if ( v1 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    v2 = MmGetSystemRoutineAddress(&DestinationString);
    if ( !v2 )
      v2 = RtlQueryRegistryValues;
    v1 = ((__int64 (__fastcall *)(__int64, const wchar_t *, void **, _QWORD, _QWORD))v2)(
           2,
           L"ComputerName\\ComputerName",
           &v16,
           0,
           0);
    if ( v1 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x140013180  mov     [rsp-8+arg_0], rbx
0x140013185  mov     [rsp-8+arg_8], rdi
0x14001318a  push    rbp
0x14001318b  lea     rbp, [rsp-20h]
0x140013190  sub     rsp, 120h
0x140013197  xor     edi, edi
0x140013199  lea     rdx, lldpReadComputerName
0x1400131a0  xorps   xmm0, xmm0
0x1400131a3  mov     [rsp+120h+var_E0], rdx
0x1400131a8  mov     ecx, 14h
0x1400131ad  mov     [rbp+20h+var_70], rdx
0x1400131b1  lea     rax, aChassisid; "ChassisId"
0x1400131b8  mov     [rsp+120h+var_D8], ecx
0x1400131bc  mov     [rsp+120h+var_D0], rax
0x1400131c1  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400131c8  lea     rax, aComputername; "ComputerName"
0x1400131cf  mov     [rbp+20h+var_68], ecx
0x1400131d2  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1400131d7  mov     [rbp+20h+var_60], rax
0x1400131db  mov     [rsp+120h+var_C8], rdi
0x1400131e0  mov     [rsp+120h+var_C0], edi
0x1400131e4  mov     [rsp+120h+var_B8], rdi
0x1400131e9  mov     [rsp+120h+var_B0], edi
0x1400131ed  mov     [rsp+120h+var_A8], rdi
0x1400131f2  movups  [rbp+20h+var_A0], xmm0
0x1400131f6  mov     [rbp+20h+var_58], rdi
0x1400131fa  movups  [rbp+20h+var_90], xmm0
0x1400131fe  mov     [rbp+20h+var_50], edi
0x140013201  movups  [rbp+20h+var_80], xmm0
0x140013205  mov     [rbp+20h+var_48], rdi
0x140013209  mov     [rbp+20h+var_40], edi
0x14001320c  mov     [rbp+20h+var_38], rdi
0x140013210  movups  [rbp+20h+var_30], xmm0
0x140013214  movups  [rbp+20h+var_20], xmm0
0x140013218  movups  [rbp+20h+var_10], xmm0
0x14001321c  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x140013221  call    cs:__imp_RtlInitUnicodeString
0x140013228  nop     dword ptr [rax+rax+00h]
0x14001322d  lea     rcx, [rsp+120h+DestinationString]; SystemRoutineName
0x140013232  call    cs:__imp_MmGetSystemRoutineAddress
0x140013239  nop     dword ptr [rax+rax+00h]
0x14001323e  lea     r8, [rsp+120h+var_E0]
0x140013243  mov     [rsp+120h+var_100], rdi
0x140013248  test    rax, rax
0x14001324b  lea     rdx, aMslldpParamete; "Mslldp\\Parameters"
0x140013252  lea     ecx, [rdi+1]
0x140013255  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14001325d  xor     r9d, r9d
0x140013260  call    _guard_dispatch_icall
0x140013265  mov     ebx, eax
0x140013267  test    eax, eax
0x140013269  jz      loc_1400132FB
0x14001326f  xorps   xmm0, xmm0
0x140013272  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140013279  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14001327e  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x140013283  call    cs:__imp_RtlInitUnicodeString
0x14001328a  nop     dword ptr [rax+rax+00h]
0x14001328f  lea     rcx, [rsp+120h+DestinationString]; SystemRoutineName
0x140013294  call    cs:__imp_MmGetSystemRoutineAddress
0x14001329b  nop     dword ptr [rax+rax+00h]
0x1400132a0  lea     r8, [rbp+20h+var_70]
0x1400132a4  mov     [rsp+120h+var_100], rdi
0x1400132a9  test    rax, rax
0x1400132ac  lea     rdx, aComputernameCo; "ComputerName\\ComputerName"
0x1400132b3  lea     ecx, [rdi+2]
0x1400132b6  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400132be  xor     r9d, r9d
0x1400132c1  call    _guard_dispatch_icall
0x1400132c6  mov     ebx, eax
0x1400132c8  test    eax, eax
0x1400132ca  jz      short loc_1400132FB
0x1400132cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132d3  lea     rax, WPP_GLOBAL_Control
0x1400132da  cmp     rcx, rax
0x1400132dd  jz      short loc_1400132FB
0x1400132df  cmp     byte ptr [rcx+29h], 2
0x1400132e3  jb      short loc_1400132FB
0x1400132e5  mov     rcx, [rcx+18h]
0x1400132e9  lea     edx, [rdi+11h]
0x1400132ec  mov     r9d, ebx
0x1400132ef  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x1400132f6  call    WPP_SF_d
0x1400132fb  lea     r11, [rsp+120h+var_s0]
0x140013303  mov     eax, ebx
0x140013305  mov     rbx, [r11+10h]
0x140013309  mov     rdi, [r11+18h]
0x14001330d  mov     rsp, r11
0x140013310  pop     rbp
0x140013311  retn
```
