# ReadRegDword

- ea: `0x1400ba08c`
- end: `0x1400ba197`
- name: `ReadRegDword`
- size: `267`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140036c48`

## callees

- `0x140020dc0`
- `0x1400b9ff4`
- `0x1400ba08c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400ba178`
- `ntoskrnl!ZwClose` at `0x1400ba178`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ba0d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ba0d0`
- `ntoskrnl!ZwOpenKey` at `0x1400ba10f`
- `ntoskrnl!ZwOpenKey` at `0x1400ba10f`

## pseudocode

```c
__int64 __fastcall ReadRegDword(PCWSTR SourceString, const WCHAR *a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v7; // r15d
  NTSTATUS v8; // ebx
  void *KeyHandle; // [rsp+30h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-19h] BYREF

  KeyHandle = 0;
  v7 = *a5;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    *a5 = Dot11ReadULong(KeyHandle, a2, v7, 0, a4);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids, (unsigned int)v8);
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400ba08c  push    rbp
0x1400ba08e  push    rbx
0x1400ba08f  push    rsi
0x1400ba090  push    rdi
0x1400ba091  push    r14
0x1400ba093  push    r15
0x1400ba095  lea     rbp, [rsp-27h]
0x1400ba09a  sub     rsp, 88h
0x1400ba0a1  mov     rdi, [rbp+4Fh+arg_20]
0x1400ba0a5  xorps   xmm0, xmm0
0x1400ba0a8  mov     r14, rdx
0x1400ba0ab  mov     [rbp+4Fh+KeyHandle], 0
0x1400ba0b3  mov     rdx, rcx; SourceString
0x1400ba0b6  mov     esi, r9d
0x1400ba0b9  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1400ba0bd  mov     r15d, [rdi]
0x1400ba0c0  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400ba0c4  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400ba0c8  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ba0cc  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400ba0d0  call    cs:__imp_RtlInitUnicodeString
0x1400ba0d7  nop     dword ptr [rax+rax+00h]
0x1400ba0dc  lea     rax, [rbp+4Fh+DestinationString]
0x1400ba0e0  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400ba0e7  xorps   xmm0, xmm0
0x1400ba0ea  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400ba0ee  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400ba0f2  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x1400ba0fa  mov     edx, 20019h; DesiredAccess
0x1400ba0ff  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1400ba106  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1400ba10a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ba10f  call    cs:__imp_ZwOpenKey
0x1400ba116  nop     dword ptr [rax+rax+00h]
0x1400ba11b  mov     ebx, eax
0x1400ba11d  test    eax, eax
0x1400ba11f  jns     short loc_1400BA157
0x1400ba121  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba128  lea     rax, WPP_GLOBAL_Control
0x1400ba12f  cmp     rcx, rax
0x1400ba132  jz      short loc_1400BA16F
0x1400ba134  test    dword ptr [rcx+2Ch], 200h
0x1400ba13b  jz      short loc_1400BA16F
0x1400ba13d  mov     rcx, [rcx+18h]
0x1400ba141  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400ba148  mov     edx, 0Fh
0x1400ba14d  mov     r9d, ebx
0x1400ba150  call    WPP_SF_d
0x1400ba155  jmp     short loc_1400BA16F
0x1400ba157  mov     rcx, [rbp+4Fh+KeyHandle]
0x1400ba15b  xor     r9d, r9d
0x1400ba15e  mov     r8d, r15d
0x1400ba161  mov     [rsp+0B0h+var_90], esi
0x1400ba165  mov     rdx, r14
0x1400ba168  call    Dot11ReadULong
0x1400ba16d  mov     [rdi], eax
0x1400ba16f  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1400ba173  test    rcx, rcx
0x1400ba176  jz      short loc_1400BA184
0x1400ba178  call    cs:__imp_ZwClose
0x1400ba17f  nop     dword ptr [rax+rax+00h]
0x1400ba184  mov     eax, ebx
0x1400ba186  add     rsp, 88h
0x1400ba18d  pop     r15
0x1400ba18f  pop     r14
0x1400ba191  pop     rdi
0x1400ba192  pop     rsi
0x1400ba193  pop     rbx
0x1400ba194  pop     rbp
0x1400ba195  retn
```
