# PrjfDeletePathTierNode

- ea: `0x140044bb4`
- end: `0x140044c18`
- name: `PrjfDeletePathTierNode`
- size: `100`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400442ec`
- `0x140044cec`
- `0x14004565c`

## callees

- `0x140044bb4`
- `0x140044c20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044c05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044c05`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140044bf1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140044bf1`

## pseudocode

```c
void __fastcall PrjfDeletePathTierNode(struct _UNICODE_STRING *P)
{
  unsigned __int64 Buffer; // rcx

  if ( (*(_DWORD *)&P->Length & 0x10) == 0 )
  {
    Buffer = (unsigned __int64)P[3].Buffer;
    if ( Buffer )
    {
      PrjfDeletePathTree(Buffer);
      P[3].Buffer = 0;
    }
  }
  if ( *(_DWORD *)&P[3].Length )
    *(_DWORD *)&P[3].Length = 0;
  if ( P[2].Buffer )
    RtlFreeUnicodeString(P + 2);
  ExFreePoolWithTag(P, 0x6D6E4A50u);
}

```

## disassembly

```asm
0x140044bb4  push    rbx
0x140044bb6  sub     rsp, 20h
0x140044bba  mov     eax, [rcx]
0x140044bbc  mov     rbx, rcx
0x140044bbf  test    al, 10h
0x140044bc1  jnz     short loc_140044BD9
0x140044bc3  mov     rcx, [rcx+38h]; P
0x140044bc7  test    rcx, rcx
0x140044bca  jz      short loc_140044BD9
0x140044bcc  call    PrjfDeletePathTree
0x140044bd1  mov     qword ptr [rbx+38h], 0
0x140044bd9  cmp     dword ptr [rbx+30h], 0
0x140044bdd  jz      short loc_140044BE6
0x140044bdf  mov     dword ptr [rbx+30h], 0
0x140044be6  cmp     qword ptr [rbx+28h], 0
0x140044beb  jz      short loc_140044BFD
0x140044bed  lea     rcx, [rbx+20h]; UnicodeString
0x140044bf1  call    cs:__imp_RtlFreeUnicodeString
0x140044bf8  nop     dword ptr [rax+rax+00h]
0x140044bfd  mov     edx, 6D6E4A50h; Tag
0x140044c02  mov     rcx, rbx; P
0x140044c05  call    cs:__imp_ExFreePoolWithTag
0x140044c0c  nop     dword ptr [rax+rax+00h]
0x140044c11  add     rsp, 20h
0x140044c15  pop     rbx
0x140044c16  retn
```
