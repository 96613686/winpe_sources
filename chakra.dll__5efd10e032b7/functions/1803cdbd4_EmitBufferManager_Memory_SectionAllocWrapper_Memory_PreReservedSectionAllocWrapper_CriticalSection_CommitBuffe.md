# EmitBufferManager<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper,CriticalSection>::CommitBuffer(EmitBufferAllocation<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper> *,unsigned __int64,uchar *,unsigned __int64,uchar const *,ulong)

- ea: `0x1803cdbd4`
- end: `0x1803cddd9`
- name: `?CommitBuffer@?$EmitBufferManager@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@VCriticalSection@@@@QEAA_NPEAU?$EmitBufferAllocation@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@@_KPEAE_KPEBEK@Z`
- size: `517`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Source, size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1803cdb70`
- `0x1805611a0`

## callees

- `0x1803cdbd4`
- `0x180492b84`
- `0x180492bbc`
- `0x1805611a0`
- `0x1805a9c5a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1803cdcff`
- `msvcrt!memcpy_s` at `0x1803cdcff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cdd43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cdd55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cdd8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cddb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cdd43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cdd55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cdd8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803cddb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803cdc10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803cdc10`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1803cdd7c`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1803cdd7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall EmitBufferManager<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper,CriticalSection>::CommitBuffer(
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
      || (unsigned int)Memory::CustomHeap::Heap<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::ProtectAllocationWithExecuteReadWrite(
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
        || (unsigned int)Memory::CustomHeap::Heap<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::ProtectAllocationWithExecuteReadOnly(
                           v11,
                           *a2,
                           v14) )
      {
        continue;
      }
    }
    goto LABEL_15;
  }
  if ( !FlushInstructionCache(*(HANDLE *)(a1 + 376), (LPCVOID)(v18 + v19), dwSize) )
  {
LABEL_15:
    LeaveCriticalSection(v8);
    return 0;
  }
  v16 = EmitBufferManager<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper,CriticalSection>::FinalizeAllocation(
          a1,
          a2,
          a4);
  LeaveCriticalSection(v8);
  return v16;
}

```

## disassembly

```asm
0x1803cdbd4  mov     rax, rsp
0x1803cdbd7  mov     [rax+20h], r9
0x1803cdbdb  mov     [rax+18h], r8
0x1803cdbdf  mov     [rax+10h], rdx
0x1803cdbe3  mov     [rax+8], rcx
0x1803cdbe7  push    rbx
0x1803cdbe8  push    rbp
0x1803cdbe9  push    rsi
0x1803cdbea  push    rdi
0x1803cdbeb  push    r12
0x1803cdbed  push    r13
0x1803cdbef  push    r14
0x1803cdbf1  push    r15
0x1803cdbf3  sub     rsp, 58h
0x1803cdbf7  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1803cdbff  mov     r13, rcx
0x1803cdc02  lea     rbx, [rcx+150h]
0x1803cdc09  mov     [rax-50h], rbx
0x1803cdc0d  mov     rcx, rbx; lpCriticalSection
0x1803cdc10  call    cs:__imp_EnterCriticalSection
0x1803cdc17  nop     dword ptr [rax+rax+00h]
0x1803cdc1c  nop
0x1803cdc1d  mov     r14, [rsp+98h+arg_8]
0x1803cdc25  mov     rcx, [r14+8]
0x1803cdc29  mov     [rsp+98h+var_70], rcx
0x1803cdc2e  mov     r15, [rsp+98h+arg_18]
0x1803cdc36  add     r15, rcx
0x1803cdc39  mov     rax, [r14]
0x1803cdc3c  mov     rcx, [rax+18h]
0x1803cdc40  mov     [rsp+98h+var_68], rcx
0x1803cdc45  mov     ebp, dword ptr [rsp+98h+Size]
0x1803cdc4c  add     rbp, [rsp+98h+arg_20]
0x1803cdc54  mov     [rsp+98h+dwSize], rbp
0x1803cdc59  test    rbp, rbp
0x1803cdc5c  jz      loc_1803CDD66
0x1803cdc62  mov     ecx, r15d
0x1803cdc65  and     ecx, 0FFFh
0x1803cdc6b  mov     eax, 1000h
0x1803cdc70  sub     eax, ecx
0x1803cdc72  mov     r12d, eax
0x1803cdc75  mov     esi, eax
0x1803cdc77  cmp     rbp, r12
0x1803cdc7a  cmovbe  rsi, rbp
0x1803cdc7e  cmp     byte ptr cs:word_18073FD88+1, 0
0x1803cdc85  jnz     short loc_1803CDC9A
0x1803cdc87  mov     r8, r15
0x1803cdc8a  mov     rdx, [r14]
0x1803cdc8d  call    ?ProtectAllocationWithExecuteReadWrite@?$Heap@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@CustomHeap@Memory@@QEAAHPEAUAllocation@23@PEAD@Z; Memory::CustomHeap::Heap<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::ProtectAllocationWithExecuteReadWrite(Memory::CustomHeap::Allocation *,char *)
0x1803cdc92  test    eax, eax
0x1803cdc94  jz      loc_1803CDD52
0x1803cdc9a  mov     rdi, r15
0x1803cdc9d  mov     [rsp+98h+var_78], r15
0x1803cdca2  mov     eax, dword ptr [rsp+98h+Size]
0x1803cdca9  test    eax, eax
0x1803cdcab  jz      short loc_1803CDCE1
0x1803cdcad  cmp     eax, r12d
0x1803cdcb0  cmovb   r12d, eax
0x1803cdcb4  mov     edi, r12d
0x1803cdcb7  mov     r8d, r12d; Size
0x1803cdcba  mov     edx, 0CCh; Val
0x1803cdcbf  mov     rcx, r15; void *
0x1803cdcc2  call    memset_0
0x1803cdcc7  sub     dword ptr [rsp+98h+Size], r12d
0x1803cdccf  add     r15, rdi
0x1803cdcd2  add     [r14+8], rdi
0x1803cdcd6  sub     rbp, rdi
0x1803cdcd9  sub     rsi, rdi
0x1803cdcdc  mov     rdi, [rsp+98h+var_78]
0x1803cdce1  test    rsi, rsi
0x1803cdce4  jz      short loc_1803CDD20
0x1803cdce6  mov     edx, [r14+10h]
0x1803cdcea  sub     edx, [r14+8]; DestinationSize
0x1803cdcee  mov     r9, rsi; SourceSize
0x1803cdcf1  mov     r12, [rsp+98h+Source]
0x1803cdcf9  mov     r8, r12; Source
0x1803cdcfc  mov     rcx, r15; Destination
0x1803cdcff  call    cs:__imp_memcpy_s
0x1803cdd06  nop     dword ptr [rax+rax+00h]
0x1803cdd0b  add     r15, rsi
0x1803cdd0e  add     r12, rsi
0x1803cdd11  mov     [rsp+98h+Source], r12
0x1803cdd19  add     [r14+8], rsi
0x1803cdd1d  sub     rbp, rsi
0x1803cdd20  cmp     byte ptr cs:word_18073FD88+1, 0
0x1803cdd27  jnz     loc_1803CDC59
0x1803cdd2d  mov     r8, rdi
0x1803cdd30  mov     rdx, [r14]
0x1803cdd33  call    ?ProtectAllocationWithExecuteReadOnly@?$Heap@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@CustomHeap@Memory@@QEAAHPEAUAllocation@23@PEAD@Z; Memory::CustomHeap::Heap<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::ProtectAllocationWithExecuteReadOnly(Memory::CustomHeap::Allocation *,char *)
0x1803cdd38  test    eax, eax
0x1803cdd3a  jnz     loc_1803CDC59
0x1803cdd40  mov     rcx, rbx; lpCriticalSection
0x1803cdd43  call    cs:__imp_LeaveCriticalSection
0x1803cdd4a  nop     dword ptr [rax+rax+00h]
0x1803cdd4f  nop
0x1803cdd50  jmp     short loc_1803CDD62
0x1803cdd52  mov     rcx, rbx; lpCriticalSection
0x1803cdd55  call    cs:__imp_LeaveCriticalSection
0x1803cdd5c  nop     dword ptr [rax+rax+00h]
0x1803cdd61  nop
0x1803cdd62  xor     al, al
0x1803cdd64  jmp     short loc_1803CDDC7
0x1803cdd66  mov     rdx, [rsp+98h+var_68]
0x1803cdd6b  add     rdx, [rsp+98h+var_70]; lpBaseAddress
0x1803cdd70  mov     r8, [rsp+98h+dwSize]; dwSize
0x1803cdd75  mov     rcx, [r13+178h]; hProcess
0x1803cdd7c  call    cs:__imp_FlushInstructionCache
0x1803cdd83  nop     dword ptr [rax+rax+00h]
0x1803cdd88  test    eax, eax
0x1803cdd8a  jnz     short loc_1803CDD9E
0x1803cdd8c  mov     rcx, rbx; lpCriticalSection
0x1803cdd8f  call    cs:__imp_LeaveCriticalSection
0x1803cdd96  nop     dword ptr [rax+rax+00h]
0x1803cdd9b  nop
0x1803cdd9c  jmp     short loc_1803CDD62
0x1803cdd9e  mov     r8, [rsp+98h+arg_18]
0x1803cdda6  mov     rdx, r14
0x1803cdda9  mov     rcx, r13
0x1803cddac  call    ?FinalizeAllocation@?$EmitBufferManager@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@VCriticalSection@@@@AEAA_NPEAU?$EmitBufferAllocation@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@@PEAE@Z; EmitBufferManager<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper,CriticalSection>::FinalizeAllocation(EmitBufferAllocation<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper> *,uchar *)
0x1803cddb1  mov     dil, al
0x1803cddb4  mov     rcx, rbx; lpCriticalSection
0x1803cddb7  call    cs:__imp_LeaveCriticalSection
0x1803cddbe  nop     dword ptr [rax+rax+00h]
0x1803cddc3  nop
0x1803cddc4  mov     al, dil
0x1803cddc7  add     rsp, 58h
0x1803cddcb  pop     r15
0x1803cddcd  pop     r14
0x1803cddcf  pop     r13
0x1803cddd1  pop     r12
0x1803cddd3  pop     rdi
0x1803cddd4  pop     rsi
0x1803cddd5  pop     rbp
0x1803cddd6  pop     rbx
0x1803cddd7  retn
```
