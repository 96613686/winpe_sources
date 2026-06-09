# WfpHashtableDestroy

- ea: `0x18000f89c`
- end: `0x18000f958`
- name: `WfpHashtableDestroy`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b8c0`
- `0x18001e380`
- `0x180049f38`

## callees

- `0x18000f89c`
- `0x18004b010`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18000f93b`
- `ntdll!RtlDeleteHashTable` at `0x18000f93b`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f905`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f905`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000f8cf`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000f8cf`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000f8e7`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000f8e7`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000f92c`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000f92c`

## pseudocode

```c
__int64 __fastcall WfpHashtableDestroy(__int64 a1, void (__fastcall *a2)(__int64 *))
{
  __int64 v4; // rax
  _OWORD v6[3]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v7; // [rsp+60h] [rbp+10h] BYREF

  v7 = 0;
  memset(v6, 0, sizeof(v6));
  RtlInitEnumerationHashTable(a1, (char *)v6 + 8);
  while ( 1 )
  {
    v4 = RtlEnumerateEntryHashTable(a1, (char *)v6 + 8);
    v7 = v4;
    if ( !v4 )
      break;
    RtlRemoveEntryHashTable(a1, v4, 0);
    if ( a2 )
      a2(&v7);
  }
  RtlEndEnumerationHashTable(a1, (char *)v6 + 8);
  return RtlDeleteHashTable(a1);
}

```

## disassembly

```asm
0x18000f89c  mov     [rsp-8+arg_8], rbx
0x18000f8a1  mov     [rsp-8+arg_10], rdi
0x18000f8a6  push    rbp
0x18000f8a7  mov     rbp, rsp
0x18000f8aa  sub     rsp, 50h
0x18000f8ae  xorps   xmm0, xmm0
0x18000f8b1  mov     [rbp+arg_0], 0
0x18000f8b9  mov     rdi, rdx
0x18000f8bc  mov     rbx, rcx
0x18000f8bf  lea     rdx, [rbp+var_28]
0x18000f8c3  movups  xmmword ptr [rbp-30h], xmm0
0x18000f8c7  movups  [rbp+var_20], xmm0
0x18000f8cb  movups  [rbp+var_10], xmm0
0x18000f8cf  call    cs:__imp_RtlInitEnumerationHashTable
0x18000f8d6  nop     dword ptr [rax+rax+00h]
0x18000f8db  mov     [rbp+var_30], rbx
0x18000f8df  mov     rcx, [rbp+var_30]
0x18000f8e3  lea     rdx, [rbp+var_28]
0x18000f8e7  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000f8ee  nop     dword ptr [rax+rax+00h]
0x18000f8f3  mov     [rbp+arg_0], rax
0x18000f8f7  test    rax, rax
0x18000f8fa  jz      short loc_18000F924
0x18000f8fc  xor     r8d, r8d
0x18000f8ff  mov     rdx, rax
0x18000f902  mov     rcx, rbx
0x18000f905  call    cs:__imp_RtlRemoveEntryHashTable
0x18000f90c  nop     dword ptr [rax+rax+00h]
0x18000f911  test    rdi, rdi
0x18000f914  jz      short loc_18000F8DF
0x18000f916  lea     rcx, [rbp+arg_0]
0x18000f91a  mov     rax, rdi
0x18000f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f922  jmp     short loc_18000F8DF
0x18000f924  mov     rcx, [rbp+var_30]
0x18000f928  lea     rdx, [rbp+var_28]
0x18000f92c  call    cs:__imp_RtlEndEnumerationHashTable
0x18000f933  nop     dword ptr [rax+rax+00h]
0x18000f938  mov     rcx, rbx
0x18000f93b  call    cs:__imp_RtlDeleteHashTable
0x18000f942  nop     dword ptr [rax+rax+00h]
0x18000f947  mov     rbx, [rsp+50h+arg_8]
0x18000f94c  mov     rdi, [rsp+50h+arg_10]
0x18000f951  add     rsp, 50h
0x18000f955  pop     rbp
0x18000f956  retn
```
