# AllocAndReadStringFromRegistry

- ea: `0x180080998`
- end: `0x180080b55`
- name: `AllocAndReadStringFromRegistry`
- size: `445`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180080b5c`

## callees

- `0x18002c080`
- `0x180080998`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800809e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800809fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800809e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800809fe`
- `ntoskrnl!ExAllocatePool2` at `0x180080a64`
- `ntoskrnl!ExAllocatePool2` at `0x180080ad5`
- `ntoskrnl!ExAllocatePool2` at `0x180080a64`
- `ntoskrnl!ExAllocatePool2` at `0x180080ad5`
- `ntoskrnl!ZwQueryValueKey` at `0x180080aa0`
- `ntoskrnl!ZwQueryValueKey` at `0x180080aa0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080b32`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080b32`
- `ntoskrnl!ZwClose` at `0x180080b1c`
- `ntoskrnl!ZwClose` at `0x180080b1c`
- `ntoskrnl!ZwOpenKey` at `0x180080a39`
- `ntoskrnl!ZwOpenKey` at `0x180080a39`

## string_xrefs

- `0x1800809f3`: `DataPath`

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
0x180080998  mov     qword ptr [rsp-8+arg_8], rdx
0x18008099d  push    rbp
0x18008099e  push    rbx
0x18008099f  push    rsi
0x1800809a0  push    rdi
0x1800809a1  push    r12
0x1800809a3  push    r13
0x1800809a5  push    r14
0x1800809a7  push    r15
0x1800809a9  lea     rbp, [rsp-1Fh]
0x1800809ae  sub     rsp, 98h
0x1800809b5  xorps   xmm0, xmm0
0x1800809b8  xor     eax, eax
0x1800809ba  xorps   xmm1, xmm1
0x1800809bd  mov     [rbp+57h+KeyHandle], rax
0x1800809c1  mov     rdx, rcx; SourceString
0x1800809c4  mov     [rbp+57h+arg_8], eax
0x1800809c7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800809cb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800809cf  mov     r13, r9
0x1800809d2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800809d6  mov     r12, r8
0x1800809d9  xor     edi, edi
0x1800809db  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800809df  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1800809e3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800809e7  call    cs:__imp_RtlInitUnicodeString
0x1800809ee  nop     dword ptr [rax+rax+00h]
0x1800809f3  lea     rdx, aDatapath; "DataPath"
0x1800809fa  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800809fe  call    cs:__imp_RtlInitUnicodeString
0x180080a05  nop     dword ptr [rax+rax+00h]
0x180080a0a  lea     rax, [rbp+57h+DestinationString]
0x180080a0e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180080a15  xorps   xmm0, xmm0
0x180080a18  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180080a1c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180080a20  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180080a24  mov     edx, 20019h; DesiredAccess
0x180080a29  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180080a30  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180080a34  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180080a39  call    cs:__imp_ZwOpenKey
0x180080a40  nop     dword ptr [rax+rax+00h]
0x180080a45  mov     ebx, eax
0x180080a47  test    eax, eax
0x180080a49  js      loc_180080B13
0x180080a4f  mov     r14d, 47524C4Bh
0x180080a55  mov     ebx, 218h
0x180080a5a  mov     r8d, r14d
0x180080a5d  mov     edx, ebx
0x180080a5f  mov     ecx, 100h
0x180080a64  call    cs:__imp_ExAllocatePool2
0x180080a6b  nop     dword ptr [rax+rax+00h]
0x180080a70  mov     rdi, rax
0x180080a73  test    rax, rax
0x180080a76  jnz     short loc_180080A82
0x180080a78  mov     ebx, 0C0000017h
0x180080a7d  jmp     loc_180080B13
0x180080a82  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180080a86  lea     rax, [rbp+57h+arg_8]
0x180080a8a  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x180080a8f  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180080a93  mov     r9, rdi; KeyValueInformation
0x180080a96  mov     [rsp+0D0h+Length], ebx; Length
0x180080a9a  mov     r8d, 2; KeyValueInformationClass
0x180080aa0  call    cs:__imp_ZwQueryValueKey
0x180080aa7  nop     dword ptr [rax+rax+00h]
0x180080aac  mov     ebx, eax
0x180080aae  test    eax, eax
0x180080ab0  js      short loc_180080B13
0x180080ab2  cmp     dword ptr [rdi+4], 1
0x180080ab6  jnz     short loc_180080B0E
0x180080ab8  mov     esi, [rdi+8]
0x180080abb  test    sil, 1
0x180080abf  jnz     short loc_180080B0E
0x180080ac1  lea     eax, [rsi-1]
0x180080ac4  cmp     eax, 270Fh
0x180080ac9  ja      short loc_180080B0E
0x180080acb  mov     r8d, r14d
0x180080ace  mov     edx, esi
0x180080ad0  mov     ecx, 100h
0x180080ad5  call    cs:__imp_ExAllocatePool2
0x180080adc  nop     dword ptr [rax+rax+00h]
0x180080ae1  mov     [r12], rax
0x180080ae5  mov     r14, rax
0x180080ae8  test    rax, rax
0x180080aeb  jz      short loc_180080A78
0x180080aed  lea     rdx, [rdi+0Ch]; Src
0x180080af1  mov     r8d, esi; Size
0x180080af4  mov     rcx, rax; void *
0x180080af7  call    memmove
0x180080afc  shr     esi, 1
0x180080afe  xor     eax, eax
0x180080b00  mov     [r13+0], esi
0x180080b04  lea     ecx, [rsi-1]
0x180080b07  mov     [r14+rcx*2], ax
0x180080b0c  jmp     short loc_180080B13
0x180080b0e  mov     ebx, 0C0000034h
0x180080b13  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180080b17  test    rcx, rcx
0x180080b1a  jz      short loc_180080B28
0x180080b1c  call    cs:__imp_ZwClose
0x180080b23  nop     dword ptr [rax+rax+00h]
0x180080b28  test    rdi, rdi
0x180080b2b  jz      short loc_180080B3E
0x180080b2d  xor     edx, edx; Tag
0x180080b2f  mov     rcx, rdi; P
0x180080b32  call    cs:__imp_ExFreePoolWithTag
0x180080b39  nop     dword ptr [rax+rax+00h]
0x180080b3e  mov     eax, ebx
0x180080b40  add     rsp, 98h
0x180080b47  pop     r15
0x180080b49  pop     r14
0x180080b4b  pop     r13
0x180080b4d  pop     r12
0x180080b4f  pop     rdi
0x180080b50  pop     rsi
0x180080b51  pop     rbx
0x180080b52  pop     rbp
0x180080b53  retn
```
