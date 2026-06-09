# HvSocketCreateProviderHandle

- ea: `0x14001a670`
- end: `0x14001a6cf`
- name: `HvSocketCreateProviderHandle`
- size: `95`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000a048`
- `0x14001a670`

## string_xrefs

- `0x14001a69a`: `HvSocketCreateProviderHandle`

## pseudocode

```c
__int64 __fastcall HvSocketCreateProviderHandle(__int64 a1, _QWORD *a2)
{
  *a2 = a1;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketCreateProviderHandle",
      44,
      a1,
      *(_QWORD *)(a1 + 8),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
    __fastfail(0xEu);
  return 0;
}

```

## disassembly

```asm
0x14001a670  push    rbx
0x14001a672  sub     rsp, 30h
0x14001a676  mov     [rdx], rcx
0x14001a679  mov     rbx, rcx
0x14001a67c  mov     eax, cs:dword_140013058
0x14001a682  cmp     eax, 5
0x14001a685  jbe     short loc_14001A6AB
0x14001a687  mov     r9, [rcx+8]
0x14001a68b  lea     rax, aReferenceObjec; "Reference object"
0x14001a692  mov     r8, rcx
0x14001a695  mov     [rsp+38h+var_18], rax
0x14001a69a  lea     rcx, aHvsocketcreate; "HvSocketCreateProviderHandle"
0x14001a6a1  mov     edx, 2Ch ; ','
0x14001a6a6  call    HvsocketTraceReferenceCount
0x14001a6ab  mov     eax, 1
0x14001a6b0  lock xadd [rbx+8], rax
0x14001a6b6  inc     rax
0x14001a6b9  cmp     rax, 1
0x14001a6bd  jg      short loc_14001A6C6
0x14001a6bf  mov     ecx, 0Eh
0x14001a6c4  int     29h; Win8: RtlFailFast(ecx)
0x14001a6c6  xor     eax, eax
0x14001a6c8  add     rsp, 30h
0x14001a6cc  pop     rbx
0x14001a6cd  retn
```
