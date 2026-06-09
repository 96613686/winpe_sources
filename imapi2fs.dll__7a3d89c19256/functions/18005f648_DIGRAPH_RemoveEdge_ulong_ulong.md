# DIGRAPH::RemoveEdge(ulong,ulong)

- ea: `0x18005f648`
- end: `0x18005f70b`
- name: `?RemoveEdge@DIGRAPH@@QEAAEKK@Z`
- size: `195`
- prototype: `unsigned __int8 __fastcall(DIGRAPH *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001b20`
- `0x180071674`
- `0x180071944`

## callees

- `0x180003e60`
- `0x18005f648`
- `0x180081750`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTable` at `0x18005f6eb`
- `ntdll!RtlDeleteElementGenericTable` at `0x18005f6eb`
- `ntdll!RtlFindSetBits` at `0x18005f6d8`
- `ntdll!RtlFindSetBits` at `0x18005f6d8`
- `ntdll!RtlClearBits` at `0x18005f6c6`
- `ntdll!RtlClearBits` at `0x18005f6c6`
- `ntdll!RtlLookupElementGenericTable` at `0x18005f695`
- `ntdll!RtlLookupElementGenericTable` at `0x18005f695`
- `ntdll!RtlInitializeBitMap` at `0x18005f6af`
- `ntdll!RtlInitializeBitMap` at `0x18005f6af`

## pseudocode

```c
unsigned __int8 __fastcall DIGRAPH::RemoveEdge(DIGRAPH *this, unsigned int a2, int a3)
{
  struct PARENT_ENTRY *ParentEntry; // rax
  struct _RTL_GENERIC_TABLE *v5; // rbx
  ULONG *v6; // rax
  struct _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+30h] [rbp-18h] BYREF

  Buffer = a3 & 0xFFFFFFE0;
  BitMapHeader = 0;
  ParentEntry = DIGRAPH::GetParentEntry(this, a2);
  if ( ParentEntry )
  {
    v5 = (struct _RTL_GENERIC_TABLE *)((char *)ParentEntry + 16);
    v6 = (ULONG *)RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)ParentEntry + 16), &Buffer);
    if ( v6 )
    {
      RtlInitializeBitMap(&BitMapHeader, v6 + 1, 0x20u);
      RtlClearBits(&BitMapHeader, a3 - Buffer, 1u);
      if ( RtlFindSetBits(&BitMapHeader, 1u, 0) == -1 )
        RtlDeleteElementGenericTable(v5, &Buffer);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18005f648  mov     [rsp+arg_18], rbx
0x18005f64d  push    rdi
0x18005f64e  sub     rsp, 40h
0x18005f652  mov     rax, cs:__security_cookie
0x18005f659  xor     rax, rsp
0x18005f65c  mov     [rsp+48h+var_10], rax
0x18005f661  mov     eax, r8d
0x18005f664  mov     [rsp+48h+Buffer], 0
0x18005f66d  and     eax, 0FFFFFFE0h
0x18005f670  xorps   xmm0, xmm0
0x18005f673  mov     dword ptr [rsp+48h+Buffer], eax
0x18005f677  mov     edi, r8d
0x18005f67a  movups  xmmword ptr [rsp+48h+BitMapHeader.SizeOfBitMap], xmm0
0x18005f67f  call    ?GetParentEntry@DIGRAPH@@AEBAPEAUPARENT_ENTRY@@K@Z; DIGRAPH::GetParentEntry(ulong)
0x18005f684  test    rax, rax
0x18005f687  jz      short loc_18005F6F1
0x18005f689  lea     rbx, [rax+10h]
0x18005f68d  mov     rcx, rbx; Table
0x18005f690  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18005f695  call    cs:__imp_RtlLookupElementGenericTable
0x18005f69b  test    rax, rax
0x18005f69e  jz      short loc_18005F6F1
0x18005f6a0  lea     rdx, [rax+4]; BitMapBuffer
0x18005f6a4  mov     r8d, 20h ; ' '; SizeOfBitMap
0x18005f6aa  lea     rcx, [rsp+48h+BitMapHeader]; BitMapHeader
0x18005f6af  call    cs:__imp_RtlInitializeBitMap
0x18005f6b5  sub     edi, dword ptr [rsp+48h+Buffer]
0x18005f6b9  lea     rcx, [rsp+48h+BitMapHeader]; BitMapHeader
0x18005f6be  mov     edx, edi; StartingIndex
0x18005f6c0  mov     r8d, 1; NumberToClear
0x18005f6c6  call    cs:__imp_RtlClearBits
0x18005f6cc  xor     r8d, r8d; HintIndex
0x18005f6cf  lea     rcx, [rsp+48h+BitMapHeader]; BitMapHeader
0x18005f6d4  lea     edx, [r8+1]; NumberToFind
0x18005f6d8  call    cs:__imp_RtlFindSetBits
0x18005f6de  cmp     eax, 0FFFFFFFFh
0x18005f6e1  jnz     short loc_18005F6F1
0x18005f6e3  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18005f6e8  mov     rcx, rbx; Table
0x18005f6eb  call    cs:__imp_RtlDeleteElementGenericTable
0x18005f6f1  mov     al, 1
0x18005f6f3  mov     rcx, [rsp+48h+var_10]
0x18005f6f8  xor     rcx, rsp; StackCookie
0x18005f6fb  call    __security_check_cookie
0x18005f700  mov     rbx, [rsp+48h+arg_18]
0x18005f705  add     rsp, 40h
0x18005f709  pop     rdi
0x18005f70a  retn
```
