# KSRCacheGetPackageLocation

- ea: `0x18008a840`
- end: `0x18008a994`
- name: `KSRCacheGetPackageLocation`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007f6e4`

## callees

- `0x18002c200`
- `0x18008a840`
- `0x18008acb4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18008a8d9`
- `ntoskrnl!ExAllocatePool2` at `0x18008a8d9`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a8ab`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a909`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a8ab`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a909`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008a971`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008a971`
- `ntoskrnl!ZwClose` at `0x18008a958`
- `ntoskrnl!ZwClose` at `0x18008a958`

## string_xrefs

- `0x18008a861`: `InstalledLocation`

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
0x18008a840  mov     [rsp-18h+arg_0], rbx
0x18008a845  mov     [rsp-18h+arg_8], rdi
0x18008a84a  push    rbp
0x18008a84b  push    r14
0x18008a84d  push    r15
0x18008a84f  mov     rbp, rsp
0x18008a852  sub     rsp, 50h
0x18008a856  mov     r15, rdx
0x18008a859  mov     [rbp+KeyHandle], 0
0x18008a861  lea     rax, aInstalledlocat; "InstalledLocation"
0x18008a868  mov     qword ptr [rbp+ValueName.Length], 240022h
0x18008a870  xor     edi, edi
0x18008a872  mov     [rbp+ValueName.Buffer], rax
0x18008a876  lea     rdx, [rbp+KeyHandle]
0x18008a87a  mov     [rbp+arg_18], edi
0x18008a87d  mov     r14, r8
0x18008a880  call    KSRCachepGetPackageDataKey
0x18008a885  mov     ebx, eax
0x18008a887  test    eax, eax
0x18008a889  js      loc_18008A94D
0x18008a88f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18008a893  lea     rax, [rbp+arg_18]
0x18008a897  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18008a89c  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18008a8a0  xor     r9d, r9d; KeyValueInformation
0x18008a8a3  mov     [rsp+50h+Length], edi; Length
0x18008a8a7  lea     rdx, [rbp+ValueName]; ValueName
0x18008a8ab  call    cs:__imp_ZwQueryValueKey
0x18008a8b2  nop     dword ptr [rax+rax+00h]
0x18008a8b7  mov     ebx, eax
0x18008a8b9  cmp     eax, 80000005h
0x18008a8be  jz      short loc_18008A8CB
0x18008a8c0  cmp     eax, 0C0000023h
0x18008a8c5  jnz     loc_18008A94D
0x18008a8cb  mov     edx, [rbp+arg_18]
0x18008a8ce  mov     ecx, 100h
0x18008a8d3  mov     r8d, 4352536Bh
0x18008a8d9  call    cs:__imp_ExAllocatePool2
0x18008a8e0  nop     dword ptr [rax+rax+00h]
0x18008a8e5  mov     ecx, [rbp+arg_18]
0x18008a8e8  lea     rdx, [rbp+ValueName]; ValueName
0x18008a8ec  mov     rdi, rax
0x18008a8ef  mov     r8d, 2; KeyValueInformationClass
0x18008a8f5  lea     rax, [rbp+arg_18]
0x18008a8f9  mov     r9, rdi; KeyValueInformation
0x18008a8fc  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18008a901  mov     [rsp+50h+Length], ecx; Length
0x18008a905  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18008a909  call    cs:__imp_ZwQueryValueKey
0x18008a910  nop     dword ptr [rax+rax+00h]
0x18008a915  mov     ebx, eax
0x18008a917  test    eax, eax
0x18008a919  js      short loc_18008A94D
0x18008a91b  cmp     dword ptr [rdi+4], 1
0x18008a91f  jz      short loc_18008A928
0x18008a921  mov     ebx, 0C0000024h
0x18008a926  jmp     short loc_18008A94D
0x18008a928  mov     r8d, [rdi+8]; Size
0x18008a92c  cmp     [r14], r8
0x18008a92f  jnb     short loc_18008A93B
0x18008a931  mov     [r14], r8
0x18008a934  mov     ebx, 0C0000023h
0x18008a939  jmp     short loc_18008A94D
0x18008a93b  lea     rdx, [rdi+0Ch]; Src
0x18008a93f  mov     rcx, r15; void *
0x18008a942  call    memmove
0x18008a947  mov     eax, [rdi+8]
0x18008a94a  mov     [r14], rax
0x18008a94d  cmp     [rbp+KeyHandle], 0
0x18008a952  jz      short loc_18008A964
0x18008a954  mov     rcx, [rbp+KeyHandle]; Handle
0x18008a958  call    cs:__imp_ZwClose
0x18008a95f  nop     dword ptr [rax+rax+00h]
0x18008a964  test    rdi, rdi
0x18008a967  jz      short loc_18008A97D
0x18008a969  mov     edx, 4352536Bh; Tag
0x18008a96e  mov     rcx, rdi; P
0x18008a971  call    cs:__imp_ExFreePoolWithTag
0x18008a978  nop     dword ptr [rax+rax+00h]
0x18008a97d  mov     rdi, [rsp+50h+arg_8]
0x18008a982  mov     eax, ebx
0x18008a984  mov     rbx, [rsp+50h+arg_0]
0x18008a989  add     rsp, 50h
0x18008a98d  pop     r15
0x18008a98f  pop     r14
0x18008a991  pop     rbp
0x18008a992  retn
```
