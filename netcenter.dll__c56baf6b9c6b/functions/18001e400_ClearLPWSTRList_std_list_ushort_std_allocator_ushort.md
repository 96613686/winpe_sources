# ClearLPWSTRList(std::list<ushort *,std::allocator<ushort *>> *)

- ea: `0x18001e400`
- end: `0x18001e458`
- name: `?ClearLPWSTRList@@YAXPEAV?$list@PEAGV?$allocator@PEAG@std@@@std@@@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fde8`

## callees

- `0x1800077a4`
- `0x18001e400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e421`

## pseudocode

```c
void __fastcall ClearLPWSTRList(__int64 **a1)
{
  __int64 *i; // rbx

  if ( a1 )
  {
    for ( i = *a1; ; CoTaskMemFree((LPVOID)i[2]) )
    {
      i = (__int64 *)*i;
      if ( i == *a1 )
        break;
    }
    if ( a1[1] )
    {
      std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(a1, *a1);
      **a1 = (__int64)*a1;
      (*a1)[1] = (__int64)*a1;
      a1[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x18001e400  test    rcx, rcx
0x18001e403  jz      short locret_18001E457
0x18001e405  mov     [rsp+arg_0], rbx
0x18001e40a  push    rdi
0x18001e40b  sub     rsp, 20h
0x18001e40f  mov     rbx, [rcx]
0x18001e412  mov     rdi, rcx
0x18001e415  mov     rbx, [rbx]
0x18001e418  cmp     rbx, [rdi]
0x18001e41b  jz      short loc_18001E429
0x18001e41d  mov     rcx, [rbx+10h]; pv
0x18001e421  call    cs:__imp_CoTaskMemFree
0x18001e427  jmp     short loc_18001E415
0x18001e429  cmp     qword ptr [rdi+8], 0
0x18001e42e  jbe     short loc_18001E44D
0x18001e430  mov     rdx, [rdi]
0x18001e433  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x18001e438  mov     rax, [rdi]
0x18001e43b  mov     [rax], rax
0x18001e43e  mov     rax, [rdi]
0x18001e441  mov     [rax+8], rax
0x18001e445  mov     qword ptr [rdi+8], 0
0x18001e44d  mov     rbx, [rsp+28h+arg_0]
0x18001e452  add     rsp, 20h
0x18001e456  pop     rdi
0x18001e457  retn
```
