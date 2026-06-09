# AllocAndReadStringFromRegistry

- ea: `0x18007f36c`
- end: `0x18007f529`
- name: `AllocAndReadStringFromRegistry`
- size: `445`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007f530`

## callees

- `0x18002c040`
- `0x18007f36c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007f3bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007f3d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007f3bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007f3d2`
- `ntoskrnl!ExAllocatePool2` at `0x18007f438`
- `ntoskrnl!ExAllocatePool2` at `0x18007f4a9`
- `ntoskrnl!ExAllocatePool2` at `0x18007f438`
- `ntoskrnl!ExAllocatePool2` at `0x18007f4a9`
- `ntoskrnl!ZwQueryValueKey` at `0x18007f474`
- `ntoskrnl!ZwQueryValueKey` at `0x18007f474`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f506`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f506`
- `ntoskrnl!ZwClose` at `0x18007f4f0`
- `ntoskrnl!ZwClose` at `0x18007f4f0`
- `ntoskrnl!ZwOpenKey` at `0x18007f40d`
- `ntoskrnl!ZwOpenKey` at `0x18007f40d`

## string_xrefs

- `0x18007f3c7`: `DataPath`

## pseudocode

```c
__int64 __fastcall AllocAndReadStringFromRegistry(PCWSTR SourceString, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  _DWORD *Pool2; // rdi
  NTSTATUS v7; // ebx
  unsigned int v8; // esi
  _WORD *v9; // rax
  _WORD *v10; // r14
  unsigned int v11; // esi
  void *KeyHandle; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  ULONG ResultLength; // [rsp+E8h] [rbp+6Fh] BYREF
  int v18; // [rsp+ECh] [rbp+73h]

  v18 = HIDWORD(a2);
  KeyHandle = 0;
  ResultLength = 0;
  Pool2 = 0;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&ValueName, L"DataPath");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(256, 536, 1196575819);
    if ( !Pool2 )
    {
LABEL_3:
      v7 = -1073741801;
      goto LABEL_11;
    }
    v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, 0x218u, &ResultLength);
    if ( v7 >= 0 )
    {
      if ( Pool2[1] != 1 || (v8 = Pool2[2], (v8 & 1) != 0) || v8 - 1 > 0x270F )
      {
        v7 = -1073741772;
      }
      else
      {
        v9 = (_WORD *)ExAllocatePool2(256, v8, 1196575819);
        *a3 = v9;
        v10 = v9;
        if ( !v9 )
          goto LABEL_3;
        memmove(v9, Pool2 + 3, v8);
        v11 = v8 >> 1;
        *a4 = v11;
        v10[v11 - 1] = 0;
      }
    }
  }
LABEL_11:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007f36c  mov     qword ptr [rsp-8+arg_8], rdx
0x18007f371  push    rbp
0x18007f372  push    rbx
0x18007f373  push    rsi
0x18007f374  push    rdi
0x18007f375  push    r12
0x18007f377  push    r13
0x18007f379  push    r14
0x18007f37b  push    r15
0x18007f37d  lea     rbp, [rsp-1Fh]
0x18007f382  sub     rsp, 98h
0x18007f389  xorps   xmm0, xmm0
0x18007f38c  xor     eax, eax
0x18007f38e  xorps   xmm1, xmm1
0x18007f391  mov     [rbp+57h+KeyHandle], rax
0x18007f395  mov     rdx, rcx; SourceString
0x18007f398  mov     [rbp+57h+arg_8], eax
0x18007f39b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18007f39f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007f3a3  mov     r13, r9
0x18007f3a6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18007f3aa  mov     r12, r8
0x18007f3ad  xor     edi, edi
0x18007f3af  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007f3b3  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x18007f3b7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007f3bb  call    cs:__imp_RtlInitUnicodeString
0x18007f3c2  nop     dword ptr [rax+rax+00h]
0x18007f3c7  lea     rdx, aDatapath; "DataPath"
0x18007f3ce  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18007f3d2  call    cs:__imp_RtlInitUnicodeString
0x18007f3d9  nop     dword ptr [rax+rax+00h]
0x18007f3de  lea     rax, [rbp+57h+DestinationString]
0x18007f3e2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007f3e9  xorps   xmm0, xmm0
0x18007f3ec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007f3f0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007f3f4  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18007f3f8  mov     edx, 20019h; DesiredAccess
0x18007f3fd  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007f404  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007f408  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007f40d  call    cs:__imp_ZwOpenKey
0x18007f414  nop     dword ptr [rax+rax+00h]
0x18007f419  mov     ebx, eax
0x18007f41b  test    eax, eax
0x18007f41d  js      loc_18007F4E7
0x18007f423  mov     r14d, 47524C4Bh
0x18007f429  mov     ebx, 218h
0x18007f42e  mov     r8d, r14d
0x18007f431  mov     edx, ebx
0x18007f433  mov     ecx, 100h
0x18007f438  call    cs:__imp_ExAllocatePool2
0x18007f43f  nop     dword ptr [rax+rax+00h]
0x18007f444  mov     rdi, rax
0x18007f447  test    rax, rax
0x18007f44a  jnz     short loc_18007F456
0x18007f44c  mov     ebx, 0C0000017h
0x18007f451  jmp     loc_18007F4E7
0x18007f456  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007f45a  lea     rax, [rbp+57h+arg_8]
0x18007f45e  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x18007f463  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18007f467  mov     r9, rdi; KeyValueInformation
0x18007f46a  mov     [rsp+0D0h+Length], ebx; Length
0x18007f46e  mov     r8d, 2; KeyValueInformationClass
0x18007f474  call    cs:__imp_ZwQueryValueKey
0x18007f47b  nop     dword ptr [rax+rax+00h]
0x18007f480  mov     ebx, eax
0x18007f482  test    eax, eax
0x18007f484  js      short loc_18007F4E7
0x18007f486  cmp     dword ptr [rdi+4], 1
0x18007f48a  jnz     short loc_18007F4E2
0x18007f48c  mov     esi, [rdi+8]
0x18007f48f  test    sil, 1
0x18007f493  jnz     short loc_18007F4E2
0x18007f495  lea     eax, [rsi-1]
0x18007f498  cmp     eax, 270Fh
0x18007f49d  ja      short loc_18007F4E2
0x18007f49f  mov     r8d, r14d
0x18007f4a2  mov     edx, esi
0x18007f4a4  mov     ecx, 100h
0x18007f4a9  call    cs:__imp_ExAllocatePool2
0x18007f4b0  nop     dword ptr [rax+rax+00h]
0x18007f4b5  mov     [r12], rax
0x18007f4b9  mov     r14, rax
0x18007f4bc  test    rax, rax
0x18007f4bf  jz      short loc_18007F44C
0x18007f4c1  lea     rdx, [rdi+0Ch]; Src
0x18007f4c5  mov     r8d, esi; Size
0x18007f4c8  mov     rcx, rax; void *
0x18007f4cb  call    memmove
0x18007f4d0  shr     esi, 1
0x18007f4d2  xor     eax, eax
0x18007f4d4  mov     [r13+0], esi
0x18007f4d8  lea     ecx, [rsi-1]
0x18007f4db  mov     [r14+rcx*2], ax
0x18007f4e0  jmp     short loc_18007F4E7
0x18007f4e2  mov     ebx, 0C0000034h
0x18007f4e7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18007f4eb  test    rcx, rcx
0x18007f4ee  jz      short loc_18007F4FC
0x18007f4f0  call    cs:__imp_ZwClose
0x18007f4f7  nop     dword ptr [rax+rax+00h]
0x18007f4fc  test    rdi, rdi
0x18007f4ff  jz      short loc_18007F512
0x18007f501  xor     edx, edx; Tag
0x18007f503  mov     rcx, rdi; P
0x18007f506  call    cs:__imp_ExFreePoolWithTag
0x18007f50d  nop     dword ptr [rax+rax+00h]
0x18007f512  mov     eax, ebx
0x18007f514  add     rsp, 98h
0x18007f51b  pop     r15
0x18007f51d  pop     r14
0x18007f51f  pop     r13
0x18007f521  pop     r12
0x18007f523  pop     rdi
0x18007f524  pop     rsi
0x18007f525  pop     rbx
0x18007f526  pop     rbp
0x18007f527  retn
```
