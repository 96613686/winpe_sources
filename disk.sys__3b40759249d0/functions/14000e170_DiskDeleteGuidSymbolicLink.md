# DiskDeleteGuidSymbolicLink

- ea: `0x14000e170`
- end: `0x14000e1ec`
- name: `DiskDeleteGuidSymbolicLink`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140014f00`

## callees

- `0x14000e170`
- `0x1400159c0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e1ce`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e1ce`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000e1b4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000e1b4`

## pseudocode

```c
__int64 __fastcall DiskDeleteGuidSymbolicLink(__int64 a1)
{
  __int64 v1; // rcx
  __int64 v2; // rbx
  __int64 v3; // rcx
  NTSTATUS GuidSymbolicLinkName; // edi
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v2 = *(_QWORD *)(v1 + 96);
  if ( !*(_BYTE *)(v2 + 524) )
    return 0;
  v3 = *(_QWORD *)(v1 + 1168);
  SymbolicLinkName = 0;
  GuidSymbolicLinkName = DiskGetGuidSymbolicLinkName((const GUID *)(v3 + 4), &SymbolicLinkName);
  if ( GuidSymbolicLinkName >= 0 )
  {
    GuidSymbolicLinkName = IoDeleteSymbolicLink(&SymbolicLinkName);
    *(_BYTE *)(v2 + 524) = 0;
  }
  RtlFreeUnicodeString(&SymbolicLinkName);
  return (unsigned int)GuidSymbolicLinkName;
}

```

## disassembly

```asm
0x14000e170  push    rbx
0x14000e172  sub     rsp, 30h
0x14000e176  mov     rcx, [rcx+40h]
0x14000e17a  mov     rbx, [rcx+60h]
0x14000e17e  cmp     byte ptr [rbx+20Ch], 0
0x14000e185  jz      short loc_14000E1E3
0x14000e187  mov     rcx, [rcx+490h]
0x14000e18e  lea     rdx, [rsp+38h+SymbolicLinkName]
0x14000e193  xorps   xmm0, xmm0
0x14000e196  mov     [rsp+38h+arg_0], rdi
0x14000e19b  add     rcx, 4
0x14000e19f  movups  xmmword ptr [rsp+38h+SymbolicLinkName.Length], xmm0
0x14000e1a4  call    DiskGetGuidSymbolicLinkName
0x14000e1a9  mov     edi, eax
0x14000e1ab  test    eax, eax
0x14000e1ad  js      short loc_14000E1C9
0x14000e1af  lea     rcx, [rsp+38h+SymbolicLinkName]; SymbolicLinkName
0x14000e1b4  call    cs:__imp_IoDeleteSymbolicLink
0x14000e1bb  nop     dword ptr [rax+rax+00h]
0x14000e1c0  mov     edi, eax
0x14000e1c2  mov     byte ptr [rbx+20Ch], 0
0x14000e1c9  lea     rcx, [rsp+38h+SymbolicLinkName]; UnicodeString
0x14000e1ce  call    cs:__imp_RtlFreeUnicodeString
0x14000e1d5  nop     dword ptr [rax+rax+00h]
0x14000e1da  mov     eax, edi
0x14000e1dc  mov     rdi, [rsp+38h+arg_0]
0x14000e1e1  jmp     short loc_14000E1E5
0x14000e1e3  xor     eax, eax
0x14000e1e5  add     rsp, 30h
0x14000e1e9  pop     rbx
0x14000e1ea  retn
```
