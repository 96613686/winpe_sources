# StSecpSealKeyTestHookSet

- ea: `0x14000ef5c`
- end: `0x14000f03e`
- name: `StSecpSealKeyTestHookSet`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ecd4`
- `0x14000f044`

## callees

- `0x140003580`
- `0x14000ef5c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000efd6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000efd6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000efe6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000efe6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000f009`

## string_xrefs

- `0x14000f002`: `\REGISTRY\MACHINE\Software\Microsoft\StorageSec\Encrypt`
- `0x14000ef87`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
_BOOL8 StSecpSealKeyTestHookSet()
{
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  __int64 v3; // [rsp+40h] [rbp-19h] BYREF
  int v4; // [rsp+48h] [rbp-11h]
  const wchar_t *v5; // [rsp+50h] [rbp-9h]
  int *v6; // [rsp+58h] [rbp-1h]
  int v7; // [rsp+60h] [rbp+7h]
  __int64 v8; // [rsp+68h] [rbp+Fh]
  int v9; // [rsp+70h] [rbp+17h]
  __int64 v10; // [rsp+78h] [rbp+1Fh]
  int v11; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]
  __int128 v13; // [rsp+90h] [rbp+37h]
  __int128 v14; // [rsp+A0h] [rbp+47h]

  v3 = 0;
  v4 = 288;
  v5 = L"SkipSealKey";
  v7 = 0x4000000;
  v6 = &g_SkipSealKey;
  v8 = 0;
  v9 = 4;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  if ( ((int (__fastcall *)(_QWORD, const WCHAR *, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(
         0,
         L"\\REGISTRY\\MACHINE\\Software\\Microsoft\\StorageSec\\Encrypt",
         &v3,
         0,
         0) < 0 )
    g_SkipSealKey = 0;
  return g_SkipSealKey != 0;
}

```

## disassembly

```asm
0x14000ef5c  push    rbp
0x14000ef5e  lea     rbp, [rsp-57h]
0x14000ef63  sub     rsp, 0B0h
0x14000ef6a  xorps   xmm0, xmm0
0x14000ef6d  mov     [rbp+57h+var_70], 0
0x14000ef75  lea     rax, aSkipsealkey; "SkipSealKey"
0x14000ef7c  mov     [rbp+57h+var_68], 120h
0x14000ef83  mov     [rbp+57h+var_60], rax
0x14000ef87  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000ef8e  lea     rax, g_SkipSealKey
0x14000ef95  mov     [rbp+57h+var_50], 4000000h
0x14000ef9c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000efa0  mov     [rbp+57h+var_58], rax
0x14000efa4  mov     [rbp+57h+var_48], 0
0x14000efac  mov     [rbp+57h+var_40], 4
0x14000efb3  mov     [rbp+57h+var_38], 0
0x14000efbb  mov     [rbp+57h+var_30], 0
0x14000efc2  mov     [rbp+57h+var_28], 0
0x14000efca  movups  [rbp+57h+var_20], xmm0
0x14000efce  movups  [rbp+57h+var_10], xmm0
0x14000efd2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000efd6  call    cs:__imp_RtlInitUnicodeString
0x14000efdd  nop     dword ptr [rax+rax+00h]
0x14000efe2  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14000efe6  call    cs:__imp_MmGetSystemRoutineAddress
0x14000efed  nop     dword ptr [rax+rax+00h]
0x14000eff2  lea     r8, [rbp+57h+var_70]
0x14000eff6  mov     [rsp+0B0h+var_90], 0
0x14000efff  test    rax, rax
0x14000f002  lea     rdx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\Software\\Microsof"...
0x14000f009  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000f011  xor     r9d, r9d
0x14000f014  xor     ecx, ecx
0x14000f016  call    _guard_dispatch_icall
0x14000f01b  test    eax, eax
0x14000f01d  jns     short loc_14000F029
0x14000f01f  mov     cs:g_SkipSealKey, 0
0x14000f029  xor     eax, eax
0x14000f02b  cmp     cs:g_SkipSealKey, eax
0x14000f031  setnz   al
0x14000f034  add     rsp, 0B0h
0x14000f03b  pop     rbp
0x14000f03c  retn
```
