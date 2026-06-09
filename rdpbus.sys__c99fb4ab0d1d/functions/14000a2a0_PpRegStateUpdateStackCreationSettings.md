# PpRegStateUpdateStackCreationSettings

- ea: `0x14000a2a0`
- end: `0x14000a414`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400091b0`

## callees

- `0x140002350`
- `0x140009db8`
- `0x14000a2a0`
- `0x14000a5c8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000a384`
- `ntoskrnl!ZwClose` at `0x14000a3f5`
- `ntoskrnl!ZwClose` at `0x14000a384`
- `ntoskrnl!ZwClose` at `0x14000a3f5`
- `ntoskrnl!ZwSetValueKey` at `0x14000a3e3`
- `ntoskrnl!ZwSetValueKey` at `0x14000a3e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a32e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a32e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000a398`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000a398`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000a30e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000a30e`

## string_xrefs

- `0x14000a3a8`: `Security`

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
    if ( !HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) = 2;
      }
      else
      {
        HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) != 1 )
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
0x14000a2a0  mov     [rsp-8+arg_0], rbx
0x14000a2a5  mov     [rsp-8+arg_8], rdi
0x14000a2aa  push    rbp
0x14000a2ab  mov     rbp, rsp
0x14000a2ae  sub     rsp, 60h
0x14000a2b2  lea     rax, [rbp+Handle]
0x14000a2b6  mov     [rbp+P], 0
0x14000a2be  xor     r9d, r9d
0x14000a2c1  mov     [rsp+60h+Data], rax
0x14000a2c6  xor     r8d, r8d
0x14000a2c9  mov     [rbp+KeyHandle], 0
0x14000a2d1  mov     rdi, rdx
0x14000a2d4  mov     [rbp+Handle], 0
0x14000a2dc  call    PiRegStateOpenClassKey
0x14000a2e1  test    eax, eax
0x14000a2e3  js      loc_14000A403
0x14000a2e9  cmp     dword ptr cs:WPP_MAIN_CB.Queue+0Ch, 0
0x14000a2f0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x14000a2f7  jnz     short loc_14000A346
0x14000a2f9  xor     edx, edx
0x14000a2fb  lea     rax, [rbp+P]
0x14000a2ff  mov     r9b, 1
0x14000a302  mov     [rsp+60h+Data], rax
0x14000a307  mov     rcx, rbx
0x14000a30a  lea     r8d, [rdx+1]
0x14000a30e  call    cs:__imp_SeCaptureSecurityDescriptor
0x14000a315  nop     dword ptr [rax+rax+00h]
0x14000a31a  test    eax, eax
0x14000a31c  js      short loc_14000A33C
0x14000a31e  mov     rcx, [rbp+P]; P
0x14000a322  xor     edx, edx; Tag
0x14000a324  mov     dword ptr cs:WPP_MAIN_CB.Queue+0Ch, 1
0x14000a32e  call    cs:__imp_ExFreePoolWithTag
0x14000a335  nop     dword ptr [rax+rax+00h]
0x14000a33a  jmp     short loc_14000A346
0x14000a33c  mov     dword ptr cs:WPP_MAIN_CB.Queue+0Ch, 2
0x14000a346  mov     rcx, [rbp+Handle]
0x14000a34a  lea     rdx, aProperties; "Properties"
0x14000a351  xor     eax, eax
0x14000a353  cmp     dword ptr cs:WPP_MAIN_CB.Queue+0Ch, 1
0x14000a35a  cmovnz  rbx, rax
0x14000a35e  lea     rax, [rbp+KeyHandle]
0x14000a362  mov     [rsp+60h+var_30], rax
0x14000a367  mov     qword ptr [rsp+60h+DataSize], 0
0x14000a370  mov     [rsp+60h+Data], rbx
0x14000a375  mov     [rbp+P], rbx
0x14000a379  call    CmRegUtilCreateWstrKey
0x14000a37e  mov     rcx, [rbp+Handle]; Handle
0x14000a382  mov     ebx, eax
0x14000a384  call    cs:__imp_ZwClose
0x14000a38b  nop     dword ptr [rax+rax+00h]
0x14000a390  test    ebx, ebx
0x14000a392  js      short loc_14000A401
0x14000a394  mov     rcx, [rdi+8]; SecurityDescriptor
0x14000a398  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000a39f  nop     dword ptr [rax+rax+00h]
0x14000a3a4  mov     r11, [rdi+8]
0x14000a3a8  lea     rdx, aSecurity; "Security"
0x14000a3af  xorps   xmm0, xmm0
0x14000a3b2  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a3b6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000a3ba  mov     r10d, eax
0x14000a3bd  call    WdmlibRtlInitUnicodeStringEx
0x14000a3c2  mov     ebx, eax
0x14000a3c4  test    eax, eax
0x14000a3c6  js      short loc_14000A3F1
0x14000a3c8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000a3cc  lea     rdx, [rbp+DestinationString]; ValueName
0x14000a3d0  mov     [rsp+60h+DataSize], r10d; DataSize
0x14000a3d5  mov     r9d, 3; Type
0x14000a3db  xor     r8d, r8d; TitleIndex
0x14000a3de  mov     [rsp+60h+Data], r11; Data
0x14000a3e3  call    cs:__imp_ZwSetValueKey
0x14000a3ea  nop     dword ptr [rax+rax+00h]
0x14000a3ef  mov     ebx, eax
0x14000a3f1  mov     rcx, [rbp+KeyHandle]; Handle
0x14000a3f5  call    cs:__imp_ZwClose
0x14000a3fc  nop     dword ptr [rax+rax+00h]
0x14000a401  mov     eax, ebx
0x14000a403  mov     rbx, [rsp+60h+arg_0]
0x14000a408  mov     rdi, [rsp+60h+arg_8]
0x14000a40d  add     rsp, 60h
0x14000a411  pop     rbp
0x14000a412  retn
```
