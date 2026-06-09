# CmRegUtilOpenExistingWstrKey

- ea: `0x140022360`
- end: `0x1400223e5`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140021af0`
- `0x140021e6c`

## callees

- `0x140005d08`
- `0x140022360`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400223bf`
- `ntoskrnl!ZwOpenKey` at `0x1400223bf`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilOpenExistingWstrKey(__int64 a1, const WCHAR *a2, __int64 a3, void **a4)
{
  NTSTATUS result; // eax
  ACCESS_MASK v6; // r10d
  void *v7; // r11
  void *KeyHandle; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    KeyHandle = 0;
    *a4 = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = v7;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, v6, &ObjectAttributes);
    if ( result >= 0 )
      *a4 = KeyHandle;
  }
  return result;
}

```

## disassembly

```asm
0x140022360  mov     [rsp-8+arg_0], rbx
0x140022365  push    rbp
0x140022366  mov     rbp, rsp
0x140022369  sub     rsp, 70h
0x14002236d  mov     r11, rcx
0x140022370  xorps   xmm0, xmm0
0x140022373  lea     rcx, [rbp+DestinationString]; DestinationString
0x140022377  mov     rbx, r9
0x14002237a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002237e  mov     r10d, r8d
0x140022381  call    WdmlibRtlInitUnicodeStringEx
0x140022386  test    eax, eax
0x140022388  js      short loc_1400223D6
0x14002238a  xor     eax, eax
0x14002238c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140022394  mov     [rbp+KeyHandle], rax
0x140022398  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002239c  mov     [rbx], rax
0x14002239f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400223a3  lea     rax, [rbp+DestinationString]
0x1400223a7  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400223af  mov     edx, r10d; DesiredAccess
0x1400223b2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400223b6  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x1400223ba  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400223bf  call    cs:__imp_ZwOpenKey
0x1400223c6  nop     dword ptr [rax+rax+00h]
0x1400223cb  test    eax, eax
0x1400223cd  js      short loc_1400223D6
0x1400223cf  mov     rcx, [rbp+KeyHandle]
0x1400223d3  mov     [rbx], rcx
0x1400223d6  mov     rbx, [rsp+70h+arg_0]
0x1400223de  add     rsp, 70h
0x1400223e2  pop     rbp
0x1400223e3  retn
```
