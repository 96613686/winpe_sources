# AllocAndReadStringFromRegistry

- ea: `0x1800813ac`
- end: `0x180081569`
- name: `AllocAndReadStringFromRegistry`
- size: `445`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180081570`

## callees

- `0x18002c200`
- `0x1800813ac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800813fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180081412`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800813fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180081412`
- `ntoskrnl!ExAllocatePool2` at `0x180081478`
- `ntoskrnl!ExAllocatePool2` at `0x1800814e9`
- `ntoskrnl!ExAllocatePool2` at `0x180081478`
- `ntoskrnl!ExAllocatePool2` at `0x1800814e9`
- `ntoskrnl!ZwQueryValueKey` at `0x1800814b4`
- `ntoskrnl!ZwQueryValueKey` at `0x1800814b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180081546`
- `ntoskrnl!ExFreePoolWithTag` at `0x180081546`
- `ntoskrnl!ZwClose` at `0x180081530`
- `ntoskrnl!ZwClose` at `0x180081530`
- `ntoskrnl!ZwOpenKey` at `0x18008144d`
- `ntoskrnl!ZwOpenKey` at `0x18008144d`

## string_xrefs

- `0x180081407`: `DataPath`

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
0x1800813ac  mov     qword ptr [rsp-8+arg_8], rdx
0x1800813b1  push    rbp
0x1800813b2  push    rbx
0x1800813b3  push    rsi
0x1800813b4  push    rdi
0x1800813b5  push    r12
0x1800813b7  push    r13
0x1800813b9  push    r14
0x1800813bb  push    r15
0x1800813bd  lea     rbp, [rsp-1Fh]
0x1800813c2  sub     rsp, 98h
0x1800813c9  xorps   xmm0, xmm0
0x1800813cc  xor     eax, eax
0x1800813ce  xorps   xmm1, xmm1
0x1800813d1  mov     [rbp+57h+KeyHandle], rax
0x1800813d5  mov     rdx, rcx; SourceString
0x1800813d8  mov     [rbp+57h+arg_8], eax
0x1800813db  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800813df  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800813e3  mov     r13, r9
0x1800813e6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800813ea  mov     r12, r8
0x1800813ed  xor     edi, edi
0x1800813ef  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800813f3  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1800813f7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800813fb  call    cs:__imp_RtlInitUnicodeString
0x180081402  nop     dword ptr [rax+rax+00h]
0x180081407  lea     rdx, aDatapath; "DataPath"
0x18008140e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180081412  call    cs:__imp_RtlInitUnicodeString
0x180081419  nop     dword ptr [rax+rax+00h]
0x18008141e  lea     rax, [rbp+57h+DestinationString]
0x180081422  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180081429  xorps   xmm0, xmm0
0x18008142c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180081430  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180081434  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180081438  mov     edx, 20019h; DesiredAccess
0x18008143d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180081444  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180081448  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008144d  call    cs:__imp_ZwOpenKey
0x180081454  nop     dword ptr [rax+rax+00h]
0x180081459  mov     ebx, eax
0x18008145b  test    eax, eax
0x18008145d  js      loc_180081527
0x180081463  mov     r14d, 47524C4Bh
0x180081469  mov     ebx, 218h
0x18008146e  mov     r8d, r14d
0x180081471  mov     edx, ebx
0x180081473  mov     ecx, 100h
0x180081478  call    cs:__imp_ExAllocatePool2
0x18008147f  nop     dword ptr [rax+rax+00h]
0x180081484  mov     rdi, rax
0x180081487  test    rax, rax
0x18008148a  jnz     short loc_180081496
0x18008148c  mov     ebx, 0C0000017h
0x180081491  jmp     loc_180081527
0x180081496  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008149a  lea     rax, [rbp+57h+arg_8]
0x18008149e  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800814a3  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800814a7  mov     r9, rdi; KeyValueInformation
0x1800814aa  mov     [rsp+0D0h+Length], ebx; Length
0x1800814ae  mov     r8d, 2; KeyValueInformationClass
0x1800814b4  call    cs:__imp_ZwQueryValueKey
0x1800814bb  nop     dword ptr [rax+rax+00h]
0x1800814c0  mov     ebx, eax
0x1800814c2  test    eax, eax
0x1800814c4  js      short loc_180081527
0x1800814c6  cmp     dword ptr [rdi+4], 1
0x1800814ca  jnz     short loc_180081522
0x1800814cc  mov     esi, [rdi+8]
0x1800814cf  test    sil, 1
0x1800814d3  jnz     short loc_180081522
0x1800814d5  lea     eax, [rsi-1]
0x1800814d8  cmp     eax, 270Fh
0x1800814dd  ja      short loc_180081522
0x1800814df  mov     r8d, r14d
0x1800814e2  mov     edx, esi
0x1800814e4  mov     ecx, 100h
0x1800814e9  call    cs:__imp_ExAllocatePool2
0x1800814f0  nop     dword ptr [rax+rax+00h]
0x1800814f5  mov     [r12], rax
0x1800814f9  mov     r14, rax
0x1800814fc  test    rax, rax
0x1800814ff  jz      short loc_18008148C
0x180081501  lea     rdx, [rdi+0Ch]; Src
0x180081505  mov     r8d, esi; Size
0x180081508  mov     rcx, rax; void *
0x18008150b  call    memmove
0x180081510  shr     esi, 1
0x180081512  xor     eax, eax
0x180081514  mov     [r13+0], esi
0x180081518  lea     ecx, [rsi-1]
0x18008151b  mov     [r14+rcx*2], ax
0x180081520  jmp     short loc_180081527
0x180081522  mov     ebx, 0C0000034h
0x180081527  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008152b  test    rcx, rcx
0x18008152e  jz      short loc_18008153C
0x180081530  call    cs:__imp_ZwClose
0x180081537  nop     dword ptr [rax+rax+00h]
0x18008153c  test    rdi, rdi
0x18008153f  jz      short loc_180081552
0x180081541  xor     edx, edx; Tag
0x180081543  mov     rcx, rdi; P
0x180081546  call    cs:__imp_ExFreePoolWithTag
0x18008154d  nop     dword ptr [rax+rax+00h]
0x180081552  mov     eax, ebx
0x180081554  add     rsp, 98h
0x18008155b  pop     r15
0x18008155d  pop     r14
0x18008155f  pop     r13
0x180081561  pop     r12
0x180081563  pop     rdi
0x180081564  pop     rsi
0x180081565  pop     rbx
0x180081566  pop     rbp
0x180081567  retn
```
