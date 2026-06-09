# PpRegStateUpdateStackCreationSettings

- ea: `0x1401580c0`
- end: `0x140158234`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140156fd0`

## callees

- `0x14007df10`
- `0x140157bd8`
- `0x1401580c0`
- `0x1401583e8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401581a4`
- `ntoskrnl!ZwClose` at `0x140158215`
- `ntoskrnl!ZwClose` at `0x1401581a4`
- `ntoskrnl!ZwClose` at `0x140158215`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401581b8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401581b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015814e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015814e`
- `ntoskrnl!ZwSetValueKey` at `0x140158203`
- `ntoskrnl!ZwSetValueKey` at `0x140158203`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14015812e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14015812e`

## string_xrefs

- `0x1401581c8`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r9d
  void *Data; // r10
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
0x1401580c0  mov     [rsp-8+arg_0], rbx
0x1401580c5  mov     [rsp-8+arg_8], rdi
0x1401580ca  push    rbp
0x1401580cb  mov     rbp, rsp
0x1401580ce  sub     rsp, 60h
0x1401580d2  lea     rax, [rbp+Handle]
0x1401580d6  mov     [rbp+P], 0
0x1401580de  xor     r9d, r9d
0x1401580e1  mov     [rsp+60h+Data], rax
0x1401580e6  xor     r8d, r8d
0x1401580e9  mov     [rbp+KeyHandle], 0
0x1401580f1  mov     rdi, rdx
0x1401580f4  mov     [rbp+Handle], 0
0x1401580fc  call    PiRegStateOpenClassKey
0x140158101  test    eax, eax
0x140158103  js      loc_140158223
0x140158109  cmp     cs:PiRegStateDiscriptor, 0
0x140158110  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140158117  jnz     short loc_140158166
0x140158119  xor     edx, edx
0x14015811b  lea     rax, [rbp+P]
0x14015811f  mov     r9b, 1
0x140158122  mov     [rsp+60h+Data], rax
0x140158127  mov     rcx, rbx
0x14015812a  lea     r8d, [rdx+1]
0x14015812e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140158135  nop     dword ptr [rax+rax+00h]
0x14015813a  test    eax, eax
0x14015813c  js      short loc_14015815C
0x14015813e  mov     rcx, [rbp+P]; P
0x140158142  xor     edx, edx; Tag
0x140158144  mov     cs:PiRegStateDiscriptor, 1
0x14015814e  call    cs:__imp_ExFreePoolWithTag
0x140158155  nop     dword ptr [rax+rax+00h]
0x14015815a  jmp     short loc_140158166
0x14015815c  mov     cs:PiRegStateDiscriptor, 2
0x140158166  mov     rcx, [rbp+Handle]
0x14015816a  lea     rdx, aProperties_0; "Properties"
0x140158171  xor     eax, eax
0x140158173  cmp     cs:PiRegStateDiscriptor, 1
0x14015817a  cmovnz  rbx, rax
0x14015817e  lea     rax, [rbp+KeyHandle]
0x140158182  mov     [rsp+60h+var_30], rax
0x140158187  mov     qword ptr [rsp+60h+DataSize], 0
0x140158190  mov     [rsp+60h+Data], rbx
0x140158195  mov     [rbp+P], rbx
0x140158199  call    CmRegUtilCreateWstrKey
0x14015819e  mov     rcx, [rbp+Handle]; Handle
0x1401581a2  mov     ebx, eax
0x1401581a4  call    cs:__imp_ZwClose
0x1401581ab  nop     dword ptr [rax+rax+00h]
0x1401581b0  test    ebx, ebx
0x1401581b2  js      short loc_140158221
0x1401581b4  mov     rcx, [rdi+8]; SecurityDescriptor
0x1401581b8  call    cs:__imp_RtlLengthSecurityDescriptor
0x1401581bf  nop     dword ptr [rax+rax+00h]
0x1401581c4  mov     r10, [rdi+8]
0x1401581c8  lea     rdx, aSecurity; "Security"
0x1401581cf  xorps   xmm0, xmm0
0x1401581d2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1401581d6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1401581da  mov     r9d, eax
0x1401581dd  call    WdmlibRtlInitUnicodeStringEx
0x1401581e2  mov     ebx, eax
0x1401581e4  test    eax, eax
0x1401581e6  js      short loc_140158211
0x1401581e8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1401581ec  lea     rdx, [rbp+DestinationString]; ValueName
0x1401581f0  mov     [rsp+60h+DataSize], r9d; DataSize
0x1401581f5  xor     r8d, r8d; TitleIndex
0x1401581f8  mov     r9d, 3; Type
0x1401581fe  mov     [rsp+60h+Data], r10; Data
0x140158203  call    cs:__imp_ZwSetValueKey
0x14015820a  nop     dword ptr [rax+rax+00h]
0x14015820f  mov     ebx, eax
0x140158211  mov     rcx, [rbp+KeyHandle]; Handle
0x140158215  call    cs:__imp_ZwClose
0x14015821c  nop     dword ptr [rax+rax+00h]
0x140158221  mov     eax, ebx
0x140158223  mov     rbx, [rsp+60h+arg_0]
0x140158228  mov     rdi, [rsp+60h+arg_8]
0x14015822d  add     rsp, 60h
0x140158231  pop     rbp
0x140158232  retn
```
