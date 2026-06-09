# std::list<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::~list<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>(void)

- ea: `0x180018310`
- end: `0x180018375`
- name: `??1?$list@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018420`
- `0x18001dcd3`

## callees

- `0x1800014d0`
- `0x180018310`
- `0x1800184f8`

## pseudocode

```c
void __fastcall std::list<std::pair<HardwareAddress const,VisibleDock>>::~list<std::pair<HardwareAddress const,VisibleDock>>(
        __int64 a1)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      VisibleDock::~VisibleDock((VisibleDock *)(v2 + 4));
      operator delete(v2);
      v3 = *(_QWORD **)a1;
      v2 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x180018310  mov     [rsp+arg_0], rbx
0x180018315  mov     [rsp+arg_8], rsi
0x18001831a  push    rdi
0x18001831b  sub     rsp, 20h
0x18001831f  mov     rax, [rcx]
0x180018322  mov     rdi, rcx
0x180018325  mov     rsi, [rax]
0x180018328  mov     [rax], rax
0x18001832b  mov     rax, [rcx]
0x18001832e  mov     [rax+8], rax
0x180018332  mov     qword ptr [rcx+8], 0
0x18001833a  mov     rcx, [rcx]
0x18001833d  cmp     rsi, rcx
0x180018340  jz      short loc_180018361
0x180018342  mov     rbx, [rsi]
0x180018345  lea     rcx, [rsi+20h]; this
0x180018349  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x18001834e  mov     rcx, rsi; Block
0x180018351  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018356  mov     rcx, [rdi]; Block
0x180018359  mov     rsi, rbx
0x18001835c  cmp     rbx, rcx
0x18001835f  jnz     short loc_180018342
0x180018361  mov     rbx, [rsp+28h+arg_0]
0x180018366  mov     rsi, [rsp+28h+arg_8]
0x18001836b  add     rsp, 20h
0x18001836f  pop     rdi
0x180018370  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
