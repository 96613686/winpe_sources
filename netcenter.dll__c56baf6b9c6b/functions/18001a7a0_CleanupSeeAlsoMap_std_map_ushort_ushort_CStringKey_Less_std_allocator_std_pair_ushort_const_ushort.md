# CleanupSeeAlsoMap(std::map<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>> *)

- ea: `0x18001a7a0`
- end: `0x18001a85b`
- name: `?CleanupSeeAlsoMap@@YAXPEAV?$map@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@@std@@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800144f0`

## callees

- `0x1800076a8`
- `0x18001a7a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7d7`

## pseudocode

```c
void __fastcall CleanupSeeAlsoMap(__int64 **a1)
{
  __int64 *v2; // rbx
  __int64 **v3; // rsi
  __int64 **v4; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx

  if ( a1 )
  {
    v2 = (__int64 *)**a1;
    while ( 1 )
    {
      v3 = (__int64 **)*a1;
      if ( v2 == *a1 )
        break;
      CoTaskMemFree((LPVOID)v2[4]);
      CoTaskMemFree((LPVOID)v2[5]);
      v4 = (__int64 **)v2[2];
      if ( *((_BYTE *)v4 + 25) )
      {
        for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 25) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v2 = i;
        v2 = i;
      }
      else
      {
        v2 = (__int64 *)v2[2];
        for ( j = *v4; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v2 = j;
      }
    }
    if ( a1[1] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,void *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short * const,void *>,void *>>>(
        a1,
        a1,
        v3[1]);
      v3[1] = (__int64 *)v3;
      *v3 = (__int64 *)v3;
      v3[2] = (__int64 *)v3;
      a1[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x18001a7a0  test    rcx, rcx
0x18001a7a3  jz      locret_18001A85A
0x18001a7a9  mov     [rsp+arg_0], rbx
0x18001a7ae  mov     [rsp+arg_8], rsi
0x18001a7b3  push    rdi
0x18001a7b4  sub     rsp, 20h
0x18001a7b8  mov     rbx, [rcx]
0x18001a7bb  mov     rdi, rcx
0x18001a7be  mov     rbx, [rbx]
0x18001a7c1  mov     rsi, [rdi]
0x18001a7c4  cmp     rbx, rsi
0x18001a7c7  jz      short loc_18001A822
0x18001a7c9  mov     rcx, [rbx+20h]; pv
0x18001a7cd  call    cs:__imp_CoTaskMemFree
0x18001a7d3  mov     rcx, [rbx+28h]; pv
0x18001a7d7  call    cs:__imp_CoTaskMemFree
0x18001a7dd  mov     rcx, [rbx+10h]
0x18001a7e1  cmp     byte ptr [rcx+19h], 0
0x18001a7e5  jz      short loc_18001A805
0x18001a7e7  mov     rax, [rbx+8]
0x18001a7eb  jmp     short loc_18001A7FA
0x18001a7ed  cmp     rbx, [rax+10h]
0x18001a7f1  jnz     short loc_18001A800
0x18001a7f3  mov     rbx, rax
0x18001a7f6  mov     rax, [rax+8]
0x18001a7fa  cmp     byte ptr [rax+19h], 0
0x18001a7fe  jz      short loc_18001A7ED
0x18001a800  mov     rbx, rax
0x18001a803  jmp     short loc_18001A7C1
0x18001a805  mov     rbx, rcx
0x18001a808  mov     rcx, [rcx]
0x18001a80b  cmp     byte ptr [rcx+19h], 0
0x18001a80f  jnz     short loc_18001A7C1
0x18001a811  mov     rax, [rcx]
0x18001a814  mov     rbx, rcx
0x18001a817  mov     rcx, rax
0x18001a81a  cmp     byte ptr [rax+19h], 0
0x18001a81e  jz      short loc_18001A811
0x18001a820  jmp     short loc_18001A7C1
0x18001a822  cmp     qword ptr [rdi+8], 0
0x18001a827  jbe     short loc_18001A84B
0x18001a829  mov     r8, [rsi+8]
0x18001a82d  mov     rdx, rdi
0x18001a830  mov     rcx, rdi
0x18001a833  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAGPEAX@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAX@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAGPEAX@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAGPEAX@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,void *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort * const,void *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort * const,void *>,void *>> &,std::_Tree_node<std::pair<ushort * const,void *>,void *> *)
0x18001a838  mov     [rsi+8], rsi
0x18001a83c  mov     [rsi], rsi
0x18001a83f  mov     [rsi+10h], rsi
0x18001a843  mov     qword ptr [rdi+8], 0
0x18001a84b  mov     rbx, [rsp+28h+arg_0]
0x18001a850  mov     rsi, [rsp+28h+arg_8]
0x18001a855  add     rsp, 20h
0x18001a859  pop     rdi
0x18001a85a  retn
```
