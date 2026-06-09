# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000f878`
- end: `0x18000fa21`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007c50`
- `0x18000f774`
- `0x18000f7a8`

## callees

- `0x18000f878`
- `0x18000fa28`
- `0x180011e20`
- `0x1800124ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f935`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f99f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f935`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f99f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f991`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f991`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9c4`

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
0x18000f878  mov     [rsp+Buf1], rdx
0x18000f87d  push    rbx
0x18000f87e  push    rbp
0x18000f87f  push    rsi
0x18000f880  push    rdi
0x18000f881  push    r12
0x18000f883  push    r13
0x18000f885  push    r14
0x18000f887  push    r15
0x18000f889  sub     rsp, 58h
0x18000f88d  mov     ebp, [rsp+98h+arg_28]
0x18000f894  mov     r13, r9
0x18000f897  mov     r12, [rsp+98h+arg_20]
0x18000f89f  mov     r15, r8
0x18000f8a2  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000f8a6  mov     rsi, rdx
0x18000f8a9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000f8ae  mov     rbx, rcx
0x18000f8b1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000f8b6  test    al, al
0x18000f8b8  jz      short loc_18000F8C1
0x18000f8ba  mov     al, 1
0x18000f8bc  jmp     loc_18000FA02
0x18000f8c1  lea     rdx, [r12+20h]
0x18000f8c6  add     rdx, r15; unsigned __int64
0x18000f8c9  lea     r14, [rbx+18h]
0x18000f8cd  cmp     qword ptr [r14], 0
0x18000f8d1  jnz     loc_18000F9DA
0x18000f8d7  xorps   xmm0, xmm0
0x18000f8da  lea     rcx, [rsp+98h+var_68]; this
0x18000f8df  xorps   xmm1, xmm1
0x18000f8e2  add     rdx, 0Ah; unsigned __int64
0x18000f8e6  movdqu  [rsp+98h+var_68], xmm0
0x18000f8ec  movdqu  [rsp+98h+var_58], xmm1
0x18000f8f2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f8f7  test    al, al
0x18000f8f9  jz      loc_18000F9BA
0x18000f8ff  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000f904  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000f909  sub     rdi, rsi
0x18000f90c  cmp     rdi, 0Ah
0x18000f910  jb      loc_18000FA13
0x18000f916  mov     rbp, [rbx+30h]
0x18000f91a  mov     qword ptr [rbx+30h], 0
0x18000f922  test    rbp, rbp
0x18000f925  jz      short loc_18000F93B
0x18000f927  call    cs:__imp_GetProcessHeap
0x18000f92d  mov     r8, rbp; lpMem
0x18000f930  xor     edx, edx; dwFlags
0x18000f932  mov     rcx, rax; hHeap
0x18000f935  call    cs:__imp_HeapFree
0x18000f93b  mov     [r14], rsi
0x18000f93e  lea     rax, [rdi+rsi]
0x18000f942  mov     [rbx+28h], rax
0x18000f946  xor     edi, edi
0x18000f948  xor     eax, eax
0x18000f94a  mov     byte ptr [rbx+39h], 0
0x18000f94e  mov     [rsi], ax
0x18000f951  movzx   eax, word ptr [rbx]
0x18000f954  mov     [rsi+2], ax
0x18000f958  movzx   eax, word ptr [rbx+2]
0x18000f95c  mov     [rsi+4], ax
0x18000f960  mov     al, [rbx+4]
0x18000f963  mov     [rsi+8], al
0x18000f966  movzx   eax, word ptr [rbx+6]
0x18000f96a  mov     [rsi+6], ax
0x18000f96e  mov     al, [rbx+8]
0x18000f971  mov     [rsi+9], al
0x18000f974  mov     rax, [r14]
0x18000f977  add     rax, 0Ah
0x18000f97b  mov     [rbx+20h], rax
0x18000f97f  mov     rsi, [rbx+30h]
0x18000f983  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000f988  mov     [rbx+30h], rax
0x18000f98c  test    rsi, rsi
0x18000f98f  jz      short loc_18000F9A5
0x18000f991  call    cs:__imp_GetProcessHeap
0x18000f997  mov     r8, rsi; lpMem
0x18000f99a  xor     edx, edx; dwFlags
0x18000f99c  mov     rcx, rax; hHeap
0x18000f99f  call    cs:__imp_HeapFree
0x18000f9a5  mov     rsi, [rsp+98h+Buf1]
0x18000f9ad  mov     ebp, [rsp+98h+arg_28]
0x18000f9b4  mov     byte ptr [rbx+3Ah], 1
0x18000f9b8  jmp     short loc_18000F9BF
0x18000f9ba  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000f9bf  test    rdi, rdi
0x18000f9c2  jz      short loc_18000F9E8
0x18000f9c4  call    cs:__imp_GetProcessHeap
0x18000f9ca  mov     r8, rdi; lpMem
0x18000f9cd  xor     edx, edx; dwFlags
0x18000f9cf  mov     rcx, rax; hHeap
0x18000f9d2  call    cs:__imp_HeapFree
0x18000f9d8  jmp     short loc_18000F9E8
0x18000f9da  cmp     byte ptr [rbx+3Ah], 0
0x18000f9de  jz      short loc_18000F9E8
0x18000f9e0  mov     rcx, r14; this
0x18000f9e3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f9e8  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000f9ec  mov     r9, r13; void *
0x18000f9ef  mov     r8, r15; Size
0x18000f9f2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000f9f7  mov     rdx, rsi; Buf1
0x18000f9fa  mov     rcx, rbx; this
0x18000f9fd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000fa02  add     rsp, 58h
0x18000fa06  pop     r15
0x18000fa08  pop     r14
0x18000fa0a  pop     r13
0x18000fa0c  pop     r12
0x18000fa0e  pop     rdi
0x18000fa0f  pop     rsi
0x18000fa10  pop     rbp
0x18000fa11  pop     rbx
0x18000fa12  retn
0x18000fa13  mov     rcx, [rsp+98h]; this
0x18000fa1b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
