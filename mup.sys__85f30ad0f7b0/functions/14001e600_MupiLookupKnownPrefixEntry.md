# MupiLookupKnownPrefixEntry

- ea: `0x14001e600`
- end: `0x14001e676`
- name: `MupiLookupKnownPrefixEntry`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003140`
- `0x1400033d0`
- `0x14001067c`
- `0x14001d744`

## callees

- `0x1400036c8`
- `0x14001e600`

## import_xrefs

- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001e613`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001e613`

## pseudocode

```c
struct _RTL_SPLAY_LINKS **__fastcall MupiLookupKnownPrefixEntry(
        struct _UNICODE_PREFIX_TABLE *a1,
        const UNICODE_STRING *a2)
{
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _RTL_SPLAY_LINKS **p_RightChild; // rbx

  UnicodePrefix = RtlFindUnicodePrefix(a1, a2, 1u);
  p_RightChild = &UnicodePrefix[-1].Links.RightChild;
  if ( !UnicodePrefix )
    p_RightChild = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_Zq(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x19u,
      (__int64)WPP_ea0133f9b224365980f4880a222ef939_Traceguids,
      &a2->Length,
      p_RightChild);
  }
  return p_RightChild;
}

```

## disassembly

```asm
0x14001e600  mov     [rsp+arg_0], rbx
0x14001e605  push    rdi
0x14001e606  sub     rsp, 30h
0x14001e60a  mov     r8d, 1; CaseInsensitiveIndex
0x14001e610  mov     rdi, rdx
0x14001e613  call    cs:__imp_RtlFindUnicodePrefix
0x14001e61a  nop     dword ptr [rax+rax+00h]
0x14001e61f  xor     ecx, ecx
0x14001e621  lea     rbx, [rax-10h]
0x14001e625  test    rax, rax
0x14001e628  lea     rax, WPP_GLOBAL_Control
0x14001e62f  cmovz   rbx, rcx
0x14001e633  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e63a  cmp     rcx, rax
0x14001e63d  jz      short loc_14001E648
0x14001e63f  test    dword ptr [rcx+2Ch], 2000000h
0x14001e646  jnz     short loc_14001E657
0x14001e648  mov     rax, rbx
0x14001e64b  mov     rbx, [rsp+38h+arg_0]
0x14001e650  add     rsp, 30h
0x14001e654  pop     rdi
0x14001e655  retn
0x14001e657  mov     rcx, [rcx+18h]
0x14001e65b  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001e662  mov     edx, 19h
0x14001e667  mov     [rsp+38h+var_18], rbx
0x14001e66c  mov     r9, rdi
0x14001e66f  call    WPP_SF_Zq
0x14001e674  jmp     short loc_14001E648
```
