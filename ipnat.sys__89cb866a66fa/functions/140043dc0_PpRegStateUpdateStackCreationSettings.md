# PpRegStateUpdateStackCreationSettings

- ea: `0x140043dc0`
- end: `0x140043f34`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140042cc0`

## callees

- `0x14002811c`
- `0x1400438d8`
- `0x140043dc0`
- `0x14004403c`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140043eb8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140043eb8`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140043e2e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140043e2e`
- `ntoskrnl!ZwSetValueKey` at `0x140043f03`
- `ntoskrnl!ZwSetValueKey` at `0x140043f03`
- `ntoskrnl!ZwClose` at `0x140043ea4`
- `ntoskrnl!ZwClose` at `0x140043f15`
- `ntoskrnl!ZwClose` at `0x140043ea4`
- `ntoskrnl!ZwClose` at `0x140043f15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043e4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043e4e`

## string_xrefs

- `0x140043ec8`: `Security`

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
0x140043dc0  mov     [rsp-8+arg_0], rbx
0x140043dc5  mov     [rsp-8+arg_8], rdi
0x140043dca  push    rbp
0x140043dcb  mov     rbp, rsp
0x140043dce  sub     rsp, 60h
0x140043dd2  lea     rax, [rbp+Handle]
0x140043dd6  mov     [rbp+P], 0
0x140043dde  xor     r9d, r9d
0x140043de1  mov     [rsp+60h+Data], rax
0x140043de6  xor     r8d, r8d
0x140043de9  mov     [rbp+KeyHandle], 0
0x140043df1  mov     rdi, rdx
0x140043df4  mov     [rbp+Handle], 0
0x140043dfc  call    PiRegStateOpenClassKey
0x140043e01  test    eax, eax
0x140043e03  js      loc_140043F23
0x140043e09  cmp     cs:PiRegStateDiscriptor, 0
0x140043e10  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140043e17  jnz     short loc_140043E66
0x140043e19  xor     edx, edx
0x140043e1b  lea     rax, [rbp+P]
0x140043e1f  mov     r9b, 1
0x140043e22  mov     [rsp+60h+Data], rax
0x140043e27  mov     rcx, rbx
0x140043e2a  lea     r8d, [rdx+1]
0x140043e2e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140043e35  nop     dword ptr [rax+rax+00h]
0x140043e3a  test    eax, eax
0x140043e3c  js      short loc_140043E5C
0x140043e3e  mov     rcx, [rbp+P]; P
0x140043e42  xor     edx, edx; Tag
0x140043e44  mov     cs:PiRegStateDiscriptor, 1
0x140043e4e  call    cs:__imp_ExFreePoolWithTag
0x140043e55  nop     dword ptr [rax+rax+00h]
0x140043e5a  jmp     short loc_140043E66
0x140043e5c  mov     cs:PiRegStateDiscriptor, 2
0x140043e66  mov     rcx, [rbp+Handle]
0x140043e6a  lea     rdx, aProperties; "Properties"
0x140043e71  xor     eax, eax
0x140043e73  cmp     cs:PiRegStateDiscriptor, 1
0x140043e7a  cmovnz  rbx, rax
0x140043e7e  lea     rax, [rbp+KeyHandle]
0x140043e82  mov     [rsp+60h+var_30], rax
0x140043e87  mov     qword ptr [rsp+60h+DataSize], 0
0x140043e90  mov     [rsp+60h+Data], rbx
0x140043e95  mov     [rbp+P], rbx
0x140043e99  call    CmRegUtilCreateWstrKey
0x140043e9e  mov     rcx, [rbp+Handle]; Handle
0x140043ea2  mov     ebx, eax
0x140043ea4  call    cs:__imp_ZwClose
0x140043eab  nop     dword ptr [rax+rax+00h]
0x140043eb0  test    ebx, ebx
0x140043eb2  js      short loc_140043F21
0x140043eb4  mov     rcx, [rdi+8]; SecurityDescriptor
0x140043eb8  call    cs:__imp_RtlLengthSecurityDescriptor
0x140043ebf  nop     dword ptr [rax+rax+00h]
0x140043ec4  mov     r11, [rdi+8]
0x140043ec8  lea     rdx, aSecurity; "Security"
0x140043ecf  xorps   xmm0, xmm0
0x140043ed2  lea     rcx, [rbp+DestinationString]; DestinationString
0x140043ed6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140043eda  mov     r10d, eax
0x140043edd  call    WdmlibRtlInitUnicodeStringEx
0x140043ee2  mov     ebx, eax
0x140043ee4  test    eax, eax
0x140043ee6  js      short loc_140043F11
0x140043ee8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140043eec  lea     rdx, [rbp+DestinationString]; ValueName
0x140043ef0  mov     [rsp+60h+DataSize], r10d; DataSize
0x140043ef5  mov     r9d, 3; Type
0x140043efb  xor     r8d, r8d; TitleIndex
0x140043efe  mov     [rsp+60h+Data], r11; Data
0x140043f03  call    cs:__imp_ZwSetValueKey
0x140043f0a  nop     dword ptr [rax+rax+00h]
0x140043f0f  mov     ebx, eax
0x140043f11  mov     rcx, [rbp+KeyHandle]; Handle
0x140043f15  call    cs:__imp_ZwClose
0x140043f1c  nop     dword ptr [rax+rax+00h]
0x140043f21  mov     eax, ebx
0x140043f23  mov     rbx, [rsp+60h+arg_0]
0x140043f28  mov     rdi, [rsp+60h+arg_8]
0x140043f2d  add     rsp, 60h
0x140043f31  pop     rbp
0x140043f32  retn
```
