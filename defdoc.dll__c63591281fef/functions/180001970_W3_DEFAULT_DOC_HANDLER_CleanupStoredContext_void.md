# W3_DEFAULT_DOC_HANDLER::CleanupStoredContext(void)

- ea: `0x180001970`
- end: `0x1800019ad`
- name: `?CleanupStoredContext@W3_DEFAULT_DOC_HANDLER@@UEAAXXZ`
- size: `61`
- prototype: `void __fastcall(W3_DEFAULT_DOC_HANDLER *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001970`
- `0x180004010`

## pseudocode

```c
void __fastcall W3_DEFAULT_DOC_HANDLER::CleanupStoredContext(W3_DEFAULT_DOC_HANDLER *this)
{
  __int64 v2; // rcx

  if ( this )
  {
    *(_QWORD *)this = &W3_DEFAULT_DOC_HANDLER::`vftable';
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 256LL))(v2);
      *((_QWORD *)this + 1) = 0;
    }
  }
}

```

## disassembly

```asm
0x180001970  test    rcx, rcx
0x180001973  jz      short locret_1800019AC
0x180001975  push    rbx
0x180001976  sub     rsp, 20h
0x18000197a  lea     rax, ??_7W3_DEFAULT_DOC_HANDLER@@6B@; const W3_DEFAULT_DOC_HANDLER::`vftable'
0x180001981  mov     rbx, rcx
0x180001984  mov     [rcx], rax
0x180001987  mov     rcx, [rcx+8]
0x18000198b  test    rcx, rcx
0x18000198e  jz      short loc_1800019A7
0x180001990  mov     rax, [rcx]
0x180001993  mov     rax, [rax+100h]
0x18000199a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000199f  mov     qword ptr [rbx+8], 0
0x1800019a7  add     rsp, 20h
0x1800019ab  pop     rbx
0x1800019ac  retn
```
