# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180003618`
- end: `0x180003650`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: ``
- caller_count: `61`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003658`
- `0x180003b14`
- `0x180007f10`
- `0x180008dcc`
- `0x180008f6c`
- `0x180010348`
- `0x180010494`
- `0x1800105fc`
- `0x180010658`
- `0x1800106b8`
- `0x180010800`
- `0x1800108b0`
- `0x18001097c`
- `0x180010a60`
- `0x180010b1c`
- `0x180011c7c`
- `0x180011ca0`
- `0x180011cc4`
- `0x180011ce8`
- `0x180011d5c`
- `0x180011d8c`
- `0x180011dbc`
- `0x180011e34`
- `0x180011f50`
- `0x180012154`
- `0x180012204`
- `0x180012228`
- `0x180012264`
- `0x1800188e8`
- `0x18001892c`
- `0x180018a68`
- `0x180018c9c`
- `0x180019094`
- `0x1800190b8`
- `0x180019114`
- `0x180019168`
- `0x18001ad20`
- `0x18001c854`
- `0x18001c8b4`
- `0x18001c914`
- `0x18001cc0c`
- `0x18001cd24`
- `0x18001d33c`
- `0x18001d360`
- `0x18001d384`
- `0x18001d3a8`
- `0x18001d3d8`
- `0x18001d408`
- `0x18001d4ec`
- `0x18001d658`

## callees

- `0x180001824`
- `0x180003618`
- `0x18000742c`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, &v3);
    a1 = v2;
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180003618  mov     rax, rsp
0x18000361b  mov     [rax+10h], rdx
0x18000361f  mov     [rax+8], rcx
0x180003623  sub     rsp, 28h
0x180003627  cmp     rdx, 1000h
0x18000362e  jb      short loc_180003647
0x180003630  lea     rdx, [rax+10h]; unsigned __int64 *
0x180003634  lea     rcx, [rax+8]; void **
0x180003638  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000363d  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x180003642  mov     rcx, [rsp+28h+arg_0]; void *
0x180003647  add     rsp, 28h
0x18000364b  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
