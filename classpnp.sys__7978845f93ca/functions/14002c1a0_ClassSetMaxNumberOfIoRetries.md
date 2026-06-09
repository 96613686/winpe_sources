# ClassSetMaxNumberOfIoRetries

- ea: `0x14002c1a0`
- end: `0x14002c30a`
- name: `ClassSetMaxNumberOfIoRetries`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x140056a40`

## callees

- `0x14002c1a0`
- `0x14003e470`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002c1f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c289`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c1f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c289`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14002c2bd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002c299`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002c299`
- `ntoskrnl!ZwClose` at `0x14002c2ec`
- `ntoskrnl!ZwClose` at `0x14002c2ec`
- `ntoskrnl!ZwOpenKey` at `0x14002c22f`
- `ntoskrnl!ZwOpenKey` at `0x14002c22f`

## string_xrefs

- `0x14002c252`: `RtlQueryRegistryValuesEx`
- `0x14002c1e5`: `\Registry\Machine\System\CurrentControlSet\Control\Classpnp`

## pseudocode

```c
int ClassSetMaxNumberOfIoRetries()
{
  int result; // eax
  void *v1; // rbx
  PVOID SystemRoutineAddress; // rax
  int v3; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v7[14]; // [rsp+80h] [rbp-19h] BYREF
  unsigned int v8; // [rsp+100h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+108h] [rbp+6Fh] BYREF

  KeyHandle = 0;
  v8 = 4;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  memset(v7, 0, sizeof(v7));
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Classpnp");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v1 = KeyHandle;
    v7[2] = L"MaxNumberOfIoRetries";
    LODWORD(v7[1]) = 292;
    v7[3] = &v8;
    LODWORD(v7[4]) = 0x4000000;
    v7[5] = 0;
    LODWORD(v7[6]) = 0;
    SystemRoutineName = 0;
    RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    if ( ((int (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(0x40000000, v1, v7, 0, 0) >= 0
      && v8 )
    {
      v3 = 255;
      if ( v8 <= 0xFF )
        v3 = v8;
      MaxNumberOfIoRetries = v3;
    }
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x14002c1a0  mov     [rsp-8+arg_10], rbx
0x14002c1a5  push    rbp
0x14002c1a6  lea     rbp, [rsp-57h]
0x14002c1ab  sub     rsp, 0F0h
0x14002c1b2  xorps   xmm0, xmm0
0x14002c1b5  mov     [rbp+57h+KeyHandle], 0
0x14002c1bd  xor     eax, eax
0x14002c1bf  mov     [rbp+57h+arg_0], 4
0x14002c1c6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002c1ca  xor     edx, edx; Val
0x14002c1cc  lea     rcx, [rbp+57h+var_70]; void *
0x14002c1d0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002c1d4  lea     r8d, [rax+70h]; Size
0x14002c1d8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002c1dc  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002c1e0  call    memset
0x14002c1e5  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002c1ec  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002c1f0  call    cs:__imp_RtlInitUnicodeString
0x14002c1f7  nop     dword ptr [rax+rax+00h]
0x14002c1fc  lea     rax, [rbp+57h+DestinationString]
0x14002c200  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002c207  xorps   xmm0, xmm0
0x14002c20a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002c20e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002c212  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14002c21a  mov     edx, 20019h; DesiredAccess
0x14002c21f  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002c226  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002c22a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c22f  call    cs:__imp_ZwOpenKey
0x14002c236  nop     dword ptr [rax+rax+00h]
0x14002c23b  test    eax, eax
0x14002c23d  js      loc_14002C2F8
0x14002c243  mov     rbx, [rbp+57h+KeyHandle]
0x14002c247  lea     rax, aMaxnumberofior; "MaxNumberOfIoRetries"
0x14002c24e  mov     [rbp+57h+var_60], rax
0x14002c252  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14002c259  lea     rax, [rbp+57h+arg_0]
0x14002c25d  mov     [rbp+57h+var_68], 124h
0x14002c264  xorps   xmm0, xmm0
0x14002c267  mov     [rbp+57h+var_58], rax
0x14002c26b  lea     rcx, [rbp+57h+SystemRoutineName]; DestinationString
0x14002c26f  mov     [rbp+57h+var_50], 4000000h
0x14002c276  mov     [rbp+57h+var_48], 0
0x14002c27e  mov     [rbp+57h+var_40], 0
0x14002c285  movups  xmmword ptr [rbp+57h+SystemRoutineName.Length], xmm0
0x14002c289  call    cs:__imp_RtlInitUnicodeString
0x14002c290  nop     dword ptr [rax+rax+00h]
0x14002c295  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x14002c299  call    cs:__imp_MmGetSystemRoutineAddress
0x14002c2a0  nop     dword ptr [rax+rax+00h]
0x14002c2a5  lea     r8, [rbp+57h+var_70]
0x14002c2a9  mov     [rsp+0F0h+var_D0], 0
0x14002c2b2  test    rax, rax
0x14002c2b5  mov     rdx, rbx
0x14002c2b8  mov     ecx, 40000000h
0x14002c2bd  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14002c2c5  xor     r9d, r9d
0x14002c2c8  call    _guard_dispatch_icall
0x14002c2cd  test    eax, eax
0x14002c2cf  js      short loc_14002C2E8
0x14002c2d1  mov     ecx, [rbp+57h+arg_0]
0x14002c2d4  test    ecx, ecx
0x14002c2d6  jz      short loc_14002C2E8
0x14002c2d8  mov     eax, 0FFh
0x14002c2dd  cmp     ecx, eax
0x14002c2df  cmovbe  eax, ecx
0x14002c2e2  mov     cs:MaxNumberOfIoRetries, eax
0x14002c2e8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002c2ec  call    cs:__imp_ZwClose
0x14002c2f3  nop     dword ptr [rax+rax+00h]
0x14002c2f8  mov     rbx, [rsp+0F0h+arg_10]
0x14002c300  add     rsp, 0F0h
0x14002c307  pop     rbp
0x14002c308  retn
```
