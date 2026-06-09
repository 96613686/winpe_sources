# PpRegStateUpdateStackCreationSettings

- ea: `0x140086130`
- end: `0x1400862a4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140085040`

## callees

- `0x1400216ec`
- `0x140085c48`
- `0x140086130`
- `0x140086458`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140086228`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140086228`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14008619e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14008619e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400861be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400861be`
- `ntoskrnl!ZwClose` at `0x140086214`
- `ntoskrnl!ZwClose` at `0x140086285`
- `ntoskrnl!ZwClose` at `0x140086214`
- `ntoskrnl!ZwClose` at `0x140086285`
- `ntoskrnl!ZwSetValueKey` at `0x140086273`
- `ntoskrnl!ZwSetValueKey` at `0x140086273`

## string_xrefs

- `0x140086238`: `Security`

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
0x140086130  mov     [rsp-8+arg_0], rbx
0x140086135  mov     [rsp-8+arg_8], rdi
0x14008613a  push    rbp
0x14008613b  mov     rbp, rsp
0x14008613e  sub     rsp, 60h
0x140086142  lea     rax, [rbp+Handle]
0x140086146  mov     [rbp+P], 0
0x14008614e  xor     r9d, r9d
0x140086151  mov     [rsp+60h+Data], rax
0x140086156  xor     r8d, r8d
0x140086159  mov     [rbp+KeyHandle], 0
0x140086161  mov     rdi, rdx
0x140086164  mov     [rbp+Handle], 0
0x14008616c  call    PiRegStateOpenClassKey
0x140086171  test    eax, eax
0x140086173  js      loc_140086293
0x140086179  cmp     cs:PiRegStateDiscriptor, 0
0x140086180  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140086187  jnz     short loc_1400861D6
0x140086189  xor     edx, edx
0x14008618b  lea     rax, [rbp+P]
0x14008618f  mov     r9b, 1
0x140086192  mov     [rsp+60h+Data], rax
0x140086197  mov     rcx, rbx
0x14008619a  lea     r8d, [rdx+1]
0x14008619e  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400861a5  nop     dword ptr [rax+rax+00h]
0x1400861aa  test    eax, eax
0x1400861ac  js      short loc_1400861CC
0x1400861ae  mov     rcx, [rbp+P]; P
0x1400861b2  xor     edx, edx; Tag
0x1400861b4  mov     cs:PiRegStateDiscriptor, 1
0x1400861be  call    cs:__imp_ExFreePoolWithTag
0x1400861c5  nop     dword ptr [rax+rax+00h]
0x1400861ca  jmp     short loc_1400861D6
0x1400861cc  mov     cs:PiRegStateDiscriptor, 2
0x1400861d6  mov     rcx, [rbp+Handle]
0x1400861da  lea     rdx, aProperties; "Properties"
0x1400861e1  xor     eax, eax
0x1400861e3  cmp     cs:PiRegStateDiscriptor, 1
0x1400861ea  cmovnz  rbx, rax
0x1400861ee  lea     rax, [rbp+KeyHandle]
0x1400861f2  mov     [rsp+60h+var_30], rax
0x1400861f7  mov     qword ptr [rsp+60h+DataSize], 0
0x140086200  mov     [rsp+60h+Data], rbx
0x140086205  mov     [rbp+P], rbx
0x140086209  call    CmRegUtilCreateWstrKey
0x14008620e  mov     rcx, [rbp+Handle]; Handle
0x140086212  mov     ebx, eax
0x140086214  call    cs:__imp_ZwClose
0x14008621b  nop     dword ptr [rax+rax+00h]
0x140086220  test    ebx, ebx
0x140086222  js      short loc_140086291
0x140086224  mov     rcx, [rdi+8]; SecurityDescriptor
0x140086228  call    cs:__imp_RtlLengthSecurityDescriptor
0x14008622f  nop     dword ptr [rax+rax+00h]
0x140086234  mov     r11, [rdi+8]
0x140086238  lea     rdx, aSecurity; "Security"
0x14008623f  xorps   xmm0, xmm0
0x140086242  lea     rcx, [rbp+DestinationString]; DestinationString
0x140086246  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14008624a  mov     r10d, eax
0x14008624d  call    WdmlibRtlInitUnicodeStringEx
0x140086252  mov     ebx, eax
0x140086254  test    eax, eax
0x140086256  js      short loc_140086281
0x140086258  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14008625c  lea     rdx, [rbp+DestinationString]; ValueName
0x140086260  mov     [rsp+60h+DataSize], r10d; DataSize
0x140086265  mov     r9d, 3; Type
0x14008626b  xor     r8d, r8d; TitleIndex
0x14008626e  mov     [rsp+60h+Data], r11; Data
0x140086273  call    cs:__imp_ZwSetValueKey
0x14008627a  nop     dword ptr [rax+rax+00h]
0x14008627f  mov     ebx, eax
0x140086281  mov     rcx, [rbp+KeyHandle]; Handle
0x140086285  call    cs:__imp_ZwClose
0x14008628c  nop     dword ptr [rax+rax+00h]
0x140086291  mov     eax, ebx
0x140086293  mov     rbx, [rsp+60h+arg_0]
0x140086298  mov     rdi, [rsp+60h+arg_8]
0x14008629d  add     rsp, 60h
0x1400862a1  pop     rbp
0x1400862a2  retn
```
