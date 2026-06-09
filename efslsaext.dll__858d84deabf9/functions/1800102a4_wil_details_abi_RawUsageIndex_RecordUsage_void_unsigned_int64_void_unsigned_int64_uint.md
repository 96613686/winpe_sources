# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800102a4`
- end: `0x18001044d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ce90`
- `0x1800101a4`
- `0x1800101d8`

## callees

- `0x180006318`
- `0x1800080a8`
- `0x1800102a4`
- `0x180010454`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010353`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010353`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010361`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010361`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103fe`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
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
0x1800102a4  mov     [rsp+Buf1], rdx
0x1800102a9  push    rbx
0x1800102aa  push    rbp
0x1800102ab  push    rsi
0x1800102ac  push    rdi
0x1800102ad  push    r12
0x1800102af  push    r13
0x1800102b1  push    r14
0x1800102b3  push    r15
0x1800102b5  sub     rsp, 58h
0x1800102b9  mov     ebp, [rsp+98h+arg_28]
0x1800102c0  mov     r13, r9
0x1800102c3  mov     r12, [rsp+98h+arg_20]
0x1800102cb  mov     r15, r8
0x1800102ce  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800102d2  mov     rsi, rdx
0x1800102d5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800102da  mov     rbx, rcx
0x1800102dd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800102e2  test    al, al
0x1800102e4  jz      short loc_1800102ED
0x1800102e6  mov     al, 1
0x1800102e8  jmp     loc_18001042E
0x1800102ed  lea     rdx, [r12+20h]
0x1800102f2  add     rdx, r15; unsigned __int64
0x1800102f5  lea     r14, [rbx+18h]
0x1800102f9  cmp     qword ptr [r14], 0
0x1800102fd  jnz     loc_180010406
0x180010303  xorps   xmm0, xmm0
0x180010306  lea     rcx, [rsp+98h+var_68]; this
0x18001030b  xorps   xmm1, xmm1
0x18001030e  add     rdx, 0Ah; unsigned __int64
0x180010312  movdqu  [rsp+98h+var_68], xmm0
0x180010318  movdqu  [rsp+98h+var_58], xmm1
0x18001031e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180010323  test    al, al
0x180010325  jz      loc_1800103E6
0x18001032b  mov     rdi, qword ptr [rsp+98h+var_58]
0x180010330  mov     rsi, qword ptr [rsp+98h+var_68]
0x180010335  sub     rdi, rsi
0x180010338  cmp     rdi, 0Ah
0x18001033c  jb      loc_18001043F
0x180010342  mov     rbp, [rbx+30h]
0x180010346  mov     qword ptr [rbx+30h], 0
0x18001034e  test    rbp, rbp
0x180010351  jz      short loc_180010367
0x180010353  call    cs:__imp_GetProcessHeap
0x180010359  mov     r8, rbp; lpMem
0x18001035c  xor     edx, edx; dwFlags
0x18001035e  mov     rcx, rax; hHeap
0x180010361  call    cs:__imp_HeapFree
0x180010367  mov     [r14], rsi
0x18001036a  lea     rax, [rdi+rsi]
0x18001036e  mov     [rbx+28h], rax
0x180010372  xor     edi, edi
0x180010374  xor     eax, eax
0x180010376  mov     byte ptr [rbx+39h], 0
0x18001037a  mov     [rsi], ax
0x18001037d  movzx   eax, word ptr [rbx]
0x180010380  mov     [rsi+2], ax
0x180010384  movzx   eax, word ptr [rbx+2]
0x180010388  mov     [rsi+4], ax
0x18001038c  mov     al, [rbx+4]
0x18001038f  mov     [rsi+8], al
0x180010392  movzx   eax, word ptr [rbx+6]
0x180010396  mov     [rsi+6], ax
0x18001039a  mov     al, [rbx+8]
0x18001039d  mov     [rsi+9], al
0x1800103a0  mov     rax, [r14]
0x1800103a3  add     rax, 0Ah
0x1800103a7  mov     [rbx+20h], rax
0x1800103ab  mov     rsi, [rbx+30h]
0x1800103af  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800103b4  mov     [rbx+30h], rax
0x1800103b8  test    rsi, rsi
0x1800103bb  jz      short loc_1800103D1
0x1800103bd  call    cs:__imp_GetProcessHeap
0x1800103c3  mov     r8, rsi; lpMem
0x1800103c6  xor     edx, edx; dwFlags
0x1800103c8  mov     rcx, rax; hHeap
0x1800103cb  call    cs:__imp_HeapFree
0x1800103d1  mov     rsi, [rsp+98h+Buf1]
0x1800103d9  mov     ebp, [rsp+98h+arg_28]
0x1800103e0  mov     byte ptr [rbx+3Ah], 1
0x1800103e4  jmp     short loc_1800103EB
0x1800103e6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800103eb  test    rdi, rdi
0x1800103ee  jz      short loc_180010414
0x1800103f0  call    cs:__imp_GetProcessHeap
0x1800103f6  mov     r8, rdi; lpMem
0x1800103f9  xor     edx, edx; dwFlags
0x1800103fb  mov     rcx, rax; hHeap
0x1800103fe  call    cs:__imp_HeapFree
0x180010404  jmp     short loc_180010414
0x180010406  cmp     byte ptr [rbx+3Ah], 0
0x18001040a  jz      short loc_180010414
0x18001040c  mov     rcx, r14; this
0x18001040f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180010414  mov     [rsp+98h+var_70], ebp; unsigned int
0x180010418  mov     r9, r13; void *
0x18001041b  mov     r8, r15; Size
0x18001041e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180010423  mov     rdx, rsi; Buf1
0x180010426  mov     rcx, rbx; this
0x180010429  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18001042e  add     rsp, 58h
0x180010432  pop     r15
0x180010434  pop     r14
0x180010436  pop     r13
0x180010438  pop     r12
0x18001043a  pop     rdi
0x18001043b  pop     rsi
0x18001043c  pop     rbp
0x18001043d  pop     rbx
0x18001043e  retn
0x18001043f  mov     rcx, [rsp+98h]; this
0x180010447  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
