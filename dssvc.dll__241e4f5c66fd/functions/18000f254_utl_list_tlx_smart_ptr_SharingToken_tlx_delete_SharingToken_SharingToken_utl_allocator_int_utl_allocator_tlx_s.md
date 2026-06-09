# utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)

- ea: `0x18000f254`
- end: `0x18000f2a9`
- name: `?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000d68c`
- `0x180012194`
- `0x1800134f4`
- `0x18001686c`
- `0x180017318`
- `0x180017518`

## callees

- `0x180002bac`
- `0x18000f120`
- `0x18000f254`

## pseudocode

```c
void __fastcall utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(
        __int64 a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rdx
  __int64 v4; // rax
  utl::_RefCountBase *v5; // rcx

  while ( 1 )
  {
    v2 = *(__int64 **)a1;
    if ( *(_QWORD *)a1 == a1 )
      break;
    v3 = (__int64 *)v2[1];
    v4 = *v2;
    *v3 = *v2;
    *(_QWORD *)(v4 + 8) = v3;
    v5 = (utl::_RefCountBase *)v2[3];
    if ( v5 )
      utl::_RefCountBase::_DecStrong(v5);
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  }
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18000f254  mov     [rsp+arg_0], rbx
0x18000f259  push    rdi
0x18000f25a  sub     rsp, 20h
0x18000f25e  mov     rdi, rcx
0x18000f261  mov     rbx, [rdi]
0x18000f264  cmp     rbx, rdi
0x18000f267  jz      short loc_18000F296
0x18000f269  mov     rdx, [rbx+8]
0x18000f26d  mov     rax, [rbx]
0x18000f270  mov     [rdx], rax
0x18000f273  mov     [rax+8], rdx
0x18000f277  mov     rcx, [rbx+18h]; this
0x18000f27b  test    rcx, rcx
0x18000f27e  jz      short loc_18000F285
0x18000f280  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000f285  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f28c  mov     rcx, rbx; void *
0x18000f28f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f294  jmp     short loc_18000F261
0x18000f296  mov     rbx, [rsp+28h+arg_0]
0x18000f29b  mov     qword ptr [rdi+10h], 0
0x18000f2a3  add     rsp, 20h
0x18000f2a7  pop     rdi
0x18000f2a8  retn
```
