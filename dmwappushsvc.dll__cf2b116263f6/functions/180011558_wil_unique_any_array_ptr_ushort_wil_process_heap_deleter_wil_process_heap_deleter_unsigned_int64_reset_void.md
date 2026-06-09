# wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)

- ea: `0x180011558`
- end: `0x1800115b4`
- name: `?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ`
- size: `92`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011340`

## callees

- `0x180008794`
- `0x180011558`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(
        __int64 a1,
        void *a2)
{
  wil::details *v2; // rbx
  wil::details *v4; // rsi

  v2 = *(wil::details **)a1;
  if ( *(_QWORD *)a1 )
  {
    v4 = (wil::details *)((char *)v2 + 8 * *(_QWORD *)(a1 + 8));
    while ( v2 != v4 )
    {
      wil::details::FreeProcessHeap(*(wil::details **)v2, a2);
      v2 = (wil::details *)((char *)v2 + 8);
    }
    wil::details::FreeProcessHeap(*(wil::details **)a1, a2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180011558  mov     [rsp+arg_0], rbx
0x18001155d  mov     [rsp+arg_8], rsi
0x180011562  push    rdi
0x180011563  sub     rsp, 20h
0x180011567  mov     rbx, [rcx]
0x18001156a  mov     rdi, rcx
0x18001156d  test    rbx, rbx
0x180011570  jz      short loc_1800115A4
0x180011572  mov     rax, [rcx+8]
0x180011576  lea     rsi, [rbx+rax*8]
0x18001157a  jmp     short loc_180011588
0x18001157c  mov     rcx, [rbx]; this
0x18001157f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180011584  add     rbx, 8
0x180011588  cmp     rbx, rsi
0x18001158b  jnz     short loc_18001157C
0x18001158d  mov     rcx, [rdi]; this
0x180011590  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180011595  mov     qword ptr [rdi], 0
0x18001159c  mov     qword ptr [rdi+8], 0
0x1800115a4  mov     rbx, [rsp+28h+arg_0]
0x1800115a9  mov     rsi, [rsp+28h+arg_8]
0x1800115ae  add     rsp, 20h
0x1800115b2  pop     rdi
0x1800115b3  retn
```
