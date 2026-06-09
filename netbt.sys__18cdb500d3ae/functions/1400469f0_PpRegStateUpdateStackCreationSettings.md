# PpRegStateUpdateStackCreationSettings

- ea: `0x1400469f0`
- end: `0x140046b64`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140045900`

## callees

- `0x140030d6c`
- `0x140046508`
- `0x1400469f0`
- `0x140046d18`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140046ad4`
- `ntoskrnl!ZwClose` at `0x140046b45`
- `ntoskrnl!ZwClose` at `0x140046ad4`
- `ntoskrnl!ZwClose` at `0x140046b45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a7e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140046ae8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140046ae8`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140046a5e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140046a5e`
- `ntoskrnl!ZwSetValueKey` at `0x140046b33`
- `ntoskrnl!ZwSetValueKey` at `0x140046b33`

## string_xrefs

- `0x140046af8`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x1400469f0  mov     [rsp-8+arg_0], rbx
0x1400469f5  mov     [rsp-8+arg_8], rdi
0x1400469fa  push    rbp
0x1400469fb  mov     rbp, rsp
0x1400469fe  sub     rsp, 60h
0x140046a02  lea     rax, [rbp+Handle]
0x140046a06  mov     [rbp+P], 0
0x140046a0e  xor     r9d, r9d
0x140046a11  mov     [rsp+60h+Data], rax
0x140046a16  xor     r8d, r8d
0x140046a19  mov     [rbp+KeyHandle], 0
0x140046a21  mov     rdi, rdx
0x140046a24  mov     [rbp+Handle], 0
0x140046a2c  call    PiRegStateOpenClassKey
0x140046a31  test    eax, eax
0x140046a33  js      loc_140046B53
0x140046a39  cmp     cs:PiRegStateDiscriptor, 0
0x140046a40  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140046a47  jnz     short loc_140046A96
0x140046a49  xor     edx, edx
0x140046a4b  lea     rax, [rbp+P]
0x140046a4f  mov     r9b, 1
0x140046a52  mov     [rsp+60h+Data], rax
0x140046a57  mov     rcx, rbx
0x140046a5a  lea     r8d, [rdx+1]
0x140046a5e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140046a65  nop     dword ptr [rax+rax+00h]
0x140046a6a  test    eax, eax
0x140046a6c  js      short loc_140046A8C
0x140046a6e  mov     rcx, [rbp+P]; P
0x140046a72  xor     edx, edx; Tag
0x140046a74  mov     cs:PiRegStateDiscriptor, 1
0x140046a7e  call    cs:__imp_ExFreePoolWithTag
0x140046a85  nop     dword ptr [rax+rax+00h]
0x140046a8a  jmp     short loc_140046A96
0x140046a8c  mov     cs:PiRegStateDiscriptor, 2
0x140046a96  mov     rcx, [rbp+Handle]
0x140046a9a  lea     rdx, aProperties; "Properties"
0x140046aa1  xor     eax, eax
0x140046aa3  cmp     cs:PiRegStateDiscriptor, 1
0x140046aaa  cmovnz  rbx, rax
0x140046aae  lea     rax, [rbp+KeyHandle]
0x140046ab2  mov     [rsp+60h+var_30], rax
0x140046ab7  mov     qword ptr [rsp+60h+DataSize], 0
0x140046ac0  mov     [rsp+60h+Data], rbx
0x140046ac5  mov     [rbp+P], rbx
0x140046ac9  call    CmRegUtilCreateWstrKey
0x140046ace  mov     rcx, [rbp+Handle]; Handle
0x140046ad2  mov     ebx, eax
0x140046ad4  call    cs:__imp_ZwClose
0x140046adb  nop     dword ptr [rax+rax+00h]
0x140046ae0  test    ebx, ebx
0x140046ae2  js      short loc_140046B51
0x140046ae4  mov     rcx, [rdi+8]; SecurityDescriptor
0x140046ae8  call    cs:__imp_RtlLengthSecurityDescriptor
0x140046aef  nop     dword ptr [rax+rax+00h]
0x140046af4  mov     r11, [rdi+8]
0x140046af8  lea     rdx, aSecurity; "Security"
0x140046aff  xorps   xmm0, xmm0
0x140046b02  lea     rcx, [rbp+DestinationString]; DestinationString
0x140046b06  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140046b0a  mov     r10d, eax
0x140046b0d  call    WdmlibRtlInitUnicodeStringEx
0x140046b12  mov     ebx, eax
0x140046b14  test    eax, eax
0x140046b16  js      short loc_140046B41
0x140046b18  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140046b1c  lea     rdx, [rbp+DestinationString]; ValueName
0x140046b20  mov     [rsp+60h+DataSize], r10d; DataSize
0x140046b25  mov     r9d, 3; Type
0x140046b2b  xor     r8d, r8d; TitleIndex
0x140046b2e  mov     [rsp+60h+Data], r11; Data
0x140046b33  call    cs:__imp_ZwSetValueKey
0x140046b3a  nop     dword ptr [rax+rax+00h]
0x140046b3f  mov     ebx, eax
0x140046b41  mov     rcx, [rbp+KeyHandle]; Handle
0x140046b45  call    cs:__imp_ZwClose
0x140046b4c  nop     dword ptr [rax+rax+00h]
0x140046b51  mov     eax, ebx
0x140046b53  mov     rbx, [rsp+60h+arg_0]
0x140046b58  mov     rdi, [rsp+60h+arg_8]
0x140046b5d  add     rsp, 60h
0x140046b61  pop     rbp
0x140046b62  retn
```
