# PrinterFinder::_TryCreateAssociationContext(ushort const *)

- ea: `0x14000b968`
- end: `0x14000b9fe`
- name: `?_TryCreateAssociationContext@PrinterFinder@@CAPEAUDAF_ASSOCIATION_HANDLE__@@PEBG@Z`
- size: `150`
- prototype: `struct DAF_ASSOCIATION_HANDLE__ *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140005f00`
- `0x140006724`

## callees

- `0x14000b470`
- `0x14000b8f4`
- `0x14000b968`
- `0x14000bf78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000b9d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000b9d5`
- `deviceassociation!DafCreateAssociationContext` at `0x14000b9a8`
- `deviceassociation!DafCreateAssociationContext` at `0x14000b9a8`

## pseudocode

```c
struct DAF_ASSOCIATION_HANDLE__ *__fastcall PrinterFinder::_TryCreateAssociationContext(
        const unsigned __int16 *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // eax
  int AssociationContext; // eax
  __int64 v5; // rbx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *Block; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  Block = 0;
  v3 = DafConcatenateWithDelimiter(a1, a1, a3, &Block);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)(unsigned int)v3,
      v7);
  v10 = 0;
  AssociationContext = DafCreateAssociationContext(Block, 0, 0, 0);
  if ( AssociationContext < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)(unsigned int)AssociationContext,
      (int)&v10);
  v5 = v10;
  free(Block);
  return (struct DAF_ASSOCIATION_HANDLE__ *)v5;
}

```

## disassembly

```asm
0x14000b968  push    rbx
0x14000b96a  sub     rsp, 30h
0x14000b96e  lea     r9, [rsp+38h+Block]
0x14000b973  mov     [rsp+38h+Block], 0
0x14000b97c  mov     rdx, rcx
0x14000b97f  call    DafConcatenateWithDelimiter
0x14000b984  test    eax, eax
0x14000b986  js      short loc_14000B9E4
0x14000b988  mov     rcx, [rsp+38h+Block]
0x14000b98d  lea     rax, [rsp+38h+arg_10]
0x14000b992  xor     r9d, r9d
0x14000b995  mov     qword ptr [rsp+38h+var_18], rax; int
0x14000b99a  xor     r8d, r8d
0x14000b99d  mov     [rsp+38h+arg_10], 0
0x14000b9a6  xor     edx, edx
0x14000b9a8  call    cs:__imp_DafCreateAssociationContext
0x14000b9ae  test    eax, eax
0x14000b9b0  jns     short loc_14000B9CB
0x14000b9b2  mov     rcx, [rsp+38h]; this
0x14000b9b7  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000b9be  mov     r9d, eax; char *
0x14000b9c1  mov     edx, 132h; void *
0x14000b9c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000b9cb  mov     rcx, [rsp+38h+Block]; Block
0x14000b9d0  mov     rbx, [rsp+38h+arg_10]
0x14000b9d5  call    cs:__imp_free
0x14000b9db  mov     rax, rbx
0x14000b9de  add     rsp, 30h
0x14000b9e2  pop     rbx
0x14000b9e3  retn
0x14000b9e4  mov     rcx, [rsp+38h]; this
0x14000b9e9  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000b9f0  mov     r9d, eax; char *
0x14000b9f3  mov     edx, 127h; void *
0x14000b9f8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
