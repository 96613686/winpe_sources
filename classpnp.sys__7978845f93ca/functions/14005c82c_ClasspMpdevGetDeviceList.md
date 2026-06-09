# ClasspMpdevGetDeviceList

- ea: `0x14005c82c`
- end: `0x14005c8f1`
- name: `ClasspMpdevGetDeviceList`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14005ce5c`

## callees

- `0x14003e470`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14005c89a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005c89a`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14005c8cd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14005c8aa`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14005c8aa`

## string_xrefs

- `0x14005c86e`: `RtlQueryRegistryValuesEx`
- `0x14005c8c6`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\MPDEV`

## pseudocode

```c
__int64 __fastcall ClasspMpdevGetDeviceList(__int64 a1, __int64 a2)
{
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v6[14]; // [rsp+40h] [rbp-19h] BYREF
  int v7; // [rsp+C0h] [rbp+67h] BYREF
  int v8; // [rsp+C4h] [rbp+6Bh]

  v8 = HIDWORD(a1);
  v7 = 0;
  memset(v6, 0, sizeof(v6));
  LODWORD(v6[1]) = 304;
  v6[2] = L"MPIOSupportedDeviceList";
  v6[3] = a2;
  v6[5] = &v7;
  LODWORD(v6[4]) = 117440519;
  LODWORD(v6[6]) = 4;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  return ((__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
           0,
           L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MPDEV",
           v6,
           0,
           0);
}

```

## disassembly

```asm
0x14005c82c  mov     [rsp-8+arg_8], rbx
0x14005c831  mov     [rsp-8+arg_0], rcx
0x14005c836  push    rbp
0x14005c837  lea     rbp, [rsp-57h]
0x14005c83c  sub     rsp, 0B0h
0x14005c843  mov     rbx, rdx
0x14005c846  mov     dword ptr [rbp+57h+arg_0], 0
0x14005c84d  xor     edx, edx; Val
0x14005c84f  lea     rcx, [rbp+57h+var_70]; void *
0x14005c853  lea     r8d, [rdx+70h]; Size
0x14005c857  call    memset
0x14005c85c  lea     rax, aMpiosupportedd; "MPIOSupportedDeviceList"
0x14005c863  mov     [rbp+57h+var_68], 130h
0x14005c86a  mov     [rbp+57h+var_60], rax
0x14005c86e  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14005c875  lea     rax, [rbp+57h+arg_0]
0x14005c879  mov     [rbp+57h+var_58], rbx
0x14005c87d  xorps   xmm0, xmm0
0x14005c880  mov     [rbp+57h+var_48], rax
0x14005c884  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005c888  mov     [rbp+57h+var_50], 7000007h
0x14005c88f  mov     [rbp+57h+var_40], 4
0x14005c896  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005c89a  call    cs:__imp_RtlInitUnicodeString
0x14005c8a1  nop     dword ptr [rax+rax+00h]
0x14005c8a6  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14005c8aa  call    cs:__imp_MmGetSystemRoutineAddress
0x14005c8b1  nop     dword ptr [rax+rax+00h]
0x14005c8b6  lea     r8, [rbp+57h+var_70]
0x14005c8ba  mov     [rsp+0B0h+var_90], 0
0x14005c8c3  test    rax, rax
0x14005c8c6  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x14005c8cd  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14005c8d5  xor     r9d, r9d
0x14005c8d8  xor     ecx, ecx
0x14005c8da  call    _guard_dispatch_icall
0x14005c8df  mov     rbx, [rsp+0B0h+arg_8]
0x14005c8e7  add     rsp, 0B0h
0x14005c8ee  pop     rbp
0x14005c8ef  retn
```
