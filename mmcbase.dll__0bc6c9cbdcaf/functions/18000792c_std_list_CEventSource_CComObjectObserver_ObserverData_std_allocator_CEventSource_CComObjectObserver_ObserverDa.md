# std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::clear(void)

- ea: `0x18000792c`
- end: `0x180007972`
- name: `?clear@?$list@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@QEAAXXZ`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005590`
- `0x180007908`

## callees

- `0x18000792c`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180007959`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180007959`

## pseudocode

```c
void __fastcall std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::clear(
        __int64 a1)
{
  _QWORD *v1; // rax
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v1 = *(_QWORD **)a1;
  v3 = **(_QWORD ***)a1;
  *v1 = v1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v3 != *(_QWORD **)a1 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
}

```

## disassembly

```asm
0x18000792c  mov     [rsp+arg_0], rbx
0x180007931  push    rdi
0x180007932  sub     rsp, 20h
0x180007936  mov     rax, [rcx]
0x180007939  mov     rdi, rcx
0x18000793c  mov     rcx, [rax]
0x18000793f  mov     [rax], rax
0x180007942  mov     rax, [rdi]
0x180007945  mov     [rax+8], rax
0x180007949  mov     qword ptr [rdi+8], 0
0x180007951  cmp     rcx, [rdi]
0x180007954  jz      short loc_180007967
0x180007956  mov     rbx, [rcx]
0x180007959  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000795f  mov     rcx, rbx
0x180007962  cmp     rbx, [rdi]
0x180007965  jnz     short loc_180007956
0x180007967  mov     rbx, [rsp+28h+arg_0]
0x18000796c  add     rsp, 20h
0x180007970  pop     rdi
0x180007971  retn
```
