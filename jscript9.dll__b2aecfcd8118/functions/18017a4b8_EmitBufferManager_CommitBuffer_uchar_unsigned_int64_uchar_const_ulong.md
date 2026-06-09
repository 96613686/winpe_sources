# EmitBufferManager::CommitBuffer(uchar *,unsigned __int64,uchar const *,ulong)

- ea: `0x18017a4b8`
- end: `0x18017a63e`
- name: `?CommitBuffer@EmitBufferManager@@QEAAXPEAE_KPEBEK@Z`
- size: `390`
- prototype: `void(EmitBufferManager *__hidden this, unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d1bc`

## callees

- `0x1800b7f9c`
- `0x18017a4b8`
- `0x1801cc26b`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18017a589`
- `msvcrt!memcpy_s` at `0x18017a589`
- `KERNEL32!FlushInstructionCache` at `0x18017a5ec`
- `KERNEL32!FlushInstructionCache` at `0x18017a5ec`

## pseudocode

```c
void __fastcall EmitBufferManager::CommitBuffer(
        EmitBufferManager *this,
        unsigned __int8 *a2,
        __int64 a3,
        const unsigned __int8 *a4,
        unsigned int Size)
{
  __int64 v5; // r14
  EmitBufferManager *v6; // rdx
  unsigned int v7; // r15d
  char *v9; // rsi
  SIZE_T v10; // rbp
  SIZE_T v11; // r12
  rsize_t v12; // rdi
  CustomHeap::Heap *v13; // rax
  struct CustomHeap::Allocation *v14; // rdx
  char *v15; // rbx
  unsigned int v16[2]; // [rsp+30h] [rbp-68h] BYREF
  CustomHeap::Heap *v17; // [rsp+38h] [rbp-60h]
  SIZE_T dwSize; // [rsp+40h] [rbp-58h]
  LPCVOID lpBaseAddress; // [rsp+48h] [rbp-50h]

  v5 = *(_QWORD *)this;
  v6 = this;
  v7 = Size;
  v9 = (char *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + *(_QWORD *)(**(_QWORD **)this + 16LL));
  v10 = a3 + Size;
  lpBaseAddress = v9;
  dwSize = v10;
  while ( v10 )
  {
    v11 = 4096 - ((unsigned __int16)v9 & 0xFFFu);
    v12 = v11;
    v13 = (EmitBufferManager *)((char *)v6 + 24);
    v14 = *(struct CustomHeap::Allocation **)v5;
    v17 = v13;
    if ( v10 <= v11 )
      v12 = v10;
    if ( !CustomHeap::Heap::ProtectAllocationInternal(v13, v14, v9, 0x40u, v16, 0x10u) )
      return;
    v15 = v9;
    *(_QWORD *)v16 = v9;
    if ( v7 )
    {
      if ( v7 < (unsigned int)v11 )
        LODWORD(v11) = v7;
      memset_0(v9, 204, (unsigned int)v11);
      *(_QWORD *)(v5 + 8) += (unsigned int)v11;
      v9 += (unsigned int)v11;
      v10 -= (unsigned int)v11;
      v7 -= v11;
      v12 -= (unsigned int)v11;
      v15 = *(char **)v16;
    }
    if ( v12 )
    {
      memcpy_s(v9, (unsigned int)(*(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 + 8)), a4, v12);
      *(_QWORD *)(v5 + 8) += v12;
      v9 += v12;
      a4 += v12;
      v10 -= v12;
    }
    if ( !CustomHeap::Heap::ProtectAllocationInternal(
            v17,
            *(struct CustomHeap::Allocation **)v5,
            v15,
            0x10u,
            v16,
            0x40u) )
      return;
    v6 = this;
  }
  FlushInstructionCache(hProcess, lpBaseAddress, dwSize);
}

```

## disassembly

```asm
0x18017a4b8  mov     r11, rsp
0x18017a4bb  mov     [r11+20h], r9
0x18017a4bf  mov     [r11+18h], r8
0x18017a4c3  mov     [r11+10h], rdx
0x18017a4c7  mov     [r11+8], rcx
0x18017a4cb  push    rbx
0x18017a4cc  push    rbp
0x18017a4cd  push    rsi
0x18017a4ce  push    rdi
0x18017a4cf  push    r12
0x18017a4d1  push    r13
0x18017a4d3  push    r14
0x18017a4d5  push    r15
0x18017a4d7  sub     rsp, 58h
0x18017a4db  mov     r14, [rcx]
0x18017a4de  mov     rdx, rcx
0x18017a4e1  mov     r15d, dword ptr [rsp+98h+Size]
0x18017a4e9  mov     r13, r9
0x18017a4ec  mov     ebp, r15d
0x18017a4ef  mov     rax, [r14]
0x18017a4f2  mov     rsi, [rax+10h]
0x18017a4f6  add     rsi, [r14+8]
0x18017a4fa  add     rbp, r8
0x18017a4fd  mov     [rsp+98h+lpBaseAddress], rsi
0x18017a502  mov     [rsp+98h+dwSize], rbp
0x18017a507  test    rbp, rbp
0x18017a50a  jz      loc_18017A5DB
0x18017a510  mov     ecx, esi
0x18017a512  mov     [rsp+98h+var_70], 10h; unsigned int
0x18017a51a  and     ecx, 0FFFh
0x18017a520  mov     eax, 1000h
0x18017a525  sub     eax, ecx
0x18017a527  mov     r9d, 40h ; '@'; unsigned int
0x18017a52d  mov     r12d, eax
0x18017a530  lea     rcx, [rsp+98h+var_68]
0x18017a535  mov     edi, eax
0x18017a537  cmp     rbp, r12
0x18017a53a  lea     rax, [rdx+18h]
0x18017a53e  mov     [rsp+98h+var_78], rcx; unsigned int *
0x18017a543  mov     rdx, [r14]; struct CustomHeap::Allocation *
0x18017a546  mov     r8, rsi; char *
0x18017a549  mov     rcx, rax; this
0x18017a54c  mov     [rsp+98h+var_60], rax
0x18017a551  cmovbe  rdi, rbp
0x18017a555  call    ?ProtectAllocationInternal@Heap@CustomHeap@@AEAAHPEAUAllocation@2@PEADKPEAKK@Z; CustomHeap::Heap::ProtectAllocationInternal(CustomHeap::Allocation *,char *,ulong,ulong *,ulong)
0x18017a55a  test    eax, eax
0x18017a55c  jz      loc_18017A5F8
0x18017a562  mov     rbx, rsi
0x18017a565  mov     qword ptr [rsp+98h+var_68], rbx
0x18017a56a  test    r15d, r15d
0x18017a56d  jnz     loc_18017A60A
0x18017a573  test    rdi, rdi
0x18017a576  jz      short loc_18017A5A2
0x18017a578  mov     edx, [r14+10h]
0x18017a57c  mov     r9, rdi; SourceSize
0x18017a57f  sub     edx, [r14+8]; DestinationSize
0x18017a583  mov     r8, r13; Source
0x18017a586  mov     rcx, rsi; Destination
0x18017a589  call    cs:__imp_memcpy_s
0x18017a590  nop     dword ptr [rax+rax+00h]
0x18017a595  add     [r14+8], rdi
0x18017a599  add     rsi, rdi
0x18017a59c  add     r13, rdi
0x18017a59f  sub     rbp, rdi
0x18017a5a2  mov     rdx, [r14]; struct CustomHeap::Allocation *
0x18017a5a5  lea     rax, [rsp+98h+var_68]
0x18017a5aa  mov     rcx, [rsp+98h+var_60]; this
0x18017a5af  mov     r9d, 10h; unsigned int
0x18017a5b5  mov     [rsp+98h+var_70], 40h ; '@'; unsigned int
0x18017a5bd  mov     r8, rbx; char *
0x18017a5c0  mov     [rsp+98h+var_78], rax; unsigned int *
0x18017a5c5  call    ?ProtectAllocationInternal@Heap@CustomHeap@@AEAAHPEAUAllocation@2@PEADKPEAKK@Z; CustomHeap::Heap::ProtectAllocationInternal(CustomHeap::Allocation *,char *,ulong,ulong *,ulong)
0x18017a5ca  test    eax, eax
0x18017a5cc  jz      short loc_18017A5F8
0x18017a5ce  mov     rdx, [rsp+98h+arg_0]
0x18017a5d6  jmp     loc_18017A507
0x18017a5db  mov     r8, [rsp+98h+dwSize]; dwSize
0x18017a5e0  mov     rdx, [rsp+98h+lpBaseAddress]; lpBaseAddress
0x18017a5e5  mov     rcx, cs:hProcess; hProcess
0x18017a5ec  call    cs:__imp_FlushInstructionCache
0x18017a5f3  nop     dword ptr [rax+rax+00h]
0x18017a5f8  add     rsp, 58h
0x18017a5fc  pop     r15
0x18017a5fe  pop     r14
0x18017a600  pop     r13
0x18017a602  pop     r12
0x18017a604  pop     rdi
0x18017a605  pop     rsi
0x18017a606  pop     rbp
0x18017a607  pop     rbx
0x18017a608  retn
0x18017a60a  cmp     r15d, r12d
0x18017a60d  mov     edx, 0CCh; Val
0x18017a612  mov     rcx, rsi; void *
0x18017a615  cmovb   r12d, r15d
0x18017a619  mov     r8d, r12d; Size
0x18017a61c  mov     ebx, r12d
0x18017a61f  call    memset_0
0x18017a624  add     [r14+8], rbx
0x18017a628  add     rsi, rbx
0x18017a62b  sub     rbp, rbx
0x18017a62e  sub     r15d, r12d
0x18017a631  sub     rdi, rbx
0x18017a634  mov     rbx, qword ptr [rsp+98h+var_68]
0x18017a639  jmp     loc_18017A573
```
