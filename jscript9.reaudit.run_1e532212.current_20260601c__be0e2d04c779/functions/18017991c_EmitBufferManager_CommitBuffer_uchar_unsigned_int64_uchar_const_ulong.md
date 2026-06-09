# EmitBufferManager::CommitBuffer(uchar *,unsigned __int64,uchar const *,ulong)

- ea: `0x18017991c`
- end: `0x180179a95`
- name: `?CommitBuffer@EmitBufferManager@@QEAAXPEAE_KPEBEK@Z`
- size: `377`
- prototype: `void(EmitBufferManager *__hidden this, unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003cde0`

## callees

- `0x1800a81fc`
- `0x18017991c`
- `0x1801c989b`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1801799ed`
- `msvcrt!memcpy_s` at `0x1801799ed`
- `KERNEL32!FlushInstructionCache` at `0x180179a4a`
- `KERNEL32!FlushInstructionCache` at `0x180179a4a`

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
0x18017991c  mov     r11, rsp
0x18017991f  mov     [r11+20h], r9
0x180179923  mov     [r11+18h], r8
0x180179927  mov     [r11+10h], rdx
0x18017992b  mov     [r11+8], rcx
0x18017992f  push    rbx
0x180179930  push    rbp
0x180179931  push    rsi
0x180179932  push    rdi
0x180179933  push    r12
0x180179935  push    r13
0x180179937  push    r14
0x180179939  push    r15
0x18017993b  sub     rsp, 58h
0x18017993f  mov     r14, [rcx]
0x180179942  mov     rdx, rcx
0x180179945  mov     r15d, dword ptr [rsp+98h+Size]
0x18017994d  mov     r13, r9
0x180179950  mov     ebp, r15d
0x180179953  mov     rax, [r14]
0x180179956  mov     rsi, [rax+10h]
0x18017995a  add     rsi, [r14+8]
0x18017995e  add     rbp, r8
0x180179961  mov     [rsp+98h+lpBaseAddress], rsi
0x180179966  mov     [rsp+98h+dwSize], rbp
0x18017996b  test    rbp, rbp
0x18017996e  jz      loc_180179A39
0x180179974  mov     ecx, esi
0x180179976  mov     [rsp+98h+var_70], 10h; unsigned int
0x18017997e  and     ecx, 0FFFh
0x180179984  mov     eax, 1000h
0x180179989  sub     eax, ecx
0x18017998b  mov     r9d, 40h ; '@'; unsigned int
0x180179991  mov     r12d, eax
0x180179994  lea     rcx, [rsp+98h+var_68]
0x180179999  mov     edi, eax
0x18017999b  cmp     rbp, r12
0x18017999e  lea     rax, [rdx+18h]
0x1801799a2  mov     [rsp+98h+var_78], rcx; unsigned int *
0x1801799a7  mov     rdx, [r14]; struct CustomHeap::Allocation *
0x1801799aa  mov     r8, rsi; char *
0x1801799ad  mov     rcx, rax; this
0x1801799b0  mov     [rsp+98h+var_60], rax
0x1801799b5  cmovbe  rdi, rbp
0x1801799b9  call    ?ProtectAllocationInternal@Heap@CustomHeap@@AEAAHPEAUAllocation@2@PEADKPEAKK@Z; CustomHeap::Heap::ProtectAllocationInternal(CustomHeap::Allocation *,char *,ulong,ulong *,ulong)
0x1801799be  test    eax, eax
0x1801799c0  jz      loc_180179A50
0x1801799c6  mov     rbx, rsi
0x1801799c9  mov     qword ptr [rsp+98h+var_68], rbx
0x1801799ce  test    r15d, r15d
0x1801799d1  jnz     loc_180179A61
0x1801799d7  test    rdi, rdi
0x1801799da  jz      short loc_180179A00
0x1801799dc  mov     edx, [r14+10h]
0x1801799e0  mov     r9, rdi; SourceSize
0x1801799e3  sub     edx, [r14+8]; DestinationSize
0x1801799e7  mov     r8, r13; Source
0x1801799ea  mov     rcx, rsi; Destination
0x1801799ed  call    cs:__imp_memcpy_s
0x1801799f3  add     [r14+8], rdi
0x1801799f7  add     rsi, rdi
0x1801799fa  add     r13, rdi
0x1801799fd  sub     rbp, rdi
0x180179a00  mov     rdx, [r14]; struct CustomHeap::Allocation *
0x180179a03  lea     rax, [rsp+98h+var_68]
0x180179a08  mov     rcx, [rsp+98h+var_60]; this
0x180179a0d  mov     r9d, 10h; unsigned int
0x180179a13  mov     [rsp+98h+var_70], 40h ; '@'; unsigned int
0x180179a1b  mov     r8, rbx; char *
0x180179a1e  mov     [rsp+98h+var_78], rax; unsigned int *
0x180179a23  call    ?ProtectAllocationInternal@Heap@CustomHeap@@AEAAHPEAUAllocation@2@PEADKPEAKK@Z; CustomHeap::Heap::ProtectAllocationInternal(CustomHeap::Allocation *,char *,ulong,ulong *,ulong)
0x180179a28  test    eax, eax
0x180179a2a  jz      short loc_180179A50
0x180179a2c  mov     rdx, [rsp+98h+arg_0]
0x180179a34  jmp     loc_18017996B
0x180179a39  mov     r8, [rsp+98h+dwSize]; dwSize
0x180179a3e  mov     rdx, [rsp+98h+lpBaseAddress]; lpBaseAddress
0x180179a43  mov     rcx, cs:hProcess; hProcess
0x180179a4a  call    cs:__imp_FlushInstructionCache
0x180179a50  add     rsp, 58h
0x180179a54  pop     r15
0x180179a56  pop     r14
0x180179a58  pop     r13
0x180179a5a  pop     r12
0x180179a5c  pop     rdi
0x180179a5d  pop     rsi
0x180179a5e  pop     rbp
0x180179a5f  pop     rbx
0x180179a60  retn
0x180179a61  cmp     r15d, r12d
0x180179a64  mov     edx, 0CCh; Val
0x180179a69  mov     rcx, rsi; void *
0x180179a6c  cmovb   r12d, r15d
0x180179a70  mov     r8d, r12d; Size
0x180179a73  mov     ebx, r12d
0x180179a76  call    memset_0
0x180179a7b  add     [r14+8], rbx
0x180179a7f  add     rsi, rbx
0x180179a82  sub     rbp, rbx
0x180179a85  sub     r15d, r12d
0x180179a88  sub     rdi, rbx
0x180179a8b  mov     rbx, qword ptr [rsp+98h+var_68]
0x180179a90  jmp     loc_1801799D7
```
