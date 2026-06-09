# RfsRegKeyExists

- ea: `0x140086030`
- end: `0x1400860d0`
- name: `RfsRegKeyExists`
- size: `160`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008a19c`

## callees

- `0x140086030`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008609e`
- `ntoskrnl!ZwOpenKey` at `0x14008609e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008605d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008605d`
- `ntoskrnl!ZwClose` at `0x1400860b6`
- `ntoskrnl!ZwClose` at `0x1400860b6`

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
0x140086030  mov     [rsp-8+arg_0], rbx
0x140086035  push    rbp
0x140086036  mov     rbp, rsp
0x140086039  sub     rsp, 60h
0x14008603d  xorps   xmm0, xmm0
0x140086040  xor     eax, eax
0x140086042  mov     rdx, rcx; SourceString
0x140086045  mov     [rbp+KeyHandle], rax
0x140086049  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008604d  lea     rcx, [rbp+DestinationString]; DestinationString
0x140086051  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140086055  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140086059  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14008605d  call    cs:__imp_RtlInitUnicodeString
0x140086064  nop     dword ptr [rax+rax+00h]
0x140086069  lea     rax, [rbp+DestinationString]
0x14008606d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140086074  xorps   xmm0, xmm0
0x140086077  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14008607b  mov     ebx, 1
0x140086080  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140086088  mov     edx, ebx; DesiredAccess
0x14008608a  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140086091  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140086095  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140086099  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008609e  call    cs:__imp_ZwOpenKey
0x1400860a5  nop     dword ptr [rax+rax+00h]
0x1400860aa  test    eax, eax
0x1400860ac  jns     short loc_1400860B2
0x1400860ae  xor     bl, bl
0x1400860b0  jmp     short loc_1400860C2
0x1400860b2  mov     rcx, [rbp+KeyHandle]; Handle
0x1400860b6  call    cs:__imp_ZwClose
0x1400860bd  nop     dword ptr [rax+rax+00h]
0x1400860c2  mov     al, bl
0x1400860c4  mov     rbx, [rsp+60h+arg_0]
0x1400860c9  add     rsp, 60h
0x1400860cd  pop     rbp
0x1400860ce  retn
```
