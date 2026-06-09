# RtlpPrintErrorInformation

- ea: `0x18014f3c4`
- end: `0x18014f7b8`
- name: `RtlpPrintErrorInformation`
- size: `1012`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180111dec`

## callees

- `0x180007060`
- `0x18014f3c4`

## string_xrefs

- `0x18014f5ab`: `heap_failure_commit_limit`

## pseudocode

```c
__int64 RtlpPrintErrorInformation()
{
  const char *v0; // rbx

  v0 = byte_180175FF3;
  if ( NtCurrentPeb()->Ldr )
    DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
  else
    DbgPrint("HEAP: ");
  DbgPrint("Heap error detected at %p (heap handle %p)\n", (const void *)qword_1801C50F8, (const void *)qword_1801C50F0);
  if ( dword_1801C50E8 > 12 )
  {
    if ( dword_1801C50E8 > 18 )
    {
      switch ( dword_1801C50E8 )
      {
        case 19:
          v0 = "heap_failure_null_heap";
          break;
        case 20:
          v0 = "heap_failure_allocation_limit";
          break;
        case 21:
          v0 = "heap_failure_commit_limit";
          break;
        case 22:
          v0 = "heap_failure_invalid_va_mgr_query";
          break;
        case 23:
          v0 = "heap_failure_segment_lfh_delay_free_corruption";
          break;
      }
    }
    else
    {
      switch ( dword_1801C50E8 )
      {
        case 18:
          v0 = "heap_failure_vs_subsegment_corruption";
          break;
        case 13:
          v0 = "heap_failure_freelists_corruption";
          break;
        case 14:
          v0 = "heap_failure_listentry_corruption";
          break;
        case 15:
          v0 = "heap_failure_lfh_bitmap_mismatch";
          break;
        case 16:
          v0 = "heap_failure_segment_lfh_bitmap_corruption";
          break;
        case 17:
          v0 = "heap_failure_segment_lfh_double_free";
          break;
      }
    }
  }
  else if ( dword_1801C50E8 == 12 )
  {
    v0 = "heap_failure_cross_heap_operation";
  }
  else if ( dword_1801C50E8 > 6 )
  {
    switch ( dword_1801C50E8 )
    {
      case 7:
        v0 = "heap_failure_buffer_underrun";
        break;
      case 8:
        v0 = "heap_failure_block_not_busy";
        break;
      case 9:
        v0 = "heap_failure_invalid_argument";
        break;
      case 10:
        v0 = "heap_failure_invalid_allocation_type";
        break;
      case 11:
        v0 = "heap_failure_usage_after_free";
        break;
    }
  }
  else if ( dword_1801C50E8 == 6 )
  {
    v0 = "heap_failure_buffer_overrun";
  }
  else if ( dword_1801C50E8 )
  {
    switch ( dword_1801C50E8 )
    {
      case 1:
        v0 = "heap_failure_unknown";
        break;
      case 2:
        v0 = "heap_failure_generic";
        break;
      case 3:
        v0 = "heap_failure_entry_corruption";
        break;
      case 4:
        v0 = "heap_failure_multiple_entries_corruption";
        break;
      case 5:
        v0 = "heap_failure_virtual_block_corruption";
        break;
    }
  }
  else
  {
    v0 = "heap_failure_internal";
  }
  if ( NtCurrentPeb()->Ldr )
    DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
  else
    DbgPrint("HEAP: ");
  DbgPrint("Error code: %d - %s\n", dword_1801C50E8, v0);
  if ( qword_1801C5100 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("Parameter1: %p\n", (const void *)qword_1801C5100);
  }
  if ( qword_1801C5108 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("Parameter2: %p\n", (const void *)qword_1801C5108);
  }
  if ( qword_1801C5110 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("Parameter3: %p\n", (const void *)qword_1801C5110);
  }
  if ( qword_1801C5118 || qword_1801C5120 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint(
      "Last known valid blocks: before - %p, after - %p\n",
      (const void *)qword_1801C5118,
      (const void *)qword_1801C5120);
  }
  if ( NtCurrentPeb()->Ldr )
    DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
  else
    DbgPrint("HEAP: ");
  return DbgPrint("Stack trace available at %p\n", &BackTrace);
}

```

## disassembly

```asm
0x18014f3c4  push    rbx
0x18014f3c6  push    rbp
0x18014f3c7  push    rsi
0x18014f3c8  push    rdi
0x18014f3c9  sub     rsp, 28h
0x18014f3cd  mov     rax, gs:60h
0x18014f3d6  lea     rbx, byte_180175FF3
0x18014f3dd  xor     edi, edi
0x18014f3df  lea     rsi, aHeap; "HEAP: "
0x18014f3e6  lea     rbp, aHeapWz; "HEAP[%wZ]: "
0x18014f3ed  cmp     [rax+18h], rdi
0x18014f3f1  jz      short loc_18014F412
0x18014f3f3  mov     rax, gs:60h
0x18014f3fc  mov     rcx, [rax+18h]
0x18014f400  mov     rdx, [rcx+10h]
0x18014f404  mov     rcx, rbp
0x18014f407  add     rdx, 58h ; 'X'
0x18014f40b  call    DbgPrint
0x18014f410  jmp     short loc_18014F41A
0x18014f412  mov     rcx, rsi
0x18014f415  call    DbgPrint
0x18014f41a  mov     r8, cs:qword_1801C50F0
0x18014f421  lea     rcx, aHeapErrorDetec; "Heap error detected at %p (heap handle "...
0x18014f428  mov     rdx, cs:qword_1801C50F8
0x18014f42f  call    DbgPrint
0x18014f434  mov     ecx, cs:dword_1801C50E8
0x18014f43a  cmp     ecx, 0Ch
0x18014f43d  jg      loc_18014F52A
0x18014f443  jz      loc_18014F51E
0x18014f449  cmp     ecx, 6
0x18014f44c  jg      short loc_18014F4C5
0x18014f44e  jz      short loc_18014F4B9
0x18014f450  test    ecx, ecx
0x18014f452  jz      short loc_18014F4AD
0x18014f454  sub     ecx, 1
0x18014f457  jz      short loc_18014F4A1
0x18014f459  sub     ecx, 1
0x18014f45c  jz      short loc_18014F495
0x18014f45e  sub     ecx, 1
0x18014f461  jz      short loc_18014F489
0x18014f463  sub     ecx, 1
0x18014f466  jz      short loc_18014F47D
0x18014f468  cmp     ecx, 1
0x18014f46b  jnz     loc_18014F5C4
0x18014f471  lea     rbx, aHeapFailureVir; "heap_failure_virtual_block_corruption"
0x18014f478  jmp     loc_18014F5C4
0x18014f47d  lea     rbx, aHeapFailureMul; "heap_failure_multiple_entries_corruptio"...
0x18014f484  jmp     loc_18014F5C4
0x18014f489  lea     rbx, aHeapFailureEnt; "heap_failure_entry_corruption"
0x18014f490  jmp     loc_18014F5C4
0x18014f495  lea     rbx, aHeapFailureGen; "heap_failure_generic"
0x18014f49c  jmp     loc_18014F5C4
0x18014f4a1  lea     rbx, aHeapFailureUnk; "heap_failure_unknown"
0x18014f4a8  jmp     loc_18014F5C4
0x18014f4ad  lea     rbx, aHeapFailureInt; "heap_failure_internal"
0x18014f4b4  jmp     loc_18014F5C4
0x18014f4b9  lea     rbx, aHeapFailureBuf; "heap_failure_buffer_overrun"
0x18014f4c0  jmp     loc_18014F5C4
0x18014f4c5  sub     ecx, 7
0x18014f4c8  jz      short loc_18014F512
0x18014f4ca  sub     ecx, 1
0x18014f4cd  jz      short loc_18014F506
0x18014f4cf  sub     ecx, 1
0x18014f4d2  jz      short loc_18014F4FA
0x18014f4d4  sub     ecx, 1
0x18014f4d7  jz      short loc_18014F4EE
0x18014f4d9  cmp     ecx, 1
0x18014f4dc  jnz     loc_18014F5C4
0x18014f4e2  lea     rbx, aHeapFailureUsa; "heap_failure_usage_after_free"
0x18014f4e9  jmp     loc_18014F5C4
0x18014f4ee  lea     rbx, aHeapFailureInv_1; "heap_failure_invalid_allocation_type"
0x18014f4f5  jmp     loc_18014F5C4
0x18014f4fa  lea     rbx, aHeapFailureInv_0; "heap_failure_invalid_argument"
0x18014f501  jmp     loc_18014F5C4
0x18014f506  lea     rbx, aHeapFailureBlo; "heap_failure_block_not_busy"
0x18014f50d  jmp     loc_18014F5C4
0x18014f512  lea     rbx, aHeapFailureBuf_0; "heap_failure_buffer_underrun"
0x18014f519  jmp     loc_18014F5C4
0x18014f51e  lea     rbx, aHeapFailureCro; "heap_failure_cross_heap_operation"
0x18014f525  jmp     loc_18014F5C4
0x18014f52a  cmp     ecx, 12h
0x18014f52d  jg      short loc_18014F580
0x18014f52f  jz      short loc_18014F577
0x18014f531  sub     ecx, 0Dh
0x18014f534  jz      short loc_18014F56E
0x18014f536  sub     ecx, 1
0x18014f539  jz      short loc_18014F565
0x18014f53b  sub     ecx, 1
0x18014f53e  jz      short loc_18014F55C
0x18014f540  sub     ecx, 1
0x18014f543  jz      short loc_18014F553
0x18014f545  cmp     ecx, 1
0x18014f548  jnz     short loc_18014F5C4
0x18014f54a  lea     rbx, aHeapFailureSeg_0; "heap_failure_segment_lfh_double_free"
0x18014f551  jmp     short loc_18014F5C4
0x18014f553  lea     rbx, aHeapFailureSeg_1; "heap_failure_segment_lfh_bitmap_corrupt"...
0x18014f55a  jmp     short loc_18014F5C4
0x18014f55c  lea     rbx, aHeapFailureLfh; "heap_failure_lfh_bitmap_mismatch"
0x18014f563  jmp     short loc_18014F5C4
0x18014f565  lea     rbx, aHeapFailureLis; "heap_failure_listentry_corruption"
0x18014f56c  jmp     short loc_18014F5C4
0x18014f56e  lea     rbx, aHeapFailureFre; "heap_failure_freelists_corruption"
0x18014f575  jmp     short loc_18014F5C4
0x18014f577  lea     rbx, aHeapFailureVsS; "heap_failure_vs_subsegment_corruption"
0x18014f57e  jmp     short loc_18014F5C4
0x18014f580  sub     ecx, 13h
0x18014f583  jz      short loc_18014F5BD
0x18014f585  sub     ecx, 1
0x18014f588  jz      short loc_18014F5B4
0x18014f58a  sub     ecx, 1
0x18014f58d  jz      short loc_18014F5AB
0x18014f58f  sub     ecx, 1
0x18014f592  jz      short loc_18014F5A2
0x18014f594  cmp     ecx, 1
0x18014f597  jnz     short loc_18014F5C4
0x18014f599  lea     rbx, aHeapFailureSeg; "heap_failure_segment_lfh_delay_free_cor"...
0x18014f5a0  jmp     short loc_18014F5C4
0x18014f5a2  lea     rbx, aHeapFailureInv; "heap_failure_invalid_va_mgr_query"
0x18014f5a9  jmp     short loc_18014F5C4
0x18014f5ab  lea     rbx, aHeapFailureCom; "heap_failure_commit_limit"
0x18014f5b2  jmp     short loc_18014F5C4
0x18014f5b4  lea     rbx, aHeapFailureAll; "heap_failure_allocation_limit"
0x18014f5bb  jmp     short loc_18014F5C4
0x18014f5bd  lea     rbx, aHeapFailureNul; "heap_failure_null_heap"
0x18014f5c4  mov     rax, gs:60h
0x18014f5cd  cmp     [rax+18h], rdi
0x18014f5d1  jz      short loc_18014F5F2
0x18014f5d3  mov     rax, gs:60h
0x18014f5dc  mov     rcx, [rax+18h]
0x18014f5e0  mov     rdx, [rcx+10h]
0x18014f5e4  mov     rcx, rbp
0x18014f5e7  add     rdx, 58h ; 'X'
0x18014f5eb  call    DbgPrint
0x18014f5f0  jmp     short loc_18014F5FA
0x18014f5f2  mov     rcx, rsi
0x18014f5f5  call    DbgPrint
0x18014f5fa  mov     edx, cs:dword_1801C50E8
0x18014f600  lea     rcx, aErrorCodeDS; "Error code: %d - %s\n"
0x18014f607  mov     r8, rbx
0x18014f60a  call    DbgPrint
0x18014f60f  cmp     cs:qword_1801C5100, rdi
0x18014f616  jz      short loc_18014F661
0x18014f618  mov     rax, gs:60h
0x18014f621  cmp     [rax+18h], rdi
0x18014f625  jz      short loc_18014F646
0x18014f627  mov     rax, gs:60h
0x18014f630  mov     rcx, [rax+18h]
0x18014f634  mov     rdx, [rcx+10h]
0x18014f638  mov     rcx, rbp
0x18014f63b  add     rdx, 58h ; 'X'
0x18014f63f  call    DbgPrint
0x18014f644  jmp     short loc_18014F64E
0x18014f646  mov     rcx, rsi
0x18014f649  call    DbgPrint
0x18014f64e  mov     rdx, cs:qword_1801C5100
0x18014f655  lea     rcx, aParameter1P; "Parameter1: %p\n"
0x18014f65c  call    DbgPrint
0x18014f661  cmp     cs:qword_1801C5108, rdi
0x18014f668  jz      short loc_18014F6B3
0x18014f66a  mov     rax, gs:60h
0x18014f673  cmp     [rax+18h], rdi
0x18014f677  jz      short loc_18014F698
0x18014f679  mov     rax, gs:60h
0x18014f682  mov     rcx, [rax+18h]
0x18014f686  mov     rdx, [rcx+10h]
0x18014f68a  mov     rcx, rbp
0x18014f68d  add     rdx, 58h ; 'X'
0x18014f691  call    DbgPrint
0x18014f696  jmp     short loc_18014F6A0
0x18014f698  mov     rcx, rsi
0x18014f69b  call    DbgPrint
0x18014f6a0  mov     rdx, cs:qword_1801C5108
0x18014f6a7  lea     rcx, aParameter2P; "Parameter2: %p\n"
0x18014f6ae  call    DbgPrint
0x18014f6b3  cmp     cs:qword_1801C5110, rdi
0x18014f6ba  jz      short loc_18014F705
0x18014f6bc  mov     rax, gs:60h
0x18014f6c5  cmp     [rax+18h], rdi
0x18014f6c9  jz      short loc_18014F6EA
0x18014f6cb  mov     rax, gs:60h
0x18014f6d4  mov     rcx, [rax+18h]
0x18014f6d8  mov     rdx, [rcx+10h]
0x18014f6dc  mov     rcx, rbp
0x18014f6df  add     rdx, 58h ; 'X'
0x18014f6e3  call    DbgPrint
0x18014f6e8  jmp     short loc_18014F6F2
0x18014f6ea  mov     rcx, rsi
0x18014f6ed  call    DbgPrint
0x18014f6f2  mov     rdx, cs:qword_1801C5110
0x18014f6f9  lea     rcx, aParameter3P; "Parameter3: %p\n"
0x18014f700  call    DbgPrint
0x18014f705  cmp     cs:qword_1801C5118, rdi
0x18014f70c  jnz     short loc_18014F717
0x18014f70e  cmp     cs:qword_1801C5120, rdi
0x18014f715  jz      short loc_18014F767
0x18014f717  mov     rax, gs:60h
0x18014f720  cmp     [rax+18h], rdi
0x18014f724  jz      short loc_18014F745
0x18014f726  mov     rax, gs:60h
0x18014f72f  mov     rcx, [rax+18h]
0x18014f733  mov     rdx, [rcx+10h]
0x18014f737  mov     rcx, rbp
0x18014f73a  add     rdx, 58h ; 'X'
0x18014f73e  call    DbgPrint
0x18014f743  jmp     short loc_18014F74D
0x18014f745  mov     rcx, rsi
0x18014f748  call    DbgPrint
0x18014f74d  mov     r8, cs:qword_1801C5120
0x18014f754  lea     rcx, aLastKnownValid; "Last known valid blocks: before - %p, a"...
0x18014f75b  mov     rdx, cs:qword_1801C5118
0x18014f762  call    DbgPrint
0x18014f767  mov     rax, gs:60h
0x18014f770  cmp     [rax+18h], rdi
0x18014f774  jz      short loc_18014F795
0x18014f776  mov     rax, gs:60h
0x18014f77f  mov     rcx, [rax+18h]
0x18014f783  mov     rdx, [rcx+10h]
0x18014f787  mov     rcx, rbp
0x18014f78a  add     rdx, 58h ; 'X'
0x18014f78e  call    DbgPrint
0x18014f793  jmp     short loc_18014F79D
0x18014f795  mov     rcx, rsi
0x18014f798  call    DbgPrint
0x18014f79d  lea     rdx, BackTrace
0x18014f7a4  lea     rcx, aStackTraceAvai; "Stack trace available at %p\n"
0x18014f7ab  add     rsp, 28h
0x18014f7af  pop     rdi
0x18014f7b0  pop     rsi
0x18014f7b1  pop     rbp
0x18014f7b2  pop     rbx
0x18014f7b3  jmp     DbgPrint
```
