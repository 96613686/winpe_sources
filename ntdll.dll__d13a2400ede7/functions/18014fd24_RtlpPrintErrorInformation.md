# RtlpPrintErrorInformation

- ea: `0x18014fd24`
- end: `0x180150118`
- name: `RtlpPrintErrorInformation`
- size: `1012`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801131dc`

## callees

- `0x180007060`
- `0x18014fd24`

## string_xrefs

- `0x18014ff0b`: `heap_failure_commit_limit`

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
0x18014fd24  push    rbx
0x18014fd26  push    rbp
0x18014fd27  push    rsi
0x18014fd28  push    rdi
0x18014fd29  sub     rsp, 28h
0x18014fd2d  mov     rax, gs:60h
0x18014fd36  lea     rbx, byte_180175FF3
0x18014fd3d  xor     edi, edi
0x18014fd3f  lea     rsi, aHeap; "HEAP: "
0x18014fd46  lea     rbp, aHeapWz; "HEAP[%wZ]: "
0x18014fd4d  cmp     [rax+18h], rdi
0x18014fd51  jz      short loc_18014FD72
0x18014fd53  mov     rax, gs:60h
0x18014fd5c  mov     rcx, [rax+18h]
0x18014fd60  mov     rdx, [rcx+10h]
0x18014fd64  mov     rcx, rbp
0x18014fd67  add     rdx, 58h ; 'X'
0x18014fd6b  call    DbgPrint
0x18014fd70  jmp     short loc_18014FD7A
0x18014fd72  mov     rcx, rsi
0x18014fd75  call    DbgPrint
0x18014fd7a  mov     r8, cs:qword_1801C50F0
0x18014fd81  lea     rcx, aHeapErrorDetec; "Heap error detected at %p (heap handle "...
0x18014fd88  mov     rdx, cs:qword_1801C50F8
0x18014fd8f  call    DbgPrint
0x18014fd94  mov     ecx, cs:dword_1801C50E8
0x18014fd9a  cmp     ecx, 0Ch
0x18014fd9d  jg      loc_18014FE8A
0x18014fda3  jz      loc_18014FE7E
0x18014fda9  cmp     ecx, 6
0x18014fdac  jg      short loc_18014FE25
0x18014fdae  jz      short loc_18014FE19
0x18014fdb0  test    ecx, ecx
0x18014fdb2  jz      short loc_18014FE0D
0x18014fdb4  sub     ecx, 1
0x18014fdb7  jz      short loc_18014FE01
0x18014fdb9  sub     ecx, 1
0x18014fdbc  jz      short loc_18014FDF5
0x18014fdbe  sub     ecx, 1
0x18014fdc1  jz      short loc_18014FDE9
0x18014fdc3  sub     ecx, 1
0x18014fdc6  jz      short loc_18014FDDD
0x18014fdc8  cmp     ecx, 1
0x18014fdcb  jnz     loc_18014FF24
0x18014fdd1  lea     rbx, aHeapFailureVir; "heap_failure_virtual_block_corruption"
0x18014fdd8  jmp     loc_18014FF24
0x18014fddd  lea     rbx, aHeapFailureMul; "heap_failure_multiple_entries_corruptio"...
0x18014fde4  jmp     loc_18014FF24
0x18014fde9  lea     rbx, aHeapFailureEnt; "heap_failure_entry_corruption"
0x18014fdf0  jmp     loc_18014FF24
0x18014fdf5  lea     rbx, aHeapFailureGen; "heap_failure_generic"
0x18014fdfc  jmp     loc_18014FF24
0x18014fe01  lea     rbx, aHeapFailureUnk; "heap_failure_unknown"
0x18014fe08  jmp     loc_18014FF24
0x18014fe0d  lea     rbx, aHeapFailureInt; "heap_failure_internal"
0x18014fe14  jmp     loc_18014FF24
0x18014fe19  lea     rbx, aHeapFailureBuf; "heap_failure_buffer_overrun"
0x18014fe20  jmp     loc_18014FF24
0x18014fe25  sub     ecx, 7
0x18014fe28  jz      short loc_18014FE72
0x18014fe2a  sub     ecx, 1
0x18014fe2d  jz      short loc_18014FE66
0x18014fe2f  sub     ecx, 1
0x18014fe32  jz      short loc_18014FE5A
0x18014fe34  sub     ecx, 1
0x18014fe37  jz      short loc_18014FE4E
0x18014fe39  cmp     ecx, 1
0x18014fe3c  jnz     loc_18014FF24
0x18014fe42  lea     rbx, aHeapFailureUsa; "heap_failure_usage_after_free"
0x18014fe49  jmp     loc_18014FF24
0x18014fe4e  lea     rbx, aHeapFailureInv_1; "heap_failure_invalid_allocation_type"
0x18014fe55  jmp     loc_18014FF24
0x18014fe5a  lea     rbx, aHeapFailureInv_0; "heap_failure_invalid_argument"
0x18014fe61  jmp     loc_18014FF24
0x18014fe66  lea     rbx, aHeapFailureBlo; "heap_failure_block_not_busy"
0x18014fe6d  jmp     loc_18014FF24
0x18014fe72  lea     rbx, aHeapFailureBuf_0; "heap_failure_buffer_underrun"
0x18014fe79  jmp     loc_18014FF24
0x18014fe7e  lea     rbx, aHeapFailureCro; "heap_failure_cross_heap_operation"
0x18014fe85  jmp     loc_18014FF24
0x18014fe8a  cmp     ecx, 12h
0x18014fe8d  jg      short loc_18014FEE0
0x18014fe8f  jz      short loc_18014FED7
0x18014fe91  sub     ecx, 0Dh
0x18014fe94  jz      short loc_18014FECE
0x18014fe96  sub     ecx, 1
0x18014fe99  jz      short loc_18014FEC5
0x18014fe9b  sub     ecx, 1
0x18014fe9e  jz      short loc_18014FEBC
0x18014fea0  sub     ecx, 1
0x18014fea3  jz      short loc_18014FEB3
0x18014fea5  cmp     ecx, 1
0x18014fea8  jnz     short loc_18014FF24
0x18014feaa  lea     rbx, aHeapFailureSeg_0; "heap_failure_segment_lfh_double_free"
0x18014feb1  jmp     short loc_18014FF24
0x18014feb3  lea     rbx, aHeapFailureSeg_1; "heap_failure_segment_lfh_bitmap_corrupt"...
0x18014feba  jmp     short loc_18014FF24
0x18014febc  lea     rbx, aHeapFailureLfh; "heap_failure_lfh_bitmap_mismatch"
0x18014fec3  jmp     short loc_18014FF24
0x18014fec5  lea     rbx, aHeapFailureLis; "heap_failure_listentry_corruption"
0x18014fecc  jmp     short loc_18014FF24
0x18014fece  lea     rbx, aHeapFailureFre; "heap_failure_freelists_corruption"
0x18014fed5  jmp     short loc_18014FF24
0x18014fed7  lea     rbx, aHeapFailureVsS; "heap_failure_vs_subsegment_corruption"
0x18014fede  jmp     short loc_18014FF24
0x18014fee0  sub     ecx, 13h
0x18014fee3  jz      short loc_18014FF1D
0x18014fee5  sub     ecx, 1
0x18014fee8  jz      short loc_18014FF14
0x18014feea  sub     ecx, 1
0x18014feed  jz      short loc_18014FF0B
0x18014feef  sub     ecx, 1
0x18014fef2  jz      short loc_18014FF02
0x18014fef4  cmp     ecx, 1
0x18014fef7  jnz     short loc_18014FF24
0x18014fef9  lea     rbx, aHeapFailureSeg; "heap_failure_segment_lfh_delay_free_cor"...
0x18014ff00  jmp     short loc_18014FF24
0x18014ff02  lea     rbx, aHeapFailureInv; "heap_failure_invalid_va_mgr_query"
0x18014ff09  jmp     short loc_18014FF24
0x18014ff0b  lea     rbx, aHeapFailureCom; "heap_failure_commit_limit"
0x18014ff12  jmp     short loc_18014FF24
0x18014ff14  lea     rbx, aHeapFailureAll; "heap_failure_allocation_limit"
0x18014ff1b  jmp     short loc_18014FF24
0x18014ff1d  lea     rbx, aHeapFailureNul; "heap_failure_null_heap"
0x18014ff24  mov     rax, gs:60h
0x18014ff2d  cmp     [rax+18h], rdi
0x18014ff31  jz      short loc_18014FF52
0x18014ff33  mov     rax, gs:60h
0x18014ff3c  mov     rcx, [rax+18h]
0x18014ff40  mov     rdx, [rcx+10h]
0x18014ff44  mov     rcx, rbp
0x18014ff47  add     rdx, 58h ; 'X'
0x18014ff4b  call    DbgPrint
0x18014ff50  jmp     short loc_18014FF5A
0x18014ff52  mov     rcx, rsi
0x18014ff55  call    DbgPrint
0x18014ff5a  mov     edx, cs:dword_1801C50E8
0x18014ff60  lea     rcx, aErrorCodeDS; "Error code: %d - %s\n"
0x18014ff67  mov     r8, rbx
0x18014ff6a  call    DbgPrint
0x18014ff6f  cmp     cs:qword_1801C5100, rdi
0x18014ff76  jz      short loc_18014FFC1
0x18014ff78  mov     rax, gs:60h
0x18014ff81  cmp     [rax+18h], rdi
0x18014ff85  jz      short loc_18014FFA6
0x18014ff87  mov     rax, gs:60h
0x18014ff90  mov     rcx, [rax+18h]
0x18014ff94  mov     rdx, [rcx+10h]
0x18014ff98  mov     rcx, rbp
0x18014ff9b  add     rdx, 58h ; 'X'
0x18014ff9f  call    DbgPrint
0x18014ffa4  jmp     short loc_18014FFAE
0x18014ffa6  mov     rcx, rsi
0x18014ffa9  call    DbgPrint
0x18014ffae  mov     rdx, cs:qword_1801C5100
0x18014ffb5  lea     rcx, aParameter1P; "Parameter1: %p\n"
0x18014ffbc  call    DbgPrint
0x18014ffc1  cmp     cs:qword_1801C5108, rdi
0x18014ffc8  jz      short loc_180150013
0x18014ffca  mov     rax, gs:60h
0x18014ffd3  cmp     [rax+18h], rdi
0x18014ffd7  jz      short loc_18014FFF8
0x18014ffd9  mov     rax, gs:60h
0x18014ffe2  mov     rcx, [rax+18h]
0x18014ffe6  mov     rdx, [rcx+10h]
0x18014ffea  mov     rcx, rbp
0x18014ffed  add     rdx, 58h ; 'X'
0x18014fff1  call    DbgPrint
0x18014fff6  jmp     short loc_180150000
0x18014fff8  mov     rcx, rsi
0x18014fffb  call    DbgPrint
0x180150000  mov     rdx, cs:qword_1801C5108
0x180150007  lea     rcx, aParameter2P; "Parameter2: %p\n"
0x18015000e  call    DbgPrint
0x180150013  cmp     cs:qword_1801C5110, rdi
0x18015001a  jz      short loc_180150065
0x18015001c  mov     rax, gs:60h
0x180150025  cmp     [rax+18h], rdi
0x180150029  jz      short loc_18015004A
0x18015002b  mov     rax, gs:60h
0x180150034  mov     rcx, [rax+18h]
0x180150038  mov     rdx, [rcx+10h]
0x18015003c  mov     rcx, rbp
0x18015003f  add     rdx, 58h ; 'X'
0x180150043  call    DbgPrint
0x180150048  jmp     short loc_180150052
0x18015004a  mov     rcx, rsi
0x18015004d  call    DbgPrint
0x180150052  mov     rdx, cs:qword_1801C5110
0x180150059  lea     rcx, aParameter3P; "Parameter3: %p\n"
0x180150060  call    DbgPrint
0x180150065  cmp     cs:qword_1801C5118, rdi
0x18015006c  jnz     short loc_180150077
0x18015006e  cmp     cs:qword_1801C5120, rdi
0x180150075  jz      short loc_1801500C7
0x180150077  mov     rax, gs:60h
0x180150080  cmp     [rax+18h], rdi
0x180150084  jz      short loc_1801500A5
0x180150086  mov     rax, gs:60h
0x18015008f  mov     rcx, [rax+18h]
0x180150093  mov     rdx, [rcx+10h]
0x180150097  mov     rcx, rbp
0x18015009a  add     rdx, 58h ; 'X'
0x18015009e  call    DbgPrint
0x1801500a3  jmp     short loc_1801500AD
0x1801500a5  mov     rcx, rsi
0x1801500a8  call    DbgPrint
0x1801500ad  mov     r8, cs:qword_1801C5120
0x1801500b4  lea     rcx, aLastKnownValid; "Last known valid blocks: before - %p, a"...
0x1801500bb  mov     rdx, cs:qword_1801C5118
0x1801500c2  call    DbgPrint
0x1801500c7  mov     rax, gs:60h
0x1801500d0  cmp     [rax+18h], rdi
0x1801500d4  jz      short loc_1801500F5
0x1801500d6  mov     rax, gs:60h
0x1801500df  mov     rcx, [rax+18h]
0x1801500e3  mov     rdx, [rcx+10h]
0x1801500e7  mov     rcx, rbp
0x1801500ea  add     rdx, 58h ; 'X'
0x1801500ee  call    DbgPrint
0x1801500f3  jmp     short loc_1801500FD
0x1801500f5  mov     rcx, rsi
0x1801500f8  call    DbgPrint
0x1801500fd  lea     rdx, BackTrace
0x180150104  lea     rcx, aStackTraceAvai; "Stack trace available at %p\n"
0x18015010b  add     rsp, 28h
0x18015010f  pop     rdi
0x180150110  pop     rsi
0x180150111  pop     rbp
0x180150112  pop     rbx
0x180150113  jmp     DbgPrint
```
