# StSecpGetSidFromProductId

- ea: `0x14000dd68`
- end: `0x14000ddc8`
- name: `StSecpGetSidFromProductId`
- size: `96`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140010f90`

## callees

- `0x14000dd68`
- `0x140011810`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ddae`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ddae`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000dd88`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000dd88`

## pseudocode

```c
__int64 __fastcall StSecpGetSidFromProductId(PCUNICODE_STRING SourceString, __int64 a2)
{
  int AppSid; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  AppSid = RtlUpcaseUnicodeString(&DestinationString, SourceString, 1u);
  if ( AppSid >= 0 )
    AppSid = StSecpGetAppSid((PUCHAR *)&DestinationString, a2);
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)AppSid;
}

```

## disassembly

```asm
0x14000dd68  mov     [rsp+arg_0], rbx
0x14000dd6d  push    rdi
0x14000dd6e  sub     rsp, 30h
0x14000dd72  mov     rdi, rdx
0x14000dd75  xorps   xmm0, xmm0
0x14000dd78  mov     rdx, rcx; SourceString
0x14000dd7b  mov     r8b, 1; AllocateDestinationString
0x14000dd7e  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000dd83  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14000dd88  call    cs:__imp_RtlUpcaseUnicodeString
0x14000dd8f  nop     dword ptr [rax+rax+00h]
0x14000dd94  mov     ebx, eax
0x14000dd96  test    eax, eax
0x14000dd98  js      short loc_14000DDA9
0x14000dd9a  mov     rdx, rdi
0x14000dd9d  lea     rcx, [rsp+38h+DestinationString]
0x14000dda2  call    StSecpGetAppSid
0x14000dda7  mov     ebx, eax
0x14000dda9  lea     rcx, [rsp+38h+DestinationString]; UnicodeString
0x14000ddae  call    cs:__imp_RtlFreeUnicodeString
0x14000ddb5  nop     dword ptr [rax+rax+00h]
0x14000ddba  mov     eax, ebx
0x14000ddbc  mov     rbx, [rsp+38h+arg_0]
0x14000ddc1  add     rsp, 30h
0x14000ddc5  pop     rdi
0x14000ddc6  retn
```
