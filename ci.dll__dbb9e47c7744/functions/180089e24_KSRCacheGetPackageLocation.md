# KSRCacheGetPackageLocation

- ea: `0x180089e24`
- end: `0x180089f78`
- name: `KSRCacheGetPackageLocation`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007ecd0`

## callees

- `0x18002c080`
- `0x180089e24`
- `0x18008a298`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180089ebd`
- `ntoskrnl!ExAllocatePool2` at `0x180089ebd`
- `ntoskrnl!ZwQueryValueKey` at `0x180089e8f`
- `ntoskrnl!ZwQueryValueKey` at `0x180089eed`
- `ntoskrnl!ZwQueryValueKey` at `0x180089e8f`
- `ntoskrnl!ZwQueryValueKey` at `0x180089eed`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089f55`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089f55`
- `ntoskrnl!ZwClose` at `0x180089f3c`
- `ntoskrnl!ZwClose` at `0x180089f3c`

## string_xrefs

- `0x180089e45`: `InstalledLocation`

## pseudocode

```c
__int64 __fastcall KSRCacheGetPackageLocation(struct _UNICODE_STRING *a1, void *a2, size_t *a3)
{
  _DWORD *Pool2; // rdi
  int PackageDataKey; // ebx
  NTSTATUS v7; // eax
  size_t v8; // r8
  HANDLE KeyHandle; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+38h] BYREF

  KeyHandle = 0;
  *(_QWORD *)&ValueName.Length = 2359330;
  Pool2 = 0;
  ValueName.Buffer = L"InstalledLocation";
  ResultLength = 0;
  PackageDataKey = KSRCachepGetPackageDataKey(a1, &KeyHandle);
  if ( PackageDataKey >= 0 )
  {
    v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    PackageDataKey = v7;
    if ( v7 == -2147483643 || v7 == -1073741789 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1129468779);
      PackageDataKey = ZwQueryValueKey(
                         KeyHandle,
                         &ValueName,
                         KeyValuePartialInformation,
                         Pool2,
                         ResultLength,
                         &ResultLength);
      if ( PackageDataKey >= 0 )
      {
        if ( Pool2[1] == 1 )
        {
          v8 = (unsigned int)Pool2[2];
          if ( *a3 >= v8 )
          {
            memmove(a2, Pool2 + 3, v8);
            *a3 = (unsigned int)Pool2[2];
          }
          else
          {
            *a3 = v8;
            PackageDataKey = -1073741789;
          }
        }
        else
        {
          PackageDataKey = -1073741788;
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x4352536Bu);
  return (unsigned int)PackageDataKey;
}

```

## disassembly

```asm
0x180089e24  mov     [rsp-18h+arg_0], rbx
0x180089e29  mov     [rsp-18h+arg_8], rdi
0x180089e2e  push    rbp
0x180089e2f  push    r14
0x180089e31  push    r15
0x180089e33  mov     rbp, rsp
0x180089e36  sub     rsp, 50h
0x180089e3a  mov     r15, rdx
0x180089e3d  mov     [rbp+KeyHandle], 0
0x180089e45  lea     rax, aInstalledlocat; "InstalledLocation"
0x180089e4c  mov     qword ptr [rbp+ValueName.Length], 240022h
0x180089e54  xor     edi, edi
0x180089e56  mov     [rbp+ValueName.Buffer], rax
0x180089e5a  lea     rdx, [rbp+KeyHandle]
0x180089e5e  mov     [rbp+arg_18], edi
0x180089e61  mov     r14, r8
0x180089e64  call    KSRCachepGetPackageDataKey
0x180089e69  mov     ebx, eax
0x180089e6b  test    eax, eax
0x180089e6d  js      loc_180089F31
0x180089e73  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180089e77  lea     rax, [rbp+arg_18]
0x180089e7b  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180089e80  lea     r8d, [rdi+2]; KeyValueInformationClass
0x180089e84  xor     r9d, r9d; KeyValueInformation
0x180089e87  mov     [rsp+50h+Length], edi; Length
0x180089e8b  lea     rdx, [rbp+ValueName]; ValueName
0x180089e8f  call    cs:__imp_ZwQueryValueKey
0x180089e96  nop     dword ptr [rax+rax+00h]
0x180089e9b  mov     ebx, eax
0x180089e9d  cmp     eax, 80000005h
0x180089ea2  jz      short loc_180089EAF
0x180089ea4  cmp     eax, 0C0000023h
0x180089ea9  jnz     loc_180089F31
0x180089eaf  mov     edx, [rbp+arg_18]
0x180089eb2  mov     ecx, 100h
0x180089eb7  mov     r8d, 4352536Bh
0x180089ebd  call    cs:__imp_ExAllocatePool2
0x180089ec4  nop     dword ptr [rax+rax+00h]
0x180089ec9  mov     ecx, [rbp+arg_18]
0x180089ecc  lea     rdx, [rbp+ValueName]; ValueName
0x180089ed0  mov     rdi, rax
0x180089ed3  mov     r8d, 2; KeyValueInformationClass
0x180089ed9  lea     rax, [rbp+arg_18]
0x180089edd  mov     r9, rdi; KeyValueInformation
0x180089ee0  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180089ee5  mov     [rsp+50h+Length], ecx; Length
0x180089ee9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180089eed  call    cs:__imp_ZwQueryValueKey
0x180089ef4  nop     dword ptr [rax+rax+00h]
0x180089ef9  mov     ebx, eax
0x180089efb  test    eax, eax
0x180089efd  js      short loc_180089F31
0x180089eff  cmp     dword ptr [rdi+4], 1
0x180089f03  jz      short loc_180089F0C
0x180089f05  mov     ebx, 0C0000024h
0x180089f0a  jmp     short loc_180089F31
0x180089f0c  mov     r8d, [rdi+8]; Size
0x180089f10  cmp     [r14], r8
0x180089f13  jnb     short loc_180089F1F
0x180089f15  mov     [r14], r8
0x180089f18  mov     ebx, 0C0000023h
0x180089f1d  jmp     short loc_180089F31
0x180089f1f  lea     rdx, [rdi+0Ch]; Src
0x180089f23  mov     rcx, r15; void *
0x180089f26  call    memmove
0x180089f2b  mov     eax, [rdi+8]
0x180089f2e  mov     [r14], rax
0x180089f31  cmp     [rbp+KeyHandle], 0
0x180089f36  jz      short loc_180089F48
0x180089f38  mov     rcx, [rbp+KeyHandle]; Handle
0x180089f3c  call    cs:__imp_ZwClose
0x180089f43  nop     dword ptr [rax+rax+00h]
0x180089f48  test    rdi, rdi
0x180089f4b  jz      short loc_180089F61
0x180089f4d  mov     edx, 4352536Bh; Tag
0x180089f52  mov     rcx, rdi; P
0x180089f55  call    cs:__imp_ExFreePoolWithTag
0x180089f5c  nop     dword ptr [rax+rax+00h]
0x180089f61  mov     rdi, [rsp+50h+arg_8]
0x180089f66  mov     eax, ebx
0x180089f68  mov     rbx, [rsp+50h+arg_0]
0x180089f6d  add     rsp, 50h
0x180089f71  pop     r15
0x180089f73  pop     r14
0x180089f75  pop     rbp
0x180089f76  retn
```
