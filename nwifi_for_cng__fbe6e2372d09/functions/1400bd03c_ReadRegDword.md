# ReadRegDword

- ea: `0x1400bd03c`
- end: `0x1400bd147`
- name: `ReadRegDword`
- size: `267`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140036e68`

## callees

- `0x140020dc0`
- `0x1400bcfa4`
- `0x1400bd03c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400bd128`
- `ntoskrnl!ZwClose` at `0x1400bd128`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd080`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd080`
- `ntoskrnl!ZwOpenKey` at `0x1400bd0bf`
- `ntoskrnl!ZwOpenKey` at `0x1400bd0bf`

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
0x1400bd03c  push    rbp
0x1400bd03e  push    rbx
0x1400bd03f  push    rsi
0x1400bd040  push    rdi
0x1400bd041  push    r14
0x1400bd043  push    r15
0x1400bd045  lea     rbp, [rsp-27h]
0x1400bd04a  sub     rsp, 88h
0x1400bd051  mov     rdi, [rbp+4Fh+arg_20]
0x1400bd055  xorps   xmm0, xmm0
0x1400bd058  mov     r14, rdx
0x1400bd05b  mov     [rbp+4Fh+KeyHandle], 0
0x1400bd063  mov     rdx, rcx; SourceString
0x1400bd066  mov     esi, r9d
0x1400bd069  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1400bd06d  mov     r15d, [rdi]
0x1400bd070  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400bd074  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400bd078  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bd07c  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400bd080  call    cs:__imp_RtlInitUnicodeString
0x1400bd087  nop     dword ptr [rax+rax+00h]
0x1400bd08c  lea     rax, [rbp+4Fh+DestinationString]
0x1400bd090  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400bd097  xorps   xmm0, xmm0
0x1400bd09a  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400bd09e  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400bd0a2  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x1400bd0aa  mov     edx, 20019h; DesiredAccess
0x1400bd0af  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1400bd0b6  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1400bd0ba  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bd0bf  call    cs:__imp_ZwOpenKey
0x1400bd0c6  nop     dword ptr [rax+rax+00h]
0x1400bd0cb  mov     ebx, eax
0x1400bd0cd  test    eax, eax
0x1400bd0cf  jns     short loc_1400BD107
0x1400bd0d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd0d8  lea     rax, WPP_GLOBAL_Control
0x1400bd0df  cmp     rcx, rax
0x1400bd0e2  jz      short loc_1400BD11F
0x1400bd0e4  test    dword ptr [rcx+2Ch], 200h
0x1400bd0eb  jz      short loc_1400BD11F
0x1400bd0ed  mov     rcx, [rcx+18h]
0x1400bd0f1  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400bd0f8  mov     edx, 0Fh
0x1400bd0fd  mov     r9d, ebx
0x1400bd100  call    WPP_SF_d
0x1400bd105  jmp     short loc_1400BD11F
0x1400bd107  mov     rcx, [rbp+4Fh+KeyHandle]
0x1400bd10b  xor     r9d, r9d
0x1400bd10e  mov     r8d, r15d
0x1400bd111  mov     [rsp+0B0h+var_90], esi
0x1400bd115  mov     rdx, r14
0x1400bd118  call    Dot11ReadULong
0x1400bd11d  mov     [rdi], eax
0x1400bd11f  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1400bd123  test    rcx, rcx
0x1400bd126  jz      short loc_1400BD134
0x1400bd128  call    cs:__imp_ZwClose
0x1400bd12f  nop     dword ptr [rax+rax+00h]
0x1400bd134  mov     eax, ebx
0x1400bd136  add     rsp, 88h
0x1400bd13d  pop     r15
0x1400bd13f  pop     r14
0x1400bd141  pop     rdi
0x1400bd142  pop     rsi
0x1400bd143  pop     rbx
0x1400bd144  pop     rbp
0x1400bd145  retn
```
