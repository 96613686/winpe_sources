# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b558`
- end: `0x14000b701`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140006fe0`
- `0x14000b454`
- `0x14000b488`

## callees

- `0x14000b558`
- `0x14000b708`
- `0x140010108`
- `0x140010580`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b607`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b6a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b607`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b6a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b615`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b67f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b6b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b615`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b67f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b6b2`

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
0x14000b558  mov     [rsp+Buf1], rdx
0x14000b55d  push    rbx
0x14000b55e  push    rbp
0x14000b55f  push    rsi
0x14000b560  push    rdi
0x14000b561  push    r12
0x14000b563  push    r13
0x14000b565  push    r14
0x14000b567  push    r15
0x14000b569  sub     rsp, 58h
0x14000b56d  mov     ebp, [rsp+98h+arg_28]
0x14000b574  mov     r13, r9
0x14000b577  mov     r12, [rsp+98h+arg_20]
0x14000b57f  mov     r15, r8
0x14000b582  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b586  mov     rsi, rdx
0x14000b589  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b58e  mov     rbx, rcx
0x14000b591  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b596  test    al, al
0x14000b598  jz      short loc_14000B5A1
0x14000b59a  mov     al, 1
0x14000b59c  jmp     loc_14000B6E2
0x14000b5a1  lea     rdx, [r12+20h]
0x14000b5a6  add     rdx, r15; unsigned __int64
0x14000b5a9  lea     r14, [rbx+18h]
0x14000b5ad  cmp     qword ptr [r14], 0
0x14000b5b1  jnz     loc_14000B6BA
0x14000b5b7  xorps   xmm0, xmm0
0x14000b5ba  lea     rcx, [rsp+98h+var_68]; this
0x14000b5bf  xorps   xmm1, xmm1
0x14000b5c2  add     rdx, 0Ah; unsigned __int64
0x14000b5c6  movdqu  [rsp+98h+var_68], xmm0
0x14000b5cc  movdqu  [rsp+98h+var_58], xmm1
0x14000b5d2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b5d7  test    al, al
0x14000b5d9  jz      loc_14000B69A
0x14000b5df  mov     rdi, qword ptr [rsp+98h+var_58]
0x14000b5e4  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000b5e9  sub     rdi, rsi
0x14000b5ec  cmp     rdi, 0Ah
0x14000b5f0  jb      loc_14000B6F3
0x14000b5f6  mov     rbp, [rbx+30h]
0x14000b5fa  mov     qword ptr [rbx+30h], 0
0x14000b602  test    rbp, rbp
0x14000b605  jz      short loc_14000B61B
0x14000b607  call    cs:__imp_GetProcessHeap
0x14000b60d  mov     r8, rbp; lpMem
0x14000b610  xor     edx, edx; dwFlags
0x14000b612  mov     rcx, rax; hHeap
0x14000b615  call    cs:__imp_HeapFree
0x14000b61b  mov     [r14], rsi
0x14000b61e  lea     rax, [rdi+rsi]
0x14000b622  mov     [rbx+28h], rax
0x14000b626  xor     edi, edi
0x14000b628  xor     eax, eax
0x14000b62a  mov     byte ptr [rbx+39h], 0
0x14000b62e  mov     [rsi], ax
0x14000b631  movzx   eax, word ptr [rbx]
0x14000b634  mov     [rsi+2], ax
0x14000b638  movzx   eax, word ptr [rbx+2]
0x14000b63c  mov     [rsi+4], ax
0x14000b640  mov     al, [rbx+4]
0x14000b643  mov     [rsi+8], al
0x14000b646  movzx   eax, word ptr [rbx+6]
0x14000b64a  mov     [rsi+6], ax
0x14000b64e  mov     al, [rbx+8]
0x14000b651  mov     [rsi+9], al
0x14000b654  mov     rax, [r14]
0x14000b657  add     rax, 0Ah
0x14000b65b  mov     [rbx+20h], rax
0x14000b65f  mov     rsi, [rbx+30h]
0x14000b663  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000b668  mov     [rbx+30h], rax
0x14000b66c  test    rsi, rsi
0x14000b66f  jz      short loc_14000B685
0x14000b671  call    cs:__imp_GetProcessHeap
0x14000b677  mov     r8, rsi; lpMem
0x14000b67a  xor     edx, edx; dwFlags
0x14000b67c  mov     rcx, rax; hHeap
0x14000b67f  call    cs:__imp_HeapFree
0x14000b685  mov     rsi, [rsp+98h+Buf1]
0x14000b68d  mov     ebp, [rsp+98h+arg_28]
0x14000b694  mov     byte ptr [rbx+3Ah], 1
0x14000b698  jmp     short loc_14000B69F
0x14000b69a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000b69f  test    rdi, rdi
0x14000b6a2  jz      short loc_14000B6C8
0x14000b6a4  call    cs:__imp_GetProcessHeap
0x14000b6aa  mov     r8, rdi; lpMem
0x14000b6ad  xor     edx, edx; dwFlags
0x14000b6af  mov     rcx, rax; hHeap
0x14000b6b2  call    cs:__imp_HeapFree
0x14000b6b8  jmp     short loc_14000B6C8
0x14000b6ba  cmp     byte ptr [rbx+3Ah], 0
0x14000b6be  jz      short loc_14000B6C8
0x14000b6c0  mov     rcx, r14; this
0x14000b6c3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b6c8  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b6cc  mov     r9, r13; void *
0x14000b6cf  mov     r8, r15; Size
0x14000b6d2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b6d7  mov     rdx, rsi; Buf1
0x14000b6da  mov     rcx, rbx; this
0x14000b6dd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b6e2  add     rsp, 58h
0x14000b6e6  pop     r15
0x14000b6e8  pop     r14
0x14000b6ea  pop     r13
0x14000b6ec  pop     r12
0x14000b6ee  pop     rdi
0x14000b6ef  pop     rsi
0x14000b6f0  pop     rbp
0x14000b6f1  pop     rbx
0x14000b6f2  retn
0x14000b6f3  mov     rcx, [rsp+98h]; this
0x14000b6fb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
