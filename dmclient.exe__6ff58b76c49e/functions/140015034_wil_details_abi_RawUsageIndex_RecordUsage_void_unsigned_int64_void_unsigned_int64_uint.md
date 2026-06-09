# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140015034`
- end: `0x1400151dd`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140013290`
- `0x140014f30`
- `0x140014f64`

## callees

- `0x140015034`
- `0x1400151e4`
- `0x140016b54`
- `0x140016bbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001514d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015180`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001514d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015180`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001515b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001518e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001515b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001518e`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebp
  void *v9; // rsi
  unsigned __int64 v12; // rdx
  _QWORD *v13; // r14
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rsi
  __int64 v18; // rdi
  void *v19; // rbp
  HANDLE ProcessHeap; // rax
  void *v21; // rdi
  void *v22; // rsi
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int128 v25; // [rsp+30h] [rbp-68h] BYREF
  __int128 v26; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a6;
  v9 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, a2, a3, a4, a5, a6) )
    return 1;
  v12 = a3 + a5 + 32;
  v13 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v12);
  }
  else
  {
    v25 = 0;
    v26 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v25, v12 + 10) )
    {
      v17 = v25;
      v18 = v26 - v25;
      if ( (_QWORD)v26 - (_QWORD)v25 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(retaddr, v14, v15, v16);
      v19 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v19 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
      *v13 = v17;
      *((_QWORD *)this + 5) = v18 + v17;
      v21 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v17 = 0;
      *(_WORD *)(v17 + 2) = *(_WORD *)this;
      *(_WORD *)(v17 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v17 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v17 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v17 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v22 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v26 + 1);
      if ( v22 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v22);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v21 = (void *)*((_QWORD *)&v26 + 1);
    }
    if ( v21 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v21);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x140015034  mov     [rsp+Buf1], rdx
0x140015039  push    rbx
0x14001503a  push    rbp
0x14001503b  push    rsi
0x14001503c  push    rdi
0x14001503d  push    r12
0x14001503f  push    r13
0x140015041  push    r14
0x140015043  push    r15
0x140015045  sub     rsp, 58h
0x140015049  mov     ebp, [rsp+98h+arg_28]
0x140015050  mov     r13, r9
0x140015053  mov     r12, [rsp+98h+arg_20]
0x14001505b  mov     r15, r8
0x14001505e  mov     [rsp+98h+var_70], ebp; unsigned int
0x140015062  mov     rsi, rdx
0x140015065  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14001506a  mov     rbx, rcx
0x14001506d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140015072  test    al, al
0x140015074  jz      short loc_14001507D
0x140015076  mov     al, 1
0x140015078  jmp     loc_1400151BE
0x14001507d  lea     rdx, [r12+20h]
0x140015082  add     rdx, r15; unsigned __int64
0x140015085  lea     r14, [rbx+18h]
0x140015089  cmp     qword ptr [r14], 0
0x14001508d  jnz     loc_140015196
0x140015093  xorps   xmm0, xmm0
0x140015096  lea     rcx, [rsp+98h+var_68]; this
0x14001509b  xorps   xmm1, xmm1
0x14001509e  add     rdx, 0Ah; unsigned __int64
0x1400150a2  movdqu  [rsp+98h+var_68], xmm0
0x1400150a8  movdqu  [rsp+98h+var_58], xmm1
0x1400150ae  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400150b3  test    al, al
0x1400150b5  jz      loc_140015176
0x1400150bb  mov     rdi, qword ptr [rsp+98h+var_58]
0x1400150c0  mov     rsi, qword ptr [rsp+98h+var_68]
0x1400150c5  sub     rdi, rsi
0x1400150c8  cmp     rdi, 0Ah
0x1400150cc  jb      loc_1400151CF
0x1400150d2  mov     rbp, [rbx+30h]
0x1400150d6  mov     qword ptr [rbx+30h], 0
0x1400150de  test    rbp, rbp
0x1400150e1  jz      short loc_1400150F7
0x1400150e3  call    cs:__imp_GetProcessHeap
0x1400150e9  mov     r8, rbp; lpMem
0x1400150ec  xor     edx, edx; dwFlags
0x1400150ee  mov     rcx, rax; hHeap
0x1400150f1  call    cs:__imp_HeapFree
0x1400150f7  mov     [r14], rsi
0x1400150fa  lea     rax, [rdi+rsi]
0x1400150fe  mov     [rbx+28h], rax
0x140015102  xor     edi, edi
0x140015104  xor     eax, eax
0x140015106  mov     byte ptr [rbx+39h], 0
0x14001510a  mov     [rsi], ax
0x14001510d  movzx   eax, word ptr [rbx]
0x140015110  mov     [rsi+2], ax
0x140015114  movzx   eax, word ptr [rbx+2]
0x140015118  mov     [rsi+4], ax
0x14001511c  mov     al, [rbx+4]
0x14001511f  mov     [rsi+8], al
0x140015122  movzx   eax, word ptr [rbx+6]
0x140015126  mov     [rsi+6], ax
0x14001512a  mov     al, [rbx+8]
0x14001512d  mov     [rsi+9], al
0x140015130  mov     rax, [r14]
0x140015133  add     rax, 0Ah
0x140015137  mov     [rbx+20h], rax
0x14001513b  mov     rsi, [rbx+30h]
0x14001513f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140015144  mov     [rbx+30h], rax
0x140015148  test    rsi, rsi
0x14001514b  jz      short loc_140015161
0x14001514d  call    cs:__imp_GetProcessHeap
0x140015153  mov     r8, rsi; lpMem
0x140015156  xor     edx, edx; dwFlags
0x140015158  mov     rcx, rax; hHeap
0x14001515b  call    cs:__imp_HeapFree
0x140015161  mov     rsi, [rsp+98h+Buf1]
0x140015169  mov     ebp, [rsp+98h+arg_28]
0x140015170  mov     byte ptr [rbx+3Ah], 1
0x140015174  jmp     short loc_14001517B
0x140015176  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14001517b  test    rdi, rdi
0x14001517e  jz      short loc_1400151A4
0x140015180  call    cs:__imp_GetProcessHeap
0x140015186  mov     r8, rdi; lpMem
0x140015189  xor     edx, edx; dwFlags
0x14001518b  mov     rcx, rax; hHeap
0x14001518e  call    cs:__imp_HeapFree
0x140015194  jmp     short loc_1400151A4
0x140015196  cmp     byte ptr [rbx+3Ah], 0
0x14001519a  jz      short loc_1400151A4
0x14001519c  mov     rcx, r14; this
0x14001519f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400151a4  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400151a8  mov     r9, r13; void *
0x1400151ab  mov     r8, r15; Size
0x1400151ae  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400151b3  mov     rdx, rsi; Buf1
0x1400151b6  mov     rcx, rbx; this
0x1400151b9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400151be  add     rsp, 58h
0x1400151c2  pop     r15
0x1400151c4  pop     r14
0x1400151c6  pop     r13
0x1400151c8  pop     r12
0x1400151ca  pop     rdi
0x1400151cb  pop     rsi
0x1400151cc  pop     rbp
0x1400151cd  pop     rbx
0x1400151ce  retn
0x1400151cf  mov     rcx, [rsp+98h]; this
0x1400151d7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
