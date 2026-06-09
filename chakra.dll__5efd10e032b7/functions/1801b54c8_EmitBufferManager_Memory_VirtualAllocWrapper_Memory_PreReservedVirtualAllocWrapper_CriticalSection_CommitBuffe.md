# EmitBufferManager<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper,CriticalSection>::CommitBuffer(EmitBufferAllocation<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper> *,unsigned __int64,uchar *,unsigned __int64,uchar const *,ulong)

- ea: `0x1801b54c8`
- end: `0x1801b56dc`
- name: `?CommitBuffer@?$EmitBufferManager@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@VCriticalSection@@@@QEAA_NPEAU?$EmitBufferAllocation@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@@_KPEAE_KPEBEK@Z`
- size: `532`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Source, size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801b580c`
- `0x1801c9470`

## callees

- `0x1801b54c8`
- `0x1801b56e4`
- `0x1801b5778`
- `0x1801b580c`
- `0x1805a9c5a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1801b55c3`
- `msvcrt!memcpy_s` at `0x1801b55c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5607`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b56b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b56ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5607`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b56b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b56ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b5504`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b5504`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1801b562e`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1801b562e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall EmitBufferManager<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper,CriticalSection>::CommitBuffer(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char *Source,
        size_t Size)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  char *v9; // r15
  SIZE_T v10; // rbp
  __int64 v11; // rcx
  rsize_t v12; // r12
  rsize_t v13; // rsi
  char *v14; // rdi
  char v16; // di
  char *v17; // [rsp+20h] [rbp-78h]
  __int64 v18; // [rsp+28h] [rbp-70h]
  __int64 v19; // [rsp+30h] [rbp-68h]
  SIZE_T dwSize; // [rsp+38h] [rbp-60h]

  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 336));
  v18 = a2[1];
  v9 = (char *)(v18 + a4);
  v19 = *(_QWORD *)(*a2 + 24LL);
  v10 = a5 + (unsigned int)Size;
  dwSize = v10;
  while ( v10 )
  {
    v11 = (unsigned __int16)v9 & 0xFFF;
    v12 = (unsigned int)(4096 - v11);
    v13 = v12;
    if ( v10 <= v12 )
      v13 = v10;
    if ( *(&word_18073FD88 + 1)
      || (unsigned int)Memory::CustomHeap::Heap<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::ProtectAllocationWithExecuteReadWrite(
                         v11,
                         *a2,
                         v9) )
    {
      v14 = v9;
      v17 = v9;
      if ( (_DWORD)Size )
      {
        if ( (unsigned int)Size < (unsigned int)v12 )
          LODWORD(v12) = Size;
        memset_0(v9, 204, (unsigned int)v12);
        LODWORD(Size) = Size - v12;
        v9 += (unsigned int)v12;
        a2[1] += (unsigned int)v12;
        v10 -= (unsigned int)v12;
        v13 -= (unsigned int)v12;
        v14 = v17;
      }
      if ( v13 )
      {
        memcpy_s(v9, (unsigned int)(*((_DWORD *)a2 + 4) - *((_DWORD *)a2 + 2)), Source, v13);
        v9 += v13;
        Source += v13;
        a2[1] += v13;
        v10 -= v13;
      }
      if ( *(&word_18073FD88 + 1)
        || (unsigned int)Memory::CustomHeap::Heap<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::ProtectAllocationWithExecuteReadOnly(
                           v11,
                           *a2,
                           v14) )
      {
        continue;
      }
    }
    goto LABEL_12;
  }
  if ( !FlushInstructionCache(*(HANDLE *)(a1 + 376), (LPCVOID)(v18 + v19), dwSize) )
  {
LABEL_12:
    LeaveCriticalSection(v8);
    return 0;
  }
  v16 = EmitBufferManager<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper,CriticalSection>::FinalizeAllocation(
          a1,
          a2,
          a4);
  LeaveCriticalSection(v8);
  return v16;
}

```

## disassembly

```asm
0x1801b54c8  mov     rax, rsp
0x1801b54cb  mov     [rax+20h], r9
0x1801b54cf  mov     [rax+18h], r8
0x1801b54d3  mov     [rax+10h], rdx
0x1801b54d7  mov     [rax+8], rcx
0x1801b54db  push    rbx
0x1801b54dc  push    rbp
0x1801b54dd  push    rsi
0x1801b54de  push    rdi
0x1801b54df  push    r12
0x1801b54e1  push    r13
0x1801b54e3  push    r14
0x1801b54e5  push    r15
0x1801b54e7  sub     rsp, 58h
0x1801b54eb  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1801b54f3  mov     r13, rcx
0x1801b54f6  lea     rbx, [rcx+150h]
0x1801b54fd  mov     [rax-50h], rbx
0x1801b5501  mov     rcx, rbx; lpCriticalSection
0x1801b5504  call    cs:__imp_EnterCriticalSection
0x1801b550b  nop     dword ptr [rax+rax+00h]
0x1801b5510  nop
0x1801b5511  mov     r14, [rsp+98h+arg_8]
0x1801b5519  mov     rcx, [r14+8]
0x1801b551d  mov     [rsp+98h+var_70], rcx
0x1801b5522  mov     r15, [rsp+98h+arg_18]
0x1801b552a  add     r15, rcx
0x1801b552d  mov     rax, [r14]
0x1801b5530  mov     rcx, [rax+18h]
0x1801b5534  mov     [rsp+98h+var_68], rcx
0x1801b5539  mov     ebp, dword ptr [rsp+98h+Size]
0x1801b5540  add     rbp, [rsp+98h+arg_20]
0x1801b5548  mov     [rsp+98h+dwSize], rbp
0x1801b554d  test    rbp, rbp
0x1801b5550  jz      loc_1801B5618
0x1801b5556  mov     ecx, r15d
0x1801b5559  and     ecx, 0FFFh
0x1801b555f  mov     eax, 1000h
0x1801b5564  sub     eax, ecx
0x1801b5566  mov     r12d, eax
0x1801b5569  mov     esi, eax
0x1801b556b  cmp     rbp, r12
0x1801b556e  cmovbe  rsi, rbp
0x1801b5572  cmp     byte ptr cs:word_18073FD88+1, 0
0x1801b5579  jnz     short loc_1801B558E
0x1801b557b  mov     r8, r15
0x1801b557e  mov     rdx, [r14]
0x1801b5581  call    ?ProtectAllocationWithExecuteReadWrite@?$Heap@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@CustomHeap@Memory@@QEAAHPEAUAllocation@23@PEAD@Z; Memory::CustomHeap::Heap<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::ProtectAllocationWithExecuteReadWrite(Memory::CustomHeap::Allocation *,char *)
0x1801b5586  test    eax, eax
0x1801b5588  jz      loc_1801B56C7
0x1801b558e  mov     rdi, r15
0x1801b5591  mov     [rsp+98h+var_78], r15
0x1801b5596  mov     eax, dword ptr [rsp+98h+Size]
0x1801b559d  test    eax, eax
0x1801b559f  jnz     loc_1801B5679
0x1801b55a5  test    rsi, rsi
0x1801b55a8  jz      short loc_1801B55E4
0x1801b55aa  mov     edx, [r14+10h]
0x1801b55ae  sub     edx, [r14+8]; DestinationSize
0x1801b55b2  mov     r9, rsi; SourceSize
0x1801b55b5  mov     r12, [rsp+98h+Source]
0x1801b55bd  mov     r8, r12; Source
0x1801b55c0  mov     rcx, r15; Destination
0x1801b55c3  call    cs:__imp_memcpy_s
0x1801b55ca  nop     dword ptr [rax+rax+00h]
0x1801b55cf  add     r15, rsi
0x1801b55d2  add     r12, rsi
0x1801b55d5  mov     [rsp+98h+Source], r12
0x1801b55dd  add     [r14+8], rsi
0x1801b55e1  sub     rbp, rsi
0x1801b55e4  cmp     byte ptr cs:word_18073FD88+1, 0
0x1801b55eb  jnz     loc_1801B554D
0x1801b55f1  mov     r8, rdi
0x1801b55f4  mov     rdx, [r14]
0x1801b55f7  call    ?ProtectAllocationWithExecuteReadOnly@?$Heap@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@CustomHeap@Memory@@QEAAHPEAUAllocation@23@PEAD@Z; Memory::CustomHeap::Heap<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::ProtectAllocationWithExecuteReadOnly(Memory::CustomHeap::Allocation *,char *)
0x1801b55fc  test    eax, eax
0x1801b55fe  jnz     loc_1801B554D
0x1801b5604  mov     rcx, rbx; lpCriticalSection
0x1801b5607  call    cs:__imp_LeaveCriticalSection
0x1801b560e  nop     dword ptr [rax+rax+00h]
0x1801b5613  nop
0x1801b5614  xor     al, al
0x1801b5616  jmp     short loc_1801B5667
0x1801b5618  mov     rdx, [rsp+98h+var_68]
0x1801b561d  add     rdx, [rsp+98h+var_70]; lpBaseAddress
0x1801b5622  mov     r8, [rsp+98h+dwSize]; dwSize
0x1801b5627  mov     rcx, [r13+178h]; hProcess
0x1801b562e  call    cs:__imp_FlushInstructionCache
0x1801b5635  nop     dword ptr [rax+rax+00h]
0x1801b563a  test    eax, eax
0x1801b563c  jz      short loc_1801B56B2
0x1801b563e  mov     r8, [rsp+98h+arg_18]
0x1801b5646  mov     rdx, r14
0x1801b5649  mov     rcx, r13
0x1801b564c  call    ?FinalizeAllocation@?$EmitBufferManager@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@VCriticalSection@@@@AEAA_NPEAU?$EmitBufferAllocation@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@@PEAE@Z; EmitBufferManager<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper,CriticalSection>::FinalizeAllocation(EmitBufferAllocation<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper> *,uchar *)
0x1801b5651  mov     dil, al
0x1801b5654  mov     rcx, rbx; lpCriticalSection
0x1801b5657  call    cs:__imp_LeaveCriticalSection
0x1801b565e  nop     dword ptr [rax+rax+00h]
0x1801b5663  nop
0x1801b5664  mov     al, dil
0x1801b5667  add     rsp, 58h
0x1801b566b  pop     r15
0x1801b566d  pop     r14
0x1801b566f  pop     r13
0x1801b5671  pop     r12
0x1801b5673  pop     rdi
0x1801b5674  pop     rsi
0x1801b5675  pop     rbp
0x1801b5676  pop     rbx
0x1801b5677  retn
0x1801b5679  cmp     eax, r12d
0x1801b567c  cmovb   r12d, eax
0x1801b5680  mov     edi, r12d
0x1801b5683  mov     r8d, r12d; Size
0x1801b5686  mov     edx, 0CCh; Val
0x1801b568b  mov     rcx, r15; void *
0x1801b568e  call    memset_0
0x1801b5693  sub     dword ptr [rsp+98h+Size], r12d
0x1801b569b  add     r15, rdi
0x1801b569e  add     [r14+8], rdi
0x1801b56a2  sub     rbp, rdi
0x1801b56a5  sub     rsi, rdi
0x1801b56a8  mov     rdi, [rsp+98h+var_78]
0x1801b56ad  jmp     loc_1801B55A5
0x1801b56b2  mov     rcx, rbx; lpCriticalSection
0x1801b56b5  call    cs:__imp_LeaveCriticalSection
0x1801b56bc  nop     dword ptr [rax+rax+00h]
0x1801b56c1  nop
0x1801b56c2  jmp     loc_1801B5614
0x1801b56c7  mov     rcx, rbx; lpCriticalSection
0x1801b56ca  call    cs:__imp_LeaveCriticalSection
0x1801b56d1  nop     dword ptr [rax+rax+00h]
0x1801b56d6  nop
0x1801b56d7  jmp     loc_1801B5614
```
