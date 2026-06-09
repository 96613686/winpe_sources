# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005b30`
- end: `0x180005cd9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003030`
- `0x180005a30`
- `0x180005a64`

## callees

- `0x180005b30`
- `0x180005ce0`
- `0x180007858`
- `0x1800078bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c7c`

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
0x180005b30  mov     [rsp+Buf1], rdx
0x180005b35  push    rbx
0x180005b36  push    rbp
0x180005b37  push    rsi
0x180005b38  push    rdi
0x180005b39  push    r12
0x180005b3b  push    r13
0x180005b3d  push    r14
0x180005b3f  push    r15
0x180005b41  sub     rsp, 58h
0x180005b45  mov     ebp, [rsp+98h+arg_28]
0x180005b4c  mov     r13, r9
0x180005b4f  mov     r12, [rsp+98h+arg_20]
0x180005b57  mov     r15, r8
0x180005b5a  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005b5e  mov     rsi, rdx
0x180005b61  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005b66  mov     rbx, rcx
0x180005b69  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005b6e  test    al, al
0x180005b70  jz      short loc_180005B79
0x180005b72  mov     al, 1
0x180005b74  jmp     loc_180005CBA
0x180005b79  lea     rdx, [r12+20h]
0x180005b7e  add     rdx, r15; unsigned __int64
0x180005b81  lea     r14, [rbx+18h]
0x180005b85  cmp     qword ptr [r14], 0
0x180005b89  jnz     loc_180005C92
0x180005b8f  xorps   xmm0, xmm0
0x180005b92  lea     rcx, [rsp+98h+var_68]; this
0x180005b97  xorps   xmm1, xmm1
0x180005b9a  add     rdx, 0Ah; unsigned __int64
0x180005b9e  movdqu  [rsp+98h+var_68], xmm0
0x180005ba4  movdqu  [rsp+98h+var_58], xmm1
0x180005baa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005baf  test    al, al
0x180005bb1  jz      loc_180005C72
0x180005bb7  mov     rdi, qword ptr [rsp+98h+var_58]
0x180005bbc  mov     rsi, qword ptr [rsp+98h+var_68]
0x180005bc1  sub     rdi, rsi
0x180005bc4  cmp     rdi, 0Ah
0x180005bc8  jb      loc_180005CCB
0x180005bce  mov     rbp, [rbx+30h]
0x180005bd2  mov     qword ptr [rbx+30h], 0
0x180005bda  test    rbp, rbp
0x180005bdd  jz      short loc_180005BF3
0x180005bdf  call    cs:__imp_GetProcessHeap
0x180005be5  mov     r8, rbp; lpMem
0x180005be8  xor     edx, edx; dwFlags
0x180005bea  mov     rcx, rax; hHeap
0x180005bed  call    cs:__imp_HeapFree
0x180005bf3  mov     [r14], rsi
0x180005bf6  lea     rax, [rdi+rsi]
0x180005bfa  mov     [rbx+28h], rax
0x180005bfe  xor     edi, edi
0x180005c00  xor     eax, eax
0x180005c02  mov     byte ptr [rbx+39h], 0
0x180005c06  mov     [rsi], ax
0x180005c09  movzx   eax, word ptr [rbx]
0x180005c0c  mov     [rsi+2], ax
0x180005c10  movzx   eax, word ptr [rbx+2]
0x180005c14  mov     [rsi+4], ax
0x180005c18  mov     al, [rbx+4]
0x180005c1b  mov     [rsi+8], al
0x180005c1e  movzx   eax, word ptr [rbx+6]
0x180005c22  mov     [rsi+6], ax
0x180005c26  mov     al, [rbx+8]
0x180005c29  mov     [rsi+9], al
0x180005c2c  mov     rax, [r14]
0x180005c2f  add     rax, 0Ah
0x180005c33  mov     [rbx+20h], rax
0x180005c37  mov     rsi, [rbx+30h]
0x180005c3b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180005c40  mov     [rbx+30h], rax
0x180005c44  test    rsi, rsi
0x180005c47  jz      short loc_180005C5D
0x180005c49  call    cs:__imp_GetProcessHeap
0x180005c4f  mov     r8, rsi; lpMem
0x180005c52  xor     edx, edx; dwFlags
0x180005c54  mov     rcx, rax; hHeap
0x180005c57  call    cs:__imp_HeapFree
0x180005c5d  mov     rsi, [rsp+98h+Buf1]
0x180005c65  mov     ebp, [rsp+98h+arg_28]
0x180005c6c  mov     byte ptr [rbx+3Ah], 1
0x180005c70  jmp     short loc_180005C77
0x180005c72  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180005c77  test    rdi, rdi
0x180005c7a  jz      short loc_180005CA0
0x180005c7c  call    cs:__imp_GetProcessHeap
0x180005c82  mov     r8, rdi; lpMem
0x180005c85  xor     edx, edx; dwFlags
0x180005c87  mov     rcx, rax; hHeap
0x180005c8a  call    cs:__imp_HeapFree
0x180005c90  jmp     short loc_180005CA0
0x180005c92  cmp     byte ptr [rbx+3Ah], 0
0x180005c96  jz      short loc_180005CA0
0x180005c98  mov     rcx, r14; this
0x180005c9b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005ca0  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005ca4  mov     r9, r13; void *
0x180005ca7  mov     r8, r15; Size
0x180005caa  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005caf  mov     rdx, rsi; Buf1
0x180005cb2  mov     rcx, rbx; this
0x180005cb5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005cba  add     rsp, 58h
0x180005cbe  pop     r15
0x180005cc0  pop     r14
0x180005cc2  pop     r13
0x180005cc4  pop     r12
0x180005cc6  pop     rdi
0x180005cc7  pop     rsi
0x180005cc8  pop     rbp
0x180005cc9  pop     rbx
0x180005cca  retn
0x180005ccb  mov     rcx, [rsp+98h]; this
0x180005cd3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
