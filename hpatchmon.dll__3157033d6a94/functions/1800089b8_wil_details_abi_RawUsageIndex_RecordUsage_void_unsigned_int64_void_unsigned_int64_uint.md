# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800089b8`
- end: `0x180008b61`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004730`
- `0x1800088b4`
- `0x1800088e8`

## callees

- `0x1800089b8`
- `0x180008b68`
- `0x18000c5a8`
- `0x18000c80c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008adf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008adf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b04`

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
0x1800089b8  mov     [rsp+Buf1], rdx
0x1800089bd  push    rbx
0x1800089be  push    rbp
0x1800089bf  push    rsi
0x1800089c0  push    rdi
0x1800089c1  push    r12
0x1800089c3  push    r13
0x1800089c5  push    r14
0x1800089c7  push    r15
0x1800089c9  sub     rsp, 58h
0x1800089cd  mov     ebp, [rsp+98h+arg_28]
0x1800089d4  mov     r13, r9
0x1800089d7  mov     r12, [rsp+98h+arg_20]
0x1800089df  mov     r15, r8
0x1800089e2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800089e6  mov     rsi, rdx
0x1800089e9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800089ee  mov     rbx, rcx
0x1800089f1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800089f6  test    al, al
0x1800089f8  jz      short loc_180008A01
0x1800089fa  mov     al, 1
0x1800089fc  jmp     loc_180008B42
0x180008a01  lea     rdx, [r12+20h]
0x180008a06  add     rdx, r15; unsigned __int64
0x180008a09  lea     r14, [rbx+18h]
0x180008a0d  cmp     qword ptr [r14], 0
0x180008a11  jnz     loc_180008B1A
0x180008a17  xorps   xmm0, xmm0
0x180008a1a  lea     rcx, [rsp+98h+var_68]; this
0x180008a1f  xorps   xmm1, xmm1
0x180008a22  add     rdx, 0Ah; unsigned __int64
0x180008a26  movdqu  [rsp+98h+var_68], xmm0
0x180008a2c  movdqu  [rsp+98h+var_58], xmm1
0x180008a32  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008a37  test    al, al
0x180008a39  jz      loc_180008AFA
0x180008a3f  mov     rdi, qword ptr [rsp+98h+var_58]
0x180008a44  mov     rsi, qword ptr [rsp+98h+var_68]
0x180008a49  sub     rdi, rsi
0x180008a4c  cmp     rdi, 0Ah
0x180008a50  jb      loc_180008B53
0x180008a56  mov     rbp, [rbx+30h]
0x180008a5a  mov     qword ptr [rbx+30h], 0
0x180008a62  test    rbp, rbp
0x180008a65  jz      short loc_180008A7B
0x180008a67  call    cs:__imp_GetProcessHeap
0x180008a6d  mov     r8, rbp; lpMem
0x180008a70  xor     edx, edx; dwFlags
0x180008a72  mov     rcx, rax; hHeap
0x180008a75  call    cs:__imp_HeapFree
0x180008a7b  mov     [r14], rsi
0x180008a7e  lea     rax, [rdi+rsi]
0x180008a82  mov     [rbx+28h], rax
0x180008a86  xor     edi, edi
0x180008a88  xor     eax, eax
0x180008a8a  mov     byte ptr [rbx+39h], 0
0x180008a8e  mov     [rsi], ax
0x180008a91  movzx   eax, word ptr [rbx]
0x180008a94  mov     [rsi+2], ax
0x180008a98  movzx   eax, word ptr [rbx+2]
0x180008a9c  mov     [rsi+4], ax
0x180008aa0  mov     al, [rbx+4]
0x180008aa3  mov     [rsi+8], al
0x180008aa6  movzx   eax, word ptr [rbx+6]
0x180008aaa  mov     [rsi+6], ax
0x180008aae  mov     al, [rbx+8]
0x180008ab1  mov     [rsi+9], al
0x180008ab4  mov     rax, [r14]
0x180008ab7  add     rax, 0Ah
0x180008abb  mov     [rbx+20h], rax
0x180008abf  mov     rsi, [rbx+30h]
0x180008ac3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180008ac8  mov     [rbx+30h], rax
0x180008acc  test    rsi, rsi
0x180008acf  jz      short loc_180008AE5
0x180008ad1  call    cs:__imp_GetProcessHeap
0x180008ad7  mov     r8, rsi; lpMem
0x180008ada  xor     edx, edx; dwFlags
0x180008adc  mov     rcx, rax; hHeap
0x180008adf  call    cs:__imp_HeapFree
0x180008ae5  mov     rsi, [rsp+98h+Buf1]
0x180008aed  mov     ebp, [rsp+98h+arg_28]
0x180008af4  mov     byte ptr [rbx+3Ah], 1
0x180008af8  jmp     short loc_180008AFF
0x180008afa  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180008aff  test    rdi, rdi
0x180008b02  jz      short loc_180008B28
0x180008b04  call    cs:__imp_GetProcessHeap
0x180008b0a  mov     r8, rdi; lpMem
0x180008b0d  xor     edx, edx; dwFlags
0x180008b0f  mov     rcx, rax; hHeap
0x180008b12  call    cs:__imp_HeapFree
0x180008b18  jmp     short loc_180008B28
0x180008b1a  cmp     byte ptr [rbx+3Ah], 0
0x180008b1e  jz      short loc_180008B28
0x180008b20  mov     rcx, r14; this
0x180008b23  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008b28  mov     [rsp+98h+var_70], ebp; unsigned int
0x180008b2c  mov     r9, r13; void *
0x180008b2f  mov     r8, r15; Size
0x180008b32  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180008b37  mov     rdx, rsi; Buf1
0x180008b3a  mov     rcx, rbx; this
0x180008b3d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180008b42  add     rsp, 58h
0x180008b46  pop     r15
0x180008b48  pop     r14
0x180008b4a  pop     r13
0x180008b4c  pop     r12
0x180008b4e  pop     rdi
0x180008b4f  pop     rsi
0x180008b50  pop     rbp
0x180008b51  pop     rbx
0x180008b52  retn
0x180008b53  mov     rcx, [rsp+98h]; this
0x180008b5b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
