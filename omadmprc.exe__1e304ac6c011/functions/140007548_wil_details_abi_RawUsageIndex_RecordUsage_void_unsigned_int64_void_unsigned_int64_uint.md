# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140007548`
- end: `0x14000767e`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `310`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140004180`
- `0x140007434`
- `0x14000746c`

## callees

- `0x140007548`
- `0x140007684`
- `0x140008614`
- `0x14000a33c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007608`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007638`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007608`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007638`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned __int64 v11; // rdx
  void *v12; // r14
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  void *v16[2]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v17; // [rsp+40h] [rbp-58h]

  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, Buf1, Size, a4, a5, a6) )
    return 1;
  v11 = Size + a5 + 32;
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v11);
  }
  else
  {
    *(_OWORD *)v16 = 0;
    v17 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v16, v11 + 10) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(this, v16[0], 0, v17 - (unsigned __int64)v16[0]);
      v12 = (void *)*((_QWORD *)this + 6);
      v13 = 0;
      *((_QWORD *)this + 6) = *((_QWORD *)&v17 + 1);
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v13 = (void *)*((_QWORD *)&v17 + 1);
    }
    if ( v13 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v13);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, Buf1, Size, a4, a5, a6);
}

```

## disassembly

```asm
0x140007548  push    rbx
0x14000754a  push    rbp
0x14000754b  push    rsi
0x14000754c  push    rdi
0x14000754d  push    r12
0x14000754f  push    r13
0x140007551  push    r14
0x140007553  push    r15
0x140007555  sub     rsp, 58h
0x140007559  mov     r13d, [rsp+98h+arg_28]
0x140007561  mov     r15, r9
0x140007564  mov     rbp, [rsp+98h+arg_20]
0x14000756c  mov     rsi, r8
0x14000756f  mov     [rsp+98h+var_70], r13d; unsigned int
0x140007574  mov     r12, rdx
0x140007577  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x14000757c  mov     rbx, rcx
0x14000757f  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140007584  test    al, al
0x140007586  jz      short loc_14000758F
0x140007588  mov     al, 1
0x14000758a  jmp     loc_14000766C
0x14000758f  lea     rdx, [rbp+20h]
0x140007593  add     rdx, rsi; unsigned __int64
0x140007596  lea     rcx, [rbx+18h]; this
0x14000759a  cmp     qword ptr [rcx], 0
0x14000759e  jnz     loc_140007646
0x1400075a4  xorps   xmm0, xmm0
0x1400075a7  lea     rcx, [rsp+98h+var_68]; this
0x1400075ac  xorps   xmm1, xmm1
0x1400075af  add     rdx, 0Ah; unsigned __int64
0x1400075b3  movdqu  xmmword ptr [rsp+98h+var_68], xmm0
0x1400075b9  movdqu  [rsp+98h+var_58], xmm1
0x1400075bf  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400075c4  test    al, al
0x1400075c6  jz      short loc_14000761A
0x1400075c8  mov     rdx, [rsp+98h+var_68]; void *
0x1400075cd  xor     r8d, r8d; unsigned __int64
0x1400075d0  mov     r9, qword ptr [rsp+98h+var_58]
0x1400075d5  mov     rcx, rbx; this
0x1400075d8  sub     r9, rdx; unsigned __int64
0x1400075db  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400075e0  mov     r14, [rbx+30h]
0x1400075e4  xor     edi, edi
0x1400075e6  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1400075eb  mov     [rbx+30h], rax
0x1400075ef  test    r14, r14
0x1400075f2  jz      short loc_140007614
0x1400075f4  call    cs:__imp_GetProcessHeap
0x1400075fb  nop     dword ptr [rax+rax+00h]
0x140007600  mov     r8, r14; lpMem
0x140007603  xor     edx, edx; dwFlags
0x140007605  mov     rcx, rax; hHeap
0x140007608  call    cs:__imp_HeapFree
0x14000760f  nop     dword ptr [rax+rax+00h]
0x140007614  mov     byte ptr [rbx+3Ah], 1
0x140007618  jmp     short loc_14000761F
0x14000761a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000761f  test    rdi, rdi
0x140007622  jz      short loc_140007651
0x140007624  call    cs:__imp_GetProcessHeap
0x14000762b  nop     dword ptr [rax+rax+00h]
0x140007630  mov     r8, rdi; lpMem
0x140007633  xor     edx, edx; dwFlags
0x140007635  mov     rcx, rax; hHeap
0x140007638  call    cs:__imp_HeapFree
0x14000763f  nop     dword ptr [rax+rax+00h]
0x140007644  jmp     short loc_140007651
0x140007646  cmp     byte ptr [rbx+3Ah], 0
0x14000764a  jz      short loc_140007651
0x14000764c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007651  mov     [rsp+98h+var_70], r13d; unsigned int
0x140007656  mov     r9, r15; void *
0x140007659  mov     r8, rsi; Size
0x14000765c  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x140007661  mov     rdx, r12; Buf1
0x140007664  mov     rcx, rbx; this
0x140007667  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000766c  add     rsp, 58h
0x140007670  pop     r15
0x140007672  pop     r14
0x140007674  pop     r13
0x140007676  pop     r12
0x140007678  pop     rdi
0x140007679  pop     rsi
0x14000767a  pop     rbp
0x14000767b  pop     rbx
0x14000767c  retn
```
