# PpRegStateUpdateStackCreationSettings

- ea: `0x14000e330`
- end: `0x14000e4a4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d240`

## callees

- `0x140006430`
- `0x14000de48`
- `0x14000e330`
- `0x14000e658`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e414`
- `ntoskrnl!ZwClose` at `0x14000e485`
- `ntoskrnl!ZwClose` at `0x14000e414`
- `ntoskrnl!ZwClose` at `0x14000e485`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e3be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e3be`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000e428`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000e428`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e39e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e39e`
- `ntoskrnl!ZwSetValueKey` at `0x14000e473`
- `ntoskrnl!ZwSetValueKey` at `0x14000e473`

## string_xrefs

- `0x14000e438`: `Security`

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
0x14000e330  mov     [rsp-8+arg_0], rbx
0x14000e335  mov     [rsp-8+arg_8], rdi
0x14000e33a  push    rbp
0x14000e33b  mov     rbp, rsp
0x14000e33e  sub     rsp, 60h
0x14000e342  lea     rax, [rbp+Handle]
0x14000e346  mov     [rbp+P], 0
0x14000e34e  xor     r9d, r9d
0x14000e351  mov     [rsp+60h+Data], rax
0x14000e356  xor     r8d, r8d
0x14000e359  mov     [rbp+KeyHandle], 0
0x14000e361  mov     rdi, rdx
0x14000e364  mov     [rbp+Handle], 0
0x14000e36c  call    PiRegStateOpenClassKey
0x14000e371  test    eax, eax
0x14000e373  js      loc_14000E493
0x14000e379  cmp     cs:PiRegStateDiscriptor, 0
0x14000e380  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x14000e387  jnz     short loc_14000E3D6
0x14000e389  xor     edx, edx
0x14000e38b  lea     rax, [rbp+P]
0x14000e38f  mov     r9b, 1
0x14000e392  mov     [rsp+60h+Data], rax
0x14000e397  mov     rcx, rbx
0x14000e39a  lea     r8d, [rdx+1]
0x14000e39e  call    cs:__imp_SeCaptureSecurityDescriptor
0x14000e3a5  nop     dword ptr [rax+rax+00h]
0x14000e3aa  test    eax, eax
0x14000e3ac  js      short loc_14000E3CC
0x14000e3ae  mov     rcx, [rbp+P]; P
0x14000e3b2  xor     edx, edx; Tag
0x14000e3b4  mov     cs:PiRegStateDiscriptor, 1
0x14000e3be  call    cs:__imp_ExFreePoolWithTag
0x14000e3c5  nop     dword ptr [rax+rax+00h]
0x14000e3ca  jmp     short loc_14000E3D6
0x14000e3cc  mov     cs:PiRegStateDiscriptor, 2
0x14000e3d6  mov     rcx, [rbp+Handle]
0x14000e3da  lea     rdx, aProperties; "Properties"
0x14000e3e1  xor     eax, eax
0x14000e3e3  cmp     cs:PiRegStateDiscriptor, 1
0x14000e3ea  cmovnz  rbx, rax
0x14000e3ee  lea     rax, [rbp+KeyHandle]
0x14000e3f2  mov     [rsp+60h+var_30], rax
0x14000e3f7  mov     qword ptr [rsp+60h+DataSize], 0
0x14000e400  mov     [rsp+60h+Data], rbx
0x14000e405  mov     [rbp+P], rbx
0x14000e409  call    CmRegUtilCreateWstrKey
0x14000e40e  mov     rcx, [rbp+Handle]; Handle
0x14000e412  mov     ebx, eax
0x14000e414  call    cs:__imp_ZwClose
0x14000e41b  nop     dword ptr [rax+rax+00h]
0x14000e420  test    ebx, ebx
0x14000e422  js      short loc_14000E491
0x14000e424  mov     rcx, [rdi+8]; SecurityDescriptor
0x14000e428  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000e42f  nop     dword ptr [rax+rax+00h]
0x14000e434  mov     r11, [rdi+8]
0x14000e438  lea     rdx, aSecurity; "Security"
0x14000e43f  xorps   xmm0, xmm0
0x14000e442  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e446  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e44a  mov     r10d, eax
0x14000e44d  call    WdmlibRtlInitUnicodeStringEx
0x14000e452  mov     ebx, eax
0x14000e454  test    eax, eax
0x14000e456  js      short loc_14000E481
0x14000e458  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e45c  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e460  mov     [rsp+60h+DataSize], r10d; DataSize
0x14000e465  mov     r9d, 3; Type
0x14000e46b  xor     r8d, r8d; TitleIndex
0x14000e46e  mov     [rsp+60h+Data], r11; Data
0x14000e473  call    cs:__imp_ZwSetValueKey
0x14000e47a  nop     dword ptr [rax+rax+00h]
0x14000e47f  mov     ebx, eax
0x14000e481  mov     rcx, [rbp+KeyHandle]; Handle
0x14000e485  call    cs:__imp_ZwClose
0x14000e48c  nop     dword ptr [rax+rax+00h]
0x14000e491  mov     eax, ebx
0x14000e493  mov     rbx, [rsp+60h+arg_0]
0x14000e498  mov     rdi, [rsp+60h+arg_8]
0x14000e49d  add     rsp, 60h
0x14000e4a1  pop     rbp
0x14000e4a2  retn
```
