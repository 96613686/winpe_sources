# EmitBufferManager<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper,CriticalSection>::CommitBufferForInterpreter(EmitBufferAllocation<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper> *,uchar *,unsigned __int64)

- ea: `0x1805610d0`
- end: `0x180561197`
- name: `?CommitBufferForInterpreter@?$EmitBufferManager@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@VCriticalSection@@@@QEAA_NPEAU?$EmitBufferAllocation@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@@PEAE_K@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18055e8c4`

## callees

- `0x180492b84`
- `0x1805610d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180561137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18056116e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180561180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180561137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18056116e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180561180`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180561102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180561102`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18056115a`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18056115a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall EmitBufferManager<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper,CriticalSection>::CommitBufferForInterpreter(
        __int64 a1,
        _QWORD *a2,
        const void *a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rcx

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 336));
  a2[1] += 4096LL;
  if ( (*(&word_18073FD88 + 1)
     || (unsigned int)Memory::CustomHeap::Heap<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::ProtectAllocationWithExecuteReadOnly(
                        v5,
                        *a2,
                        0))
    && FlushInstructionCache(*(HANDLE *)(a1 + 376), a3, 0x1000u) )
  {
    LeaveCriticalSection(v4);
    return 1;
  }
  else
  {
    LeaveCriticalSection(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x1805610d0  mov     rax, rsp
0x1805610d3  mov     [rax+20h], r9
0x1805610d7  mov     [rax+18h], r8
0x1805610db  mov     [rax+10h], rdx
0x1805610df  mov     [rax+8], rcx
0x1805610e3  push    rbx
0x1805610e4  push    rdi
0x1805610e5  sub     rsp, 38h
0x1805610e9  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1805610f1  mov     rdi, rcx
0x1805610f4  lea     rbx, [rcx+150h]
0x1805610fb  mov     [rax-20h], rbx
0x1805610ff  mov     rcx, rbx; lpCriticalSection
0x180561102  call    cs:__imp_EnterCriticalSection
0x180561109  nop     dword ptr [rax+rax+00h]
0x18056110e  nop
0x18056110f  mov     rdx, [rsp+48h+arg_8]
0x180561114  add     qword ptr [rdx+8], 1000h
0x18056111c  cmp     byte ptr cs:word_18073FD88+1, 0
0x180561123  jnz     short loc_180561148
0x180561125  xor     r8d, r8d
0x180561128  mov     rdx, [rdx]
0x18056112b  call    ?ProtectAllocationWithExecuteReadOnly@?$Heap@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@CustomHeap@Memory@@QEAAHPEAUAllocation@23@PEAD@Z; Memory::CustomHeap::Heap<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::ProtectAllocationWithExecuteReadOnly(Memory::CustomHeap::Allocation *,char *)
0x180561130  test    eax, eax
0x180561132  jnz     short loc_180561148
0x180561134  mov     rcx, rbx; lpCriticalSection
0x180561137  call    cs:__imp_LeaveCriticalSection
0x18056113e  nop     dword ptr [rax+rax+00h]
0x180561143  nop
0x180561144  xor     al, al
0x180561146  jmp     short loc_18056118F
0x180561148  mov     r8d, 1000h; dwSize
0x18056114e  mov     rdx, [rsp+48h+lpBaseAddress]; lpBaseAddress
0x180561153  mov     rcx, [rdi+178h]; hProcess
0x18056115a  call    cs:__imp_FlushInstructionCache
0x180561161  nop     dword ptr [rax+rax+00h]
0x180561166  nop
0x180561167  test    eax, eax
0x180561169  jnz     short loc_18056117D
0x18056116b  mov     rcx, rbx; lpCriticalSection
0x18056116e  call    cs:__imp_LeaveCriticalSection
0x180561175  nop     dword ptr [rax+rax+00h]
0x18056117a  nop
0x18056117b  jmp     short loc_180561144
0x18056117d  mov     rcx, rbx; lpCriticalSection
0x180561180  call    cs:__imp_LeaveCriticalSection
0x180561187  nop     dword ptr [rax+rax+00h]
0x18056118c  nop
0x18056118d  mov     al, 1
0x18056118f  add     rsp, 38h
0x180561193  pop     rdi
0x180561194  pop     rbx
0x180561195  retn
```
