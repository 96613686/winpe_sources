# std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003,std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>>::~vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003,std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>>(void)

- ea: `0x18000c8d0`
- end: `0x18000c90b`
- name: `??1?$vector@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@V?$allocator@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@@std@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800140d7`
- `0x1800140fd`
- `0x1800142e4`
- `0x18001438e`

## callees

- `0x18000c8d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c8e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c8e1`

## pseudocode

```c
void __fastcall std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>::~vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000c8d0  push    rbx
0x18000c8d2  sub     rsp, 20h
0x18000c8d6  mov     rbx, rcx
0x18000c8d9  mov     rcx, [rcx]
0x18000c8dc  test    rcx, rcx
0x18000c8df  jz      short loc_18000C904
0x18000c8e1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c8e8  nop     dword ptr [rax+rax+00h]
0x18000c8ed  mov     qword ptr [rbx], 0
0x18000c8f4  mov     qword ptr [rbx+8], 0
0x18000c8fc  mov     qword ptr [rbx+10h], 0
0x18000c904  add     rsp, 20h
0x18000c908  pop     rbx
0x18000c909  retn
```
