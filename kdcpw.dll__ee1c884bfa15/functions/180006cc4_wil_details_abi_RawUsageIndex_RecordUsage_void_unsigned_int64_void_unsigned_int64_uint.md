# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006cc4`
- end: `0x180006e6d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003900`
- `0x180006bc4`
- `0x180006bf8`

## callees

- `0x180006cc4`
- `0x180006e74`
- `0x180008ed8`
- `0x180008f3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006deb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006deb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ddd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ddd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e10`

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
0x180006cc4  mov     [rsp+Buf1], rdx
0x180006cc9  push    rbx
0x180006cca  push    rbp
0x180006ccb  push    rsi
0x180006ccc  push    rdi
0x180006ccd  push    r12
0x180006ccf  push    r13
0x180006cd1  push    r14
0x180006cd3  push    r15
0x180006cd5  sub     rsp, 58h
0x180006cd9  mov     ebp, [rsp+98h+arg_28]
0x180006ce0  mov     r13, r9
0x180006ce3  mov     r12, [rsp+98h+arg_20]
0x180006ceb  mov     r15, r8
0x180006cee  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006cf2  mov     rsi, rdx
0x180006cf5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006cfa  mov     rbx, rcx
0x180006cfd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006d02  test    al, al
0x180006d04  jz      short loc_180006D0D
0x180006d06  mov     al, 1
0x180006d08  jmp     loc_180006E4E
0x180006d0d  lea     rdx, [r12+20h]
0x180006d12  add     rdx, r15; unsigned __int64
0x180006d15  lea     r14, [rbx+18h]
0x180006d19  cmp     qword ptr [r14], 0
0x180006d1d  jnz     loc_180006E26
0x180006d23  xorps   xmm0, xmm0
0x180006d26  lea     rcx, [rsp+98h+var_68]; this
0x180006d2b  xorps   xmm1, xmm1
0x180006d2e  add     rdx, 0Ah; unsigned __int64
0x180006d32  movdqu  [rsp+98h+var_68], xmm0
0x180006d38  movdqu  [rsp+98h+var_58], xmm1
0x180006d3e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006d43  test    al, al
0x180006d45  jz      loc_180006E06
0x180006d4b  mov     rdi, qword ptr [rsp+98h+var_58]
0x180006d50  mov     rsi, qword ptr [rsp+98h+var_68]
0x180006d55  sub     rdi, rsi
0x180006d58  cmp     rdi, 0Ah
0x180006d5c  jb      loc_180006E5F
0x180006d62  mov     rbp, [rbx+30h]
0x180006d66  mov     qword ptr [rbx+30h], 0
0x180006d6e  test    rbp, rbp
0x180006d71  jz      short loc_180006D87
0x180006d73  call    cs:__imp_GetProcessHeap
0x180006d79  mov     r8, rbp; lpMem
0x180006d7c  xor     edx, edx; dwFlags
0x180006d7e  mov     rcx, rax; hHeap
0x180006d81  call    cs:__imp_HeapFree
0x180006d87  mov     [r14], rsi
0x180006d8a  lea     rax, [rdi+rsi]
0x180006d8e  mov     [rbx+28h], rax
0x180006d92  xor     edi, edi
0x180006d94  xor     eax, eax
0x180006d96  mov     byte ptr [rbx+39h], 0
0x180006d9a  mov     [rsi], ax
0x180006d9d  movzx   eax, word ptr [rbx]
0x180006da0  mov     [rsi+2], ax
0x180006da4  movzx   eax, word ptr [rbx+2]
0x180006da8  mov     [rsi+4], ax
0x180006dac  mov     al, [rbx+4]
0x180006daf  mov     [rsi+8], al
0x180006db2  movzx   eax, word ptr [rbx+6]
0x180006db6  mov     [rsi+6], ax
0x180006dba  mov     al, [rbx+8]
0x180006dbd  mov     [rsi+9], al
0x180006dc0  mov     rax, [r14]
0x180006dc3  add     rax, 0Ah
0x180006dc7  mov     [rbx+20h], rax
0x180006dcb  mov     rsi, [rbx+30h]
0x180006dcf  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180006dd4  mov     [rbx+30h], rax
0x180006dd8  test    rsi, rsi
0x180006ddb  jz      short loc_180006DF1
0x180006ddd  call    cs:__imp_GetProcessHeap
0x180006de3  mov     r8, rsi; lpMem
0x180006de6  xor     edx, edx; dwFlags
0x180006de8  mov     rcx, rax; hHeap
0x180006deb  call    cs:__imp_HeapFree
0x180006df1  mov     rsi, [rsp+98h+Buf1]
0x180006df9  mov     ebp, [rsp+98h+arg_28]
0x180006e00  mov     byte ptr [rbx+3Ah], 1
0x180006e04  jmp     short loc_180006E0B
0x180006e06  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180006e0b  test    rdi, rdi
0x180006e0e  jz      short loc_180006E34
0x180006e10  call    cs:__imp_GetProcessHeap
0x180006e16  mov     r8, rdi; lpMem
0x180006e19  xor     edx, edx; dwFlags
0x180006e1b  mov     rcx, rax; hHeap
0x180006e1e  call    cs:__imp_HeapFree
0x180006e24  jmp     short loc_180006E34
0x180006e26  cmp     byte ptr [rbx+3Ah], 0
0x180006e2a  jz      short loc_180006E34
0x180006e2c  mov     rcx, r14; this
0x180006e2f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006e34  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006e38  mov     r9, r13; void *
0x180006e3b  mov     r8, r15; Size
0x180006e3e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006e43  mov     rdx, rsi; Buf1
0x180006e46  mov     rcx, rbx; this
0x180006e49  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006e4e  add     rsp, 58h
0x180006e52  pop     r15
0x180006e54  pop     r14
0x180006e56  pop     r13
0x180006e58  pop     r12
0x180006e5a  pop     rdi
0x180006e5b  pop     rsi
0x180006e5c  pop     rbp
0x180006e5d  pop     rbx
0x180006e5e  retn
0x180006e5f  mov     rcx, [rsp+98h]; this
0x180006e67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
