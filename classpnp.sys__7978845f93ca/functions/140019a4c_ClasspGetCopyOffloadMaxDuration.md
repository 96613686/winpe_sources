# ClasspGetCopyOffloadMaxDuration

- ea: `0x140019a4c`
- end: `0x140019bbb`
- name: `ClasspGetCopyOffloadMaxDuration`
- size: `367`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400579b4`

## callees

- `0x140019a4c`
- `0x14001fc38`
- `0x140026f28`
- `0x14003e470`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140019b00`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019b00`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140019b33`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140019b10`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140019b10`

## string_xrefs

- `0x140019ad0`: `RtlQueryRegistryValuesEx`
- `0x140019b2c`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\DISK`
- `0x140019abe`: `CopyOffloadMaxTargetDuration`

## pseudocode

```c
__int64 __fastcall ClasspGetCopyOffloadMaxDuration(__int64 a1, __int64 a2, unsigned int *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v6; // edi
  int v7; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-39h] BYREF
  _QWORD v10[14]; // [rsp+48h] [rbp-29h] BYREF
  unsigned int v11; // [rsp+E0h] [rbp+6Fh] BYREF
  int v12; // [rsp+E4h] [rbp+73h]

  v12 = HIDWORD(a2);
  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1);
  }
  memset(v10, 0, sizeof(v10));
  LODWORD(v10[1]) = 288;
  v10[2] = L"CopyOffloadMaxTargetDuration";
  LODWORD(v10[4]) = 0x4000000;
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
  if ( v6 < 0 || (v7 = v11, v11 <= 4) )
  {
    *a3 = 4;
    v7 = 4;
  }
  else
  {
    *a3 = v11;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1, v6, v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140019a4c  mov     rax, rsp
0x140019a4f  mov     [rax+8], rbx
0x140019a53  mov     [rax+18h], rsi
0x140019a57  mov     [rax+10h], rdx
0x140019a5b  push    rbp
0x140019a5c  push    rdi
0x140019a5d  push    r15
0x140019a5f  lea     rbp, [rax-5Fh]
0x140019a63  sub     rsp, 0B0h
0x140019a6a  mov     rbx, r8
0x140019a6d  mov     [rbp+57h+arg_8], 0
0x140019a74  mov     rsi, rcx
0x140019a77  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a7e  lea     r15, WPP_GLOBAL_Control
0x140019a85  cmp     rcx, r15
0x140019a88  jz      short loc_140019AAF
0x140019a8a  mov     eax, [rcx+2Ch]
0x140019a8d  test    al, 2
0x140019a8f  jz      short loc_140019AAF
0x140019a91  cmp     byte ptr [rcx+29h], 5
0x140019a95  jb      short loc_140019AAF
0x140019a97  mov     rcx, [rcx+18h]
0x140019a9b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140019aa2  mov     edx, 60h ; '`'
0x140019aa7  mov     r9, rsi
0x140019aaa  call    WPP_SF_q
0x140019aaf  xor     edx, edx; Val
0x140019ab1  lea     rcx, [rbp+57h+var_80]; void *
0x140019ab5  lea     r8d, [rdx+70h]; Size
0x140019ab9  call    memset
0x140019abe  lea     rax, aCopyoffloadmax; "CopyOffloadMaxTargetDuration"
0x140019ac5  mov     [rbp+57h+var_78], 120h
0x140019acc  mov     [rbp+57h+var_70], rax
0x140019ad0  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140019ad7  lea     rax, [rbp+57h+arg_8]
0x140019adb  mov     [rbp+57h+var_60], 4000000h
0x140019ae2  mov     [rbp+57h+var_68], rax
0x140019ae6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019aea  lea     rax, [rbp+57h+arg_8]
0x140019aee  mov     [rbp+57h+var_50], 4
0x140019af5  xorps   xmm0, xmm0
0x140019af8  mov     [rbp+57h+var_58], rax
0x140019afc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140019b00  call    cs:__imp_RtlInitUnicodeString
0x140019b07  nop     dword ptr [rax+rax+00h]
0x140019b0c  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140019b10  call    cs:__imp_MmGetSystemRoutineAddress
0x140019b17  nop     dword ptr [rax+rax+00h]
0x140019b1c  lea     r8, [rbp+57h+var_80]
0x140019b20  mov     qword ptr [rsp+0C0h+var_A0], 0
0x140019b29  test    rax, rax
0x140019b2c  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140019b33  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140019b3b  xor     r9d, r9d
0x140019b3e  xor     ecx, ecx
0x140019b40  call    _guard_dispatch_icall
0x140019b45  mov     edi, eax
0x140019b47  test    eax, eax
0x140019b49  js      short loc_140019B5A
0x140019b4b  mov     r8d, [rbp+57h+arg_8]
0x140019b4f  cmp     r8d, 4
0x140019b53  jbe     short loc_140019B5A
0x140019b55  mov     [rbx], r8d
0x140019b58  jmp     short loc_140019B66
0x140019b5a  mov     dword ptr [rbx], 4
0x140019b60  mov     r8d, 4
0x140019b66  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b6d  cmp     rcx, r15
0x140019b70  jz      short loc_140019BA0
0x140019b72  mov     eax, [rcx+2Ch]
0x140019b75  test    al, 2
0x140019b77  jz      short loc_140019BA0
0x140019b79  cmp     byte ptr [rcx+29h], 5
0x140019b7d  jb      short loc_140019BA0
0x140019b7f  mov     rcx, [rcx+18h]
0x140019b83  mov     edx, 61h ; 'a'
0x140019b88  mov     [rsp+0C0h+var_98], r8d
0x140019b8d  mov     r9, rsi
0x140019b90  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140019b97  mov     [rsp+0C0h+var_A0], edi
0x140019b9b  call    WPP_SF_qDD
0x140019ba0  lea     r11, [rsp+0C0h+var_10]
0x140019ba8  mov     eax, edi
0x140019baa  mov     rbx, [r11+20h]
0x140019bae  mov     rsi, [r11+30h]
0x140019bb2  mov     rsp, r11
0x140019bb5  pop     r15
0x140019bb7  pop     rdi
0x140019bb8  pop     rbp
0x140019bb9  retn
```
