# std::_Uninitialized_move<BitsSnapshot::Job *,std::allocator<BitsSnapshot::Job>>(BitsSnapshot::Job * const,BitsSnapshot::Job * const,BitsSnapshot::Job *,std::allocator<BitsSnapshot::Job> &)

- ea: `0x180011820`
- end: `0x180011873`
- name: `??$_Uninitialized_move@PEAUJob@BitsSnapshot@@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@YAPEAUJob@BitsSnapshot@@QEAU12@0PEAU12@AEAV?$allocator@UJob@BitsSnapshot@@@0@@Z`
- size: `83`
- prototype: `BitsSnapshot::Job *__fastcall(__int64, __int64, BitsSnapshot::Job *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001167c`

## callees

- `0x1800114c0`
- `0x180011820`
- `0x1800118c4`

## pseudocode

```c
BitsSnapshot::Job *__fastcall std::_Uninitialized_move<BitsSnapshot::Job *>(
        __int64 a1,
        __int64 a2,
        BitsSnapshot::Job *a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 104 )
  {
    std::_Default_allocator_traits<std::allocator<BitsSnapshot::Job>>::construct<BitsSnapshot::Job,BitsSnapshot::Job>(
      a1,
      a3,
      i);
    a3 = (BitsSnapshot::Job *)((char *)a3 + 104);
  }
  std::_Destroy_range<std::allocator<BitsSnapshot::Job>>(a3);
  return a3;
}

```

## disassembly

```asm
0x180011820  mov     [rsp+arg_0], rbx
0x180011825  mov     [rsp+arg_8], rsi
0x18001182a  push    rdi
0x18001182b  sub     rsp, 20h
0x18001182f  mov     rbx, r8
0x180011832  mov     rsi, rdx
0x180011835  mov     rdi, rcx
0x180011838  cmp     rcx, rdx
0x18001183b  jz      short loc_180011855
0x18001183d  mov     r8, rdi
0x180011840  mov     rdx, rbx
0x180011843  call    ??$construct@UJob@BitsSnapshot@@U12@@?$_Default_allocator_traits@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@SAXAEAV?$allocator@UJob@BitsSnapshot@@@1@QEAUJob@BitsSnapshot@@$$QEAU34@@Z; std::_Default_allocator_traits<std::allocator<BitsSnapshot::Job>>::construct<BitsSnapshot::Job,BitsSnapshot::Job>(std::allocator<BitsSnapshot::Job> &,BitsSnapshot::Job * const,BitsSnapshot::Job &&)
0x180011848  add     rbx, 68h ; 'h'
0x18001184c  add     rdi, 68h ; 'h'
0x180011850  cmp     rdi, rsi
0x180011853  jnz     short loc_18001183D
0x180011855  mov     rdx, rbx
0x180011858  mov     rcx, rbx; this
0x18001185b  call    ??$_Destroy_range@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@YAXPEAUJob@BitsSnapshot@@QEAU12@AEAV?$allocator@UJob@BitsSnapshot@@@0@@Z; std::_Destroy_range<std::allocator<BitsSnapshot::Job>>(BitsSnapshot::Job *,BitsSnapshot::Job * const,std::allocator<BitsSnapshot::Job> &)
0x180011860  mov     rsi, [rsp+28h+arg_8]
0x180011865  mov     rax, rbx
0x180011868  mov     rbx, [rsp+28h+arg_0]
0x18001186d  add     rsp, 20h
0x180011871  pop     rdi
0x180011872  retn
```
