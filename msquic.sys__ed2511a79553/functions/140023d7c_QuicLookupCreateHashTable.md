# QuicLookupCreateHashTable

- ea: `0x140023d7c`
- end: `0x140023e43`
- name: `QuicLookupCreateHashTable`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005008`

## callees

- `0x140023d7c`
- `0x140029094`
- `0x1400337e4`
- `0x140038bf4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003e6c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e6c2`
- `ntoskrnl!ExAllocatePool2` at `0x140023dbd`
- `ntoskrnl!ExAllocatePool2` at `0x140023dbd`

## pseudocode

```c
bool __fastcall QuicLookupCreateHashTable(__int64 a1, unsigned __int16 a2)
{
  __int64 v2; // rdi
  __int64 Pool2; // rax
  bool v5; // zf
  unsigned __int16 v6; // si
  __int64 v7; // rbp
  unsigned __int64 v8; // r14
  __int64 v10; // rdi

  v2 = a2;
  if ( !a2 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\lookup.c", 86, "PartitionCount > 0");
    __int2c();
  }
  Pool2 = ExAllocatePool2(66, v2 << 6, 808674129);
  *(_QWORD *)(a1 + 16) = Pool2;
  v5 = Pool2 == 0;
  if ( Pool2 )
  {
    v6 = 0;
    if ( (_WORD)v2 )
    {
      while ( 1 )
      {
        v7 = v6;
        v8 = (unsigned __int64)v6 << 6;
        if ( !(unsigned __int8)CxPlatHashtableInitializeEx(v8 + *(_QWORD *)(a1 + 16) + 8LL) )
          break;
        ++v6;
        *(_DWORD *)(v8 + *(_QWORD *)(a1 + 16)) = 0;
        if ( v6 >= (unsigned __int16)v2 )
        {
          Pool2 = *(_QWORD *)(a1 + 16);
          goto LABEL_8;
        }
      }
      if ( v6 )
      {
        v10 = 0;
        do
        {
          CxPlatHashtableUninitialize((PVOID)(v10 + *(_QWORD *)(a1 + 16) + 8LL));
          v10 += 64;
          --v7;
        }
        while ( v7 );
      }
      ExFreePoolWithTag(*(PVOID *)(a1 + 16), 0x30336351u);
      Pool2 = 0;
      *(_QWORD *)(a1 + 16) = 0;
    }
    else
    {
LABEL_8:
      *(_WORD *)(a1 + 12) = v2;
    }
    v5 = Pool2 == 0;
  }
  return !v5;
}

```

## disassembly

```asm
0x140023d7c  mov     rax, rsp
0x140023d7f  mov     [rax+8], rbx
0x140023d83  mov     [rax+10h], rbp
0x140023d87  mov     [rax+18h], rsi
0x140023d8b  mov     [rax+20h], rdi
0x140023d8f  push    r12
0x140023d91  push    r14
0x140023d93  push    r15
0x140023d95  sub     rsp, 20h
0x140023d99  movzx   edi, dx
0x140023d9c  xor     r15d, r15d
0x140023d9f  mov     rbx, rcx
0x140023da2  test    di, di
0x140023da5  jz      loc_14003E678
0x140023dab  mov     rdx, rdi
0x140023dae  mov     ecx, 42h ; 'B'
0x140023db3  shl     rdx, 6
0x140023db7  mov     r8d, 30336351h
0x140023dbd  call    cs:__imp_ExAllocatePool2
0x140023dc4  nop     dword ptr [rax+rax+00h]
0x140023dc9  mov     [rbx+10h], rax
0x140023dcd  test    rax, rax
0x140023dd0  jz      short loc_140023E20
0x140023dd2  movzx   esi, r15w
0x140023dd6  cmp     r15w, di
0x140023dda  jnb     short loc_140023E19
0x140023ddc  mov     r12d, 1
0x140023de2  mov     rcx, [rbx+10h]
0x140023de6  add     rcx, 8
0x140023dea  movzx   ebp, si
0x140023ded  mov     r14d, ebp
0x140023df0  shl     r14, 6
0x140023df4  add     rcx, r14
0x140023df7  call    CxPlatHashtableInitializeEx
0x140023dfc  test    al, al
0x140023dfe  jz      loc_14003E697
0x140023e04  mov     rax, [rbx+10h]
0x140023e08  add     si, r12w
0x140023e0c  mov     [r14+rax], r15d
0x140023e10  cmp     si, di
0x140023e13  jb      short loc_140023DE2
0x140023e15  mov     rax, [rbx+10h]
0x140023e19  mov     [rbx+0Ch], di
0x140023e1d  test    rax, rax
0x140023e20  mov     rbx, [rsp+38h+arg_0]
0x140023e25  setnz   al
0x140023e28  mov     rbp, [rsp+38h+arg_8]
0x140023e2d  mov     rsi, [rsp+38h+arg_10]
0x140023e32  mov     rdi, [rsp+38h+arg_18]
0x140023e37  add     rsp, 20h
0x140023e3b  pop     r15
0x140023e3d  pop     r14
0x140023e3f  pop     r12
0x140023e41  retn
0x14003e678  lea     r8, aPartitioncount; "PartitionCount > 0"
0x14003e67f  mov     edx, 56h ; 'V'
0x14003e684  lea     rcx, aCW1SMsquicSrcC_3; "C:\\__w\\1\\s\\msquic\\src\\core\\looku"...
0x14003e68b  call    CxPlatLogAssert
0x14003e690  int     2Ch; Windows NT - assertion failure
0x14003e692  jmp     loc_140023DAB
0x14003e697  cmp     r15w, si
0x14003e69b  jnb     short loc_14003E6B9
0x14003e69d  mov     rdi, r15
0x14003e6a0  mov     rcx, [rbx+10h]
0x14003e6a4  add     rcx, 8
0x14003e6a8  add     rcx, rdi; P
0x14003e6ab  call    CxPlatHashtableUninitialize
0x14003e6b0  add     rdi, 40h ; '@'
0x14003e6b4  sub     rbp, r12
0x14003e6b7  jnz     short loc_14003E6A0
0x14003e6b9  mov     rcx, [rbx+10h]; P
0x14003e6bd  mov     edx, 30336351h; Tag
0x14003e6c2  call    cs:__imp_ExFreePoolWithTag
0x14003e6c9  nop     dword ptr [rax+rax+00h]
0x14003e6ce  mov     rax, r15
0x14003e6d1  mov     [rbx+10h], r15
0x14003e6d5  jmp     loc_140023E1D
```
