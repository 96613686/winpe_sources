# LuafvIsFileInSystemManagedAdminAppData

- ea: `0x1400047cc`
- end: `0x140004884`
- name: `LuafvIsFileInSystemManagedAdminAppData`
- size: `184`
- prototype: `_BOOL8 __fastcall(__int64, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140025820`

## callees

- `0x1400047cc`
- `0x14000561c`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140004855`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140004855`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000483a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000483a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004822`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004822`

## pseudocode

```c
_BOOL8 __fastcall LuafvIsFileInSystemManagedAdminAppData(__int64 a1, const UNICODE_STRING *a2)
{
  BOOL v4; // ebx
  __int64 v5; // r8
  __int64 v6; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  DestinationString = 0;
  v4 = 0;
  if ( (int)GetUserProfilePaths(a1) >= 0 )
  {
    v6 = (unsigned int)*(unsigned __int16 *)(a1 + 120) + 16;
    DestinationString.MaximumLength = *(_WORD *)(a1 + 122) + 18;
    LOBYTE(v5) = 1;
    DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, v6, v5);
    if ( !DestinationString.Buffer )
      return v4;
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 120));
    if ( RtlAppendUnicodeStringToString(&DestinationString, &AppData) >= 0 )
      v4 = RtlPrefixUnicodeString(&DestinationString, a2, 1u) != 0;
  }
  if ( DestinationString.Buffer )
    LuafvFreePool(DestinationString.Buffer);
  return v4;
}

```

## disassembly

```asm
0x1400047cc  push    rbx
0x1400047ce  push    rbp
0x1400047cf  push    rsi
0x1400047d0  push    rdi
0x1400047d1  sub     rsp, 38h
0x1400047d5  xorps   xmm0, xmm0
0x1400047d8  mov     rsi, rdx
0x1400047db  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1400047e0  mov     rdi, rcx
0x1400047e3  xor     ebx, ebx
0x1400047e5  call    GetUserProfilePaths
0x1400047ea  test    eax, eax
0x1400047ec  js      short loc_140004866
0x1400047ee  movzx   eax, word ptr [rdi+7Ah]
0x1400047f2  lea     ebp, [rbx+1]
0x1400047f5  movzx   edx, word ptr [rdi+78h]
0x1400047f9  add     ax, 12h
0x1400047fd  add     edx, 10h
0x140004800  mov     [rsp+58h+DestinationString.MaximumLength], ax
0x140004805  mov     r8b, bpl
0x140004808  mov     ecx, ebp
0x14000480a  call    LuafvAllocatePool
0x14000480f  mov     [rsp+58h+DestinationString.Buffer], rax
0x140004814  test    rax, rax
0x140004817  jz      short loc_140004878
0x140004819  lea     rdx, [rdi+78h]; SourceString
0x14000481d  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140004822  call    cs:__imp_RtlCopyUnicodeString
0x140004829  nop     dword ptr [rax+rax+00h]
0x14000482e  lea     rdx, AppData; Source
0x140004835  lea     rcx, [rsp+58h+DestinationString]; Destination
0x14000483a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140004841  nop     dword ptr [rax+rax+00h]
0x140004846  test    eax, eax
0x140004848  js      short loc_140004866
0x14000484a  mov     r8b, bpl; CaseInSensitive
0x14000484d  lea     rcx, [rsp+58h+DestinationString]; String1
0x140004852  mov     rdx, rsi; String2
0x140004855  call    cs:__imp_RtlPrefixUnicodeString
0x14000485c  nop     dword ptr [rax+rax+00h]
0x140004861  test    al, al
0x140004863  cmovnz  ebx, ebp
0x140004866  mov     rax, [rsp+58h+DestinationString.Buffer]
0x14000486b  test    rax, rax
0x14000486e  jz      short loc_140004878
0x140004870  mov     rcx, rax
0x140004873  call    LuafvFreePool
0x140004878  mov     eax, ebx
0x14000487a  add     rsp, 38h
0x14000487e  pop     rdi
0x14000487f  pop     rsi
0x140004880  pop     rbp
0x140004881  pop     rbx
0x140004882  retn
```
