# PpRegStateUpdateStackCreationSettings

- ea: `0x140012080`
- end: `0x1400121f4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140010f90`

## callees

- `0x1400037b8`
- `0x140011b98`
- `0x140012080`
- `0x1400123a8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140012164`
- `ntoskrnl!ZwClose` at `0x1400121d5`
- `ntoskrnl!ZwClose` at `0x140012164`
- `ntoskrnl!ZwClose` at `0x1400121d5`
- `ntoskrnl!ZwSetValueKey` at `0x1400121c3`
- `ntoskrnl!ZwSetValueKey` at `0x1400121c3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140012178`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140012178`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400120ee`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400120ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001210e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001210e`

## string_xrefs

- `0x140012188`: `Security`

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
0x140012080  mov     [rsp-8+arg_0], rbx
0x140012085  mov     [rsp-8+arg_8], rdi
0x14001208a  push    rbp
0x14001208b  mov     rbp, rsp
0x14001208e  sub     rsp, 60h
0x140012092  lea     rax, [rbp+Handle]
0x140012096  mov     [rbp+P], 0
0x14001209e  xor     r9d, r9d
0x1400120a1  mov     [rsp+60h+Data], rax
0x1400120a6  xor     r8d, r8d
0x1400120a9  mov     [rbp+KeyHandle], 0
0x1400120b1  mov     rdi, rdx
0x1400120b4  mov     [rbp+Handle], 0
0x1400120bc  call    PiRegStateOpenClassKey
0x1400120c1  test    eax, eax
0x1400120c3  js      loc_1400121E3
0x1400120c9  cmp     cs:PiRegStateDiscriptor, 0
0x1400120d0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400120d7  jnz     short loc_140012126
0x1400120d9  xor     edx, edx
0x1400120db  lea     rax, [rbp+P]
0x1400120df  mov     r9b, 1
0x1400120e2  mov     [rsp+60h+Data], rax
0x1400120e7  mov     rcx, rbx
0x1400120ea  lea     r8d, [rdx+1]
0x1400120ee  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400120f5  nop     dword ptr [rax+rax+00h]
0x1400120fa  test    eax, eax
0x1400120fc  js      short loc_14001211C
0x1400120fe  mov     rcx, [rbp+P]; P
0x140012102  xor     edx, edx; Tag
0x140012104  mov     cs:PiRegStateDiscriptor, 1
0x14001210e  call    cs:__imp_ExFreePoolWithTag
0x140012115  nop     dword ptr [rax+rax+00h]
0x14001211a  jmp     short loc_140012126
0x14001211c  mov     cs:PiRegStateDiscriptor, 2
0x140012126  mov     rcx, [rbp+Handle]
0x14001212a  lea     rdx, aProperties; "Properties"
0x140012131  xor     eax, eax
0x140012133  cmp     cs:PiRegStateDiscriptor, 1
0x14001213a  cmovnz  rbx, rax
0x14001213e  lea     rax, [rbp+KeyHandle]
0x140012142  mov     [rsp+60h+var_30], rax
0x140012147  mov     qword ptr [rsp+60h+DataSize], 0
0x140012150  mov     [rsp+60h+Data], rbx
0x140012155  mov     [rbp+P], rbx
0x140012159  call    CmRegUtilCreateWstrKey
0x14001215e  mov     rcx, [rbp+Handle]; Handle
0x140012162  mov     ebx, eax
0x140012164  call    cs:__imp_ZwClose
0x14001216b  nop     dword ptr [rax+rax+00h]
0x140012170  test    ebx, ebx
0x140012172  js      short loc_1400121E1
0x140012174  mov     rcx, [rdi+8]; SecurityDescriptor
0x140012178  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001217f  nop     dword ptr [rax+rax+00h]
0x140012184  mov     r11, [rdi+8]
0x140012188  lea     rdx, aSecurity; "Security"
0x14001218f  xorps   xmm0, xmm0
0x140012192  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012196  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001219a  mov     r10d, eax
0x14001219d  call    WdmlibRtlInitUnicodeStringEx
0x1400121a2  mov     ebx, eax
0x1400121a4  test    eax, eax
0x1400121a6  js      short loc_1400121D1
0x1400121a8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400121ac  lea     rdx, [rbp+DestinationString]; ValueName
0x1400121b0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400121b5  mov     r9d, 3; Type
0x1400121bb  xor     r8d, r8d; TitleIndex
0x1400121be  mov     [rsp+60h+Data], r11; Data
0x1400121c3  call    cs:__imp_ZwSetValueKey
0x1400121ca  nop     dword ptr [rax+rax+00h]
0x1400121cf  mov     ebx, eax
0x1400121d1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400121d5  call    cs:__imp_ZwClose
0x1400121dc  nop     dword ptr [rax+rax+00h]
0x1400121e1  mov     eax, ebx
0x1400121e3  mov     rbx, [rsp+60h+arg_0]
0x1400121e8  mov     rdi, [rsp+60h+arg_8]
0x1400121ed  add     rsp, 60h
0x1400121f1  pop     rbp
0x1400121f2  retn
```
