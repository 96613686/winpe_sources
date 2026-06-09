# DfscGetSiteName

- ea: `0x140018ca4`
- end: `0x140018d3d`
- name: `DfscGetSiteName`
- size: `153`
- prototype: `void __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b230`

## callees

- `0x140018ca4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140018d20`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140018d20`
- `ntoskrnl!ExAllocatePool2` at `0x140018cf0`
- `ntoskrnl!ExAllocatePool2` at `0x140018cf0`

## pseudocode

```c
void __fastcall DfscGetSiteName(PUNICODE_STRING DestinationString)
{
  WCHAR *Pool2; // rax

  if ( DestinationString && ::DestinationString.Length && ::DestinationString.Buffer && *::DestinationString.Buffer )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(258, ::DestinationString.Length + 2LL, 1262708292);
    DestinationString->Buffer = Pool2;
    if ( Pool2 )
    {
      DestinationString->Length = 0;
      DestinationString->MaximumLength = ::DestinationString.Length + 2;
      RtlCopyUnicodeString(DestinationString, &::DestinationString);
    }
  }
}

```

## disassembly

```asm
0x140018ca4  test    rcx, rcx
0x140018ca7  jz      locret_140018D3B
0x140018cad  mov     [rsp+arg_0], rbx
0x140018cb2  mov     [rsp+arg_8], rsi
0x140018cb7  push    rdi
0x140018cb8  sub     rsp, 20h
0x140018cbc  mov     rbx, rcx
0x140018cbf  xor     edi, edi
0x140018cc1  movzx   ecx, cs:DestinationString.Length
0x140018cc8  test    cx, cx
0x140018ccb  jz      short loc_140018D2C
0x140018ccd  mov     rax, cs:DestinationString.Buffer
0x140018cd4  test    rax, rax
0x140018cd7  jz      short loc_140018D2C
0x140018cd9  cmp     [rax], di
0x140018cdc  jz      short loc_140018D2C
0x140018cde  lea     esi, [rdi+2]
0x140018ce1  mov     r8d, 4B436644h
0x140018ce7  lea     rdx, [rsi+rcx]
0x140018ceb  mov     ecx, 102h
0x140018cf0  call    cs:__imp_ExAllocatePool2
0x140018cf7  nop     dword ptr [rax+rax+00h]
0x140018cfc  mov     [rbx+8], rax
0x140018d00  test    rax, rax
0x140018d03  jz      short loc_140018D2C
0x140018d05  mov     [rbx], di
0x140018d08  lea     rdx, DestinationString; SourceString
0x140018d0f  movzx   eax, cs:DestinationString.Length
0x140018d16  mov     rcx, rbx; DestinationString
0x140018d19  add     ax, si
0x140018d1c  mov     [rbx+2], ax
0x140018d20  call    cs:__imp_RtlCopyUnicodeString
0x140018d27  nop     dword ptr [rax+rax+00h]
0x140018d2c  mov     rbx, [rsp+28h+arg_0]
0x140018d31  mov     rsi, [rsp+28h+arg_8]
0x140018d36  add     rsp, 20h
0x140018d3a  pop     rdi
0x140018d3b  retn
```
