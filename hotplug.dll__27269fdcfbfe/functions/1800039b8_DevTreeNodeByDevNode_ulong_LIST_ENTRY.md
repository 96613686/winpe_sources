# DevTreeNodeByDevNode(ulong,_LIST_ENTRY *)

- ea: `0x1800039b8`
- end: `0x180003a0e`
- name: `?DevTreeNodeByDevNode@@YAPEAU_DeviceTreeNode@@KPEAU_LIST_ENTRY@@@Z`
- size: `86`
- prototype: `struct _DeviceTreeNode *__fastcall(unsigned int, struct _LIST_ENTRY *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003714`
- `0x1800039b8`
- `0x180004114`
- `0x180006514`

## callees

- `0x1800039b8`

## pseudocode

```c
struct _DeviceTreeNode *__fastcall DevTreeNodeByDevNode(unsigned int a1, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *i; // rbx
  struct _LIST_ENTRY *v5; // rdx
  struct _DeviceTreeNode *result; // rax

  if ( a1 )
  {
    for ( i = a2->Flink; i != a2; i = i->Flink )
    {
      if ( a1 == LODWORD(i[6].Flink) )
        return (struct _DeviceTreeNode *)i;
      v5 = i + 1;
      if ( v5->Flink != v5 )
      {
        result = DevTreeNodeByDevNode(a1, v5);
        if ( result )
          return result;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800039b8  mov     [rsp+arg_0], rbx
0x1800039bd  mov     [rsp+arg_8], rsi
0x1800039c2  push    rdi
0x1800039c3  sub     rsp, 20h
0x1800039c7  mov     rdi, rdx
0x1800039ca  mov     esi, ecx
0x1800039cc  test    ecx, ecx
0x1800039ce  jz      short loc_1800039F7
0x1800039d0  mov     rbx, [rdx]
0x1800039d3  jmp     short loc_1800039F2
0x1800039d5  cmp     esi, [rbx+60h]
0x1800039d8  jz      short loc_180003A09
0x1800039da  lea     rdx, [rbx+10h]; struct _LIST_ENTRY *
0x1800039de  cmp     [rdx], rdx
0x1800039e1  jz      short loc_1800039EF
0x1800039e3  mov     ecx, esi; unsigned int
0x1800039e5  call    ?DevTreeNodeByDevNode@@YAPEAU_DeviceTreeNode@@KPEAU_LIST_ENTRY@@@Z; DevTreeNodeByDevNode(ulong,_LIST_ENTRY *)
0x1800039ea  test    rax, rax
0x1800039ed  jnz     short loc_1800039F9
0x1800039ef  mov     rbx, [rbx]
0x1800039f2  cmp     rbx, rdi
0x1800039f5  jnz     short loc_1800039D5
0x1800039f7  xor     eax, eax
0x1800039f9  mov     rbx, [rsp+28h+arg_0]
0x1800039fe  mov     rsi, [rsp+28h+arg_8]
0x180003a03  add     rsp, 20h
0x180003a07  pop     rdi
0x180003a08  retn
0x180003a09  mov     rax, rbx
0x180003a0c  jmp     short loc_1800039F9
```
