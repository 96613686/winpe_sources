# ClasspGetMaximumTokenListIdentifier

- ea: `0x140030fdc`
- end: `0x140031142`
- name: `ClasspGetMaximumTokenListIdentifier`
- size: `358`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400561c0`

## callees

- `0x14001fc38`
- `0x140026f28`
- `0x140030fdc`
- `0x14003e470`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140031090`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031090`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400310c3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400310a0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400310a0`

## string_xrefs

- `0x140031060`: `RtlQueryRegistryValuesEx`
- `0x1400310bc`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\DISK`

## pseudocode

```c
__int64 __fastcall ClasspGetMaximumTokenListIdentifier(__int64 a1, __int64 a2, _DWORD *a3)
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
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1);
  }
  memset(v10, 0, sizeof(v10));
  LODWORD(v10[1]) = 288;
  v10[2] = L"MaximumListIdentifier";
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
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1, v6, v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140030fdc  mov     rax, rsp
0x140030fdf  mov     [rax+8], rbx
0x140030fe3  mov     [rax+18h], rsi
0x140030fe7  mov     [rax+10h], rdx
0x140030feb  push    rbp
0x140030fec  push    rdi
0x140030fed  push    r15
0x140030fef  lea     rbp, [rax-5Fh]
0x140030ff3  sub     rsp, 0B0h
0x140030ffa  mov     rbx, r8
0x140030ffd  mov     [rbp+57h+arg_8], 0
0x140031004  mov     rsi, rcx
0x140031007  mov     rcx, cs:WPP_GLOBAL_Control
0x14003100e  lea     r15, WPP_GLOBAL_Control
0x140031015  cmp     rcx, r15
0x140031018  jz      short loc_14003103F
0x14003101a  mov     eax, [rcx+2Ch]
0x14003101d  test    al, 2
0x14003101f  jz      short loc_14003103F
0x140031021  cmp     byte ptr [rcx+29h], 5
0x140031025  jb      short loc_14003103F
0x140031027  mov     rcx, [rcx+18h]
0x14003102b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140031032  mov     edx, 5Eh ; '^'
0x140031037  mov     r9, rsi
0x14003103a  call    WPP_SF_q
0x14003103f  xor     edx, edx; Val
0x140031041  lea     rcx, [rbp+57h+var_80]; void *
0x140031045  lea     r8d, [rdx+70h]; Size
0x140031049  call    memset
0x14003104e  lea     rax, aMaximumlistide; "MaximumListIdentifier"
0x140031055  mov     [rbp+57h+var_78], 120h
0x14003105c  mov     [rbp+57h+var_70], rax
0x140031060  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140031067  lea     rax, [rbp+57h+arg_8]
0x14003106b  mov     [rbp+57h+var_60], 4000004h
0x140031072  mov     [rbp+57h+var_68], rax
0x140031076  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003107a  lea     rax, [rbp+57h+arg_8]
0x14003107e  mov     [rbp+57h+var_50], 4
0x140031085  xorps   xmm0, xmm0
0x140031088  mov     [rbp+57h+var_58], rax
0x14003108c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140031090  call    cs:__imp_RtlInitUnicodeString
0x140031097  nop     dword ptr [rax+rax+00h]
0x14003109c  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1400310a0  call    cs:__imp_MmGetSystemRoutineAddress
0x1400310a7  nop     dword ptr [rax+rax+00h]
0x1400310ac  lea     r8, [rbp+57h+var_80]
0x1400310b0  mov     qword ptr [rsp+0C0h+var_A0], 0
0x1400310b9  test    rax, rax
0x1400310bc  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1400310c3  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400310cb  xor     r9d, r9d
0x1400310ce  xor     ecx, ecx
0x1400310d0  call    _guard_dispatch_icall
0x1400310d5  mov     edi, eax
0x1400310d7  test    eax, eax
0x1400310d9  js      short loc_1400310E4
0x1400310db  mov     r8d, [rbp+57h+arg_8]
0x1400310df  mov     [rbx], r8d
0x1400310e2  jmp     short loc_1400310ED
0x1400310e4  mov     dword ptr [rbx], 0
0x1400310ea  xor     r8d, r8d
0x1400310ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400310f4  cmp     rcx, r15
0x1400310f7  jz      short loc_140031127
0x1400310f9  mov     eax, [rcx+2Ch]
0x1400310fc  test    al, 2
0x1400310fe  jz      short loc_140031127
0x140031100  cmp     byte ptr [rcx+29h], 5
0x140031104  jb      short loc_140031127
0x140031106  mov     rcx, [rcx+18h]
0x14003110a  mov     edx, 5Fh ; '_'
0x14003110f  mov     [rsp+0C0h+var_98], r8d
0x140031114  mov     r9, rsi
0x140031117  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003111e  mov     [rsp+0C0h+var_A0], edi
0x140031122  call    WPP_SF_qDD
0x140031127  lea     r11, [rsp+0C0h+var_10]
0x14003112f  mov     eax, edi
0x140031131  mov     rbx, [r11+20h]
0x140031135  mov     rsi, [r11+30h]
0x140031139  mov     rsp, r11
0x14003113c  pop     r15
0x14003113e  pop     rdi
0x14003113f  pop     rbp
0x140031140  retn
```
