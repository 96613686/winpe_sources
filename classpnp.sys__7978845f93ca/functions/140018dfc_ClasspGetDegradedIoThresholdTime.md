# ClasspGetDegradedIoThresholdTime

- ea: `0x140018dfc`
- end: `0x140018f62`
- name: `ClasspGetDegradedIoThresholdTime`
- size: `358`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400579b4`

## callees

- `0x140018dfc`
- `0x14001fc38`
- `0x140026f28`
- `0x14003e470`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140018eb0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018eb0`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140018ee3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018ec0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018ec0`

## string_xrefs

- `0x140018e80`: `RtlQueryRegistryValuesEx`
- `0x140018edc`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\DISK`

## pseudocode

```c
__int64 __fastcall ClasspGetDegradedIoThresholdTime(__int64 a1, __int64 a2, _DWORD *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v6; // edi
  int v7; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-39h] BYREF
  _QWORD v10[14]; // [rsp+48h] [rbp-29h] BYREF
  int v11; // [rsp+E0h] [rbp+6Fh] BYREF
  int v12; // [rsp+E4h] [rbp+73h]

  v12 = HIDWORD(a2);
  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1);
  }
  memset(v10, 0, sizeof(v10));
  LODWORD(v10[1]) = 288;
  v10[2] = L"IoThresholdTime";
  LODWORD(v10[4]) = 67108868;
  v10[3] = &v11;
  LODWORD(v10[6]) = 4;
  v10[5] = &v11;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v6 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
         0,
         L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\DISK",
         v10,
         0,
         0);
  if ( v6 < 0 )
  {
    *a3 = 0;
    v7 = 0;
  }
  else
  {
    v7 = v11;
    *a3 = v11;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1, v6, v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140018dfc  mov     rax, rsp
0x140018dff  mov     [rax+8], rbx
0x140018e03  mov     [rax+18h], rsi
0x140018e07  mov     [rax+10h], rdx
0x140018e0b  push    rbp
0x140018e0c  push    rdi
0x140018e0d  push    r15
0x140018e0f  lea     rbp, [rax-5Fh]
0x140018e13  sub     rsp, 0B0h
0x140018e1a  mov     rbx, r8
0x140018e1d  mov     [rbp+57h+arg_8], 0
0x140018e24  mov     rsi, rcx
0x140018e27  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e2e  lea     r15, WPP_GLOBAL_Control
0x140018e35  cmp     rcx, r15
0x140018e38  jz      short loc_140018E5F
0x140018e3a  mov     eax, [rcx+2Ch]
0x140018e3d  test    al, 2
0x140018e3f  jz      short loc_140018E5F
0x140018e41  cmp     byte ptr [rcx+29h], 5
0x140018e45  jb      short loc_140018E5F
0x140018e47  mov     rcx, [rcx+18h]
0x140018e4b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140018e52  mov     edx, 5Ch ; '\'
0x140018e57  mov     r9, rsi
0x140018e5a  call    WPP_SF_q
0x140018e5f  xor     edx, edx; Val
0x140018e61  lea     rcx, [rbp+57h+var_80]; void *
0x140018e65  lea     r8d, [rdx+70h]; Size
0x140018e69  call    memset
0x140018e6e  lea     rax, aIothresholdtim; "IoThresholdTime"
0x140018e75  mov     [rbp+57h+var_78], 120h
0x140018e7c  mov     [rbp+57h+var_70], rax
0x140018e80  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140018e87  lea     rax, [rbp+57h+arg_8]
0x140018e8b  mov     [rbp+57h+var_60], 4000004h
0x140018e92  mov     [rbp+57h+var_68], rax
0x140018e96  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018e9a  lea     rax, [rbp+57h+arg_8]
0x140018e9e  mov     [rbp+57h+var_50], 4
0x140018ea5  xorps   xmm0, xmm0
0x140018ea8  mov     [rbp+57h+var_58], rax
0x140018eac  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140018eb0  call    cs:__imp_RtlInitUnicodeString
0x140018eb7  nop     dword ptr [rax+rax+00h]
0x140018ebc  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140018ec0  call    cs:__imp_MmGetSystemRoutineAddress
0x140018ec7  nop     dword ptr [rax+rax+00h]
0x140018ecc  lea     r8, [rbp+57h+var_80]
0x140018ed0  mov     qword ptr [rsp+0C0h+var_A0], 0
0x140018ed9  test    rax, rax
0x140018edc  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140018ee3  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140018eeb  xor     r9d, r9d
0x140018eee  xor     ecx, ecx
0x140018ef0  call    _guard_dispatch_icall
0x140018ef5  mov     edi, eax
0x140018ef7  test    eax, eax
0x140018ef9  js      short loc_140018F04
0x140018efb  mov     r8d, [rbp+57h+arg_8]
0x140018eff  mov     [rbx], r8d
0x140018f02  jmp     short loc_140018F0D
0x140018f04  mov     dword ptr [rbx], 0
0x140018f0a  xor     r8d, r8d
0x140018f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f14  cmp     rcx, r15
0x140018f17  jz      short loc_140018F47
0x140018f19  mov     eax, [rcx+2Ch]
0x140018f1c  test    al, 2
0x140018f1e  jz      short loc_140018F47
0x140018f20  cmp     byte ptr [rcx+29h], 5
0x140018f24  jb      short loc_140018F47
0x140018f26  mov     rcx, [rcx+18h]
0x140018f2a  mov     edx, 5Dh ; ']'
0x140018f2f  mov     [rsp+0C0h+var_98], r8d
0x140018f34  mov     r9, rsi
0x140018f37  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140018f3e  mov     [rsp+0C0h+var_A0], edi
0x140018f42  call    WPP_SF_qDD
0x140018f47  lea     r11, [rsp+0C0h+var_10]
0x140018f4f  mov     eax, edi
0x140018f51  mov     rbx, [r11+20h]
0x140018f55  mov     rsi, [r11+30h]
0x140018f59  mov     rsp, r11
0x140018f5c  pop     r15
0x140018f5e  pop     rdi
0x140018f5f  pop     rbp
0x140018f60  retn
```
