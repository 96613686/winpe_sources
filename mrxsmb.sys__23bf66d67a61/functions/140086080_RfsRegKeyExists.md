# RfsRegKeyExists

- ea: `0x140086080`
- end: `0x140086120`
- name: `RfsRegKeyExists`
- size: `160`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008a1ec`

## callees

- `0x140086080`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400860ee`
- `ntoskrnl!ZwOpenKey` at `0x1400860ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400860ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400860ad`
- `ntoskrnl!ZwClose` at `0x140086106`
- `ntoskrnl!ZwClose` at `0x140086106`

## pseudocode

```c
char __fastcall RfsRegKeyExists(PCWSTR SourceString)
{
  char v1; // bl
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  v1 = 1;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) < 0 )
    return 0;
  ZwClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x140086080  mov     [rsp-8+arg_0], rbx
0x140086085  push    rbp
0x140086086  mov     rbp, rsp
0x140086089  sub     rsp, 60h
0x14008608d  xorps   xmm0, xmm0
0x140086090  xor     eax, eax
0x140086092  mov     rdx, rcx; SourceString
0x140086095  mov     [rbp+KeyHandle], rax
0x140086099  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008609d  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400860a1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400860a5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400860a9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400860ad  call    cs:__imp_RtlInitUnicodeString
0x1400860b4  nop     dword ptr [rax+rax+00h]
0x1400860b9  lea     rax, [rbp+DestinationString]
0x1400860bd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400860c4  xorps   xmm0, xmm0
0x1400860c7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400860cb  mov     ebx, 1
0x1400860d0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400860d8  mov     edx, ebx; DesiredAccess
0x1400860da  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400860e1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400860e5  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400860e9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400860ee  call    cs:__imp_ZwOpenKey
0x1400860f5  nop     dword ptr [rax+rax+00h]
0x1400860fa  test    eax, eax
0x1400860fc  jns     short loc_140086102
0x1400860fe  xor     bl, bl
0x140086100  jmp     short loc_140086112
0x140086102  mov     rcx, [rbp+KeyHandle]; Handle
0x140086106  call    cs:__imp_ZwClose
0x14008610d  nop     dword ptr [rax+rax+00h]
0x140086112  mov     al, bl
0x140086114  mov     rbx, [rsp+60h+arg_0]
0x140086119  add     rsp, 60h
0x14008611d  pop     rbp
0x14008611e  retn
```
