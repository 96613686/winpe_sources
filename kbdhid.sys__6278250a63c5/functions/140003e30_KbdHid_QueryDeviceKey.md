# KbdHid_QueryDeviceKey

- ea: `0x140003e30`
- end: `0x140003f4e`
- name: `KbdHid_QueryDeviceKey`
- size: `286`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ff70`

## callees

- `0x140003e30`
- `0x140007240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f06`
- `ntoskrnl!ZwQueryValueKey` at `0x140003ecf`
- `ntoskrnl!ZwQueryValueKey` at `0x140003ecf`
- `ntoskrnl!ExAllocatePool2` at `0x140003e98`
- `ntoskrnl!ExAllocatePool2` at `0x140003e98`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003e5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003e5a`

## pseudocode

```c
__int64 __fastcall KbdHid_QueryDeviceKey(HANDLE KeyHandle, const WCHAR *a2, void *a3)
{
  unsigned int *Pool2; // rbx
  NTSTATUS v6; // edi
  unsigned int v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  ULONG Length; // [rsp+68h] [rbp+20h] BYREF

  Length = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( (unsigned int)DestinationString.MaximumLength + 28 < (unsigned int)DestinationString.MaximumLength + 24 )
    return 3221225621LL;
  Length = DestinationString.MaximumLength + 28;
  Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1214538315);
  if ( !Pool2 )
    return 3221225495LL;
  v6 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length);
  if ( v6 >= 0 )
  {
    v7 = Pool2[3];
    if ( v7 > 4 )
      v6 = -1073741789;
    else
      memmove(a3, (char *)Pool2 + Pool2[2], v7);
  }
  ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003e30  mov     [rsp+arg_8], rsi
0x140003e35  mov     [rsp+arg_18], r9d
0x140003e3a  push    rdi
0x140003e3b  sub     rsp, 40h
0x140003e3f  mov     rdi, rcx
0x140003e42  mov     [rsp+48h+arg_18], 0
0x140003e4a  xorps   xmm0, xmm0
0x140003e4d  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140003e52  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x140003e57  mov     rsi, r8
0x140003e5a  call    cs:__imp_RtlInitUnicodeString
0x140003e61  nop     dword ptr [rax+rax+00h]
0x140003e66  movzx   edx, [rsp+48h+DestinationString.MaximumLength]
0x140003e6b  add     edx, 18h
0x140003e6e  cmp     edx, 18h
0x140003e71  jb      loc_140003F3D
0x140003e77  lea     eax, [rdx+4]
0x140003e7a  cmp     eax, edx
0x140003e7c  jb      loc_140003F3D
0x140003e82  mov     edx, eax
0x140003e84  mov     ecx, 100h
0x140003e89  mov     r8d, 4864624Bh
0x140003e8f  mov     [rsp+48h+arg_0], rbx
0x140003e94  mov     [rsp+48h+arg_18], eax
0x140003e98  call    cs:__imp_ExAllocatePool2
0x140003e9f  nop     dword ptr [rax+rax+00h]
0x140003ea4  mov     rbx, rax
0x140003ea7  test    rax, rax
0x140003eaa  jz      short loc_140003F25
0x140003eac  mov     ecx, [rsp+48h+arg_18]
0x140003eb0  lea     rax, [rsp+48h+arg_18]
0x140003eb5  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140003eba  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x140003ebf  mov     [rsp+48h+Length], ecx; Length
0x140003ec3  mov     r9, rbx; KeyValueInformation
0x140003ec6  mov     rcx, rdi; KeyHandle
0x140003ec9  mov     r8d, 1; KeyValueInformationClass
0x140003ecf  call    cs:__imp_ZwQueryValueKey
0x140003ed6  nop     dword ptr [rax+rax+00h]
0x140003edb  mov     edi, eax
0x140003edd  test    eax, eax
0x140003edf  js      short loc_140003F01
0x140003ee1  mov     eax, [rbx+0Ch]
0x140003ee4  cmp     eax, 4
0x140003ee7  ja      short loc_140003EFC
0x140003ee9  mov     edx, [rbx+8]
0x140003eec  mov     r8d, eax; Size
0x140003eef  add     rdx, rbx; Src
0x140003ef2  mov     rcx, rsi; void *
0x140003ef5  call    memmove
0x140003efa  jmp     short loc_140003F01
0x140003efc  mov     edi, 0C0000023h
0x140003f01  xor     edx, edx; Tag
0x140003f03  mov     rcx, rbx; P
0x140003f06  call    cs:__imp_ExFreePoolWithTag
0x140003f0d  nop     dword ptr [rax+rax+00h]
0x140003f12  mov     rbx, [rsp+48h+arg_0]
0x140003f17  mov     eax, edi
0x140003f19  mov     rsi, [rsp+48h+arg_8]
0x140003f1e  add     rsp, 40h
0x140003f22  pop     rdi
0x140003f23  retn
0x140003f25  mov     rbx, [rsp+48h+arg_0]
0x140003f2a  mov     edi, 0C0000017h
0x140003f2f  mov     eax, edi
0x140003f31  mov     rsi, [rsp+48h+arg_8]
0x140003f36  add     rsp, 40h
0x140003f3a  pop     rdi
0x140003f3b  retn
0x140003f3d  mov     rsi, [rsp+48h+arg_8]
0x140003f42  mov     eax, 0C0000095h
0x140003f47  add     rsp, 40h
0x140003f4b  pop     rdi
0x140003f4c  retn
```
