# MupiLookupKnownPrefixEntry

- ea: `0x14001e5b0`
- end: `0x14001e626`
- name: `MupiLookupKnownPrefixEntry`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003140`
- `0x1400033d0`
- `0x14001067c`
- `0x14001d6f4`

## callees

- `0x1400036c8`
- `0x14001e5b0`

## import_xrefs

- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001e5c3`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001e5c3`

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
0x14001e5b0  mov     [rsp+arg_0], rbx
0x14001e5b5  push    rdi
0x14001e5b6  sub     rsp, 30h
0x14001e5ba  mov     r8d, 1; CaseInsensitiveIndex
0x14001e5c0  mov     rdi, rdx
0x14001e5c3  call    cs:__imp_RtlFindUnicodePrefix
0x14001e5ca  nop     dword ptr [rax+rax+00h]
0x14001e5cf  xor     ecx, ecx
0x14001e5d1  lea     rbx, [rax-10h]
0x14001e5d5  test    rax, rax
0x14001e5d8  lea     rax, WPP_GLOBAL_Control
0x14001e5df  cmovz   rbx, rcx
0x14001e5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5ea  cmp     rcx, rax
0x14001e5ed  jz      short loc_14001E5F8
0x14001e5ef  test    dword ptr [rcx+2Ch], 2000000h
0x14001e5f6  jnz     short loc_14001E607
0x14001e5f8  mov     rax, rbx
0x14001e5fb  mov     rbx, [rsp+38h+arg_0]
0x14001e600  add     rsp, 30h
0x14001e604  pop     rdi
0x14001e605  retn
0x14001e607  mov     rcx, [rcx+18h]
0x14001e60b  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001e612  mov     edx, 19h
0x14001e617  mov     [rsp+38h+var_18], rbx
0x14001e61c  mov     r9, rdi
0x14001e61f  call    WPP_SF_Zq
0x14001e624  jmp     short loc_14001E5F8
```
