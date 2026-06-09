# Common::CreateCacheMapIfNeeded(void)

- ea: `0x180009a9c`
- end: `0x180009b40`
- name: `?CreateCacheMapIfNeeded@Common@@YAJXZ`
- size: `164`
- prototype: `__int64 __fastcall(Common *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x1800058d0`
- `0x180009a9c`
- `0x180009c4c`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180009afe`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180009afe`

## string_xrefs

- `0x180009b18`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::CreateCacheMapIfNeeded(Common *this)
{
  PRTL_AVL_TABLE v1; // rbx
  int TableContext; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PRTL_AVL_TABLE Table; // [rsp+40h] [rbp+8h] BYREF

  if ( ::Table )
    return 0;
  Table = 0;
  Common::GlobalHeap::Alloc(0x78u, (void **)&Table);
  v1 = Table;
  if ( Table )
  {
    Table[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    v1[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    RtlInitializeGenericTableAvl(
      v1,
      (PRTL_AVL_COMPARE_ROUTINE)Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapFree,
      0);
    ::Table = v1;
    return 0;
  }
  ::Table = 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)0x8007000ELL,
    TableContext);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180009a9c  push    rbx
0x180009a9e  sub     rsp, 30h
0x180009aa2  cmp     cs:Table, 0
0x180009aaa  jnz     short loc_180009B0B
0x180009aac  lea     rdx, [rsp+38h+Table]; void **
0x180009ab1  mov     [rsp+38h+Table], 0
0x180009aba  mov     ecx, 78h ; 'x'; unsigned __int64
0x180009abf  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180009ac4  mov     rbx, [rsp+38h+Table]
0x180009ac9  test    rbx, rbx
0x180009acc  jz      short loc_180009B13
0x180009ace  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x180009ad5  mov     qword ptr [rsp+38h+TableContext], 0; TableContext
0x180009ade  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEBG@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180009ae5  mov     [rbx+68h], rax
0x180009ae9  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180009af0  mov     [rbx+70h], rax
0x180009af4  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180009afb  mov     rcx, rbx; Table
0x180009afe  call    cs:__imp_RtlInitializeGenericTableAvl
0x180009b04  mov     cs:Table, rbx
0x180009b0b  xor     eax, eax
0x180009b0d  add     rsp, 30h
0x180009b11  pop     rbx
0x180009b12  retn
0x180009b13  mov     rcx, [rsp+38h]; this
0x180009b18  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180009b1f  mov     ebx, 8007000Eh
0x180009b24  mov     cs:Table, 0
0x180009b2f  mov     r9d, ebx; char *
0x180009b32  mov     edx, 3Bh ; ';'; void *
0x180009b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b3c  mov     eax, ebx
0x180009b3e  jmp     short loc_180009B0D
```
