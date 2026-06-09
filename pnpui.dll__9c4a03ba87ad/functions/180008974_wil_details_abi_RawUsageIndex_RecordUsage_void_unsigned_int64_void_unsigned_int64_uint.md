# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008974`
- end: `0x180008b1d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004c80`
- `0x180008874`
- `0x1800088a8`

## callees

- `0x180008974`
- `0x180008b24`
- `0x18000a598`
- `0x18000a5e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ace`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ace`

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
0x180008974  mov     [rsp+Buf1], rdx
0x180008979  push    rbx
0x18000897a  push    rbp
0x18000897b  push    rsi
0x18000897c  push    rdi
0x18000897d  push    r12
0x18000897f  push    r13
0x180008981  push    r14
0x180008983  push    r15
0x180008985  sub     rsp, 58h
0x180008989  mov     ebp, [rsp+98h+arg_28]
0x180008990  mov     r13, r9
0x180008993  mov     r12, [rsp+98h+arg_20]
0x18000899b  mov     r15, r8
0x18000899e  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800089a2  mov     rsi, rdx
0x1800089a5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800089aa  mov     rbx, rcx
0x1800089ad  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800089b2  test    al, al
0x1800089b4  jz      short loc_1800089BD
0x1800089b6  mov     al, 1
0x1800089b8  jmp     loc_180008AFE
0x1800089bd  lea     rdx, [r12+20h]
0x1800089c2  add     rdx, r15; unsigned __int64
0x1800089c5  lea     r14, [rbx+18h]
0x1800089c9  cmp     qword ptr [r14], 0
0x1800089cd  jnz     loc_180008AD6
0x1800089d3  xorps   xmm0, xmm0
0x1800089d6  lea     rcx, [rsp+98h+var_68]; this
0x1800089db  xorps   xmm1, xmm1
0x1800089de  add     rdx, 0Ah; unsigned __int64
0x1800089e2  movdqu  [rsp+98h+var_68], xmm0
0x1800089e8  movdqu  [rsp+98h+var_58], xmm1
0x1800089ee  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800089f3  test    al, al
0x1800089f5  jz      loc_180008AB6
0x1800089fb  mov     rdi, qword ptr [rsp+98h+var_58]
0x180008a00  mov     rsi, qword ptr [rsp+98h+var_68]
0x180008a05  sub     rdi, rsi
0x180008a08  cmp     rdi, 0Ah
0x180008a0c  jb      loc_180008B0F
0x180008a12  mov     rbp, [rbx+30h]
0x180008a16  mov     qword ptr [rbx+30h], 0
0x180008a1e  test    rbp, rbp
0x180008a21  jz      short loc_180008A37
0x180008a23  call    cs:__imp_GetProcessHeap
0x180008a29  mov     r8, rbp; lpMem
0x180008a2c  xor     edx, edx; dwFlags
0x180008a2e  mov     rcx, rax; hHeap
0x180008a31  call    cs:__imp_HeapFree
0x180008a37  mov     [r14], rsi
0x180008a3a  lea     rax, [rdi+rsi]
0x180008a3e  mov     [rbx+28h], rax
0x180008a42  xor     edi, edi
0x180008a44  xor     eax, eax
0x180008a46  mov     byte ptr [rbx+39h], 0
0x180008a4a  mov     [rsi], ax
0x180008a4d  movzx   eax, word ptr [rbx]
0x180008a50  mov     [rsi+2], ax
0x180008a54  movzx   eax, word ptr [rbx+2]
0x180008a58  mov     [rsi+4], ax
0x180008a5c  mov     al, [rbx+4]
0x180008a5f  mov     [rsi+8], al
0x180008a62  movzx   eax, word ptr [rbx+6]
0x180008a66  mov     [rsi+6], ax
0x180008a6a  mov     al, [rbx+8]
0x180008a6d  mov     [rsi+9], al
0x180008a70  mov     rax, [r14]
0x180008a73  add     rax, 0Ah
0x180008a77  mov     [rbx+20h], rax
0x180008a7b  mov     rsi, [rbx+30h]
0x180008a7f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180008a84  mov     [rbx+30h], rax
0x180008a88  test    rsi, rsi
0x180008a8b  jz      short loc_180008AA1
0x180008a8d  call    cs:__imp_GetProcessHeap
0x180008a93  mov     r8, rsi; lpMem
0x180008a96  xor     edx, edx; dwFlags
0x180008a98  mov     rcx, rax; hHeap
0x180008a9b  call    cs:__imp_HeapFree
0x180008aa1  mov     rsi, [rsp+98h+Buf1]
0x180008aa9  mov     ebp, [rsp+98h+arg_28]
0x180008ab0  mov     byte ptr [rbx+3Ah], 1
0x180008ab4  jmp     short loc_180008ABB
0x180008ab6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180008abb  test    rdi, rdi
0x180008abe  jz      short loc_180008AE4
0x180008ac0  call    cs:__imp_GetProcessHeap
0x180008ac6  mov     r8, rdi; lpMem
0x180008ac9  xor     edx, edx; dwFlags
0x180008acb  mov     rcx, rax; hHeap
0x180008ace  call    cs:__imp_HeapFree
0x180008ad4  jmp     short loc_180008AE4
0x180008ad6  cmp     byte ptr [rbx+3Ah], 0
0x180008ada  jz      short loc_180008AE4
0x180008adc  mov     rcx, r14; this
0x180008adf  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008ae4  mov     [rsp+98h+var_70], ebp; unsigned int
0x180008ae8  mov     r9, r13; void *
0x180008aeb  mov     r8, r15; Size
0x180008aee  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180008af3  mov     rdx, rsi; Buf1
0x180008af6  mov     rcx, rbx; this
0x180008af9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180008afe  add     rsp, 58h
0x180008b02  pop     r15
0x180008b04  pop     r14
0x180008b06  pop     r13
0x180008b08  pop     r12
0x180008b0a  pop     rdi
0x180008b0b  pop     rsi
0x180008b0c  pop     rbp
0x180008b0d  pop     rbx
0x180008b0e  retn
0x180008b0f  mov     rcx, [rsp+98h]; this
0x180008b17  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
