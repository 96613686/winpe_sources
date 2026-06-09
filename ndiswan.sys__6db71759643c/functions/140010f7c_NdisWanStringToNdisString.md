# NdisWanStringToNdisString

- ea: `0x140010f7c`
- end: `0x140010fef`
- name: `NdisWanStringToNdisString`
- size: `115`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bfcc`
- `0x14000e400`
- `0x140035ad8`

## callees

- `0x140010f7c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140010f92`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010f92`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010fdc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010fdc`
- `ntoskrnl!ExAllocatePool2` at `0x140010fae`
- `ntoskrnl!ExAllocatePool2` at `0x140010fae`

## pseudocode

```c
void __fastcall NdisWanStringToNdisString(PUNICODE_STRING DestinationString, const WCHAR *a2)
{
  WCHAR *Pool2; // rax
  struct _UNICODE_STRING DestinationStringa; // [rsp+20h] [rbp-18h] BYREF

  DestinationStringa = 0;
  RtlInitUnicodeString(&DestinationStringa, a2);
  Pool2 = (WCHAR *)ExAllocatePool2(64, DestinationStringa.MaximumLength, 1299079511);
  DestinationString->Buffer = Pool2;
  if ( Pool2 )
  {
    DestinationString->MaximumLength = DestinationStringa.MaximumLength;
    DestinationString->Length = DestinationStringa.Length;
    RtlCopyUnicodeString(DestinationString, &DestinationStringa);
  }
}

```

## disassembly

```asm
0x140010f7c  push    rbx
0x140010f7e  sub     rsp, 30h
0x140010f82  mov     rbx, rcx
0x140010f85  xorps   xmm0, xmm0
0x140010f88  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140010f8d  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140010f92  call    cs:__imp_RtlInitUnicodeString
0x140010f99  nop     dword ptr [rax+rax+00h]
0x140010f9e  movzx   edx, [rsp+38h+DestinationString.MaximumLength]
0x140010fa3  mov     ecx, 40h ; '@'
0x140010fa8  mov     r8d, 4D6E6157h
0x140010fae  call    cs:__imp_ExAllocatePool2
0x140010fb5  nop     dword ptr [rax+rax+00h]
0x140010fba  mov     [rbx+8], rax
0x140010fbe  test    rax, rax
0x140010fc1  jz      short loc_140010FE8
0x140010fc3  movzx   eax, [rsp+38h+DestinationString.MaximumLength]
0x140010fc8  lea     rdx, [rsp+38h+DestinationString]; SourceString
0x140010fcd  mov     [rbx+2], ax
0x140010fd1  mov     rcx, rbx; DestinationString
0x140010fd4  movzx   eax, [rsp+38h+DestinationString.Length]
0x140010fd9  mov     [rbx], ax
0x140010fdc  call    cs:__imp_RtlCopyUnicodeString
0x140010fe3  nop     dword ptr [rax+rax+00h]
0x140010fe8  add     rsp, 30h
0x140010fec  pop     rbx
0x140010fed  retn
```
