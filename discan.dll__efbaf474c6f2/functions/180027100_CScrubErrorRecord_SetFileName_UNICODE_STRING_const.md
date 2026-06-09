# CScrubErrorRecord::SetFileName(_UNICODE_STRING const *)

- ea: `0x180027100`
- end: `0x180027157`
- name: `?SetFileName@CScrubErrorRecord@@QEAAJPEBU_UNICODE_STRING@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *this, const struct _UNICODE_STRING *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18002730c`

## callees

- `0x18000f478`
- `0x180027100`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180027145`
- `ntdll!RtlCopyUnicodeString` at `0x180027145`

## pseudocode

```c
__int64 __fastcall CScrubErrorRecord::SetFileName(
        struct _UNICODE_STRING *this,
        const struct _UNICODE_STRING *a2,
        __int64 a3)
{
  if ( a2->Length > this[1].MaximumLength )
  {
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CCRTAllocator>::ReallocateBytes(
                             &this[2],
                             a2->Length,
                             a3) )
      return 2147942414LL;
    this[1].MaximumLength = a2->Length;
    this[1].Buffer = *(PWSTR *)&this[2].Length;
  }
  RtlCopyUnicodeString(this + 1, a2);
  return 0;
}

```

## disassembly

```asm
0x180027100  push    rbx
0x180027102  push    rsi
0x180027103  push    rdi
0x180027104  push    r14
0x180027106  sub     rsp, 28h
0x18002710a  movzx   eax, word ptr [rdx]
0x18002710d  mov     rdi, rdx
0x180027110  mov     rbx, rcx
0x180027113  cmp     ax, [rcx+12h]
0x180027117  jbe     short loc_18002713E
0x180027119  mov     edx, eax
0x18002711b  add     rcx, 20h ; ' '
0x18002711f  call    ?ReallocateBytes@?$CHeapPtrBase@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CCRTAllocator>::ReallocateBytes(unsigned __int64)
0x180027124  test    al, al
0x180027126  jnz     short loc_18002712F
0x180027128  mov     eax, 8007000Eh
0x18002712d  jmp     short loc_18002714D
0x18002712f  movzx   eax, word ptr [rdi]
0x180027132  mov     [rbx+12h], ax
0x180027136  mov     rax, [rbx+20h]
0x18002713a  mov     [rbx+18h], rax
0x18002713e  mov     rdx, rdi; SourceString
0x180027141  lea     rcx, [rbx+10h]; DestinationString
0x180027145  call    cs:__imp_RtlCopyUnicodeString
0x18002714b  xor     eax, eax
0x18002714d  add     rsp, 28h
0x180027151  pop     r14
0x180027153  pop     rdi
0x180027154  pop     rsi
0x180027155  pop     rbx
0x180027156  retn
```
