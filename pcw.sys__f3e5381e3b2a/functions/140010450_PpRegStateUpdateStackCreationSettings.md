# PpRegStateUpdateStackCreationSettings

- ea: `0x140010450`
- end: `0x1400105c4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f350`

## callees

- `0x140001208`
- `0x14000ff68`
- `0x140010450`
- `0x1400105cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400104de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104de`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400104be`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400104be`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140010548`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140010548`
- `ntoskrnl!ZwClose` at `0x140010534`
- `ntoskrnl!ZwClose` at `0x1400105a5`
- `ntoskrnl!ZwClose` at `0x140010534`
- `ntoskrnl!ZwClose` at `0x1400105a5`
- `ntoskrnl!ZwSetValueKey` at `0x140010593`
- `ntoskrnl!ZwSetValueKey` at `0x140010593`

## string_xrefs

- `0x140010558`: `Security`

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
0x140010450  mov     [rsp-8+arg_0], rbx
0x140010455  mov     [rsp-8+arg_8], rdi
0x14001045a  push    rbp
0x14001045b  mov     rbp, rsp
0x14001045e  sub     rsp, 60h
0x140010462  lea     rax, [rbp+Handle]
0x140010466  mov     [rbp+P], 0
0x14001046e  xor     r9d, r9d
0x140010471  mov     [rsp+60h+Data], rax
0x140010476  xor     r8d, r8d
0x140010479  mov     [rbp+KeyHandle], 0
0x140010481  mov     rdi, rdx
0x140010484  mov     [rbp+Handle], 0
0x14001048c  call    PiRegStateOpenClassKey
0x140010491  test    eax, eax
0x140010493  js      loc_1400105B3
0x140010499  cmp     cs:PiRegStateDiscriptor, 0
0x1400104a0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400104a7  jnz     short loc_1400104F6
0x1400104a9  xor     edx, edx
0x1400104ab  lea     rax, [rbp+P]
0x1400104af  mov     r9b, 1
0x1400104b2  mov     [rsp+60h+Data], rax
0x1400104b7  mov     rcx, rbx
0x1400104ba  lea     r8d, [rdx+1]
0x1400104be  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400104c5  nop     dword ptr [rax+rax+00h]
0x1400104ca  test    eax, eax
0x1400104cc  js      short loc_1400104EC
0x1400104ce  mov     rcx, [rbp+P]; P
0x1400104d2  xor     edx, edx; Tag
0x1400104d4  mov     cs:PiRegStateDiscriptor, 1
0x1400104de  call    cs:__imp_ExFreePoolWithTag
0x1400104e5  nop     dword ptr [rax+rax+00h]
0x1400104ea  jmp     short loc_1400104F6
0x1400104ec  mov     cs:PiRegStateDiscriptor, 2
0x1400104f6  mov     rcx, [rbp+Handle]
0x1400104fa  lea     rdx, aProperties; "Properties"
0x140010501  xor     eax, eax
0x140010503  cmp     cs:PiRegStateDiscriptor, 1
0x14001050a  cmovnz  rbx, rax
0x14001050e  lea     rax, [rbp+KeyHandle]
0x140010512  mov     [rsp+60h+var_30], rax
0x140010517  mov     qword ptr [rsp+60h+DataSize], 0
0x140010520  mov     [rsp+60h+Data], rbx
0x140010525  mov     [rbp+P], rbx
0x140010529  call    CmRegUtilCreateWstrKey
0x14001052e  mov     rcx, [rbp+Handle]; Handle
0x140010532  mov     ebx, eax
0x140010534  call    cs:__imp_ZwClose
0x14001053b  nop     dword ptr [rax+rax+00h]
0x140010540  test    ebx, ebx
0x140010542  js      short loc_1400105B1
0x140010544  mov     rcx, [rdi+8]; SecurityDescriptor
0x140010548  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001054f  nop     dword ptr [rax+rax+00h]
0x140010554  mov     r11, [rdi+8]
0x140010558  lea     rdx, aSecurity; "Security"
0x14001055f  xorps   xmm0, xmm0
0x140010562  lea     rcx, [rbp+DestinationString]; DestinationString
0x140010566  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001056a  mov     r10d, eax
0x14001056d  call    WdmlibRtlInitUnicodeStringEx
0x140010572  mov     ebx, eax
0x140010574  test    eax, eax
0x140010576  js      short loc_1400105A1
0x140010578  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001057c  lea     rdx, [rbp+DestinationString]; ValueName
0x140010580  mov     [rsp+60h+DataSize], r10d; DataSize
0x140010585  mov     r9d, 3; Type
0x14001058b  xor     r8d, r8d; TitleIndex
0x14001058e  mov     [rsp+60h+Data], r11; Data
0x140010593  call    cs:__imp_ZwSetValueKey
0x14001059a  nop     dword ptr [rax+rax+00h]
0x14001059f  mov     ebx, eax
0x1400105a1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400105a5  call    cs:__imp_ZwClose
0x1400105ac  nop     dword ptr [rax+rax+00h]
0x1400105b1  mov     eax, ebx
0x1400105b3  mov     rbx, [rsp+60h+arg_0]
0x1400105b8  mov     rdi, [rsp+60h+arg_8]
0x1400105bd  add     rsp, 60h
0x1400105c1  pop     rbp
0x1400105c2  retn
```
