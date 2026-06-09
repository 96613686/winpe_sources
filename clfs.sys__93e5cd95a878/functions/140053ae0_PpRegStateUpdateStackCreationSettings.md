# PpRegStateUpdateStackCreationSettings

- ea: `0x140053ae0`
- end: `0x140053c54`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400529f0`

## callees

- `0x140017cc4`
- `0x1400535f8`
- `0x140053ae0`
- `0x140053e08`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140053bd8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140053bd8`
- `ntoskrnl!ZwClose` at `0x140053bc4`
- `ntoskrnl!ZwClose` at `0x140053c35`
- `ntoskrnl!ZwClose` at `0x140053bc4`
- `ntoskrnl!ZwClose` at `0x140053c35`
- `ntoskrnl!ZwSetValueKey` at `0x140053c23`
- `ntoskrnl!ZwSetValueKey` at `0x140053c23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053b6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053b6e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140053b4e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140053b4e`

## string_xrefs

- `0x140053be8`: `Security`

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
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
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
0x140053ae0  mov     [rsp-8+arg_0], rbx
0x140053ae5  mov     [rsp-8+arg_8], rdi
0x140053aea  push    rbp
0x140053aeb  mov     rbp, rsp
0x140053aee  sub     rsp, 60h
0x140053af2  lea     rax, [rbp+Handle]
0x140053af6  mov     [rbp+P], 0
0x140053afe  xor     r9d, r9d
0x140053b01  mov     [rsp+60h+Data], rax
0x140053b06  xor     r8d, r8d
0x140053b09  mov     [rbp+KeyHandle], 0
0x140053b11  mov     rdi, rdx
0x140053b14  mov     [rbp+Handle], 0
0x140053b1c  call    PiRegStateOpenClassKey
0x140053b21  test    eax, eax
0x140053b23  js      loc_140053C43
0x140053b29  cmp     cs:PiRegStateDiscriptor, 0
0x140053b30  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140053b37  jnz     short loc_140053B86
0x140053b39  xor     edx, edx
0x140053b3b  lea     rax, [rbp+P]
0x140053b3f  mov     r9b, 1
0x140053b42  mov     [rsp+60h+Data], rax
0x140053b47  mov     rcx, rbx
0x140053b4a  lea     r8d, [rdx+1]
0x140053b4e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140053b55  nop     dword ptr [rax+rax+00h]
0x140053b5a  test    eax, eax
0x140053b5c  js      short loc_140053B7C
0x140053b5e  mov     rcx, [rbp+P]; P
0x140053b62  xor     edx, edx; Tag
0x140053b64  mov     cs:PiRegStateDiscriptor, 1
0x140053b6e  call    cs:__imp_ExFreePoolWithTag
0x140053b75  nop     dword ptr [rax+rax+00h]
0x140053b7a  jmp     short loc_140053B86
0x140053b7c  mov     cs:PiRegStateDiscriptor, 2
0x140053b86  mov     rcx, [rbp+Handle]
0x140053b8a  lea     rdx, aProperties; "Properties"
0x140053b91  xor     eax, eax
0x140053b93  cmp     cs:PiRegStateDiscriptor, 1
0x140053b9a  cmovnz  rbx, rax
0x140053b9e  lea     rax, [rbp+KeyHandle]
0x140053ba2  mov     [rsp+60h+var_30], rax
0x140053ba7  mov     qword ptr [rsp+60h+DataSize], 0
0x140053bb0  mov     [rsp+60h+Data], rbx
0x140053bb5  mov     [rbp+P], rbx
0x140053bb9  call    CmRegUtilCreateWstrKey
0x140053bbe  mov     rcx, [rbp+Handle]; Handle
0x140053bc2  mov     ebx, eax
0x140053bc4  call    cs:__imp_ZwClose
0x140053bcb  nop     dword ptr [rax+rax+00h]
0x140053bd0  test    ebx, ebx
0x140053bd2  js      short loc_140053C41
0x140053bd4  mov     rcx, [rdi+8]; SecurityDescriptor
0x140053bd8  call    cs:__imp_RtlLengthSecurityDescriptor
0x140053bdf  nop     dword ptr [rax+rax+00h]
0x140053be4  mov     r11, [rdi+8]
0x140053be8  lea     rdx, aSecurity; "Security"
0x140053bef  xorps   xmm0, xmm0
0x140053bf2  lea     rcx, [rbp+DestinationString]; DestinationString
0x140053bf6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140053bfa  mov     r10d, eax
0x140053bfd  call    WdmlibRtlInitUnicodeStringEx
0x140053c02  mov     ebx, eax
0x140053c04  test    eax, eax
0x140053c06  js      short loc_140053C31
0x140053c08  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140053c0c  lea     rdx, [rbp+DestinationString]; ValueName
0x140053c10  mov     [rsp+60h+DataSize], r10d; DataSize
0x140053c15  mov     r9d, 3; Type
0x140053c1b  xor     r8d, r8d; TitleIndex
0x140053c1e  mov     [rsp+60h+Data], r11; Data
0x140053c23  call    cs:__imp_ZwSetValueKey
0x140053c2a  nop     dword ptr [rax+rax+00h]
0x140053c2f  mov     ebx, eax
0x140053c31  mov     rcx, [rbp+KeyHandle]; Handle
0x140053c35  call    cs:__imp_ZwClose
0x140053c3c  nop     dword ptr [rax+rax+00h]
0x140053c41  mov     eax, ebx
0x140053c43  mov     rbx, [rsp+60h+arg_0]
0x140053c48  mov     rdi, [rsp+60h+arg_8]
0x140053c4d  add     rsp, 60h
0x140053c51  pop     rbp
0x140053c52  retn
```
