# CleanUpAfterProcessSecurityContext

- ea: `0x1400014c0`
- end: `0x140001599`
- name: `CleanUpAfterProcessSecurityContext`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400049c8`

## callees

- `0x1400014c0`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall CleanUpAfterProcessSecurityContext(__int64 a1, __int64 a2)
{
  unsigned int i; // ebx
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 4); ++i )
    {
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL * i + 8) )
      {
        (*(void (**)(void))(gLsapSspiExtension + 8))();
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL * i + 8) = 0;
      }
    }
    (*(void (__fastcall **)(_QWORD))(gLsapSspiExtension + 8))(*(_QWORD *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  result = *(_QWORD *)(a2 + 32);
  if ( *(_QWORD *)(result + 8) )
  {
    (*(void (**)(void))(gLsapSspiExtension + 8))();
    result = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(result + 8) = 0;
  }
  if ( *(_QWORD *)(a2 + 24) )
  {
    result = (*(__int64 (**)(void))(gLsapSspiExtension + 8))();
    *(_QWORD *)(a2 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400014c0  mov     [rsp+arg_18], rbp
0x1400014c5  push    r14
0x1400014c7  sub     rsp, 20h
0x1400014cb  xor     r14d, r14d
0x1400014ce  mov     [rsp+28h+arg_10], rdi
0x1400014d3  mov     rbp, rdx
0x1400014d6  mov     rdi, rcx
0x1400014d9  cmp     [rcx+8], r14
0x1400014dd  jz      short loc_140001546
0x1400014df  mov     [rsp+28h+arg_0], rbx
0x1400014e4  mov     ebx, r14d
0x1400014e7  cmp     [rcx+4], ebx
0x1400014ea  jbe     short loc_140001529
0x1400014ec  mov     [rsp+28h+arg_8], rsi
0x1400014f1  mov     rax, [rdi+8]
0x1400014f5  mov     esi, ebx
0x1400014f7  add     rsi, rsi
0x1400014fa  mov     rcx, [rax+rsi*8+8]
0x1400014ff  test    rcx, rcx
0x140001502  jz      short loc_14000151D
0x140001504  mov     rax, cs:gLsapSspiExtension
0x14000150b  mov     rax, [rax+8]
0x14000150f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001514  mov     rax, [rdi+8]
0x140001518  mov     [rax+rsi*8+8], r14
0x14000151d  inc     ebx
0x14000151f  cmp     ebx, [rdi+4]
0x140001522  jb      short loc_1400014F1
0x140001524  mov     rsi, [rsp+28h+arg_8]
0x140001529  mov     rax, cs:gLsapSspiExtension
0x140001530  mov     rcx, [rdi+8]
0x140001534  mov     rax, [rax+8]
0x140001538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000153d  mov     rbx, [rsp+28h+arg_0]
0x140001542  mov     [rdi+8], r14
0x140001546  mov     rax, [rbp+20h]
0x14000154a  mov     rdi, [rsp+28h+arg_10]
0x14000154f  mov     rcx, [rax+8]
0x140001553  test    rcx, rcx
0x140001556  jz      short loc_140001570
0x140001558  mov     rax, cs:gLsapSspiExtension
0x14000155f  mov     rax, [rax+8]
0x140001563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001568  mov     rax, [rbp+20h]
0x14000156c  mov     [rax+8], r14
0x140001570  mov     rcx, [rbp+18h]
0x140001574  test    rcx, rcx
0x140001577  jz      short loc_14000158D
0x140001579  mov     rax, cs:gLsapSspiExtension
0x140001580  mov     rax, [rax+8]
0x140001584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001589  mov     [rbp+18h], r14
0x14000158d  mov     rbp, [rsp+28h+arg_18]
0x140001592  add     rsp, 20h
0x140001596  pop     r14
0x140001598  retn
```
