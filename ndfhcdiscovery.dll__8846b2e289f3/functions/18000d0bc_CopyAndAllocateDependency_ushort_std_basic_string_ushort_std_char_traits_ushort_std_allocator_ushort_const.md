# CopyAndAllocateDependency(ushort * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *)

- ea: `0x18000d0bc`
- end: `0x18000d12b`
- name: `?CopyAndAllocateDependency@@YAJPEAPEAGPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b7a0`

## callees

- `0x18000d0bc`
- `0x18001065c`
- `0x180010684`
- `0x180010a6c`

## pseudocode

```c
__int64 __fastcall CopyAndAllocateDependency(unsigned __int16 **a1, __int64 a2)
{
  unsigned __int16 *v3; // rbx
  unsigned __int64 v4; // rcx
  int v5; // eax
  void *v6; // rdx
  const unsigned __int16 *v7; // r8
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v11; // [rsp+48h] [rbp+10h] BYREF

  if ( *(_QWORD *)(a2 + 24) < 8u )
    v3 = (unsigned __int16 *)a2;
  else
    v3 = *(unsigned __int16 **)a2;
  v4 = *(_QWORD *)(a2 + 16);
  v11 = 0;
  if ( v4 < 0xFFFFFFFF )
    ++v4;
  v5 = ULongLongToULong(v4, &v11);
  if ( v5 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v6, (unsigned int)v7, (const char *)(unsigned int)v5, v9);
  return UtilAssembleStringsWithAlloc(a1, v11, v7, v3);
}

```

## disassembly

```asm
0x18000d0bc  mov     [rsp+arg_0], rbx
0x18000d0c1  push    rdi
0x18000d0c2  sub     rsp, 30h
0x18000d0c6  cmp     qword ptr [rdx+18h], 8
0x18000d0cb  mov     rdi, rcx
0x18000d0ce  jb      short loc_18000D0D5
0x18000d0d0  mov     rbx, [rdx]
0x18000d0d3  jmp     short loc_18000D0D8
0x18000d0d5  mov     rbx, rdx
0x18000d0d8  mov     rcx, [rdx+10h]
0x18000d0dc  mov     edx, 0FFFFFFFFh
0x18000d0e1  cmp     rcx, rdx
0x18000d0e4  mov     [rsp+38h+arg_8], 0
0x18000d0ec  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x18000d0f1  lea     rax, [rcx+1]
0x18000d0f5  cmovb   rcx, rax; unsigned __int64
0x18000d0f9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000d0fe  test    eax, eax
0x18000d100  js      short loc_18000D11D
0x18000d102  mov     edx, [rsp+38h+arg_8]; unsigned int
0x18000d106  mov     r9, rbx; unsigned __int16 *
0x18000d109  mov     rcx, rdi; unsigned __int16 **
0x18000d10c  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000d111  mov     rbx, [rsp+38h+arg_0]
0x18000d116  add     rsp, 30h
0x18000d11a  pop     rdi
0x18000d11b  retn
0x18000d11d  mov     rcx, [rsp+38h]; this
0x18000d122  mov     r9d, eax; char *
0x18000d125  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
