# std::list<PIXEventsThreadInfo,std::allocator<PIXEventsThreadInfo>>::_List_node_remove_op::~_List_node_remove_op(void)

- ea: `0x180008240`
- end: `0x18000826c`
- name: `??1_List_node_remove_op@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800119f0`

## callees

- `0x180006e2c`
- `0x180008240`

## pseudocode

```c
void __fastcall std::list<PIXEventsThreadInfo>::_List_node_remove_op::~_List_node_remove_op(__int64 a1)
{
  _QWORD *v1; // rcx
  _QWORD *v2; // rbx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
  {
    do
    {
      v2 = (_QWORD *)*v1;
      std::_Deallocate<16>(v1, 0x28u);
      v1 = v2;
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x180008240  push    rbx
0x180008242  sub     rsp, 20h
0x180008246  mov     rcx, [rcx+8]
0x18000824a  test    rcx, rcx
0x18000824d  jnz     short loc_180008255
0x18000824f  add     rsp, 20h
0x180008253  pop     rbx
0x180008254  retn
0x180008255  mov     rbx, [rcx]
0x180008258  mov     edx, 28h ; '('
0x18000825d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008262  mov     rcx, rbx
0x180008265  test    rbx, rbx
0x180008268  jnz     short loc_180008255
0x18000826a  jmp     short loc_18000824F
```
