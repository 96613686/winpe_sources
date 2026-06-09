# KSRCacheGetPackageLocation

- ea: `0x1800887f4`
- end: `0x180088948`
- name: `KSRCacheGetPackageLocation`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007d6a4`

## callees

- `0x18002c040`
- `0x1800887f4`
- `0x180088c68`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18008888d`
- `ntoskrnl!ExAllocatePool2` at `0x18008888d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008885f`
- `ntoskrnl!ZwQueryValueKey` at `0x1800888bd`
- `ntoskrnl!ZwQueryValueKey` at `0x18008885f`
- `ntoskrnl!ZwQueryValueKey` at `0x1800888bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180088925`
- `ntoskrnl!ExFreePoolWithTag` at `0x180088925`
- `ntoskrnl!ZwClose` at `0x18008890c`
- `ntoskrnl!ZwClose` at `0x18008890c`

## string_xrefs

- `0x180088815`: `InstalledLocation`

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
0x1800887f4  mov     [rsp-18h+arg_0], rbx
0x1800887f9  mov     [rsp-18h+arg_8], rdi
0x1800887fe  push    rbp
0x1800887ff  push    r14
0x180088801  push    r15
0x180088803  mov     rbp, rsp
0x180088806  sub     rsp, 50h
0x18008880a  mov     r15, rdx
0x18008880d  mov     [rbp+KeyHandle], 0
0x180088815  lea     rax, aInstalledlocat; "InstalledLocation"
0x18008881c  mov     qword ptr [rbp+ValueName.Length], 240022h
0x180088824  xor     edi, edi
0x180088826  mov     [rbp+ValueName.Buffer], rax
0x18008882a  lea     rdx, [rbp+KeyHandle]
0x18008882e  mov     [rbp+arg_18], edi
0x180088831  mov     r14, r8
0x180088834  call    KSRCachepGetPackageDataKey
0x180088839  mov     ebx, eax
0x18008883b  test    eax, eax
0x18008883d  js      loc_180088901
0x180088843  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180088847  lea     rax, [rbp+arg_18]
0x18008884b  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180088850  lea     r8d, [rdi+2]; KeyValueInformationClass
0x180088854  xor     r9d, r9d; KeyValueInformation
0x180088857  mov     [rsp+50h+Length], edi; Length
0x18008885b  lea     rdx, [rbp+ValueName]; ValueName
0x18008885f  call    cs:__imp_ZwQueryValueKey
0x180088866  nop     dword ptr [rax+rax+00h]
0x18008886b  mov     ebx, eax
0x18008886d  cmp     eax, 80000005h
0x180088872  jz      short loc_18008887F
0x180088874  cmp     eax, 0C0000023h
0x180088879  jnz     loc_180088901
0x18008887f  mov     edx, [rbp+arg_18]
0x180088882  mov     ecx, 100h
0x180088887  mov     r8d, 4352536Bh
0x18008888d  call    cs:__imp_ExAllocatePool2
0x180088894  nop     dword ptr [rax+rax+00h]
0x180088899  mov     ecx, [rbp+arg_18]
0x18008889c  lea     rdx, [rbp+ValueName]; ValueName
0x1800888a0  mov     rdi, rax
0x1800888a3  mov     r8d, 2; KeyValueInformationClass
0x1800888a9  lea     rax, [rbp+arg_18]
0x1800888ad  mov     r9, rdi; KeyValueInformation
0x1800888b0  mov     [rsp+50h+ResultLength], rax; ResultLength
0x1800888b5  mov     [rsp+50h+Length], ecx; Length
0x1800888b9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800888bd  call    cs:__imp_ZwQueryValueKey
0x1800888c4  nop     dword ptr [rax+rax+00h]
0x1800888c9  mov     ebx, eax
0x1800888cb  test    eax, eax
0x1800888cd  js      short loc_180088901
0x1800888cf  cmp     dword ptr [rdi+4], 1
0x1800888d3  jz      short loc_1800888DC
0x1800888d5  mov     ebx, 0C0000024h
0x1800888da  jmp     short loc_180088901
0x1800888dc  mov     r8d, [rdi+8]; Size
0x1800888e0  cmp     [r14], r8
0x1800888e3  jnb     short loc_1800888EF
0x1800888e5  mov     [r14], r8
0x1800888e8  mov     ebx, 0C0000023h
0x1800888ed  jmp     short loc_180088901
0x1800888ef  lea     rdx, [rdi+0Ch]; Src
0x1800888f3  mov     rcx, r15; void *
0x1800888f6  call    memmove
0x1800888fb  mov     eax, [rdi+8]
0x1800888fe  mov     [r14], rax
0x180088901  cmp     [rbp+KeyHandle], 0
0x180088906  jz      short loc_180088918
0x180088908  mov     rcx, [rbp+KeyHandle]; Handle
0x18008890c  call    cs:__imp_ZwClose
0x180088913  nop     dword ptr [rax+rax+00h]
0x180088918  test    rdi, rdi
0x18008891b  jz      short loc_180088931
0x18008891d  mov     edx, 4352536Bh; Tag
0x180088922  mov     rcx, rdi; P
0x180088925  call    cs:__imp_ExFreePoolWithTag
0x18008892c  nop     dword ptr [rax+rax+00h]
0x180088931  mov     rdi, [rsp+50h+arg_8]
0x180088936  mov     eax, ebx
0x180088938  mov     rbx, [rsp+50h+arg_0]
0x18008893d  add     rsp, 50h
0x180088941  pop     r15
0x180088943  pop     r14
0x180088945  pop     rbp
0x180088946  retn
```
