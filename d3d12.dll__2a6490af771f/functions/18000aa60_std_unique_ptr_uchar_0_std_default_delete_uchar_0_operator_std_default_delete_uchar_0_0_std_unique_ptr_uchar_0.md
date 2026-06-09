# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &&)

- ea: `0x18000aa60`
- end: `0x18000aa91`
- name: `??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000195c`
- `0x180001a60`

## callees

- `0x18000aa60`
- `0x18000b7e0`

## pseudocode

```c
void **__fastcall std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(
        void **a1,
        void **a2)
{
  void *v3; // rax
  void *v4; // rcx

  if ( a1 != a2 )
  {
    v3 = *a2;
    *a2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 )
      operator delete(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18000aa60  push    rbx
0x18000aa62  sub     rsp, 20h
0x18000aa66  mov     rbx, rcx
0x18000aa69  cmp     rcx, rdx
0x18000aa6c  jz      short loc_18000AA88
0x18000aa6e  mov     rax, [rdx]
0x18000aa71  mov     qword ptr [rdx], 0
0x18000aa78  mov     rcx, [rcx]; Block
0x18000aa7b  mov     [rbx], rax
0x18000aa7e  test    rcx, rcx
0x18000aa81  jz      short loc_18000AA88
0x18000aa83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa88  mov     rax, rbx
0x18000aa8b  add     rsp, 20h
0x18000aa8f  pop     rbx
0x18000aa90  retn
```
