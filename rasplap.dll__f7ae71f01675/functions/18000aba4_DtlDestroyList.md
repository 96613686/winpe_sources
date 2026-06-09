# DtlDestroyList

- ea: `0x18000aba4`
- end: `0x18000abf6`
- name: `DtlDestroyList`
- size: `82`
- prototype: `__int64 __fastcall(HGLOBAL hMem)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000929c`
- `0x180009588`
- `0x180009784`
- `0x18000aca4`

## callees

- `0x1800089c0`
- `0x18000aba4`
- `0x18000abfc`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000abe5`
- `KERNEL32!GlobalFree` at `0x18000abe5`

## pseudocode

```c
HGLOBAL __fastcall DtlDestroyList(_QWORD *hMem, void (__fastcall *a2)(void *))
{
  _QWORD *i; // rdx
  void *v5; // rdx
  HGLOBAL result; // rax

  if ( hMem )
  {
    for ( i = (_QWORD *)*hMem; i; i = (_QWORD *)*hMem )
    {
      DtlRemoveNode((__int64)hMem, i);
      if ( a2 )
        a2(v5);
      else
        Free0(v5);
    }
    return GlobalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000aba4  test    rcx, rcx
0x18000aba7  jz      short locret_18000ABF5
0x18000aba9  mov     [rsp+arg_0], rbx
0x18000abae  push    rdi
0x18000abaf  sub     rsp, 20h
0x18000abb3  mov     rdi, rdx
0x18000abb6  mov     rbx, rcx
0x18000abb9  mov     rdx, [rcx]
0x18000abbc  jmp     short loc_18000ABDD
0x18000abbe  call    DtlRemoveNode
0x18000abc3  mov     rcx, rdx
0x18000abc6  test    rdi, rdi
0x18000abc9  jz      short loc_18000ABD5
0x18000abcb  mov     rax, rdi
0x18000abce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abd3  jmp     short loc_18000ABDA
0x18000abd5  call    Free0
0x18000abda  mov     rdx, [rbx]
0x18000abdd  mov     rcx, rbx; hMem
0x18000abe0  test    rdx, rdx
0x18000abe3  jnz     short loc_18000ABBE
0x18000abe5  call    cs:__imp_GlobalFree
0x18000abeb  mov     rbx, [rsp+28h+arg_0]
0x18000abf0  add     rsp, 20h
0x18000abf4  pop     rdi
0x18000abf5  retn
```
